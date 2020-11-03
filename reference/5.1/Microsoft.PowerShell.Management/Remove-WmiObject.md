---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WmiObject
ms.openlocfilehash: 287eb02e7de2f4182e0ecfd7f6b6a7cafb66969e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193952"
---
# <span data-ttu-id="623a9-103">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="623a9-103">Remove-WmiObject</span></span>

## <span data-ttu-id="623a9-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="623a9-104">SYNOPSIS</span></span>
<span data-ttu-id="623a9-105">Exclui uma instância de uma classe existente do Windows Management Instrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="623a9-105">Deletes an instance of an existing Windows Management Instrumentation (WMI) class.</span></span>

## <span data-ttu-id="623a9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="623a9-106">SYNTAX</span></span>

### <span data-ttu-id="623a9-107">classe (padrão)</span><span class="sxs-lookup"><span data-stu-id="623a9-107">class (Default)</span></span>

```
Remove-WmiObject [-Class] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="623a9-108">objeto</span><span class="sxs-lookup"><span data-stu-id="623a9-108">object</span></span>

```
Remove-WmiObject -InputObject <ManagementObject> [-AsJob] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="623a9-109">caminho</span><span class="sxs-lookup"><span data-stu-id="623a9-109">path</span></span>

```
Remove-WmiObject -Path <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="623a9-110">WQLQuery</span><span class="sxs-lookup"><span data-stu-id="623a9-110">WQLQuery</span></span>

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="623a9-111">Consulta</span><span class="sxs-lookup"><span data-stu-id="623a9-111">query</span></span>

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="623a9-112">list</span><span class="sxs-lookup"><span data-stu-id="623a9-112">list</span></span>

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="623a9-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="623a9-113">DESCRIPTION</span></span>
<span data-ttu-id="623a9-114">O cmdlet **Remove-WmiObject** exclui uma instância de uma classe de instrumentação de gerenciamento do Windows (WMI) existente.</span><span class="sxs-lookup"><span data-stu-id="623a9-114">The **Remove-WmiObject** cmdlet deletes an instance of an existing Windows Management Instrumentation (WMI)class.</span></span>

## <span data-ttu-id="623a9-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="623a9-115">EXAMPLES</span></span>

### <span data-ttu-id="623a9-116">Exemplo 1: fechar todas as instâncias de um processo Win32</span><span class="sxs-lookup"><span data-stu-id="623a9-116">Example 1: Close all instances of a Win32 process</span></span>

```
PS C:\> notepad
PS C:\> $np = Get-WmiObject -Query "select * from win32_process where name='notepad.exe'"
PS C:\> $np | Remove-WmiObject
```

<span data-ttu-id="623a9-117">Este exemplo fecha todas as instâncias de Notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="623a9-117">This example closes all the instances of Notepad.exe.</span></span>

<span data-ttu-id="623a9-118">O primeiro comando inicia uma instância do bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="623a9-118">The first command starts an instance of Notepad.</span></span>

<span data-ttu-id="623a9-119">O segundo comando usa o cmdlet Get-WmiObject para recuperar as instâncias do Win32_Process que correspondem a Notepad.exe e, em seguida, as armazena na variável $np.</span><span class="sxs-lookup"><span data-stu-id="623a9-119">The second command uses the Get-WmiObject cmdlet to retrieve the instances of the Win32_Process that correspond to Notepad.exe, and then stores them in the $np variable.</span></span>

<span data-ttu-id="623a9-120">O terceiro comando passa o objeto na variável $np para **Remove-WmiObject** , que exclui todas as instâncias de Notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="623a9-120">The third command passes the object in the $np variable to **Remove-WmiObject** , which deletes all the instances of Notepad.exe.</span></span>

### <span data-ttu-id="623a9-121">Exemplo 2: excluir uma pasta</span><span class="sxs-lookup"><span data-stu-id="623a9-121">Example 2: Delete a folder</span></span>

```
PS C:\> $a = Get-WMIObject -Query "Select * From Win32_Directory Where Name ='C:\\Test'"
PS C:\> $a | Remove-WMIObject
```

<span data-ttu-id="623a9-122">Esse comando exclui a pasta C:\Test.</span><span class="sxs-lookup"><span data-stu-id="623a9-122">This command deletes the C:\Test folder.</span></span>

<span data-ttu-id="623a9-123">O primeiro comando usa **Get-WmiObject** para consultar a pasta C:\test e, em seguida, armazena o objeto na variável $a.</span><span class="sxs-lookup"><span data-stu-id="623a9-123">The first command uses **Get-WMIObject** to query for the C:\Test folder, and then stores the object in the $a variable.</span></span>

<span data-ttu-id="623a9-124">O segundo comando canaliza a variável $a para **Remove-WmiObject** , que exclui a pasta.</span><span class="sxs-lookup"><span data-stu-id="623a9-124">The second command pipes the $a variable to **Remove-WMIObject** , which deletes the folder.</span></span>

## <span data-ttu-id="623a9-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="623a9-125">PARAMETERS</span></span>

### <span data-ttu-id="623a9-126">-AsJob</span><span class="sxs-lookup"><span data-stu-id="623a9-126">-AsJob</span></span>
<span data-ttu-id="623a9-127">Indica que este cmdlet é executado como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="623a9-127">Indicates that this cmdlet run as a background job.</span></span>
<span data-ttu-id="623a9-128">Use este parâmetro para executar comandos que levam muito tempo para serem concluídos.</span><span class="sxs-lookup"><span data-stu-id="623a9-128">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="623a9-129">Novos cmdlets do CIM, apresentados pelo Windows PowerShell 3.0, executam as mesmas tarefas que os cmdlets do WMI.</span><span class="sxs-lookup"><span data-stu-id="623a9-129">New CIM cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span>
<span data-ttu-id="623a9-130">Os cmdlets do CIM estão em conformidade com os padrões do WSMan (WS-Management) e com o padrão modelo CIM (CIM), que permite que os cmdlets usem as mesmas técnicas para gerenciar computadores que executam o sistema operacional Windows e aqueles que executam outros sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="623a9-130">The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard, which enables the cmdlets to use the same techniques to manage computers that run the Windows operating system and those running other operating systems.</span></span>
<span data-ttu-id="623a9-131">Em vez de usar **Remove-WmiObject** , considere usar o cmdlet Remove-CimInstance https://go.microsoft.com/fwlink/?LinkId=227964 .</span><span class="sxs-lookup"><span data-stu-id="623a9-131">Instead of using **Remove-WmiObject** , consider using the Remove-CimInstancehttps://go.microsoft.com/fwlink/?LinkId=227964 cmdlet.</span></span>

<span data-ttu-id="623a9-132">Quando você usa o parâmetro *AsJob* , o comando retorna um objeto que representa o trabalho em segundo plano e, em seguida, exibe o prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="623a9-132">When you use the *AsJob* parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span>
<span data-ttu-id="623a9-133">É possível continuar a trabalhar na sessão enquanto o trabalho é concluído.</span><span class="sxs-lookup"><span data-stu-id="623a9-133">You can continue to work in the session while the job finishes.</span></span>
<span data-ttu-id="623a9-134">Se **Remove-WmiObject** for usado em um computador remoto, o trabalho será criado no computador local e os resultados de computadores remotos serão retornados automaticamente para o computador local.</span><span class="sxs-lookup"><span data-stu-id="623a9-134">If **Remove-WmiObject** is used against a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="623a9-135">Para gerenciar o trabalho, use os cmdlets que contêm o substantivo do **trabalho** (os cmdlets de **trabalho** ).</span><span class="sxs-lookup"><span data-stu-id="623a9-135">To manage the job, use the cmdlets that contain the **Job** noun (the **Job** cmdlets).</span></span>
<span data-ttu-id="623a9-136">Para obter os resultados do trabalho, use o cmdlet Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="623a9-136">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="623a9-137">Para usar esse parâmetro para computadores remotos, os computadores locais e remotos devem ser configurados para comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="623a9-137">To use this parameter for remote computers, the local and remote computers must be configured for remoting.</span></span>
<span data-ttu-id="623a9-138">Inicie o Windows PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="623a9-138">Start Windows PowerShell by using the Run as administrator option.</span></span>
<span data-ttu-id="623a9-139">Para obter mais informações, consulte about_Remote_Requirements.</span><span class="sxs-lookup"><span data-stu-id="623a9-139">For more information, see about_Remote_Requirements.</span></span>

<span data-ttu-id="623a9-140">Para obter mais informações sobre trabalhos em segundo plano do Windows PowerShell, consulte about_Jobs e about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="623a9-140">For more information about Windows PowerShell background jobs, see about_Jobs and about_Remote_Jobs.</span></span>

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

### <span data-ttu-id="623a9-141">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="623a9-141">-Authentication</span></span>
<span data-ttu-id="623a9-142">Especifica o nível de autenticação a ser usado para a conexão WMI.</span><span class="sxs-lookup"><span data-stu-id="623a9-142">Specifies the authentication level to use for the WMI connection.</span></span>
<span data-ttu-id="623a9-143">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="623a9-143">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="623a9-144">-1: inalterado.</span><span class="sxs-lookup"><span data-stu-id="623a9-144">-1: Unchanged.</span></span>
- <span data-ttu-id="623a9-145">0: padrão.</span><span class="sxs-lookup"><span data-stu-id="623a9-145">0: Default.</span></span>
- <span data-ttu-id="623a9-146">1: nenhum.</span><span class="sxs-lookup"><span data-stu-id="623a9-146">1: None.</span></span>
<span data-ttu-id="623a9-147">Nenhuma autenticação em executada.</span><span class="sxs-lookup"><span data-stu-id="623a9-147">No authentication in performed.</span></span>
- <span data-ttu-id="623a9-148">2: conectar.</span><span class="sxs-lookup"><span data-stu-id="623a9-148">2: Connect.</span></span>
<span data-ttu-id="623a9-149">A autenticação é executada somente quando o cliente estabelece uma relação com o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="623a9-149">Authentication is performed only when the client establishes a relationship with the application.</span></span>
- <span data-ttu-id="623a9-150">3: chamar.</span><span class="sxs-lookup"><span data-stu-id="623a9-150">3: Call.</span></span>
<span data-ttu-id="623a9-151">A autenticação é executada somente no início de cada chamada quando o aplicativo recebe a solicitação.</span><span class="sxs-lookup"><span data-stu-id="623a9-151">Authentication is performed only at the start of each call when the application receives the request.</span></span>
- <span data-ttu-id="623a9-152">4: pacote.</span><span class="sxs-lookup"><span data-stu-id="623a9-152">4: Packet.</span></span>
<span data-ttu-id="623a9-153">A autenticação é executada em todos os dados que são recebidos do cliente.</span><span class="sxs-lookup"><span data-stu-id="623a9-153">Authentication is performed on all the data that is received from the client.</span></span>
- <span data-ttu-id="623a9-154">5: PacketIntegrity.</span><span class="sxs-lookup"><span data-stu-id="623a9-154">5: PacketIntegrity.</span></span>
<span data-ttu-id="623a9-155">Todos os dados transferidos entre o cliente e o aplicativo são autenticados e verificados.</span><span class="sxs-lookup"><span data-stu-id="623a9-155">All the data that is transferred between the client and the application is authenticated and verified.</span></span>
- <span data-ttu-id="623a9-156">6: PacketPrivacy.</span><span class="sxs-lookup"><span data-stu-id="623a9-156">6: PacketPrivacy.</span></span>
<span data-ttu-id="623a9-157">As propriedades dos outros níveis de autenticação são usadas e todos os dados são criptografados.</span><span class="sxs-lookup"><span data-stu-id="623a9-157">The properties of the other authentication levels are used, and all the data is encrypted.</span></span>

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

### <span data-ttu-id="623a9-158">-Autoridade</span><span class="sxs-lookup"><span data-stu-id="623a9-158">-Authority</span></span>
<span data-ttu-id="623a9-159">Especifica a autoridade a ser usada para autenticar a conexão WMI.</span><span class="sxs-lookup"><span data-stu-id="623a9-159">Specifies the authority to use to authenticate the WMI connection.</span></span>
<span data-ttu-id="623a9-160">É possível especificar uma autenticação padrão NTLM ou Kerberos.</span><span class="sxs-lookup"><span data-stu-id="623a9-160">You can specify standard NTLM or Kerberos authentication.</span></span>
<span data-ttu-id="623a9-161">Para usar o NTLM, defina a configuração da autoridade como ntlmdomain: \<DomainName\>, em que \<DomainName\> identifica um nome de domínio válido do NTLM.</span><span class="sxs-lookup"><span data-stu-id="623a9-161">To use NTLM, set the authority setting to ntlmdomain:\<DomainName\>, where \<DomainName\> identifies a valid NTLM domain name.</span></span>
<span data-ttu-id="623a9-162">Para usar o Kerberos, especifique Kerberos: \<DomainName\> \\ \<ServerName\> .</span><span class="sxs-lookup"><span data-stu-id="623a9-162">To use Kerberos, specify kerberos:\<DomainName\>\\\<ServerName\>.</span></span>
<span data-ttu-id="623a9-163">Não é possível, ao conectar-se ao computador local, incluir a configuração da autoridade.</span><span class="sxs-lookup"><span data-stu-id="623a9-163">You cannot include the authority setting when you connect to the local computer.</span></span>

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

### <span data-ttu-id="623a9-164">-Classe</span><span class="sxs-lookup"><span data-stu-id="623a9-164">-Class</span></span>
<span data-ttu-id="623a9-165">Especifica o nome de uma classe WMI que este cmdlet exclui.</span><span class="sxs-lookup"><span data-stu-id="623a9-165">Specifies the name of a WMI class that this cmdlet deletes.</span></span>

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

### <span data-ttu-id="623a9-166">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="623a9-166">-ComputerName</span></span>
<span data-ttu-id="623a9-167">Especifica o nome do computador no qual este cmdlet é executado.</span><span class="sxs-lookup"><span data-stu-id="623a9-167">Specifies the name of the computer on which this cmdlet runs.</span></span>
<span data-ttu-id="623a9-168">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="623a9-168">The default is the local computer.</span></span>

<span data-ttu-id="623a9-169">Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um ou mais computadores.</span><span class="sxs-lookup"><span data-stu-id="623a9-169">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more computers.</span></span>
<span data-ttu-id="623a9-170">Para especificar o computador local, digite o nome do computador, um ponto (.) ou localhost.</span><span class="sxs-lookup"><span data-stu-id="623a9-170">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="623a9-171">Esse parâmetro não depende da comunicação remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="623a9-171">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="623a9-172">Você pode usar o parâmetro *ComputerName* , mesmo que seu computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="623a9-172">You can use the *ComputerName* parameter even if your computer is not configured to run remote commands.</span></span>

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

### <span data-ttu-id="623a9-173">-Credential</span><span class="sxs-lookup"><span data-stu-id="623a9-173">-Credential</span></span>
<span data-ttu-id="623a9-174">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="623a9-174">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="623a9-175">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="623a9-175">The default is the current user.</span></span>

<span data-ttu-id="623a9-176">Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um gerado pelo cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="623a9-176">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="623a9-177">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="623a9-177">If you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="623a9-178">-EnableAllPrivileges</span><span class="sxs-lookup"><span data-stu-id="623a9-178">-EnableAllPrivileges</span></span>
<span data-ttu-id="623a9-179">Indica que esse cmdlet habilita todas as permissões do usuário atual antes do comando que faz a chamada WMI.</span><span class="sxs-lookup"><span data-stu-id="623a9-179">Indicates that this cmdlet enables all the permissions of the current user before the command it makes the WMI call.</span></span>

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

### <span data-ttu-id="623a9-180">-Representação</span><span class="sxs-lookup"><span data-stu-id="623a9-180">-Impersonation</span></span>
<span data-ttu-id="623a9-181">Especifica o nível de representação a ser usado.</span><span class="sxs-lookup"><span data-stu-id="623a9-181">Specifies the impersonation level to use.</span></span>
<span data-ttu-id="623a9-182">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="623a9-182">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="623a9-183">0: padrão.</span><span class="sxs-lookup"><span data-stu-id="623a9-183">0: Default.</span></span>
<span data-ttu-id="623a9-184">Lê o registro local para o nível de representação padrão, que geralmente é definido como 3: Impersonate.</span><span class="sxs-lookup"><span data-stu-id="623a9-184">Reads the local registry for the default impersonation level, which is usually set to 3: Impersonate.</span></span>
- <span data-ttu-id="623a9-185">1: anônimo.</span><span class="sxs-lookup"><span data-stu-id="623a9-185">1: Anonymous.</span></span>
<span data-ttu-id="623a9-186">Oculta as credenciais do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="623a9-186">Hides the credentials of the caller.</span></span>
- <span data-ttu-id="623a9-187">2: identificar.</span><span class="sxs-lookup"><span data-stu-id="623a9-187">2: Identify.</span></span>
<span data-ttu-id="623a9-188">Permite que os objetos consultem as credenciais do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="623a9-188">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="623a9-189">3: representar.</span><span class="sxs-lookup"><span data-stu-id="623a9-189">3: Impersonate.</span></span>
<span data-ttu-id="623a9-190">Permite que os objetos utilizem as credenciais do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="623a9-190">Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="623a9-191">4: delegar.</span><span class="sxs-lookup"><span data-stu-id="623a9-191">4: Delegate.</span></span>
<span data-ttu-id="623a9-192">Autoriza que os objetos permitam que outros objetos utilizem as credenciais do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="623a9-192">Allows objects to permit other objects to use the credentials of the caller.</span></span>

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

### <span data-ttu-id="623a9-193">-InputObject</span><span class="sxs-lookup"><span data-stu-id="623a9-193">-InputObject</span></span>
<span data-ttu-id="623a9-194">Especifica um objeto **ManagementObject** a ser usado como entrada.</span><span class="sxs-lookup"><span data-stu-id="623a9-194">Specifies a **ManagementObject** object to use as input.</span></span>
<span data-ttu-id="623a9-195">Quando esse parâmetro é utilizado, todos os outros parâmetros são ignorados.</span><span class="sxs-lookup"><span data-stu-id="623a9-195">When this parameter is used, all other parameters are ignored.</span></span>

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

### <span data-ttu-id="623a9-196">-Localidade</span><span class="sxs-lookup"><span data-stu-id="623a9-196">-Locale</span></span>
<span data-ttu-id="623a9-197">Especifica o local preferido para objetos WMI.</span><span class="sxs-lookup"><span data-stu-id="623a9-197">Specifies the preferred locale for WMI objects.</span></span>
<span data-ttu-id="623a9-198">O parâmetro *locale* é especificado como uma matriz no formato de MS_ \<LCID\> na ordem preferida.</span><span class="sxs-lookup"><span data-stu-id="623a9-198">The *Locale* parameter is specified as an array in the MS_\<LCID\> format in the preferred order.</span></span>

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

### <span data-ttu-id="623a9-199">-Namespace</span><span class="sxs-lookup"><span data-stu-id="623a9-199">-Namespace</span></span>
<span data-ttu-id="623a9-200">Especifica o namespace do repositório WMI em que a classe WMI referenciada está localizada quando usada com o parâmetro de *classe* .</span><span class="sxs-lookup"><span data-stu-id="623a9-200">Specifies the WMI repository namespace where the referenced WMI class is located when it is used with the *Class* parameter.</span></span>

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

### <span data-ttu-id="623a9-201">-Path</span><span class="sxs-lookup"><span data-stu-id="623a9-201">-Path</span></span>
<span data-ttu-id="623a9-202">Especifica o caminho do objeto WMI de uma classe WMI ou especifica o caminho do objeto WMI de uma instância de uma classe WMI para exclusão.</span><span class="sxs-lookup"><span data-stu-id="623a9-202">Specifies the WMI object path of a WMI class, or specifies the WMI object path of an instance of a WMI class to delete.</span></span>

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

### <span data-ttu-id="623a9-203">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="623a9-203">-ThrottleLimit</span></span>
<span data-ttu-id="623a9-204">Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="623a9-204">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="623a9-205">Esse parâmetro é usado junto com o parâmetro *AsJob* .</span><span class="sxs-lookup"><span data-stu-id="623a9-205">This parameter is used together with the *AsJob* parameter.</span></span>
<span data-ttu-id="623a9-206">O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="623a9-206">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="623a9-207">-Confirm</span><span class="sxs-lookup"><span data-stu-id="623a9-207">-Confirm</span></span>
<span data-ttu-id="623a9-208">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="623a9-208">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="623a9-209">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="623a9-209">-WhatIf</span></span>
<span data-ttu-id="623a9-210">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="623a9-210">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="623a9-211">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="623a9-211">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="623a9-212">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="623a9-212">CommonParameters</span></span>
<span data-ttu-id="623a9-213">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="623a9-213">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="623a9-214">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="623a9-214">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="623a9-215">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="623a9-215">INPUTS</span></span>

### <span data-ttu-id="623a9-216">System. Management. ManagementObject</span><span class="sxs-lookup"><span data-stu-id="623a9-216">System.Management.ManagementObject</span></span>
<span data-ttu-id="623a9-217">É possível canalizar um objeto de gerenciamento para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="623a9-217">You can pipe a management object to this cmdlet.</span></span>

## <span data-ttu-id="623a9-218">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="623a9-218">OUTPUTS</span></span>

### <span data-ttu-id="623a9-219">Nenhum, System. Management. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="623a9-219">None, System.Management.Automation.RemotingJob</span></span>
<span data-ttu-id="623a9-220">Esse cmdlet retorna um objeto de trabalho, se você especificar o parâmetro *AsJob* .</span><span class="sxs-lookup"><span data-stu-id="623a9-220">This cmdlet returns a job object, if you specify the *AsJob* parameter.</span></span>
<span data-ttu-id="623a9-221">Caso contrário, ele não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="623a9-221">Otherwise, it does not generate any output.</span></span>

## <span data-ttu-id="623a9-222">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="623a9-222">NOTES</span></span>

## <span data-ttu-id="623a9-223">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="623a9-223">RELATED LINKS</span></span>

[<span data-ttu-id="623a9-224">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="623a9-224">Get-WmiObject</span></span>](Get-WmiObject.md)

[<span data-ttu-id="623a9-225">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="623a9-225">Invoke-WmiMethod</span></span>](Invoke-WmiMethod.md)

[<span data-ttu-id="623a9-226">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="623a9-226">Set-WmiInstance</span></span>](Set-WmiInstance.md)
