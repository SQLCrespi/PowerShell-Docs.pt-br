---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: 6a03d5a644e3d4be515a93a702d0ef0aff23a8d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193363"
---
# <span data-ttu-id="eb176-103">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="eb176-103">Test-Connection</span></span>

## <span data-ttu-id="eb176-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="eb176-104">SYNOPSIS</span></span>
<span data-ttu-id="eb176-105">Envia pacotes de solicitação de eco ICMP, ou pings, para um ou mais computadores.</span><span class="sxs-lookup"><span data-stu-id="eb176-105">Sends ICMP echo request packets, or pings, to one or more computers.</span></span>

## <span data-ttu-id="eb176-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="eb176-106">SYNTAX</span></span>

### <span data-ttu-id="eb176-107">Defaultping (padrão)</span><span class="sxs-lookup"><span data-stu-id="eb176-107">DefaultPing (Default)</span></span>

```
Test-Connection [-TargetName] <string[]> [-Ping] [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-Count <int>] [-Delay <int>] [-BufferSize <int>]
 [-DontFragment] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="eb176-108">RepeatPing</span><span class="sxs-lookup"><span data-stu-id="eb176-108">RepeatPing</span></span>

```
Test-Connection [-TargetName] <string[]> -Repeat [-Ping] [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-Delay <int>] [-BufferSize <int>] [-DontFragment]
 [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="eb176-109">MtuSizeDetect</span><span class="sxs-lookup"><span data-stu-id="eb176-109">MtuSizeDetect</span></span>

```
Test-Connection [-TargetName] <string[]> -MtuSize [-IPv4] [-IPv6] [-ResolveDestination]
 [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="eb176-110">Rotas</span><span class="sxs-lookup"><span data-stu-id="eb176-110">TraceRoute</span></span>

```
Test-Connection [-TargetName] <string[]> -Traceroute [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="eb176-111">TcpPort</span><span class="sxs-lookup"><span data-stu-id="eb176-111">TcpPort</span></span>

```
Test-Connection [-TargetName] <string[]> -TcpPort <int> [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

## <span data-ttu-id="eb176-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="eb176-112">DESCRIPTION</span></span>

<span data-ttu-id="eb176-113">O `Test-Connection` cmdlet envia pacotes de solicitação de eco do protocolo ICMP, ou pings, para um ou mais computadores remotos e retorna as respostas de resposta de eco.</span><span class="sxs-lookup"><span data-stu-id="eb176-113">The `Test-Connection` cmdlet sends Internet Control Message Protocol (ICMP) echo request packets, or pings, to one or more remote computers and returns the echo response replies.</span></span> <span data-ttu-id="eb176-114">Você pode usar este cmdlet para determinar se um computador específico pode ser contatado em uma rede IP.</span><span class="sxs-lookup"><span data-stu-id="eb176-114">You can use this cmdlet to determine whether a particular computer can be contacted across an IP network.</span></span>

<span data-ttu-id="eb176-115">Você pode usar os parâmetros de `Test-Connection` para especificar os computadores de envio e de recebimento, para executar o comando como um trabalho em segundo plano, definir um tempo limite e um número de pings e configurar a conexão e a autenticação.</span><span class="sxs-lookup"><span data-stu-id="eb176-115">You can use the parameters of `Test-Connection` to specify both the sending and receiving computers, to run the command as a background job, to set a time-out and number of pings, and to configure the connection and authentication.</span></span>

<span data-ttu-id="eb176-116">Diferentemente do comando **ping** conhecido, `Test-Connection` retorna um objeto **TestConnectionCommand + PingStatus** que você pode investigar no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb176-116">Unlike the familiar **ping** command, `Test-Connection` returns a **TestConnectionCommand+PingStatus** object that you can investigate in PowerShell.</span></span> <span data-ttu-id="eb176-117">O parâmetro **Quiet** retorna um valor **booliano** em um objeto **System. Boolean** para cada conexão testada.</span><span class="sxs-lookup"><span data-stu-id="eb176-117">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object for each tested connection.</span></span> <span data-ttu-id="eb176-118">Se várias conexões forem testadas, uma matriz de valores **boolianos** será retornada.</span><span class="sxs-lookup"><span data-stu-id="eb176-118">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="eb176-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="eb176-119">EXAMPLES</span></span>

### <span data-ttu-id="eb176-120">Exemplo 1: enviar solicitações de eco para um computador remoto</span><span class="sxs-lookup"><span data-stu-id="eb176-120">Example 1: Send echo requests to a remote computer</span></span>

<span data-ttu-id="eb176-121">Este exemplo envia pacotes de solicitação de eco do computador local para o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="eb176-121">This example sends echo request packets from the local computer to the Server01 computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -IPv4
```

```Output
   Destination: Server01

Ping Source           Address                   Latency BufferSize Status
                                                   (ms)        (B)
---- ------           -------                   ------- ---------- ------
   1 ADMIN1           10.59.137.44                   24         32 Success
   2 ADMIN1           10.59.137.44                   39         32 Success
   3 ADMIN1           *                               *          * TimedOut
   4 ADMIN1           10.59.137.44                   28         32 Success
```

<span data-ttu-id="eb176-122">`Test-Connection` usa o parâmetro **TargetName** para especificar o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="eb176-122">`Test-Connection` uses the **TargetName** parameter to specify the Server01 computer.</span></span> <span data-ttu-id="eb176-123">O parâmetro **IPv4** especifica o protocolo para o teste.</span><span class="sxs-lookup"><span data-stu-id="eb176-123">The **IPv4** parameter specifies the protocol for the test.</span></span>

<span data-ttu-id="eb176-124">Uma série de objetos **TestConnectionCommand + PingStatus** é enviada para o fluxo de saída, um objeto por resposta de ping do computador de destino.</span><span class="sxs-lookup"><span data-stu-id="eb176-124">A series of **TestConnectionCommand+PingStatus** objects are sent to the output stream, one object per ping reply from the target machine.</span></span>

### <span data-ttu-id="eb176-125">Exemplo 2: enviar solicitações de eco para vários computadores</span><span class="sxs-lookup"><span data-stu-id="eb176-125">Example 2: Send echo requests to several computers</span></span>

<span data-ttu-id="eb176-126">Este exemplo envia pings do computador local para vários computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="eb176-126">This example sends pings from the local computer to several remote computers.</span></span>

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### <span data-ttu-id="eb176-127">Exemplo 3: usar parâmetros para personalizar o comando de teste</span><span class="sxs-lookup"><span data-stu-id="eb176-127">Example 3: Use parameters to customize the test command</span></span>

<span data-ttu-id="eb176-128">Este exemplo usa os parâmetros de `Test-Connection` para personalizar o comando.</span><span class="sxs-lookup"><span data-stu-id="eb176-128">This example uses the parameters of `Test-Connection` to customize the command.</span></span> <span data-ttu-id="eb176-129">O computador local envia um teste de ping para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="eb176-129">The local computer sends a ping test to a remote computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

<span data-ttu-id="eb176-130">`Test-Connection` usa o parâmetro **TargetName** para especificar Server01.</span><span class="sxs-lookup"><span data-stu-id="eb176-130">`Test-Connection` uses the **TargetName** parameter to specify Server01.</span></span> <span data-ttu-id="eb176-131">O parâmetro **Count** especifica que três pings são enviados para o computador Server01 com um **atraso** de intervalos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="eb176-131">The **Count** parameter specifies three pings are sent to the Server01 computer with a **Delay** of 2-second intervals.</span></span>

<span data-ttu-id="eb176-132">Você pode usar essas opções quando espera-se que a resposta de ping demore mais do que o normal, devido a um número estendido de saltos ou a uma condição de rede de tráfego alto.</span><span class="sxs-lookup"><span data-stu-id="eb176-132">You might use these options when the ping response is expected to take longer than usual, either because of an extended number of hops or a high-traffic network condition.</span></span>

### <span data-ttu-id="eb176-133">Exemplo 4: executar um teste como um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="eb176-133">Example 4: Run a test as a background job</span></span>

<span data-ttu-id="eb176-134">Este exemplo mostra como executar um `Test-Connection` comando como um trabalho em segundo plano do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb176-134">This example shows how to run a `Test-Connection` command as a PowerShell background job.</span></span>

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content -Path "Servers.txt") }
$Results = Receive-Job $job -Wait
```

<span data-ttu-id="eb176-135">O `Start-Job` comando usa o `Test-Connection` cmdlet para executar ping em vários computadores em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="eb176-135">The `Start-Job` command uses the `Test-Connection` cmdlet to ping many computers in an enterprise.</span></span>
<span data-ttu-id="eb176-136">O valor do parâmetro **TargetName** é um `Get-Content` comando que lê uma lista de nomes de computador a partir do `Servers.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="eb176-136">The value of the **TargetName** parameter is a `Get-Content` command that reads a list of computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="eb176-137">O comando usa o `Start-Job` cmdlet para executar o comando como um trabalho em segundo plano e salva o trabalho na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="eb176-137">The command uses the `Start-Job` cmdlet to run the command as a background job and it saves the job in the `$job` variable.</span></span>

<span data-ttu-id="eb176-138">O `Receive-Job` comando é instruído `-Wait` até até que o trabalho seja concluído e, em seguida, obtém os resultados e os armazena na `$Results` variável.</span><span class="sxs-lookup"><span data-stu-id="eb176-138">The `Receive-Job` command is instructed to `-Wait` until the job is completed, and then gets the results and stores them in the `$Results` variable.</span></span>

### <span data-ttu-id="eb176-139">Exemplo 5: criar uma sessão somente se um teste de conexão tiver sucesso</span><span class="sxs-lookup"><span data-stu-id="eb176-139">Example 5: Create a session only if a connection test succeeds</span></span>

<span data-ttu-id="eb176-140">Este exemplo criará uma sessão no computador Server01 somente se pelo menos um dos pings enviados para o computador for executado com sucesso.</span><span class="sxs-lookup"><span data-stu-id="eb176-140">This example creates a session on the Server01 computer only if at least one of the pings sent to the computer succeeds.</span></span>

```powershell
if (Test-Connection -TargetName Server01 -Quiet) { New-PSSession -ComputerName Server01 }
```

<span data-ttu-id="eb176-141">O `Test-Connection` cmdlet executa ping no `Server01` computador, com o parâmetro **Quiet** fornecido.</span><span class="sxs-lookup"><span data-stu-id="eb176-141">The `Test-Connection` cmdlet pings the `Server01` computer, with the **Quiet** parameter provided.</span></span>
<span data-ttu-id="eb176-142">O valor resultante será `$True` se qualquer um dos quatro pings for bem-sucedidos.</span><span class="sxs-lookup"><span data-stu-id="eb176-142">The resulting value is `$True` if any of the four pings succeed.</span></span> <span data-ttu-id="eb176-143">Se nenhum dos pings for bem-sucedidos, o valor será `$False` .</span><span class="sxs-lookup"><span data-stu-id="eb176-143">If none of the pings succeed, the value is `$False`.</span></span>

<span data-ttu-id="eb176-144">Se o `Test-Connection` comando retornar um valor de `$True` , o comando usará o `New-PSSession` cmdlet para criar a **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="eb176-144">If the `Test-Connection` command returns a value of `$True`, the command uses the `New-PSSession` cmdlet to create the **PSSession** .</span></span>

### <span data-ttu-id="eb176-145">Exemplo 6: usar o parâmetro traceroute</span><span class="sxs-lookup"><span data-stu-id="eb176-145">Example 6: Use the Traceroute parameter</span></span>

<span data-ttu-id="eb176-146">Introduzido no PowerShell 6,0, o parâmetro **traceroute** mapeia uma rota entre o computador local e o destino remoto que você especifica com o parâmetro **TargetName** .</span><span class="sxs-lookup"><span data-stu-id="eb176-146">Introduced in PowerShell 6.0, the **Traceroute** parameter maps a route between the local computer and the remote destination you specify with the **TargetName** parameter.</span></span>

```powershell
Test-Connection -TargetName www.google.com -Traceroute
```

```Output
   Target: google.com

Hop Hostname                  Ping Latency Status           Source       TargetAddress
                                      (ms)
--- --------                  ---- ------- ------           ------       -------------
  1 172.20.0.1                   1       4 Success          Lira         172.217.9.174
  1 172.20.0.1                   2       3 Success          Lira         172.217.9.174
  1 172.20.0.1                   3       2 Success          Lira         172.217.9.174
  2 12.108.153.193               1       3 Success          Lira         172.217.9.174
  2 12.108.153.193               2       3 Success          Lira         172.217.9.174
  2 12.108.153.193               3       2 Success          Lira         172.217.9.174
  3 12.244.85.177                1      11 Success          Lira         172.217.9.174
  3 12.244.85.177                2      12 Success          Lira         172.217.9.174
  3 12.244.85.177                3      12 Success          Lira         172.217.9.174
  4 *                            1      14 DestinationNetw… Lira         172.217.9.174
  4 *                            2       * TimedOut         Lira         172.217.9.174
  4 *                            3      20 DestinationNetw… Lira         172.217.9.174
  5 *                            1       * TimedOut         Lira         172.217.9.174
  5 *                            2      15 DestinationNetw… Lira         172.217.9.174
  5 *                            3       * TimedOut         Lira         172.217.9.174
  6 *                            1      18 DestinationNetw… Lira         172.217.9.174
  6 *                            2       * TimedOut         Lira         172.217.9.174
  6 *                            3      16 DestinationNetw… Lira         172.217.9.174
  7 *                            1       * TimedOut         Lira         172.217.9.174
  7 *                            2       * TimedOut         Lira         172.217.9.174
  7 *                            3       * TimedOut         Lira         172.217.9.174
  8 *                            1       * TimedOut         Lira         172.217.9.174
  8 *                            2       * TimedOut         Lira         172.217.9.174
  8 *                            3       * TimedOut         Lira         172.217.9.174
  9 *                            1       * TimedOut         Lira         172.217.9.174
  9 *                            2       * TimedOut         Lira         172.217.9.174
  9 *                            3       * TimedOut         Lira         172.217.9.174
 10 *                            1       * TimedOut         Lira         172.217.9.174
 10 *                            2       * TimedOut         Lira         172.217.9.174
 10 *                            3       * TimedOut         Lira         172.217.9.174
 11 172.217.9.174                1      23 Success          Lira         172.217.9.174
 11 172.217.9.174                2      21 Success          Lira         172.217.9.174
 11 172.217.9.174                3      22 Success          Lira         172.217.9.174
```

<span data-ttu-id="eb176-147">O `Test-Connection` comando é chamado com o parâmetro **traceroute** .</span><span class="sxs-lookup"><span data-stu-id="eb176-147">The `Test-Connection` command is called with the **Traceroute** parameter.</span></span> <span data-ttu-id="eb176-148">Os resultados, que são `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceStatus]` objetos, são gerados para o fluxo de saída de **êxito** .</span><span class="sxs-lookup"><span data-stu-id="eb176-148">The results, which are `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceStatus]` objects, are output to the **Success** output stream.</span></span>

## <span data-ttu-id="eb176-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="eb176-149">PARAMETERS</span></span>

### <span data-ttu-id="eb176-150">-BufferSize</span><span class="sxs-lookup"><span data-stu-id="eb176-150">-BufferSize</span></span>

<span data-ttu-id="eb176-151">Especifica o tamanho, em bytes, do buffer enviado com esse comando.</span><span class="sxs-lookup"><span data-stu-id="eb176-151">Specifies the size, in bytes, of the buffer sent with this command.</span></span> <span data-ttu-id="eb176-152">O valor padrão é 32.</span><span class="sxs-lookup"><span data-stu-id="eb176-152">The default value is 32.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing, RepeatPing
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eb176-153">-Repetir</span><span class="sxs-lookup"><span data-stu-id="eb176-153">-Repeat</span></span>

<span data-ttu-id="eb176-154">Faz com que o cmdlet envie solicitações de ping continuamente.</span><span class="sxs-lookup"><span data-stu-id="eb176-154">Causes the cmdlet to send ping requests continuously.</span></span> <span data-ttu-id="eb176-155">Esse parâmetro não pode ser usado com o parâmetro **Count** .</span><span class="sxs-lookup"><span data-stu-id="eb176-155">This parameter can't be used with the **Count** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RepeatPing
Aliases: Continuous

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eb176-156">-Contagem</span><span class="sxs-lookup"><span data-stu-id="eb176-156">-Count</span></span>

<span data-ttu-id="eb176-157">Especifica o número de solicitações de eco a enviar.</span><span class="sxs-lookup"><span data-stu-id="eb176-157">Specifies the number of echo requests to send.</span></span> <span data-ttu-id="eb176-158">O valor padrão é 4.</span><span class="sxs-lookup"><span data-stu-id="eb176-158">The default value is 4.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eb176-159">-Atraso</span><span class="sxs-lookup"><span data-stu-id="eb176-159">-Delay</span></span>

<span data-ttu-id="eb176-160">Especifica o intervalo entre pings, em segundos.</span><span class="sxs-lookup"><span data-stu-id="eb176-160">Specifies the interval between pings, in seconds.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing, RepeatPing
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eb176-161">-DontFragment</span><span class="sxs-lookup"><span data-stu-id="eb176-161">-DontFragment</span></span>

<span data-ttu-id="eb176-162">Esse parâmetro define o sinalizador **não fragmentar** no cabeçalho IP.</span><span class="sxs-lookup"><span data-stu-id="eb176-162">This parameter sets the **Don't Fragment** flag in the IP header.</span></span> <span data-ttu-id="eb176-163">Você pode usar esse parâmetro com o parâmetro **BufferSize** para testar o tamanho do MTU do caminho.</span><span class="sxs-lookup"><span data-stu-id="eb176-163">You can use this parameter with the **BufferSize** parameter to test the Path MTU size.</span></span> <span data-ttu-id="eb176-164">Para obter mais informações sobre Path MTU, consulte o artigo [descoberta de MTU de caminho](https://wikipedia.org/wiki/Path_MTU_Discovery) na Wikipédia.</span><span class="sxs-lookup"><span data-stu-id="eb176-164">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultPing, RepeatPing
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eb176-165">-IPv4</span><span class="sxs-lookup"><span data-stu-id="eb176-165">-IPv4</span></span>

<span data-ttu-id="eb176-166">Força o cmdlet a usar o protocolo IPv4 para o teste.</span><span class="sxs-lookup"><span data-stu-id="eb176-166">Forces the cmdlet to use the IPv4 protocol for the test.</span></span>

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

### <span data-ttu-id="eb176-167">-IPv6</span><span class="sxs-lookup"><span data-stu-id="eb176-167">-IPv6</span></span>

<span data-ttu-id="eb176-168">Força o cmdlet a usar o protocolo IPv6 para o teste.</span><span class="sxs-lookup"><span data-stu-id="eb176-168">Forces the cmdlet to use the IPv6 protocol for the test.</span></span>

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

### <span data-ttu-id="eb176-169">-MaxHops</span><span class="sxs-lookup"><span data-stu-id="eb176-169">-MaxHops</span></span>

<span data-ttu-id="eb176-170">Define o número máximo de saltos que uma mensagem de solicitação ICMP pode ser enviada.</span><span class="sxs-lookup"><span data-stu-id="eb176-170">Sets the maximum number of hops that an ICMP request message can be sent.</span></span> <span data-ttu-id="eb176-171">O valor padrão é controlado pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="eb176-171">The default value is controlled by the operating system.</span></span> <span data-ttu-id="eb176-172">O valor padrão para o Windows 10 é de 128 saltos.</span><span class="sxs-lookup"><span data-stu-id="eb176-172">The default value for Windows 10 is 128 hops.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing, RepeatPing, TraceRoute
Aliases: Ttl, TimeToLive, Hops

Required: False
Position: Named
Default value: 128 hops in Windows 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eb176-173">-Ping</span><span class="sxs-lookup"><span data-stu-id="eb176-173">-Ping</span></span>

<span data-ttu-id="eb176-174">Faz com que o cmdlet faça um teste de ping.</span><span class="sxs-lookup"><span data-stu-id="eb176-174">Causes the cmdlet to do a ping test.</span></span> <span data-ttu-id="eb176-175">Esse é o modo padrão para o `Test-Connection` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eb176-175">This is the default mode for the `Test-Connection` cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultPing, RepeatPing
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eb176-176">-Quiet</span><span class="sxs-lookup"><span data-stu-id="eb176-176">-Quiet</span></span>

<span data-ttu-id="eb176-177">O parâmetro **Quiet** retorna um valor **booliano** .</span><span class="sxs-lookup"><span data-stu-id="eb176-177">The **Quiet** parameter returns a **Boolean** value.</span></span> <span data-ttu-id="eb176-178">O uso desse parâmetro suprime todos os erros.</span><span class="sxs-lookup"><span data-stu-id="eb176-178">Using this parameter suppresses all errors.</span></span>

<span data-ttu-id="eb176-179">Cada conexão testada retorna um valor **booliano** .</span><span class="sxs-lookup"><span data-stu-id="eb176-179">Each connection that's tested returns a **Boolean** value.</span></span> <span data-ttu-id="eb176-180">Se o parâmetro **TargetName** especificar vários computadores, uma matriz de valores **boolianos** será retornada.</span><span class="sxs-lookup"><span data-stu-id="eb176-180">If the **TargetName** parameter specifies multiple computers, an array of **Boolean** values is returned.</span></span>

<span data-ttu-id="eb176-181">Se **qualquer** ping para um determinado destino for executado com sucesso, `$True` será retornado.</span><span class="sxs-lookup"><span data-stu-id="eb176-181">If **any** ping to a given target succeeds, `$True` is returned.</span></span>

<span data-ttu-id="eb176-182">Se **todos os** pings para um determinado destino falharem, `$False` será retornado.</span><span class="sxs-lookup"><span data-stu-id="eb176-182">If **all** pings to a given target fail, `$False` is returned.</span></span>

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

### <span data-ttu-id="eb176-183">-ResolveDestination</span><span class="sxs-lookup"><span data-stu-id="eb176-183">-ResolveDestination</span></span>

<span data-ttu-id="eb176-184">Faz com que o cmdlet tente resolver o nome DNS do destino.</span><span class="sxs-lookup"><span data-stu-id="eb176-184">Causes the cmdlet to attempt to resolve the DNS name of the target.</span></span> <span data-ttu-id="eb176-185">Quando usado em conjunto com o parâmetro **traceroute** , os nomes DNS de todos os hosts intermediários também serão recuperados, se possível.</span><span class="sxs-lookup"><span data-stu-id="eb176-185">When used in conjunction with the **Traceroute** parameter, the DNS names of all intermediate hosts will also be retrieved, if possible.</span></span>

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

### <span data-ttu-id="eb176-186">-Source</span><span class="sxs-lookup"><span data-stu-id="eb176-186">-Source</span></span>

<span data-ttu-id="eb176-187">Especifica os nomes dos computadores de onde se origina o ping.</span><span class="sxs-lookup"><span data-stu-id="eb176-187">Specifies the names of the computers where the ping originates.</span></span> <span data-ttu-id="eb176-188">Digite uma lista separada por vírgulas de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="eb176-188">Enter a comma-separated list of computer names.</span></span> <span data-ttu-id="eb176-189">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="eb176-189">The default is the local computer.</span></span>

<span data-ttu-id="eb176-190">**Observação:** Esse parâmetro não é funcional no PowerShell versões 6 e superiores.</span><span class="sxs-lookup"><span data-stu-id="eb176-190">**NOTE:** This parameter is not functional in PowerShell versions 6 and up.</span></span>
<span data-ttu-id="eb176-191">O fornecimento desse parâmetro não terá nenhum efeito sobre o comando.</span><span class="sxs-lookup"><span data-stu-id="eb176-191">Supplying this parameter will have no effect on the command.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultPing, RepeatPing, TraceRoute, TcpPort
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eb176-192">-TargetName</span><span class="sxs-lookup"><span data-stu-id="eb176-192">-TargetName</span></span>

<span data-ttu-id="eb176-193">Especifica os computadores a serem testados.</span><span class="sxs-lookup"><span data-stu-id="eb176-193">Specifies the computer(s) to test.</span></span> <span data-ttu-id="eb176-194">Digite os nomes de computador ou endereços IP no formato IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="eb176-194">Type the computer names or type IP addresses in IPv4 or IPv6 format.</span></span>

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

### <span data-ttu-id="eb176-195">-TimeoutSeconds</span><span class="sxs-lookup"><span data-stu-id="eb176-195">-TimeoutSeconds</span></span>

<span data-ttu-id="eb176-196">Define o valor de tempo limite para o teste.</span><span class="sxs-lookup"><span data-stu-id="eb176-196">Sets the timeout value for the test.</span></span> <span data-ttu-id="eb176-197">O teste falhará se uma resposta não for recebida antes do tempo limite expirar.</span><span class="sxs-lookup"><span data-stu-id="eb176-197">The test fails if a response isn't received before the timeout expires.</span></span> <span data-ttu-id="eb176-198">O padrão é cinco segundos.</span><span class="sxs-lookup"><span data-stu-id="eb176-198">The default is five seconds.</span></span>

<span data-ttu-id="eb176-199">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="eb176-199">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="eb176-200">-Traceroute</span><span class="sxs-lookup"><span data-stu-id="eb176-200">-Traceroute</span></span>

<span data-ttu-id="eb176-201">Faz com que o cmdlet faça um teste de traceroute.</span><span class="sxs-lookup"><span data-stu-id="eb176-201">Causes the cmdlet to do a traceroute test.</span></span> <span data-ttu-id="eb176-202">Quando esse parâmetro é usado, o cmdlet retorna um `TestConnectionCommand+TraceStatus` objeto.</span><span class="sxs-lookup"><span data-stu-id="eb176-202">When this parameter is used, the cmdlet returns a `TestConnectionCommand+TraceStatus` object.</span></span>

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

### <span data-ttu-id="eb176-203">-MtuSize</span><span class="sxs-lookup"><span data-stu-id="eb176-203">-MtuSize</span></span>

<span data-ttu-id="eb176-204">Esse parâmetro é usado para descobrir o tamanho de MTU do caminho.</span><span class="sxs-lookup"><span data-stu-id="eb176-204">This parameter is used to discover the Path MTU size.</span></span> <span data-ttu-id="eb176-205">O cmdlet retorna um objeto **PingReply # MTUSize** que contém o tamanho de MTU do caminho para o destino.</span><span class="sxs-lookup"><span data-stu-id="eb176-205">The cmdlet returns a **PingReply#MTUSize** object that contains the Path MTU size to the target.</span></span> <span data-ttu-id="eb176-206">Para obter mais informações sobre Path MTU, consulte o artigo [descoberta de MTU de caminho](https://wikipedia.org/wiki/Path_MTU_Discovery) na Wikipédia.</span><span class="sxs-lookup"><span data-stu-id="eb176-206">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MtuSizeDetect
Aliases: MtuSizeDetect

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eb176-207">-TcpPort</span><span class="sxs-lookup"><span data-stu-id="eb176-207">-TcpPort</span></span>

<span data-ttu-id="eb176-208">Especifica o número da porta TCP no destino a ser usado no teste de conexão TCP.</span><span class="sxs-lookup"><span data-stu-id="eb176-208">Specifies the TCP port number on the target to be used in the TCP connection test.</span></span> <span data-ttu-id="eb176-209">O cmdlet tentará fazer uma conexão TCP com a porta especificada no destino.</span><span class="sxs-lookup"><span data-stu-id="eb176-209">The cmdlet will attempt to make a TCP connection to the specified port on the target.</span></span>

<span data-ttu-id="eb176-210">Se uma conexão puder ser estabelecida, `$True` será retornada.</span><span class="sxs-lookup"><span data-stu-id="eb176-210">If a connection can be made, `$True` will be returned.</span></span>

<span data-ttu-id="eb176-211">Se não for possível estabelecer uma conexão, `$False` será retornado.</span><span class="sxs-lookup"><span data-stu-id="eb176-211">If a connection cannot be made, `$False` will be returned.</span></span>

```yaml
Type: System.Int32
Parameter Sets: TcpPort
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eb176-212">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="eb176-212">CommonParameters</span></span>

<span data-ttu-id="eb176-213">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="eb176-213">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="eb176-214">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="eb176-214">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="eb176-215">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="eb176-215">INPUTS</span></span>

### <span data-ttu-id="eb176-216">Nenhum</span><span class="sxs-lookup"><span data-stu-id="eb176-216">None</span></span>

<span data-ttu-id="eb176-217">Não é possível canalizar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eb176-217">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="eb176-218">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="eb176-218">OUTPUTS</span></span>

### <span data-ttu-id="eb176-219">TestConnectionCommand + PingStatus, TestConnectionCommand + TraceStatus, Boolean, TestConnectionCommand + PingMtuStatus</span><span class="sxs-lookup"><span data-stu-id="eb176-219">TestConnectionCommand+PingStatus, TestConnectionCommand+TraceStatus, Boolean, TestConnectionCommand+PingMtuStatus</span></span>

<span data-ttu-id="eb176-220">Por padrão, `Test-Connection` retorna um objeto **TestConnectionCommand + PingStatus** para cada resposta de ping.</span><span class="sxs-lookup"><span data-stu-id="eb176-220">By default, `Test-Connection` returns a **TestConnectionCommand+PingStatus** object for each ping reply.</span></span>

<span data-ttu-id="eb176-221">Se você especificar o parâmetro **traceroute** , o cmdlet retornará um objeto **TestConnectionCommand + TRACESTATUS** para cada resposta de ping ao longo da rota.</span><span class="sxs-lookup"><span data-stu-id="eb176-221">If you specify the **Traceroute** parameter, the cmdlet will return a **TestConnectionCommand+TraceStatus** object for each ping reply along the route.</span></span>

<span data-ttu-id="eb176-222">Se você especificar os parâmetros **Quiet** ou **TCPPort** , ele retornará um valor **booliano** .</span><span class="sxs-lookup"><span data-stu-id="eb176-222">If you specify the **Quiet** or **TcpPort** parameters, it returns a **Boolean** value.</span></span> <span data-ttu-id="eb176-223">Se várias conexões forem testadas, uma matriz de valores **boolianos** será retornada.</span><span class="sxs-lookup"><span data-stu-id="eb176-223">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="eb176-224">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="eb176-224">NOTES</span></span>

## <span data-ttu-id="eb176-225">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="eb176-225">RELATED LINKS</span></span>

[<span data-ttu-id="eb176-226">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="eb176-226">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="eb176-227">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="eb176-227">Stop-Computer</span></span>](Stop-Computer.md)

