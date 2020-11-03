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
# Test-Connection

## SINOPSE
Envia pacotes de solicitação de eco ICMP, ou pings, para um ou mais computadores.

## SYNTAX

### Defaultping (padrão)

```
Test-Connection [-TargetName] <string[]> [-Ping] [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-Count <int>] [-Delay <int>] [-BufferSize <int>]
 [-DontFragment] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### RepeatPing

```
Test-Connection [-TargetName] <string[]> -Repeat [-Ping] [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-Delay <int>] [-BufferSize <int>] [-DontFragment]
 [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### MtuSizeDetect

```
Test-Connection [-TargetName] <string[]> -MtuSize [-IPv4] [-IPv6] [-ResolveDestination]
 [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### Rotas

```
Test-Connection [-TargetName] <string[]> -Traceroute [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### TcpPort

```
Test-Connection [-TargetName] <string[]> -TcpPort <int> [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

## DESCRIPTION

O `Test-Connection` cmdlet envia pacotes de solicitação de eco do protocolo ICMP, ou pings, para um ou mais computadores remotos e retorna as respostas de resposta de eco. Você pode usar este cmdlet para determinar se um computador específico pode ser contatado em uma rede IP.

Você pode usar os parâmetros de `Test-Connection` para especificar os computadores de envio e de recebimento, para executar o comando como um trabalho em segundo plano, definir um tempo limite e um número de pings e configurar a conexão e a autenticação.

Diferentemente do comando **ping** conhecido, `Test-Connection` retorna um objeto **TestConnectionCommand + PingStatus** que você pode investigar no PowerShell. O parâmetro **Quiet** retorna um valor **booliano** em um objeto **System. Boolean** para cada conexão testada. Se várias conexões forem testadas, uma matriz de valores **boolianos** será retornada.

## EXEMPLOS

### Exemplo 1: enviar solicitações de eco para um computador remoto

Este exemplo envia pacotes de solicitação de eco do computador local para o computador Server01.

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

`Test-Connection` usa o parâmetro **TargetName** para especificar o computador Server01. O parâmetro **IPv4** especifica o protocolo para o teste.

Uma série de objetos **TestConnectionCommand + PingStatus** é enviada para o fluxo de saída, um objeto por resposta de ping do computador de destino.

### Exemplo 2: enviar solicitações de eco para vários computadores

Este exemplo envia pings do computador local para vários computadores remotos.

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### Exemplo 3: usar parâmetros para personalizar o comando de teste

Este exemplo usa os parâmetros de `Test-Connection` para personalizar o comando. O computador local envia um teste de ping para um computador remoto.

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

`Test-Connection` usa o parâmetro **TargetName** para especificar Server01. O parâmetro **Count** especifica que três pings são enviados para o computador Server01 com um **atraso** de intervalos de 2 segundos.

Você pode usar essas opções quando espera-se que a resposta de ping demore mais do que o normal, devido a um número estendido de saltos ou a uma condição de rede de tráfego alto.

### Exemplo 4: executar um teste como um trabalho em segundo plano

Este exemplo mostra como executar um `Test-Connection` comando como um trabalho em segundo plano do PowerShell.

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content -Path "Servers.txt") }
$Results = Receive-Job $job -Wait
```

O `Start-Job` comando usa o `Test-Connection` cmdlet para executar ping em vários computadores em uma empresa.
O valor do parâmetro **TargetName** é um `Get-Content` comando que lê uma lista de nomes de computador a partir do `Servers.txt` arquivo. O comando usa o `Start-Job` cmdlet para executar o comando como um trabalho em segundo plano e salva o trabalho na `$job` variável.

O `Receive-Job` comando é instruído `-Wait` até até que o trabalho seja concluído e, em seguida, obtém os resultados e os armazena na `$Results` variável.

### Exemplo 5: criar uma sessão somente se um teste de conexão tiver sucesso

Este exemplo criará uma sessão no computador Server01 somente se pelo menos um dos pings enviados para o computador for executado com sucesso.

```powershell
if (Test-Connection -TargetName Server01 -Quiet) { New-PSSession -ComputerName Server01 }
```

O `Test-Connection` cmdlet executa ping no `Server01` computador, com o parâmetro **Quiet** fornecido.
O valor resultante será `$True` se qualquer um dos quatro pings for bem-sucedidos. Se nenhum dos pings for bem-sucedidos, o valor será `$False` .

Se o `Test-Connection` comando retornar um valor de `$True` , o comando usará o `New-PSSession` cmdlet para criar a **PSSession** .

### Exemplo 6: usar o parâmetro traceroute

Introduzido no PowerShell 6,0, o parâmetro **traceroute** mapeia uma rota entre o computador local e o destino remoto que você especifica com o parâmetro **TargetName** .

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

O `Test-Connection` comando é chamado com o parâmetro **traceroute** . Os resultados, que são `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceStatus]` objetos, são gerados para o fluxo de saída de **êxito** .

## PARAMETERS

### -BufferSize

Especifica o tamanho, em bytes, do buffer enviado com esse comando. O valor padrão é 32.

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

### -Repetir

Faz com que o cmdlet envie solicitações de ping continuamente. Esse parâmetro não pode ser usado com o parâmetro **Count** .

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

### -Contagem

Especifica o número de solicitações de eco a enviar. O valor padrão é 4.

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

### -Atraso

Especifica o intervalo entre pings, em segundos.

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

### -DontFragment

Esse parâmetro define o sinalizador **não fragmentar** no cabeçalho IP. Você pode usar esse parâmetro com o parâmetro **BufferSize** para testar o tamanho do MTU do caminho. Para obter mais informações sobre Path MTU, consulte o artigo [descoberta de MTU de caminho](https://wikipedia.org/wiki/Path_MTU_Discovery) na Wikipédia.

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
Parameter Sets: DefaultPing, RepeatPing, TraceRoute
Aliases: Ttl, TimeToLive, Hops

Required: False
Position: Named
Default value: 128 hops in Windows 10
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ping

Faz com que o cmdlet faça um teste de ping. Esse é o modo padrão para o `Test-Connection` cmdlet.

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

### -Quiet

O parâmetro **Quiet** retorna um valor **booliano** . O uso desse parâmetro suprime todos os erros.

Cada conexão testada retorna um valor **booliano** . Se o parâmetro **TargetName** especificar vários computadores, uma matriz de valores **boolianos** será retornada.

Se **qualquer** ping para um determinado destino for executado com sucesso, `$True` será retornado.

Se **todos os** pings para um determinado destino falharem, `$False` será retornado.

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

Faz com que o cmdlet tente resolver o nome DNS do destino. Quando usado em conjunto com o parâmetro **traceroute** , os nomes DNS de todos os hosts intermediários também serão recuperados, se possível.

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

**Observação:** Esse parâmetro não é funcional no PowerShell versões 6 e superiores.
O fornecimento desse parâmetro não terá nenhum efeito sobre o comando.

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

### -TargetName

Especifica os computadores a serem testados. Digite os nomes de computador ou endereços IP no formato IPv4 ou IPv6.

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

Faz com que o cmdlet faça um teste de traceroute. Quando esse parâmetro é usado, o cmdlet retorna um `TestConnectionCommand+TraceStatus` objeto.

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

### -MtuSize

Esse parâmetro é usado para descobrir o tamanho de MTU do caminho. O cmdlet retorna um objeto **PingReply # MTUSize** que contém o tamanho de MTU do caminho para o destino. Para obter mais informações sobre Path MTU, consulte o artigo [descoberta de MTU de caminho](https://wikipedia.org/wiki/Path_MTU_Discovery) na Wikipédia.

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

### -TcpPort

Especifica o número da porta TCP no destino a ser usado no teste de conexão TCP. O cmdlet tentará fazer uma conexão TCP com a porta especificada no destino.

Se uma conexão puder ser estabelecida, `$True` será retornada.

Se não for possível estabelecer uma conexão, `$False` será retornado.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível canalizar a entrada para este cmdlet.

## SAÍDAS

### TestConnectionCommand + PingStatus, TestConnectionCommand + TraceStatus, Boolean, TestConnectionCommand + PingMtuStatus

Por padrão, `Test-Connection` retorna um objeto **TestConnectionCommand + PingStatus** para cada resposta de ping.

Se você especificar o parâmetro **traceroute** , o cmdlet retornará um objeto **TestConnectionCommand + TRACESTATUS** para cada resposta de ping ao longo da rota.

Se você especificar os parâmetros **Quiet** ou **TCPPort** , ele retornará um valor **booliano** . Se várias conexões forem testadas, uma matriz de valores **boolianos** será retornada.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)

