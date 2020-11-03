---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmiObject
ms.openlocfilehash: ed759ff3d0dd35cd55f9dac5a2d76e36eac4dc6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194164"
---
# <span data-ttu-id="d3a8d-103">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="d3a8d-103">Get-WmiObject</span></span>

## <span data-ttu-id="d3a8d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d3a8d-104">SYNOPSIS</span></span>
<span data-ttu-id="d3a8d-105">Obtém as instâncias de classes do Windows Management Instrumentation (WMI) ou obtém informações sobre as classes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-105">Gets instances of Windows Management Instrumentation (WMI) classes or information about the available classes.</span></span>

## <span data-ttu-id="d3a8d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d3a8d-106">SYNTAX</span></span>

### <span data-ttu-id="d3a8d-107">consulta (padrão)</span><span class="sxs-lookup"><span data-stu-id="d3a8d-107">query (Default)</span></span>

```
Get-WmiObject [-Class] <String> [[-Property] <String[]>] [-Filter <String>] [-Amended] [-DirectRead]
 [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="d3a8d-108">list</span><span class="sxs-lookup"><span data-stu-id="d3a8d-108">list</span></span>

```
Get-WmiObject [[-Class] <String>] [-Recurse] [-Amended] [-List] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="d3a8d-109">WQLQuery</span><span class="sxs-lookup"><span data-stu-id="d3a8d-109">WQLQuery</span></span>

```
Get-WmiObject [-Amended] [-DirectRead] -Query <String> [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="d3a8d-110">classe</span><span class="sxs-lookup"><span data-stu-id="d3a8d-110">class</span></span>

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="d3a8d-111">caminho</span><span class="sxs-lookup"><span data-stu-id="d3a8d-111">path</span></span>

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

## <span data-ttu-id="d3a8d-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d3a8d-112">DESCRIPTION</span></span>

<span data-ttu-id="d3a8d-113">A partir do PowerShell 3,0, esse cmdlet foi substituído pelo `Get-CimInstance` .</span><span class="sxs-lookup"><span data-stu-id="d3a8d-113">Starting in PowerShell 3.0, this cmdlet has been superseded by `Get-CimInstance`.</span></span>

<span data-ttu-id="d3a8d-114">O `Get-WmiObject` cmdlet obtém instâncias de classes WMI ou informações sobre as classes WMI disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-114">The `Get-WmiObject` cmdlet gets instances of WMI classes or information about the available WMI classes.</span></span> <span data-ttu-id="d3a8d-115">Para especificar um computador remoto, use o parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="d3a8d-115">To specify a remote computer, use the **ComputerName** parameter.</span></span> <span data-ttu-id="d3a8d-116">Se o parâmetro **List** for especificado, o cmdlet obtém informações sobre as classes WMI disponíveis em um namespace especificado.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-116">If the **List** parameter is specified, the cmdlet gets information about the WMI classes that are available in a specified namespace.</span></span> <span data-ttu-id="d3a8d-117">Se o parâmetro **Query** for especificado, o cmdlet executa uma instrução do WMI query language (WQL).</span><span class="sxs-lookup"><span data-stu-id="d3a8d-117">If the **Query** parameter is specified, the cmdlet runs a WMI query language (WQL) statement.</span></span>

<span data-ttu-id="d3a8d-118">O `Get-WmiObject` cmdlet não usa a comunicação remota do Windows PowerShell para executar operações remotas.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-118">The `Get-WmiObject` cmdlet does not use Windows PowerShell remoting to perform remote operations.</span></span>
<span data-ttu-id="d3a8d-119">Você pode usar o parâmetro **ComputerName** do `Get-WmiObject` cmdlet, mesmo que o computador não atenda aos requisitos da comunicação remota do Windows PowerShell ou não esteja configurado para comunicação remota no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-119">You can use the **ComputerName** parameter of the `Get-WmiObject` cmdlet even if your computer does not meet the requirements for Windows PowerShell remoting or is not configured for remoting in Windows PowerShell.</span></span>

<span data-ttu-id="d3a8d-120">A partir do Windows PowerShell 3,0, a propriedade **__Server** do objeto que `Get-WmiObject` retorna tem um alias **PSComputerName** .</span><span class="sxs-lookup"><span data-stu-id="d3a8d-120">Beginning in Windows PowerShell 3.0, the **__Server** property of the object that `Get-WmiObject` returns has a **PSComputerName** alias.</span></span> <span data-ttu-id="d3a8d-121">Isso facilita incluir o nome do computador de origem na saída e nos relatórios.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-121">This makes it easier to include the source computer name in output and reports.</span></span>

## <span data-ttu-id="d3a8d-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d3a8d-122">EXAMPLES</span></span>

### <span data-ttu-id="d3a8d-123">Exemplo 1: obter processos no computador local</span><span class="sxs-lookup"><span data-stu-id="d3a8d-123">Example 1: Get processes on the local computer</span></span>

<span data-ttu-id="d3a8d-124">Este exemplo obtém os processos no computador local.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-124">This example get the processes on the local computer.</span></span>

```powershell
Get-WmiObject -Class Win32_Process
```

### <span data-ttu-id="d3a8d-125">Exemplo 2: Obtém serviços em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="d3a8d-125">Example 2: Gets services on a remote computer</span></span>

<span data-ttu-id="d3a8d-126">Este exemplo obtém os serviços em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-126">This example gets the services on a remote computer.</span></span> <span data-ttu-id="d3a8d-127">O parâmetro **ComputerName** especifica o endereço IP de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-127">The **ComputerName** parameter specifies the IP address of a remote computer.</span></span> <span data-ttu-id="d3a8d-128">Por padrão, a conta de usuário atual deve ser um membro do grupo **Administradores** no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-128">By default, the current user account must be a member of the **Administrators** group on the remote computer.</span></span>

```powershell
Get-WmiObject -Class Win32_Service -ComputerName 10.1.4.62
```

### <span data-ttu-id="d3a8d-129">Exemplo 3: obter as classes WMI no namespace raiz ou padrão do computador local</span><span class="sxs-lookup"><span data-stu-id="d3a8d-129">Example 3: Get WMI classes in the root or default namespace of the local computer</span></span>

<span data-ttu-id="d3a8d-130">Este exemplo obtém as classes WMI no namespace raiz ou padrão do computador local.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-130">This example gets the WMI classes in the root or default namespace of the local computer.</span></span>

```powershell
Get-WmiObject -Namespace "root/default" -List
```

### <span data-ttu-id="d3a8d-131">Exemplo 4: obter um serviço nomeado em vários computadores</span><span class="sxs-lookup"><span data-stu-id="d3a8d-131">Example 4: Get a named service on multiple computers</span></span>

<span data-ttu-id="d3a8d-132">Este exemplo obtém o serviço WinRM nos computadores especificados pelo valor do parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="d3a8d-132">This example gets the WinRM service on the computers specified by the value of the **ComputerName** parameter.</span></span>

```powershell
Get-WmiObject -Query "select * from win32_service where name='WinRM'" -ComputerName Server01, Server02 |
  Format-List -Property PSComputerName, Name, ExitCode, Name, ProcessID, StartMode, State, Status
```

```Output
PSComputerName : SERVER01
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 844
StartMode      : Auto
State          : Running
Status         : OK

PSComputerName : SERVER02
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 932
StartMode      : Auto
State          : Running
Status         : OK
```

<span data-ttu-id="d3a8d-133">Um operador de pipeline (|) envia a saída para o `Format-List` cmdlet, que adiciona a propriedade **PSComputerName** à saída padrão.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-133">A pipeline operator (|) sends the output to the `Format-List` cmdlet, which adds the **PSComputerName** property to the default output.</span></span> <span data-ttu-id="d3a8d-134">**PSComputerName** é um alias da propriedade **__Server** dos objetos que `Get-WmiObject` retorna.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-134">**PSComputerName** is an alias of the **__Server** property of the objects that `Get-WmiObject` returns.</span></span> <span data-ttu-id="d3a8d-135">Esse alias foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-135">This alias was introduced in PowerShell 3.0.</span></span>

### <span data-ttu-id="d3a8d-136">Exemplo 5: parar um serviço em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="d3a8d-136">Example 5: Stop a service on a remote computer</span></span>

<span data-ttu-id="d3a8d-137">Este exemplo interrompe o serviço WinRM em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-137">This example stops the WinRM service on a remote computer.</span></span> <span data-ttu-id="d3a8d-138">`Get-WmiObject` Obtém a instância do objeto de serviço WinRM em Server01.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-138">`Get-WmiObject` gets the instance of the WinRM service object on Server01.</span></span> <span data-ttu-id="d3a8d-139">Em seguida, ele invoca o método **StopService** da classe **Win32_Service** WMI nesse objeto.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-139">Then, it invokes the **StopService** method of the **Win32_Service** WMI class on that object.</span></span>

```powershell
(Get-WmiObject -Class Win32_Service -Filter "name='WinRM'" -ComputerName Server01).StopService()
```

<span data-ttu-id="d3a8d-140">Isso é equivalente a usar o `Stop-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-140">This is equivalent to using the `Stop-Service` cmdlet.</span></span>

### <span data-ttu-id="d3a8d-141">Exemplo 6: obter o BIOS no computador local</span><span class="sxs-lookup"><span data-stu-id="d3a8d-141">Example 6: Get the BIOS on the local computer</span></span>

<span data-ttu-id="d3a8d-142">Este exemplo obtém as informações do BIOS do computador local.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-142">This example gets the BIOS information from the local computer.</span></span> <span data-ttu-id="d3a8d-143">O parâmetro **Property** do `Format-List` cmdlet é usado para exibir todas as propriedades do objeto retornado em uma lista.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-143">The **Property** parameter of the `Format-List` cmdlet is used to display all properties of the returned object in a list.</span></span> <span data-ttu-id="d3a8d-144">Por padrão, somente o subconjunto de propriedades definido no `Types.ps1xml` arquivo de configuração é exibido.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-144">By default, only the subset of properties defined in the `Types.ps1xml` configuration file are displayed.</span></span>

```powershell
Get-WmiObject -Class Win32_Bios | Format-List -Property *
```

```Output
Status                : OK
Name                  : Phoenix ROM BIOS PLUS Version 1.10 A05
Caption               : Phoenix ROM BIOS PLUS Version 1.10 A05
SMBIOSPresent         : True
__GENUS               : 2
__CLASS               : Win32_BIOS
__SUPERCLASS          : CIM_BIOSElement
__DYNASTY             : CIM_ManagedSystemElement
__RELPATH             : Win32_BIOS.Name="Phoenix ROM BIOS PLUS Version 1.10
__PROPERTY_COUNT      : 27
__DERIVATION          : {CIM_BIOSElement, CIM_SoftwareElement, CIM_LogicalElement,
__SERVER              : Server01
__NAMESPACE           : root\cimv2
__PATH                : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
BiosCharacteristics   : {7, 9, 10, 11...}
BIOSVersion           : {DELL   - 15, Phoenix ROM BIOS PLUS Version 1.10 A05}
BuildNumber           :
CodeSet               :
CurrentLanguage       : en|US|iso8859-1
Description           : Phoenix ROM BIOS PLUS Version 1.10 A05
IdentificationCode    :
InstallableLanguages  : 1
InstallDate           :
LanguageEdition       :
ListOfLanguages       : {en|US|iso8859-1}
Manufacturer          : Dell Inc.
OtherTargetOS         :
PrimaryBIOS           : True
ReleaseDate           : 20101103000000.000000+000
SerialNumber          : 8VDM9P1
SMBIOSBIOSVersion     : A05
SMBIOSMajorVersion    : 2
SMBIOSMinorVersion    : 6
SoftwareElementID     : Phoenix ROM BIOS PLUS Version 1.10 A05
SoftwareElementState  : 3
TargetOperatingSystem : 0
Version               : DELL   - 15
Scope                 : System.Management.ManagementScope
Path                  : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
Options               : System.Management.ObjectGetOptions
ClassPath             : \\JUNE-PC\root\cimv2:Win32_BIOS
Properties            : {BiosCharacteristics, BIOSVersion, BuildNumber, Caption...}
SystemProperties      : {__GENUS, __CLASS, __SUPERCLASS, __DYNASTY...}
Qualifiers            : {dynamic, Locale, provider, UUID}
Site                  :
Container             :
```

### <span data-ttu-id="d3a8d-145">Exemplo 7: obter os serviços em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="d3a8d-145">Example 7: Get the services on a remote computer</span></span>

<span data-ttu-id="d3a8d-146">Este exemplo usa o parâmetro **Credential** do `Get-WmiObject` cmdlet para obter os serviços em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-146">This example uses the **Credential** parameter of the `Get-WmiObject` cmdlet to get the services on a remote computer.</span></span> <span data-ttu-id="d3a8d-147">O valor do parâmetro **Credential** é um nome de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-147">The value of the **Credential** parameter is a user account name.</span></span> <span data-ttu-id="d3a8d-148">O usuário é solicitado para uma senha.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-148">The user is prompted for a password.</span></span>

```powershell
Get-WmiObject Win32_Service -Credential FABRIKAM\administrator -ComputerName Fabrikam
```

> [!NOTE]
> <span data-ttu-id="d3a8d-149">As credenciais não podem ser usadas ao direcionar o computador local.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-149">Credentials cannot be used when targeting the local computer.</span></span>

## <span data-ttu-id="d3a8d-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d3a8d-150">PARAMETERS</span></span>

### <span data-ttu-id="d3a8d-151">-Emendado</span><span class="sxs-lookup"><span data-stu-id="d3a8d-151">-Amended</span></span>

<span data-ttu-id="d3a8d-152">Obtém ou define um valor que indica se os objetos que são retornados do WMI devem conter informações aperfeiçoadas.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-152">Gets or sets a value that indicates whether the objects that are returned from WMI should contain amended information.</span></span> <span data-ttu-id="d3a8d-153">Normalmente, informações aperfeiçoadas são informações localizáveis, como descrições de objeto e propriedade, que são anexadas ao objeto WMI.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-153">Typically, amended information is localizable information, such as object and property descriptions, that is attached to the WMI object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3a8d-154">-AsJob</span><span class="sxs-lookup"><span data-stu-id="d3a8d-154">-AsJob</span></span>

<span data-ttu-id="d3a8d-155">Executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-155">Runs the command as a background job.</span></span> <span data-ttu-id="d3a8d-156">Use este parâmetro para executar comandos que levam muito tempo para serem concluídos.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-156">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="d3a8d-157">Quando você usa o parâmetro **AsJob** , o comando retorna um objeto que representa o trabalho em segundo plano e, em seguida, exibe o prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-157">When you use the **AsJob** parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span> <span data-ttu-id="d3a8d-158">É possível continuar a trabalhar na sessão enquanto o trabalho é concluído.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-158">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="d3a8d-159">Se `Get-WmiObject` é usado em um computador remoto, o trabalho é criado no computador local e os resultados de computadores remotos são retornados automaticamente para o computador local.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-159">If `Get-WmiObject` is used on a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="d3a8d-160">Para gerenciar o trabalho, utilize os cmdlets que contêm os cmdlets Job.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-160">To manage the job, use the cmdlets that contain the Job cmdlets.</span></span> <span data-ttu-id="d3a8d-161">Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-161">To get the job results, use the `Receive-Job` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="d3a8d-162">Para utilizar esse parâmetro com computadores remotos, os computadores local e remoto precisam ser configurados para acesso remoto.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-162">To use this parameter with remote computers, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="d3a8d-163">Além disso, você deve iniciar o Windows PowerShell usando a opção "Executar como administrador" no Windows Vista e versões posteriores do Windows.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-163">Additionally, you must start Windows PowerShell by using the "Run as administrator" option in Windows Vista and later versions of Windows.</span></span> <span data-ttu-id="d3a8d-164">Para obter mais informações, consulte [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3a8d-164">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="d3a8d-165">Para obter mais informações sobre trabalhos em segundo plano do Windows PowerShell, consulte [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md) e [about_Remote_Jobs](../Microsoft.PowerShell.Core/about/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="d3a8d-165">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/about/about_Remote_Jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3a8d-166">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="d3a8d-166">-Authentication</span></span>

<span data-ttu-id="d3a8d-167">Especifica o nível de autenticação a ser usado com a conexão WMI.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-167">Specifies the authentication level to be used with the WMI connection.</span></span>
<span data-ttu-id="d3a8d-168">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="d3a8d-168">Valid values are:</span></span>

- <span data-ttu-id="d3a8d-169">-1: inalterado</span><span class="sxs-lookup"><span data-stu-id="d3a8d-169">-1: Unchanged</span></span>
- <span data-ttu-id="d3a8d-170">0: padrão</span><span class="sxs-lookup"><span data-stu-id="d3a8d-170">0: Default</span></span>
- <span data-ttu-id="d3a8d-171">1: nenhum (nenhuma autenticação em executada.)</span><span class="sxs-lookup"><span data-stu-id="d3a8d-171">1: None (No authentication in performed.)</span></span>
- <span data-ttu-id="d3a8d-172">2: conectar (a autenticação é executada somente quando o cliente estabelece uma relação com o aplicativo.)</span><span class="sxs-lookup"><span data-stu-id="d3a8d-172">2: Connect (Authentication is performed only when the client establishes a relationship with the application.)</span></span>
- <span data-ttu-id="d3a8d-173">3: chamada (a autenticação é executada somente no início de cada chamada quando o aplicativo recebe a solicitação).</span><span class="sxs-lookup"><span data-stu-id="d3a8d-173">3: Call (Authentication is performed only at the beginning of each call when the application receives the request.)</span></span>
- <span data-ttu-id="d3a8d-174">4: pacote (a autenticação é executada em todos os dados que são recebidos do cliente.)</span><span class="sxs-lookup"><span data-stu-id="d3a8d-174">4: Packet (Authentication is performed on all the data that is received from the client.)</span></span>
- <span data-ttu-id="d3a8d-175">5: PacketIntegrity (todos os dados transferidos entre o cliente e o aplicativo são autenticados e verificados.)</span><span class="sxs-lookup"><span data-stu-id="d3a8d-175">5: PacketIntegrity (All the data that is transferred between the client and the application is authenticated and verified.)</span></span>
- <span data-ttu-id="d3a8d-176">6: PacketPrivacy (as propriedades dos outros níveis de autenticação são usadas e todos os dados são criptografados).</span><span class="sxs-lookup"><span data-stu-id="d3a8d-176">6: PacketPrivacy (The properties of the other authentication levels are used, and all the data is encrypted.)</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3a8d-177">-Autoridade</span><span class="sxs-lookup"><span data-stu-id="d3a8d-177">-Authority</span></span>

<span data-ttu-id="d3a8d-178">Especifica a autoridade a ser usada para autenticar a conexão WMI.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-178">Specifies the authority to use to authenticate the WMI connection.</span></span> <span data-ttu-id="d3a8d-179">É possível especificar uma autenticação padrão NTLM ou Kerberos.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-179">You can specify standard NTLM or Kerberos authentication.</span></span> <span data-ttu-id="d3a8d-180">Para usar o NTLM, defina a configuração de autoridade como `ntlmdomain:<DomainName>` , onde `<DomainName>` identifica um nome de domínio NTLM válido.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-180">To use NTLM, set the authority setting to `ntlmdomain:<DomainName>`, where `<DomainName>` identifies a valid NTLM domain name.</span></span> <span data-ttu-id="d3a8d-181">Para usar o Kerberos, especifique `kerberos:<DomainName>\<ServerName>` .</span><span class="sxs-lookup"><span data-stu-id="d3a8d-181">To use Kerberos, specify `kerberos:<DomainName>\<ServerName>`.</span></span> <span data-ttu-id="d3a8d-182">Não é possível, ao conectar-se ao computador local, incluir a configuração da autoridade.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-182">You cannot include the authority setting when you connect to the local computer.</span></span>

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

### <span data-ttu-id="d3a8d-183">-Classe</span><span class="sxs-lookup"><span data-stu-id="d3a8d-183">-Class</span></span>

<span data-ttu-id="d3a8d-184">Especifica o nome de uma classe WMI.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-184">Specifies the name of a WMI class.</span></span> <span data-ttu-id="d3a8d-185">Quando esse parâmetro é utilizado, o cmdlet recupera instâncias da classe WMI.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-185">When this parameter is used, the cmdlet retrieves instances of the WMI class.</span></span>

```yaml
Type: System.String
Parameter Sets: query, list
Aliases: ClassName

Required: True (query), False (list)
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3a8d-186">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d3a8d-186">-ComputerName</span></span>

<span data-ttu-id="d3a8d-187">Especifica o computador de destino para a operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-187">Specifies the target computer for the management operation.</span></span> <span data-ttu-id="d3a8d-188">Insira um nome de domínio totalmente qualificado (FQDN), um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-188">Enter a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="d3a8d-189">Quando o computador remoto está em um domínio diferente do computador local, o nome de domínio totalmente qualificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-189">When the remote computer is in a different domain than the local computer, the fully qualified domain name is required.</span></span>

<span data-ttu-id="d3a8d-190">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-190">The default is the local computer.</span></span> <span data-ttu-id="d3a8d-191">Para especificar o computador local, como em uma lista de nomes de computador, use "localhost", o nome do computador local ou um ponto (.).</span><span class="sxs-lookup"><span data-stu-id="d3a8d-191">To specify the local computer, such as in a list of computer names, use "localhost", the local computer name, or a dot (.).</span></span>

<span data-ttu-id="d3a8d-192">Esse parâmetro não se baseia no Windows PowerShell remotamente, que usa o WS-Management.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-192">This parameter does not rely on Windows PowerShell remoting, which uses WS-Management.</span></span> <span data-ttu-id="d3a8d-193">Você pode usar o parâmetro **ComputerName** de `Get-WmiObject` mesmo que o computador não esteja configurado para executar WS-Management comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-193">You can use the **ComputerName** parameter of `Get-WmiObject` even if your computer is not configured to run WS-Management remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3a8d-194">-Credential</span><span class="sxs-lookup"><span data-stu-id="d3a8d-194">-Credential</span></span>

<span data-ttu-id="d3a8d-195">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-195">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="d3a8d-196">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-196">The default is the current user.</span></span> <span data-ttu-id="d3a8d-197">Digite um nome de usuário, como "User01", "Domínio01 \ Usuário01" ou User@Contoso.com .</span><span class="sxs-lookup"><span data-stu-id="d3a8d-197">Type a user name, such as "User01", "Domain01\User01", or User@Contoso.com.</span></span> <span data-ttu-id="d3a8d-198">Ou insira um objeto **PSCredential** , como um objeto que é retornado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-198">Or, enter a **PSCredential** object, such as an object that is returned by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="d3a8d-199">Quando você digitar um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-199">When you type a user name, you are prompted for a password.</span></span> <span data-ttu-id="d3a8d-200">As credenciais não podem ser usadas ao direcionar o computador local.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-200">Credentials cannot be used when targeting the local computer.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3a8d-201">-DirectRead</span><span class="sxs-lookup"><span data-stu-id="d3a8d-201">-DirectRead</span></span>

<span data-ttu-id="d3a8d-202">Especifica se o acesso direto ao provedor WMI é solicitado para a classe especificada sem qualquer relação com a sua classe base ou suas classes derivadas.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-202">Specifies whether direct access to the WMI provider is requested for the specified class without any regard to its base class or to its derived classes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: query, WQLQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3a8d-203">-EnableAllPrivileges</span><span class="sxs-lookup"><span data-stu-id="d3a8d-203">-EnableAllPrivileges</span></span>

<span data-ttu-id="d3a8d-204">Habilita todos os privilégios do usuário atual antes do comando realizar a chamada WMI.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-204">Enables all the privileges of the current user before the command makes the WMI call.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3a8d-205">-Filter</span><span class="sxs-lookup"><span data-stu-id="d3a8d-205">-Filter</span></span>

<span data-ttu-id="d3a8d-206">Especifica uma cláusula **Where** para usar como um filtro.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-206">Specifies a **Where** clause to use as a filter.</span></span> <span data-ttu-id="d3a8d-207">Utiliza a sintaxe de linguagem de consulta WMI (WQL).</span><span class="sxs-lookup"><span data-stu-id="d3a8d-207">Uses the syntax of the WMI Query Language (WQL).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3a8d-208">Não inclua a palavra-chave **Where** no valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-208">Do not include the **Where** keyword in the value of the parameter.</span></span> <span data-ttu-id="d3a8d-209">Por exemplo, os seguintes comandos retornam somente os discos lógicos que têm um **DeviceID** de 'c:' e serviços com o nome 'WinRM' sem usar a palavra-chave **Where** .</span><span class="sxs-lookup"><span data-stu-id="d3a8d-209">For example, the following commands return only the logical disks that have a **DeviceID** of 'c:' and services that have the name 'WinRM' without using the **Where** keyword.</span></span>

`Get-WmiObject Win32_LogicalDisk -filter "DeviceID = 'c:' "`

`Get-WmiObject win32_service -filter "name='WinRM'"`

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3a8d-210">-Representação</span><span class="sxs-lookup"><span data-stu-id="d3a8d-210">-Impersonation</span></span>

<span data-ttu-id="d3a8d-211">Especifica o nível de representação a ser usado.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-211">Specifies the impersonation level to use.</span></span>

<span data-ttu-id="d3a8d-212">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="d3a8d-212">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d3a8d-213">0: padrão.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-213">0: Default.</span></span> <span data-ttu-id="d3a8d-214">Lê o registro local para o nível de representação padrão.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-214">Reads the local registry for the default impersonation level.</span></span> <span data-ttu-id="d3a8d-215">O padrão é geralmente definido como **Impersonate** .</span><span class="sxs-lookup"><span data-stu-id="d3a8d-215">The default is usually set to **Impersonate** .</span></span>
- <span data-ttu-id="d3a8d-216">1: anônimo.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-216">1: Anonymous.</span></span> <span data-ttu-id="d3a8d-217">Oculta as credenciais do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-217">Hides the credentials of the caller.</span></span>
- <span data-ttu-id="d3a8d-218">2: identificar.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-218">2: Identify.</span></span> <span data-ttu-id="d3a8d-219">Permite que os objetos consultem as credenciais do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-219">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="d3a8d-220">3: representar.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-220">3: Impersonate.</span></span> <span data-ttu-id="d3a8d-221">Permite que os objetos utilizem as credenciais do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-221">Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="d3a8d-222">4: delegar.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-222">4: Delegate.</span></span> <span data-ttu-id="d3a8d-223">Autoriza que os objetos permitam que outros objetos utilizem as credenciais do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-223">Allows objects to permit other objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3a8d-224">-Lista</span><span class="sxs-lookup"><span data-stu-id="d3a8d-224">-List</span></span>

<span data-ttu-id="d3a8d-225">Obtém os nomes das classes WMI no namespace do repositório WMI especificados pelo parâmetro **Namespace** .</span><span class="sxs-lookup"><span data-stu-id="d3a8d-225">Gets the names of the WMI classes in the WMI repository namespace that is specified by the **Namespace** parameter.</span></span>

<span data-ttu-id="d3a8d-226">Se você especificar o parâmetro de **lista** , mas não o parâmetro **namespace** , `Get-WmiObject` o usará o namespace **Root\Cimv2** por padrão.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-226">If you specify the **List** parameter, but not the **Namespace** parameter, `Get-WmiObject` uses the **Root\Cimv2** namespace by default.</span></span> <span data-ttu-id="d3a8d-227">Esse cmdlet não usa a entrada de registro de **namespace padrão** na `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WBEM\Scripting` chave do registro para determinar o namespace padrão.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-227">This cmdlet does not use the **Default Namespace** registry entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WBEM\Scripting` registry key to determine the default namespace.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3a8d-228">-Localidade</span><span class="sxs-lookup"><span data-stu-id="d3a8d-228">-Locale</span></span>

<span data-ttu-id="d3a8d-229">Especifica o local preferido para objetos WMI.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-229">Specifies the preferred locale for WMI objects.</span></span>
<span data-ttu-id="d3a8d-230">Insira um valor no formato MS_\<LCID\>.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-230">Enter a value in MS_\<LCID\> format.</span></span>

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

### <span data-ttu-id="d3a8d-231">-Namespace</span><span class="sxs-lookup"><span data-stu-id="d3a8d-231">-Namespace</span></span>

<span data-ttu-id="d3a8d-232">Quando utilizado com o parâmetro **Class** , o parâmetro **Namespace** especifica o namespace do repositório WMI onde se encontra a classe WMI especificada.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-232">When used with the **Class** parameter, the **Namespace** parameter specifies the WMI repository namespace where the specified WMI class is located.</span></span> <span data-ttu-id="d3a8d-233">Quando utilizado com o parâmetro **List** , ele especifica o namespace do qual coletar informações de classe WMI.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-233">When used with the **List** parameter, it specifies the namespace from which to gather WMI class information.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3a8d-234">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="d3a8d-234">-Property</span></span>

<span data-ttu-id="d3a8d-235">Especifica as propriedades de classe WMI das quais esse cmdlet obtém informações.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-235">Specifies the WMI class properties that this cmdlet gets information from.</span></span> <span data-ttu-id="d3a8d-236">Digite os nomes das propriedades.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-236">Enter the property names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: query
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3a8d-237">-Query</span><span class="sxs-lookup"><span data-stu-id="d3a8d-237">-Query</span></span>

<span data-ttu-id="d3a8d-238">Executa a instrução de linguagem de consulta WMI (WQL).</span><span class="sxs-lookup"><span data-stu-id="d3a8d-238">Runs the specified WMI Query Language (WQL) statement.</span></span> <span data-ttu-id="d3a8d-239">Esse parâmetro não oferece suporte a consultas de evento.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-239">This parameter does not support event queries.</span></span>

```yaml
Type: System.String
Parameter Sets: WQLQuery
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3a8d-240">-Recurse</span><span class="sxs-lookup"><span data-stu-id="d3a8d-240">-Recurse</span></span>

<span data-ttu-id="d3a8d-241">Pesquisa o namespace atual e todos os outros namespaces para o nome da classe que é especificada pelo parâmetro **Class** .</span><span class="sxs-lookup"><span data-stu-id="d3a8d-241">Searches the current namespace and all other namespaces for the class name that is specified by the **Class** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d3a8d-242">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="d3a8d-242">-ThrottleLimit</span></span>

<span data-ttu-id="d3a8d-243">Especifica o número máximo de operações de WMI que podem ser executadas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-243">Specifies the maximum number of WMI operations that can be executed simultaneously.</span></span> <span data-ttu-id="d3a8d-244">Esse parâmetro é válido somente quando o parâmetro **AsJob** é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-244">This parameter is valid only when the **AsJob** parameter is used in the command.</span></span>

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

### <span data-ttu-id="d3a8d-245">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d3a8d-245">CommonParameters</span></span>

<span data-ttu-id="d3a8d-246">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d3a8d-247">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d3a8d-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d3a8d-248">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d3a8d-248">INPUTS</span></span>

### <span data-ttu-id="d3a8d-249">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d3a8d-249">None</span></span>

<span data-ttu-id="d3a8d-250">Não é possível canalizar a entrada para `Get-WmiObject` .</span><span class="sxs-lookup"><span data-stu-id="d3a8d-250">You cannot pipe input to `Get-WmiObject`.</span></span>

## <span data-ttu-id="d3a8d-251">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d3a8d-251">OUTPUTS</span></span>

### <span data-ttu-id="d3a8d-252">PSObject ou System. Management. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="d3a8d-252">PSObject or System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="d3a8d-253">Ao utilizar o parâmetro **AsJob** , o cmdlet retorna um objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-253">When you use the **AsJob** parameter, the cmdlet returns a job object.</span></span> <span data-ttu-id="d3a8d-254">Caso contrário, o objeto que `Get-WmiObject` retorna depende do valor do parâmetro de **classe** .</span><span class="sxs-lookup"><span data-stu-id="d3a8d-254">Otherwise, the object that `Get-WmiObject` returns depends on the value of the **Class** parameter.</span></span>

## <span data-ttu-id="d3a8d-255">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d3a8d-255">NOTES</span></span>

<span data-ttu-id="d3a8d-256">Para acessar informações de WMI em um computador remoto, o cmdlet deve ser executado em uma conta que seja membro do grupo Administradores locais no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-256">To access WMI information on a remote computer, the cmdlet must run under an account that is a member of the local administrators group on the remote computer.</span></span> <span data-ttu-id="d3a8d-257">Ou, o controle de acesso padrão no namespace WMI do repositório remoto pode ser alterado para conceder direitos de acesso a outras contas.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-257">Or, the default access control on the WMI namespace of the remote repository can be changed to give access rights to other accounts.</span></span>

<span data-ttu-id="d3a8d-258">Apenas algumas das propriedades de cada classe WMI são exibidas por padrão.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-258">Only some of the properties of each WMI class are displayed by default.</span></span> <span data-ttu-id="d3a8d-259">O conjunto de propriedades que é exibido para cada classe WMI que é especificada no arquivo de configuração Types.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-259">The set of properties that is displayed for each WMI class is specified in the Types.ps1xml configuration file.</span></span> <span data-ttu-id="d3a8d-260">Para obter todas as propriedades de um objeto WMI, use `Get-Member` os `Format-List` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="d3a8d-260">To get all properties of a WMI object, use the `Get-Member` or `Format-List` cmdlets.</span></span>

## <span data-ttu-id="d3a8d-261">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d3a8d-261">RELATED LINKS</span></span>

[<span data-ttu-id="d3a8d-262">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="d3a8d-262">Invoke-WmiMethod</span></span>](Invoke-WmiMethod.md)

[<span data-ttu-id="d3a8d-263">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="d3a8d-263">Remove-WmiObject</span></span>](Remove-WmiObject.md)

[<span data-ttu-id="d3a8d-264">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="d3a8d-264">Set-WmiInstance</span></span>](Set-WmiInstance.md)

[<span data-ttu-id="d3a8d-265">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="d3a8d-265">Get-WSManInstance</span></span>](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[<span data-ttu-id="d3a8d-266">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="d3a8d-266">Invoke-WSManAction</span></span>](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[<span data-ttu-id="d3a8d-267">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="d3a8d-267">New-WSManInstance</span></span>](../Microsoft.WsMan.Management/New-WSManInstance.md)

[<span data-ttu-id="d3a8d-268">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="d3a8d-268">Remove-WSManInstance</span></span>](../Microsoft.WsMan.Management/Remove-WSManInstance.md)
