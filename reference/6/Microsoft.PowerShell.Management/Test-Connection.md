---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: 54ba1d7db60db7b4bb64f3161bba9c1fba124219
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193365"
---
# <span data-ttu-id="42f03-103">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="42f03-103">Test-Connection</span></span>

## <span data-ttu-id="42f03-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="42f03-104">SYNOPSIS</span></span>
<span data-ttu-id="42f03-105">Envia pacotes de solicitação de eco ICMP, ou pings, para um ou mais computadores.</span><span class="sxs-lookup"><span data-stu-id="42f03-105">Sends ICMP echo request packets, or pings, to one or more computers.</span></span>

## <span data-ttu-id="42f03-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="42f03-106">SYNTAX</span></span>

### <span data-ttu-id="42f03-107">PingCount (padrão)</span><span class="sxs-lookup"><span data-stu-id="42f03-107">PingCount (Default)</span></span>

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Count <Int32>] [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="42f03-108">PingContinues</span><span class="sxs-lookup"><span data-stu-id="42f03-108">PingContinues</span></span>

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-Continues] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="42f03-109">DetectionOfMTUSize</span><span class="sxs-lookup"><span data-stu-id="42f03-109">DetectionOfMTUSize</span></span>

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -MTUSizeDetect [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="42f03-110">Rotas</span><span class="sxs-lookup"><span data-stu-id="42f03-110">TraceRoute</span></span>

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-TimeoutSeconds <Int32>] [-TargetName] <String[]> -Traceroute [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="42f03-111">ConnectionByTCPPort</span><span class="sxs-lookup"><span data-stu-id="42f03-111">ConnectionByTCPPort</span></span>

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -TCPPort <Int32> [-Quiet] [<CommonParameters>]
```

## <span data-ttu-id="42f03-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="42f03-112">DESCRIPTION</span></span>

<span data-ttu-id="42f03-113">O `Test-Connection` cmdlet envia pacotes de solicitação de eco do protocolo ICMP, ou pings, para um ou mais computadores remotos e retorna as respostas de resposta de eco.</span><span class="sxs-lookup"><span data-stu-id="42f03-113">The `Test-Connection` cmdlet sends Internet Control Message Protocol (ICMP) echo request packets, or pings, to one or more remote computers and returns the echo response replies.</span></span> <span data-ttu-id="42f03-114">Você pode usar este cmdlet para determinar se um computador específico pode ser contatado em uma rede IP.</span><span class="sxs-lookup"><span data-stu-id="42f03-114">You can use this cmdlet to determine whether a particular computer can be contacted across an IP network.</span></span>

<span data-ttu-id="42f03-115">Você pode usar os parâmetros de `Test-Connection` para especificar os computadores de envio e de recebimento, para executar o comando como um trabalho em segundo plano, definir um tempo limite e um número de pings e configurar a conexão e a autenticação.</span><span class="sxs-lookup"><span data-stu-id="42f03-115">You can use the parameters of `Test-Connection` to specify both the sending and receiving computers, to run the command as a background job, to set a time-out and number of pings, and to configure the connection and authentication.</span></span>

<span data-ttu-id="42f03-116">Diferentemente do comando **ping** conhecido, `Test-Connection` retorna um objeto **TestConnectionCommand + PingReport** que você pode investigar no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42f03-116">Unlike the familiar **ping** command, `Test-Connection` returns a **TestConnectionCommand+PingReport** object that you can investigate in PowerShell.</span></span> <span data-ttu-id="42f03-117">O parâmetro **Quiet** retorna um valor **booliano** em um objeto **System. Boolean** para cada conexão testada.</span><span class="sxs-lookup"><span data-stu-id="42f03-117">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object for each tested connection.</span></span> <span data-ttu-id="42f03-118">Se várias conexões forem testadas, uma matriz de valores **boolianos** será retornada.</span><span class="sxs-lookup"><span data-stu-id="42f03-118">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="42f03-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="42f03-119">EXAMPLES</span></span>

### <span data-ttu-id="42f03-120">Exemplo 1: enviar solicitações de eco para um computador remoto</span><span class="sxs-lookup"><span data-stu-id="42f03-120">Example 1: Send echo requests to a remote computer</span></span>

<span data-ttu-id="42f03-121">Este exemplo envia pacotes de solicitação de eco do computador local para o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="42f03-121">This example sends echo request packets from the local computer to the Server01 computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -IPv4
```

```Output
Pinging Server01 [10.59.137.44] with 32 bytes of data:
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Ping complete.

Source     Destination Replies
------     ----------- -------
Server01   Server01    {System.Net.NetworkInformation.PingReply, System.Net.NetworkInformation ...
```

<span data-ttu-id="42f03-122">`Test-Connection` usa o parâmetro **TargetName** para especificar o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="42f03-122">`Test-Connection` uses the **TargetName** parameter to specify the Server01 computer.</span></span> <span data-ttu-id="42f03-123">O parâmetro **IPv4** especifica o protocolo para o teste.</span><span class="sxs-lookup"><span data-stu-id="42f03-123">The **IPv4** parameter specifies the protocol for the test.</span></span>

<span data-ttu-id="42f03-124">A saída de ping é enviada ao fluxo de **informações** enquanto o objeto **TestConnectionCommand + PingReport** enviado para o fluxo de **êxito** .</span><span class="sxs-lookup"><span data-stu-id="42f03-124">The ping output is sent to the **Information** stream while the **TestConnectionCommand+PingReport** object sent to the **Success** stream.</span></span> <span data-ttu-id="42f03-125">Para obter mais informações sobre os fluxos de saída, consulte [about_Redirection](../microsoft.powershell.core/about/about_redirection.md).</span><span class="sxs-lookup"><span data-stu-id="42f03-125">For more information about the output streams, see [about_Redirection](../microsoft.powershell.core/about/about_redirection.md).</span></span>

### <span data-ttu-id="42f03-126">Exemplo 2: enviar solicitações de eco para vários computadores</span><span class="sxs-lookup"><span data-stu-id="42f03-126">Example 2: Send echo requests to several computers</span></span>

<span data-ttu-id="42f03-127">Este exemplo envia pings do computador local para vários computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="42f03-127">This example sends pings from the local computer to several remote computers.</span></span>

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### <span data-ttu-id="42f03-128">Exemplo 3: enviar solicitações de eco de vários computadores a um computador</span><span class="sxs-lookup"><span data-stu-id="42f03-128">Example 3: Send echo requests from several computers to a computer</span></span>

<span data-ttu-id="42f03-129">Este exemplo envia pings de computadores de origem diferentes para um único computador remoto, Server01.</span><span class="sxs-lookup"><span data-stu-id="42f03-129">This example sends pings from different source computers to a single remote computer, Server01.</span></span>

```powershell
Test-Connection -Source Server02, Server12, localhost -TargetName Server01
```

<span data-ttu-id="42f03-130">Use esse formato de comando para testar a latência de conexões de vários pontos.</span><span class="sxs-lookup"><span data-stu-id="42f03-130">Use this command format to test the latency of connections from multiple points.</span></span>

### <span data-ttu-id="42f03-131">Exemplo 4: usar parâmetros para personalizar o comando de teste</span><span class="sxs-lookup"><span data-stu-id="42f03-131">Example 4: Use parameters to customize the test command</span></span>

<span data-ttu-id="42f03-132">Este exemplo usa os parâmetros de `Test-Connection` para personalizar o comando.</span><span class="sxs-lookup"><span data-stu-id="42f03-132">This example uses the parameters of `Test-Connection` to customize the command.</span></span> <span data-ttu-id="42f03-133">O computador local envia um teste de ping para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="42f03-133">The local computer sends a ping test to a remote computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

<span data-ttu-id="42f03-134">`Test-Connection` usa o parâmetro **TargetName** para especificar Server01.</span><span class="sxs-lookup"><span data-stu-id="42f03-134">`Test-Connection` uses the **TargetName** parameter to specify Server01.</span></span> <span data-ttu-id="42f03-135">O parâmetro **Count** especifica que três pings são enviados para o computador Server01 com um **atraso** de intervalos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="42f03-135">The **Count** parameter specifies three pings are sent to the Server01 computer with a **Delay** of 2-second intervals.</span></span>

<span data-ttu-id="42f03-136">Você pode usar essas opções quando espera-se que a resposta de ping demore mais do que o normal, devido a um número estendido de saltos ou a uma condição de rede de tráfego alto.</span><span class="sxs-lookup"><span data-stu-id="42f03-136">You might use these options when the ping response is expected to take longer than usual, either because of an extended number of hops or a high-traffic network condition.</span></span>

### <span data-ttu-id="42f03-137">Exemplo 5: executar um teste como um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="42f03-137">Example 5: Run a test as a background job</span></span>

<span data-ttu-id="42f03-138">Este exemplo mostra como executar um `Test-Connection` comando como um trabalho em segundo plano do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42f03-138">This example shows how to run a `Test-Connection` command as a PowerShell background job.</span></span>

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content "Servers.txt") }
if ($job.JobStateInfo.State -ne "Running") { $Results = Receive-Job $job }
```

<span data-ttu-id="42f03-139">O `Start-Job` comando usa o `Test-Connection` cmdlet para executar ping em vários computadores em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="42f03-139">The `Start-Job` command uses the `Test-Connection` cmdlet to ping many computers in an enterprise.</span></span>
<span data-ttu-id="42f03-140">O valor do parâmetro **TargetName** é um `Get-Content` comando que lê uma lista de nomes de computador a partir do `Servers.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="42f03-140">The value of the **TargetName** parameter is a `Get-Content` command that reads a list of computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="42f03-141">O comando usa o `Start-Job` cmdlet para executar o comando como um trabalho em segundo plano e salva o trabalho na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="42f03-141">The command uses the `Start-Job` cmdlet to run the command as a background job and it saves the job in the `$job` variable.</span></span>

<span data-ttu-id="42f03-142">O `if` comando verifica para ver se o trabalho ainda não está em execução.</span><span class="sxs-lookup"><span data-stu-id="42f03-142">The `if` command checks to see that the job isn't still running.</span></span> <span data-ttu-id="42f03-143">Se o trabalho não estiver em execução, `Receive-Job` o obterá os resultados e os armazenará na `$Results` variável.</span><span class="sxs-lookup"><span data-stu-id="42f03-143">If the job isn't running, `Receive-Job` gets the results and stores them in the `$Results` variable.</span></span>

### <span data-ttu-id="42f03-144">Exemplo 6: criar uma sessão somente se um teste de conexão tiver sucesso</span><span class="sxs-lookup"><span data-stu-id="42f03-144">Example 6: Create a session only if a connection test succeeds</span></span>

<span data-ttu-id="42f03-145">Este exemplo criará uma sessão no computador Server01 somente se pelo menos um dos pings enviados para o computador for executado com sucesso.</span><span class="sxs-lookup"><span data-stu-id="42f03-145">This example creates a session on the Server01 computer only if at least one of the pings sent to the computer succeeds.</span></span>

```powershell
if (Test-Connection -TargetName Server01 -Quiet) {New-PSSession Server01}
```

<span data-ttu-id="42f03-146">O `if` comando usa o `Test-Connection` cmdlet para executar ping no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="42f03-146">The `if` command uses the `Test-Connection` cmdlet to ping the Server01 computer.</span></span> <span data-ttu-id="42f03-147">O comando usa o parâmetro **Quiet** , que retorna um valor **booliano** , em vez de um objeto **TestConnectionCommand + PingReport** .</span><span class="sxs-lookup"><span data-stu-id="42f03-147">The command uses the **Quiet** parameter, which returns a **Boolean** value, instead of a **TestConnectionCommand+PingReport** object.</span></span>

<span data-ttu-id="42f03-148">O valor será `$True` se qualquer um dos quatro pings for bem-sucedidos.</span><span class="sxs-lookup"><span data-stu-id="42f03-148">The value is `$True` if any of the four pings succeed.</span></span> <span data-ttu-id="42f03-149">Se nenhum dos pings for bem-sucedidos, o valor será `$False` .</span><span class="sxs-lookup"><span data-stu-id="42f03-149">If none of the pings succeed, the value is `$False`.</span></span>

<span data-ttu-id="42f03-150">Se o `Test-Connection` comando retornar um valor de `$True` , o comando usará o `New-PSSession` cmdlet para criar a **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="42f03-150">If the `Test-Connection` command returns a value of `$True`, the command uses the `New-PSSession` cmdlet to create the **PSSession** .</span></span>

### <span data-ttu-id="42f03-151">Exemplo 7: usar o parâmetro traceroute</span><span class="sxs-lookup"><span data-stu-id="42f03-151">Example 7: Use the Traceroute parameter</span></span>

<span data-ttu-id="42f03-152">A partir do PowerShell 6,0, o parâmetro **traceroute** mapeia uma rota entre o computador local e o destino remoto que você especifica com o parâmetro **TargetName** .</span><span class="sxs-lookup"><span data-stu-id="42f03-152">Beginning in PowerShell 6.0, the **Traceroute** parameter maps a route between the local computer and the remote destination you specify with the **TargetName** parameter.</span></span>

```powershell
Test-Connection -TargetName www.microsoft.com -Traceroute | ForEach-Object {
  $_ | Format-Table Source, DestinationAddress, DestinationHost
  $_.Replies | ForEach-Object {
      $_ | Format-Table Hop, ReplyRouterAddress
      $_.PingReplies | Format-Table
  }
}
```

```Output
Tracing route to www.microsoft.com [96.6.27.90] over a maximum of 128 hops:
  1   0 ms   0 ms   0 ms   192.168.0.3 [192.168.0.3]
  2   0 ms   0 ms   0 ms   192.168.1.1 [192.168.1.1]
  3   3 ms   29 ms   4 ms   96.6.27.90 [96.6.27.90]
Trace complete.

Source      DestinationAddress DestinationHost   Replies
------      ------------------ ---------------   -------
SERVER01    96.6.27.90         www.microsoft.com {, , }

Hop ReplyRouterAddress
--- ------------------
  1 192.168.0.3

    Status Address      RoundtripTime Options Buffer
    ------ -------      ------------- ------- ------
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  2 192.168.1.1

    Status Address     RoundtripTime Options Buffer
    ------ -------     ------------- ------- ------
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  3 96.6.27.90

 Status Address    RoundtripTime Options                                   Buffer
 ------ -------    ------------- -------                                   ------
Success 96.6.27.90             3 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             2 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             4 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
```

<span data-ttu-id="42f03-153">O `Test-Connection` comando usa o parâmetro **traceroute** .</span><span class="sxs-lookup"><span data-stu-id="42f03-153">The `Test-Connection` command uses the **Traceroute** parameter.</span></span> <span data-ttu-id="42f03-154">Os resultados, que são `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteResult]` objetos, são canalizados para o `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="42f03-154">The results, which are `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteResult]` objects, are piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="42f03-155">`ForEach-Object` Cria uma saída estruturada dos `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteReply]` objetos contidos e dos `[System.Net.NetworkInformation.PingReply]` objetos subsequentes.</span><span class="sxs-lookup"><span data-stu-id="42f03-155">`ForEach-Object` creates a structured output of the contained `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteReply]` objects and subsequent `[System.Net.NetworkInformation.PingReply]` objects.</span></span>

## <span data-ttu-id="42f03-156">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="42f03-156">PARAMETERS</span></span>

### <span data-ttu-id="42f03-157">-BufferSize</span><span class="sxs-lookup"><span data-stu-id="42f03-157">-BufferSize</span></span>

<span data-ttu-id="42f03-158">Especifica o tamanho, em bytes, do buffer enviado com esse comando.</span><span class="sxs-lookup"><span data-stu-id="42f03-158">Specifies the size, in bytes, of the buffer sent with this command.</span></span> <span data-ttu-id="42f03-159">O valor padrão é 32.</span><span class="sxs-lookup"><span data-stu-id="42f03-159">The default value is 32.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42f03-160">-Contagem</span><span class="sxs-lookup"><span data-stu-id="42f03-160">-Count</span></span>

<span data-ttu-id="42f03-161">Especifica o número de solicitações de eco a enviar.</span><span class="sxs-lookup"><span data-stu-id="42f03-161">Specifies the number of echo requests to send.</span></span> <span data-ttu-id="42f03-162">O valor padrão é 4.</span><span class="sxs-lookup"><span data-stu-id="42f03-162">The default value is 4.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42f03-163">-Atraso</span><span class="sxs-lookup"><span data-stu-id="42f03-163">-Delay</span></span>

<span data-ttu-id="42f03-164">Especifica o intervalo entre pings, em segundos.</span><span class="sxs-lookup"><span data-stu-id="42f03-164">Specifies the interval between pings, in seconds.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42f03-165">-DontFragment</span><span class="sxs-lookup"><span data-stu-id="42f03-165">-DontFragment</span></span>

<span data-ttu-id="42f03-166">Esse parâmetro define o sinalizador **não fragmentar** no cabeçalho IP.</span><span class="sxs-lookup"><span data-stu-id="42f03-166">This parameter sets the **Don't Fragment** flag in the IP header.</span></span> <span data-ttu-id="42f03-167">Você pode usar esse parâmetro com o parâmetro **BufferSize** para testar o tamanho do MTU do caminho.</span><span class="sxs-lookup"><span data-stu-id="42f03-167">You can use this parameter with the **BufferSize** parameter to test the Path MTU size.</span></span> <span data-ttu-id="42f03-168">Para obter mais informações sobre Path MTU, consulte o artigo [descoberta de MTU de caminho](https://wikipedia.org/wiki/Path_MTU_Discovery) na Wikipédia.</span><span class="sxs-lookup"><span data-stu-id="42f03-168">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42f03-169">-IPv4</span><span class="sxs-lookup"><span data-stu-id="42f03-169">-IPv4</span></span>

<span data-ttu-id="42f03-170">Força o cmdlet a usar o protocolo IPv4 para o teste.</span><span class="sxs-lookup"><span data-stu-id="42f03-170">Forces the cmdlet to use the IPv4 protocol for the test.</span></span>

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

### <span data-ttu-id="42f03-171">-IPv6</span><span class="sxs-lookup"><span data-stu-id="42f03-171">-IPv6</span></span>

<span data-ttu-id="42f03-172">Força o cmdlet a usar o protocolo IPv6 para o teste.</span><span class="sxs-lookup"><span data-stu-id="42f03-172">Forces the cmdlet to use the IPv6 protocol for the test.</span></span>

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

### <span data-ttu-id="42f03-173">-MaxHops</span><span class="sxs-lookup"><span data-stu-id="42f03-173">-MaxHops</span></span>

<span data-ttu-id="42f03-174">Define o número máximo de saltos que uma mensagem de solicitação ICMP pode ser enviada.</span><span class="sxs-lookup"><span data-stu-id="42f03-174">Sets the maximum number of hops that an ICMP request message can be sent.</span></span> <span data-ttu-id="42f03-175">O valor padrão é controlado pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="42f03-175">The default value is controlled by the operating system.</span></span> <span data-ttu-id="42f03-176">O valor padrão para o Windows 10 é de 128 saltos.</span><span class="sxs-lookup"><span data-stu-id="42f03-176">The default value for Windows 10 is 128 hops.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues, TraceRoute
Aliases: Ttl, TimeToLive, Hops

Required: False
Position: Named
Default value: 128 hops in Windows 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42f03-177">-Ping</span><span class="sxs-lookup"><span data-stu-id="42f03-177">-Ping</span></span>

<span data-ttu-id="42f03-178">Faz com que o cmdlet faça um teste de ping, que é a ação padrão.</span><span class="sxs-lookup"><span data-stu-id="42f03-178">Causes the cmdlet to do a ping test, which is the default action.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: Ping test
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42f03-179">-Quiet</span><span class="sxs-lookup"><span data-stu-id="42f03-179">-Quiet</span></span>

<span data-ttu-id="42f03-180">O parâmetro **Quiet** retorna um valor **booliano** em um objeto **System. Boolean** .</span><span class="sxs-lookup"><span data-stu-id="42f03-180">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object.</span></span> <span data-ttu-id="42f03-181">O uso desse parâmetro suprime todos os erros.</span><span class="sxs-lookup"><span data-stu-id="42f03-181">Using this parameter suppresses all errors.</span></span>

<span data-ttu-id="42f03-182">Cada conexão testada retorna um valor **booliano** .</span><span class="sxs-lookup"><span data-stu-id="42f03-182">Each connection that's tested returns a **Boolean** value.</span></span> <span data-ttu-id="42f03-183">Se o parâmetro **TargetName** especificar vários computadores, uma matriz de valores **boolianos** será retornada.</span><span class="sxs-lookup"><span data-stu-id="42f03-183">If the **TargetName** parameter specifies multiple computers, an array of **Boolean** values is returned.</span></span>

<span data-ttu-id="42f03-184">Se **qualquer** ping for executado com sucesso, `$True` será retornado.</span><span class="sxs-lookup"><span data-stu-id="42f03-184">If **any** ping succeeds, `$True` is returned.</span></span>

<span data-ttu-id="42f03-185">Se **todos os** pings falharem, `$False` será retornado.</span><span class="sxs-lookup"><span data-stu-id="42f03-185">If **all** pings fail, `$False` is returned.</span></span>

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

### <span data-ttu-id="42f03-186">-ResolveDestination</span><span class="sxs-lookup"><span data-stu-id="42f03-186">-ResolveDestination</span></span>

<span data-ttu-id="42f03-187">Faz com que o cmdlet tente resolver o nome DNS do destino.</span><span class="sxs-lookup"><span data-stu-id="42f03-187">Causes the cmdlet to attempt to resolve the DNS name of the target.</span></span>

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

### <span data-ttu-id="42f03-188">-Source</span><span class="sxs-lookup"><span data-stu-id="42f03-188">-Source</span></span>

<span data-ttu-id="42f03-189">Especifica os nomes dos computadores de onde se origina o ping.</span><span class="sxs-lookup"><span data-stu-id="42f03-189">Specifies the names of the computers where the ping originates.</span></span> <span data-ttu-id="42f03-190">Digite uma lista separada por vírgulas de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="42f03-190">Enter a comma-separated list of computer names.</span></span> <span data-ttu-id="42f03-191">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="42f03-191">The default is the local computer.</span></span>

```yaml
Type: System.String
Parameter Sets: PingCount, PingContinues, TraceRoute, ConnectionByTCPPort
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42f03-192">-TargetName</span><span class="sxs-lookup"><span data-stu-id="42f03-192">-TargetName</span></span>

<span data-ttu-id="42f03-193">Especifica os computadores a serem testados.</span><span class="sxs-lookup"><span data-stu-id="42f03-193">Specifies the computers to test.</span></span> <span data-ttu-id="42f03-194">Digite os nomes de computador ou endereços IP no formato IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="42f03-194">Type the computer names or type IP addresses in IPv4 or IPv6 format.</span></span> <span data-ttu-id="42f03-195">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="42f03-195">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="42f03-196">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="42f03-196">This parameter is required.</span></span> <span data-ttu-id="42f03-197">**ComputerName** é um alias para este parâmetro.</span><span class="sxs-lookup"><span data-stu-id="42f03-197">**ComputerName** is an alias for this parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ComputerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="42f03-198">-TCPPort</span><span class="sxs-lookup"><span data-stu-id="42f03-198">-TCPPort</span></span>

<span data-ttu-id="42f03-199">Especifica o número da porta TCP no destino a ser usado no teste de conexão TCP.</span><span class="sxs-lookup"><span data-stu-id="42f03-199">Specifies the TCP port number on the target to be used in the TCP connection test.</span></span> <span data-ttu-id="42f03-200">O cmdlet tentará fazer uma conexão TCP com a porta especificada no destino.</span><span class="sxs-lookup"><span data-stu-id="42f03-200">The cmdlet will attempt to make a TCP connection to the specified port on the target.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ConnectionByTCPPort
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42f03-201">-TimeoutSeconds</span><span class="sxs-lookup"><span data-stu-id="42f03-201">-TimeoutSeconds</span></span>

<span data-ttu-id="42f03-202">Define o valor de tempo limite para o teste.</span><span class="sxs-lookup"><span data-stu-id="42f03-202">Sets the timeout value for the test.</span></span> <span data-ttu-id="42f03-203">O teste falhará se uma resposta não for recebida antes do tempo limite expirar.</span><span class="sxs-lookup"><span data-stu-id="42f03-203">The test fails if a response isn't received before the timeout expires.</span></span> <span data-ttu-id="42f03-204">O padrão é cinco segundos.</span><span class="sxs-lookup"><span data-stu-id="42f03-204">The default is five seconds.</span></span>

<span data-ttu-id="42f03-205">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="42f03-205">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5 seconds
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42f03-206">-Traceroute</span><span class="sxs-lookup"><span data-stu-id="42f03-206">-Traceroute</span></span>

<span data-ttu-id="42f03-207">Faz com que o cmdlet faça um teste de traceroute.</span><span class="sxs-lookup"><span data-stu-id="42f03-207">Causes the cmdlet to do a traceroute test.</span></span> <span data-ttu-id="42f03-208">Quando esse parâmetro é usado, o cmdlet retorna um `TestConnectionCommand+TraceRouteResult` objeto.</span><span class="sxs-lookup"><span data-stu-id="42f03-208">When this parameter is used, the cmdlet returns a `TestConnectionCommand+TraceRouteResult` object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TraceRoute
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42f03-209">-Continua</span><span class="sxs-lookup"><span data-stu-id="42f03-209">-Continues</span></span>

<span data-ttu-id="42f03-210">Faz com que o cmdlet envie solicitações de ping continuamente.</span><span class="sxs-lookup"><span data-stu-id="42f03-210">Causes the cmdlet to send ping requests continuously.</span></span> <span data-ttu-id="42f03-211">Esse parâmetro não pode ser usado com o parâmetro **Count** .</span><span class="sxs-lookup"><span data-stu-id="42f03-211">This parameter can't be used with the **Count** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42f03-212">-MTUSizeDetect</span><span class="sxs-lookup"><span data-stu-id="42f03-212">-MTUSizeDetect</span></span>

<span data-ttu-id="42f03-213">Esse parâmetro é usado para descobrir o tamanho de MTU do caminho.</span><span class="sxs-lookup"><span data-stu-id="42f03-213">This parameter is used to discover the Path MTU size.</span></span> <span data-ttu-id="42f03-214">O cmdlet retorna um objeto **PingReply # MTUSize** que contém o tamanho de MTU do caminho para o destino.</span><span class="sxs-lookup"><span data-stu-id="42f03-214">The cmdlet returns a **PingReply#MTUSize** object that contains the Path MTU size to the target.</span></span> <span data-ttu-id="42f03-215">Para obter mais informações sobre Path MTU, consulte o artigo [descoberta de MTU de caminho](https://wikipedia.org/wiki/Path_MTU_Discovery) na Wikipédia.</span><span class="sxs-lookup"><span data-stu-id="42f03-215">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DetectionOfMTUSize
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42f03-216">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="42f03-216">CommonParameters</span></span>

<span data-ttu-id="42f03-217">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="42f03-217">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="42f03-218">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="42f03-218">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="42f03-219">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="42f03-219">INPUTS</span></span>

### <span data-ttu-id="42f03-220">Nenhum</span><span class="sxs-lookup"><span data-stu-id="42f03-220">None</span></span>

<span data-ttu-id="42f03-221">Não é possível canalizar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="42f03-221">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="42f03-222">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="42f03-222">OUTPUTS</span></span>

### <span data-ttu-id="42f03-223">TestConnectionCommand + PingReport, TestConnectionCommand + TraceRouteResult, Boolean, PingReply # MTUSize</span><span class="sxs-lookup"><span data-stu-id="42f03-223">TestConnectionCommand+PingReport, TestConnectionCommand+TraceRouteResult, Boolean, PingReply#MTUSize</span></span>

<span data-ttu-id="42f03-224">Se você especificar o parâmetro **Quiet** , ele retornará um valor **booliano** .</span><span class="sxs-lookup"><span data-stu-id="42f03-224">If you specify the **Quiet** parameter, it returns a **Boolean** value.</span></span> <span data-ttu-id="42f03-225">Se várias conexões forem testadas, uma matriz de valores **boolianos** será retornada.</span><span class="sxs-lookup"><span data-stu-id="42f03-225">If multiple connections are tested, an array of **Boolean** values is returned.</span></span> <span data-ttu-id="42f03-226">Caso contrário, `Test-Connection` retorna um objeto **TestConnectionCommand + PingReport** para cada ping.</span><span class="sxs-lookup"><span data-stu-id="42f03-226">Otherwise, `Test-Connection` returns a **TestConnectionCommand+PingReport** object for each ping.</span></span>

## <span data-ttu-id="42f03-227">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="42f03-227">NOTES</span></span>

## <span data-ttu-id="42f03-228">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="42f03-228">RELATED LINKS</span></span>

[<span data-ttu-id="42f03-229">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="42f03-229">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="42f03-230">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="42f03-230">Stop-Computer</span></span>](Stop-Computer.md)
