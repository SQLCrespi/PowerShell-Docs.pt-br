---
ms.date: 09/13/2016
ms.topic: reference
title: Adicionar mensagens de usuário para o cmdlet
description: Adicionar mensagens de usuário para o cmdlet
ms.openlocfilehash: de6fcc093af1d01287eed1eb8cc7b81cf5d2fdd8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668330"
---
# <a name="adding-user-messages-to-your-cmdlet"></a><span data-ttu-id="e5b11-103">Adicionar mensagens de usuário para o cmdlet</span><span class="sxs-lookup"><span data-stu-id="e5b11-103">Adding User Messages to Your Cmdlet</span></span>

<span data-ttu-id="e5b11-104">Os cmdlets podem gravar vários tipos de mensagens que podem ser exibidas para o usuário pelo tempo de execução do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5b11-104">Cmdlets can write several kinds of messages that can be displayed to the user by the Windows PowerShell runtime.</span></span> <span data-ttu-id="e5b11-105">Essas mensagens incluem os seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="e5b11-105">These messages include the following types:</span></span>

- <span data-ttu-id="e5b11-106">Mensagens detalhadas que contêm informações gerais do usuário.</span><span class="sxs-lookup"><span data-stu-id="e5b11-106">Verbose messages that contain general user information.</span></span>

- <span data-ttu-id="e5b11-107">Mensagens de depuração que contêm informações de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="e5b11-107">Debug messages that contain troubleshooting information.</span></span>

- <span data-ttu-id="e5b11-108">Mensagens de aviso que contêm uma notificação de que o cmdlet está prestes a executar uma operação que pode ter resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="e5b11-108">Warning messages that contain a notification that the cmdlet is about to perform an operation that can have unexpected results.</span></span>

- <span data-ttu-id="e5b11-109">Mensagens de relatório de progresso que contêm informações sobre a quantidade de trabalho que o cmdlet concluiu ao executar uma operação que leva muito tempo.</span><span class="sxs-lookup"><span data-stu-id="e5b11-109">Progress report messages that contain information about how much work the cmdlet has completed when performing an operation that takes a long time.</span></span>

<span data-ttu-id="e5b11-110">Não há limites para o número de mensagens que seu cmdlet pode gravar ou o tipo de mensagens que seu cmdlet grava.</span><span class="sxs-lookup"><span data-stu-id="e5b11-110">There are no limits to the number of messages that your cmdlet can write or the type of messages that your cmdlet writes.</span></span> <span data-ttu-id="e5b11-111">Cada mensagem é escrita fazendo uma chamada específica de dentro do método de processamento de entrada do seu cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5b11-111">Each message is written by making a specific call from within the input processing method of your cmdlet.</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="e5b11-112">Definindo o cmdlet</span><span class="sxs-lookup"><span data-stu-id="e5b11-112">Defining the Cmdlet</span></span>

<span data-ttu-id="e5b11-113">A primeira etapa na criação de cmdlet é sempre nomear o cmdlet e declarar a classe .NET que implementa o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5b11-113">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="e5b11-114">Qualquer tipo de cmdlet pode gravar notificações de usuário de seus métodos de processamento de entrada; Portanto, em geral, você pode nomear esse cmdlet usando qualquer verbo que indique quais modificações do sistema o cmdlet executa.</span><span class="sxs-lookup"><span data-stu-id="e5b11-114">Any sort of cmdlet can write user notifications from its input processing methods; so, in general, you can name this cmdlet using any verb that indicates what system modifications the cmdlet performs.</span></span> <span data-ttu-id="e5b11-115">Para obter mais informações sobre verbos de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="e5b11-115">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="e5b11-116">O cmdlet Stop-Proc foi projetado para modificar o sistema; Portanto, a Declaração [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) para a classe .NET deve incluir a `SupportsShouldProcess` palavra-chave Attribute e ser definida como `true` .</span><span class="sxs-lookup"><span data-stu-id="e5b11-116">The Stop-Proc cmdlet is designed to modify the system; therefore, the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaration for the .NET class must include the `SupportsShouldProcess` attribute keyword and be set to `true`.</span></span>

<span data-ttu-id="e5b11-117">O código a seguir é a definição para esta Stop-Proc classe de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5b11-117">The following code is the definition for this Stop-Proc cmdlet class.</span></span> <span data-ttu-id="e5b11-118">Para obter mais informações sobre essa definição, consulte [criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="e5b11-118">For more information about this definition, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="e5b11-119">Definindo parâmetros para a modificação do sistema</span><span class="sxs-lookup"><span data-stu-id="e5b11-119">Defining Parameters for System Modification</span></span>

<span data-ttu-id="e5b11-120">O cmdlet Stop-Proc define três parâmetros: `Name` , `Force` e `PassThru` .</span><span class="sxs-lookup"><span data-stu-id="e5b11-120">The Stop-Proc cmdlet defines three parameters: `Name`, `Force`, and `PassThru`.</span></span> <span data-ttu-id="e5b11-121">Para obter mais informações sobre como definir esses parâmetros, consulte [criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="e5b11-121">For more information about defining these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

<span data-ttu-id="e5b11-122">Aqui está a declaração de parâmetro para o cmdlet Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="e5b11-122">Here is the parameter declaration for the Stop-Proc cmdlet.</span></span>

```csharp
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true
)]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;

/// <summary>
/// Specify the Force parameter that allows the user to override
/// the ShouldContinue call to force the stop operation. This
/// parameter should always be used with caution.
/// </summary>
[Parameter]
public SwitchParameter Force
{
  get { return force; }
  set { force = value; }
}
private bool force;

/// <summary>
/// Specify the PassThru parameter that allows the user to specify
/// that the cmdlet should pass the process object down the pipeline
/// after the process has been stopped.
/// </summary>
[Parameter]
public SwitchParameter PassThru
{
  get { return passThru; }
  set { passThru = value; }
}
private bool passThru;
```

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="e5b11-123">Substituindo um método de processamento de entrada</span><span class="sxs-lookup"><span data-stu-id="e5b11-123">Overriding an Input Processing Method</span></span>

<span data-ttu-id="e5b11-124">O cmdlet deve substituir um método de processamento de entrada, geralmente ele será [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span><span class="sxs-lookup"><span data-stu-id="e5b11-124">Your cmdlet must override an input processing method, most often it will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="e5b11-125">Esse cmdlet Stop-Proc substitui o método de processamento de entrada [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="e5b11-125">This Stop-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) input processing method.</span></span> <span data-ttu-id="e5b11-126">Nessa implementação do cmdlet Stop-Proc, são feitas chamadas para gravar mensagens detalhadas, depurar mensagens e mensagens de aviso.</span><span class="sxs-lookup"><span data-stu-id="e5b11-126">In this implementation of the Stop-Proc cmdlet, calls are made to write verbose messages, debug messages, and warning messages.</span></span>

> [!NOTE]
> <span data-ttu-id="e5b11-127">Para obter mais informações sobre como esse método chama os métodos [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , consulte [criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="e5b11-127">For more information about how this method calls the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="writing-a-verbose-message"></a><span data-ttu-id="e5b11-128">Escrevendo uma mensagem detalhada</span><span class="sxs-lookup"><span data-stu-id="e5b11-128">Writing a Verbose Message</span></span>

<span data-ttu-id="e5b11-129">O método [System. Management. Automation. cmdlet. WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) é usado para gravar informações gerais em nível de usuário que não estão relacionadas a condições de erro específicas.</span><span class="sxs-lookup"><span data-stu-id="e5b11-129">The [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method is used to write general user-level information that is unrelated to specific error conditions.</span></span> <span data-ttu-id="e5b11-130">O administrador do sistema pode usar essas informações para continuar processando outros comandos.</span><span class="sxs-lookup"><span data-stu-id="e5b11-130">The system administrator can then use that information to continue processing other commands.</span></span> <span data-ttu-id="e5b11-131">Além disso, todas as informações escritas usando esse método devem ser localizadas conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e5b11-131">In addition, any information written using this method should be localized as needed.</span></span>

<span data-ttu-id="e5b11-132">O seguinte código desse Stop-Proc cmdlet mostra duas chamadas para o método [System. Management. Automation. cmdlet. WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) da substituição do método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="e5b11-132">The following code from this Stop-Proc cmdlet shows two calls to the [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
message = String.Format("Attempting to stop process \"{0}\".", name);
WriteVerbose(message);
```

```csharp
message = String.Format("Stopped process \"{0}\", pid {1}.",
                        processName, process.Id);

WriteVerbose(message);
```

## <a name="writing-a-debug-message"></a><span data-ttu-id="e5b11-133">Gravando uma mensagem de depuração</span><span class="sxs-lookup"><span data-stu-id="e5b11-133">Writing a Debug Message</span></span>

<span data-ttu-id="e5b11-134">O método [System. Management. Automation. cmdlet. WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) é usado para gravar mensagens de depuração que podem ser usadas para solucionar problemas da operação do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5b11-134">The [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method is used to write debug messages that can be used to troubleshoot the operation of the cmdlet.</span></span> <span data-ttu-id="e5b11-135">A chamada é feita de um método de processamento de entrada.</span><span class="sxs-lookup"><span data-stu-id="e5b11-135">The call is made from an input processing method.</span></span>

> [!NOTE]
> <span data-ttu-id="e5b11-136">O Windows PowerShell também define um `Debug` parâmetro que apresenta informações detalhadas e de depuração.</span><span class="sxs-lookup"><span data-stu-id="e5b11-136">Windows PowerShell also defines a `Debug` parameter that presents both verbose and debug information.</span></span> <span data-ttu-id="e5b11-137">Se o cmdlet der suporte a esse parâmetro, ele não precisará chamar [System. Management. Automation. cmdlet. WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) no mesmo código que chama [System. Management. Automation. cmdlet. WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).</span><span class="sxs-lookup"><span data-stu-id="e5b11-137">If your cmdlet supports this parameter, it does not need to call [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) in the same code that calls [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).</span></span>

<span data-ttu-id="e5b11-138">As duas seções de código a seguir do cmdlet Stop-Proc de exemplo mostram chamadas para o método [System. Management. Automation. cmdlet. WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) da substituição do método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="e5b11-138">The following two sections of code from the sample Stop-Proc cmdlet show calls to the [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="e5b11-139">Essa mensagem de depuração é gravada imediatamente antes de [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) ser chamado.</span><span class="sxs-lookup"><span data-stu-id="e5b11-139">This debug message is written immediately before [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) is called.</span></span>

```csharp
message =
          String.Format("Acquired name for pid {0} : \"{1}\"",
                       process.Id, processName);
WriteDebug(message);
```

<span data-ttu-id="e5b11-140">Essa mensagem de depuração é gravada imediatamente antes de [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) ser chamado.</span><span class="sxs-lookup"><span data-stu-id="e5b11-140">This debug message is written immediately before [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) is called.</span></span>

```csharp
message =
         String.Format("Writing process \"{0}\" to pipeline",
         processName);
WriteDebug(message);
WriteObject(process);
```

<span data-ttu-id="e5b11-141">O Windows PowerShell roteia automaticamente quaisquer chamadas [System. Management. Automation. cmdlet. WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) para a infraestrutura de rastreamento e os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e5b11-141">Windows PowerShell automatically routes any [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) calls to the tracing infrastructure and cmdlets.</span></span> <span data-ttu-id="e5b11-142">Isso permite que as chamadas de método sejam rastreadas para o aplicativo de hospedagem, um arquivo ou um depurador sem a necessidade de fazer qualquer trabalho de desenvolvimento extra dentro do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5b11-142">This allows the method calls to be traced to the hosting application, a file, or a debugger without your having to do any extra development work within the cmdlet.</span></span> <span data-ttu-id="e5b11-143">A seguinte entrada de linha de comando implementa uma operação de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="e5b11-143">The following command-line entry implements a tracing operation.</span></span>

<span data-ttu-id="e5b11-144">**PS> Trace-expressão Stop-proc-File proc. log-Command Stop-proc bloco de notas**</span><span class="sxs-lookup"><span data-stu-id="e5b11-144">**PS> trace-expression stop-proc -file proc.log -command stop-proc notepad**</span></span>

## <a name="writing-a-warning-message"></a><span data-ttu-id="e5b11-145">Gravando uma mensagem de aviso</span><span class="sxs-lookup"><span data-stu-id="e5b11-145">Writing a Warning Message</span></span>

<span data-ttu-id="e5b11-146">O método [System. Management. Automation. cmdlet. WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) é usado para gravar um aviso quando o cmdlet está prestes a executar uma operação que pode ter um resultado inesperado, por exemplo, substituindo um arquivo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="e5b11-146">The [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method is used to write a warning when the cmdlet is about to perform an operation that might have an unexpected result, for example, overwriting a read-only file.</span></span>

<span data-ttu-id="e5b11-147">O código a seguir do cmdlet Stop-Proc de exemplo mostra a chamada para o método [System. Management. Automation. cmdlet. WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) da substituição do método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="e5b11-147">The following code from the sample Stop-Proc cmdlet shows the call to the [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
 if (criticalProcess)
 {
   message =
             String.Format("Stopping the critical process \"{0}\".",
                           processName);
   WriteWarning(message);
} // if (criticalProcess...
```

## <a name="writing-a-progress-message"></a><span data-ttu-id="e5b11-148">Gravando uma mensagem de progresso</span><span class="sxs-lookup"><span data-stu-id="e5b11-148">Writing a Progress Message</span></span>

<span data-ttu-id="e5b11-149">O [System. Management. Automation. cmdlet. WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) é usado para gravar mensagens de progresso quando as operações de cmdlet demoram um longo período de tempo para serem concluídas.</span><span class="sxs-lookup"><span data-stu-id="e5b11-149">The [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) is used to write progress messages when cmdlet operations take an extended amount of time to complete.</span></span> <span data-ttu-id="e5b11-150">Uma chamada para [System. Management. Automation. cmdlet. WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) passa um objeto [System. Management. Automation. ProgressRecord](/dotnet/api/System.Management.Automation.ProgressRecord) que é enviado ao aplicativo de hospedagem para renderização para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e5b11-150">A call to [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) passes a [System.Management.Automation.Progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord) object that is sent to the hosting application for rendering to the user.</span></span>

> [!NOTE]
> <span data-ttu-id="e5b11-151">Este cmdlet de Stop-Proc não inclui uma chamada para o método [System. Management. Automation. cmdlet. WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) .</span><span class="sxs-lookup"><span data-stu-id="e5b11-151">This Stop-Proc cmdlet does not include a call to the [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) method.</span></span>

<span data-ttu-id="e5b11-152">O código a seguir é um exemplo de uma mensagem de progresso escrita por um cmdlet que está tentando copiar um item.</span><span class="sxs-lookup"><span data-stu-id="e5b11-152">The following code is an example of a progress message written by a cmdlet that is attempting to copy an item.</span></span>

```csharp
int myId = 0;
string myActivity = "Copy-item: Copying *.* to c:\abc";
string myStatus = "Copying file bar.txt";
ProgressRecord pr = new ProgressRecord(myId, myActivity, myStatus);
WriteProgress(pr);

pr.RecordType = ProgressRecordType.Completed;
WriteProgress(pr);
```

## <a name="code-sample"></a><span data-ttu-id="e5b11-153">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="e5b11-153">Code Sample</span></span>

<span data-ttu-id="e5b11-154">Para obter o código de exemplo completo em C#, consulte [exemplo de StopProcessSample02](./stopprocesssample02-sample.md).</span><span class="sxs-lookup"><span data-stu-id="e5b11-154">For the complete C# sample code, see [StopProcessSample02 Sample](./stopprocesssample02-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="e5b11-155">Definir tipos de objeto e formatação</span><span class="sxs-lookup"><span data-stu-id="e5b11-155">Define Object Types and Formatting</span></span>

<span data-ttu-id="e5b11-156">O Windows PowerShell passa informações entre os cmdlets usando objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="e5b11-156">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="e5b11-157">Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou o cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5b11-157">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="e5b11-158">Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="e5b11-158">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="e5b11-159">Criando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="e5b11-159">Building the Cmdlet</span></span>

<span data-ttu-id="e5b11-160">Depois de implementar um cmdlet, ele deve ser registrado com o Windows PowerShell por meio de um snap-in do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5b11-160">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="e5b11-161">Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="e5b11-161">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="e5b11-162">Testando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="e5b11-162">Testing the Cmdlet</span></span>

<span data-ttu-id="e5b11-163">Quando o cmdlet tiver sido registrado com o Windows PowerShell, você poderá testá-lo executando-o na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="e5b11-163">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="e5b11-164">Vamos testar o cmdlet Stop-Proc de exemplo.</span><span class="sxs-lookup"><span data-stu-id="e5b11-164">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="e5b11-165">Para obter mais informações sobre como usar cmdlets na linha de comando, consulte o [introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="e5b11-165">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="e5b11-166">A seguinte entrada de linha de comando usa Stop-Proc para interromper o processo chamado "NOTEPAD", fornecer notificações detalhadas e imprimir informações de depuração.</span><span class="sxs-lookup"><span data-stu-id="e5b11-166">The following command-line entry uses Stop-Proc to stop the process named "NOTEPAD", provide verbose notifications, and print debug information.</span></span>

    ```powershell
    PS> stop-proc -Name notepad -Verbose -Debug
    ```

    <span data-ttu-id="e5b11-167">A saída a seguir aparece.</span><span class="sxs-lookup"><span data-stu-id="e5b11-167">The following output appears.</span></span>

    ```
    VERBOSE: Attempting to stop process " notepad ".
    DEBUG: Acquired name for pid 5584 : "notepad"

    Confirm
    Continue with this operation?
    [Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): Y

    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (5584)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    VERBOSE: Stopped process "notepad", pid 5584.
    ```

## <a name="see-also"></a><span data-ttu-id="e5b11-168">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e5b11-168">See Also</span></span>

[<span data-ttu-id="e5b11-169">Criar um cmdlet que modifica o sistema</span><span class="sxs-lookup"><span data-stu-id="e5b11-169">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="e5b11-170">Como criar um cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5b11-170">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="e5b11-171">[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e5b11-171">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="e5b11-172">[Como registrar cmdlets, provedores e aplicativos host](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e5b11-172">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="e5b11-173">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5b11-173">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
