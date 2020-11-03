---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 6/17/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Computer
ms.openlocfilehash: 553b61c9669afab325e9feec101d701c2b9a7c83
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194900"
---
# <span data-ttu-id="27188-103">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="27188-103">Restart-Computer</span></span>

## <span data-ttu-id="27188-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="27188-104">SYNOPSIS</span></span>
<span data-ttu-id="27188-105">Reinicia o sistema operacional em computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="27188-105">Restarts the operating system on local and remote computers.</span></span>

## <span data-ttu-id="27188-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="27188-106">SYNTAX</span></span>

### <span data-ttu-id="27188-107">Padrãoset (padrão)</span><span class="sxs-lookup"><span data-stu-id="27188-107">DefaultSet (Default)</span></span>

```
Restart-Computer [-DcomAuthentication <AuthenticationLevel>] [-Impersonation <ImpersonationLevel>]
 [-WsmanAuthentication <String>] [-Protocol <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-Wait] [-Timeout <Int32>] [-For <WaitForServiceTypes>]
 [-Delay <Int16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="27188-108">AsJobset</span><span class="sxs-lookup"><span data-stu-id="27188-108">AsJobSet</span></span>

```
Restart-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>]
 [-Impersonation <ImpersonationLevel>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Force] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="27188-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="27188-109">DESCRIPTION</span></span>

<span data-ttu-id="27188-110">O `Restart-Computer` cmdlet reinicia o sistema operacional nos computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="27188-110">The `Restart-Computer` cmdlet restarts the operating system on the local and remote computers.</span></span>

<span data-ttu-id="27188-111">Você pode usar os parâmetros de `Restart-Computer` para executar as operações de reinicialização como um trabalho em segundo plano, para especificar os níveis de autenticação e as credenciais alternativas, para limitar as operações executadas ao mesmo tempo e forçar uma reinicialização imediata.</span><span class="sxs-lookup"><span data-stu-id="27188-111">You can use the parameters of `Restart-Computer` to run the restart operations as a background job, to specify the authentication levels and alternate credentials, to limit the operations that run at the same time, and to force an immediate restart.</span></span>

<span data-ttu-id="27188-112">A partir do Windows PowerShell 3,0, você pode aguardar a conclusão da reinicialização antes de executar o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="27188-112">Starting in Windows PowerShell 3.0, you can wait for the restart to complete before you run the next command.</span></span> <span data-ttu-id="27188-113">Especifique um tempo limite de espera e um intervalo de consulta e aguarde a disponibilidade de serviços específicos no computador reiniciado.</span><span class="sxs-lookup"><span data-stu-id="27188-113">Specify a waiting time-out and query interval, and wait for particular services to be available on the restarted computer.</span></span> <span data-ttu-id="27188-114">Esse recurso torna o uso prático `Restart-Computer` em scripts e funções.</span><span class="sxs-lookup"><span data-stu-id="27188-114">This feature makes it practical to use `Restart-Computer` in scripts and functions.</span></span>

<span data-ttu-id="27188-115">Você pode usar o protocolo WSMan (WS-Management) para reiniciar o computador, caso as chamadas DCOM (Component Object Model distribuídas) sejam bloqueadas, como por um firewall corporativo.</span><span class="sxs-lookup"><span data-stu-id="27188-115">You can use the WS-Management (WSMan) protocol to restart the computer, in case Distributed Component Object Model (DCOM) calls are blocked, such as by an enterprise firewall.</span></span> <span data-ttu-id="27188-116">Para obter mais informações, consulte [protocolo WS-Management](/windows/desktop/WinRM/ws-management-protocol).</span><span class="sxs-lookup"><span data-stu-id="27188-116">For more information, see [WS-Management Protocol](/windows/desktop/WinRM/ws-management-protocol).</span></span>

<span data-ttu-id="27188-117">Esse cmdlet requer a comunicação remota do Windows PowerShell somente quando você usa o parâmetro **AsJob** em um comando.</span><span class="sxs-lookup"><span data-stu-id="27188-117">This cmdlet requires Windows PowerShell remoting only when you use the **AsJob** parameter in a command.</span></span>

## <span data-ttu-id="27188-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="27188-118">EXAMPLES</span></span>

### <span data-ttu-id="27188-119">Exemplo 1: reiniciar o computador local</span><span class="sxs-lookup"><span data-stu-id="27188-119">Example 1: Restart the local computer</span></span>

<span data-ttu-id="27188-120">`Restart-Computer` reinicia o computador local.</span><span class="sxs-lookup"><span data-stu-id="27188-120">`Restart-Computer` restarts the local computer.</span></span>

```powershell
Restart-Computer
```

### <span data-ttu-id="27188-121">Exemplo 2: reiniciar vários computadores</span><span class="sxs-lookup"><span data-stu-id="27188-121">Example 2: Restart multiple computers</span></span>

<span data-ttu-id="27188-122">`Restart-Computer` pode reiniciar computadores remotos e locais.</span><span class="sxs-lookup"><span data-stu-id="27188-122">`Restart-Computer` can restart remote and local computers.</span></span> <span data-ttu-id="27188-123">O parâmetro **ComputerName** aceita uma matriz de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="27188-123">The **ComputerName** parameter accepts an array of computer names.</span></span>

```powershell
Restart-Computer -ComputerName Server01, Server02, localhost
```

### <span data-ttu-id="27188-124">Exemplo 3: reiniciar computadores como um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="27188-124">Example 3: Restart computers as a background job</span></span>

<span data-ttu-id="27188-125">Esses comandos executam um `Restart-Computer` comando como um trabalho em segundo plano em dois computadores remotos e, em seguida, obtêm os resultados.</span><span class="sxs-lookup"><span data-stu-id="27188-125">These commands run a `Restart-Computer` command as a background job on two remote computers, and then get the results.</span></span>

<span data-ttu-id="27188-126">Como **AsJob** cria o trabalho no computador local e retorna automaticamente os resultados para o computador local, você pode executar `Receive-Job` como um comando local.</span><span class="sxs-lookup"><span data-stu-id="27188-126">Because **AsJob** creates the job on the local computer and automatically returns the results to the local computer, you can run `Receive-Job` as a local command.</span></span>

```powershell
$Job = Restart-Computer -ComputerName "Server01", "Server02" -AsJob
$Job | Receive-Job
```

<span data-ttu-id="27188-127">`Restart-Computer` usa o parâmetro **ComputerName** para especificar **Server01** e **Server02** .</span><span class="sxs-lookup"><span data-stu-id="27188-127">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01** and **Server02** .</span></span> <span data-ttu-id="27188-128">O parâmetro **AsJob** executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="27188-128">The **AsJob** parameter runs the command as a background job.</span></span> <span data-ttu-id="27188-129">O objeto de trabalho é armazenado na `$Job` variável.</span><span class="sxs-lookup"><span data-stu-id="27188-129">The job object is stored in the `$Job` variable.</span></span> <span data-ttu-id="27188-130">`$Job` é enviado ao pipeline para o `Receive-Job` cmdlet que obtém os resultados.</span><span class="sxs-lookup"><span data-stu-id="27188-130">`$Job` is sent down the pipeline to the `Receive-Job` cmdlet that gets the results.</span></span>

### <span data-ttu-id="27188-131">Exemplo 4: reiniciar um computador remoto</span><span class="sxs-lookup"><span data-stu-id="27188-131">Example 4: Restart a remote computer</span></span>

<span data-ttu-id="27188-132">`Restart-Computer` reinicia um computador remoto com configurações personalizadas de representação e autenticação.</span><span class="sxs-lookup"><span data-stu-id="27188-132">`Restart-Computer` restarts a remote computer with customized impersonation and authentication settings.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

<span data-ttu-id="27188-133">`Restart-Computer` usa o parâmetro **ComputerName** para especificar **Server01** .</span><span class="sxs-lookup"><span data-stu-id="27188-133">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01** .</span></span> <span data-ttu-id="27188-134">O parâmetro **Impersonation** especifica Anonymous para ocultar a identidade do solicitante.</span><span class="sxs-lookup"><span data-stu-id="27188-134">The **Impersonation** parameter specifies Anonymous to hide the requester's identity.</span></span> <span data-ttu-id="27188-135">O parâmetro **DcomAuthentication** especifica PacketIntegrity como o nível de autenticação da conexão.</span><span class="sxs-lookup"><span data-stu-id="27188-135">The **DcomAuthentication** parameter specifies PacketIntegrity as the connection's authentication level.</span></span>

### <span data-ttu-id="27188-136">Exemplo 5: forçar a reinicialização de computadores listados em um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="27188-136">Example 5: Force restart of computers listed in a text file</span></span>

<span data-ttu-id="27188-137">Este exemplo força uma reinicialização imediata dos computadores listados no `Domain01.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="27188-137">This example forces an immediate restart of the computers listed in the `Domain01.txt` file.</span></span> <span data-ttu-id="27188-138">Os nomes de computador do arquivo de texto são armazenados em uma variável.</span><span class="sxs-lookup"><span data-stu-id="27188-138">The computer names from the text file are stored in a variable.</span></span> <span data-ttu-id="27188-139">O parâmetro **Force** força uma reinicialização imediata e o parâmetro **ThrottleLimit** limita o número de conexões simultâneas.</span><span class="sxs-lookup"><span data-stu-id="27188-139">The **Force** parameter forces an immediate restart and the **ThrottleLimit** parameter limits the number of concurrent connections.</span></span>

```powershell
$Names = Get-Content -Path C:\Domain01.txt
$Creds = Get-Credential
Restart-Computer -ComputerName $Names -Credential $Creds -Force -ThrottleLimit 10
```

<span data-ttu-id="27188-140">`Get-Content` usa o parâmetro **path** para obter uma lista de nomes de computador de um arquivo de texto, **Domain01.txt** .</span><span class="sxs-lookup"><span data-stu-id="27188-140">`Get-Content` uses the **Path** parameter to get a list of computer names from a text file, **Domain01.txt** .</span></span> <span data-ttu-id="27188-141">Os nomes dos computadores são armazenados na variável `$Names` .</span><span class="sxs-lookup"><span data-stu-id="27188-141">The computer names are stored in the variable `$Names`.</span></span> <span data-ttu-id="27188-142">`Get-Credential` solicita um nome de usuário e uma senha e armazena os valores na variável `$Creds` .</span><span class="sxs-lookup"><span data-stu-id="27188-142">`Get-Credential` prompts you for a username and password and stores the values in the variable `$Creds`.</span></span> <span data-ttu-id="27188-143">`Restart-Computer` usa os parâmetros **ComputerName** e **Credential** com suas variáveis.</span><span class="sxs-lookup"><span data-stu-id="27188-143">`Restart-Computer` uses the **ComputerName** and **Credential** parameters with their variables.</span></span> <span data-ttu-id="27188-144">O parâmetro **Force** causa uma reinicialização imediata de cada computador.</span><span class="sxs-lookup"><span data-stu-id="27188-144">The **Force** parameter causes an immediate restart of each computer.</span></span> <span data-ttu-id="27188-145">O parâmetro **ThrottleLimit** limita o comando a 10 conexões simultâneas.</span><span class="sxs-lookup"><span data-stu-id="27188-145">The **ThrottleLimit** parameter limits the command to 10 concurrent connections.</span></span>

### <span data-ttu-id="27188-146">Exemplo 6: reiniciar um computador remoto e aguardar o PowerShell</span><span class="sxs-lookup"><span data-stu-id="27188-146">Example 6: Restart a remote computer and wait for PowerShell</span></span>

<span data-ttu-id="27188-147">`Restart-Computer` reinicia o computador remoto e aguarda até 5 minutos (300 segundos) para que o PowerShell fique disponível no computador reiniciado antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="27188-147">`Restart-Computer` restarts the remote computer and then waits up to 5 minutes (300 seconds) for PowerShell to become available on the restarted computer before it continues.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Wait -For PowerShell -Timeout 300 -Delay 2
```

<span data-ttu-id="27188-148">`Restart-Computer` usa o parâmetro **ComputerName** para especificar **Server01** .</span><span class="sxs-lookup"><span data-stu-id="27188-148">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01** .</span></span> <span data-ttu-id="27188-149">O parâmetro **Wait** aguarda a conclusão da reinicialização.</span><span class="sxs-lookup"><span data-stu-id="27188-149">The **Wait** parameter waits for the restart to finish.</span></span> <span data-ttu-id="27188-150">O **para** especifica que o PowerShell pode executar comandos no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="27188-150">The **For** specifies that PowerShell can run commands on the remote computer.</span></span> <span data-ttu-id="27188-151">O parâmetro **Timeout** especifica uma espera de cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="27188-151">The **Timeout** parameter specifies a five-minute wait.</span></span> <span data-ttu-id="27188-152">O parâmetro **Delay** consulta o computador remoto a cada dois segundos para determinar se ele foi reiniciado.</span><span class="sxs-lookup"><span data-stu-id="27188-152">The **Delay** parameter queries the remote computer every two seconds to determine whether it's restarted.</span></span>

### <span data-ttu-id="27188-153">Exemplo 7: reiniciar um computador usando o protocolo WSMan</span><span class="sxs-lookup"><span data-stu-id="27188-153">Example 7: Restart a computer by using the WSMan Protocol</span></span>

<span data-ttu-id="27188-154">`Restart-Computer` reinicia o computador remoto usando o protocolo WSMan em vez do padrão, DCOM.</span><span class="sxs-lookup"><span data-stu-id="27188-154">`Restart-Computer` restarts the remote computer by using the WSMan protocol instead of the default, DCOM.</span></span> <span data-ttu-id="27188-155">A autenticação Kerberos determina se o usuário atual tem permissão para reiniciar o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="27188-155">Kerberos authentication determines whether the current user has permission to restart the remote computer.</span></span>

<span data-ttu-id="27188-156">Essas configurações foram projetadas para empresas nas quais as reinicializações baseadas em DCOM falham porque o DCOM está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="27188-156">These settings are designed for enterprises in which DCOM-based restarts fail because DCOM is blocked.</span></span> <span data-ttu-id="27188-157">Por exemplo, por um firewall.</span><span class="sxs-lookup"><span data-stu-id="27188-157">For example, by a firewall.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Protocol WSMan -WsmanAuthentication Kerberos
```

<span data-ttu-id="27188-158">`Restart-Computer` usa o parâmetro **ComputerName** para especificar o computador remoto, **Server01** .</span><span class="sxs-lookup"><span data-stu-id="27188-158">`Restart-Computer` uses the **ComputerName** parameter to specify the remote computer, **Server01** .</span></span>
<span data-ttu-id="27188-159">O parâmetro **Protocol** especifica o uso do protocolo WSMan.</span><span class="sxs-lookup"><span data-stu-id="27188-159">The **Protocol** parameter specifies to use the WSMan protocol.</span></span> <span data-ttu-id="27188-160">O parâmetro **WsmanAuthentication** especifica o método de autenticação como **Kerberos** .</span><span class="sxs-lookup"><span data-stu-id="27188-160">The **WsmanAuthentication** parameter specifies the authentication method as **Kerberos** .</span></span>

## <span data-ttu-id="27188-161">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="27188-161">PARAMETERS</span></span>

### <span data-ttu-id="27188-162">-AsJob</span><span class="sxs-lookup"><span data-stu-id="27188-162">-AsJob</span></span>

<span data-ttu-id="27188-163">Indica que `Restart-Computer` o é executado como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="27188-163">Indicates that `Restart-Computer` runs as a background job.</span></span>

<span data-ttu-id="27188-164">Para usar esse parâmetro, os computadores locais e remotos devem ser configurados para comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="27188-164">To use this parameter, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="27188-165">No Windows Vista e versões posteriores do sistema operacional Windows, você deve abrir o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="27188-165">On Windows Vista and later versions of the Windows operating system, you must open PowerShell by using the **Run as Administrator** option.</span></span> <span data-ttu-id="27188-166">Para obter mais informações, consulte [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27188-166">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="27188-167">Quando você especifica o parâmetro **AsJob** , o comando retorna imediatamente um objeto que representa o trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="27188-167">When you specify the **AsJob** parameter, the command immediately returns an object that represents the background job.</span></span> <span data-ttu-id="27188-168">É possível continuar a trabalhar na sessão enquanto o trabalho é concluído.</span><span class="sxs-lookup"><span data-stu-id="27188-168">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="27188-169">O trabalho é criado no computador local e os resultados de computadores remotos são retornados automaticamente para o computador local.</span><span class="sxs-lookup"><span data-stu-id="27188-169">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="27188-170">Para gerenciar o trabalho, use os cmdlets **Job** .</span><span class="sxs-lookup"><span data-stu-id="27188-170">To manage the job, use the **Job** cmdlets.</span></span> <span data-ttu-id="27188-171">Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="27188-171">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="27188-172">Para obter mais informações sobre trabalhos em segundo plano do Windows PowerShell, consulte [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) e [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="27188-172">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27188-173">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="27188-173">-ComputerName</span></span>

<span data-ttu-id="27188-174">Especifica um nome de computador ou uma matriz separada por vírgulas de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="27188-174">Specifies one computer name or a comma-separated array of computer names.</span></span> <span data-ttu-id="27188-175">`Restart-Computer` aceita objetos **ComputerName** do pipeline ou das variáveis.</span><span class="sxs-lookup"><span data-stu-id="27188-175">`Restart-Computer` accepts **ComputerName** objects from the pipeline or variables.</span></span>

<span data-ttu-id="27188-176">Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="27188-176">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span> <span data-ttu-id="27188-177">Para especificar o computador local, digite o nome do computador, um ponto `.` ou localhost.</span><span class="sxs-lookup"><span data-stu-id="27188-177">To specify the local computer, type the computer name, a dot `.`, or localhost.</span></span>

<span data-ttu-id="27188-178">Esse parâmetro não depende da comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27188-178">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="27188-179">Você pode usar o parâmetro **ComputerName** mesmo que o computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="27188-179">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

<span data-ttu-id="27188-180">Se o parâmetro **ComputerName** não for especificado, `Restart-Computer` o reiniciará o computador local.</span><span class="sxs-lookup"><span data-stu-id="27188-180">If the **ComputerName** parameter isn't specified, `Restart-Computer` restarts the local computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="27188-181">-Credential</span><span class="sxs-lookup"><span data-stu-id="27188-181">-Credential</span></span>

<span data-ttu-id="27188-182">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="27188-182">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="27188-183">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="27188-183">The default is the current user.</span></span>

<span data-ttu-id="27188-184">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="27188-184">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="27188-185">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="27188-185">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="27188-186">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="27188-186">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="27188-187">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="27188-187">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="27188-188">-DcomAuthentication</span><span class="sxs-lookup"><span data-stu-id="27188-188">-DcomAuthentication</span></span>

<span data-ttu-id="27188-189">Especifica o nível de autenticação que é usado para a conexão WMI.</span><span class="sxs-lookup"><span data-stu-id="27188-189">Specifies the authentication level that is used for the WMI connection.</span></span> <span data-ttu-id="27188-190">`Restart-Computer` usa o WMI.</span><span class="sxs-lookup"><span data-stu-id="27188-190">`Restart-Computer` uses WMI.</span></span>

<span data-ttu-id="27188-191">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="27188-191">Valid values are:</span></span>

- <span data-ttu-id="27188-192">**Chamada** : autenticação com em nível de chamada</span><span class="sxs-lookup"><span data-stu-id="27188-192">**Call** :            Call-level COM authentication</span></span>
- <span data-ttu-id="27188-193">**Conectar** : autenticação com no nível de conexão</span><span class="sxs-lookup"><span data-stu-id="27188-193">**Connect** :         Connect-level COM authentication</span></span>
- <span data-ttu-id="27188-194">**Padrão** : autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="27188-194">**Default** :         Windows Authentication</span></span>
- <span data-ttu-id="27188-195">**Nenhum** : nenhuma autenticação com</span><span class="sxs-lookup"><span data-stu-id="27188-195">**None** :            No COM authentication</span></span>
- <span data-ttu-id="27188-196">**Pacote** : autenticação com em nível de pacote.</span><span class="sxs-lookup"><span data-stu-id="27188-196">**Packet** :          Packet-level COM authentication.</span></span>
- <span data-ttu-id="27188-197">**PacketIntegrity** : autenticação com de nível de integridade de pacote</span><span class="sxs-lookup"><span data-stu-id="27188-197">**PacketIntegrity** : Packet Integrity-level COM authentication</span></span>
- <span data-ttu-id="27188-198">**PacketPrivacy** de privacidade: pacote de autenticação com.</span><span class="sxs-lookup"><span data-stu-id="27188-198">**PacketPrivacy** :   Packet Privacy-level COM authentication.</span></span>
- <span data-ttu-id="27188-199">**Inalterado** : o nível de autenticação é o mesmo que o comando anterior.</span><span class="sxs-lookup"><span data-stu-id="27188-199">**Unchanged** :       The authentication level is the same as the previous command.</span></span>

<span data-ttu-id="27188-200">Para obter mais informações, consulte [Enumeração AuthenticationLevel](/dotnet/api/system.management.authenticationlevel).</span><span class="sxs-lookup"><span data-stu-id="27188-200">For more information, see [AuthenticationLevel Enumeration](/dotnet/api/system.management.authenticationlevel).</span></span>

<span data-ttu-id="27188-201">Este parâmetro é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="27188-201">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27188-202">-Atraso</span><span class="sxs-lookup"><span data-stu-id="27188-202">-Delay</span></span>

<span data-ttu-id="27188-203">Especifica a frequência de consultas, em segundos.</span><span class="sxs-lookup"><span data-stu-id="27188-203">Specifies the frequency of queries, in seconds.</span></span> <span data-ttu-id="27188-204">O PowerShell consulta o serviço especificado pelo parâmetro **for** para determinar se o serviço está disponível depois que o computador é reiniciado.</span><span class="sxs-lookup"><span data-stu-id="27188-204">PowerShell queries the service specified by the **For** parameter to determine whether the service is available after the computer is restarted.</span></span>

<span data-ttu-id="27188-205">Esse parâmetro é válido somente junto com os parâmetros **Wait** e **for** .</span><span class="sxs-lookup"><span data-stu-id="27188-205">This parameter is valid only together with the **Wait** and **For** parameters.</span></span>

<span data-ttu-id="27188-206">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="27188-206">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="27188-207">Se o parâmetro **Delay** não for especificado, o `Restart-Computer` usará um atraso de cinco segundos.</span><span class="sxs-lookup"><span data-stu-id="27188-207">If the **Delay** parameter isn't specified, `Restart-Computer` uses a five second delay.</span></span>

```yaml
Type: System.Int16
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27188-208">-Para</span><span class="sxs-lookup"><span data-stu-id="27188-208">-For</span></span>

<span data-ttu-id="27188-209">Especifica o comportamento do PowerShell, pois ele aguarda que o serviço ou o recurso especificado se torne disponível após a reinicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="27188-209">Specifies the behavior of PowerShell as it waits for the specified service or feature to become available after the computer restarts.</span></span> <span data-ttu-id="27188-210">Esse parâmetro só é válido com o parâmetro **Wait** .</span><span class="sxs-lookup"><span data-stu-id="27188-210">This parameter is only valid with the **Wait** parameter.</span></span>

<span data-ttu-id="27188-211">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="27188-211">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="27188-212">**Padrão** : aguarda a reinicialização do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27188-212">**Default** : Waits for PowerShell to restart.</span></span>
- <span data-ttu-id="27188-213">**PowerShell** : pode executar comandos em uma sessão remota do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="27188-213">**PowerShell** : Can run commands in a PowerShell remote session on the computer.</span></span>
- <span data-ttu-id="27188-214">**WMI** : recebe uma resposta a uma consulta Win32_ComputerSystem para o computador.</span><span class="sxs-lookup"><span data-stu-id="27188-214">**WMI** : Receives a reply to a Win32_ComputerSystem query for the computer.</span></span>
- <span data-ttu-id="27188-215">**WinRM** : pode estabelecer uma sessão remota para o computador usando o WS-Management.</span><span class="sxs-lookup"><span data-stu-id="27188-215">**WinRM** : Can establish a remote session to the computer by using WS-Management.</span></span>

<span data-ttu-id="27188-216">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="27188-216">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WaitForServiceTypes
Parameter Sets: DefaultSet
Aliases:
Accepted values: Wmi, WinRM, PowerShell

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27188-217">-Force</span><span class="sxs-lookup"><span data-stu-id="27188-217">-Force</span></span>

<span data-ttu-id="27188-218">Força uma reinicialização imediata do computador.</span><span class="sxs-lookup"><span data-stu-id="27188-218">Forces an immediate restart of the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27188-219">-Representação</span><span class="sxs-lookup"><span data-stu-id="27188-219">-Impersonation</span></span>

<span data-ttu-id="27188-220">Especifica o nível de representação que esse cmdlet usa para chamar o WMI.</span><span class="sxs-lookup"><span data-stu-id="27188-220">Specifies the impersonation level that this cmdlet uses to call WMI.</span></span> <span data-ttu-id="27188-221">`Restart-Computer` usa o WMI.</span><span class="sxs-lookup"><span data-stu-id="27188-221">`Restart-Computer` uses WMI.</span></span>
<span data-ttu-id="27188-222">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="27188-222">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="27188-223">**Padrão** : representação padrão.</span><span class="sxs-lookup"><span data-stu-id="27188-223">**Default** : Default impersonation.</span></span> <span data-ttu-id="27188-224">Apesar do nome, esse não é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="27188-224">Despite the name, this isn't the default value.</span></span>
- <span data-ttu-id="27188-225">**Anônimo** : oculta a identidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="27188-225">**Anonymous** : Hides the identity of the caller.</span></span>
- <span data-ttu-id="27188-226">**Identificar** : permite que os objetos consultem as credenciais do chamador.</span><span class="sxs-lookup"><span data-stu-id="27188-226">**Identify** : Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="27188-227">**Impersonate** : permite que os objetos usem as credenciais do chamador.</span><span class="sxs-lookup"><span data-stu-id="27188-227">**Impersonate** : Allows objects to use the credentials of the caller.</span></span>

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

### <span data-ttu-id="27188-228">-Protocol</span><span class="sxs-lookup"><span data-stu-id="27188-228">-Protocol</span></span>

<span data-ttu-id="27188-229">Especifica o protocolo a ser usado para reiniciar os computadores.</span><span class="sxs-lookup"><span data-stu-id="27188-229">Specifies which protocol to use to restart the computers.</span></span> <span data-ttu-id="27188-230">Os valores válidos são **WSMan** e **DCOM** .</span><span class="sxs-lookup"><span data-stu-id="27188-230">The valid values are **WSMan** and **DCOM** .</span></span>

<span data-ttu-id="27188-231">Este parâmetro é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="27188-231">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27188-232">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="27188-232">-ThrottleLimit</span></span>

<span data-ttu-id="27188-233">Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="27188-233">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="27188-234">O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="27188-234">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

<span data-ttu-id="27188-235">Se o parâmetro **ThrottleLimit** não for especificado ou um valor de 0 for usado, `Restart-Computer` o usará um máximo de 32 conexões simultâneas.</span><span class="sxs-lookup"><span data-stu-id="27188-235">If the **ThrottleLimit** parameter isn't specified or a value of 0 is used, `Restart-Computer` uses a maximum of 32 concurrent connections.</span></span>

```yaml
Type: System.Int32
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27188-236">-Tempo limite</span><span class="sxs-lookup"><span data-stu-id="27188-236">-Timeout</span></span>

<span data-ttu-id="27188-237">Especifica a duração da espera, em segundos.</span><span class="sxs-lookup"><span data-stu-id="27188-237">Specifies the duration of the wait, in seconds.</span></span> <span data-ttu-id="27188-238">Quando o tempo limite expira, o `Restart-Computer` retorna ao prompt de comando, mesmo que os computadores não sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="27188-238">When the timeout elapses, `Restart-Computer` returns to the command prompt, even if the computers aren't restarted.</span></span>

<span data-ttu-id="27188-239">O parâmetro **Timeout** só é válido com o parâmetro **Wait** .</span><span class="sxs-lookup"><span data-stu-id="27188-239">The **Timeout** parameter is only valid with the **Wait** parameter.</span></span> <span data-ttu-id="27188-240">O **tempo limite** substitui o período de espera indefinido do parâmetro de **espera** .</span><span class="sxs-lookup"><span data-stu-id="27188-240">**Timeout** overrides the **Wait** parameter's indefinite waiting period.</span></span>

<span data-ttu-id="27188-241">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="27188-241">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultSet
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27188-242">-Wait</span><span class="sxs-lookup"><span data-stu-id="27188-242">-Wait</span></span>

<span data-ttu-id="27188-243">`Restart-Computer` suprime o prompt do PowerShell e bloqueia o pipeline até que os computadores sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="27188-243">`Restart-Computer` suppresses the PowerShell prompt and blocks the pipeline until the computers have restarted.</span></span> <span data-ttu-id="27188-244">Você pode usar esse parâmetro em um script para reiniciar os computadores e continuar a processar quando a reinicialização for concluída.</span><span class="sxs-lookup"><span data-stu-id="27188-244">You can use this parameter in a script to restart computers and then continue to process when the restart is finished.</span></span>

<span data-ttu-id="27188-245">O parâmetro **Wait** aguarda indefinidamente para que os computadores sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="27188-245">The **Wait** parameter waits indefinitely for the computers to restart.</span></span> <span data-ttu-id="27188-246">Você pode usar o **tempo limite** para ajustar o tempo e os parâmetros **de e de** **atraso** para aguardar que serviços específicos se tornem disponíveis nos computadores reiniciados.</span><span class="sxs-lookup"><span data-stu-id="27188-246">You can use **Timeout** to adjust the timing and the **For** and **Delay** parameters to wait for particular services to become available on the restarted computers.</span></span>

<span data-ttu-id="27188-247">O parâmetro **Wait** não é válido quando você está reiniciando o computador local.</span><span class="sxs-lookup"><span data-stu-id="27188-247">The **Wait** parameter isn't valid when you're restarting the local computer.</span></span> <span data-ttu-id="27188-248">Se o valor do parâmetro **ComputerName** contiver os nomes de computadores remotos e o computador local, o `Restart-Computer` gerará um erro de não finalização para **aguardar** no computador local, mas aguardará a reinicialização dos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="27188-248">If the value of the **ComputerName** parameter contains the names of remote computers and the local computer, `Restart-Computer` generates a non-terminating error for **Wait** on the local computer, but waits for the remote computers to restart.</span></span>

<span data-ttu-id="27188-249">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="27188-249">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27188-250">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="27188-250">-WsmanAuthentication</span></span>

<span data-ttu-id="27188-251">Especifica o mecanismo usado para autenticar as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="27188-251">Specifies the mechanism that is used to authenticate the user credentials.</span></span> <span data-ttu-id="27188-252">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="27188-252">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="27188-253">Os valores aceitáveis para esse parâmetro são: **Basic** , **CredSSP** , **Default** , **Digest** , **Kerberos** e **Negotiate** .</span><span class="sxs-lookup"><span data-stu-id="27188-253">The acceptable values for this parameter are: **Basic** , **CredSSP** , **Default** , **Digest** , **Kerberos** , and **Negotiate** .</span></span>

<span data-ttu-id="27188-254">Para obter mais informações, consulte [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="27188-254">For more information, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="27188-255">A autenticação do Credential Security Service Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, é projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="27188-255">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="27188-256">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="27188-256">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="27188-257">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="27188-257">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: Basic, CredSSP, Default, Digest, Kerberos, Negotiate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27188-258">-Confirm</span><span class="sxs-lookup"><span data-stu-id="27188-258">-Confirm</span></span>

<span data-ttu-id="27188-259">Solicita a confirmação antes de executar `Restart-Computer` .</span><span class="sxs-lookup"><span data-stu-id="27188-259">Prompts you for confirmation before running `Restart-Computer`.</span></span>

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

### <span data-ttu-id="27188-260">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="27188-260">-WhatIf</span></span>

<span data-ttu-id="27188-261">Mostra o que aconteceria se o `Restart-Computer` for executado.</span><span class="sxs-lookup"><span data-stu-id="27188-261">Shows what would happen if the `Restart-Computer` runs.</span></span> <span data-ttu-id="27188-262">O `Restart-Computer` cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="27188-262">The `Restart-Computer` cmdlet isn't run.</span></span>

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

### <span data-ttu-id="27188-263">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="27188-263">CommonParameters</span></span>

<span data-ttu-id="27188-264">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="27188-264">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="27188-265">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="27188-265">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="27188-266">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="27188-266">INPUTS</span></span>

### <span data-ttu-id="27188-267">System.String</span><span class="sxs-lookup"><span data-stu-id="27188-267">System.String</span></span>

<span data-ttu-id="27188-268">`Restart-Computer` aceita nomes de computador do pipeline ou de variáveis.</span><span class="sxs-lookup"><span data-stu-id="27188-268">`Restart-Computer` accepts computer names from the pipeline or variables.</span></span>

<span data-ttu-id="27188-269">No Windows PowerShell 2.0, o parâmetro **ComputerName** aceita entradas do pipeline somente pelo nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="27188-269">In Windows PowerShell 2.0, the **ComputerName** parameter takes input from the pipeline only by property name.</span></span> <span data-ttu-id="27188-270">No Windows PowerShell 3,0 e posterior, o parâmetro **ComputerName** usa a entrada do pipeline por valor.</span><span class="sxs-lookup"><span data-stu-id="27188-270">In Windows PowerShell 3.0, and later, the **ComputerName** parameter takes input from the pipeline by value.</span></span>

## <span data-ttu-id="27188-271">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="27188-271">OUTPUTS</span></span>

### <span data-ttu-id="27188-272">Nenhum, System. Management. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="27188-272">None, System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="27188-273">Se você especificar o parâmetro **AsJob** , o `Restart-Computer` retornará um objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="27188-273">If you specify the **AsJob** parameter, `Restart-Computer` returns a job object.</span></span> <span data-ttu-id="27188-274">Do contrário, nenhuma saída é gerada.</span><span class="sxs-lookup"><span data-stu-id="27188-274">Otherwise, no output is generated.</span></span>

## <span data-ttu-id="27188-275">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="27188-275">NOTES</span></span>

- <span data-ttu-id="27188-276">`Restart-Computer` Só funciona em computadores que executam o Windows e exige que o WinRM e o WMI desliguem um sistema, incluindo o sistema local.</span><span class="sxs-lookup"><span data-stu-id="27188-276">`Restart-Computer` only work on computers running Windows and requires WinRM and WMI to shutdown a system, including the local system.</span></span>
- <span data-ttu-id="27188-277">`Restart-Computer` usa o [método Win32Shutdown](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) da classe Instrumentação de gerenciamento do Windows (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) .</span><span class="sxs-lookup"><span data-stu-id="27188-277">`Restart-Computer` uses the [Win32Shutdown method](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) of the Windows Management Instrumentation (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) class.</span></span>  <span data-ttu-id="27188-278">Esse método requer que o privilégio **SeShutdownPrivilege** seja habilitado para a conta de usuário usada para reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="27188-278">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

<span data-ttu-id="27188-279">No Windows PowerShell 2,0, o parâmetro **AsJob** não funciona de maneira confiável quando você está reiniciando ou parando computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="27188-279">In Windows PowerShell 2.0, the **AsJob** parameter doesn't work reliably when you are restarting or stopping remote computers.</span></span> <span data-ttu-id="27188-280">No Windows PowerShell 3.0, a implementação é alterada para resolver esse problema.</span><span class="sxs-lookup"><span data-stu-id="27188-280">In Windows PowerShell 3.0, the implementation is changed to resolve this problem.</span></span>

## <span data-ttu-id="27188-281">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="27188-281">RELATED LINKS</span></span>

[<span data-ttu-id="27188-282">Sobre Gerenciamento Remoto do Windows</span><span class="sxs-lookup"><span data-stu-id="27188-282">About Windows Remote Management</span></span>](/windows/desktop/WinRM/about-windows-remote-management)

[<span data-ttu-id="27188-283">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="27188-283">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="27188-284">Protocolo WS-Management</span><span class="sxs-lookup"><span data-stu-id="27188-284">WS-Management Protocol</span></span>](/windows/desktop/WinRM/ws-management-protocol)
