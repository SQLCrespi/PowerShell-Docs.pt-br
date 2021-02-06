---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmaninstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManInstance
ms.openlocfilehash: 00680a466c9cc9dd719fbce3d66f4eb10ec47860
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597385"
---
# <span data-ttu-id="bd22c-102">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="bd22c-102">Get-WSManInstance</span></span>

## <span data-ttu-id="bd22c-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="bd22c-103">SYNOPSIS</span></span>
<span data-ttu-id="bd22c-104">Exibe informações de gerenciamento para uma instância do recurso especificada por um URI de recurso.</span><span class="sxs-lookup"><span data-stu-id="bd22c-104">Displays management information for a resource instance specified by a Resource URI.</span></span>

## <span data-ttu-id="bd22c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bd22c-105">SYNTAX</span></span>

### <span data-ttu-id="bd22c-106">GetInstance (padrão)</span><span class="sxs-lookup"><span data-stu-id="bd22c-106">GetInstance (Default)</span></span>

```
Get-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-ConnectionURI <Uri>] [-Dialect <Uri>]
 [-Fragment <String>] [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet <Hashtable>]
 [-SessionOption <SessionOption>] [-UseSSL] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="bd22c-107">Enumerar</span><span class="sxs-lookup"><span data-stu-id="bd22c-107">Enumerate</span></span>

```
Get-WSManInstance [-ApplicationName <String>] [-BasePropertiesOnly] [-ComputerName <String>]
 [-ConnectionURI <Uri>] [-Dialect <Uri>] [-Enumerate] [-Filter <String>] [-OptionSet <Hashtable>]
 [-Port <Int32>] [-Associations] [-ResourceURI] <Uri> [-ReturnType <String>] [-SessionOption <SessionOption>]
 [-Shallow] [-UseSSL] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="bd22c-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd22c-108">DESCRIPTION</span></span>
<span data-ttu-id="bd22c-109">O cmdlet **Get-WSManInstance** recupera uma instância de um recurso de gerenciamento que é especificado por um recurso Uniform Resource Identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="bd22c-109">The **Get-WSManInstance** cmdlet retrieves an instance of a management resource that is specified by a resource Uniform Resource Identifier (URI).</span></span>
<span data-ttu-id="bd22c-110">As informações recuperadas podem ser um conjunto de informações XML complexas, que é um objeto ou um valor simples.</span><span class="sxs-lookup"><span data-stu-id="bd22c-110">The information that is retrieved can be a complex XML information set, which is an object, or a simple value.</span></span>
<span data-ttu-id="bd22c-111">Esse cmdlet é o equivalente ao comando **Get** do Web Services para gerenciamento (WS-Management) padrão.</span><span class="sxs-lookup"><span data-stu-id="bd22c-111">This cmdlet is the equivalent to the standard Web Services for Management (WS-Management) **Get** command.</span></span>

<span data-ttu-id="bd22c-112">Este cmdlet usa a camada de conexão/transporte do WS-Management para recuperar informações.</span><span class="sxs-lookup"><span data-stu-id="bd22c-112">This cmdlet uses the WS-Management connection/transport layer to retrieve information.</span></span>

## <span data-ttu-id="bd22c-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="bd22c-113">EXAMPLES</span></span>

### <span data-ttu-id="bd22c-114">Exemplo 1: obter todas as informações do WMI</span><span class="sxs-lookup"><span data-stu-id="bd22c-114">Example 1: Get all information from WMI</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI wmicimv2/win32_service -SelectorSet @{name="winrm"} -ComputerName "Server01"
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : true
Caption                 : Windows Remote Management (WS-Management)
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Windows Remote Management (WinRM) service implements the WS-Management protocol for remote
management. WS-Management is a standard web services protocol used for remote software and
hardware management. The WinRM service listens on the network for WS-Management requests
and processes them. The WinRM Service needs to be configured with a listener using the
winrm.cmd command line tool or through Group Policy in order for it to listen over the
network. The WinRM service provides access to WMI data and enables event collection. Event
collection and subscription to events require that the service is running. WinRM messages
use HTTP and HTTPS as transports. The WinRM service does not depend on IIS but is
preconfigured to share a port with IIS on the same computer.  The WinRM service reserves the
/wsman URL prefix. To prevent conflicts with IIS, administrators should ensure that any
websites hosted on IIS do not use the /wsman URL prefix.
DesktopInteract         : false
DisplayName             : Windows Remote Management (WS-Management)
ErrorControl            : Normal
ExitCode                : 0
InstallDate             : InstallDate
Name                    : winrm
PathName                : C:\Windows\System32\svchost.exe -k NetworkService
ProcessId               : 948
ServiceSpecificExitCode : 0
ServiceType             : Share Process
Started                 : true
StartMode               : Auto
StartName               : NT AUTHORITY\NetworkService
State                   : Running
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : SERVER01
TagId                   : 0
WaitHint                : 0
```

<span data-ttu-id="bd22c-115">Esse comando retorna todas as informações que Instrumentação de Gerenciamento do Windows (WMI) expõe sobre o serviço **WinRM** no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="bd22c-115">This command returns all of the information that Windows Management Instrumentation (WMI) exposes about the **WinRM** service on the remote server01 computer.</span></span>

### <span data-ttu-id="bd22c-116">Exemplo 2: obter o status do serviço de spooler</span><span class="sxs-lookup"><span data-stu-id="bd22c-116">Example 2: Get the status of the Spooler service</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI wmicimv2/win32_service -SelectorSet @{name="spooler"} -Fragment Status -ComputerName "Server01"
XmlFragment=OK
```

<span data-ttu-id="bd22c-117">Esse comando retorna apenas o status do serviço de **spooler** no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="bd22c-117">This command returns only the status of the **Spooler** service on the remote server01 computer.</span></span>

### <span data-ttu-id="bd22c-118">Exemplo 3: obter referências de ponto de extremidade para todos os serviços</span><span class="sxs-lookup"><span data-stu-id="bd22c-118">Example 3: Get endpoint references for all services</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -ResourceURI wmicimv2/win32_service -ReturnType EPR
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : false
Caption                 : Visual Studio 2008 Remote Debugger
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Allows members of the Administrators group to remotely debug server applications using Visual
Studio 2008. Use the Visual Studio 2008 Remote Debugging Configuration Wizard to enable this
service.
DesktopInteract         : false
DisplayName             : Visual Studio 2008 Remote Debugger
ErrorControl            : Ignore
ExitCode                : 1077
InstallDate             : InstallDate
Name                    : msvsmon90
PathName                : "C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\Remote Debugger\x86\msvsmon.exe" /service msvsmon90
ProcessId               : 0
ServiceSpecificExitCode : 0
ServiceType             : Own Process
Started                 : false
StartMode               : Disabled
StartName               : LocalSystem
State                   : Stopped
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : COMPUTER01
TagId                   : 0
WaitHint                : 0
...
```

<span data-ttu-id="bd22c-119">Este comando retorna referências de ponto de extremidade que correspondem a todos os serviços existentes no computador local.</span><span class="sxs-lookup"><span data-stu-id="bd22c-119">This command returns endpoint references that correspond to all the services on the local computer.</span></span>

### <span data-ttu-id="bd22c-120">Exemplo 4: obter serviços que atendem aos critérios especificados</span><span class="sxs-lookup"><span data-stu-id="bd22c-120">Example 4: Get services that meet specified criteria</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -ResourceURI wmicimv2/* -Filter "select * from win32_service where StartMode = 'Auto' and State = 'Stopped'" -ComputerName "Server01"
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : false
Caption                 : Windows Media Center Service Launcher
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Starts Windows Media Center Scheduler and Windows Media Center Receiver services
at startup if TV is enabled within Windows Media Center.
DesktopInteract         : false
DisplayName             : Windows Media Center Service Launcher
ErrorControl            : Ignore
ExitCode                : 0
InstallDate             : InstallDate
Name                    : ehstart
PathName                : C:\Windows\system32\svchost.exe -k LocalServiceNoNetwork
ProcessId               : 0
ServiceSpecificExitCode : 0
ServiceType             : Share Process
Started                 : false
StartMode               : Auto
StartName               : NT AUTHORITY\LocalService
State                   : Stopped
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : Server01
TagId                   : 0
WaitHint                : 0
...
```

<span data-ttu-id="bd22c-121">Esse comando lista todos os serviços que atendem aos seguintes critérios no computador remoto Server01:</span><span class="sxs-lookup"><span data-stu-id="bd22c-121">This command lists all of the services that meet the following criteria on the remote Server01 computer:</span></span>

- <span data-ttu-id="bd22c-122">O tipo de inicialização do serviço é automático.</span><span class="sxs-lookup"><span data-stu-id="bd22c-122">The startup type of the service is Automatic.</span></span>
- <span data-ttu-id="bd22c-123">O serviço foi interrompido.</span><span class="sxs-lookup"><span data-stu-id="bd22c-123">The service is stopped.</span></span>

### <span data-ttu-id="bd22c-124">Exemplo 5: obter a configuração do ouvinte que corresponde aos critérios no computador local</span><span class="sxs-lookup"><span data-stu-id="bd22c-124">Example 5: Get listener configuration that matches criteria on the local computer</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI winrm/config/listener -SelectorSet @{Address="*";Transport="http"}
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 80
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {100.0.0.1, 123.123.123.123, ::1, 2001:4898:0:fff:0:5efe:123.123.123.123...}
```

<span data-ttu-id="bd22c-125">Este comando lista a configuração de ouvinte do WS-Management no computador local para o ouvinte que corresponde aos critérios no seletor definido.</span><span class="sxs-lookup"><span data-stu-id="bd22c-125">This command lists the WS-Management listener configuration on the local computer for the listener that matches the criteria in the selector set.</span></span>

### <span data-ttu-id="bd22c-126">Exemplo 6: obter a configuração do ouvinte que corresponde aos critérios em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="bd22c-126">Example 6: Get listener configuration that matches criteria on a remote computer</span></span>

```
PS C:\> Get-WSManInstance -ResourceURI winrm/config/listener -SelectorSet @{Address="*";Transport="http"} -ComputerName "Server01"
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 80
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {100.0.0.1, 123.123.123.124, ::1, 2001:4898:0:fff:0:5efe:123.123.123.124...}
```

<span data-ttu-id="bd22c-127">Este comando lista a configuração de ouvinte do WS-Management no computador remoto servidor01 para o ouvinte que corresponde aos critérios no seletor definido.</span><span class="sxs-lookup"><span data-stu-id="bd22c-127">This command lists the WS-Management listener configuration on the remote server01 computer for the listener that matches the criteria in the selector set.</span></span>

### <span data-ttu-id="bd22c-128">Exemplo 7: obter instâncias associadas relacionadas a uma instância especificada</span><span class="sxs-lookup"><span data-stu-id="bd22c-128">Example 7: Get associated instances related to a specified instance</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -Dialect Association -Filter "{Object=win32_service?name=winrm}" -ResourceURI wmicimv2/*
xsi                       : http://www.w3.org/2001/XMLSchema-instance
p                         : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_ComputerSystem
cim                       : http://schemas.dmtf.org/wbem/wscim/1/common
type                      : p:Win32_ComputerSystem_Type
lang                      : en-US
AdminPasswordStatus       : 1
AutomaticManagedPagefile  : true
AutomaticResetBootOption  : true
AutomaticResetCapability  : true
BootOptionOnLimit         : BootOptionOnLimit
BootOptionOnWatchDog      : BootOptionOnWatchDog
BootROMSupported          : true
BootupState               : Normal boot
Caption                   : SERVER01
ChassisBootupState        : 3
CreationClassName         : Win32_ComputerSystem
CurrentTimeZone           : -480
DaylightInEffect          : false
Description               : AT/AT COMPATIBLE
DNSHostName               : server01
Domain                    : site01.corp.fabrikam.com
DomainRole                : 1
EnableDaylightSavingsTime : true
FrontPanelResetStatus     : 2
InfraredSupported         : false
InstallDate               : InstallDate
KeyboardPasswordStatus    : 2
LastLoadInfo              : LastLoadInfo
Manufacturer              : Dell Inc.
Model                     : OptiPlex 745
Name                      : SERVER01
NameFormat                : NameFormat
NetworkServerModeEnabled  : true
NumberOfLogicalProcessors : 2
NumberOfProcessors        : 1
OEMStringArray            : www.dell.com
PartOfDomain              : true
PauseAfterReset           : -1
PCSystemType              : 5
PowerManagementSupported  : PowerManagementSupported
PowerOnPasswordStatus     : 1
PowerState                : 0
PowerSupplyState          : 3
PrimaryOwnerContact       : PrimaryOwnerContact
PrimaryOwnerName          : testuser01
ResetCapability           : 1
ResetCount                : -1
ResetLimit                : -1
Roles                     : {LM_Workstation, LM_Server, SQLServer, NT}
Status                    : OK
SystemStartupDelay        : SystemStartupDelay
SystemStartupSetting      : SystemStartupSetting
SystemType                : X86-based PC
ThermalState              : 3
TotalPhysicalMemory       : 3217760256
UserName                  : FABRIKAM\testuser01
WakeUpType                : 6
Workgroup                 : Workgroup
xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_Service_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : false
Caption                 : Remote Procedure Call (RPC)
CheckPoint              : 0
CreationClassName       : Win32_Service
Description             : Serves as the endpoint mapper and COM Service Control Manager. If this service is stopped
or disabled, programs using COM or Remote Procedure Call (RPC) services will not function
properly.
DesktopInteract         : false
DisplayName             : Remote Procedure Call (RPC)
ErrorControl            : Normal
ExitCode                : 0
InstallDate             : InstallDate
Name                    : RpcSs
PathName                : C:\Windows\system32\svchost.exe -k rpcss
ProcessId               : 1100
ServiceSpecificExitCode : 0
ServiceType             : Share Process
Started                 : true
StartMode               : Auto
StartName               : NT AUTHORITY\NetworkService
State                   : Running
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : SERVER01
TagId                   : 0
WaitHint                : 0

xsi                     : http://www.w3.org/2001/XMLSchema-instance
p                       : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_SystemDriver
cim                     : http://schemas.dmtf.org/wbem/wscim/1/common
type                    : p:Win32_SystemDriver_Type
lang                    : en-US
AcceptPause             : false
AcceptStop              : true
Caption                 : HTTP
CreationClassName       : Win32_SystemDriver
Description             : HTTP
DesktopInteract         : false
DisplayName             : HTTP
ErrorControl            : Normal
ExitCode                : 0
InstallDate             : InstallDate
Name                    : HTTP
PathName                : C:\Windows\system32\drivers\HTTP.sys
ServiceSpecificExitCode : 0
ServiceType             : Kernel Driver
Started                 : true
StartMode               : Manual
StartName               :
State                   : Running
Status                  : OK
SystemCreationClassName : Win32_ComputerSystem
SystemName              : SERVER01
TagId                   : 0
```

<span data-ttu-id="bd22c-129">Este comando obtém as instâncias associadas que estão relacionadas à instância especificada (winrm).</span><span class="sxs-lookup"><span data-stu-id="bd22c-129">This command gets the associated instances that are related to the specified instance (winrm).</span></span>

<span data-ttu-id="bd22c-130">Você deve incluir o filtro entre aspas, conforme mostrado no exemplo.</span><span class="sxs-lookup"><span data-stu-id="bd22c-130">You must enclose the filter in quotation marks, as shown in the example.</span></span>

### <span data-ttu-id="bd22c-131">Exemplo 8: obter instâncias de associação relacionadas a uma instância especificada</span><span class="sxs-lookup"><span data-stu-id="bd22c-131">Example 8: Get association instances related to a specified instance</span></span>

```
PS C:\> Get-WSManInstance -Enumerate -Dialect Association -Associations -Filter "{Object=win32_service?name=winrm}" -ResourceURI wmicimv2/*
```

<span data-ttu-id="bd22c-132">Este comando obtém as instâncias de associação que estão relacionadas à instância especificada (winrm).</span><span class="sxs-lookup"><span data-stu-id="bd22c-132">This command gets association instances that are related to the specified instance (winrm).</span></span>
<span data-ttu-id="bd22c-133">Como o valor de *dialeto* é Association e o parâmetro *Associations* é usado, esse comando retorna as instâncias de associação, não as instâncias associadas.</span><span class="sxs-lookup"><span data-stu-id="bd22c-133">Because the *Dialect* value is association and the *Associations* parameter is used, this command returns association instances, not associated instances.</span></span>

<span data-ttu-id="bd22c-134">Você deve incluir o filtro entre aspas, conforme mostrado no exemplo.</span><span class="sxs-lookup"><span data-stu-id="bd22c-134">You must enclose the filter in quotation marks, as shown in the example.</span></span>

## <span data-ttu-id="bd22c-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bd22c-135">PARAMETERS</span></span>

### <span data-ttu-id="bd22c-136">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="bd22c-136">-ApplicationName</span></span>
<span data-ttu-id="bd22c-137">Especifica o nome do aplicativo na conexão.</span><span class="sxs-lookup"><span data-stu-id="bd22c-137">Specifies the application name in the connection.</span></span>
<span data-ttu-id="bd22c-138">O valor padrão do parâmetro *ApplicationName* é WSMan.</span><span class="sxs-lookup"><span data-stu-id="bd22c-138">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="bd22c-139">O identificador completo para o ponto de extremidade remoto é no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="bd22c-139">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="bd22c-140">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="bd22c-140">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="bd22c-141">Por exemplo: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="bd22c-141">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="bd22c-142">Os Serviços de Informações da Internet (IIS), que hospedam a sessão, encaminham solicitações com esse ponto de extremidade para o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="bd22c-142">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="bd22c-143">Essa configuração padrão de WSMAN é apropriada para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="bd22c-143">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="bd22c-144">Esse parâmetro é projetado para ser usado se muitos computadores estabelecerem conexões remotas com um computador que esteja executando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd22c-144">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="bd22c-145">Nesse caso, o IIS hospeda WS-Management de eficiência.</span><span class="sxs-lookup"><span data-stu-id="bd22c-145">In this case, IIS hosts WS-Management for efficiency.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-146">-Associações</span><span class="sxs-lookup"><span data-stu-id="bd22c-146">-Associations</span></span>
<span data-ttu-id="bd22c-147">Indica que esse cmdlet obtém as instâncias de associação, não as instâncias associadas.</span><span class="sxs-lookup"><span data-stu-id="bd22c-147">Indicates that this cmdlet gets association instances, not associated instances.</span></span>
<span data-ttu-id="bd22c-148">Você pode usar esse parâmetro somente quando o parâmetro *dialeto* tiver um valor de Association.</span><span class="sxs-lookup"><span data-stu-id="bd22c-148">You can use this parameter only when the *Dialect* parameter has a value of Association.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-149">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="bd22c-149">-Authentication</span></span>
<span data-ttu-id="bd22c-150">Especifica o mecanismo de autenticação a ser usado no servidor.</span><span class="sxs-lookup"><span data-stu-id="bd22c-150">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="bd22c-151">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="bd22c-151">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bd22c-152">Básica.</span><span class="sxs-lookup"><span data-stu-id="bd22c-152">Basic.</span></span>
<span data-ttu-id="bd22c-153">É um esquema no qual o nome de usuário e senha são enviados em texto não criptografado para o servidor ou proxy.</span><span class="sxs-lookup"><span data-stu-id="bd22c-153">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="bd22c-154">Padrão.</span><span class="sxs-lookup"><span data-stu-id="bd22c-154">Default.</span></span>
<span data-ttu-id="bd22c-155">Utiliza o método de autenticação implementado pelo protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="bd22c-155">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="bd22c-156">Este é o padrão.</span><span class="sxs-lookup"><span data-stu-id="bd22c-156">This is the default.</span></span>
- <span data-ttu-id="bd22c-157">Digest.</span><span class="sxs-lookup"><span data-stu-id="bd22c-157">Digest.</span></span>
<span data-ttu-id="bd22c-158">É um esquema de desafio/resposta que utiliza uma cadeia de caracteres de dados do servidor especificada para o desafio.</span><span class="sxs-lookup"><span data-stu-id="bd22c-158">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="bd22c-159">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="bd22c-159">Kerberos.</span></span>
<span data-ttu-id="bd22c-160">O computador cliente e o servidor autenticam mutuamente utilizando certificados Kerberos.</span><span class="sxs-lookup"><span data-stu-id="bd22c-160">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="bd22c-161">Negotiate.</span><span class="sxs-lookup"><span data-stu-id="bd22c-161">Negotiate.</span></span>
<span data-ttu-id="bd22c-162">É um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser utilizado para autenticação.</span><span class="sxs-lookup"><span data-stu-id="bd22c-162">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="bd22c-163">Por exemplo, esse valor de parâmetro permite que a negociação determine se o protocolo Kerberos ou NTLM é usado.</span><span class="sxs-lookup"><span data-stu-id="bd22c-163">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="bd22c-164">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="bd22c-164">CredSSP.</span></span>
<span data-ttu-id="bd22c-165">Use a autenticação do Credential Security Support Provider (CredSSP), que permite que o usuário delegue as credenciais.</span><span class="sxs-lookup"><span data-stu-id="bd22c-165">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="bd22c-166">Esta opção foi criada para os comandos executados em um computador remoto, mas coletam dados ou executam comandos adicionais em outros computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="bd22c-166">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="bd22c-167">Cuidado: o CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="bd22c-167">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="bd22c-168">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="bd22c-168">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="bd22c-169">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="bd22c-169">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am
Accepted values: None, Default, Digest, Negotiate, Basic, Kerberos, ClientCertificate, Credssp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-170">-BasePropertiesOnly</span><span class="sxs-lookup"><span data-stu-id="bd22c-170">-BasePropertiesOnly</span></span>
<span data-ttu-id="bd22c-171">Indica que esse cmdlet enumera somente as propriedades que fazem parte da classe base que é especificada pelo parâmetro *ResourceURI* .</span><span class="sxs-lookup"><span data-stu-id="bd22c-171">Indicates that this cmdlet enumerates only the properties that are part of the base class that is specified by the *ResourceURI* parameter.</span></span>
<span data-ttu-id="bd22c-172">Esse parâmetro não terá nenhum efeito se o parâmetro *superficial* for especificado.</span><span class="sxs-lookup"><span data-stu-id="bd22c-172">This parameter has no effect if the *Shallow* parameter is specified.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases: UBPO, Base

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-173">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="bd22c-173">-CertificateThumbprint</span></span>
<span data-ttu-id="bd22c-174">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="bd22c-174">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="bd22c-175">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="bd22c-175">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="bd22c-176">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="bd22c-176">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="bd22c-177">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="bd22c-177">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="bd22c-178">Para obter uma impressão digital do certificado, use o comando Get-Item ou Get-ChildItem na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="bd22c-178">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-179">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="bd22c-179">-ComputerName</span></span>
<span data-ttu-id="bd22c-180">Especifica o computador no qual executar a operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="bd22c-180">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="bd22c-181">O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="bd22c-181">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="bd22c-182">Utilize o nome do computador local, o localhost ou um ponto (.) para especificar o computador local.</span><span class="sxs-lookup"><span data-stu-id="bd22c-182">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="bd22c-183">O computador local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="bd22c-183">The local computer is the default.</span></span>
<span data-ttu-id="bd22c-184">Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="bd22c-184">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="bd22c-185">É possível redirecionar um valor desse parâmetro para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bd22c-185">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-186">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="bd22c-186">-ConnectionURI</span></span>
<span data-ttu-id="bd22c-187">Especifica o ponto de extremidade de conexão.</span><span class="sxs-lookup"><span data-stu-id="bd22c-187">Specifies the connection endpoint.</span></span>
<span data-ttu-id="bd22c-188">O formato dessa cadeia de caracteres é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bd22c-188">The format of this string is as follows:</span></span>

<span data-ttu-id="bd22c-189">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="bd22c-189">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="bd22c-190">A cadeia de caracteres a seguir é um valor formatado corretamente para este parâmetro:</span><span class="sxs-lookup"><span data-stu-id="bd22c-190">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="bd22c-191">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="bd22c-191">The URI must be fully qualified.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: CURI, CU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-192">-Credential</span><span class="sxs-lookup"><span data-stu-id="bd22c-192">-Credential</span></span>
<span data-ttu-id="bd22c-193">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="bd22c-193">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="bd22c-194">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="bd22c-194">The default is the current user.</span></span>
<span data-ttu-id="bd22c-195">Digite um nome de usuário, como User01, Domínio01 \ Usuário01 ou User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="bd22c-195">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="bd22c-196">Ou insira um objeto **PSCredential** , como um retornado pelo cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="bd22c-196">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="bd22c-197">Quando você digita um nome de usuário, esse cmdlet solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="bd22c-197">When you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: cred, c

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-198">-Dialeto</span><span class="sxs-lookup"><span data-stu-id="bd22c-198">-Dialect</span></span>
<span data-ttu-id="bd22c-199">Especifica o dialeto a ser usado no predicado de filtro.</span><span class="sxs-lookup"><span data-stu-id="bd22c-199">Specifies the dialect to use in the filter predicate.</span></span>
<span data-ttu-id="bd22c-200">Isso pode ser qualquer dialeto compatível com o serviço remoto.</span><span class="sxs-lookup"><span data-stu-id="bd22c-200">This can be any dialect that is supported by the remote service.</span></span>
<span data-ttu-id="bd22c-201">Os seguintes aliases podem ser usados para o URI do dialeto:</span><span class="sxs-lookup"><span data-stu-id="bd22c-201">The following aliases can be used for the dialect URI:</span></span>

- <span data-ttu-id="bd22c-202">WQL `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span><span class="sxs-lookup"><span data-stu-id="bd22c-202">WQL `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span></span>
- <span data-ttu-id="bd22c-203">Seletor `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span><span class="sxs-lookup"><span data-stu-id="bd22c-203">Selector `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span></span>
- <span data-ttu-id="bd22c-204">Associação `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span><span class="sxs-lookup"><span data-stu-id="bd22c-204">Association `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-205">-Enumerar</span><span class="sxs-lookup"><span data-stu-id="bd22c-205">-Enumerate</span></span>
<span data-ttu-id="bd22c-206">Indica que esse cmdlet retorna todas as instâncias de um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="bd22c-206">Indicates that this cmdlet returns all of the instances of a management resource.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-207">-Filter</span><span class="sxs-lookup"><span data-stu-id="bd22c-207">-Filter</span></span>
<span data-ttu-id="bd22c-208">Especifica a expressão de filtro para a enumeração.</span><span class="sxs-lookup"><span data-stu-id="bd22c-208">Specifies the filter expression for the enumeration.</span></span>
<span data-ttu-id="bd22c-209">Se você especificar esse parâmetro, também deverá especificar o *dialeto*.</span><span class="sxs-lookup"><span data-stu-id="bd22c-209">If you specify this parameter, you must also specify *Dialect*.</span></span>

<span data-ttu-id="bd22c-210">Os valores válidos desse parâmetro dependem do dialeto especificado no *dialeto*.</span><span class="sxs-lookup"><span data-stu-id="bd22c-210">The valid values of this parameter depend on the dialect that is specified in *Dialect*.</span></span>
<span data-ttu-id="bd22c-211">Por exemplo, se *Dialect* for WQL, o parâmetro de *filtro* deverá conter uma cadeia de caracteres e a cadeia de caracteres deverá conter uma consulta WQL válida, como a consulta a seguir:</span><span class="sxs-lookup"><span data-stu-id="bd22c-211">For example, if *Dialect* is WQL, the *Filter* parameter must contain a string, and the string must contain a valid WQL query such as the following query:</span></span>

`"Select * from Win32_Service where State != Running"`

<span data-ttu-id="bd22c-212">Se *dialeto* for associação, o *filtro* deverá conter uma cadeia de caracteres e a cadeia de caracteres deverá conter um filtro válido, como o filtro a seguir:</span><span class="sxs-lookup"><span data-stu-id="bd22c-212">If *Dialect* is Association, *Filter* must contain a string, and the string must contain a valid filter, such as the following filter:</span></span>

`-filter:Object=EPR\[;AssociationClassName=AssocClassName\]\[;ResultClassName=ClassName\]\[;Role=RefPropertyName\]\[;ResultRole=RefPropertyName\]}`

```yaml
Type: System.String
Parameter Sets: Enumerate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-213">-Fragmento</span><span class="sxs-lookup"><span data-stu-id="bd22c-213">-Fragment</span></span>
<span data-ttu-id="bd22c-214">Especifica uma seção na instância a ser atualizada ou recuperada para a operação especificada.</span><span class="sxs-lookup"><span data-stu-id="bd22c-214">Specifies a section inside the instance that is to be updated or retrieved for the specified operation.</span></span>
<span data-ttu-id="bd22c-215">Por exemplo, para obter o status de um serviço de spooler, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bd22c-215">For example, to get the status of a spooler service, specify the following:</span></span>

`-Fragment Status`

```yaml
Type: System.String
Parameter Sets: GetInstance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-216">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="bd22c-216">-OptionSet</span></span>
<span data-ttu-id="bd22c-217">Especifica um conjunto de opções para um serviço para modificar ou refinar a natureza da solicitação.</span><span class="sxs-lookup"><span data-stu-id="bd22c-217">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="bd22c-218">Elas se assemelham a opções usadas em shells de linha de comando porque são específicas de serviço.</span><span class="sxs-lookup"><span data-stu-id="bd22c-218">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="bd22c-219">Qualquer número de opções pode ser especificado.</span><span class="sxs-lookup"><span data-stu-id="bd22c-219">Any number of options can be specified.</span></span>

<span data-ttu-id="bd22c-220">O exemplo a seguir demonstra a sintaxe que passa os valores 1, 2 e 3 para os parâmetros a, b e c:</span><span class="sxs-lookup"><span data-stu-id="bd22c-220">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: OS

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-221">-Port</span><span class="sxs-lookup"><span data-stu-id="bd22c-221">-Port</span></span>
<span data-ttu-id="bd22c-222">Especifica a porta a ser usada quando o cliente se conecta ao serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="bd22c-222">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="bd22c-223">Quando o transporte é HTTP, a porta padrão é 80.</span><span class="sxs-lookup"><span data-stu-id="bd22c-223">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="bd22c-224">Quando o transporte é HTTPS, a porta padrão é 443.</span><span class="sxs-lookup"><span data-stu-id="bd22c-224">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="bd22c-225">Quando você usa HTTPS como o transporte, o valor do parâmetro *ComputerName* deve corresponder ao CN (nome comum) do certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="bd22c-225">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="bd22c-226">No entanto, se o parâmetro *SkipCNCheck* for especificado como parte do parâmetro *SessionOption* , o nome comum do certificado do servidor não precisará corresponder ao nome do host do servidor.</span><span class="sxs-lookup"><span data-stu-id="bd22c-226">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="bd22c-227">O parâmetro *SkipCNCheck* deve ser usado somente para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="bd22c-227">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-228">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="bd22c-228">-ResourceURI</span></span>
<span data-ttu-id="bd22c-229">Especifica o URI da classe ou instância de recurso.</span><span class="sxs-lookup"><span data-stu-id="bd22c-229">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="bd22c-230">O URI identifica um tipo específico de recurso, como discos ou processos, em um computador.</span><span class="sxs-lookup"><span data-stu-id="bd22c-230">The URI identifies a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="bd22c-231">Um URI consiste em um prefixo e um caminho de um recurso.</span><span class="sxs-lookup"><span data-stu-id="bd22c-231">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="bd22c-232">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bd22c-232">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: RURI

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-233">-ReturnType</span><span class="sxs-lookup"><span data-stu-id="bd22c-233">-ReturnType</span></span>
<span data-ttu-id="bd22c-234">Especifica o tipo de dados a serem retornados.</span><span class="sxs-lookup"><span data-stu-id="bd22c-234">Specifies the type of data to be returned.</span></span>
<span data-ttu-id="bd22c-235">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="bd22c-235">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bd22c-236">Objeto</span><span class="sxs-lookup"><span data-stu-id="bd22c-236">Object</span></span>
- <span data-ttu-id="bd22c-237">EPR</span><span class="sxs-lookup"><span data-stu-id="bd22c-237">EPR</span></span>
- <span data-ttu-id="bd22c-238">ObjectAndEPR</span><span class="sxs-lookup"><span data-stu-id="bd22c-238">ObjectAndEPR</span></span>

<span data-ttu-id="bd22c-239">O valor padrão é Object.</span><span class="sxs-lookup"><span data-stu-id="bd22c-239">The default value is Object.</span></span>

<span data-ttu-id="bd22c-240">Se você especificar objeto ou não especificar esse parâmetro, esse cmdlet retornará apenas objetos.</span><span class="sxs-lookup"><span data-stu-id="bd22c-240">If you specify Object or do not specify this parameter, this cmdlet returns only objects.</span></span>
<span data-ttu-id="bd22c-241">Se você especificar referência de ponto de extremidade (EPR), esse cmdlet retornará apenas as referências de ponto de extremidade dos objetos.</span><span class="sxs-lookup"><span data-stu-id="bd22c-241">If you specify endpoint reference (EPR) this cmdlet returns only the endpoint references of the objects.</span></span>
<span data-ttu-id="bd22c-242">Referências do ponto de extremidade contêm informações sobre o URI do recurso e os seletores da instância.</span><span class="sxs-lookup"><span data-stu-id="bd22c-242">Endpoint references contain information about the resource URI and the selectors for the instance.</span></span>
<span data-ttu-id="bd22c-243">Se você especificar ObjectAndEPR, esse cmdlet retornará o objeto e suas referências de ponto de extremidade associadas.</span><span class="sxs-lookup"><span data-stu-id="bd22c-243">If you specify ObjectAndEPR, this cmdlet returns both the object and its associated endpoint references.</span></span>

```yaml
Type: System.String
Parameter Sets: Enumerate
Aliases: RT
Accepted values: object, epr, objectandepr

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-244">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="bd22c-244">-SelectorSet</span></span>
<span data-ttu-id="bd22c-245">Especifica um conjunto de pares de valor que são utilizados para selecionar instâncias do recurso de gerenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="bd22c-245">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="bd22c-246">O parâmetro *SelectorSet* é usado quando há mais de uma instância do recurso.</span><span class="sxs-lookup"><span data-stu-id="bd22c-246">The *SelectorSet* parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="bd22c-247">O valor do parâmetro *SelectorSet* deve ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="bd22c-247">The value of the *SelectorSet* parameter must be a hash table.</span></span>

<span data-ttu-id="bd22c-248">O exemplo a seguir mostra como inserir um valor para esse parâmetro:</span><span class="sxs-lookup"><span data-stu-id="bd22c-248">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: GetInstance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-249">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="bd22c-249">-SessionOption</span></span>
<span data-ttu-id="bd22c-250">Especifica as opções estendidas para a sessão de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="bd22c-250">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="bd22c-251">Insira um objeto **SessionOption** que você cria usando o cmdlet New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="bd22c-251">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="bd22c-252">Para obter mais informações sobre as opções disponíveis, digite `Get-Help New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="bd22c-252">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

```yaml
Type: Microsoft.WSMan.Management.SessionOption
Parameter Sets: (All)
Aliases: SO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-253">-Superficial</span><span class="sxs-lookup"><span data-stu-id="bd22c-253">-Shallow</span></span>
<span data-ttu-id="bd22c-254">Indica que esse cmdlet retorna apenas instâncias da classe base especificada no URI de recurso.</span><span class="sxs-lookup"><span data-stu-id="bd22c-254">Indicates that this cmdlet returns only instances of the base class that is specified in the resource URI.</span></span>
<span data-ttu-id="bd22c-255">Se você não especificar esse parâmetro, o cmdlet retornará instâncias da classe base especificada no URI e em todas as suas classes derivadas.</span><span class="sxs-lookup"><span data-stu-id="bd22c-255">If you do not specify this parameter,, this cmdlet returns instances of the base class that is specified in the URI and in all its derived classes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Enumerate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-256">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="bd22c-256">-UseSSL</span></span>
<span data-ttu-id="bd22c-257">Especifica que o protocolo de protocolo SSL (SSL) é usado para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="bd22c-257">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="bd22c-258">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="bd22c-258">By default, SSL is not used.</span></span>

<span data-ttu-id="bd22c-259">WS-Management criptografa todo o conteúdo do PowerShell que é transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="bd22c-259">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="bd22c-260">O parâmetro *UseSSL* permite especificar a proteção adicional do HTTPS em vez de http.</span><span class="sxs-lookup"><span data-stu-id="bd22c-260">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="bd22c-261">Se o SSL não estiver disponível na porta que é usada para a conexão e você especificar esse parâmetro, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="bd22c-261">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SSL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd22c-262">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bd22c-262">CommonParameters</span></span>
<span data-ttu-id="bd22c-263">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bd22c-263">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bd22c-264">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bd22c-264">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bd22c-265">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="bd22c-265">INPUTS</span></span>

### <span data-ttu-id="bd22c-266">Nenhum</span><span class="sxs-lookup"><span data-stu-id="bd22c-266">None</span></span>
<span data-ttu-id="bd22c-267">Este cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="bd22c-267">This command does not accept any input.</span></span>

## <span data-ttu-id="bd22c-268">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="bd22c-268">OUTPUTS</span></span>

### <span data-ttu-id="bd22c-269">Elemento System.Xml.Xml</span><span class="sxs-lookup"><span data-stu-id="bd22c-269">System.Xml.XmlElement</span></span>
<span data-ttu-id="bd22c-270">Esse cmdlet gera um objeto **XmlElement** .</span><span class="sxs-lookup"><span data-stu-id="bd22c-270">This cmdlet generates an **XMLElement** object.</span></span>

## <span data-ttu-id="bd22c-271">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="bd22c-271">NOTES</span></span>

## <span data-ttu-id="bd22c-272">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="bd22c-272">RELATED LINKS</span></span>

[<span data-ttu-id="bd22c-273">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="bd22c-273">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="bd22c-274">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="bd22c-274">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="bd22c-275">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="bd22c-275">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="bd22c-276">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="bd22c-276">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="bd22c-277">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="bd22c-277">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="bd22c-278">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="bd22c-278">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="bd22c-279">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="bd22c-279">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="bd22c-280">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="bd22c-280">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="bd22c-281">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="bd22c-281">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="bd22c-282">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="bd22c-282">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="bd22c-283">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="bd22c-283">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="bd22c-284">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="bd22c-284">Test-WSMan</span></span>](Test-WSMan.md)

