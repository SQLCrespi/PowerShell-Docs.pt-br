---
title: Adicionar mensagens de usuário ao seu Cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WriteWarning
- notifications, writing
- progress notification
- WriteVerbose
- Stop-Proc
- WriteProgress
- WriteDebug
- notifications, debug
- ProgressRecord
- samples, Stop-Proc cmdlet
- notifications, progress
- notifications, warning
- WriteObject
- WriteError
- verbose notification
- ProcessRecord
- notifications, verbose
- debug notification
- cmdlet, writing notifications
- warning
- code sample, user notifications
- user notifications
ms.assetid: 14c13acb-f0b7-4613-bc7d-c361d14da1a2
caps.latest.revision: 8
ms.openlocfilehash: 138c6a43937e72fffaa2a09243e500e9822e6111
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65854931"
---
# <a name="adding-user-messages-to-your-cmdlet"></a><span data-ttu-id="eb92b-102">Adicionar mensagens de usuário para o cmdlet</span><span class="sxs-lookup"><span data-stu-id="eb92b-102">Adding User Messages to Your Cmdlet</span></span>

<span data-ttu-id="eb92b-103">Cmdlets pode gravar vários tipos de mensagens que podem ser exibidos ao usuário no tempo de execução do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb92b-103">Cmdlets can write several kinds of messages that can be displayed to the user by the Windows PowerShell runtime.</span></span> <span data-ttu-id="eb92b-104">Essas mensagens incluem os seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="eb92b-104">These messages include the following types:</span></span>

- <span data-ttu-id="eb92b-105">Mensagens detalhadas que contêm informações gerais de usuário.</span><span class="sxs-lookup"><span data-stu-id="eb92b-105">Verbose messages that contain general user information.</span></span>

- <span data-ttu-id="eb92b-106">Mensagens que contêm informações de solução de problemas de depuração.</span><span class="sxs-lookup"><span data-stu-id="eb92b-106">Debug messages that contain troubleshooting information.</span></span>

- <span data-ttu-id="eb92b-107">Mensagens de aviso que contêm uma notificação de que o cmdlet está prestes a realizar uma operação que pode ter resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="eb92b-107">Warning messages that contain a notification that the cmdlet is about to perform an operation that can have unexpected results.</span></span>

- <span data-ttu-id="eb92b-108">Relatório de progresso, mensagens que contêm informações sobre a quantidade funcionar o cmdlet foi concluída ao executar uma operação que demora muito tempo.</span><span class="sxs-lookup"><span data-stu-id="eb92b-108">Progress report messages that contain information about how much work the cmdlet has completed when performing an operation that takes a long time.</span></span>

<span data-ttu-id="eb92b-109">Não há nenhum limite para o número de mensagens que seu cmdlet pode gravar ou o tipo de mensagens que grava seu cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eb92b-109">There are no limits to the number of messages that your cmdlet can write or the type of messages that your cmdlet writes.</span></span> <span data-ttu-id="eb92b-110">Cada mensagem é gravada, fazendo uma chamada específica de dentro da método do seu cmdlet de processamento de entrada.</span><span class="sxs-lookup"><span data-stu-id="eb92b-110">Each message is written by making a specific call from within the input processing method of your cmdlet.</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="eb92b-111">Definindo o Cmdlet</span><span class="sxs-lookup"><span data-stu-id="eb92b-111">Defining the Cmdlet</span></span>

<span data-ttu-id="eb92b-112">A primeira etapa na criação de cmdlet sempre é o cmdlet de nomenclatura e declarar a classe .NET que implementa o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eb92b-112">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="eb92b-113">Qualquer tipo de cmdlet pode gravar as notificações do usuário de seu métodos; de processamento de entrada em geral, você pode nomear este cmdlet usando qualquer verbo que indica quais modificações no sistema que executa o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eb92b-113">Any sort of cmdlet can write user notifications from its input processing methods; so, in general, you can name this cmdlet using any verb that indicates what system modifications the cmdlet performs.</span></span> <span data-ttu-id="eb92b-114">Para obter mais informações sobre os verbos aprovados do cmdlet, consulte [nomes de verbos de Cmdlet](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="eb92b-114">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="eb92b-115">O cmdlet Stop-Proc foi projetado para modificar o sistema; Portanto, o [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaração para a classe do .NET deve incluir o `SupportsShouldProcess` palavra-chave de atributo e definido como `true`.</span><span class="sxs-lookup"><span data-stu-id="eb92b-115">The Stop-Proc cmdlet is designed to modify the system; therefore, the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaration for the .NET class must include the `SupportsShouldProcess` attribute keyword and be set to `true`.</span></span>

<span data-ttu-id="eb92b-116">O código a seguir é a definição para essa classe do cmdlet Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="eb92b-116">The following code is the definition for this Stop-Proc cmdlet class.</span></span> <span data-ttu-id="eb92b-117">Para obter mais informações sobre essa definição, consulte [criação de um Cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="eb92b-117">For more information about this definition, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="eb92b-118">Definir parâmetros para modificação do sistema</span><span class="sxs-lookup"><span data-stu-id="eb92b-118">Defining Parameters for System Modification</span></span>

<span data-ttu-id="eb92b-119">O cmdlet Stop-Proc define três parâmetros: `Name`, `Force`, e `PassThru`.</span><span class="sxs-lookup"><span data-stu-id="eb92b-119">The Stop-Proc cmdlet defines three parameters: `Name`, `Force`, and `PassThru`.</span></span> <span data-ttu-id="eb92b-120">Para obter mais informações sobre como definir esses parâmetros, consulte [criação de um Cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="eb92b-120">For more information about defining these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

<span data-ttu-id="eb92b-121">Aqui está a declaração de parâmetro para o cmdlet Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="eb92b-121">Here is the parameter declaration for the Stop-Proc cmdlet.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="eb92b-122">Substituindo uma método de processamento de entrada</span><span class="sxs-lookup"><span data-stu-id="eb92b-122">Overriding an Input Processing Method</span></span>

<span data-ttu-id="eb92b-123">O cmdlet deve substituir uma método de processamento de entrada, geralmente será [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span><span class="sxs-lookup"><span data-stu-id="eb92b-123">Your cmdlet must override an input processing method, most often it will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="eb92b-124">Esse cmdlet Stop-Proc substitui o [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) o método de processamento de entrada.</span><span class="sxs-lookup"><span data-stu-id="eb92b-124">This Stop-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) input processing method.</span></span> <span data-ttu-id="eb92b-125">Nessa implementação do cmdlet Stop-Proc, as chamadas são feitas para gravar as mensagens detalhadas, mensagens de depuração e mensagens de aviso.</span><span class="sxs-lookup"><span data-stu-id="eb92b-125">In this implementation of the Stop-Proc cmdlet, calls are made to write verbose messages, debug messages, and warning messages.</span></span>

> [!NOTE]
> <span data-ttu-id="eb92b-126">Para obter mais informações sobre como esse método chama o [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) métodos, consulte [Criação de um Cmdlet que modifica o sistema](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="eb92b-126">For more information about how this method calls the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="writing-a-verbose-message"></a><span data-ttu-id="eb92b-127">Gravar uma mensagem detalhada</span><span class="sxs-lookup"><span data-stu-id="eb92b-127">Writing a Verbose Message</span></span>

<span data-ttu-id="eb92b-128">O [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) método é usado para gravar informações gerais de nível de usuário que está relacionadas a condições de erro específicas.</span><span class="sxs-lookup"><span data-stu-id="eb92b-128">The [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method is used to write general user-level information that is unrelated to specific error conditions.</span></span> <span data-ttu-id="eb92b-129">O administrador do sistema, em seguida, pode usar essas informações para continuar processando outros comandos.</span><span class="sxs-lookup"><span data-stu-id="eb92b-129">The system administrator can then use that information to continue processing other commands.</span></span> <span data-ttu-id="eb92b-130">Além disso, qualquer informação escrita usando esse método deve ser localizada, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="eb92b-130">In addition, any information written using this method should be localized as needed.</span></span>

<span data-ttu-id="eb92b-131">O código a seguir desse cmdlet Stop-Proc mostra duas chamadas para o [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) método de substituição do [System.Management.Automation.Cmdlet.ProcessRecord ](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) método.</span><span class="sxs-lookup"><span data-stu-id="eb92b-131">The following code from this Stop-Proc cmdlet shows two calls to the [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
message = String.Format("Attempting to stop process \"{0}\".", name);
WriteVerbose(message);
```

```csharp
message = String.Format("Stopped process \"{0}\", pid {1}.",
                        processName, process.Id);

WriteVerbose(message);
```

## <a name="writing-a-debug-message"></a><span data-ttu-id="eb92b-132">Gravar uma mensagem de depuração</span><span class="sxs-lookup"><span data-stu-id="eb92b-132">Writing a Debug Message</span></span>

<span data-ttu-id="eb92b-133">O [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) método é usado para gravar mensagens de depuração que podem ser usadas para solucionar problemas da operação do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eb92b-133">The [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method is used to write debug messages that can be used to troubleshoot the operation of the cmdlet.</span></span> <span data-ttu-id="eb92b-134">A chamada é feita de uma método de processamento de entrada.</span><span class="sxs-lookup"><span data-stu-id="eb92b-134">The call is made from an input processing method.</span></span>

> [!NOTE]
> <span data-ttu-id="eb92b-135">Windows PowerShell também define um `Debug` parâmetro que apresenta ambos detalhado e informações de depuração.</span><span class="sxs-lookup"><span data-stu-id="eb92b-135">Windows PowerShell also defines a `Debug` parameter that presents both verbose and debug information.</span></span> <span data-ttu-id="eb92b-136">Se seu cmdlet oferece suporte a esse parâmetro, ele não precisa chamar [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) no mesmo código que chama [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) .</span><span class="sxs-lookup"><span data-stu-id="eb92b-136">If your cmdlet supports this parameter, it does not need to call [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) in the same code that calls [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).</span></span>

<span data-ttu-id="eb92b-137">Duas seções de código do cmdlet Stop-Proc exemplo a seguir mostram as chamadas para o [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) método de substituição do [ System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) método.</span><span class="sxs-lookup"><span data-stu-id="eb92b-137">The following two sections of code from the sample Stop-Proc cmdlet show calls to the [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="eb92b-138">Essa mensagem de depuração é gravada imediatamente antes [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) é chamado.</span><span class="sxs-lookup"><span data-stu-id="eb92b-138">This debug message is written immediately before [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) is called.</span></span>

```csharp
message =
          String.Format("Acquired name for pid {0} : \"{1}\"",
                       process.Id, processName);
WriteDebug(message);
```

<span data-ttu-id="eb92b-139">Essa mensagem de depuração é gravada imediatamente antes [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) é chamado.</span><span class="sxs-lookup"><span data-stu-id="eb92b-139">This debug message is written immediately before [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) is called.</span></span>

```csharp
message =
         String.Format("Writing process \"{0}\" to pipeline",
         processName);
WriteDebug(message);
WriteObject(process);
```

<span data-ttu-id="eb92b-140">Windows PowerShell roteia automaticamente qualquer [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) chamadas para os cmdlets e infra-estrutura de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="eb92b-140">Windows PowerShell automatically routes any [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) calls to the tracing infrastructure and cmdlets.</span></span> <span data-ttu-id="eb92b-141">Isso permite que as chamadas de método a ser rastreado para o aplicativo de hospedagem, um arquivo ou um depurador sem precisar fazer qualquer trabalho adicional de desenvolvimento dentro do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eb92b-141">This allows the method calls to be traced to the hosting application, a file, or a debugger without your having to do any extra development work within the cmdlet.</span></span> <span data-ttu-id="eb92b-142">A entrada de linha de comando a seguir implementa uma operação de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="eb92b-142">The following command-line entry implements a tracing operation.</span></span>

<span data-ttu-id="eb92b-143">**PS > Parar rastreamento-expression-proc-arquivo proc.log-bloco de notas do comando stop-proc**</span><span class="sxs-lookup"><span data-stu-id="eb92b-143">**PS> trace-expression stop-proc -file proc.log -command stop-proc notepad**</span></span>

## <a name="writing-a-warning-message"></a><span data-ttu-id="eb92b-144">Gravar uma mensagem de aviso</span><span class="sxs-lookup"><span data-stu-id="eb92b-144">Writing a Warning Message</span></span>

<span data-ttu-id="eb92b-145">O [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) método é usado para gravar um aviso quando o cmdlet está prestes a realizar uma operação que pode ter um resultado inesperado, por exemplo, substituição de um arquivo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="eb92b-145">The [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method is used to write a warning when the cmdlet is about to perform an operation that might have an unexpected result, for example, overwriting a read-only file.</span></span>

<span data-ttu-id="eb92b-146">O código do cmdlet Stop-Proc exemplo a seguir mostra a chamada para o [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) método de substituição do [ System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) método.</span><span class="sxs-lookup"><span data-stu-id="eb92b-146">The following code from the sample Stop-Proc cmdlet shows the call to the [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
 if (criticalProcess)
 {
   message =
             String.Format("Stopping the critical process \"{0}\".",
                           processName);
   WriteWarning(message);
} // if (criticalProcess...
```

## <a name="writing-a-progress-message"></a><span data-ttu-id="eb92b-147">Gravar uma mensagem de progresso</span><span class="sxs-lookup"><span data-stu-id="eb92b-147">Writing a Progress Message</span></span>

<span data-ttu-id="eb92b-148">O [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) é usado para gravar mensagens de progresso quando operações de cmdlet levar um longo período de tempo para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="eb92b-148">The [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) is used to write progress messages when cmdlet operations take an extended amount of time to complete.</span></span> <span data-ttu-id="eb92b-149">Uma chamada para [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) passa um [progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord) objeto que é enviado ao aplicativo de hospedagem para renderização para o usuário.</span><span class="sxs-lookup"><span data-stu-id="eb92b-149">A call to [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) passes a [System.Management.Automation.Progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord) object that is sent to the hosting application for rendering to the user.</span></span>

> [!NOTE]
> <span data-ttu-id="eb92b-150">Esse cmdlet Stop-Proc não inclui uma chamada para o [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) método.</span><span class="sxs-lookup"><span data-stu-id="eb92b-150">This Stop-Proc cmdlet does not include a call to the [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) method.</span></span>

<span data-ttu-id="eb92b-151">O código a seguir é um exemplo de uma mensagem de progresso, escrito por um cmdlet que está tentando copiar um item.</span><span class="sxs-lookup"><span data-stu-id="eb92b-151">The following code is an example of a progress message written by a cmdlet that is attempting to copy an item.</span></span>

```csharp
int myId = 0;
string myActivity = "Copy-item: Copying *.* to c:\abc";
string myStatus = "Copying file bar.txt";
ProgressRecord pr = new ProgressRecord(myId, myActivity, myStatus);
WriteProgress(pr);

pr.RecordType = ProgressRecordType.Completed;
WriteProgress(pr);
```

## <a name="code-sample"></a><span data-ttu-id="eb92b-152">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="eb92b-152">Code Sample</span></span>

<span data-ttu-id="eb92b-153">Para o completo C# exemplos de código, consulte [StopProcessSample02 amostra](./stopprocesssample02-sample.md).</span><span class="sxs-lookup"><span data-stu-id="eb92b-153">For the complete C# sample code, see [StopProcessSample02 Sample](./stopprocesssample02-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="eb92b-154">Definir tipos de objeto e formatação</span><span class="sxs-lookup"><span data-stu-id="eb92b-154">Define Object Types and Formatting</span></span>

<span data-ttu-id="eb92b-155">Windows PowerShell passa informações entre cmdlets usando objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="eb92b-155">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="eb92b-156">Consequentemente, talvez seja necessário definir seu próprio tipo de um cmdlet, ou o cmdlet talvez precise estender um tipo existente fornecido pelo outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eb92b-156">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="eb92b-157">Para obter mais informações sobre como definir novos tipos ou estender os tipos existentes, consulte [estendendo tipos de objeto e formatação](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span><span class="sxs-lookup"><span data-stu-id="eb92b-157">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="eb92b-158">Criando o Cmdlet</span><span class="sxs-lookup"><span data-stu-id="eb92b-158">Building the Cmdlet</span></span>

<span data-ttu-id="eb92b-159">Depois de implementar um cmdlet, ele deve ser registrado com o Windows PowerShell por meio de um snap-in do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb92b-159">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="eb92b-160">Para obter mais informações sobre como registrar cmdlets, consulte [como registrar Cmdlets, provedores e aplicativos Host](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span><span class="sxs-lookup"><span data-stu-id="eb92b-160">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="eb92b-161">Testando o Cmdlet</span><span class="sxs-lookup"><span data-stu-id="eb92b-161">Testing the Cmdlet</span></span>

<span data-ttu-id="eb92b-162">Quando seu cmdlet tiver sido registrado com o Windows PowerShell, você pode testá-lo executando-o na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="eb92b-162">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="eb92b-163">Vamos testar o exemplo de cmdlet Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="eb92b-163">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="eb92b-164">Para obter mais informações sobre como usar os cmdlets da linha de comando, consulte o [Introdução ao Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="eb92b-164">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="eb92b-165">A entrada de linha de comando a seguir usa Proc Stop para interromper o processo de chamada "NOTEPAD", forneça notificações detalhadas e imprimir informações de depuração.</span><span class="sxs-lookup"><span data-stu-id="eb92b-165">The following command-line entry uses Stop-Proc to stop the process named "NOTEPAD", provide verbose notifications, and print debug information.</span></span>

    ```powershell
    PS> stop-proc -Name notepad -Verbose -Debug
    ```

<span data-ttu-id="eb92b-166">A seguinte saída é exibida.</span><span class="sxs-lookup"><span data-stu-id="eb92b-166">The following output appears.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="eb92b-167">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eb92b-167">See Also</span></span>

[<span data-ttu-id="eb92b-168">Criar um Cmdlet que modifica o sistema</span><span class="sxs-lookup"><span data-stu-id="eb92b-168">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="eb92b-169">Como criar um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb92b-169">How to Create a Windows PowerShell Cmdlet</span></span>](http://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[<span data-ttu-id="eb92b-170">Estendendo tipos de objeto e formatação</span><span class="sxs-lookup"><span data-stu-id="eb92b-170">Extending Object Types and Formatting</span></span>](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="eb92b-171">Como registrar Cmdlets, provedores e aplicativos de Host</span><span class="sxs-lookup"><span data-stu-id="eb92b-171">How to Register Cmdlets, Providers, and Host Applications</span></span>](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="eb92b-172">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb92b-172">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
