---
ms.date: 09/13/2016
ms.topic: reference
title: Adicionar conjuntos de parâmetros como um cmdlet
description: Adicionar conjuntos de parâmetros como um cmdlet
ms.openlocfilehash: dd5ee2a880a4d516ea82e5afe0ced12369197243
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648658"
---
# <a name="adding-parameter-sets-to-a-cmdlet"></a><span data-ttu-id="e90dc-103">Adicionar conjuntos de parâmetros como um cmdlet</span><span class="sxs-lookup"><span data-stu-id="e90dc-103">Adding Parameter Sets to a Cmdlet</span></span>

## <a name="things-to-know-about-parameter-sets"></a><span data-ttu-id="e90dc-104">Coisas a saber sobre conjuntos de parâmetros</span><span class="sxs-lookup"><span data-stu-id="e90dc-104">Things to Know About Parameter Sets</span></span>

<span data-ttu-id="e90dc-105">O Windows PowerShell define um parâmetro definido como um grupo de parâmetros que operam juntos.</span><span class="sxs-lookup"><span data-stu-id="e90dc-105">Windows PowerShell defines a parameter set as a group of parameters that operate together.</span></span> <span data-ttu-id="e90dc-106">Ao agrupar os parâmetros de um cmdlet, você pode criar um único cmdlet que pode alterar sua funcionalidade com base em qual grupo de parâmetros o usuário especifica.</span><span class="sxs-lookup"><span data-stu-id="e90dc-106">By grouping the parameters of a cmdlet, you can create a single cmdlet that can change its functionality based on what group of parameters the user specifies.</span></span>

<span data-ttu-id="e90dc-107">Um exemplo de um cmdlet que usa dois conjuntos de parâmetros para definir funcionalidades diferentes é o `Get-EventLog` cmdlet fornecido pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e90dc-107">An example of a cmdlet that uses two parameter sets to define different functionalities is the `Get-EventLog` cmdlet that is provided by Windows PowerShell.</span></span> <span data-ttu-id="e90dc-108">Esse cmdlet retorna informações diferentes quando o usuário especifica o `List` `LogName` parâmetro ou.</span><span class="sxs-lookup"><span data-stu-id="e90dc-108">This cmdlet returns different information when the user specifies the `List` or `LogName` parameter.</span></span> <span data-ttu-id="e90dc-109">Se o `LogName` parâmetro for especificado, o cmdlet retornará informações sobre os eventos em um determinado log de eventos.</span><span class="sxs-lookup"><span data-stu-id="e90dc-109">If the `LogName` parameter is specified, the cmdlet returns information about the events in a given event log.</span></span> <span data-ttu-id="e90dc-110">Se o `List` parâmetro for especificado, o cmdlet retornará informações sobre os arquivos de log em si (não as informações de evento que eles contêm).</span><span class="sxs-lookup"><span data-stu-id="e90dc-110">If the `List` parameter is specified, the cmdlet returns information about the log files themselves (not the event information they contain).</span></span> <span data-ttu-id="e90dc-111">Nesse caso, os `List` parâmetros e `LogName` identificam dois conjuntos de parâmetros separados.</span><span class="sxs-lookup"><span data-stu-id="e90dc-111">In this case, the `List` and `LogName` parameters identify two separate parameter sets.</span></span>

<span data-ttu-id="e90dc-112">Duas coisas importantes a serem lembradas sobre conjuntos de parâmetros é que o tempo de execução do Windows PowerShell usa apenas um conjunto de parâmetros para uma entrada específica e que cada conjunto de parâmetros deve ter pelo menos um parâmetro exclusivo para esse conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="e90dc-112">Two important things to remember about parameter sets is that the Windows PowerShell runtime uses only one parameter set for a particular input, and that each parameter set must have at least one parameter that is unique for that parameter set.</span></span>

<span data-ttu-id="e90dc-113">Para ilustrar esse último ponto, esse cmdlet Stop-Proc usa três conjuntos de parâmetros: `ProcessName` , `ProcessId` e `InputObject` .</span><span class="sxs-lookup"><span data-stu-id="e90dc-113">To illustrate that last point, this Stop-Proc cmdlet uses three parameter sets: `ProcessName`, `ProcessId`, and `InputObject`.</span></span> <span data-ttu-id="e90dc-114">Cada um desses conjuntos de parâmetros tem um parâmetro que não está nos outros conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="e90dc-114">Each of these parameter sets has one parameter that is not in the other parameter sets.</span></span> <span data-ttu-id="e90dc-115">Os conjuntos de parâmetros podem compartilhar outros parâmetros, mas o cmdlet usa os parâmetros exclusivos `ProcessName` , `ProcessId` e `InputObject` para identificar qual conjunto de parâmetros o tempo de execução do Windows PowerShell deve usar.</span><span class="sxs-lookup"><span data-stu-id="e90dc-115">The parameter sets could share other parameters, but the cmdlet uses the unique parameters `ProcessName`, `ProcessId`, and `InputObject` to identify which set of parameters that the Windows PowerShell runtime should use.</span></span>

## <a name="declaring-the-cmdlet-class"></a><span data-ttu-id="e90dc-116">Declarando a classe cmdlet</span><span class="sxs-lookup"><span data-stu-id="e90dc-116">Declaring the Cmdlet Class</span></span>

<span data-ttu-id="e90dc-117">A primeira etapa na criação de cmdlet é sempre nomear o cmdlet e declarar a classe .NET que implementa o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e90dc-117">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="e90dc-118">Para esse cmdlet, o verbo de ciclo de vida "Stop" é usado porque o cmdlet para os processos do sistema.</span><span class="sxs-lookup"><span data-stu-id="e90dc-118">For this cmdlet, the lifecycle verb "Stop" is used because the cmdlet stops system processes.</span></span> <span data-ttu-id="e90dc-119">O nome do substantivo "proc" é usado porque o cmdlet funciona em processos.</span><span class="sxs-lookup"><span data-stu-id="e90dc-119">The noun name "Proc" is used because the cmdlet works on processes.</span></span> <span data-ttu-id="e90dc-120">Na declaração abaixo, observe que o verbo do cmdlet e o nome do substantivo são refletidos no nome da classe do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e90dc-120">In the declaration below, note that the cmdlet verb and noun name are reflected in the name of the cmdlet class.</span></span>

> [!NOTE]
> <span data-ttu-id="e90dc-121">Para obter mais informações sobre nomes de verbo de cmdlet aprovados, consulte [nomes de verbo de cmdlet](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="e90dc-121">For more information about approved cmdlet verb names, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="e90dc-122">O código a seguir é a definição de classe para este Stop-Proc cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e90dc-122">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

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

## <a name="declaring-the-parameters-of-the-cmdlet"></a><span data-ttu-id="e90dc-123">Declarando os parâmetros do cmdlet</span><span class="sxs-lookup"><span data-stu-id="e90dc-123">Declaring the Parameters of the Cmdlet</span></span>

<span data-ttu-id="e90dc-124">Esse cmdlet define três parâmetros necessários como entrada para o cmdlet (esses parâmetros também definem os conjuntos de parâmetros), bem como um `Force` parâmetro que gerencia o que o cmdlet faz e um `PassThru` parâmetro que determina se o cmdlet envia um objeto de saída por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="e90dc-124">This cmdlet defines three parameters needed as input to the cmdlet (these parameters also define the parameter sets), as well as a `Force` parameter that manages what the cmdlet does and a `PassThru` parameter that determines whether the cmdlet sends an output object through the pipeline.</span></span> <span data-ttu-id="e90dc-125">Por padrão, esse cmdlet não passa um objeto por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="e90dc-125">By default, this cmdlet does not pass an object through the pipeline.</span></span> <span data-ttu-id="e90dc-126">Para obter mais informações sobre esses dois últimos parâmetros, consulte [criando um cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="e90dc-126">For more information about these last two parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

### <a name="declaring-the-name-parameter"></a><span data-ttu-id="e90dc-127">Declarando o parâmetro Name</span><span class="sxs-lookup"><span data-stu-id="e90dc-127">Declaring the Name Parameter</span></span>

<span data-ttu-id="e90dc-128">Esse parâmetro de entrada permite que o usuário especifique os nomes dos processos a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="e90dc-128">This input parameter allows the user to specify the names of the processes to be stopped.</span></span> <span data-ttu-id="e90dc-129">Observe que a `ParameterSetName` palavra-chave Attribute do atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) especifica o `ProcessName` conjunto de parâmetros para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e90dc-129">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessName` parameter set for this parameter.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs" range="44-58":::

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

<span data-ttu-id="e90dc-130">Observe também que o alias "ProcessName" é fornecido a esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e90dc-130">Note also that the alias "ProcessName" is given to this parameter.</span></span>

### <a name="declaring-the-id-parameter"></a><span data-ttu-id="e90dc-131">Declarando o parâmetro ID</span><span class="sxs-lookup"><span data-stu-id="e90dc-131">Declaring the Id Parameter</span></span>

<span data-ttu-id="e90dc-132">Esse parâmetro de entrada permite que o usuário especifique os identificadores dos processos a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="e90dc-132">This input parameter allows the user to specify the identifiers of the processes to be stopped.</span></span> <span data-ttu-id="e90dc-133">Observe que a `ParameterSetName` palavra-chave Attribute do atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) especifica o `ProcessId` conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="e90dc-133">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessId` parameter set.</span></span>

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

<span data-ttu-id="e90dc-134">Observe também que o alias "ProcessId" é fornecido para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e90dc-134">Note also that the alias "ProcessId" is given to this parameter.</span></span>

### <a name="declaring-the-inputobject-parameter"></a><span data-ttu-id="e90dc-135">Declarando o parâmetro InputObject</span><span class="sxs-lookup"><span data-stu-id="e90dc-135">Declaring the InputObject Parameter</span></span>

<span data-ttu-id="e90dc-136">Esse parâmetro de entrada permite que o usuário especifique um objeto de entrada que contém informações sobre os processos a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="e90dc-136">This input parameter allows the user to specify an input object that contains information about the processes to be stopped.</span></span> <span data-ttu-id="e90dc-137">Observe que a `ParameterSetName` palavra-chave Attribute do atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) especifica o `InputObject` conjunto de parâmetros para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e90dc-137">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `InputObject` parameter set for this parameter.</span></span>

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

<span data-ttu-id="e90dc-138">Observe também que esse parâmetro não tem nenhum alias.</span><span class="sxs-lookup"><span data-stu-id="e90dc-138">Note also that this parameter has no alias.</span></span>

### <a name="declaring-parameters-in-multiple-parameter-sets"></a><span data-ttu-id="e90dc-139">Declarando parâmetros em vários conjuntos de parâmetros</span><span class="sxs-lookup"><span data-stu-id="e90dc-139">Declaring Parameters in Multiple Parameter Sets</span></span>

<span data-ttu-id="e90dc-140">Embora seja necessário haver um parâmetro exclusivo para cada conjunto de parâmetros, os parâmetros podem pertencer a mais de um conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="e90dc-140">Although there must be a unique parameter for each parameter set, parameters can belong to more than one parameter set.</span></span> <span data-ttu-id="e90dc-141">Nesses casos, forneça ao parâmetro compartilhado uma declaração de atributo [System. Management. Automation. ParameterAttribute](/dotnet/api/System.Management.Automation.ParameterAttribute) para cada conjunto ao qual o parâmetro pertence.</span><span class="sxs-lookup"><span data-stu-id="e90dc-141">In these cases, give the shared parameter a [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration for each set to which that the parameter belongs.</span></span> <span data-ttu-id="e90dc-142">Se um parâmetro estiver em todos os conjuntos de parâmetros, você só precisará declarar o atributo de parâmetro uma vez e não precisará especificar o nome do conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="e90dc-142">If a parameter is in all parameter sets, you only have to declare the parameter attribute once and do not need to specify the parameter set name.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="e90dc-143">Substituindo um método de processamento de entrada</span><span class="sxs-lookup"><span data-stu-id="e90dc-143">Overriding an Input Processing Method</span></span>

<span data-ttu-id="e90dc-144">Cada cmdlet deve substituir um método de processamento de entrada, com mais frequência esse será o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="e90dc-144">Every cmdlet must override an input processing method, most often this will be the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span> <span data-ttu-id="e90dc-145">Nesse cmdlet, o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) é substituído para que o cmdlet possa processar qualquer número de processos.</span><span class="sxs-lookup"><span data-stu-id="e90dc-145">In this cmdlet, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden so that the cmdlet can process any number of processes.</span></span> <span data-ttu-id="e90dc-146">Ele contém uma instrução SELECT que chama um método diferente com base no conjunto de parâmetros especificado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="e90dc-146">It contains a Select statement that calls a different method based on which parameter set the user has specified.</span></span>

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

<span data-ttu-id="e90dc-147">Os métodos auxiliares chamados pela instrução SELECT não são descritos aqui, mas você pode ver sua implementação no exemplo de código completo na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="e90dc-147">The Helper methods called by the Select statement are not described here, but you can see their implementation in the complete code sample in the next section.</span></span>

## <a name="code-sample"></a><span data-ttu-id="e90dc-148">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="e90dc-148">Code Sample</span></span>

<span data-ttu-id="e90dc-149">Para obter o código de exemplo completo em C#, consulte [exemplo de StopProcessSample04](./stopprocesssample04-sample.md).</span><span class="sxs-lookup"><span data-stu-id="e90dc-149">For the complete C# sample code, see [StopProcessSample04 Sample](./stopprocesssample04-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="e90dc-150">Definindo tipos de objeto e formatação</span><span class="sxs-lookup"><span data-stu-id="e90dc-150">Defining Object Types and Formatting</span></span>

<span data-ttu-id="e90dc-151">O Windows PowerShell passa informações entre os cmdlets usando objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="e90dc-151">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="e90dc-152">Consequentemente, um cmdlet pode precisar definir seu próprio tipo ou o cmdlet pode precisar estender um tipo existente fornecido por outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e90dc-152">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="e90dc-153">Para obter mais informações sobre como definir novos tipos ou estender tipos existentes, consulte [estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="e90dc-153">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="e90dc-154">Criando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="e90dc-154">Building the Cmdlet</span></span>

<span data-ttu-id="e90dc-155">Depois de implementar um cmdlet, você deve registrá-lo com o Windows PowerShell por meio de um snap-in do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e90dc-155">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="e90dc-156">Para obter mais informações sobre como registrar cmdlets, consulte [como registrar cmdlets, provedores e aplicativos de host](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="e90dc-156">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="e90dc-157">Testando o cmdlet</span><span class="sxs-lookup"><span data-stu-id="e90dc-157">Testing the Cmdlet</span></span>

<span data-ttu-id="e90dc-158">Quando o cmdlet tiver sido registrado com o Windows PowerShell, teste-o executando-o na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="e90dc-158">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="e90dc-159">Aqui estão alguns testes que mostram como os `ProcessId` `InputObject` parâmetros e podem ser usados para testar seus conjuntos de parâmetros para interromper um processo.</span><span class="sxs-lookup"><span data-stu-id="e90dc-159">Here are some tests that show how the `ProcessId` and `InputObject` parameters can be used to test their parameter sets to stop a process.</span></span>

- <span data-ttu-id="e90dc-160">Com o Windows PowerShell iniciado, execute o cmdlet Stop-Proc com o `ProcessId` parâmetro definido para interromper um processo com base em seu identificador.</span><span class="sxs-lookup"><span data-stu-id="e90dc-160">With Windows PowerShell started, run the Stop-Proc cmdlet with the `ProcessId` parameter set to stop a process based on its identifier.</span></span> <span data-ttu-id="e90dc-161">Nesse caso, o cmdlet está usando o `ProcessId` conjunto de parâmetros para parar o processo.</span><span class="sxs-lookup"><span data-stu-id="e90dc-161">In this case, the cmdlet is using the `ProcessId` parameter set to stop the process.</span></span>

  ```
  PS> stop-proc -Id 444
  Confirm
  Are you sure you want to perform this action?
  Performing operation "stop-proc" on Target "notepad (444)".
  [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
  ```

- <span data-ttu-id="e90dc-162">Com o Windows PowerShell iniciado, execute o cmdlet Stop-Proc com o `InputObject` parâmetro definido para parar os processos no objeto do bloco de notas recuperado pelo `Get-Process` comando.</span><span class="sxs-lookup"><span data-stu-id="e90dc-162">With Windows PowerShell started, run the Stop-Proc cmdlet with the `InputObject` parameter set to stop processes on the Notepad object retrieved by the `Get-Process` command.</span></span>

  ```
  PS> get-process notepad | stop-proc
  Confirm
  Are you sure you want to perform this action?
  Performing operation "stop-proc" on Target "notepad (444)".
  [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
  ```

## <a name="see-also"></a><span data-ttu-id="e90dc-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e90dc-163">See Also</span></span>

[<span data-ttu-id="e90dc-164">Criar um cmdlet que modifica o sistema</span><span class="sxs-lookup"><span data-stu-id="e90dc-164">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="e90dc-165">Como criar um cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e90dc-165">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="e90dc-166">[Estendendo tipos de objeto e formatação](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e90dc-166">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="e90dc-167">[Como registrar cmdlets, provedores e aplicativos host](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e90dc-167">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="e90dc-168">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e90dc-168">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
