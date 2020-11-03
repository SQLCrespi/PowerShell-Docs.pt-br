---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-wmiinstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WmiInstance
ms.openlocfilehash: 03288a2ffbef416937b2c92a7d08a5aed49ffb43
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193919"
---
# <span data-ttu-id="1b179-103">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="1b179-103">Set-WmiInstance</span></span>

## <span data-ttu-id="1b179-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1b179-104">SYNOPSIS</span></span>
<span data-ttu-id="1b179-105">Cria ou atualiza uma instância de uma classe existente do WMI (Instrumentação de Gerenciamento do Windows).</span><span class="sxs-lookup"><span data-stu-id="1b179-105">Creates or updates an instance of an existing Windows Management Instrumentation (WMI) class.</span></span>

## <span data-ttu-id="1b179-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1b179-106">SYNTAX</span></span>

### <span data-ttu-id="1b179-107">classe (padrão)</span><span class="sxs-lookup"><span data-stu-id="1b179-107">class (Default)</span></span>

```
Set-WmiInstance [-Class] <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1b179-108">objeto</span><span class="sxs-lookup"><span data-stu-id="1b179-108">object</span></span>

```
Set-WmiInstance -InputObject <ManagementObject> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1b179-109">caminho</span><span class="sxs-lookup"><span data-stu-id="1b179-109">path</span></span>

```
Set-WmiInstance -Path <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1b179-110">WQLQuery</span><span class="sxs-lookup"><span data-stu-id="1b179-110">WQLQuery</span></span>

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1b179-111">Consulta</span><span class="sxs-lookup"><span data-stu-id="1b179-111">query</span></span>

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1b179-112">list</span><span class="sxs-lookup"><span data-stu-id="1b179-112">list</span></span>

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1b179-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1b179-113">DESCRIPTION</span></span>
<span data-ttu-id="1b179-114">O `Set-WmiInstance` cmdlet cria ou atualiza uma instância de uma classe de instrumentação de gerenciamento do Windows (WMI) existente.</span><span class="sxs-lookup"><span data-stu-id="1b179-114">The `Set-WmiInstance` cmdlet creates or updates an instance of an existing Windows Management Instrumentation (WMI) class.</span></span>
<span data-ttu-id="1b179-115">A instância criada ou atualizada é gravada no repositório do WMI.</span><span class="sxs-lookup"><span data-stu-id="1b179-115">The created or updated instance is written to the WMI repository.</span></span>

<span data-ttu-id="1b179-116">Novos cmdlets do CIM, apresentados pelo Windows PowerShell 3.0, executam as mesmas tarefas que os cmdlets do WMI.</span><span class="sxs-lookup"><span data-stu-id="1b179-116">New CIM cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span>
<span data-ttu-id="1b179-117">Os cmdlets do CIM estão em conformidade com os padrões do WSMan (WS-Management) e com o padrão modelo CIM (CIM).</span><span class="sxs-lookup"><span data-stu-id="1b179-117">The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard.</span></span>
<span data-ttu-id="1b179-118">Isso permite que os cmdlets usem as mesmas técnicas para gerenciar computadores baseados no Windows e aqueles que executam outros sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="1b179-118">this enables cmdlets to use the same techniques to manage Windows-based computers and those running other operating systems.</span></span>
<span data-ttu-id="1b179-119">Em vez de usar `Set-WmiInstance` , considere usar os cmdlets [set-Ciminstance](/powershell/module/cimcmdlets/set-ciminstance) ou [New-ciminstance](/powershell/module/cimcmdlets/new-ciminstance) .</span><span class="sxs-lookup"><span data-stu-id="1b179-119">Instead of using `Set-WmiInstance`, consider using the [Set-CimInstance](/powershell/module/cimcmdlets/set-ciminstance) or [New-CimInstance](/powershell/module/cimcmdlets/new-ciminstance) cmdlets.</span></span>

## <span data-ttu-id="1b179-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1b179-120">EXAMPLES</span></span>

### <span data-ttu-id="1b179-121">Exemplo 1: definir o nível de log do WMI</span><span class="sxs-lookup"><span data-stu-id="1b179-121">Example 1: Set WMI logging level</span></span>

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2}
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
```

<span data-ttu-id="1b179-122">Esse comando define o nível de log do WMI como 2.</span><span class="sxs-lookup"><span data-stu-id="1b179-122">This command sets the WMI logging level to 2.</span></span>
<span data-ttu-id="1b179-123">O comando passa a propriedade a ser definida e o valor, em conjunto, é considerado um par de valor, no parâmetro Argument.</span><span class="sxs-lookup"><span data-stu-id="1b179-123">The command passes the property to be set and the value, together considered a value pair, in the argument parameter.</span></span>
<span data-ttu-id="1b179-124">O parâmetro usa uma tabela de hash que é definida pela construção @{propriedade = valor}.</span><span class="sxs-lookup"><span data-stu-id="1b179-124">The parameter takes a hash table that is defined by the @{property = value} construction.</span></span>
<span data-ttu-id="1b179-125">As informações de classe que são retornadas refletem o novo valor.</span><span class="sxs-lookup"><span data-stu-id="1b179-125">The class information that is returned reflects the new value.</span></span>

### <span data-ttu-id="1b179-126">Exemplo 2: criar uma variável de ambiente e seu valor</span><span class="sxs-lookup"><span data-stu-id="1b179-126">Example 2: Create an environment variable and its value</span></span>

```
PS C:\> Set-WmiInstance -Class win32_environment -Argument @{Name="testvar";VariableValue="testvalue";UserName="<SYSTEM>"}
__GENUS          : 2
__CLASS          : Win32_Environment
__SUPERCLASS     : CIM_SystemResource
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Environment.Name="testvar",UserName="<SYSTEM>"
__PROPERTY_COUNT : 8
__DERIVATION     : {CIM_SystemResource, CIM_LogicalElement, CIM_ManagedSystemElement}
__SERVER         : SYSTEM01
__NAMESPACE      : root\cimv2
__PATH           : \\SYSTEM01\root\cimv2:Win32_Environment.Name="testvar",UserName="<SYSTEM>"
Caption          : <SYSTEM>\testvar
Description      : <SYSTEM>\testvar
InstallDate      :
Name             : testvar
Status           : OK
SystemVariable   : True
UserName         : <SYSTEM>
VariableValue    : testvalue
```

<span data-ttu-id="1b179-127">Esse comando cria a variável de ambiente testvar que tem o valor testValue.</span><span class="sxs-lookup"><span data-stu-id="1b179-127">This command creates the testvar environment variable that has the value testvalue.</span></span>
<span data-ttu-id="1b179-128">Ele faz isso criando uma nova instância da classe **Win32_Environment** WMI.</span><span class="sxs-lookup"><span data-stu-id="1b179-128">It does this by creating a new instance of the **Win32_Environment** WMI class.</span></span>
<span data-ttu-id="1b179-129">Esta operação requer credenciais apropriadas e você pode precisar reiniciar o Windows PowerShell para ver a nova variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="1b179-129">This operation requires appropriate credentials and that you may have to restart Windows PowerShell to see the new environment variable.</span></span>

### <span data-ttu-id="1b179-130">Exemplo 3: definir o nível de log do WMI para vários computadores remotos</span><span class="sxs-lookup"><span data-stu-id="1b179-130">Example 3: Set WMI logging level for several remote computers</span></span>

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2} -Computername "system01", "system02", "system03"
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
...
```

<span data-ttu-id="1b179-131">Esse comando define o nível de log do WMI como 2.</span><span class="sxs-lookup"><span data-stu-id="1b179-131">This command sets the WMI logging level to 2.</span></span>
<span data-ttu-id="1b179-132">O comando passa a propriedade a ser definida e o valor, em conjunto, é considerado um par de valor, no parâmetro Argument.</span><span class="sxs-lookup"><span data-stu-id="1b179-132">The command passes the property to be set and the value, together considered a value pair, in the argument parameter.</span></span>
<span data-ttu-id="1b179-133">O parâmetro usa uma tabela de hash que é definida pela construção @{propriedade = valor}.</span><span class="sxs-lookup"><span data-stu-id="1b179-133">The parameter takes a hash table that is defined by the @{property = value} construction.</span></span>
<span data-ttu-id="1b179-134">As informações de classe retornadas refletem o novo valor.</span><span class="sxs-lookup"><span data-stu-id="1b179-134">The returned class information reflects the new value.</span></span>

## <span data-ttu-id="1b179-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1b179-135">PARAMETERS</span></span>

### <span data-ttu-id="1b179-136">-Arguments</span><span class="sxs-lookup"><span data-stu-id="1b179-136">-Arguments</span></span>
<span data-ttu-id="1b179-137">Especifica o nome da propriedade a ser alterado e o novo valor para essa propriedade.</span><span class="sxs-lookup"><span data-stu-id="1b179-137">Specifies the name of the property to be changed and the new value for that property.</span></span>
<span data-ttu-id="1b179-138">O nome e o valor devem ser um par de nome-valor.</span><span class="sxs-lookup"><span data-stu-id="1b179-138">The name and value must be a name-value pair.</span></span>
<span data-ttu-id="1b179-139">O par nome-valor é passado na linha de comando como uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="1b179-139">The name-value pair is passed on the command line as a hash table.</span></span>
<span data-ttu-id="1b179-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1b179-140">For example:</span></span>

`@{Setting1=1; Setting2=5; Setting3="test"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: class, object, path
Aliases: Args, Property

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b179-141">-AsJob</span><span class="sxs-lookup"><span data-stu-id="1b179-141">-AsJob</span></span>
<span data-ttu-id="1b179-142">Indica que este cmdket é executado como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1b179-142">Indicates that this cmdket runs as a background job.</span></span>
<span data-ttu-id="1b179-143">Use este parâmetro para executar comandos que levam muito tempo para serem concluídos.</span><span class="sxs-lookup"><span data-stu-id="1b179-143">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="1b179-144">Quando você especifica o parâmetro *AsJob* , o comando retorna um objeto que representa o trabalho em segundo plano e, em seguida, exibe o prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="1b179-144">When you specify the *AsJob* parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span>
<span data-ttu-id="1b179-145">É possível continuar a trabalhar na sessão enquanto o trabalho é concluído.</span><span class="sxs-lookup"><span data-stu-id="1b179-145">You can continue to work in the session while the job finishes.</span></span>
<span data-ttu-id="1b179-146">Se **Set-WmiInstance** for usado para um computador remoto, o trabalho será criado no computador local e os resultados de computadores remotos serão retornados automaticamente para o computador local.</span><span class="sxs-lookup"><span data-stu-id="1b179-146">If **Set-WmiInstance** is used for a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="1b179-147">Para gerenciar o trabalho, use os cmdlets que contêm o substantivo do **trabalho** (os cmdlets de **trabalho** ).</span><span class="sxs-lookup"><span data-stu-id="1b179-147">To manage the job, use the cmdlets that contain the **Job** noun (the **Job** cmdlets).</span></span>
<span data-ttu-id="1b179-148">Para obter os resultados do trabalho, use o cmdlet Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="1b179-148">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="1b179-149">Para usar esse parâmetro junto com computadores remotos, os computadores locais e remotos devem ser configurados para comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="1b179-149">To use this parameter together with remote computers, the local and remote computers must be configured for remoting.</span></span>
<span data-ttu-id="1b179-150">Além disso, você deve iniciar o Windows PowerShell usando a opção Executar como administrador no Windows Vista e versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="1b179-150">Additionally, you must start Windows PowerShell by using the Run as administrator option in Windows Vista and later versions of the Windows operating system.</span></span>
<span data-ttu-id="1b179-151">Para obter mais informações, consulte about_Remote_Requirements.</span><span class="sxs-lookup"><span data-stu-id="1b179-151">For more information, see about_Remote_Requirements.</span></span>

<span data-ttu-id="1b179-152">Para obter mais informações sobre trabalhos em segundo plano do Windows PowerShell, consulte about_Jobs e about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="1b179-152">For more information about Windows PowerShell background jobs, see about_Jobs and about_Remote_Jobs.</span></span>

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

### <span data-ttu-id="1b179-153">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="1b179-153">-Authentication</span></span>
<span data-ttu-id="1b179-154">Especifica o nível de autenticação que deve ser usado com a conexão WMI.</span><span class="sxs-lookup"><span data-stu-id="1b179-154">Specifies the authentication level that must be used with the WMI connection.</span></span>
<span data-ttu-id="1b179-155">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="1b179-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1b179-156">-1: inalterado.</span><span class="sxs-lookup"><span data-stu-id="1b179-156">-1: Unchanged.</span></span>
- <span data-ttu-id="1b179-157">0: padrão.</span><span class="sxs-lookup"><span data-stu-id="1b179-157">0: Default.</span></span>
- <span data-ttu-id="1b179-158">1: nenhum.</span><span class="sxs-lookup"><span data-stu-id="1b179-158">1: None.</span></span>
<span data-ttu-id="1b179-159">Nenhuma autenticação em executada.</span><span class="sxs-lookup"><span data-stu-id="1b179-159">No authentication in performed.</span></span>
- <span data-ttu-id="1b179-160">2: conectar.</span><span class="sxs-lookup"><span data-stu-id="1b179-160">2: Connect.</span></span>
<span data-ttu-id="1b179-161">A autenticação é executada somente quando o cliente estabelece uma relação com o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1b179-161">Authentication is performed only when the client establishes a relationship with the application.</span></span>
- <span data-ttu-id="1b179-162">3: chamar.</span><span class="sxs-lookup"><span data-stu-id="1b179-162">3: Call.</span></span>
<span data-ttu-id="1b179-163">A autenticação é executada somente no início de cada chamada quando o aplicativo recebe a solicitação.</span><span class="sxs-lookup"><span data-stu-id="1b179-163">Authentication is performed only at the start of each call when the application receives the request.</span></span>
- <span data-ttu-id="1b179-164">4: pacote.</span><span class="sxs-lookup"><span data-stu-id="1b179-164">4: Packet.</span></span>
<span data-ttu-id="1b179-165">A autenticação é executada em todos os dados que são recebidos do cliente.</span><span class="sxs-lookup"><span data-stu-id="1b179-165">Authentication is performed on all the data that is received from the client.</span></span>
- <span data-ttu-id="1b179-166">5: PacketIntegrity.</span><span class="sxs-lookup"><span data-stu-id="1b179-166">5: PacketIntegrity.</span></span>
<span data-ttu-id="1b179-167">Todos os dados transferidos entre o cliente e o aplicativo são autenticados e verificados.</span><span class="sxs-lookup"><span data-stu-id="1b179-167">All the data that is transferred between the client and the application is authenticated and verified.</span></span>
- <span data-ttu-id="1b179-168">6: PacketPrivacy.</span><span class="sxs-lookup"><span data-stu-id="1b179-168">6: PacketPrivacy.</span></span>
<span data-ttu-id="1b179-169">As propriedades dos outros níveis de autenticação são usadas e todos os dados são criptografados.</span><span class="sxs-lookup"><span data-stu-id="1b179-169">The properties of the other authentication levels are used, and all the data is encrypted.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b179-170">-Autoridade</span><span class="sxs-lookup"><span data-stu-id="1b179-170">-Authority</span></span>
<span data-ttu-id="1b179-171">Especifica a autoridade a ser usada para autenticar a conexão WMI.</span><span class="sxs-lookup"><span data-stu-id="1b179-171">Specifies the authority to use to authenticate the WMI connection.</span></span>
<span data-ttu-id="1b179-172">É possível especificar uma autenticação padrão NTLM ou Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1b179-172">You can specify standard NTLM or Kerberos authentication.</span></span>
<span data-ttu-id="1b179-173">Para usar o NTLM, defina a configuração da autoridade como ntlmdomain: \<DomainName\>, em que \<DomainName\> identifica um nome de domínio válido do NTLM.</span><span class="sxs-lookup"><span data-stu-id="1b179-173">To use NTLM, set the authority setting to ntlmdomain:\<DomainName\>, where \<DomainName\> identifies a valid NTLM domain name.</span></span>
<span data-ttu-id="1b179-174">Para usar o Kerberos, especifique Kerberos: \<DomainName\> \\ \<ServerName\> .</span><span class="sxs-lookup"><span data-stu-id="1b179-174">To use Kerberos, specify kerberos:\<DomainName\>\\\<ServerName\>.</span></span>
<span data-ttu-id="1b179-175">Não é possível, ao conectar-se ao computador local, incluir a configuração da autoridade.</span><span class="sxs-lookup"><span data-stu-id="1b179-175">You cannot include the authority setting when you connect to the local computer.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b179-176">-Classe</span><span class="sxs-lookup"><span data-stu-id="1b179-176">-Class</span></span>
<span data-ttu-id="1b179-177">Especifica o nome de uma classe WMI.</span><span class="sxs-lookup"><span data-stu-id="1b179-177">Specifies the name of a WMI class.</span></span>

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b179-178">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="1b179-178">-ComputerName</span></span>
<span data-ttu-id="1b179-179">Especifica o nome do computador no qual este cmdlet é executado.</span><span class="sxs-lookup"><span data-stu-id="1b179-179">Specifies the name of the computer on which this cmdlet runs.</span></span>
<span data-ttu-id="1b179-180">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="1b179-180">The default is the local computer.</span></span>

<span data-ttu-id="1b179-181">Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um ou mais computadores.</span><span class="sxs-lookup"><span data-stu-id="1b179-181">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more computers.</span></span>
<span data-ttu-id="1b179-182">Para especificar o computador local, digite o nome do computador, um ponto (.) ou localhost.</span><span class="sxs-lookup"><span data-stu-id="1b179-182">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="1b179-183">Esse parâmetro não depende da comunicação remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b179-183">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="1b179-184">Você pode usar o parâmetro *ComputerName* , mesmo que seu computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="1b179-184">You can use the *ComputerName* parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: class, path, WQLQuery, query, list
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b179-185">-Credential</span><span class="sxs-lookup"><span data-stu-id="1b179-185">-Credential</span></span>
<span data-ttu-id="1b179-186">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="1b179-186">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="1b179-187">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="1b179-187">The default is the current user.</span></span>

<span data-ttu-id="1b179-188">Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um gerado pelo cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="1b179-188">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="1b179-189">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="1b179-189">If you type a user name, this cmdlet prompts for a password.</span></span>

<span data-ttu-id="1b179-190">Não há suporte para esse parâmetro em nenhum provedor instalado com o parâmetro de nenhum provedor instalado com o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b179-190">This parameter is not supported by any providers installed with parameter is not supported by any providers installed with Windows PowerShell.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b179-191">-EnableAllPrivileges</span><span class="sxs-lookup"><span data-stu-id="1b179-191">-EnableAllPrivileges</span></span>
<span data-ttu-id="1b179-192">Indica que esse cmdlet habilita todas as permissões do usuário atual antes do comando que faz a chamada WMI.</span><span class="sxs-lookup"><span data-stu-id="1b179-192">Indicates that this cmdlet enables all the permissions of the current user before the command it makes the WMI call.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b179-193">-Representação</span><span class="sxs-lookup"><span data-stu-id="1b179-193">-Impersonation</span></span>
<span data-ttu-id="1b179-194">Especifica o nível de representação a ser usado.</span><span class="sxs-lookup"><span data-stu-id="1b179-194">Specifies the impersonation level to use.</span></span>
<span data-ttu-id="1b179-195">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="1b179-195">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1b179-196">0: padrão.</span><span class="sxs-lookup"><span data-stu-id="1b179-196">0: Default.</span></span>
<span data-ttu-id="1b179-197">Lê o registro local para o nível de representação padrão, que geralmente é definido como 3: Impersonate.</span><span class="sxs-lookup"><span data-stu-id="1b179-197">Reads the local registry for the default impersonation level, which is usually set to 3: Impersonate.</span></span>
- <span data-ttu-id="1b179-198">1: anônimo.</span><span class="sxs-lookup"><span data-stu-id="1b179-198">1: Anonymous.</span></span>
<span data-ttu-id="1b179-199">Oculta as credenciais do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="1b179-199">Hides the credentials of the caller.</span></span>
- <span data-ttu-id="1b179-200">2: identificar.</span><span class="sxs-lookup"><span data-stu-id="1b179-200">2: Identify.</span></span>
<span data-ttu-id="1b179-201">Permite que os objetos consultem as credenciais do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="1b179-201">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="1b179-202">3: representar.</span><span class="sxs-lookup"><span data-stu-id="1b179-202">3: Impersonate.</span></span>
<span data-ttu-id="1b179-203">Permite que os objetos utilizem as credenciais do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="1b179-203">Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="1b179-204">4: delegar.</span><span class="sxs-lookup"><span data-stu-id="1b179-204">4: Delegate.</span></span>
<span data-ttu-id="1b179-205">Autoriza que os objetos permitam que outros objetos utilizem as credenciais do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="1b179-205">Allows objects to permit other objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b179-206">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1b179-206">-InputObject</span></span>
<span data-ttu-id="1b179-207">Especifica um objeto **ManagementObject** a ser usado como entrada.</span><span class="sxs-lookup"><span data-stu-id="1b179-207">Specifies a **ManagementObject** object to use as input.</span></span>
<span data-ttu-id="1b179-208">Quando esse parâmetro é usado, todos os outros parâmetros, exceto o parâmetro *arguments* , são ignorados.</span><span class="sxs-lookup"><span data-stu-id="1b179-208">When this parameter is used, all other parameters ,except the *Arguments* parameter, are ignored.</span></span>

```yaml
Type: System.Management.ManagementObject
Parameter Sets: object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1b179-209">-Localidade</span><span class="sxs-lookup"><span data-stu-id="1b179-209">-Locale</span></span>
<span data-ttu-id="1b179-210">Especifica o local preferido para objetos WMI.</span><span class="sxs-lookup"><span data-stu-id="1b179-210">Specifies the preferred locale for WMI objects.</span></span>
<span data-ttu-id="1b179-211">O parâmetro *locale* é especificado em uma matriz no formato MS_ \<LCID\> na ordem preferida.</span><span class="sxs-lookup"><span data-stu-id="1b179-211">The *Locale* parameter is specified in an array in the MS_\<LCID\> format in the preferred order.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b179-212">-Namespace</span><span class="sxs-lookup"><span data-stu-id="1b179-212">-Namespace</span></span>
<span data-ttu-id="1b179-213">Especifica o namespace do repositório WMI em que a classe WMI referenciada está localizada quando usada com o parâmetro de *classe* .</span><span class="sxs-lookup"><span data-stu-id="1b179-213">Specifies the WMI repository namespace where the referenced WMI class is located when it is used with the *Class* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b179-214">-Path</span><span class="sxs-lookup"><span data-stu-id="1b179-214">-Path</span></span>
<span data-ttu-id="1b179-215">Especifica um caminho de objeto WMI da instância que você deseja criar ou atualizar.</span><span class="sxs-lookup"><span data-stu-id="1b179-215">Specifies a WMI object path of the instance that you want to create or update.</span></span>

```yaml
Type: System.String
Parameter Sets: path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b179-216">-PutType</span><span class="sxs-lookup"><span data-stu-id="1b179-216">-PutType</span></span>
<span data-ttu-id="1b179-217">Indica se a instância do WMI deve ser criada ou atualizada.</span><span class="sxs-lookup"><span data-stu-id="1b179-217">Indicates whether to create or update the WMI instance.</span></span>
<span data-ttu-id="1b179-218">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="1b179-218">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1b179-219">UpdateOnly.</span><span class="sxs-lookup"><span data-stu-id="1b179-219">UpdateOnly.</span></span>
<span data-ttu-id="1b179-220">Atualiza uma instância existente do WMI.</span><span class="sxs-lookup"><span data-stu-id="1b179-220">Updates an existing WMI instance.</span></span>
- <span data-ttu-id="1b179-221">Somente Create.</span><span class="sxs-lookup"><span data-stu-id="1b179-221">CreateOnly.</span></span>
<span data-ttu-id="1b179-222">Cria uma nova instância do WMI.</span><span class="sxs-lookup"><span data-stu-id="1b179-222">Creates a new WMI instance.</span></span>
- <span data-ttu-id="1b179-223">UpdateOrCreate.</span><span class="sxs-lookup"><span data-stu-id="1b179-223">UpdateOrCreate.</span></span>
<span data-ttu-id="1b179-224">Atualiza a instância do WMI se ela existir, ou cria uma nova instância caso não exista.</span><span class="sxs-lookup"><span data-stu-id="1b179-224">Updates the WMI instance if it exists or creates a new instance if an instance does not exist.</span></span>

```yaml
Type: System.Management.PutType
Parameter Sets: (All)
Aliases:
Accepted values: None, UpdateOnly, CreateOnly, UpdateOrCreate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b179-225">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="1b179-225">-ThrottleLimit</span></span>
<span data-ttu-id="1b179-226">Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="1b179-226">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="1b179-227">Esse parâmetro é usado junto com o parâmetro *AsJob* .</span><span class="sxs-lookup"><span data-stu-id="1b179-227">This parameter is used together with the *AsJob* parameter.</span></span>
<span data-ttu-id="1b179-228">O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="1b179-228">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="1b179-229">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1b179-229">-Confirm</span></span>
<span data-ttu-id="1b179-230">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1b179-230">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b179-231">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1b179-231">-WhatIf</span></span>
<span data-ttu-id="1b179-232">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="1b179-232">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="1b179-233">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="1b179-233">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1b179-234">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1b179-234">CommonParameters</span></span>
<span data-ttu-id="1b179-235">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1b179-235">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1b179-236">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1b179-236">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1b179-237">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1b179-237">INPUTS</span></span>

### <span data-ttu-id="1b179-238">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1b179-238">None</span></span>
<span data-ttu-id="1b179-239">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="1b179-239">This cmdlet does not accept input.</span></span>

## <span data-ttu-id="1b179-240">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1b179-240">OUTPUTS</span></span>

### <span data-ttu-id="1b179-241">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1b179-241">None</span></span>
<span data-ttu-id="1b179-242">Esse cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="1b179-242">This cmdlet does not generate output.</span></span>

## <span data-ttu-id="1b179-243">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1b179-243">NOTES</span></span>

## <span data-ttu-id="1b179-244">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1b179-244">RELATED LINKS</span></span>

[<span data-ttu-id="1b179-245">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="1b179-245">Get-WmiObject</span></span>](Get-WmiObject.md)

[<span data-ttu-id="1b179-246">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="1b179-246">Invoke-WmiMethod</span></span>](Invoke-WmiMethod.md)

[<span data-ttu-id="1b179-247">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="1b179-247">Remove-WmiObject</span></span>](Remove-WmiObject.md)
