---
title: Comunicação remota do PowerShell
description: Há várias maneiras diferentes de executar comandos em computadores remotos no PowerShell.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: ee83af41b53b254dd3dd993931333edac2f44f5a
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438207"
---
# <a name="chapter-8---powershell-remoting"></a>Capítulo 8 – Comunicação remota do PowerShell

O PowerShell tem várias maneiras diferentes de executar comandos em computadores remotos. No último capítulo, você viu como consultar a WMI remotamente usando os cmdlets do CIM. O PowerShell também inclui vários cmdlets que têm um parâmetro interno **ComputerName**.

Conforme mostrado no exemplo a seguir, `Get-Command` pode ser usado com o parâmetro **ParameterName** para determinar quais comandos têm um parâmetro **ComputerName**.

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

Comandos como `Get-Process` e `Get-Hotfix` têm um parâmetro **ComputerName**. Essa não é a direção de longo prazo que a Microsoft está seguindo para executar comandos em computadores remotos. Mesmo que você encontre um comando que tenha um parâmetro **ComputerName**, é provável que você precise especificar credenciais alternativas e ele não terá um parâmetro **Credencial**. E se você decidir executar o PowerShell de uma conta com privilégios elevados, um firewall entre você e o computador remoto poderá bloquear a solicitação.

Para usar os comandos de comunicação remota do PowerShell que são demonstrados neste capítulo, a comunicação remota do PowerShell deve ser habilitada no computador remoto. Use o cmdlet `Enable-PSRemoting` para habilitar a comunicação remota do PowerShell.

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

## <a name="one-to-one-remoting"></a>Comunicação remota de um para um

Se você quer que sua sessão remota seja interativa, a comunicação remota de um para um é para você.
Esse tipo de comunicação remota é fornecido por meio do cmdlet `Enter-PSSession`.

No último capítulo, armazenei minhas credenciais de administrador de domínio em uma variável chamada `$Cred`. Se você ainda não tiver feito isso, vá em frente e armazene suas credenciais de administrador de domínio na variável `$Cred`.

Isso permite que você insira as credenciais uma vez e use-as por comando, desde que sua sessão atual do PowerShell esteja ativa.

```powershell
$Cred = Get-Credential
```

Crie uma sessão de comunicação remota de um para um do PowerShell para o controlador de domínio chamado dc01.

```powershell
Enter-PSSession -ComputerName dc01 -Credential $Cred
```

```Output
[dc01]: PS C:\Users\Administrator\Documents>
```

Observe que, no exemplo anterior, o prompt do PowerShell é precedido por `[dc01]`. Isso significa que você está em uma sessão interativa do PowerShell para o computador remoto chamado dc01. Todos os comandos são executados em dc01, não no computador local. Além disso, saiba que você só tem acesso aos comandos do PowerShell que existem no computador remoto e não àqueles no computador local. Em outras palavras, se você tiver instalado módulos adicionais em seu computador, eles não estarão acessíveis no computador remoto.

Quando você estiver conectado a um computador remoto por meio de uma sessão de comunicação remota do PowerShell interativa de um para um, você estará efetivamente trabalhando no computador remoto. Os objetos são normais, assim como aqueles com os quais você está trabalhando em todo o livro.

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

Quando você terminar de trabalhar com o computador remoto, saia da sessão de comunicação remota de um para um usando o cmdlet `Exit-PSSession`.

```powershell
[dc01]:  Exit-PSSession
```

## <a name="one-to-many-remoting"></a>Comunicação remota de um para muitos

Às vezes pode ser necessário executar uma tarefa interativamente em um computador remoto. Porém, a comunicação remota é muito mais potente ao executar uma tarefa em vários computadores remotos ao mesmo tempo. Use o cmdlet `Invoke-Command` para executar um comando em um ou mais computadores remotos ao mesmo tempo.

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

No exemplo anterior, foram consultados três servidores quanto ao status do serviço de Horário do Windows. O cmdlet `Get-Service` foi colocado dentro do bloco de script de `Invoke-Command`. `Get-Service` na verdade, é executado no computador remoto e os resultados são retornados para o computador local como objetos desserializados.

O direcionamento do comando anterior para `Get-Member` mostra que os resultados são, de fato, objetos desserializados.

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

Observe que a maioria dos métodos está ausente em objetos desserializados. Isso significa que eles não são objetos dinâmicos; são inertes. Não é possível iniciar nem parar um serviço usando um objeto desserializado porque ele é um instantâneo do estado desse objeto do ponto em que o comando foi executado no computador remoto.

Isso não significa que você não pode iniciar ou parar um serviço usando um método com `Invoke-Command` no entanto. Apenas significa que o método deve ser chamado na sessão remota.

Vou parar o serviço de Horário do Windows em todos os três desses servidores remotos usando o método **Stop()** para provar esse ponto.

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

Conforme mencionado em um capítulo anterior, se existir um cmdlet para realizar uma tarefa, recomendo usá-lo em vez de usar um método. No cenário anterior, recomendo usar o cmdlet `Stop-Service` em vez do método stop. Optei por usar o método **Stop()** para provar um ponto, uma vez que muitas pessoas têm a concepção errada de que os métodos não podem ser chamados ao usar a comunicação remota do PowerShell. Eles não podem ser chamados no objeto retornado porque são desserializados, mas podem ser chamados na própria sessão remota.

## <a name="powershell-sessions"></a>Sessões do PowerShell

No último exemplo da seção anterior, executei dois comandos usando o cmdlet `Invoke-Command`.
Isso significa que duas sessões separadas precisavam ser configuradas e interrompidas para executar esses dois comandos.

De modo semelhante às sessões CIM discutidas no Capítulo 7, uma sessão do PowerShell para um computador remoto pode ser usada para executar vários comandos no computador remoto sem a sobrecarga de uma nova sessão para cada comando individual.

Crie uma sessão do PowerShell para cada um dos três computadores com os quais estamos trabalhando neste capítulo, DC01, SQL02 e WEB01.

```powershell
$Session = New-PSSession -ComputerName dc01, sql02, web01 -Credential $Cred
```

Agora, use a variável chamada `$Session` para iniciar o serviço Horário do Windows usando um método e verifique o status do serviço.

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

Quando a sessão é criada usando credenciais alternativas, não é mais necessário especificar as credenciais sempre que um comando é executado.

Quando terminar de usar as sessões, remova-as.

```powershell
Get-PSSession | Remove-PSSession
```

## <a name="summary"></a>Resumo

Neste capítulo, você aprendeu sobre a comunicação remota do PowerShell, como executar comandos em uma sessão interativa com um computador remoto e como executar comandos em vários computadores usando a comunicação remota de um para muitos. Você também aprendeu os benefícios de usar uma sessão do PowerShell ao executar vários comandos no mesmo computador remoto.

## <a name="review"></a>Revisão

1. Como habilitar a comunicação remota do PowerShell?
1. Qual é o comando do PowerShell para iniciar uma sessão interativa com um computador remoto?
1. Qual que é um benefício de usar uma sessão de comunicação remota do PowerShell em vez de especificar apenas o nome do computador com cada comando?
1. Uma sessão de comunicação remota do PowerShell pode ser usada com uma sessão de comunicação remota de um para um?
1. Qual é a diferença no tipo de objetos que são retornados por cmdlets versus aqueles retornados ao executar esses mesmos cmdlets em computadores remotos com `Invoke-Command`?

## <a name="recommended-reading"></a>Leitura recomendada

- [about_Remote][]
- [about_Remote_FAQ][]
- [about_Remote_Output][]
- [about_Remote_Requirements][]
- [about_Remote_Troubleshooting][]
- [about_Remote_Variables][]

<!-- link references -->
[about_Remote]: /powershell/module/microsoft.powershell.core/about/about_remote
[about_Remote_FAQ]: /powershell/module/microsoft.powershell.core/about/about_remote_faq
[about_Remote_Output]: /powershell/module/microsoft.powershell.core/about/about_remote_output
[about_Remote_Requirements]: /powershell/module/microsoft.powershell.core/about/about_remote_requirements
[about_Remote_Troubleshooting]: /powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting
[about_Remote_Variables]: /powershell/module/microsoft.powershell.core/about/about_remote_variables
[Breaking changes in PowerShell 6.0]: /powershell/scripting/whats-new/breaking-changes-ps6#remove--protocol-from--computer-cmdlets-5277
