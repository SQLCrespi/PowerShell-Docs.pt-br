---
title: Adicionando relatórios de erros não conclusivos ao cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a1531a-a92a-4606-9d54-c5df80d34f33
caps.latest.revision: 8
ms.openlocfilehash: a4426abec96cd922360aeef8c157b4e9f41a15b9
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71322865"
---
# <a name="adding-non-terminating-error-reporting-to-your-cmdlet"></a><span data-ttu-id="5fc85-102">Adicionar relatórios de erros de não encerramento ao seu cmdlet</span><span class="sxs-lookup"><span data-stu-id="5fc85-102">Adding Non-Terminating Error Reporting to Your Cmdlet</span></span>

<span data-ttu-id="5fc85-103">Os cmdlets podem relatar erros não conclusivos chamando o método [System. Management. Automation. cmdlet. WriteError][] e ainda continuam a operar no objeto de entrada atual ou em outros objetos de pipeline de entrada.</span><span class="sxs-lookup"><span data-stu-id="5fc85-103">Cmdlets can report nonterminating errors by calling the [System.Management.Automation.Cmdlet.WriteError][] method and still continue to operate on the current input object or on further incoming pipeline objects.</span></span>
<span data-ttu-id="5fc85-104">Esta seção explica como criar um cmdlet que relata erros não conclusivos de seus métodos de processamento de entrada.</span><span class="sxs-lookup"><span data-stu-id="5fc85-104">This section explains how to create a cmdlet that reports nonterminating errors from its input processing methods.</span></span>

<span data-ttu-id="5fc85-105">Para erros de não encerramento (bem como erros de encerramento), o cmdlet deve passar um objeto [System. Management. Automation. ErrorRecord][] identificando o erro.</span><span class="sxs-lookup"><span data-stu-id="5fc85-105">For nonterminating errors (as well as terminating errors), the cmdlet must pass an [System.Management.Automation.ErrorRecord][] object identifying the error.</span></span>
<span data-ttu-id="5fc85-106">Cada registro de erro é identificado por uma cadeia de caracteres exclusiva chamada "identificador de erro".</span><span class="sxs-lookup"><span data-stu-id="5fc85-106">Each error record is identified by a unique string called the "error identifier".</span></span>
<span data-ttu-id="5fc85-107">Além do identificador, a categoria de cada erro é especificada por constantes definidas por uma enumeração [System. Management. Automation. ErrorCategory][] .</span><span class="sxs-lookup"><span data-stu-id="5fc85-107">In addition to the identifier, the category of each error is specified by constants defined by a [System.Management.Automation.ErrorCategory][] enumeration.</span></span>
<span data-ttu-id="5fc85-108">O usuário pode exibir erros com base em sua categoria definindo a `$ErrorView` variável como "CategoryView".</span><span class="sxs-lookup"><span data-stu-id="5fc85-108">The user can view errors based on their category by setting the `$ErrorView` variable to "CategoryView".</span></span>

<span data-ttu-id="5fc85-109">Para obter mais informações sobre registros de erro, consulte [registros de erro do Windows PowerShell](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="5fc85-109">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="5fc85-110">Definindo o cmdlet</span><span class="sxs-lookup"><span data-stu-id="5fc85-110">Defining the Cmdlet</span></span>

<span data-ttu-id="5fc85-111">A primeira etapa na criação de cmdlet é sempre nomear o cmdlet e declarar a classe .NET que implementa o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5fc85-111">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span>
<span data-ttu-id="5fc85-112">Esse cmdlet recupera informações de processo, portanto, o nome do verbo escolhido aqui é "Get".</span><span class="sxs-lookup"><span data-stu-id="5fc85-112">This cmdlet retrieves process information, so the verb name chosen here is "Get".</span></span>
<span data-ttu-id="5fc85-113">(Quase qualquer tipo de cmdlet capaz de recuperar informações pode processar a entrada de linha de comando.) Para obter mais informações sobre verbos de cmdlet aprovados, consulte [nomes de verbo de cmdlet](approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="5fc85-113">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="5fc85-114">A seguir está a definição para esse cmdlet Get-proc.</span><span class="sxs-lookup"><span data-stu-id="5fc85-114">The following is the definition for this Get-Proc cmdlet.</span></span>
<span data-ttu-id="5fc85-115">Detalhes dessa definição são fornecidos na [criação do seu primeiro cmdlet](creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="5fc85-115">Details of this definition are given in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-parameters"></a><span data-ttu-id="5fc85-116">Definindo parâmetros</span><span class="sxs-lookup"><span data-stu-id="5fc85-116">Defining Parameters</span></span>

<span data-ttu-id="5fc85-117">Se necessário, o cmdlet deve definir parâmetros para processar a entrada.</span><span class="sxs-lookup"><span data-stu-id="5fc85-117">If necessary, your cmdlet must define parameters for processing input.</span></span>
<span data-ttu-id="5fc85-118">Esse cmdlet Get-proc define um parâmetro de **nome** conforme descrito em [adicionando parâmetros que processam a entrada de linha de comando](adding-parameters-that-process-command-line-input.md).</span><span class="sxs-lookup"><span data-stu-id="5fc85-118">This Get-Proc cmdlet defines a **Name** parameter as described in [Adding Parameters that Process Command-Line Input](adding-parameters-that-process-command-line-input.md).</span></span>

<span data-ttu-id="5fc85-119">Aqui está a declaração de parâmetro para o parâmetro **Name** deste cmdlet Get-proc.</span><span class="sxs-lookup"><span data-stu-id="5fc85-119">Here is the parameter declaration for the **Name** parameter of this Get-Proc cmdlet.</span></span>

```csharp
[Parameter(
           Position = 0,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true
)]
[ValidateNotNullOrEmpty]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;
```

```vb
<Parameter(Position:=0, ValueFromPipeline:=True, _
ValueFromPipelineByPropertyName:=True), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

## <a name="overriding-input-processing-methods"></a><span data-ttu-id="5fc85-120">Substituindo métodos de processamento de entrada</span><span class="sxs-lookup"><span data-stu-id="5fc85-120">Overriding Input Processing Methods</span></span>

<span data-ttu-id="5fc85-121">Todos os cmdlets devem substituir pelo menos um dos métodos de processamento de entrada fornecidos pela classe [System. Management. Automation. cmdlet][] .</span><span class="sxs-lookup"><span data-stu-id="5fc85-121">All cmdlets must override at least one of the input processing methods provided by the [System.Management.Automation.Cmdlet][] class.</span></span>
<span data-ttu-id="5fc85-122">Esses métodos são discutidos na [criação do seu primeiro cmdlet](creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="5fc85-122">These methods are discussed in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5fc85-123">Seu cmdlet deve tratar cada registro da maneira mais independente possível.</span><span class="sxs-lookup"><span data-stu-id="5fc85-123">Your cmdlet should handle each record as independently as possible.</span></span>

<span data-ttu-id="5fc85-124">Esse cmdlet Get-proc substitui o método [System. Management. Automation. cmdlet. ProcessRecord][] para manipular o parâmetro **Name** para a entrada fornecida pelo usuário ou um script.</span><span class="sxs-lookup"><span data-stu-id="5fc85-124">This Get-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord][] method to handle the **Name** parameter for input provided by the user or a script.</span></span>
<span data-ttu-id="5fc85-125">Esse método obterá os processos para cada nome de processo solicitado ou todos os processos, se nenhum nome for fornecido.</span><span class="sxs-lookup"><span data-stu-id="5fc85-125">This method will get the processes for each requested process name or all processes if no name is provided.</span></span>
<span data-ttu-id="5fc85-126">Os detalhes dessa substituição são fornecidos na [criação do seu primeiro cmdlet](creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="5fc85-126">Details of this override are given in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

### <a name="things-to-remember-when-reporting-errors"></a><span data-ttu-id="5fc85-127">Itens a serem lembrados ao relatar erros</span><span class="sxs-lookup"><span data-stu-id="5fc85-127">Things to Remember When Reporting Errors</span></span>

<span data-ttu-id="5fc85-128">O objeto [System. Management. Automation. ErrorRecord][] que o cmdlet passa ao gravar um erro requer uma exceção em seu núcleo.</span><span class="sxs-lookup"><span data-stu-id="5fc85-128">The [System.Management.Automation.ErrorRecord][] object that the cmdlet passes when writing an error requires an exception at its core.</span></span>
<span data-ttu-id="5fc85-129">Siga as diretrizes do .NET ao determinar a exceção a ser usada.</span><span class="sxs-lookup"><span data-stu-id="5fc85-129">Follow the .NET guidelines when determining the exception to use.</span></span>
<span data-ttu-id="5fc85-130">Basicamente, se o erro for semanticamente o mesmo que uma exceção existente, o cmdlet deverá usar ou derivar dessa exceção.</span><span class="sxs-lookup"><span data-stu-id="5fc85-130">Basically, if the error is semantically the same as an existing exception, the cmdlet should use or derive from that exception.</span></span>
<span data-ttu-id="5fc85-131">Caso contrário, ele deve derivar uma nova hierarquia de exceção ou exceção diretamente da classe [System. Exception][] .</span><span class="sxs-lookup"><span data-stu-id="5fc85-131">Otherwise, it should derive a new exception or exception hierarchy directly from the [System.Exception][] class.</span></span>

<span data-ttu-id="5fc85-132">Ao criar identificadores de erro (acessados por meio da propriedade FullyQualifiedErrorId da classe ErrorRecord), tenha em mente o seguinte.</span><span class="sxs-lookup"><span data-stu-id="5fc85-132">When creating error identifiers (accessed through the FullyQualifiedErrorId property of the ErrorRecord class) keep the following in mind.</span></span>

- <span data-ttu-id="5fc85-133">Use cadeias de caracteres destinadas a fins de diagnóstico para que, ao inspecionar o identificador totalmente qualificado, você possa determinar qual é o erro e de onde veio o erro.</span><span class="sxs-lookup"><span data-stu-id="5fc85-133">Use strings that are targeted for diagnostic purposes so that when inspecting the fully qualified identifier you can determine what the error is and where the error came from.</span></span>

- <span data-ttu-id="5fc85-134">Um identificador de erro totalmente qualificado bem formado pode ser o seguinte.</span><span class="sxs-lookup"><span data-stu-id="5fc85-134">A well formed fully qualified error identifier might be as follows.</span></span>

`CommandNotFoundException,Microsoft.PowerShell.Commands.GetCommandCommand`

<span data-ttu-id="5fc85-135">Observe que, no exemplo anterior, o identificador de erro (o primeiro token) designa o que é o erro e a parte restante indica de onde veio o erro.</span><span class="sxs-lookup"><span data-stu-id="5fc85-135">Notice that in the previous example, the error identifier (the first token) designates what the error is and the remaining part indicates where the error came from.</span></span>

- <span data-ttu-id="5fc85-136">Para cenários mais complexos, o identificador de erro pode ser um token separado por ponto que pode ser analisado na inspeção.</span><span class="sxs-lookup"><span data-stu-id="5fc85-136">For more complex scenarios, the error identifier can be a dot separated token that can be parsed on inspection.</span></span>
  <span data-ttu-id="5fc85-137">Isso permite uma ramificação demais nas partes do identificador de erro, bem como o identificador de erro e a categoria de erro.</span><span class="sxs-lookup"><span data-stu-id="5fc85-137">This allows you too branch on the parts of the error identifier as well as the error identifier and error category.</span></span>

<span data-ttu-id="5fc85-138">O cmdlet deve atribuir identificadores de erro específicos a caminhos de código diferentes.</span><span class="sxs-lookup"><span data-stu-id="5fc85-138">The cmdlet should assign specific error identifiers to different code paths.</span></span>
<span data-ttu-id="5fc85-139">Tenha em mente as seguintes informações para a atribuição de identificadores de erro:</span><span class="sxs-lookup"><span data-stu-id="5fc85-139">Keep the following information in mind for assignment of error identifiers:</span></span>

- <span data-ttu-id="5fc85-140">Um identificador de erro deve permanecer constante ao longo do ciclo de vida do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5fc85-140">An error identifier should remain constant throughout the cmdlet life cycle.</span></span>
  <span data-ttu-id="5fc85-141">Não altere a semântica de um identificador de erro entre as versões do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5fc85-141">Do not change the semantics of an error identifier between cmdlet versions.</span></span>

- <span data-ttu-id="5fc85-142">Use o texto para um identificador de erro que tersely corresponde ao erro que está sendo relatado.</span><span class="sxs-lookup"><span data-stu-id="5fc85-142">Use text for an error identifier that tersely corresponds to the error being reported.</span></span>
  <span data-ttu-id="5fc85-143">Não use espaço em branco ou pontuação.</span><span class="sxs-lookup"><span data-stu-id="5fc85-143">Do not use white space or punctuation.</span></span>

- <span data-ttu-id="5fc85-144">Faça com que o cmdlet gere apenas identificadores de erro que podem ser reproduzidos.</span><span class="sxs-lookup"><span data-stu-id="5fc85-144">Have your cmdlet generate only error identifiers that are reproducible.</span></span>
  <span data-ttu-id="5fc85-145">Por exemplo, ele não deve gerar um identificador que inclua um identificador de processo.</span><span class="sxs-lookup"><span data-stu-id="5fc85-145">For example, it should not generate an identifier that includes a process identifier.</span></span>
  <span data-ttu-id="5fc85-146">Os identificadores de erro são úteis para um usuário somente quando eles correspondem a identificadores que são vistos por outros usuários que estão tendo o mesmo problema.</span><span class="sxs-lookup"><span data-stu-id="5fc85-146">Error identifiers are useful to a user only when they correspond to identifiers that are seen by other users experiencing the same problem.</span></span>

<span data-ttu-id="5fc85-147">As exceções sem tratamento não são detectadas pelo PowerShell nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="5fc85-147">Unhandled exceptions are not caught by PowerShell in the following conditions:</span></span>

- <span data-ttu-id="5fc85-148">Se um cmdlet criar um novo thread e o código em execução nesse thread gerar uma exceção sem tratamento, o PowerShell não detectará o erro e encerrará o processo.</span><span class="sxs-lookup"><span data-stu-id="5fc85-148">If a cmdlet creates a new thread and code running in that thread throws an unhandled exception, PowerShell will not catch the error and will terminate the process.</span></span>

- <span data-ttu-id="5fc85-149">Se um objeto tiver código em seu destruidor ou métodos Dispose que causam uma exceção sem tratamento, o PowerShell não detectará o erro e encerrará o processo.</span><span class="sxs-lookup"><span data-stu-id="5fc85-149">If an object has code in its destructor or Dispose methods that causes an unhandled exception, PowerShell will not catch the error and will terminate the process.</span></span>

## <a name="reporting-nonterminating-errors"></a><span data-ttu-id="5fc85-150">Relatando erros de não encerramento</span><span class="sxs-lookup"><span data-stu-id="5fc85-150">Reporting Nonterminating Errors</span></span>

<span data-ttu-id="5fc85-151">Qualquer um dos métodos de processamento de entrada pode relatar um erro de não encerramento para o fluxo de saída usando o método [System. Management. Automation. cmdlet. WriteError][] .</span><span class="sxs-lookup"><span data-stu-id="5fc85-151">Any one of the input processing methods can report a nonterminating error to the output stream using the [System.Management.Automation.Cmdlet.WriteError][] method.</span></span>

<span data-ttu-id="5fc85-152">Aqui está um exemplo de código desse cmdlet Get-proc que ilustra a chamada para [System. Management. Automation. cmdlet. WriteError][] de dentro da substituição do método [System. Management. Automation. cmdlet. ProcessRecord][] .</span><span class="sxs-lookup"><span data-stu-id="5fc85-152">Here is a code example from this Get-Proc cmdlet that illustrates the call to [System.Management.Automation.Cmdlet.WriteError][] from within the override of the [System.Management.Automation.Cmdlet.ProcessRecord][] method.</span></span>
<span data-ttu-id="5fc85-153">Nesse caso, a chamada será feita se o cmdlet não encontrar um processo para um identificador de processo especificado.</span><span class="sxs-lookup"><span data-stu-id="5fc85-153">In this case, the call is made if the cmdlet cannot find a process for a specified process identifier.</span></span>

```csharp
protected override void ProcessRecord()
{
  // If no name parameter passed to cmdlet, get all processes.
  if (processNames == null)
  {
    WriteObject(Process.GetProcesses(), true);
  }
    else
    {
      // If a name parameter is passed to cmdlet, get and write
      // the associated processes.
      // Write a nonterminating error for failure to retrieve
      // a process.
      foreach (string name in processNames)
      {
        Process[] processes;

        try
        {
          processes = Process.GetProcessesByName(name);
        }
        catch (InvalidOperationException ex)
        {
          WriteError(new ErrorRecord(
                     ex,
                     "NameNotFound",
                     ErrorCategory.InvalidOperation,
                     name));
          continue;
        }

        WriteObject(processes, true);
      } // foreach (...
    } // else
  }
```

### <a name="things-to-remember-about-writing-nonterminating-errors"></a><span data-ttu-id="5fc85-154">Coisas a serem lembradas sobre a gravação de erros de não encerramento</span><span class="sxs-lookup"><span data-stu-id="5fc85-154">Things to Remember About Writing Nonterminating Errors</span></span>

<span data-ttu-id="5fc85-155">Para um erro de não encerramento, o cmdlet deve gerar um identificador de erro específico para cada objeto de entrada específico.</span><span class="sxs-lookup"><span data-stu-id="5fc85-155">For a nonterminating error, the cmdlet must generate a specific error identifier for each specific input object.</span></span>

<span data-ttu-id="5fc85-156">Geralmente, um cmdlet precisa modificar a ação do PowerShell produzida por um erro de não encerramento.</span><span class="sxs-lookup"><span data-stu-id="5fc85-156">A cmdlet frequently needs to modify the PowerShell action produced by a nonterminating error.</span></span>
<span data-ttu-id="5fc85-157">Isso pode fazer isso definindo os `ErrorAction` parâmetros e. `ErrorVariable`</span><span class="sxs-lookup"><span data-stu-id="5fc85-157">It can do this by defining the `ErrorAction` and `ErrorVariable` parameters.</span></span>
<span data-ttu-id="5fc85-158">Se definir o `ErrorAction` parâmetro, o cmdlet apresentará as opções de usuário [System. Management. Automation. preferência][], você também pode influenciar diretamente a ação definindo `$ErrorActionPreference` a variável.</span><span class="sxs-lookup"><span data-stu-id="5fc85-158">If defining the `ErrorAction` parameter, the cmdlet presents the user options [System.Management.Automation.ActionPreference][], you can also directly influence the action by setting the `$ErrorActionPreference` variable.</span></span>

<span data-ttu-id="5fc85-159">O cmdlet pode salvar erros não conclusivos em uma variável usando `ErrorVariable` o parâmetro, que não é afetado pela configuração de `ErrorAction`.</span><span class="sxs-lookup"><span data-stu-id="5fc85-159">The cmdlet can save nonterminating errors to a variable using the `ErrorVariable` parameter, which is not affected by the setting of `ErrorAction`.</span></span>
<span data-ttu-id="5fc85-160">As falhas podem ser acrescentadas a uma variável de erro existente adicionando um sinal de adição (+) à frente do nome da variável.</span><span class="sxs-lookup"><span data-stu-id="5fc85-160">Failures can be appended to an existing error variable by adding a plus sign (+) to the front of the variable name.</span></span>

## <a name="code-sample"></a><span data-ttu-id="5fc85-161">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="5fc85-161">Code Sample</span></span>

<span data-ttu-id="5fc85-162">Para obter o C# código de exemplo completo, consulte [exemplo de GetProcessSample04](./getprocesssample04-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5fc85-162">For the complete C# sample code, see [GetProcessSample04 Sample](./getprocesssample04-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="5fc85-163">Definir tipos de objeto e formatação</span><span class="sxs-lookup"><span data-stu-id="5fc85-163">Define Object Types and Formatting</span></span>

<span data-ttu-id="5fc85-164">O PowerShell passa informações entre os cmdlets usando objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="5fc85-164">PowerShell passes information between cmdlets using .NET objects.</span></span>
<span data-ttu-id="5fc85-165">Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou o cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5fc85-165">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span>
<span data-ttu-id="5fc85-166">Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span><span class="sxs-lookup"><span data-stu-id="5fc85-166">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="5fc85-167">Criando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="5fc85-167">Building the Cmdlet</span></span>

<span data-ttu-id="5fc85-168">Depois de implementar um cmdlet, você deve registrá-lo com o Windows PowerShell por meio de um snap-in do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fc85-168">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span>
<span data-ttu-id="5fc85-169">Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span><span class="sxs-lookup"><span data-stu-id="5fc85-169">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="5fc85-170">Testando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="5fc85-170">Testing the Cmdlet</span></span>

<span data-ttu-id="5fc85-171">Quando o cmdlet tiver sido registrado com o PowerShell, você poderá testá-lo executando-o na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="5fc85-171">When your cmdlet has been registered with PowerShell, you can test it by running it on the command line.</span></span>
<span data-ttu-id="5fc85-172">Vamos testar o cmdlet Get-proc de exemplo para ver se ele relata um erro:</span><span class="sxs-lookup"><span data-stu-id="5fc85-172">Let's test the sample Get-Proc cmdlet to see whether it reports an error:</span></span>

- <span data-ttu-id="5fc85-173">Inicie o PowerShell e use o cmdlet Get-proc para recuperar os processos chamados "TEST".</span><span class="sxs-lookup"><span data-stu-id="5fc85-173">Start PowerShell, and use the Get-Proc cmdlet to retrieve the processes named "TEST".</span></span>

    ```powershell
    PS> get-proc -name test
    ```

<span data-ttu-id="5fc85-174">A saída a seguir é exibida.</span><span class="sxs-lookup"><span data-stu-id="5fc85-174">The following output appears.</span></span>

    ```
    get-proc : Operation is not valid due to the current state of the object.
    At line:1 char:9
    + get-proc  <<<< -name test
    ```

## <a name="see-also"></a><span data-ttu-id="5fc85-175">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5fc85-175">See Also</span></span>

[<span data-ttu-id="5fc85-176">Adicionando parâmetros que processam a entrada do pipeline</span><span class="sxs-lookup"><span data-stu-id="5fc85-176">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="5fc85-177">Adicionando parâmetros que processam a entrada de linha de comando</span><span class="sxs-lookup"><span data-stu-id="5fc85-177">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="5fc85-178">Criando seu primeiro cmdlet</span><span class="sxs-lookup"><span data-stu-id="5fc85-178">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="5fc85-179">Estendendo tipos de objeto e formatação</span><span class="sxs-lookup"><span data-stu-id="5fc85-179">Extending Object Types and Formatting</span></span>](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="5fc85-180">Como registrar cmdlets, provedores e aplicativos host</span><span class="sxs-lookup"><span data-stu-id="5fc85-180">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="5fc85-181">Referência do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fc85-181">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="5fc85-182">Exemplos de cmdlet</span><span class="sxs-lookup"><span data-stu-id="5fc85-182">Cmdlet Samples</span></span>](./cmdlet-samples.md)

[System. Exception]: /dotnet/api/System.Exception
[System.Exception]: /dotnet/api/System.Exception
[System. Management. Automation. preferência]: /dotnet/api/System.Management.Automation.ActionPreference
[System.Management.Automation.ActionPreference]: /dotnet/api/System.Management.Automation.ActionPreference
[System. Management. Automation. cmdlet. ProcessRecord]: /dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord
[System.Management.Automation.Cmdlet.ProcessRecord]: /dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord
[System. Management. Automation. cmdlet. WriteError]: /dotnet/api/System.Management.Automation.Cmdlet.WriteError
[System.Management.Automation.Cmdlet.WriteError]: /dotnet/api/System.Management.Automation.Cmdlet.WriteError
[System. Management. Automation. cmdlet]: /dotnet/api/System.Management.Automation.Cmdlet
[System.Management.Automation.Cmdlet]: /dotnet/api/System.Management.Automation.Cmdlet
[System. Management. Automation. ErrorCategory]: /dotnet/api/System.Management.Automation.ErrorCategory
[System.Management.Automation.ErrorCategory]: /dotnet/api/System.Management.Automation.ErrorCategory
[System. Management. Automation. ErrorRecord]: /dotnet/api/System.Management.Automation.ErrorRecord
[System.Management.Automation.ErrorRecord]: /dotnet/api/System.Management.Automation.ErrorRecord
