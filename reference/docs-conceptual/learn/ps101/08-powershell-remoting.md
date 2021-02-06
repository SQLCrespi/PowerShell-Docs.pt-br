---
title: Comunicação remota do PowerShell
description: Há várias maneiras diferentes de executar comandos em computadores remotos no PowerShell.
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 0e467a41282b261c56a89578dbc841725f59a6e0
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "99603736"
---
# <a name="chapter-8---powershell-remoting"></a><span data-ttu-id="8e8fc-103">Capítulo 8 – Comunicação remota do PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e8fc-103">Chapter 8 - PowerShell remoting</span></span>

<span data-ttu-id="8e8fc-104">O PowerShell tem várias maneiras diferentes de executar comandos em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-104">PowerShell has many different ways to run commands against remote computers.</span></span> <span data-ttu-id="8e8fc-105">No último capítulo, você viu como consultar a WMI remotamente usando os cmdlets do CIM.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-105">In the last chapter, you saw how to remotely query WMI using the CIM cmdlets.</span></span> <span data-ttu-id="8e8fc-106">O PowerShell também inclui vários cmdlets que têm um parâmetro interno **ComputerName**.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-106">PowerShell also includes several cmdlets that have a built-in **ComputerName** parameter.</span></span>

<span data-ttu-id="8e8fc-107">Conforme mostrado no exemplo a seguir, `Get-Command` pode ser usado com o parâmetro **ParameterName** para determinar quais comandos têm um parâmetro **ComputerName**.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-107">As shown in the following example, `Get-Command` can be used with the **ParameterName** parameter to determine what commands have a **ComputerName** parameter.</span></span>

```powershell
Get-Command -ParameterName ComputerName
```

```Output
CommandType Name                        Version Source
----------- ----                        ------- ------
Cmdlet      Connect-PSSession           7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Connect-WSMan               7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Disconnect-WSMan            7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Enter-PSSession             7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Get-CimAssociatedInstance   7.0.0.0 CimCmdlets
Cmdlet      Get-CimClass                7.0.0.0 CimCmdlets
Cmdlet      Get-CimInstance             7.0.0.0 CimCmdlets
Cmdlet      Get-CimSession              7.0.0.0 CimCmdlets
Cmdlet      Get-Counter                 7.0.0.0 Microsoft.PowerShell.Diagnostics
Cmdlet      Get-HotFix                  7.0.0.0 Microsoft.PowerShell.Management
Cmdlet      Get-PSSession               7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Get-WinEvent                7.0.0.0 Microsoft.PowerShell.Diagnostics
Cmdlet      Get-WSManInstance           7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Invoke-CimMethod            7.0.0.0 CimCmdlets
Cmdlet      Invoke-Command              7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Invoke-WSManAction          7.0.0.0 Microsoft.WSMan.Management
Cmdlet      New-CimInstance             7.0.0.0 CimCmdlets
Cmdlet      New-CimSession              7.0.0.0 CimCmdlets
Cmdlet      New-PSSession               7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      New-WSManInstance           7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Receive-Job                 7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Receive-PSSession           7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Register-CimIndicationEvent 7.0.0.0 CimCmdlets
Cmdlet      Remove-CimInstance          7.0.0.0 CimCmdlets
Cmdlet      Remove-CimSession           7.0.0.0 CimCmdlets
Cmdlet      Remove-PSSession            7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Remove-WSManInstance        7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Rename-Computer             7.0.0.0 Microsoft.PowerShell.Management
Cmdlet      Restart-Computer            7.0.0.0 Microsoft.PowerShell.Management
Cmdlet      Send-MailMessage            7.0.0.0 Microsoft.PowerShell.Utility
Cmdlet      Set-CimInstance             7.0.0.0 CimCmdlets
Cmdlet      Set-WSManInstance           7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Stop-Computer               7.0.0.0 Microsoft.PowerShell.Management
Cmdlet      Test-Connection             7.0.0.0 Microsoft.PowerShell.Management
Cmdlet      Test-WSMan                  7.0.0.0 Microsoft.WSMan.Management
```

<span data-ttu-id="8e8fc-108">Comandos como `Get-Process` e `Get-Hotfix` têm um parâmetro **ComputerName**.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-108">Commands such as `Get-Process` and `Get-Hotfix` have a **ComputerName** parameter.</span></span> <span data-ttu-id="8e8fc-109">Essa não é a direção de longo prazo que a Microsoft está seguindo para executar comandos em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-109">This isn't the long-term direction that Microsoft is heading for running commands against remote computers.</span></span> <span data-ttu-id="8e8fc-110">Mesmo que você encontre um comando que tenha um parâmetro **ComputerName**, é provável que você precise especificar credenciais alternativas e ele não terá um parâmetro **Credencial**.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-110">Even if you find a command that has a **ComputerName** parameter, chances are that you'll need to specify alternate credentials and it won't have a **Credential** parameter.</span></span> <span data-ttu-id="8e8fc-111">E se você decidir executar o PowerShell de uma conta com privilégios elevados, um firewall entre você e o computador remoto poderá bloquear a solicitação.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-111">And if you decided to run PowerShell from an elevated account, a firewall between you and the remote computer can block the request.</span></span>

<span data-ttu-id="8e8fc-112">Para usar os comandos de comunicação remota do PowerShell que são demonstrados neste capítulo, a comunicação remota do PowerShell deve ser habilitada no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-112">To use the PowerShell remoting commands that are demonstrated in this chapter, PowerShell remoting must be enabled on the remote computer.</span></span> <span data-ttu-id="8e8fc-113">Use o cmdlet `Enable-PSRemoting` para habilitar a comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-113">Use the `Enable-PSRemoting` cmdlet to enable PowerShell remoting.</span></span>

```powershell
Enable-PSRemoting
```

```Output
WinRM has been updated to receive requests.
WinRM service type changed successfully.
WinRM service started.

WinRM has been updated for remote management.
WinRM firewall exception enabled.
```

## <a name="one-to-one-remoting"></a><span data-ttu-id="8e8fc-114">Comunicação remota de um para um</span><span class="sxs-lookup"><span data-stu-id="8e8fc-114">One-To-One Remoting</span></span>

<span data-ttu-id="8e8fc-115">Se você quer que sua sessão remota seja interativa, a comunicação remota de um para um é para você.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-115">If you want your remote session to be interactive, then one-to-one remoting is what you want.</span></span>
<span data-ttu-id="8e8fc-116">Esse tipo de comunicação remota é fornecido por meio do cmdlet `Enter-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-116">This type of remoting is provided via the `Enter-PSSession` cmdlet.</span></span>

<span data-ttu-id="8e8fc-117">No último capítulo, armazenei minhas credenciais de administrador de domínio em uma variável chamada `$Cred`.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-117">In the last chapter, I stored my domain admin credentials in a variable named `$Cred`.</span></span> <span data-ttu-id="8e8fc-118">Se você ainda não tiver feito isso, vá em frente e armazene suas credenciais de administrador de domínio na variável `$Cred`.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-118">If you haven't already done so, go ahead and store your domain admin credentials in the `$Cred` variable.</span></span>

<span data-ttu-id="8e8fc-119">Isso permite que você insira as credenciais uma vez e use-as por comando, desde que sua sessão atual do PowerShell esteja ativa.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-119">This allows you to enter the credentials once and use them on a per command basis as long as your current PowerShell session is active.</span></span>

```powershell
$Cred = Get-Credential
```

<span data-ttu-id="8e8fc-120">Crie uma sessão de comunicação remota de um para um do PowerShell para o controlador de domínio chamado dc01.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-120">Create a one-to-one PowerShell remoting session to the domain controller named dc01.</span></span>

```powershell
Enter-PSSession -ComputerName dc01 -Credential $Cred
```

```Output
[dc01]: PS C:\Users\Administrator\Documents>
```

<span data-ttu-id="8e8fc-121">Observe que, no exemplo anterior, o prompt do PowerShell é precedido por `[dc01]`.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-121">Notice that in the previous example that the PowerShell prompt is preceded by `[dc01]`.</span></span> <span data-ttu-id="8e8fc-122">Isso significa que você está em uma sessão interativa do PowerShell para o computador remoto chamado dc01.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-122">This means you're in an interactive PowerShell session to the remote computer named dc01.</span></span> <span data-ttu-id="8e8fc-123">Todos os comandos são executados em dc01, não no computador local.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-123">Any commands you execute run on dc01, not on your local computer.</span></span> <span data-ttu-id="8e8fc-124">Além disso, saiba que você só tem acesso aos comandos do PowerShell que existem no computador remoto e não àqueles no computador local.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-124">Also, keep in mind that you only have access to the PowerShell commands that exist on the remote computer and not the ones on your local computer.</span></span> <span data-ttu-id="8e8fc-125">Em outras palavras, se você tiver instalado módulos adicionais em seu computador, eles não estarão acessíveis no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-125">In other words, if you've installed additional modules on your computer, they aren't accessible on the remote computer.</span></span>

<span data-ttu-id="8e8fc-126">Quando você estiver conectado a um computador remoto por meio de uma sessão de comunicação remota do PowerShell interativa de um para um, você estará efetivamente trabalhando no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-126">When you're connected to a remote computer via a one-to-one interactive PowerShell remoting session, you're effectively sitting at the remote computer.</span></span> <span data-ttu-id="8e8fc-127">Os objetos são normais, assim como aqueles com os quais você está trabalhando em todo o livro.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-127">The objects are normal objects just like the ones you've been working with throughout this entire book.</span></span>

```powershell
[dc01]:  Get-Process | Get-Member
```

```Output
   TypeName: System.Diagnostics.Process

Name                       MemberType     Definition
----                       ----------     ----------
Handles                    AliasProperty  Handles = Handlecount
Name                       AliasProperty  Name = ProcessName
NPM                        AliasProperty  NPM = NonpagedSystemMemorySize64
PM                         AliasProperty  PM = PagedMemorySize64
SI                         AliasProperty  SI = SessionId
VM                         AliasProperty  VM = VirtualMemorySize64
WS                         AliasProperty  WS = WorkingSet64
Disposed                   Event          System.EventHandler Disposed(System.Object, ...
ErrorDataReceived          Event          System.Diagnostics.DataReceivedEventHandler ...
Exited                     Event          System.EventHandler Exited(System.Object, Sy...
OutputDataReceived         Event          System.Diagnostics.DataReceivedEventHandler ...
BeginErrorReadLine         Method         void BeginErrorReadLine()
BeginOutputReadLine        Method         void BeginOutputReadLine()
CancelErrorRead            Method         void CancelErrorRead()
CancelOutputRead           Method         void CancelOutputRead()
Close                      Method         void Close()
CloseMainWindow            Method         bool CloseMainWindow()
CreateObjRef               Method         System.Runtime.Remoting.ObjRef CreateObjRef(...
Dispose                    Method         void Dispose(), void IDisposable.Dispose()
Equals                     Method         bool Equals(System.Object obj)
GetHashCode                Method         int GetHashCode()
GetLifetimeService         Method         System.Object GetLifetimeService()
GetType                    Method         type GetType()
InitializeLifetimeService  Method         System.Object InitializeLifetimeService()
Kill                       Method         void Kill()
Refresh                    Method         void Refresh()
Start                      Method         bool Start()
ToString                   Method         string ToString()
WaitForExit                Method         bool WaitForExit(int milliseconds), void Wai...
WaitForInputIdle           Method         bool WaitForInputIdle(int milliseconds), boo...
__NounName                 NoteProperty   string __NounName=Process
BasePriority               Property       int BasePriority {get;}
Container                  Property       System.ComponentModel.IContainer Container {...
EnableRaisingEvents        Property       bool EnableRaisingEvents {get;set;}
ExitCode                   Property       int ExitCode {get;}
ExitTime                   Property       datetime ExitTime {get;}
Handle                     Property       System.IntPtr Handle {get;}
HandleCount                Property       int HandleCount {get;}
HasExited                  Property       bool HasExited {get;}
Id                         Property       int Id {get;}
MachineName                Property       string MachineName {get;}
MainModule                 Property       System.Diagnostics.ProcessModule MainModule ...
MainWindowHandle           Property       System.IntPtr MainWindowHandle {get;}
MainWindowTitle            Property       string MainWindowTitle {get;}
MaxWorkingSet              Property       System.IntPtr MaxWorkingSet {get;set;}
MinWorkingSet              Property       System.IntPtr MinWorkingSet {get;set;}
Modules                    Property       System.Diagnostics.ProcessModuleCollection M...
NonpagedSystemMemorySize   Property       int NonpagedSystemMemorySize {get;}
NonpagedSystemMemorySize64 Property       long NonpagedSystemMemorySize64 {get;}
PagedMemorySize            Property       int PagedMemorySize {get;}
PagedMemorySize64          Property       long PagedMemorySize64 {get;}
PagedSystemMemorySize      Property       int PagedSystemMemorySize {get;}
PagedSystemMemorySize64    Property       long PagedSystemMemorySize64 {get;}
PeakPagedMemorySize        Property       int PeakPagedMemorySize {get;}
PeakPagedMemorySize64      Property       long PeakPagedMemorySize64 {get;}
PeakVirtualMemorySize      Property       int PeakVirtualMemorySize {get;}
PeakVirtualMemorySize64    Property       long PeakVirtualMemorySize64 {get;}
PeakWorkingSet             Property       int PeakWorkingSet {get;}
PeakWorkingSet64           Property       long PeakWorkingSet64 {get;}
PriorityBoostEnabled       Property       bool PriorityBoostEnabled {get;set;}
PriorityClass              Property       System.Diagnostics.ProcessPriorityClass Prio...
PrivateMemorySize          Property       int PrivateMemorySize {get;}
PrivateMemorySize64        Property       long PrivateMemorySize64 {get;}
PrivilegedProcessorTime    Property       timespan PrivilegedProcessorTime {get;}
ProcessName                Property       string ProcessName {get;}
ProcessorAffinity          Property       System.IntPtr ProcessorAffinity {get;set;}
Responding                 Property       bool Responding {get;}
SafeHandle                 Property       Microsoft.Win32.SafeHandles.SafeProcessHandl...
SessionId                  Property       int SessionId {get;}
Site                       Property       System.ComponentModel.ISite Site {get;set;}
StandardError              Property       System.IO.StreamReader StandardError {get;}
StandardInput              Property       System.IO.StreamWriter StandardInput {get;}
StandardOutput             Property       System.IO.StreamReader StandardOutput {get;}
StartInfo                  Property       System.Diagnostics.ProcessStartInfo StartInf...
StartTime                  Property       datetime StartTime {get;}
SynchronizingObject        Property       System.ComponentModel.ISynchronizeInvoke Syn...
Threads                    Property       System.Diagnostics.ProcessThreadCollection T...
TotalProcessorTime         Property       timespan TotalProcessorTime {get;}
UserProcessorTime          Property       timespan UserProcessorTime {get;}
VirtualMemorySize          Property       int VirtualMemorySize {get;}
VirtualMemorySize64        Property       long VirtualMemorySize64 {get;}
WorkingSet                 Property       int WorkingSet {get;}
WorkingSet64               Property       long WorkingSet64 {get;}
PSConfiguration            PropertySet    PSConfiguration {Name, Id, PriorityClass, Fi...
PSResources                PropertySet    PSResources {Name, Id, Handlecount, WorkingS...
Company                    ScriptProperty System.Object Company {get=$this.Mainmodule....
CPU                        ScriptProperty System.Object CPU {get=$this.TotalProcessorT...
Description                ScriptProperty System.Object Description {get=$this.Mainmod...
FileVersion                ScriptProperty System.Object FileVersion {get=$this.Mainmod...
Path                       ScriptProperty System.Object Path {get=$this.Mainmodule.Fil...
Product                    ScriptProperty System.Object Product {get=$this.Mainmodule....
ProductVersion             ScriptProperty System.Object ProductVersion {get=$this.Main...
[dc01]:
```

<span data-ttu-id="8e8fc-128">Quando você terminar de trabalhar com o computador remoto, saia da sessão de comunicação remota de um para um usando o cmdlet `Exit-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-128">When you're done working with the remote computer, exit the one-to-one remoting session by using the `Exit-PSSession` cmdlet.</span></span>

```powershell
[dc01]:  Exit-PSSession
```

## <a name="one-to-many-remoting"></a><span data-ttu-id="8e8fc-129">Comunicação remota de um para muitos</span><span class="sxs-lookup"><span data-stu-id="8e8fc-129">One-To-Many Remoting</span></span>

<span data-ttu-id="8e8fc-130">Às vezes pode ser necessário executar uma tarefa interativamente em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-130">Sometimes you may need to perform a task interactively on a remote computer.</span></span> <span data-ttu-id="8e8fc-131">Porém, a comunicação remota é muito mais potente ao executar uma tarefa em vários computadores remotos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-131">But remoting is much more powerful when performing a task on multiple remote computers at the same time.</span></span> <span data-ttu-id="8e8fc-132">Use o cmdlet `Invoke-Command` para executar um comando em um ou mais computadores remotos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-132">Use the `Invoke-Command` cmdlet to run a command against one or more remote computers at the same time.</span></span>

```powershell
Invoke-Command -ComputerName dc01, sql02, web01 {Get-Service -Name W32time} -Credential $Cred
```

```Output
Status   Name        DisplayName       PSComputerName
------   ----        -----------       --------------
Running  W32time     Windows Time      web01
Start... W32time     Windows Time      dc01
Running  W32time     Windows Time      sql02
```

<span data-ttu-id="8e8fc-133">No exemplo anterior, foram consultados três servidores quanto ao status do serviço de Horário do Windows.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-133">In the previous example, three servers were queried for the status of the Windows Time service.</span></span> <span data-ttu-id="8e8fc-134">O cmdlet `Get-Service` foi colocado dentro do bloco de script de `Invoke-Command`.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-134">The `Get-Service` cmdlet was placed inside the script block of `Invoke-Command`.</span></span> <span data-ttu-id="8e8fc-135">`Get-Service` na verdade, é executado no computador remoto e os resultados são retornados para o computador local como objetos desserializados.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-135">`Get-Service` actually runs on the remote computer and the results are returned to your local computer as deserialized objects.</span></span>

<span data-ttu-id="8e8fc-136">O direcionamento do comando anterior para `Get-Member` mostra que os resultados são, de fato, objetos desserializados.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-136">Piping the previous command to `Get-Member` shows that the results are indeed deserialized objects.</span></span>

```powershell
Invoke-Command -ComputerName dc01, sql02, web01 {Get-Service -Name W32time} -Credential $Cred | Get-Member
```

```Output
   TypeName: Deserialized.System.ServiceProcess.ServiceController

Name                MemberType   Definition
----                ----------   ----------
GetType             Method       type GetType()
ToString            Method       string ToString(), string ToString(string format, Sys...
Name                NoteProperty string Name=W32time
PSComputerName      NoteProperty string PSComputerName=sql02
PSShowComputerName  NoteProperty bool PSShowComputerName=True
RequiredServices    NoteProperty Deserialized.System.ServiceProcess.ServiceController[...
RunspaceId          NoteProperty guid RunspaceId=570313c4-ac84-4109-bf67-c6b33236af0a
CanPauseAndContinue Property     System.Boolean {get;set;}
CanShutdown         Property     System.Boolean {get;set;}
CanStop             Property     System.Boolean {get;set;}
Container           Property      {get;set;}
DependentServices   Property     Deserialized.System.ServiceProcess.ServiceController[...
DisplayName         Property     System.String {get;set;}
MachineName         Property     System.String {get;set;}
ServiceHandle       Property     System.String {get;set;}
ServiceName         Property     System.String {get;set;}
ServicesDependedOn  Property     Deserialized.System.ServiceProcess.ServiceController[...
ServiceType         Property     System.String {get;set;}
Site                Property      {get;set;}
StartType           Property     System.String {get;set;}
Status              Property     System.String {get;set;}
```

<span data-ttu-id="8e8fc-137">Observe que a maioria dos métodos está ausente em objetos desserializados.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-137">Notice that the majority of the methods are missing on deserialized objects.</span></span> <span data-ttu-id="8e8fc-138">Isso significa que eles não são objetos dinâmicos; são inertes.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-138">This means they're not live objects; they're inert.</span></span> <span data-ttu-id="8e8fc-139">Não é possível iniciar nem parar um serviço usando um objeto desserializado porque ele é um instantâneo do estado desse objeto do ponto em que o comando foi executado no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-139">You can't start or stop a service using a deserialized object because it's a snapshot of the state of that object the point when the command ran on the remote computer.</span></span>

<span data-ttu-id="8e8fc-140">Isso não significa que você não pode iniciar ou parar um serviço usando um método com `Invoke-Command` no entanto.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-140">That doesn't mean you can't start or stop a service using a method with `Invoke-Command` though.</span></span> <span data-ttu-id="8e8fc-141">Apenas significa que o método deve ser chamado na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-141">It just means that the method has to be called in the remote session.</span></span>

<span data-ttu-id="8e8fc-142">Vou parar o serviço de Horário do Windows em todos os três desses servidores remotos usando o método **Stop()** para provar esse ponto.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-142">I'll stop the Windows Time service on all three of those remote servers using the **Stop()** method to prove this point.</span></span>

```powershell
Invoke-Command -ComputerName dc01, sql02, web01 {(Get-Service -Name W32time).Stop()} -Credential $Cred
Invoke-Command -ComputerName dc01, sql02, web01 {Get-Service -Name W32time} -Credential $Cred
```

```Output
Status   Name        DisplayName       PSComputerName
------   ----        -----------       --------------
Running  W32time     Windows Time      web01
Start... W32time     Windows Time      dc01
Running  W32time     Windows Time      sql02
```

<span data-ttu-id="8e8fc-143">Conforme mencionado em um capítulo anterior, se existir um cmdlet para realizar uma tarefa, recomendo usá-lo em vez de usar um método.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-143">As mentioned in a previous chapter, if a cmdlet exists for accomplishing a task, I recommend using it instead of using a method.</span></span> <span data-ttu-id="8e8fc-144">No cenário anterior, recomendo usar o cmdlet `Stop-Service` em vez do método stop.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-144">In the previous scenario, I recommend using the `Stop-Service` cmdlet instead of the stop method.</span></span> <span data-ttu-id="8e8fc-145">Optei por usar o método **Stop()** para provar um ponto, uma vez que muitas pessoas têm a concepção errada de que os métodos não podem ser chamados ao usar a comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-145">I chose to use the **Stop()** method to prove a point since many people are under the misconception that methods can't be called when using PowerShell remoting.</span></span> <span data-ttu-id="8e8fc-146">Eles não podem ser chamados no objeto retornado porque são desserializados, mas podem ser chamados na própria sessão remota.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-146">They can't be called on the object that's returned because it's deserialized, but they can be called in the remote session itself.</span></span>

## <a name="powershell-sessions"></a><span data-ttu-id="8e8fc-147">Sessões do PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e8fc-147">PowerShell Sessions</span></span>

<span data-ttu-id="8e8fc-148">No último exemplo da seção anterior, executei dois comandos usando o cmdlet `Invoke-Command`.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-148">In the last example in the previous section, I ran two commands using the `Invoke-Command` cmdlet.</span></span>
<span data-ttu-id="8e8fc-149">Isso significa que duas sessões separadas precisavam ser configuradas e interrompidas para executar esses dois comandos.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-149">That means two separate sessions had to be set up and torn down to run those two commands.</span></span>

<span data-ttu-id="8e8fc-150">De modo semelhante às sessões CIM discutidas no Capítulo 7, uma sessão do PowerShell para um computador remoto pode ser usada para executar vários comandos no computador remoto sem a sobrecarga de uma nova sessão para cada comando individual.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-150">Similar to the CIM sessions discussed in Chapter 7, a PowerShell session to a remote computer can be used to run multiple commands against the remote computer without the overhead of a new session for each individual command.</span></span>

<span data-ttu-id="8e8fc-151">Crie uma sessão do PowerShell para cada um dos três computadores com os quais estamos trabalhando neste capítulo, DC01, SQL02 e WEB01.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-151">Create a PowerShell session to each of the three computers we've been working with in this chapter, DC01, SQL02, and WEB01.</span></span>

```powershell
$Session = New-PSSession -ComputerName dc01, sql02, web01 -Credential $Cred
```

<span data-ttu-id="8e8fc-152">Agora, use a variável chamada `$Session` para iniciar o serviço Horário do Windows usando um método e verifique o status do serviço.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-152">Now use the variable named `$Session` to start the Windows Time service using a method and check the status of the service.</span></span>

```powershell
Invoke-Command -Session $Session {(Get-Service -Name W32time).Start()}
Invoke-Command -Session $Session {Get-Service -Name W32time}
```

```Output
Status   Name        DisplayName       PSComputerName
------   ----        -----------       --------------
Running  W32time     Windows Time      web01
Start... W32time     Windows Time      dc01
Running  W32time     Windows Time      sql02
```

<span data-ttu-id="8e8fc-153">Quando a sessão é criada usando credenciais alternativas, não é mais necessário especificar as credenciais sempre que um comando é executado.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-153">Once the session is created using alternate credentials, it's no longer necessary to specify the credentials each time a command is run.</span></span>

<span data-ttu-id="8e8fc-154">Quando terminar de usar as sessões, remova-as.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-154">When you're finished using the sessions, be sure to remove them.</span></span>

```powershell
Get-PSSession | Remove-PSSession
```

## <a name="summary"></a><span data-ttu-id="8e8fc-155">Resumo</span><span class="sxs-lookup"><span data-stu-id="8e8fc-155">Summary</span></span>

<span data-ttu-id="8e8fc-156">Neste capítulo, você aprendeu sobre a comunicação remota do PowerShell, como executar comandos em uma sessão interativa com um computador remoto e como executar comandos em vários computadores usando a comunicação remota de um para muitos.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-156">In this chapter you've learned about PowerShell remoting, how to run commands in an interactive session with one remote computer, and how to run commands against multiple computers using one-to-many remoting.</span></span> <span data-ttu-id="8e8fc-157">Você também aprendeu os benefícios de usar uma sessão do PowerShell ao executar vários comandos no mesmo computador remoto.</span><span class="sxs-lookup"><span data-stu-id="8e8fc-157">You've also learned the benefits of using a PowerShell session when running multiple commands against the same remote computer.</span></span>

## <a name="review"></a><span data-ttu-id="8e8fc-158">Revisão</span><span class="sxs-lookup"><span data-stu-id="8e8fc-158">Review</span></span>

1. <span data-ttu-id="8e8fc-159">Como habilitar a comunicação remota do PowerShell?</span><span class="sxs-lookup"><span data-stu-id="8e8fc-159">How do you enable PowerShell remoting?</span></span>
1. <span data-ttu-id="8e8fc-160">Qual é o comando do PowerShell para iniciar uma sessão interativa com um computador remoto?</span><span class="sxs-lookup"><span data-stu-id="8e8fc-160">What is the PowerShell command for starting an interactive session with a remote computer?</span></span>
1. <span data-ttu-id="8e8fc-161">Qual que é um benefício de usar uma sessão de comunicação remota do PowerShell em vez de especificar apenas o nome do computador com cada comando?</span><span class="sxs-lookup"><span data-stu-id="8e8fc-161">What is a benefit of using a PowerShell remoting session versus just specifying the computer name with each command?</span></span>
1. <span data-ttu-id="8e8fc-162">Uma sessão de comunicação remota do PowerShell pode ser usada com uma sessão de comunicação remota de um para um?</span><span class="sxs-lookup"><span data-stu-id="8e8fc-162">Can a PowerShell remoting session be used with a one-to-one remoting session?</span></span>
1. <span data-ttu-id="8e8fc-163">Qual é a diferença no tipo de objetos que são retornados por cmdlets versus aqueles retornados ao executar esses mesmos cmdlets em computadores remotos com `Invoke-Command`?</span><span class="sxs-lookup"><span data-stu-id="8e8fc-163">What is the difference in the type of objects that are returned by cmdlets versus those returned when running those same cmdlets against remote computers with `Invoke-Command`?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="8e8fc-164">Leitura recomendada</span><span class="sxs-lookup"><span data-stu-id="8e8fc-164">Recommended Reading</span></span>

- <span data-ttu-id="8e8fc-165">[about_Remote][]</span><span class="sxs-lookup"><span data-stu-id="8e8fc-165">[about_Remote][]</span></span>
- <span data-ttu-id="8e8fc-166">[about_Remote_FAQ][]</span><span class="sxs-lookup"><span data-stu-id="8e8fc-166">[about_Remote_FAQ][]</span></span>
- <span data-ttu-id="8e8fc-167">[about_Remote_Output][]</span><span class="sxs-lookup"><span data-stu-id="8e8fc-167">[about_Remote_Output][]</span></span>
- <span data-ttu-id="8e8fc-168">[about_Remote_Requirements][]</span><span class="sxs-lookup"><span data-stu-id="8e8fc-168">[about_Remote_Requirements][]</span></span>
- <span data-ttu-id="8e8fc-169">[about_Remote_Troubleshooting][]</span><span class="sxs-lookup"><span data-stu-id="8e8fc-169">[about_Remote_Troubleshooting][]</span></span>
- <span data-ttu-id="8e8fc-170">[about_Remote_Variables][]</span><span class="sxs-lookup"><span data-stu-id="8e8fc-170">[about_Remote_Variables][]</span></span>

<!-- link references -->
[about_Remote]: /powershell/module/microsoft.powershell.core/about/about_remote
[about_Remote_FAQ]: /powershell/module/microsoft.powershell.core/about/about_remote_faq
[about_Remote_Output]: /powershell/module/microsoft.powershell.core/about/about_remote_output
[about_Remote_Requirements]: /powershell/module/microsoft.powershell.core/about/about_remote_requirements
[about_Remote_Troubleshooting]: /powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting
[about_Remote_Variables]: /powershell/module/microsoft.powershell.core/about/about_remote_variables
[Breaking changes in PowerShell 6.0]: /powershell/scripting/whats-new/breaking-changes-ps6#remove--protocol-from--computer-cmdlets-5277
