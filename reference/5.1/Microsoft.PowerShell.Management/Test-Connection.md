---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: a8d3923db69a20cfada58391944b592cf999e6ef
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193900"
---
# <span data-ttu-id="4fe38-103">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="4fe38-103">Test-Connection</span></span>

## <span data-ttu-id="4fe38-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4fe38-104">SYNOPSIS</span></span>
<span data-ttu-id="4fe38-105">Envia pacotes de solicitação de eco ICMP, ou pings, para um ou mais computadores.</span><span class="sxs-lookup"><span data-stu-id="4fe38-105">Sends ICMP echo request packets, or pings, to one or more computers.</span></span>

## <span data-ttu-id="4fe38-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4fe38-106">SYNTAX</span></span>

### <span data-ttu-id="4fe38-107">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="4fe38-107">Default (Default)</span></span>

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-TimeToLive <Int32>]
 [-Delay <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="4fe38-108">Fonte</span><span class="sxs-lookup"><span data-stu-id="4fe38-108">Source</span></span>

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Credential <PSCredential>] [-Source] <String[]> [-Impersonation <ImpersonationLevel>]
 [-ThrottleLimit <Int32>] [-TimeToLive <Int32>] [-Delay <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="4fe38-109">Quiet</span><span class="sxs-lookup"><span data-stu-id="4fe38-109">Quiet</span></span>

```
Test-Connection [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-TimeToLive <Int32>] [-Delay <Int32>] [-Quiet]
 [<CommonParameters>]
```

## <span data-ttu-id="4fe38-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4fe38-110">DESCRIPTION</span></span>

<span data-ttu-id="4fe38-111">O `Test-Connection` cmdlet envia pacotes de solicitação de eco do protocolo ICMP, ou pings, para um ou mais computadores remotos e retorna as respostas de resposta de eco.</span><span class="sxs-lookup"><span data-stu-id="4fe38-111">The `Test-Connection` cmdlet sends Internet Control Message Protocol (ICMP) echo request packets, or pings, to one or more remote computers and returns the echo response replies.</span></span> <span data-ttu-id="4fe38-112">Você pode usar este cmdlet para determinar se um computador específico pode ser contatado em uma rede IP.</span><span class="sxs-lookup"><span data-stu-id="4fe38-112">You can use this cmdlet to determine whether a particular computer can be contacted across an IP network.</span></span>

<span data-ttu-id="4fe38-113">Você pode usar os parâmetros de `Test-Connection` para especificar os computadores de envio e de recebimento, para executar o comando como um trabalho em segundo plano, definir um tempo limite e um número de pings e configurar a conexão e a autenticação.</span><span class="sxs-lookup"><span data-stu-id="4fe38-113">You can use the parameters of `Test-Connection` to specify both the sending and receiving computers, to run the command as a background job, to set a time-out and number of pings, and to configure the connection and authentication.</span></span>

<span data-ttu-id="4fe38-114">Diferentemente do comando **ping** conhecido, `Test-Connection` retorna um objeto **Win32_PingStatus** que você pode investigar no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fe38-114">Unlike the familiar **ping** command, `Test-Connection` returns a **Win32_PingStatus** object that you can investigate in PowerShell.</span></span> <span data-ttu-id="4fe38-115">O parâmetro **Quiet** retorna um valor **booliano** em um objeto **System. Boolean** para cada conexão testada.</span><span class="sxs-lookup"><span data-stu-id="4fe38-115">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object for each tested connection.</span></span> <span data-ttu-id="4fe38-116">Se várias conexões forem testadas, uma matriz de valores **boolianos** será retornada.</span><span class="sxs-lookup"><span data-stu-id="4fe38-116">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="4fe38-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4fe38-117">EXAMPLES</span></span>

### <span data-ttu-id="4fe38-118">Exemplo 1: enviar solicitações de eco para um computador remoto</span><span class="sxs-lookup"><span data-stu-id="4fe38-118">Example 1: Send echo requests to a remote computer</span></span>

<span data-ttu-id="4fe38-119">Este exemplo envia pacotes de solicitação de eco do computador local para o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="4fe38-119">This example sends echo request packets from the local computer to the Server01 computer.</span></span>

```powershell
Test-Connection -ComputerName Server01
```

```Output
Source        Destination     IPV4Address     IPV6Address  Bytes    Time(ms)
------        -----------     -----------     -----------  -----    --------
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       1
```

<span data-ttu-id="4fe38-120">`Test-Connection` usa o parâmetro **ComputerName** para especificar o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="4fe38-120">`Test-Connection` uses the **ComputerName** parameter to specify the Server01 computer.</span></span>

### <span data-ttu-id="4fe38-121">Exemplo 2: enviar solicitações de eco para vários computadores</span><span class="sxs-lookup"><span data-stu-id="4fe38-121">Example 2: Send echo requests to several computers</span></span>

<span data-ttu-id="4fe38-122">Este exemplo envia pings do computador local para vários computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="4fe38-122">This example sends pings from the local computer to several remote computers.</span></span>

```powershell
Test-Connection -ComputerName Server01, Server02, Server12
```

### <span data-ttu-id="4fe38-123">Exemplo 3: enviar solicitações de eco de vários computadores a um computador</span><span class="sxs-lookup"><span data-stu-id="4fe38-123">Example 3: Send echo requests from several computers to a computer</span></span>

<span data-ttu-id="4fe38-124">Este exemplo envia pings de computadores de origem diferentes para um único computador remoto, Server01.</span><span class="sxs-lookup"><span data-stu-id="4fe38-124">This example sends pings from different source computers to a single remote computer, Server01.</span></span>

```powershell
Test-Connection -Source Server02, Server12, localhost -ComputerName Server01 -Credential Domain01\Admin01
```

<span data-ttu-id="4fe38-125">`Test-Connection` usa o parâmetro **Credential** para especificar as credenciais de um usuário que tem permissão para enviar uma solicitação de ping dos computadores de origem.</span><span class="sxs-lookup"><span data-stu-id="4fe38-125">`Test-Connection` uses the **Credential** parameter to specify the credentials of a user who has permission to send a ping request from the source computers.</span></span> <span data-ttu-id="4fe38-126">Use esse formato de comando para testar a latência de conexões de vários pontos.</span><span class="sxs-lookup"><span data-stu-id="4fe38-126">Use this command format to test the latency of connections from multiple points.</span></span>

### <span data-ttu-id="4fe38-127">Exemplo 4: usar parâmetros para personalizar o comando de teste</span><span class="sxs-lookup"><span data-stu-id="4fe38-127">Example 4: Use parameters to customize the test command</span></span>

<span data-ttu-id="4fe38-128">Este exemplo usa os parâmetros de `Test-Connection` para personalizar o comando.</span><span class="sxs-lookup"><span data-stu-id="4fe38-128">This example uses the parameters of `Test-Connection` to customize the command.</span></span> <span data-ttu-id="4fe38-129">O computador local envia um teste de ping para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="4fe38-129">The local computer sends a ping test to a remote computer.</span></span>

```powershell
Test-Connection -ComputerName Server01 -Count 3 -Delay 2 -TTL 255 -BufferSize 256 -ThrottleLimit 32
```

<span data-ttu-id="4fe38-130">`Test-Connection` usa o parâmetro **ComputerName** para especificar Server01.</span><span class="sxs-lookup"><span data-stu-id="4fe38-130">`Test-Connection` uses the **ComputerName** parameter to specify Server01.</span></span> <span data-ttu-id="4fe38-131">O parâmetro **Count** especifica que três pings são enviados para o computador Server01 com um **atraso** de intervalos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="4fe38-131">The **Count** parameter specifies three pings are sent to the Server01 computer with a **Delay** of 2-second intervals.</span></span>

<span data-ttu-id="4fe38-132">Você pode usar essas opções quando espera-se que a resposta de ping demore mais do que o normal, devido a um número estendido de saltos ou a uma condição de rede de tráfego alto.</span><span class="sxs-lookup"><span data-stu-id="4fe38-132">You might use these options when the ping response is expected to take longer than usual, either because of an extended number of hops or a high-traffic network condition.</span></span>

### <span data-ttu-id="4fe38-133">Exemplo 5: executar um teste como um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="4fe38-133">Example 5: Run a test as a background job</span></span>

<span data-ttu-id="4fe38-134">Este exemplo mostra como executar um `Test-Connection` comando como um trabalho em segundo plano do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fe38-134">This example shows how to run a `Test-Connection` command as a PowerShell background job.</span></span>

```powershell
$job = Test-Connection -ComputerName (Get-Content Servers.txt) -AsJob
if ($job.JobStateInfo.State -ne "Running") {$Results = Receive-Job $job}
```

<span data-ttu-id="4fe38-135">O `Test-Connection` comando executa ping de muitos computadores em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="4fe38-135">The `Test-Connection` command pings many computers in an enterprise.</span></span> <span data-ttu-id="4fe38-136">O valor do parâmetro **ComputerName** é um `Get-Content` comando que lê uma lista de nomes de computador do `Servers.txt file` .</span><span class="sxs-lookup"><span data-stu-id="4fe38-136">The value of the **ComputerName** parameter is a `Get-Content` command that reads a list of computer names from the `Servers.txt file`.</span></span> <span data-ttu-id="4fe38-137">O comando usa o parâmetro **AsJob** para executar o comando como um trabalho em segundo plano e salva o trabalho na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="4fe38-137">The command uses the **AsJob** parameter to run the command as a background job and it saves the job in the `$job` variable.</span></span>

<span data-ttu-id="4fe38-138">O `if` comando verifica para ver se o trabalho ainda não está em execução.</span><span class="sxs-lookup"><span data-stu-id="4fe38-138">The `if` command checks to see that the job isn't still running.</span></span> <span data-ttu-id="4fe38-139">Se o trabalho não estiver em execução, `Receive-Job` o obterá os resultados e os armazenará na `$Results` variável.</span><span class="sxs-lookup"><span data-stu-id="4fe38-139">If the job isn't running, `Receive-Job` gets the results and stores them in the `$Results` variable.</span></span>

### <span data-ttu-id="4fe38-140">Exemplo 6: executar ping em um computador remoto com credenciais</span><span class="sxs-lookup"><span data-stu-id="4fe38-140">Example 6: Ping a remote computer with credentials</span></span>

<span data-ttu-id="4fe38-141">Esse comando usa o `Test-Connection` cmdlet para executar ping em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="4fe38-141">This command uses the `Test-Connection` cmdlet to ping a remote computer.</span></span>

```powershell
Test-Connection Server55 -Credential Domain55\User01 -Impersonation Identify
```

<span data-ttu-id="4fe38-142">O comando usa o parâmetro **Credential** para especificar uma conta de usuário que tenha permissão para executar ping no computador remoto e o parâmetro **Impersonation** para alterar o nível de representação a ser **identificado** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-142">The command uses the **Credential** parameter to specify a user account that has permission to ping the remote computer and the **Impersonation** parameter to change the impersonation level to **Identify** .</span></span>

### <span data-ttu-id="4fe38-143">Exemplo 7: criar uma sessão somente se um teste de conexão tiver sucesso</span><span class="sxs-lookup"><span data-stu-id="4fe38-143">Example 7: Create a session only if a connection test succeeds</span></span>

<span data-ttu-id="4fe38-144">Este exemplo criará uma sessão no computador Server01 somente se pelo menos um dos pings enviados para o computador for executado com sucesso.</span><span class="sxs-lookup"><span data-stu-id="4fe38-144">This example creates a session on the Server01 computer only if at least one of the pings sent to the computer succeeds.</span></span>

```powershell
if (Test-Connection -ComputerName Server01 -Quiet) {New-PSSession Server01}
```

<span data-ttu-id="4fe38-145">O `if` comando usa o `Test-Connection` cmdlet para executar ping no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="4fe38-145">The `if` command uses the `Test-Connection` cmdlet to ping the Server01 computer.</span></span> <span data-ttu-id="4fe38-146">O comando usa o parâmetro **Quiet** , que retorna um valor **booliano** , em vez de um objeto **Win32_PingStatus** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-146">The command uses the **Quiet** parameter, which returns a **Boolean** value, instead of a **Win32_PingStatus** object.</span></span> <span data-ttu-id="4fe38-147">O valor é `$True` se qualquer um dos quatro pings for bem sucedido e for, caso contrário, `$False` .</span><span class="sxs-lookup"><span data-stu-id="4fe38-147">The value is `$True` if any of the four pings succeed and is, otherwise, `$False`.</span></span>

<span data-ttu-id="4fe38-148">Se o `Test-Connection` comando retornar um valor de `$True` , o comando usará o `New-PSSession` cmdlet para criar a **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-148">If the `Test-Connection` command returns a value of `$True`, the command uses the `New-PSSession` cmdlet to create the **PSSession** .</span></span>

## <span data-ttu-id="4fe38-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4fe38-149">PARAMETERS</span></span>

### <span data-ttu-id="4fe38-150">-AsJob</span><span class="sxs-lookup"><span data-stu-id="4fe38-150">-AsJob</span></span>

<span data-ttu-id="4fe38-151">Indica que esse cmdlet é executado como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4fe38-151">Indicates that this cmdlet runs as a background job.</span></span>

<span data-ttu-id="4fe38-152">Para usar esse parâmetro, os computadores locais e remotos devem ser configurados para comunicação remota e, no Windows Vista e em versões posteriores do sistema operacional Windows, você deve abrir o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-152">To use this parameter, the local and remote computers must be configured for remoting and, on Windows Vista and later versions of the Windows operating system, you must open PowerShell by using the **Run as administrator** option.</span></span> <span data-ttu-id="4fe38-153">Para obter mais informações, consulte [about_Remote_Requirements](../microsoft.powershell.core/about/about_remote_requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fe38-153">For more information, see [about_Remote_Requirements](../microsoft.powershell.core/about/about_remote_requirements.md).</span></span>

<span data-ttu-id="4fe38-154">Quando você especifica o parâmetro **AsJob** , o comando retorna imediatamente um objeto que representa o trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4fe38-154">When you specify the **AsJob** parameter, the command immediately returns an object that represents the background job.</span></span> <span data-ttu-id="4fe38-155">É possível continuar a trabalhar na sessão enquanto o trabalho é concluído.</span><span class="sxs-lookup"><span data-stu-id="4fe38-155">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="4fe38-156">O trabalho é criado no computador local e os resultados de computadores remotos são retornados automaticamente para o computador local.</span><span class="sxs-lookup"><span data-stu-id="4fe38-156">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="4fe38-157">Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4fe38-157">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="4fe38-158">Para obter mais informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](../Microsoft.PowerShell.Core/About/about_jobs.md) e [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_remote_jobs.md).</span><span class="sxs-lookup"><span data-stu-id="4fe38-158">For more information about PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_remote_jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4fe38-159">-BufferSize</span><span class="sxs-lookup"><span data-stu-id="4fe38-159">-BufferSize</span></span>

<span data-ttu-id="4fe38-160">Especifica o tamanho, em bytes, do buffer enviado com esse comando.</span><span class="sxs-lookup"><span data-stu-id="4fe38-160">Specifies the size, in bytes, of the buffer sent with this command.</span></span> <span data-ttu-id="4fe38-161">O valor padrão é 32.</span><span class="sxs-lookup"><span data-stu-id="4fe38-161">The default value is 32.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4fe38-162">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="4fe38-162">-ComputerName</span></span>

<span data-ttu-id="4fe38-163">Especifica os computadores para execução do ping.</span><span class="sxs-lookup"><span data-stu-id="4fe38-163">Specifies the computers to ping.</span></span> <span data-ttu-id="4fe38-164">Digite os nomes de computador ou endereços IP no formato IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="4fe38-164">Type the computer names or type IP addresses in IPv4 or IPv6 format.</span></span> <span data-ttu-id="4fe38-165">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="4fe38-165">Wildcard characters are not permitted.</span></span> <span data-ttu-id="4fe38-166">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="4fe38-166">This parameter is required.</span></span>

<span data-ttu-id="4fe38-167">Esse parâmetro não depende da comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fe38-167">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="4fe38-168">Você pode usar o parâmetro **ComputerName** mesmo que o computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="4fe38-168">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

> [!NOTE]
> <span data-ttu-id="4fe38-169">O parâmetro **ComputerName** é renomeado para **TargetName** no PowerShell 6,0 e superior.</span><span class="sxs-lookup"><span data-stu-id="4fe38-169">The **ComputerName** parameter is renamed to **TargetName** in PowerShell 6.0 and above.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, IPAddress, __SERVER, Server, Destination

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4fe38-170">-Contagem</span><span class="sxs-lookup"><span data-stu-id="4fe38-170">-Count</span></span>

<span data-ttu-id="4fe38-171">Especifica o número de solicitações de eco a enviar.</span><span class="sxs-lookup"><span data-stu-id="4fe38-171">Specifies the number of echo requests to send.</span></span> <span data-ttu-id="4fe38-172">O valor padrão é 4.</span><span class="sxs-lookup"><span data-stu-id="4fe38-172">The default value is 4.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4fe38-173">-Credential</span><span class="sxs-lookup"><span data-stu-id="4fe38-173">-Credential</span></span>

<span data-ttu-id="4fe38-174">Especifica uma conta de usuário que tenha permissão para enviar uma solicitação de ping do computador de origem.</span><span class="sxs-lookup"><span data-stu-id="4fe38-174">Specifies a user account that has permission to send a ping request from the source computer.</span></span> <span data-ttu-id="4fe38-175">Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um do `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4fe38-175">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="4fe38-176">O parâmetro **Credential** é válido somente quando o parâmetro **Source** também é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="4fe38-176">The **Credential** parameter is valid only when the **Source** parameter is used in the command.</span></span> <span data-ttu-id="4fe38-177">As credenciais não afetam o computador de destino.</span><span class="sxs-lookup"><span data-stu-id="4fe38-177">The credentials don't affect the destination computer.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Source
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4fe38-178">-DcomAuthentication</span><span class="sxs-lookup"><span data-stu-id="4fe38-178">-DcomAuthentication</span></span>

<span data-ttu-id="4fe38-179">Especifica o nível de autenticação que esse cmdlet usa com o WMI.</span><span class="sxs-lookup"><span data-stu-id="4fe38-179">Specifies the authentication level that this cmdlet uses with WMI.</span></span>
<span data-ttu-id="4fe38-180">`Test-Connection` usa o WMI.</span><span class="sxs-lookup"><span data-stu-id="4fe38-180">`Test-Connection` uses WMI.</span></span>
<span data-ttu-id="4fe38-181">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="4fe38-181">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4fe38-182">**Default** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-182">**Default** .</span></span> <span data-ttu-id="4fe38-183">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="4fe38-183">Windows Authentication</span></span>
- <span data-ttu-id="4fe38-184">**None** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-184">**None** .</span></span> <span data-ttu-id="4fe38-185">Não há autenticação COM</span><span class="sxs-lookup"><span data-stu-id="4fe38-185">No COM authentication</span></span>
- <span data-ttu-id="4fe38-186">**Conecte-se** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-186">**Connect** .</span></span> <span data-ttu-id="4fe38-187">Autenticação COM de nível de conexão</span><span class="sxs-lookup"><span data-stu-id="4fe38-187">Connect-level COM authentication</span></span>
- <span data-ttu-id="4fe38-188">**Chame** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-188">**Call** .</span></span> <span data-ttu-id="4fe38-189">Autenticação COM de nível de chamada</span><span class="sxs-lookup"><span data-stu-id="4fe38-189">Call-level COM authentication</span></span>
- <span data-ttu-id="4fe38-190">**Pacote** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-190">**Packet** .</span></span> <span data-ttu-id="4fe38-191">Autenticação COM em nível de pacote</span><span class="sxs-lookup"><span data-stu-id="4fe38-191">Packet-level COM authentication</span></span>
- <span data-ttu-id="4fe38-192">**PacketIntegrity** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-192">**PacketIntegrity** .</span></span> <span data-ttu-id="4fe38-193">Autenticação COM de nível de integridade de pacote</span><span class="sxs-lookup"><span data-stu-id="4fe38-193">Packet Integrity-level COM authentication</span></span>
- <span data-ttu-id="4fe38-194">**PacketPrivacy** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-194">**PacketPrivacy** .</span></span> <span data-ttu-id="4fe38-195">Privacidade do pacote-autenticação COM de nível</span><span class="sxs-lookup"><span data-stu-id="4fe38-195">Packet Privacy-level COM authentication</span></span>
- <span data-ttu-id="4fe38-196">**Inalterado** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-196">**Unchanged** .</span></span> <span data-ttu-id="4fe38-197">O mesmo que o comando anterior</span><span class="sxs-lookup"><span data-stu-id="4fe38-197">Same as the previous command</span></span>

<span data-ttu-id="4fe38-198">O valor padrão é **pacote** que tem um valor enumerado de **4** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-198">The default value is **Packet** that has an enumerated value of **4** .</span></span> <span data-ttu-id="4fe38-199">Para obter mais informações sobre os valores desse parâmetro, consulte enumeração [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel) .</span><span class="sxs-lookup"><span data-stu-id="4fe38-199">For more information about the values of this parameter, see [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel) enumeration.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet (enumerated value of 4)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4fe38-200">-Atraso</span><span class="sxs-lookup"><span data-stu-id="4fe38-200">-Delay</span></span>

<span data-ttu-id="4fe38-201">Especifica o intervalo entre pings, em segundos.</span><span class="sxs-lookup"><span data-stu-id="4fe38-201">Specifies the interval between pings, in seconds.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1 (second)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4fe38-202">-Representação</span><span class="sxs-lookup"><span data-stu-id="4fe38-202">-Impersonation</span></span>

<span data-ttu-id="4fe38-203">Especifica o nível de representação a ser usado quando este cmdlet chama WMI.</span><span class="sxs-lookup"><span data-stu-id="4fe38-203">Specifies the impersonation level to use when this cmdlet calls WMI.</span></span> <span data-ttu-id="4fe38-204">`Test-Connection` usa o WMI.</span><span class="sxs-lookup"><span data-stu-id="4fe38-204">`Test-Connection` uses WMI.</span></span>

<span data-ttu-id="4fe38-205">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="4fe38-205">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="4fe38-206">**Default** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-206">**Default** .</span></span> <span data-ttu-id="4fe38-207">Representação padrão.</span><span class="sxs-lookup"><span data-stu-id="4fe38-207">Default impersonation.</span></span>
- <span data-ttu-id="4fe38-208">**Anônimo** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-208">**Anonymous** .</span></span> <span data-ttu-id="4fe38-209">Oculta a identidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="4fe38-209">Hides the identity of the caller.</span></span>
- <span data-ttu-id="4fe38-210">**Identificar** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-210">**Identify** .</span></span> <span data-ttu-id="4fe38-211">Permite que os objetos consultem as credenciais do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="4fe38-211">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="4fe38-212">**Representar** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-212">**Impersonate** .</span></span> <span data-ttu-id="4fe38-213">Permite que os objetos utilizem as credenciais do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="4fe38-213">Allows objects to use the credentials of the caller.</span></span>

<span data-ttu-id="4fe38-214">O valor padrão é **Impersonate** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-214">The default value is **Impersonate** .</span></span>

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

### <span data-ttu-id="4fe38-215">-Protocol</span><span class="sxs-lookup"><span data-stu-id="4fe38-215">-Protocol</span></span>

<span data-ttu-id="4fe38-216">Especifica um protocolo.</span><span class="sxs-lookup"><span data-stu-id="4fe38-216">Specifies a protocol.</span></span> <span data-ttu-id="4fe38-217">Os valores aceitáveis para esse parâmetro são DCOM e WSMan.</span><span class="sxs-lookup"><span data-stu-id="4fe38-217">The acceptable values for this parameter are DCOM and WSMan.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4fe38-218">-Quiet</span><span class="sxs-lookup"><span data-stu-id="4fe38-218">-Quiet</span></span>

<span data-ttu-id="4fe38-219">O parâmetro **Quiet** retorna um valor **booliano** em um objeto **System. Boolean** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-219">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object.</span></span> <span data-ttu-id="4fe38-220">O uso desse parâmetro suprime todos os erros.</span><span class="sxs-lookup"><span data-stu-id="4fe38-220">Using this parameter suppresses all errors.</span></span>

<span data-ttu-id="4fe38-221">Cada conexão testada retorna um valor **booliano** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-221">Each connection that's tested returns a **Boolean** value.</span></span> <span data-ttu-id="4fe38-222">Se o parâmetro **ComputerName** especificar vários computadores, uma matriz de valores **boolianos** será retornada.</span><span class="sxs-lookup"><span data-stu-id="4fe38-222">If the **ComputerName** parameter specifies multiple computers, an array of **Boolean** values is returned.</span></span>

<span data-ttu-id="4fe38-223">Se **qualquer** ping for executado com sucesso, `$True` será retornado.</span><span class="sxs-lookup"><span data-stu-id="4fe38-223">If **any** ping succeeds, `$True` is returned.</span></span>

<span data-ttu-id="4fe38-224">Se **todos os** pings falharem, `$False` será retornado.</span><span class="sxs-lookup"><span data-stu-id="4fe38-224">If **all** pings fail, `$False` is returned.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Quiet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4fe38-225">-Source</span><span class="sxs-lookup"><span data-stu-id="4fe38-225">-Source</span></span>

<span data-ttu-id="4fe38-226">Especifica os nomes dos computadores de onde se origina o ping.</span><span class="sxs-lookup"><span data-stu-id="4fe38-226">Specifies the names of the computers where the ping originates.</span></span> <span data-ttu-id="4fe38-227">Digite uma lista separada por vírgulas de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="4fe38-227">Enter a comma-separated list of computer names.</span></span> <span data-ttu-id="4fe38-228">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="4fe38-228">The default is the local computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: FCN, SRC

Required: True
Position: 1
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4fe38-229">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="4fe38-229">-ThrottleLimit</span></span>

<span data-ttu-id="4fe38-230">Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="4fe38-230">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="4fe38-231">Se você omite esse parâmetro ou digita um valor 0, o valor padrão, 32, é usado.</span><span class="sxs-lookup"><span data-stu-id="4fe38-231">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="4fe38-232">O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="4fe38-232">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4fe38-233">-TimeToLive</span><span class="sxs-lookup"><span data-stu-id="4fe38-233">-TimeToLive</span></span>

<span data-ttu-id="4fe38-234">Especifica o número máximo de vezes que um pacote pode ser encaminhado.</span><span class="sxs-lookup"><span data-stu-id="4fe38-234">Specifies the maximum times a packet can be forwarded.</span></span> <span data-ttu-id="4fe38-235">Para cada salto em gateways, roteadores, etc. o valor **TimeToLive** é reduzido em um.</span><span class="sxs-lookup"><span data-stu-id="4fe38-235">For every hop in gateways, routers etc. the **TimeToLive** value is decreased by one.</span></span> <span data-ttu-id="4fe38-236">Em zero, o pacote é Descartado e um erro é retornado.</span><span class="sxs-lookup"><span data-stu-id="4fe38-236">At zero the packet is discarded and an error is returned.</span></span>
<span data-ttu-id="4fe38-237">No **Windows** , o valor padrão é **128** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-237">In **Windows** , The default value is **128** .</span></span> <span data-ttu-id="4fe38-238">O alias do parâmetro **TimeToLive** é **TTL** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-238">The alias of the **TimeToLive** parameter is **TTL** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TTL

Required: False
Position: Named
Default value: 128 in Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4fe38-239">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="4fe38-239">-WsmanAuthentication</span></span>

<span data-ttu-id="4fe38-240">Especifica o mecanismo usado para autenticar as credenciais do usuário quando este cmdlet usa o protocolo WSMan.</span><span class="sxs-lookup"><span data-stu-id="4fe38-240">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span>
<span data-ttu-id="4fe38-241">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="4fe38-241">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4fe38-242">Básico</span><span class="sxs-lookup"><span data-stu-id="4fe38-242">Basic</span></span>
- <span data-ttu-id="4fe38-243">CredSSP</span><span class="sxs-lookup"><span data-stu-id="4fe38-243">CredSSP</span></span>
- <span data-ttu-id="4fe38-244">Padrão</span><span class="sxs-lookup"><span data-stu-id="4fe38-244">Default</span></span>
- <span data-ttu-id="4fe38-245">Digest</span><span class="sxs-lookup"><span data-stu-id="4fe38-245">Digest</span></span>
- <span data-ttu-id="4fe38-246">Kerberos</span><span class="sxs-lookup"><span data-stu-id="4fe38-246">Kerberos</span></span>
- <span data-ttu-id="4fe38-247">Negotiate.</span><span class="sxs-lookup"><span data-stu-id="4fe38-247">Negotiate.</span></span>

<span data-ttu-id="4fe38-248">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="4fe38-248">The default value is Default.</span></span>

<span data-ttu-id="4fe38-249">Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?view=powershellsdk-1.1.0).</span><span class="sxs-lookup"><span data-stu-id="4fe38-249">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?view=powershellsdk-1.1.0).</span></span>

<span data-ttu-id="4fe38-250">Cuidado: a autenticação CredSSP (provedor de serviços de segurança de credencial), na qual as credenciais do usuário são passadas a um computador remoto para ser autenticado, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="4fe38-250">Caution: Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
<span data-ttu-id="4fe38-251">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="4fe38-251">This mechanism increases the security risk of the remote operation.</span></span>
<span data-ttu-id="4fe38-252">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="4fe38-252">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="4fe38-253">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="4fe38-253">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4fe38-254">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4fe38-254">CommonParameters</span></span>

<span data-ttu-id="4fe38-255">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4fe38-255">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4fe38-256">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4fe38-256">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4fe38-257">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4fe38-257">INPUTS</span></span>

### <span data-ttu-id="4fe38-258">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4fe38-258">None</span></span>

<span data-ttu-id="4fe38-259">Não é possível canalizar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4fe38-259">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="4fe38-260">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4fe38-260">OUTPUTS</span></span>

### <span data-ttu-id="4fe38-261">System. Management. ManagementObject # root\cimv2\ Win32_PingStatus, System. Management. Automation. RemotingJob, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="4fe38-261">System.Management.ManagementObject#root\cimv2\Win32_PingStatus, System.Management.Automation.RemotingJob, System.Boolean</span></span>

<span data-ttu-id="4fe38-262">Esse cmdlet retorna um objeto de trabalho, se você especificar o parâmetro **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-262">This cmdlet returns a job object, if you specify the **AsJob** parameter.</span></span>

<span data-ttu-id="4fe38-263">Se você especificar o parâmetro **Quiet** , ele retornará um valor **booliano** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-263">If you specify the **Quiet** parameter, it returns a **Boolean** value.</span></span> <span data-ttu-id="4fe38-264">Se várias conexões forem testadas, uma matriz de valores **boolianos** será retornada.</span><span class="sxs-lookup"><span data-stu-id="4fe38-264">If multiple connections are tested, an array of **Boolean** values is returned.</span></span> <span data-ttu-id="4fe38-265">Caso contrário, `Test-Connection` retorna um objeto **Win32_PingStatus** para cada ping.</span><span class="sxs-lookup"><span data-stu-id="4fe38-265">Otherwise, `Test-Connection` returns a **Win32_PingStatus** object for each ping.</span></span>

## <span data-ttu-id="4fe38-266">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4fe38-266">NOTES</span></span>

<span data-ttu-id="4fe38-267">Esse cmdlet usa a classe **Win32_PingStatus** .</span><span class="sxs-lookup"><span data-stu-id="4fe38-267">This cmdlet uses the **Win32_PingStatus** class.</span></span> <span data-ttu-id="4fe38-268">Um `Get-WMIObject Win32_PingStatus` comando é equivalente a um `Test-Connection` comando.</span><span class="sxs-lookup"><span data-stu-id="4fe38-268">A `Get-WMIObject Win32_PingStatus` command is equivalent to a `Test-Connection` command.</span></span>

<span data-ttu-id="4fe38-269">O conjunto de parâmetros de **origem** foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4fe38-269">The **Source** parameter set was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="4fe38-270">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4fe38-270">RELATED LINKS</span></span>

[<span data-ttu-id="4fe38-271">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="4fe38-271">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="4fe38-272">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="4fe38-272">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="4fe38-273">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="4fe38-273">Stop-Computer</span></span>](Stop-Computer.md)
