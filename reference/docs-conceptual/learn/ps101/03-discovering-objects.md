---
title: Discovering objects, properties, and methods (Descobrir objetos, propriedades e métodos)
description: Você não precisa ser um desenvolvedor para entender e usar objetos, propriedades e métodos.
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: f226221da7dd3b663f54cf23439dd7f945ed3a2a
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "99597383"
---
# <a name="chapter-3---discovering-objects-properties-and-methods"></a>Capítulo 3 – Como descobrir objetos, propriedades e métodos

Meu primeiro contato com os computadores foi um Commodore 64, mas meu primeiro computador moderno foi um clone do 286 12 MHz da IBM com 1 megabyte de memória, um disco rígido de 40 MB e uma unidade de disquete de 5-1/4 polegadas com um monitor CGA que executava o Microsoft DOS 3.3.

Muitos profissionais de TI, como eu mesmo, estão familiarizados com a linha de comando, mas quando se fala de objetos, propriedades e métodos, eles ficam paralisados e dizem "não sou um desenvolvedor". Adivinha? Você não precisa ser um desenvolvedor para ser bem-sucedido com o PowerShell. Não fique atrapalhado com a terminologia. Nem tudo pode fazer sentido no começo, mas depois de um pouco de experiência prática, você começará a ter aqueles momentos de inspiração. "Aha! É disso que o livro tratava."

Lembre-se de experimentar os exemplos no computador para obter uma experiência prática.

## <a name="requirements"></a>Requisitos

O módulo do Active Directory PowerShell é necessário para alguns dos exemplos mostrados neste capítulo.
Ele faz parte das Ferramentas de Administração de Servidor Remoto para Windows. Para a versão 1809 (ou superior) do Windows, as Ferramentas de Administração de Servidor Remoto são instaladas como um recurso do Windows.

- Para obter informações sobre como instalar as Ferramentas de Administração de Servidor Remoto, confira [Módulos de gerenciamento do Windows][].
- Para as versões mais antigas do Windows, confira [Ferramentas de Administração de Servidor Remoto para Windows][].

## <a name="get-member"></a>Get-Member

`Get-Member` ajuda você a descobrir quais objetos, propriedades e métodos estão disponíveis para os comandos.
Qualquer comando que produza a saída baseada em objeto pode ser direcionado para `Get-Member`. Uma propriedade é uma característica de um item. Sua carteira de motorista tem uma propriedade chamada cor dos olhos, e os valores mais comuns para essa propriedade são azul e castanho. Um método é uma ação que pode ser executada em um item. Continuando com o exemplo da carteira de motorista, um dos métodos é "Revoke", porque o departamento de trânsito pode revogar sua carteira de motorista.

### <a name="properties"></a>Propriedades

No exemplo a seguir, vou recuperar informações sobre o serviço de Tempo do Windows em execução no meu computador.

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

**Status**, **Name** e **DisplayName** são exemplos de propriedades, conforme mostrado no conjunto de resultados anterior. O valor da propriedade **Status** é `Running`, o valor da propriedade **Name** é `w32time` e o valor de **DisplayName** é `Windows Time`.

Agora vou direcionar o mesmo comando para `Get-Member`:

```powershell
Get-Service -Name w32time | Get-Member
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name                      MemberType    Definition
----                      ----------    ----------
Name                      AliasProperty Name = ServiceName
RequiredServices          AliasProperty RequiredServices = ServicesDependedOn
Disposed                  Event         System.EventHandler Disposed(System.Object, Sy...
Close                     Method        void Close()
Continue                  Method        void Continue()
CreateObjRef              Method        System.Runtime.Remoting.ObjRef CreateObjRef(ty...
Dispose                   Method        void Dispose(), void IDisposable.Dispose()
Equals                    Method        bool Equals(System.Object obj)
ExecuteCommand            Method        void ExecuteCommand(int command)
GetHashCode               Method        int GetHashCode()
GetLifetimeService        Method        System.Object GetLifetimeService()
GetType                   Method        type GetType()
InitializeLifetimeService Method        System.Object InitializeLifetimeService()
Pause                     Method        void Pause()
Refresh                   Method        void Refresh()
Start                     Method        void Start(), void Start(string[] args)
Stop                      Method        void Stop()
WaitForStatus             Method        void WaitForStatus(System.ServiceProcess.Servi...
CanPauseAndContinue       Property      bool CanPauseAndContinue {get;}
CanShutdown               Property      bool CanShutdown {get;}
CanStop                   Property      bool CanStop {get;}
Container                 Property      System.ComponentModel.IContainer Container {get;}
DependentServices         Property      System.ServiceProcess.ServiceController[] Depe...
DisplayName               Property      string DisplayName {get;set;}
MachineName               Property      string MachineName {get;set;}
ServiceHandle             Property      System.Runtime.InteropServices.SafeHandle Serv...
ServiceName               Property      string ServiceName {get;set;}
ServicesDependedOn        Property      System.ServiceProcess.ServiceController[] Serv...
ServiceType               Property      System.ServiceProcess.ServiceType ServiceType ...
Site                      Property      System.ComponentModel.ISite Site {get;set;}
StartType                 Property      System.ServiceProcess.ServiceStartMode StartTy...
Status                    Property      System.ServiceProcess.ServiceControllerStatus ...
ToString                  ScriptMethod  System.Object ToString();
```

A primeira linha dos resultados no exemplo anterior contém uma informação muito importante. **TypeName** informa que tipo de objeto foi retornado. Neste exemplo, um objeto **System.ServiceProcess.ServiceController** foi retornado. Em geral, isso é abreviado como a parte do **TypeName** logo após o último ponto; **ServiceController**, neste exemplo.

Depois de saber o tipo de objeto que um comando produz, você pode usar essas informações para localizar comandos que aceitem esse tipo de objeto como entrada.

```powershell
Get-Command -ParameterType ServiceController
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-Service                                        3.1.0.0    Microsof...
Cmdlet          Restart-Service                                    3.1.0.0    Microsof...
Cmdlet          Resume-Service                                     3.1.0.0    Microsof...
Cmdlet          Set-Service                                        3.1.0.0    Microsof...
Cmdlet          Start-Service                                      3.1.0.0    Microsof...
Cmdlet          Stop-Service                                       3.1.0.0    Microsof...
Cmdlet          Suspend-Service                                    3.1.0.0    Microsof...
```

Todos esses comandos têm um parâmetro que aceita um tipo de objeto **ServiceController** por pipeline, entrada de parâmetro ou ambos.

Observe que há mais propriedades do que são exibidas por padrão. Embora essas propriedades adicionais não sejam exibidas por padrão, elas podem ser selecionadas no pipeline, direcionando o comando para o cmdlet `Select-Object` e usando o parâmetro **Property**. O exemplo a seguir seleciona todas as propriedades direcionando os resultados de `Get-Service` para `Select-Object` e especificando o caractere curinga `*` como o valor do parâmetro **Property**.

```powershell
Get-Service -Name w32time | Select-Object -Property *
```

```Output
Name                : w32time
RequiredServices    : {}
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
DisplayName         : Windows Time
DependentServices   : {}
MachineName         : .
ServiceName         : w32time
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :
```

Propriedades específicas também podem ser selecionadas por meio de uma lista separada por vírgula para o valor do parâmetro **Property**.

```powershell
Get-Service -Name w32time | Select-Object -Property Status, Name, DisplayName, ServiceType
```

```Output
 Status Name    DisplayName        ServiceType
 ------ ----    -----------        -----------
Running w32time Windows Time Win32ShareProcess
```

Por padrão, quatro propriedades são retornadas em uma tabela, e cinco ou mais são retornadas em uma lista. Alguns comandos usam a formatação personalizada para substituir o número de propriedades exibidas por padrão em uma tabela.
Há vários cmdlets `Format-*` que podem ser usados para substituir manualmente esses padrões. Os mais comuns são `Format-Table` e `Format-List`, que serão abordados em um capítulo futuro.

Os caracteres curinga podem ser usados ao especificar os nomes de propriedades com `Select-Object`.

```powershell
Get-Service -Name w32time | Select-Object -Property Status, DisplayName, Can*
```

```powershell
Status              : Running
DisplayName         : Windows Time
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
```

No exemplo anterior, `Can*` foi usado como um dos valores do parâmetro **Property** para retornar todas as propriedades que começam com `Can`. Isso inclui **CanPauseAndContinue**, **CanShutdown** e **CanStop**.

### <a name="methods"></a>Métodos

Os métodos são uma ação que pode ser executada. Use o parâmetro **MemberType** para restringir os resultados de `Get-Member`, a fim de mostrar apenas os métodos de `Get-Service`.

```powershell
Get-Service -Name w32time | Get-Member -MemberType Method
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name                      MemberType Definition
----                      ---------- ----------
Close                     Method     void Close()
Continue                  Method     void Continue()
CreateObjRef              Method     System.Runtime.Remoting.ObjRef CreateObjRef(type ...
Dispose                   Method     void Dispose(), void IDisposable.Dispose()
Equals                    Method     bool Equals(System.Object obj)
ExecuteCommand            Method     void ExecuteCommand(int command)
GetHashCode               Method     int GetHashCode()
GetLifetimeService        Method     System.Object GetLifetimeService()
GetType                   Method     type GetType()
InitializeLifetimeService Method     System.Object InitializeLifetimeService()
Pause                     Method     void Pause()
Refresh                   Method     void Refresh()
Start                     Method     void Start(), void Start(string[] args)
Stop                      Method     void Stop()
WaitForStatus             Method     void WaitForStatus(System.ServiceProcess.ServiceC...
```

Como você pode ver, há muitos métodos. O método **Stop** pode ser usado para interromper um serviço Windows.

```powershell
(Get-Service -Name w32time).Stop()
```

Agora, para confirmar se o serviço de Tempo do Windows foi interrompido.

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  w32time            Windows Time
```

Raramente uso métodos, mas é importante saber um pouco a respeito deles. Há ocasiões em que você encontrará um comando `Get-*` sem um comando correspondente para modificar esse item.
Muitas vezes, um método pode ser usado para executar uma ação que o modifica. O cmdlet `Get-SqlAgentJob` no módulo do SQL Server PowerShell é um bom exemplo disso. O módulo é instalado como parte do [SSMS (SQL Server Management Studio)][SMSS]. Não existe nenhum cmdlet `Set-*` correspondente, mas um método pode ser usado para concluir a mesma tarefa.

Outro motivo para ter uma noção dos métodos é que muitos iniciantes pressupõem que alterações destrutivas não possam ser feitas com os comandos `Get-*`. Mas, de fato, eles poderão causar sérios problemas se forem usados de maneira inadequada.

Uma opção melhor será usar um cmdlet para executar a ação, se houver. Vá em frente e inicie o serviço de Tempo do Windows, mas, desta vez, use o cmdlet para iniciar os serviços.

```powershell
Get-Service -Name w32time | Start-Service -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

Por padrão, `Start-Service` não retorna nenhum resultado, assim como o método start de `Get-Service`.
No entanto, um dos benefícios do uso de um cmdlet é que, muitas vezes, o cmdlet oferece uma funcionalidade adicional que não está disponível em um método. No exemplo anterior, o parâmetro **PassThru** foi usado. Isso faz com que um cmdlet que normalmente não produz uma saída, produza uma saída.

Tenha cuidado ao fazer suposições sobre a saída de um cmdlet. Todos nós sabemos o que acontece quando fazemos suposições. Vou recuperar informações sobre o processo do PowerShell em execução no meu computador do ambiente de laboratório do Windows 10.

```powershell
Get-Process -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName
-------  ------    -----      -----     ------     --  -- -----------
    922      48   107984     140552       2.84   9020   1 powershell

```

Agora vou direcionar o mesmo comando para Get-Member:

```powershell
Get-Process -Name PowerShell | Get-Member
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
```

Observe que há mais propriedades listadas do que são exibidas por padrão. Várias propriedades padrão exibidas não aparecem como propriedades ao exibir os resultados de `Get-Member`. Isso ocorre porque muitos dos valores exibidos, como `NPM(K)`, `PM(K)`, `WS(K)` e `CPU(s)`, são propriedades calculadas. Para determinar os nomes das propriedades reais, o comando precisará ser direcionado para `Get-Member`.

Se um comando não produzir uma saída, ele não poderá ser redirecionado para `Get-Member`. Como `Start-Service` não produz nenhuma saída por padrão, ele gera um erro quando você tenta direcioná-lo para `Get-Member`.

```powershell
Start-Service -Name w32time | Get-Member
```

```Output
Get-Member : You must specify an object for the Get-Member cmdlet.
At line:1 char:31
+ Start-Service -Name w32time | Get-Member
+
    + CategoryInfo          : CloseError: (:) [Get-Member], InvalidOperationException
    + FullyQualifiedErrorId : NoObjectInGetMember,Microsoft.PowerShell.Commands.GetMembe
   rCommand
```

O parâmetro **PassThru** pode ser especificado com o cmdlet `Start-Service` para fazer com que ele produza uma saída, que é então direcionado para `Get-Member` sem erros.

```powershell
Start-Service -Name w32time -PassThru | Get-Member
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name                      MemberType    Definition
----                      ----------    ----------
Name                      AliasProperty Name = ServiceName
RequiredServices          AliasProperty RequiredServices = ServicesDependedOn
Disposed                  Event         System.EventHandler Disposed(System.Object, Sy...
Close                     Method        void Close()
Continue                  Method        void Continue()
CreateObjRef              Method        System.Runtime.Remoting.ObjRef CreateObjRef(ty...
Dispose                   Method        void Dispose(), void IDisposable.Dispose()
Equals                    Method        bool Equals(System.Object obj)
ExecuteCommand            Method        void ExecuteCommand(int command)
GetHashCode               Method        int GetHashCode()
GetLifetimeService        Method        System.Object GetLifetimeService()
GetType                   Method        type GetType()
InitializeLifetimeService Method        System.Object InitializeLifetimeService()
Pause                     Method        void Pause()
Refresh                   Method        void Refresh()
Start                     Method        void Start(), void Start(string[] args)
Stop                      Method        void Stop()
WaitForStatus             Method        void WaitForStatus(System.ServiceProcess.Servi...
CanPauseAndContinue       Property      bool CanPauseAndContinue {get;}
CanShutdown               Property      bool CanShutdown {get;}
CanStop                   Property      bool CanStop {get;}
Container                 Property      System.ComponentModel.IContainer Container {get;}
DependentServices         Property      System.ServiceProcess.ServiceController[] Depe...
DisplayName               Property      string DisplayName {get;set;}
MachineName               Property      string MachineName {get;set;}
ServiceHandle             Property      System.Runtime.InteropServices.SafeHandle Serv...
ServiceName               Property      string ServiceName {get;set;}
ServicesDependedOn        Property      System.ServiceProcess.ServiceController[] Serv...
ServiceType               Property      System.ServiceProcess.ServiceType ServiceType ...
Site                      Property      System.ComponentModel.ISite Site {get;set;}
StartType                 Property      System.ServiceProcess.ServiceStartMode StartTy...
Status                    Property      System.ServiceProcess.ServiceControllerStatus ...
ToString                  ScriptMethod  System.Object ToString();
```

A fim de ser direcionado para `Get-Member`, um comando precisa produzir uma saída baseada em objeto.

```powershell
Get-Service -Name w32time | Out-Host | Get-Member
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time

Get-Member : You must specify an object for the Get-Member cmdlet.
At line:1 char:40
+ Get-Service -Name w32time | Out-Host | Get-Member
+
    + CategoryInfo          : CloseError: (:) [Get-Member], InvalidOperationException
    + FullyQualifiedErrorId : NoObjectInGetMember,Microsoft.PowerShell.Commands.GetMemberCommand
```

`Out-Host` faz a gravação diretamente no host do PowerShell, mas não produz uma saída baseada em objeto para o pipeline. Portanto, ele não pode ser direcionado para `Get-Member`.

## <a name="active-directory"></a>Active Directory

> [!NOTE]
> As Ferramentas de Administração de Servidor Remoto listadas na seção de requisitos deste capítulo são necessárias para concluir esta seção. Além disso, conforme mencionado na introdução deste livro, o computador do ambiente de laboratório do Windows 10 precisa ser membro do domínio do ambiente de laboratório.

Use `Get-Command` com o parâmetro **Module** para determinar quais comandos foram adicionados como parte do módulo do Active Directory PowerShell quando as Ferramentas de Administração de Servidor Remoto foram instaladas.

```powershell
Get-Command -Module ActiveDirectory
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Add-ADCentralAccessPolicyMember                    1.0.0.0    ActiveDi...
Cmdlet          Add-ADComputerServiceAccount                       1.0.0.0    ActiveDi...
Cmdlet          Add-ADDomainControllerPasswordReplicationPolicy    1.0.0.0    ActiveDi...
Cmdlet          Add-ADFineGrainedPasswordPolicySubject             1.0.0.0    ActiveDi...
Cmdlet          Add-ADGroupMember                                  1.0.0.0    ActiveDi...
Cmdlet          Add-ADPrincipalGroupMembership                     1.0.0.0    ActiveDi...
Cmdlet          Add-ADResourcePropertyListMember                   1.0.0.0    ActiveDi...
Cmdlet          Clear-ADAccountExpiration                          1.0.0.0    ActiveDi...
Cmdlet          Clear-ADClaimTransformLink                         1.0.0.0    ActiveDi...
Cmdlet          Disable-ADAccount                                  1.0.0.0    ActiveDi...
...
```

Um total de 147 comandos foram adicionados como parte do módulo do Active Directory PowerShell. Alguns comandos desses comandos retornam apenas uma parte das propriedades disponíveis por padrão.

Você percebeu algo diferente sobre os nomes dos comandos deste módulo? A parte do substantivo dos comandos tem um prefixo AD. É comum ver isto nos comandos da maioria dos módulos. O prefixo foi criado para ajudar a prevenir conflitos de nomenclatura.

```powershell
Get-ADUser -Identity mike | Get-Member
```

```Output
   TypeName: Microsoft.ActiveDirectory.Management.ADUser

Name              MemberType            Definition
----              ----------            ----------
Contains          Method                bool Contains(string propertyName)
Equals            Method                bool Equals(System.Object obj)
GetEnumerator     Method                System.Collections.IDictionaryEnumerator GetEn...
GetHashCode       Method                int GetHashCode()
GetType           Method                type GetType()
ToString          Method                string ToString()
Item              ParameterizedProperty Microsoft.ActiveDirectory.Management.ADPropert...
DistinguishedName Property              System.String DistinguishedName {get;set;}
Enabled           Property              System.Boolean Enabled {get;set;}
GivenName         Property              System.String GivenName {get;set;}
Name              Property              System.String Name {get;}
ObjectClass       Property              System.String ObjectClass {get;set;}
ObjectGUID        Property              System.Nullable`1[[System.Guid, mscorlib, Vers...
SamAccountName    Property              System.String SamAccountName {get;set;}
SID               Property              System.Security.Principal.SecurityIdentifier S...
Surname           Property              System.String Surname {get;set;}
UserPrincipalName Property              System.String UserPrincipalName {get;set;}
```

Mesmo que você esteja vagamente familiarizado com o Active Directory, é provável que saiba que uma conta de usuário tem mais propriedades do que as mostradas neste exemplo.

O cmdlet `Get-ADUser` tem um parâmetro **Properties** que é usado para especificar as propriedades adicionais (não padrão) que você deseja retornar. A especificação do caractere curinga `*` retorna todas elas.

```powershell
Get-ADUser -Identity mike -Properties * | Get-Member
```

```Output
   TypeName: Microsoft.ActiveDirectory.Management.ADUser

Name                                 MemberType            Definition
----                                 ----------            ----------
Contains                             Method                bool Contains(string proper...
Equals                               Method                bool Equals(System.Object obj)
GetEnumerator                        Method                System.Collections.IDiction...
GetHashCode                          Method                int GetHashCode()
GetType                              Method                type GetType()
ToString                             Method                string ToString()
Item                                 ParameterizedProperty Microsoft.ActiveDirectory.M...
AccountExpirationDate                Property              System.DateTime AccountExpi...
accountExpires                       Property              System.Int64 accountExpires...
AccountLockoutTime                   Property              System.DateTime AccountLock...
AccountNotDelegated                  Property              System.Boolean AccountNotDe...
AllowReversiblePasswordEncryption    Property              System.Boolean AllowReversi...
AuthenticationPolicy                 Property              Microsoft.ActiveDirectory.M...
AuthenticationPolicySilo             Property              Microsoft.ActiveDirectory.M...
BadLogonCount                        Property              System.Int32 BadLogonCount ...
badPasswordTime                      Property              System.Int64 badPasswordTim...
badPwdCount                          Property              System.Int32 badPwdCount {g...
CannotChangePassword                 Property              System.Boolean CannotChange...
CanonicalName                        Property              System.String CanonicalName...
Certificates                         Property              Microsoft.ActiveDirectory.M...
City                                 Property              System.String City {get;set;}
CN                                   Property              System.String CN {get;}
codePage                             Property              System.Int32 codePage {get;...
Company                              Property              System.String Company {get;...
CompoundIdentitySupported            Property              Microsoft.ActiveDirectory.M...
Country                              Property              System.String Country {get;...
countryCode                          Property              System.Int32 countryCode {g...
Created                              Property              System.DateTime Created {get;}
createTimeStamp                      Property              System.DateTime createTimeS...
Deleted                              Property              System.Boolean Deleted {get;}
Department                           Property              System.String Department {g...
Description                          Property              System.String Description {...
DisplayName                          Property              System.String DisplayName {...
DistinguishedName                    Property              System.String Distinguished...
Division                             Property              System.String Division {get...
DoesNotRequirePreAuth                Property              System.Boolean DoesNotRequi...
dSCorePropagationData                Property              Microsoft.ActiveDirectory.M...
EmailAddress                         Property              System.String EmailAddress ...
EmployeeID                           Property              System.String EmployeeID {g...
EmployeeNumber                       Property              System.String EmployeeNumbe...
Enabled                              Property              System.Boolean Enabled {get...
Fax                                  Property              System.String Fax {get;set;}
GivenName                            Property              System.String GivenName {ge...
HomeDirectory                        Property              System.String HomeDirectory...
HomedirRequired                      Property              System.Boolean HomedirRequi...
HomeDrive                            Property              System.String HomeDrive {ge...
HomePage                             Property              System.String HomePage {get...
HomePhone                            Property              System.String HomePhone {ge...
Initials                             Property              System.String Initials {get...
instanceType                         Property              System.Int32 instanceType {...
isDeleted                            Property              System.Boolean isDeleted {g...
KerberosEncryptionType               Property              Microsoft.ActiveDirectory.M...
LastBadPasswordAttempt               Property              System.DateTime LastBadPass...
LastKnownParent                      Property              System.String LastKnownPare...
lastLogoff                           Property              System.Int64 lastLogoff {ge...
lastLogon                            Property              System.Int64 lastLogon {get...
LastLogonDate                        Property              System.DateTime LastLogonDa...
lastLogonTimestamp                   Property              System.Int64 lastLogonTimes...
LockedOut                            Property              System.Boolean LockedOut {g...
logonCount                           Property              System.Int32 logonCount {ge...
LogonWorkstations                    Property              System.String LogonWorkstat...
Manager                              Property              System.String Manager {get;...
MemberOf                             Property              Microsoft.ActiveDirectory.M...
MNSLogonAccount                      Property              System.Boolean MNSLogonAcco...
MobilePhone                          Property              System.String MobilePhone {...
Modified                             Property              System.DateTime Modified {g...
modifyTimeStamp                      Property              System.DateTime modifyTimeS...
msDS-User-Account-Control-Computed   Property              System.Int32 msDS-User-Acco...
Name                                 Property              System.String Name {get;}
nTSecurityDescriptor                 Property              System.DirectoryServices.Ac...
ObjectCategory                       Property              System.String ObjectCategor...
ObjectClass                          Property              System.String ObjectClass {...
ObjectGUID                           Property              System.Nullable`1[[System.G...
objectSid                            Property              System.Security.Principal.S...
Office                               Property              System.String Office {get;s...
OfficePhone                          Property              System.String OfficePhone {...
Organization                         Property              System.String Organization ...
OtherName                            Property              System.String OtherName {ge...
PasswordExpired                      Property              System.Boolean PasswordExpi...
PasswordLastSet                      Property              System.DateTime PasswordLas...
PasswordNeverExpires                 Property              System.Boolean PasswordNeve...
PasswordNotRequired                  Property              System.Boolean PasswordNotR...
POBox                                Property              System.String POBox {get;set;}
PostalCode                           Property              System.String PostalCode {g...
PrimaryGroup                         Property              System.String PrimaryGroup ...
primaryGroupID                       Property              System.Int32 primaryGroupID...
PrincipalsAllowedToDelegateToAccount Property              Microsoft.ActiveDirectory.M...
ProfilePath                          Property              System.String ProfilePath {...
ProtectedFromAccidentalDeletion      Property              System.Boolean ProtectedFro...
pwdAnswer                            Property              System.String pwdAnswer {ge...
pwdLastSet                           Property              System.Int64 pwdLastSet {ge...
pwdQuestion                          Property              System.String pwdQuestion {...
SamAccountName                       Property              System.String SamAccountNam...
sAMAccountType                       Property              System.Int32 sAMAccountType...
ScriptPath                           Property              System.String ScriptPath {g...
sDRightsEffective                    Property              System.Int32 sDRightsEffect...
ServicePrincipalNames                Property              Microsoft.ActiveDirectory.M...
SID                                  Property              System.Security.Principal.S...
SIDHistory                           Property              Microsoft.ActiveDirectory.M...
SmartcardLogonRequired               Property              System.Boolean SmartcardLog...
sn                                   Property              System.String sn {get;set;}
State                                Property              System.String State {get;set;}
StreetAddress                        Property              System.String StreetAddress...
Surname                              Property              System.String Surname {get;...
Title                                Property              System.String Title {get;set;}
TrustedForDelegation                 Property              System.Boolean TrustedForDe...
TrustedToAuthForDelegation           Property              System.Boolean TrustedToAut...
UseDESKeyOnly                        Property              System.Boolean UseDESKeyOnl...
userAccountControl                   Property              System.Int32 userAccountCon...
userCertificate                      Property              Microsoft.ActiveDirectory.M...
UserPrincipalName                    Property              System.String UserPrincipal...
uSNChanged                           Property              System.Int64 uSNChanged {get;}
uSNCreated                           Property              System.Int64 uSNCreated {get;}
whenChanged                          Property              System.DateTime whenChanged...
whenCreated                          Property              System.DateTime whenCreated...
```

Agora ficou melhor.

Você pode imaginar um motivo pelo qual as propriedades de uma conta de usuário do Active Directory serão tão limitadas por padrão? Imagine se você retornar todas as propriedades para cada conta de usuário no seu ambiente de produção do Active Directory. Considere a degradação do desempenho que você poderá causar, não apenas aos próprios controladores de domínio, mas também à sua rede. É duvidoso que você realmente precisará de todas as propriedades de qualquer modo. O retorno de todas as propriedades para uma só conta de usuário é perfeitamente aceitável quando você está tentando determinar quais propriedades existem.

Não é incomum executar um comando muitas vezes ao criar o protótipo dele. Se você pretende executar uma consulta enorme, consulte-a uma vez e armazene os resultados em uma variável. Em seguida, trabalhe com o conteúdo da variável em vez de usar repetidamente uma consulta cara.

```powershell
$Users = Get-ADUser -Identity mike -Properties *
```

Use o conteúdo da variável `$Users` em vez de executar o comando anterior várias vezes.
Tenha em mente que o conteúdo da variável não é atualizado quando são feitas alterações nesse usuário no Active Directory.

Você pode direcionar a variável `$Users` para `Get-Member`, a fim de descobrir as propriedades disponíveis.

```powershell
$Users | Get-Member
```

Em seguida, selecione as propriedades individuais direcionando `$Users` para `Select-Object`, tudo isso sem precisar consultar o Active Directory mais de uma vez.

```powershell
$Users | Select-Object -Property Name, LastLogonDate, LastBadPasswordAttempt
```

Se você pretende consultar o Active Directory mais de uma vez, use o parâmetro **Properties** para especificar as propriedades não padrão desejadas.

```powershell
Get-ADUser -Identity mike -Properties LastLogonDate, LastBadPasswordAttempt
```

```Output
DistinguishedName      : CN=Mike F. Robbins,OU=Sales,DC=mikefrobbins,DC=com
Enabled                : True
GivenName              : Mike
LastBadPasswordAttempt : 2/4/2017 10:46:15 AM
LastLogonDate          : 2/18/2017 12:45:14 AM
Name                   : Mike F. Robbins
ObjectClass            : user
ObjectGUID             : a82a8c58-1332-4a57-a6e2-68e0c750ea56
SamAccountName         : mike
SID                    : S-1-5-21-2989741381-570885089-3319121794-1108
Surname                : Robbins
UserPrincipalName      : miker@mikefrobbins.com
```

## <a name="summary"></a>Resumo

Neste capítulo, você aprendeu a determinar o tipo de objeto que um comando produz, determinar quais propriedades e métodos estão disponíveis para um comando e trabalhar com os comandos que limitam as propriedades retornadas por padrão.

## <a name="review"></a>Revisão

1. Que tipo de objeto o cmdlet `Get-Process` produz?
1. Como determinar quais são as propriedades disponíveis para um comando?
1. Se um comando existir para obter algo, mas não para definir a mesma coisa, o que você deverá verificar?
1. Como alguns comandos que não produzem uma saída por padrão podem ser induzidos a produzir uma saída?
1. Se você pretende trabalhar com os resultados de um comando que produz uma enorme quantidade de saída, o que você deve considerar fazer?

## <a name="recommended-reading"></a>Leitura recomendada

- [Get-Member][]
- [Exibindo a estrutura do objeto (Get-Member)][]
- [about_Objects][]
- [about_Properties][]
- [about_Methods][]
- [Não há cmdlet do PowerShell para iniciar ou parar algo? Não se esqueça de verificar métodos em obter cmdlets][use-methods]

<!-- link references -->
[Ferramentas de Administração de Servidor Remoto para Windows]: https://support.microsoft.com/help/2693643
[Módulos de gerenciamento do Windows]: /powershell/scripting/whats-new/module-compatibility#windows-management-modules
[Get-Member]: /powershell/module/microsoft.powershell.utility/get-member
[Exibindo a estrutura do objeto (Get-Member)]: /powershell/scripting/samples/viewing-object-structure--get-member-
[about_Objects]: /powershell/module/microsoft.powershell.core/about/about_objects
[about_Properties]: /powershell/module/microsoft.powershell.core/about/about_properties
[about_Methods]: /powershell/module/microsoft.powershell.core/about/about_methods
[use-methods]: https://mikefrobbins.com/2016/12/15/no-powershell-cmdlet-to-start-or-stop-something-dont-forget-to-check-for-methods-on-the-get-cmdlets/
[SMSS]: /sql/ssms/download-sql-server-management-studio-ssms
