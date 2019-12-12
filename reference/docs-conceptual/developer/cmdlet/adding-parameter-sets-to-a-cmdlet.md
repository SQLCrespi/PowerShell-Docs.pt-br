---
title: Adicionando conjuntos de parâmetros a um cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parameter sets [PowerShell Programmer's Guide]
ms.assetid: a6131db4-fd6e-45f1-bd47-17e7174afd56
caps.latest.revision: 8
ms.openlocfilehash: c9c0b9a7a587e856efc82b4d277cee373e3f8b38
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74416316"
---
# <a name="adding-parameter-sets-to-a-cmdlet"></a><span data-ttu-id="23622-102">Adicionar conjuntos de parâmetros como um cmdlet</span><span class="sxs-lookup"><span data-stu-id="23622-102">Adding Parameter Sets to a Cmdlet</span></span>

## <a name="things-to-know-about-parameter-sets"></a><span data-ttu-id="23622-103">Coisas a saber sobre conjuntos de parâmetros</span><span class="sxs-lookup"><span data-stu-id="23622-103">Things to Know About Parameter Sets</span></span>

<span data-ttu-id="23622-104">O Windows PowerShell define um parâmetro definido como um grupo de parâmetros que operam juntos.</span><span class="sxs-lookup"><span data-stu-id="23622-104">Windows PowerShell defines a parameter set as a group of parameters that operate together.</span></span> <span data-ttu-id="23622-105">Ao agrupar os parâmetros de um cmdlet, você pode criar um único cmdlet que pode alterar sua funcionalidade com base em qual grupo de parâmetros o usuário especifica.</span><span class="sxs-lookup"><span data-stu-id="23622-105">By grouping the parameters of a cmdlet, you can create a single cmdlet that can change its functionality based on what group of parameters the user specifies.</span></span>

<span data-ttu-id="23622-106">Um exemplo de um cmdlet que usa dois conjuntos de parâmetros para definir funcionalidades diferentes é o cmdlet `Get-EventLog` fornecido pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23622-106">An example of a cmdlet that uses two parameter sets to define different functionalities is the `Get-EventLog` cmdlet that is provided by Windows PowerShell.</span></span> <span data-ttu-id="23622-107">Esse cmdlet retorna informações diferentes quando o usuário especifica o parâmetro `List` ou `LogName`.</span><span class="sxs-lookup"><span data-stu-id="23622-107">This cmdlet returns different information when the user specifies the `List` or `LogName` parameter.</span></span> <span data-ttu-id="23622-108">Se o parâmetro `LogName` for especificado, o cmdlet retornará informações sobre os eventos em um determinado log de eventos.</span><span class="sxs-lookup"><span data-stu-id="23622-108">If the `LogName` parameter is specified, the cmdlet returns information about the events in a given event log.</span></span> <span data-ttu-id="23622-109">Se o parâmetro `List` for especificado, o cmdlet retornará informações sobre os arquivos de log em si (não as informações de evento que eles contêm).</span><span class="sxs-lookup"><span data-stu-id="23622-109">If the `List` parameter is specified, the cmdlet returns information about the log files themselves (not the event information they contain).</span></span> <span data-ttu-id="23622-110">Nesse caso, os parâmetros `List` e `LogName` identificam dois conjuntos de parâmetros separados.</span><span class="sxs-lookup"><span data-stu-id="23622-110">In this case, the `List` and `LogName` parameters identify two separate parameter sets.</span></span>

<span data-ttu-id="23622-111">Duas coisas importantes a serem lembradas sobre conjuntos de parâmetros é que o tempo de execução do Windows PowerShell usa apenas um conjunto de parâmetros para uma entrada específica e que cada conjunto de parâmetros deve ter pelo menos um parâmetro exclusivo para esse conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="23622-111">Two important things to remember about parameter sets is that the Windows PowerShell runtime uses only one parameter set for a particular input, and that each parameter set must have at least one parameter that is unique for that parameter set.</span></span>

<span data-ttu-id="23622-112">Para ilustrar esse último ponto, esse cmdlet Stop-proc usa três conjuntos de parâmetros: `ProcessName`, `ProcessId`e `InputObject`.</span><span class="sxs-lookup"><span data-stu-id="23622-112">To illustrate that last point, this Stop-Proc cmdlet uses three parameter sets: `ProcessName`, `ProcessId`, and `InputObject`.</span></span> <span data-ttu-id="23622-113">Cada um desses conjuntos de parâmetros tem um parâmetro que não está nos outros conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="23622-113">Each of these parameter sets has one parameter that is not in the other parameter sets.</span></span> <span data-ttu-id="23622-114">Os conjuntos de parâmetros podem compartilhar outros parâmetros, mas o cmdlet usa os parâmetros exclusivos `ProcessName`, `ProcessId`e `InputObject` para identificar qual conjunto de parâmetros o tempo de execução do Windows PowerShell deve usar.</span><span class="sxs-lookup"><span data-stu-id="23622-114">The parameter sets could share other parameters, but the cmdlet uses the unique parameters `ProcessName`, `ProcessId`, and `InputObject` to identify which set of parameters that the Windows PowerShell runtime should use.</span></span>

## <a name="declaring-the-cmdlet-class"></a><span data-ttu-id="23622-115">Declarando a classe cmdlet</span><span class="sxs-lookup"><span data-stu-id="23622-115">Declaring the Cmdlet Class</span></span>

<span data-ttu-id="23622-116">A primeira etapa na criação de cmdlet é sempre nomear o cmdlet e declarar a classe .NET que implementa o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="23622-116">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="23622-117">Para esse cmdlet, o verbo de ciclo de vida "Stop" é usado porque o cmdlet para os processos do sistema.</span><span class="sxs-lookup"><span data-stu-id="23622-117">For this cmdlet, the life-cycle verb "Stop" is used because the cmdlet stops system processes.</span></span> <span data-ttu-id="23622-118">O nome do substantivo "proc" é usado porque o cmdlet funciona em processos.</span><span class="sxs-lookup"><span data-stu-id="23622-118">The noun name "Proc" is used because the cmdlet works on processes.</span></span> <span data-ttu-id="23622-119">Na declaração abaixo, observe que o verbo do cmdlet e o nome do substantivo são refletidos no nome da classe do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="23622-119">In the declaration below, note that the cmdlet verb and noun name are reflected in the name of the cmdlet class.</span></span>

> [!NOTE]
> <span data-ttu-id="23622-120">Para obter mais informações sobre nomes de verbo de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="23622-120">For more information about approved cmdlet verb names, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="23622-121">O código a seguir é a definição de classe para esse cmdlet Stop-proc.</span><span class="sxs-lookup"><span data-stu-id="23622-121">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        DefaultParameterSetName = "ProcessId",
        SupportsShouldProcess = true)]
public class StopProcCommand : PSCmdlet
```

```vb
<Cmdlet(VerbsLifecycle.Stop, "Proc", DefaultParameterSetName:="ProcessId", _
SupportsShouldProcess:=True)> _
Public Class StopProcCommand
    Inherits PSCmdlet
```

## <a name="declaring-the-parameters-of-the-cmdlet"></a><span data-ttu-id="23622-122">Declarando os parâmetros do cmdlet</span><span class="sxs-lookup"><span data-stu-id="23622-122">Declaring the Parameters of the Cmdlet</span></span>

<span data-ttu-id="23622-123">Esse cmdlet define três parâmetros necessários como entrada para o cmdlet (esses parâmetros também definem os conjuntos de parâmetros), bem como um parâmetro `Force` que gerencia o que o cmdlet faz e um parâmetro `PassThru` que determina se o cmdlet envia um objeto de saída por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="23622-123">This cmdlet defines three parameters needed as input to the cmdlet (these parameters also define the parameter sets), as well as a `Force` parameter that manages what the cmdlet does and a `PassThru` parameter that determines whether the cmdlet sends an output object through the pipeline.</span></span> <span data-ttu-id="23622-124">Por padrão, esse cmdlet não passa um objeto por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="23622-124">By default, this cmdlet does not pass an object through the pipeline.</span></span> <span data-ttu-id="23622-125">Para obter mais informações sobre esses dois últimos parâmetros, consulte [criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="23622-125">For more information about these last two parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

### <a name="declaring-the-name-parameter"></a><span data-ttu-id="23622-126">Declarando o parâmetro Name</span><span class="sxs-lookup"><span data-stu-id="23622-126">Declaring the Name Parameter</span></span>

<span data-ttu-id="23622-127">Esse parâmetro de entrada permite que o usuário especifique os nomes dos processos a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="23622-127">This input parameter allows the user to specify the names of the processes to be stopped.</span></span> <span data-ttu-id="23622-128">Observe que a palavra-chave Attribute `ParameterSetName` do atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) especifica o parâmetro `ProcessName` definido para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="23622-128">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessName` parameter set for this parameter.</span></span>

[!code-csharp[StopProcessSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs#L44-L58 "StopProcessSample04.cs")]

```vb
<Parameter(Position:=0, ParameterSetName:="ProcessName", _
Mandatory:=True, _
ValueFromPipeline:=True, ValueFromPipelineByPropertyName:=True, _
HelpMessage:="The name of one or more processes to stop. " & _
    "Wildcards are permitted."), [Alias]("ProcessName")> _
Public Property Name() As String()
    Get
        Return processNames
    End Get
    Set(ByVal value As String())
        processNames = value
    End Set
End Property

Private processNames() As String
```

<span data-ttu-id="23622-129">Observe também que o alias "ProcessName" é fornecido a esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="23622-129">Note also that the alias "ProcessName" is given to this parameter.</span></span>

### <a name="declaring-the-id-parameter"></a><span data-ttu-id="23622-130">Declarando o parâmetro ID</span><span class="sxs-lookup"><span data-stu-id="23622-130">Declaring the Id Parameter</span></span>

<span data-ttu-id="23622-131">Esse parâmetro de entrada permite que o usuário especifique os identificadores dos processos a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="23622-131">This input parameter allows the user to specify the identifiers of the processes to be stopped.</span></span> <span data-ttu-id="23622-132">Observe que a palavra-chave Attribute `ParameterSetName` do atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) especifica o conjunto de parâmetros `ProcessId`.</span><span class="sxs-lookup"><span data-stu-id="23622-132">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessId` parameter set.</span></span>

```csharp
[Parameter(
           ParameterSetName = "ProcessId",
           Mandatory = true,
           ValueFromPipelineByPropertyName = true,
           ValueFromPipeline = true
)]
[Alias("ProcessId")]
public int[] Id
{
  get { return processIds; }
  set { processIds = value; }
}
private int[] processIds;
```

```vb
<Parameter(ParameterSetName:="ProcessId", _
Mandatory:=True, _
ValueFromPipelineByPropertyName:=True, _
ValueFromPipeline:=True), [Alias]("ProcessId")> _
Public Property Id() As Integer()
    Get
        Return processIds
    End Get
    Set(ByVal value As Integer())
        processIds = value
    End Set
End Property
Private processIds() As Integer
```

<span data-ttu-id="23622-133">Observe também que o alias "ProcessId" é fornecido para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="23622-133">Note also that the alias "ProcessId" is given to this parameter.</span></span>

### <a name="declaring-the-inputobject-parameter"></a><span data-ttu-id="23622-134">Declarando o parâmetro InputObject</span><span class="sxs-lookup"><span data-stu-id="23622-134">Declaring the InputObject Parameter</span></span>

<span data-ttu-id="23622-135">Esse parâmetro de entrada permite que o usuário especifique um objeto de entrada que contém informações sobre os processos a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="23622-135">This input parameter allows the user to specify an input object that contains information about the processes to be stopped.</span></span> <span data-ttu-id="23622-136">Observe que a palavra-chave Attribute `ParameterSetName` do atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) especifica o parâmetro `InputObject` definido para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="23622-136">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `InputObject` parameter set for this parameter.</span></span>

```csharp
[Parameter(
           ParameterSetName = "InputObject",
           Mandatory = true,
           ValueFromPipeline = true)]
public Process[] InputObject
{
  get { return inputObject; }
  set { inputObject = value; }
}
private Process[] inputObject;
```

```vb
<Parameter(ParameterSetName:="InputObject", _
Mandatory:=True, ValueFromPipeline:=True)> _
Public Property InputObject() As Process()
    Get
        Return myInputObject
    End Get
    Set(ByVal value As Process())
        myInputObject = value
    End Set
End Property
Private myInputObject() As Process
```

<span data-ttu-id="23622-137">Observe também que esse parâmetro não tem nenhum alias.</span><span class="sxs-lookup"><span data-stu-id="23622-137">Note also that this parameter has no alias.</span></span>

### <a name="declaring-parameters-in-multiple-parameter-sets"></a><span data-ttu-id="23622-138">Declarando parâmetros em vários conjuntos de parâmetros</span><span class="sxs-lookup"><span data-stu-id="23622-138">Declaring Parameters in Multiple Parameter Sets</span></span>

<span data-ttu-id="23622-139">Embora seja necessário haver um parâmetro exclusivo para cada conjunto de parâmetros, os parâmetros podem pertencer a mais de um conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="23622-139">Although there must be a unique parameter for each parameter set, parameters can belong to more than one parameter set.</span></span> <span data-ttu-id="23622-140">Nesses casos, forneça ao parâmetro compartilhado uma declaração de atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) para cada conjunto ao qual o parâmetro pertence.</span><span class="sxs-lookup"><span data-stu-id="23622-140">In these cases, give the shared parameter a [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration for each set to which that the parameter belongs.</span></span> <span data-ttu-id="23622-141">Se um parâmetro estiver em todos os conjuntos de parâmetros, você só precisará declarar o atributo de parâmetro uma vez e não precisará especificar o nome do conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="23622-141">If a parameter is in all parameter sets, you only have to declare the parameter attribute once and do not need to specify the parameter set name.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="23622-142">Substituindo um método de processamento de entrada</span><span class="sxs-lookup"><span data-stu-id="23622-142">Overriding an Input Processing Method</span></span>

<span data-ttu-id="23622-143">Cada cmdlet deve substituir um método de processamento de entrada, com mais frequência esse será o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="23622-143">Every cmdlet must override an input processing method, most often this will be the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span> <span data-ttu-id="23622-144">Nesse cmdlet, o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) é substituído para que o cmdlet possa processar qualquer número de processos.</span><span class="sxs-lookup"><span data-stu-id="23622-144">In this cmdlet, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden so that the cmdlet can process any number of processes.</span></span> <span data-ttu-id="23622-145">Ele contém uma instrução SELECT que chama um método diferente com base no conjunto de parâmetros especificado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="23622-145">It contains a Select statement that calls a different method based on which parameter set the user has specified.</span></span>

```csharp
protected override void ProcessRecord()
{
  switch (ParameterSetName)
  {
    case "ProcessName":
         ProcessByName();
         break;

    case "ProcessId":
         ProcessById();
         break;

    case "InputObject":
         foreach (Process process in inputObject)
         {
           SafeStopProcess(process);
         }
         break;

    default:
         throw new ArgumentException("Bad ParameterSet Name");
  } // switch (ParameterSetName...
} // ProcessRecord
```

```vb
Protected Overrides Sub ProcessRecord()
    Select Case ParameterSetName
        Case "ProcessName"
            ProcessByName()

        Case "ProcessId"
            ProcessById()

        Case "InputObject"
            Dim process As Process
            For Each process In myInputObject
                SafeStopProcess(process)
            Next process

        Case Else
            Throw New ArgumentException("Bad ParameterSet Name")
    End Select

End Sub 'ProcessRecord ' ProcessRecord
```

<span data-ttu-id="23622-146">Os métodos auxiliares chamados pela instrução SELECT não são descritos aqui, mas você pode ver sua implementação no exemplo de código completo na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="23622-146">The Helper methods called by the Select statement are not described here, but you can see their implementation in the complete code sample in the next section.</span></span>

## <a name="code-sample"></a><span data-ttu-id="23622-147">Exemplo de Código</span><span class="sxs-lookup"><span data-stu-id="23622-147">Code Sample</span></span>

<span data-ttu-id="23622-148">Para obter o C# código de exemplo completo, consulte [exemplo de StopProcessSample04](./stopprocesssample04-sample.md).</span><span class="sxs-lookup"><span data-stu-id="23622-148">For the complete C# sample code, see [StopProcessSample04 Sample](./stopprocesssample04-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="23622-149">Definindo tipos de objeto e formatação</span><span class="sxs-lookup"><span data-stu-id="23622-149">Defining Object Types and Formatting</span></span>

<span data-ttu-id="23622-150">O Windows PowerShell passa informações entre os cmdlets usando objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="23622-150">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="23622-151">Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou o cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="23622-151">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="23622-152">Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="23622-152">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="23622-153">Criando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="23622-153">Building the Cmdlet</span></span>

<span data-ttu-id="23622-154">Depois de implementar um cmdlet, você deve registrá-lo com o Windows PowerShell por meio de um snap-in do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23622-154">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="23622-155">Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="23622-155">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="23622-156">Testando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="23622-156">Testing the Cmdlet</span></span>

<span data-ttu-id="23622-157">Quando o cmdlet tiver sido registrado com o Windows PowerShell, teste-o executando-o na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="23622-157">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="23622-158">Aqui estão alguns testes que mostram como os parâmetros `ProcessId` e `InputObject` podem ser usados para testar seus conjuntos de parâmetros para interromper um processo.</span><span class="sxs-lookup"><span data-stu-id="23622-158">Here are some tests that show how the `ProcessId` and `InputObject` parameters can be used to test their parameter sets to stop a process.</span></span>

- <span data-ttu-id="23622-159">Com o Windows PowerShell iniciado, execute o cmdlet Stop-proc com o parâmetro `ProcessId` definido para interromper um processo com base em seu identificador.</span><span class="sxs-lookup"><span data-stu-id="23622-159">With Windows PowerShell started, run the Stop-Proc cmdlet with the `ProcessId` parameter set to stop a process based on its identifier.</span></span> <span data-ttu-id="23622-160">Nesse caso, o cmdlet está usando o parâmetro `ProcessId` definido para parar o processo.</span><span class="sxs-lookup"><span data-stu-id="23622-160">In this case, the cmdlet is using the `ProcessId` parameter set to stop the process.</span></span>

    ```
    PS> stop-proc -Id 444
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (444)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="23622-161">Com o Windows PowerShell iniciado, execute o cmdlet Stop-proc com o parâmetro `InputObject` definido para parar os processos no objeto do bloco de notas recuperado pelo comando `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="23622-161">With Windows PowerShell started, run the Stop-Proc cmdlet with the `InputObject` parameter set to stop processes on the Notepad object retrieved by the `Get-Process` command.</span></span>

    ```
    PS> get-process notepad | stop-proc
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (444)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="23622-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="23622-162">See Also</span></span>

[<span data-ttu-id="23622-163">Criando um cmdlet que modifica o sistema</span><span class="sxs-lookup"><span data-stu-id="23622-163">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="23622-164">Como criar um cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="23622-164">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="23622-165">[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="23622-165">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="23622-166">[Como registrar cmdlets, provedores e aplicativos host](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="23622-166">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="23622-167">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="23622-167">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
