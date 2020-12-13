---
ms.date: 09/13/2016
ms.topic: reference
title: Adicionar parâmetros que processam a entrada de pipeline
description: Adicionar parâmetros que processam a entrada de pipeline
ms.openlocfilehash: b150d5be93207d9c010a6d2d4de901b4526f1d79
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668347"
---
# <a name="adding-parameters-that-process-pipeline-input"></a><span data-ttu-id="2cc18-103">Adicionar parâmetros que processam a entrada de pipeline</span><span class="sxs-lookup"><span data-stu-id="2cc18-103">Adding Parameters that Process Pipeline Input</span></span>

<span data-ttu-id="2cc18-104">Uma fonte de entrada para um cmdlet é um objeto no pipeline originado de um cmdlet upstream.</span><span class="sxs-lookup"><span data-stu-id="2cc18-104">One source of input for a cmdlet is an object on the pipeline that originates from an upstream cmdlet.</span></span> <span data-ttu-id="2cc18-105">Esta seção descreve como adicionar um parâmetro ao cmdlet Get-Proc (descrito em [criando seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md)) para que o cmdlet possa processar objetos de pipeline.</span><span class="sxs-lookup"><span data-stu-id="2cc18-105">This section describes how to add a parameter to the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)) so that the cmdlet can process pipeline objects.</span></span>

<span data-ttu-id="2cc18-106">Esse cmdlet Get-Proc usa um `Name` parâmetro que aceita entrada de um objeto de pipeline, recupera informações de processo do computador local com base nos nomes fornecidos e, em seguida, exibe informações sobre os processos na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="2cc18-106">This Get-Proc cmdlet uses a `Name` parameter that accepts input from a pipeline object, retrieves process information from the local computer based on the supplied names, and then displays information about the processes at the command line.</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="2cc18-107">Definindo a classe do cmdlet</span><span class="sxs-lookup"><span data-stu-id="2cc18-107">Defining the Cmdlet Class</span></span>

<span data-ttu-id="2cc18-108">A primeira etapa na criação de cmdlet é sempre nomear o cmdlet e declarar a classe .NET que implementa o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2cc18-108">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="2cc18-109">Esse cmdlet recupera informações de processo, portanto, o nome do verbo escolhido aqui é "Get".</span><span class="sxs-lookup"><span data-stu-id="2cc18-109">This cmdlet retrieves process information, so the verb name chosen here is "Get".</span></span> <span data-ttu-id="2cc18-110">(Quase qualquer tipo de cmdlet capaz de recuperar informações pode processar a entrada de linha de comando.) Para obter mais informações sobre verbos de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="2cc18-110">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="2cc18-111">A seguir está a definição para este Get-Proc cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2cc18-111">The following is the definition for this Get-Proc cmdlet.</span></span> <span data-ttu-id="2cc18-112">Detalhes dessa definição são fornecidos na [criação do seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="2cc18-112">Details of this definition are given in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-input-from-the-pipeline"></a><span data-ttu-id="2cc18-113">Definindo a entrada do pipeline</span><span class="sxs-lookup"><span data-stu-id="2cc18-113">Defining Input from the Pipeline</span></span>

<span data-ttu-id="2cc18-114">Esta seção descreve como definir a entrada do pipeline para um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2cc18-114">This section describes how to define input from the pipeline for a cmdlet.</span></span> <span data-ttu-id="2cc18-115">Esse cmdlet Get-Proc define uma propriedade que representa o `Name` parâmetro, conforme descrito em [adicionando parâmetros que processam a entrada de linha de comando](./adding-parameters-that-process-command-line-input.md).</span><span class="sxs-lookup"><span data-stu-id="2cc18-115">This Get-Proc cmdlet defines a property that represents the `Name` parameter as described in [Adding Parameters that Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span>
<span data-ttu-id="2cc18-116">(Consulte esse tópico para obter informações gerais sobre como declarar parâmetros.)</span><span class="sxs-lookup"><span data-stu-id="2cc18-116">(See that topic for general information about declaring parameters.)</span></span>

<span data-ttu-id="2cc18-117">No entanto, quando um cmdlet precisa processar a entrada do pipeline, ele deve ter seus parâmetros associados aos valores de entrada pelo tempo de execução do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cc18-117">However, when a cmdlet needs to process pipeline input, it must have its parameters bound to input values by the Windows PowerShell runtime.</span></span> <span data-ttu-id="2cc18-118">Para fazer isso, você deve adicionar a `ValueFromPipeline` palavra-chave ou adicionar a `ValueFromPipelineByProperty` palavra-chave à declaração de atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) .</span><span class="sxs-lookup"><span data-stu-id="2cc18-118">To do this, you must add the `ValueFromPipeline` keyword or add the `ValueFromPipelineByProperty` keyword to the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="2cc18-119">Especifique a `ValueFromPipeline` palavra-chave se o cmdlet acessar o objeto de entrada completo.</span><span class="sxs-lookup"><span data-stu-id="2cc18-119">Specify the `ValueFromPipeline` keyword if the cmdlet accesses the complete input object.</span></span> <span data-ttu-id="2cc18-120">Especifique `ValueFromPipelineByProperty` se o cmdlet acessa apenas uma propriedade do objeto.</span><span class="sxs-lookup"><span data-stu-id="2cc18-120">Specify the `ValueFromPipelineByProperty` if the cmdlet accesses only a property of the object.</span></span>

<span data-ttu-id="2cc18-121">Aqui está a declaração de parâmetro para o `Name` parâmetro desse Get-Proc cmdlet que aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="2cc18-121">Here is the parameter declaration for the `Name` parameter of this Get-Proc cmdlet that accepts pipeline input.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="35-44":::

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

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#GetProc03VBNameParameter](Msh_samplesgetproc03#GetProc03VBNameParameter)]  -->

<span data-ttu-id="2cc18-122">A declaração anterior define a `ValueFromPipeline` palavra-chave para para `true` que o tempo de execução do Windows PowerShell vincule o parâmetro ao objeto de entrada se o objeto for do mesmo tipo que o parâmetro, ou se ele puder ser forçado para o mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="2cc18-122">The previous declaration sets the `ValueFromPipeline` keyword to `true` so that the Windows PowerShell runtime will bind the parameter to the incoming object if the object is the same type as the parameter, or if it can be coerced to the same type.</span></span> <span data-ttu-id="2cc18-123">A `ValueFromPipelineByPropertyName` palavra-chave também é definida como para `true` que o tempo de execução do Windows PowerShell Verifique se há uma propriedade no objeto de entrada `Name` .</span><span class="sxs-lookup"><span data-stu-id="2cc18-123">The `ValueFromPipelineByPropertyName` keyword is also set to `true` so that the Windows PowerShell runtime will check the incoming object for a `Name` property.</span></span> <span data-ttu-id="2cc18-124">Se o objeto de entrada tiver tal propriedade, o tempo de execução associará o `Name` parâmetro à `Name` Propriedade do objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="2cc18-124">If the incoming object has such a property, the runtime will bind the `Name` parameter to the `Name` property of the incoming object.</span></span>

> [!NOTE]
> <span data-ttu-id="2cc18-125">A configuração da `ValueFromPipeline` palavra-chave Attribute para um parâmetro tem precedência sobre a configuração da `ValueFromPipelineByPropertyName` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="2cc18-125">The setting of the `ValueFromPipeline` attribute keyword for a parameter takes precedence over the setting for the `ValueFromPipelineByPropertyName` keyword.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="2cc18-126">Substituindo um método de processamento de entrada</span><span class="sxs-lookup"><span data-stu-id="2cc18-126">Overriding an Input Processing Method</span></span>

<span data-ttu-id="2cc18-127">Se o cmdlet for manipular a entrada de pipeline, ele precisará substituir os métodos de processamento de entrada apropriados.</span><span class="sxs-lookup"><span data-stu-id="2cc18-127">If your cmdlet is to handle pipeline input, it needs to override the appropriate input processing methods.</span></span> <span data-ttu-id="2cc18-128">Os métodos básicos de processamento de entrada são introduzidos na [criação do seu primeiro cmdlet](./creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="2cc18-128">The basic input processing methods are introduced in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="2cc18-129">Esse cmdlet Get-Proc substitui o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) para manipular a `Name` entrada de parâmetro fornecida pelo usuário ou um script.</span><span class="sxs-lookup"><span data-stu-id="2cc18-129">This Get-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to handle the `Name` parameter input provided by the user or a script.</span></span> <span data-ttu-id="2cc18-130">Esse método obterá os processos para cada nome de processo solicitado ou todos os processos, se nenhum nome for fornecido.</span><span class="sxs-lookup"><span data-stu-id="2cc18-130">This method will get the processes for each requested process name or all processes if no name is provided.</span></span> <span data-ttu-id="2cc18-131">Observe que em [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), a chamada para [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) é o mecanismo de saída para enviar objetos de saída para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="2cc18-131">Notice that within [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), the call to [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) is the output mechanism for sending output objects to the pipeline.</span></span> <span data-ttu-id="2cc18-132">O segundo parâmetro dessa chamada, `enumerateCollection` , é definido como `true` para informar ao tempo de execução do Windows PowerShell para enumerar a matriz de objetos de processo e gravar um processo por vez na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="2cc18-132">The second parameter of this call, `enumerateCollection`, is set to `true` to tell the Windows PowerShell runtime to enumerate the array of process objects, and write one process at a time to the command line.</span></span>

```csharp
protected override void ProcessRecord()
{
  // If no process names are passed to the cmdlet, get all processes.
  if (processNames == null)
  {
      // Write the processes to the pipeline making them available
      // to the next cmdlet. The second argument of this call tells
      // PowerShell to enumerate the array, and send one process at a
      // time to the pipeline.
      WriteObject(Process.GetProcesses(), true);
  }
  else
  {
    // If process names are passed to the cmdlet, get and write
    // the associated processes.
    foreach (string name in processNames)
    {
      WriteObject(Process.GetProcessesByName(name), true);
    } // End foreach (string name...).
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()
    Dim processes As Process()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        processes = Process.GetProcesses()
    Else

        '/ If process names are specified, write the processes to the
        '/ pipeline to display them or make them available to the next cmdlet.
        For Each name As String In processNames
            '/ The second parameter of this call tells PowerShell to enumerate the
            '/ array, and send one process at a time to the pipeline.
            WriteObject(Process.GetProcessesByName(name), True)
        Next
    End If

End Sub 'ProcessRecord
```

## <a name="code-sample"></a><span data-ttu-id="2cc18-133">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="2cc18-133">Code Sample</span></span>

<span data-ttu-id="2cc18-134">Para obter o código de exemplo completo em C#, consulte [exemplo de GetProcessSample03](./getprocesssample03-sample.md).</span><span class="sxs-lookup"><span data-stu-id="2cc18-134">For the complete C# sample code, see [GetProcessSample03 Sample](./getprocesssample03-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="2cc18-135">Definindo tipos de objeto e formatação</span><span class="sxs-lookup"><span data-stu-id="2cc18-135">Defining Object Types and Formatting</span></span>

<span data-ttu-id="2cc18-136">O Windows PowerShell passa informações entre os cmdlets usando objetos .net.</span><span class="sxs-lookup"><span data-stu-id="2cc18-136">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="2cc18-137">Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou o cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2cc18-137">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="2cc18-138">Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="2cc18-138">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="2cc18-139">Criando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="2cc18-139">Building the Cmdlet</span></span>

<span data-ttu-id="2cc18-140">Depois de implementar um cmdlet, ele deve ser registrado com o Windows PowerShell por meio de um snap-in do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cc18-140">After implementing a cmdlet it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="2cc18-141">Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="2cc18-141">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="2cc18-142">Testando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="2cc18-142">Testing the Cmdlet</span></span>

<span data-ttu-id="2cc18-143">Quando o cmdlet tiver sido registrado com o Windows PowerShell, teste-o executando-o na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="2cc18-143">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="2cc18-144">Por exemplo, teste o código para o cmdlet de exemplo.</span><span class="sxs-lookup"><span data-stu-id="2cc18-144">For example, test the code for the sample cmdlet.</span></span> <span data-ttu-id="2cc18-145">Para obter mais informações sobre como usar cmdlets na linha de comando, consulte o [introdução com o Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="2cc18-145">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="2cc18-146">No prompt do Windows PowerShell, insira os seguintes comandos para recuperar os nomes de processo por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="2cc18-146">At the Windows PowerShell prompt, enter the following commands to retrieve the process names through the pipeline.</span></span>

  ```powershell
  PS> type ProcessNames | get-proc
  ```

  <span data-ttu-id="2cc18-147">A saída a seguir aparece.</span><span class="sxs-lookup"><span data-stu-id="2cc18-147">The following output appears.</span></span>

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
  -------  ------  -----   ----- -----   ------    --  -----------
      809      21  40856    4448    147    9.50  2288  iexplore
      737      21  26036   16348    144   22.03  3860  iexplore
       39       2   1024     388     30    0.08  3396  notepad
     3927      62  71836   26984    467  195.19  1848  OUTLOOK
  ```

- <span data-ttu-id="2cc18-148">Insira as linhas a seguir para obter os objetos de processo que têm uma `Name` propriedade dos processos chamados "iexplore".</span><span class="sxs-lookup"><span data-stu-id="2cc18-148">Enter the following lines to get the process objects that have a `Name` property from the processes called "IEXPLORE".</span></span> <span data-ttu-id="2cc18-149">Este exemplo usa o `Get-Process` cmdlet (fornecido pelo Windows PowerShell) como um comando upstream para recuperar os processos de "iexplore".</span><span class="sxs-lookup"><span data-stu-id="2cc18-149">This example uses the `Get-Process` cmdlet (provided by Windows PowerShell) as an upstream command to retrieve the "IEXPLORE" processes.</span></span>

  ```powershell
  PS> get-process iexplore | get-proc
  ```

  <span data-ttu-id="2cc18-150">A saída a seguir aparece.</span><span class="sxs-lookup"><span data-stu-id="2cc18-150">The following output appears.</span></span>

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
  -------  ------  -----   ----- -----   ------    --  -----------
      801      21  40720    6544    142    9.52  2288  iexplore
      726      21  25872   16652    138   22.09  3860  iexplore
      801      21  40720    6544    142    9.52  2288  iexplore
      726      21  25872   16652    138   22.09  3860  iexplore
  ```

## <a name="see-also"></a><span data-ttu-id="2cc18-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2cc18-151">See Also</span></span>

[<span data-ttu-id="2cc18-152">Adicionando parâmetros que processam a entrada de linha de comando</span><span class="sxs-lookup"><span data-stu-id="2cc18-152">Adding Parameters that Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="2cc18-153">Criando seu primeiro cmdlet</span><span class="sxs-lookup"><span data-stu-id="2cc18-153">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

<span data-ttu-id="2cc18-154">[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="2cc18-154">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="2cc18-155">[Como registrar cmdlets, provedores e aplicativos host](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="2cc18-155">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="2cc18-156">Referência do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cc18-156">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="2cc18-157">Amostras de cmdlet</span><span class="sxs-lookup"><span data-stu-id="2cc18-157">Cmdlet Samples</span></span>](./cmdlet-samples.md)
