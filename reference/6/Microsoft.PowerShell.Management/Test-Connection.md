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
# Test-Connection

## SINOPSE
Envia pacotes de solicitação de eco ICMP, ou pings, para um ou mais computadores.

## SYNTAX

### PingCount (padrão)

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Count <Int32>] [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### PingContinues

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-Continues] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### DetectionOfMTUSize

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -MTUSizeDetect [-Quiet] [<CommonParameters>]
```

### Rotas

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-TimeoutSeconds <Int32>] [-TargetName] <String[]> -Traceroute [-Quiet] [<CommonParameters>]
```

### ConnectionByTCPPort

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -TCPPort <Int32> [-Quiet] [<CommonParameters>]
```

## DESCRIPTION

O `Test-Connection` cmdlet envia pacotes de solicitação de eco do protocolo ICMP, ou pings, para um ou mais computadores remotos e retorna as respostas de resposta de eco. Você pode usar este cmdlet para determinar se um computador específico pode ser contatado em uma rede IP.

Você pode usar os parâmetros de `Test-Connection` para especificar os computadores de envio e de recebimento, para executar o comando como um trabalho em segundo plano, definir um tempo limite e um número de pings e configurar a conexão e a autenticação.

Diferentemente do comando **ping** conhecido, `Test-Connection` retorna um objeto **TestConnectionCommand + PingReport** que você pode investigar no PowerShell. O parâmetro **Quiet** retorna um valor **booliano** em um objeto **System. Boolean** para cada conexão testada. Se várias conexões forem testadas, uma matriz de valores **boolianos** será retornada.

## EXEMPLOS

### Exemplo 1: enviar solicitações de eco para um computador remoto

Este exemplo envia pacotes de solicitação de eco do computador local para o computador Server01.

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

`Test-Connection` usa o parâmetro **TargetName** para especificar o computador Server01. O parâmetro **IPv4** especifica o protocolo para o teste.

A saída de ping é enviada ao fluxo de **informações** enquanto o objeto **TestConnectionCommand + PingReport** enviado para o fluxo de **êxito** . Para obter mais informações sobre os fluxos de saída, consulte [about_Redirection](../microsoft.powershell.core/about/about_redirection.md).

### Exemplo 2: enviar solicitações de eco para vários computadores

Este exemplo envia pings do computador local para vários computadores remotos.

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### Exemplo 3: enviar solicitações de eco de vários computadores a um computador

Este exemplo envia pings de computadores de origem diferentes para um único computador remoto, Server01.

```powershell
Test-Connection -Source Server02, Server12, localhost -TargetName Server01
```

Use esse formato de comando para testar a latência de conexões de vários pontos.

### Exemplo 4: usar parâmetros para personalizar o comando de teste

Este exemplo usa os parâmetros de `Test-Connection` para personalizar o comando. O computador local envia um teste de ping para um computador remoto.

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

`Test-Connection` usa o parâmetro **TargetName** para especificar Server01. O parâmetro **Count** especifica que três pings são enviados para o computador Server01 com um **atraso** de intervalos de 2 segundos.

Você pode usar essas opções quando espera-se que a resposta de ping demore mais do que o normal, devido a um número estendido de saltos ou a uma condição de rede de tráfego alto.

### Exemplo 5: executar um teste como um trabalho em segundo plano

Este exemplo mostra como executar um `Test-Connection` comando como um trabalho em segundo plano do PowerShell.

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content "Servers.txt") }
if ($job.JobStateInfo.State -ne "Running") { $Results = Receive-Job $job }
```

O `Start-Job` comando usa o `Test-Connection` cmdlet para executar ping em vários computadores em uma empresa.
O valor do parâmetro **TargetName** é um `Get-Content` comando que lê uma lista de nomes de computador a partir do `Servers.txt` arquivo. O comando usa o `Start-Job` cmdlet para executar o comando como um trabalho em segundo plano e salva o trabalho na `$job` variável.

O `if` comando verifica para ver se o trabalho ainda não está em execução. Se o trabalho não estiver em execução, `Receive-Job` o obterá os resultados e os armazenará na `$Results` variável.

### Exemplo 6: criar uma sessão somente se um teste de conexão tiver sucesso

Este exemplo criará uma sessão no computador Server01 somente se pelo menos um dos pings enviados para o computador for executado com sucesso.

```powershell
if (Test-Connection -TargetName Server01 -Quiet) {New-PSSession Server01}
```

O `if` comando usa o `Test-Connection` cmdlet para executar ping no computador Server01. O comando usa o parâmetro **Quiet** , que retorna um valor **booliano** , em vez de um objeto **TestConnectionCommand + PingReport** .

O valor será `$True` se qualquer um dos quatro pings for bem-sucedidos. Se nenhum dos pings for bem-sucedidos, o valor será `$False` .

Se o `Test-Connection` comando retornar um valor de `$True` , o comando usará o `New-PSSession` cmdlet para criar a **PSSession** .

### Exemplo 7: usar o parâmetro traceroute

A partir do PowerShell 6,0, o parâmetro **traceroute** mapeia uma rota entre o computador local e o destino remoto que você especifica com o parâmetro **TargetName** .

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

O `Test-Connection` comando usa o parâmetro **traceroute** . Os resultados, que são `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteResult]` objetos, são canalizados para o `ForEach-Object` cmdlet. `ForEach-Object` Cria uma saída estruturada dos `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteReply]` objetos contidos e dos `[System.Net.NetworkInformation.PingReply]` objetos subsequentes.

## PARAMETERS

### -BufferSize

Especifica o tamanho, em bytes, do buffer enviado com esse comando. O valor padrão é 32.

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

### -Contagem

Especifica o número de solicitações de eco a enviar. O valor padrão é 4.

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

### -Atraso

Especifica o intervalo entre pings, em segundos.

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

### -DontFragment

Esse parâmetro define o sinalizador **não fragmentar** no cabeçalho IP. Você pode usar esse parâmetro com o parâmetro **BufferSize** para testar o tamanho do MTU do caminho. Para obter mais informações sobre Path MTU, consulte o artigo [descoberta de MTU de caminho](https://wikipedia.org/wiki/Path_MTU_Discovery) na Wikipédia.

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

### -IPv4

Força o cmdlet a usar o protocolo IPv4 para o teste.

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

### -IPv6

Força o cmdlet a usar o protocolo IPv6 para o teste.

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

### -MaxHops

Define o número máximo de saltos que uma mensagem de solicitação ICMP pode ser enviada. O valor padrão é controlado pelo sistema operacional. O valor padrão para o Windows 10 é de 128 saltos.

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

### -Ping

Faz com que o cmdlet faça um teste de ping, que é a ação padrão.

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

### -Quiet

O parâmetro **Quiet** retorna um valor **booliano** em um objeto **System. Boolean** . O uso desse parâmetro suprime todos os erros.

Cada conexão testada retorna um valor **booliano** . Se o parâmetro **TargetName** especificar vários computadores, uma matriz de valores **boolianos** será retornada.

Se **qualquer** ping for executado com sucesso, `$True` será retornado.

Se **todos os** pings falharem, `$False` será retornado.

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

### -ResolveDestination

Faz com que o cmdlet tente resolver o nome DNS do destino.

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

### -Source

Especifica os nomes dos computadores de onde se origina o ping. Digite uma lista separada por vírgulas de nomes de computador. O padrão é o computador local.

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

### -TargetName

Especifica os computadores a serem testados. Digite os nomes de computador ou endereços IP no formato IPv4 ou IPv6. Caracteres curinga não são permitidos. Este parâmetro é necessário. **ComputerName** é um alias para este parâmetro.

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

### -TCPPort

Especifica o número da porta TCP no destino a ser usado no teste de conexão TCP. O cmdlet tentará fazer uma conexão TCP com a porta especificada no destino.

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

### -TimeoutSeconds

Define o valor de tempo limite para o teste. O teste falhará se uma resposta não for recebida antes do tempo limite expirar. O padrão é cinco segundos.

Esse parâmetro foi introduzido no PowerShell 6,0.

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

### -Traceroute

Faz com que o cmdlet faça um teste de traceroute. Quando esse parâmetro é usado, o cmdlet retorna um `TestConnectionCommand+TraceRouteResult` objeto.

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

### -Continua

Faz com que o cmdlet envie solicitações de ping continuamente. Esse parâmetro não pode ser usado com o parâmetro **Count** .

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

### -MTUSizeDetect

Esse parâmetro é usado para descobrir o tamanho de MTU do caminho. O cmdlet retorna um objeto **PingReply # MTUSize** que contém o tamanho de MTU do caminho para o destino. Para obter mais informações sobre Path MTU, consulte o artigo [descoberta de MTU de caminho](https://wikipedia.org/wiki/Path_MTU_Discovery) na Wikipédia.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível canalizar a entrada para este cmdlet.

## SAÍDAS

### TestConnectionCommand + PingReport, TestConnectionCommand + TraceRouteResult, Boolean, PingReply # MTUSize

Se você especificar o parâmetro **Quiet** , ele retornará um valor **booliano** . Se várias conexões forem testadas, uma matriz de valores **boolianos** será retornada. Caso contrário, `Test-Connection` retorna um objeto **TestConnectionCommand + PingReport** para cada ping.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
