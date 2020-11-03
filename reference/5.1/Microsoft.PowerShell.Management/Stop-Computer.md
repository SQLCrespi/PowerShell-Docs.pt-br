---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: 8062210aa94cb46d5e5557ede1bac672cae39622
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194898"
---
# <span data-ttu-id="a8f84-103">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="a8f84-103">Stop-Computer</span></span>

## <span data-ttu-id="a8f84-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a8f84-104">SYNOPSIS</span></span>
<span data-ttu-id="a8f84-105">Encerra (desliga) computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="a8f84-105">Stops (shuts down) local and remote computers.</span></span>

## <span data-ttu-id="a8f84-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a8f84-106">SYNTAX</span></span>

### <span data-ttu-id="a8f84-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="a8f84-107">All</span></span>

```
Stop-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="a8f84-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a8f84-108">DESCRIPTION</span></span>

<span data-ttu-id="a8f84-109">O `Stop-Computer` cmdlet desliga o computador local e os computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="a8f84-109">The `Stop-Computer` cmdlet shuts down the local computer and remote computers.</span></span>

<span data-ttu-id="a8f84-110">Você pode usar os parâmetros de `Stop-Computer` para executar as operações de desligamento como um trabalho em segundo plano, para especificar os níveis de autenticação e credenciais alternativas, para limitar as conexões simultâneas criadas para executar o comando e forçar um desligamento imediato.</span><span class="sxs-lookup"><span data-stu-id="a8f84-110">You can use the parameters of `Stop-Computer` to run the shutdown operations as a background job, to specify the authentication levels and alternate credentials, to limit the concurrent connections that are created to run the command, and to force an immediate shut down.</span></span>

<span data-ttu-id="a8f84-111">Esse cmdlet não requer comunicação remota do PowerShell, a menos que você use o parâmetro **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="a8f84-111">This cmdlet doesn't require PowerShell remoting unless you use the **AsJob** parameter.</span></span>

## <span data-ttu-id="a8f84-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a8f84-112">EXAMPLES</span></span>

### <span data-ttu-id="a8f84-113">Exemplo 1: desligar o computador local</span><span class="sxs-lookup"><span data-stu-id="a8f84-113">Example 1: Shut down the local computer</span></span>

<span data-ttu-id="a8f84-114">Este exemplo desliga o computador local.</span><span class="sxs-lookup"><span data-stu-id="a8f84-114">This example shuts down the local computer.</span></span>

```powershell
Stop-Computer -ComputerName localhost
```

### <span data-ttu-id="a8f84-115">Exemplo 2: desligar dois computadores remotos e o computador local</span><span class="sxs-lookup"><span data-stu-id="a8f84-115">Example 2: Shut down two remote computers and the local computer</span></span>

<span data-ttu-id="a8f84-116">Este exemplo interrompe dois computadores remotos e o computador local.</span><span class="sxs-lookup"><span data-stu-id="a8f84-116">This example stops two remote computers and the local computer.</span></span>

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="a8f84-117">`Stop-Computer` usa o parâmetro **ComputerName** para especificar dois computadores remotos e o computador local.</span><span class="sxs-lookup"><span data-stu-id="a8f84-117">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers and the local computer.</span></span> <span data-ttu-id="a8f84-118">Cada computador é desligado.</span><span class="sxs-lookup"><span data-stu-id="a8f84-118">Each computer is shut down.</span></span>

### <span data-ttu-id="a8f84-119">Exemplo 3: desligar computadores remotos como um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="a8f84-119">Example 3: Shut down remote computers as a background job</span></span>

<span data-ttu-id="a8f84-120">Neste exemplo, `Stop-Computer` é executado como um trabalho em segundo plano em dois computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="a8f84-120">In this example, `Stop-Computer` runs as a background job on two remote computers.</span></span>

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" -AsJob
$results = $j | Receive-Job
$results
```

<span data-ttu-id="a8f84-121">`Stop-Computer` usa o parâmetro **ComputerName** para especificar dois computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="a8f84-121">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers.</span></span> <span data-ttu-id="a8f84-122">O parâmetro **AsJob** executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a8f84-122">The **AsJob** parameter runs the command as a background job.</span></span> <span data-ttu-id="a8f84-123">Os objetos de trabalho são armazenados na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="a8f84-123">The job objects are stored in the `$j` variable.</span></span>

<span data-ttu-id="a8f84-124">Os objetos de trabalho na `$j` variável são enviados ao pipeline para `Receive-Job` , que obtém os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="a8f84-124">The job objects in the `$j` variable are sent down the pipeline to `Receive-Job`, which gets the job results.</span></span> <span data-ttu-id="a8f84-125">Os objetos são armazenados na `$results` variável.</span><span class="sxs-lookup"><span data-stu-id="a8f84-125">The objects are stored in the `$results` variable.</span></span> <span data-ttu-id="a8f84-126">A `$results` variável exibe as informações do trabalho no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8f84-126">The `$results` variable displays the job information in the PowerShell console.</span></span>

<span data-ttu-id="a8f84-127">Como **AsJob** cria o trabalho no computador local e retorna automaticamente os resultados para o computador local, você pode executar `Receive-Job` como um comando local.</span><span class="sxs-lookup"><span data-stu-id="a8f84-127">Because **AsJob** creates the job on the local computer and automatically returns the results to the local computer, you can run `Receive-Job` as a local command.</span></span>

### <span data-ttu-id="a8f84-128">Exemplo 4: desligar um computador remoto</span><span class="sxs-lookup"><span data-stu-id="a8f84-128">Example 4: Shut down a remote computer</span></span>

<span data-ttu-id="a8f84-129">Este exemplo desliga um computador remoto usando a autenticação especificada.</span><span class="sxs-lookup"><span data-stu-id="a8f84-129">This example shuts down a remote computer using specified authentication.</span></span>

```powershell
Stop-Computer -ComputerName "Server01" -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

<span data-ttu-id="a8f84-130">`Stop-Computer` usa o parâmetro **ComputerName** para especificar o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="a8f84-130">`Stop-Computer` uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="a8f84-131">O parâmetro **Impersonation** especifica uma representação personalizada e o parâmetro **DcomAuthentication** especifica as configurações de nível de autenticação.</span><span class="sxs-lookup"><span data-stu-id="a8f84-131">The **Impersonation** parameter specifies a customized impersonation and the **DcomAuthentication** parameter specifies authentication-level settings.</span></span>

### <span data-ttu-id="a8f84-132">Exemplo 5: desligar os computadores em um domínio</span><span class="sxs-lookup"><span data-stu-id="a8f84-132">Example 5: Shut down computers in a domain</span></span>

<span data-ttu-id="a8f84-133">Neste exemplo, os comandos forçam um desligamento imediato de todos os computadores em um domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="a8f84-133">In this example, the commands force an immediate shut down of all computers in a specified domain.</span></span>

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -ThrottleLimit 10 -Credential $c
```

<span data-ttu-id="a8f84-134">`Get-Content` usa o parâmetro **path** para obter um arquivo no diretório atual com a lista de computadores de domínio.</span><span class="sxs-lookup"><span data-stu-id="a8f84-134">`Get-Content` uses the **Path** parameter to get a file in the current directory with the list of domain computers.</span></span> <span data-ttu-id="a8f84-135">Os objetos são armazenados na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="a8f84-135">The objects are stored in the `$s` variable.</span></span>

<span data-ttu-id="a8f84-136">`Get-Credential` usa o parâmetro **Credential** para especificar as credenciais de um administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="a8f84-136">`Get-Credential` uses the **Credential** parameter to specify the credentials of a domain administrator.</span></span> <span data-ttu-id="a8f84-137">As credenciais são armazenadas na `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="a8f84-137">The credentials are stored in the `$c` variable.</span></span>

<span data-ttu-id="a8f84-138">`Stop-Computer` Desliga os computadores especificados com a lista de computadores do parâmetro **ComputerName** na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="a8f84-138">`Stop-Computer` shuts down the computers specified with the **ComputerName** parameter's list of computers in the `$s` variable.</span></span> <span data-ttu-id="a8f84-139">O parâmetro **Force** força um desligamento imediato.</span><span class="sxs-lookup"><span data-stu-id="a8f84-139">The **Force** parameter forces an immediate shutdown.</span></span> <span data-ttu-id="a8f84-140">O parâmetro **ThrottleLimit** limita o comando a 10 conexões simultâneas.</span><span class="sxs-lookup"><span data-stu-id="a8f84-140">The **ThrottleLimit** parameter limits the command to 10 concurrent connections.</span></span> <span data-ttu-id="a8f84-141">O parâmetro **Credential** envia as credenciais salvas na `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="a8f84-141">The **Credential** parameter submits the credentials saved in the `$c` variable.</span></span>

## <span data-ttu-id="a8f84-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a8f84-142">PARAMETERS</span></span>

### <span data-ttu-id="a8f84-143">-AsJob</span><span class="sxs-lookup"><span data-stu-id="a8f84-143">-AsJob</span></span>

<span data-ttu-id="a8f84-144">Indica que esse cmdlet é executado como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a8f84-144">Indicates that this cmdlet runs as a background job.</span></span>

<span data-ttu-id="a8f84-145">Para usar esse parâmetro, os computadores locais e remotos devem ser configurados para comunicação remota e, no Windows Vista e em versões posteriores do sistema operacional Windows, você deve abrir o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="a8f84-145">To use this parameter, the local and remote computers must be configured for remoting and, on Windows Vista and later versions of the Windows operating system, you must open PowerShell by using the **Run as administrator** option.</span></span> <span data-ttu-id="a8f84-146">Para obter mais informações, consulte [about_Remote_Requirements](..//microsoft.powershell.core/about/about_remote_requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8f84-146">For more information, see [about_Remote_Requirements](..//microsoft.powershell.core/about/about_remote_requirements.md).</span></span>

<span data-ttu-id="a8f84-147">Quando você especifica o parâmetro **AsJob** , o comando retorna imediatamente um objeto que representa o trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a8f84-147">When you specify the **AsJob** parameter, the command immediately returns an object that represents the background job.</span></span> <span data-ttu-id="a8f84-148">É possível continuar a trabalhar na sessão enquanto o trabalho é concluído.</span><span class="sxs-lookup"><span data-stu-id="a8f84-148">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="a8f84-149">O trabalho é criado no computador local e os resultados de computadores remotos são retornados automaticamente para o computador local.</span><span class="sxs-lookup"><span data-stu-id="a8f84-149">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="a8f84-150">Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a8f84-150">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="a8f84-151">Para obter mais informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](..//microsoft.powershell.core/about/about_jobs.md) e [about_Remote_Jobs](../microsoft.powershell.core/about/about_remote_jobs.md).</span><span class="sxs-lookup"><span data-stu-id="a8f84-151">For more information about PowerShell background jobs, see [about_Jobs](..//microsoft.powershell.core/about/about_jobs.md) and [about_Remote_Jobs](../microsoft.powershell.core/about/about_remote_jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a8f84-152">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="a8f84-152">-ComputerName</span></span>

<span data-ttu-id="a8f84-153">Especifica os computadores a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="a8f84-153">Specifies the computers to stop.</span></span> <span data-ttu-id="a8f84-154">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="a8f84-154">The default is the local computer.</span></span>

<span data-ttu-id="a8f84-155">Digite o nome da NETBIOS, o endereço IP ou o nome de domínio totalmente qualificado de um ou mais computadores em uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="a8f84-155">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="a8f84-156">Para especificar o computador local, digite o nome do computador ou localhost.</span><span class="sxs-lookup"><span data-stu-id="a8f84-156">To specify the local computer, type the computer name or localhost.</span></span>

<span data-ttu-id="a8f84-157">Esse parâmetro não depende da comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8f84-157">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="a8f84-158">Você pode usar o parâmetro **ComputerName** mesmo que o computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="a8f84-158">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a8f84-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a8f84-159">-Confirm</span></span>

<span data-ttu-id="a8f84-160">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a8f84-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a8f84-161">-Credential</span><span class="sxs-lookup"><span data-stu-id="a8f84-161">-Credential</span></span>

<span data-ttu-id="a8f84-162">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="a8f84-162">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="a8f84-163">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="a8f84-163">The default is the current user.</span></span>

<span data-ttu-id="a8f84-164">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a8f84-164">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="a8f84-165">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="a8f84-165">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="a8f84-166">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="a8f84-166">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="a8f84-167">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="a8f84-167">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a8f84-168">-DcomAuthentication</span><span class="sxs-lookup"><span data-stu-id="a8f84-168">-DcomAuthentication</span></span>

<span data-ttu-id="a8f84-169">Especifica o nível de autenticação que esse cmdlet usa com o WMI.</span><span class="sxs-lookup"><span data-stu-id="a8f84-169">Specifies the authentication level that this cmdlet uses with WMI.</span></span> <span data-ttu-id="a8f84-170">`Stop-Computer` usa o WMI.</span><span class="sxs-lookup"><span data-stu-id="a8f84-170">`Stop-Computer` uses WMI.</span></span> <span data-ttu-id="a8f84-171">O valor padrão é **pacote** .</span><span class="sxs-lookup"><span data-stu-id="a8f84-171">The default value is **Packet** .</span></span>

<span data-ttu-id="a8f84-172">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="a8f84-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a8f84-173">**Padrão** : autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="a8f84-173">**Default** : Windows Authentication.</span></span>
- <span data-ttu-id="a8f84-174">**Nenhum** : nenhuma autenticação com.</span><span class="sxs-lookup"><span data-stu-id="a8f84-174">**None** : No COM authentication.</span></span>
- <span data-ttu-id="a8f84-175">**Connect** : autenticação com de nível de conexão.</span><span class="sxs-lookup"><span data-stu-id="a8f84-175">**Connect** : Connect-level COM authentication.</span></span>
- <span data-ttu-id="a8f84-176">**Chamada** : autenticação com em nível de chamada.</span><span class="sxs-lookup"><span data-stu-id="a8f84-176">**Call** : Call-level COM authentication.</span></span>
- <span data-ttu-id="a8f84-177">**Pacote** : autenticação com em nível de pacote.</span><span class="sxs-lookup"><span data-stu-id="a8f84-177">**Packet** : Packet-level COM authentication.</span></span>
- <span data-ttu-id="a8f84-178">**PacketIntegrity** : autenticação com de nível de integridade de pacote.</span><span class="sxs-lookup"><span data-stu-id="a8f84-178">**PacketIntegrity** : Packet Integrity-level COM authentication.</span></span>
- <span data-ttu-id="a8f84-179">**PacketPrivacy** de privacidade: pacote de autenticação com.</span><span class="sxs-lookup"><span data-stu-id="a8f84-179">**PacketPrivacy** : Packet Privacy-level COM authentication.</span></span>
- <span data-ttu-id="a8f84-180">**Inalterado** : o mesmo que o comando anterior.</span><span class="sxs-lookup"><span data-stu-id="a8f84-180">**Unchanged** : Same as the previous command.</span></span>

<span data-ttu-id="a8f84-181">Para obter mais informações sobre os valores desse parâmetro, consulte [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel).</span><span class="sxs-lookup"><span data-stu-id="a8f84-181">For more information about the values of this parameter, see [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel).</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a8f84-182">-Force</span><span class="sxs-lookup"><span data-stu-id="a8f84-182">-Force</span></span>

<span data-ttu-id="a8f84-183">Força um desligamento imediato do computador.</span><span class="sxs-lookup"><span data-stu-id="a8f84-183">Forces an immediate shut down of the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a8f84-184">-Representação</span><span class="sxs-lookup"><span data-stu-id="a8f84-184">-Impersonation</span></span>

<span data-ttu-id="a8f84-185">Especifica o nível de representação a ser usado quando este cmdlet chama WMI.</span><span class="sxs-lookup"><span data-stu-id="a8f84-185">Specifies the impersonation level to use when this cmdlet calls WMI.</span></span> <span data-ttu-id="a8f84-186">O valor padrão é **Impersonate** .</span><span class="sxs-lookup"><span data-stu-id="a8f84-186">The default value is **Impersonate** .</span></span>

<span data-ttu-id="a8f84-187">`Stop-Computer` usa o WMI.</span><span class="sxs-lookup"><span data-stu-id="a8f84-187">`Stop-Computer` uses WMI.</span></span> <span data-ttu-id="a8f84-188">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="a8f84-188">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a8f84-189">**Padrão** : representação padrão.</span><span class="sxs-lookup"><span data-stu-id="a8f84-189">**Default** : Default impersonation.</span></span>
- <span data-ttu-id="a8f84-190">**Anônimo** : oculta a identidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="a8f84-190">**Anonymous** : Hides the identity of the caller.</span></span>
- <span data-ttu-id="a8f84-191">**Identificar** : permite que os objetos consultem as credenciais do chamador.</span><span class="sxs-lookup"><span data-stu-id="a8f84-191">**Identify** : Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="a8f84-192">**Impersonate** : permite que os objetos usem as credenciais do chamador.</span><span class="sxs-lookup"><span data-stu-id="a8f84-192">**Impersonate** : Allows objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: Impersonate
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a8f84-193">-Protocol</span><span class="sxs-lookup"><span data-stu-id="a8f84-193">-Protocol</span></span>

<span data-ttu-id="a8f84-194">Especifica o protocolo a ser usado para reiniciar os computadores.</span><span class="sxs-lookup"><span data-stu-id="a8f84-194">Specifies which protocol to use to restart the computers.</span></span> <span data-ttu-id="a8f84-195">Os valores aceitáveis para esse parâmetro são: **WSMan** e **DCOM** .</span><span class="sxs-lookup"><span data-stu-id="a8f84-195">The acceptable values for this parameter are: **WSMan** and **DCOM** .</span></span> <span data-ttu-id="a8f84-196">O valor padrão é **DCOM** .</span><span class="sxs-lookup"><span data-stu-id="a8f84-196">The default value is **DCOM** .</span></span>

<span data-ttu-id="a8f84-197">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="a8f84-197">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: DCOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a8f84-198">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="a8f84-198">-ThrottleLimit</span></span>

<span data-ttu-id="a8f84-199">Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="a8f84-199">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="a8f84-200">Se você omite esse parâmetro ou digita um valor 0, o valor padrão, 32, é usado.</span><span class="sxs-lookup"><span data-stu-id="a8f84-200">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="a8f84-201">O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="a8f84-201">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="a8f84-202">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="a8f84-202">-WsmanAuthentication</span></span>

<span data-ttu-id="a8f84-203">Especifica o mecanismo usado para autenticar as credenciais do usuário quando este cmdlet usa o protocolo WSMan.</span><span class="sxs-lookup"><span data-stu-id="a8f84-203">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="a8f84-204">O valor padrão é **Default** .</span><span class="sxs-lookup"><span data-stu-id="a8f84-204">The default value is **Default** .</span></span>

<span data-ttu-id="a8f84-205">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="a8f84-205">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a8f84-206">Básico</span><span class="sxs-lookup"><span data-stu-id="a8f84-206">Basic</span></span>
- <span data-ttu-id="a8f84-207">CredSSP</span><span class="sxs-lookup"><span data-stu-id="a8f84-207">CredSSP</span></span>
- <span data-ttu-id="a8f84-208">Padrão</span><span class="sxs-lookup"><span data-stu-id="a8f84-208">Default</span></span>
- <span data-ttu-id="a8f84-209">Digest</span><span class="sxs-lookup"><span data-stu-id="a8f84-209">Digest</span></span>
- <span data-ttu-id="a8f84-210">Kerberos</span><span class="sxs-lookup"><span data-stu-id="a8f84-210">Kerberos</span></span>
- <span data-ttu-id="a8f84-211">Negotiate.</span><span class="sxs-lookup"><span data-stu-id="a8f84-211">Negotiate.</span></span>

<span data-ttu-id="a8f84-212">Para obter mais informações sobre os valores desse parâmetro, consulte [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="a8f84-212">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="a8f84-213">A autenticação do Credential Security Service Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, é projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="a8f84-213">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="a8f84-214">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="a8f84-214">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="a8f84-215">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="a8f84-215">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="a8f84-216">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="a8f84-216">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a8f84-217">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a8f84-217">-WhatIf</span></span>

<span data-ttu-id="a8f84-218">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="a8f84-218">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a8f84-219">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="a8f84-219">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="a8f84-220">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a8f84-220">CommonParameters</span></span>

<span data-ttu-id="a8f84-221">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a8f84-221">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a8f84-222">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a8f84-222">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a8f84-223">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a8f84-223">INPUTS</span></span>

### <span data-ttu-id="a8f84-224">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a8f84-224">None</span></span>

<span data-ttu-id="a8f84-225">Não é possível canalizar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a8f84-225">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a8f84-226">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a8f84-226">OUTPUTS</span></span>

### <span data-ttu-id="a8f84-227">Nenhum ou System. Management. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="a8f84-227">None or System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="a8f84-228">O cmdlet retorna um objeto **System. Management. Automation. RemotingJob** , se você especificar o parâmetro **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="a8f84-228">The cmdlet returns a **System.Management.Automation.RemotingJob** object, if you specify the **AsJob** parameter.</span></span> <span data-ttu-id="a8f84-229">Caso contrário, ele não gerará nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="a8f84-229">Otherwise, it doesn't generate any output.</span></span>

## <span data-ttu-id="a8f84-230">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a8f84-230">NOTES</span></span>

<span data-ttu-id="a8f84-231">Esse cmdlet usa o método **Win32Shutdown** da classe WMI **Win32_OperatingSystem** .</span><span class="sxs-lookup"><span data-stu-id="a8f84-231">This cmdlet uses the **Win32Shutdown** method of the **Win32_OperatingSystem** WMI class.</span></span> <span data-ttu-id="a8f84-232">Esse método requer que o privilégio **SeShutdownPrivilege** seja habilitado para a conta de usuário usada para reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="a8f84-232">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

## <span data-ttu-id="a8f84-233">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a8f84-233">RELATED LINKS</span></span>

[<span data-ttu-id="a8f84-234">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="a8f84-234">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="a8f84-235">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="a8f84-235">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="a8f84-236">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="a8f84-236">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="a8f84-237">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="a8f84-237">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="a8f84-238">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="a8f84-238">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="a8f84-239">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="a8f84-239">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="a8f84-240">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="a8f84-240">Test-Connection</span></span>](Test-Connection.md)
