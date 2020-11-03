---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-EventLog
ms.openlocfilehash: 4cf29146727c9a54715459a2d56e47a27c5bacc0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193955"
---
# Remove-EventLog

## SINOPSE
Exclui um log de eventos ou cancela o registro de uma fonte de evento.

## SYNTAX

### Padrão (padrão)

```
Remove-EventLog [[-ComputerName] <String[]>] [-LogName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Fonte

```
Remove-EventLog [[-ComputerName] <String[]>] [-Source <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Remove-EventLog** exclui um arquivo de log de eventos de um computador local ou remoto e cancela o registro de todas as suas origens de eventos para o log.
Você também pode usar este cmdlet para cancelar o registro de fontes de evento sem excluir nenhum dos logs de eventos.

Os cmdlets que contêm o substantivo **EventLog** , os cmdlets **EventLog** , só funcionam em logs de eventos clássicos.
Para obter eventos de logs que usam a tecnologia de log de eventos do Windows no Windows Vista e versões posteriores do sistema operacional Windows, use Get-WinEvent.

Cuidado: esse cmdlet pode excluir logs de eventos do sistema operacional, o que pode causar falhas de aplicativo e um comportamento de sistema inesperado.

## EXEMPLOS

### Exemplo 1: remover um log de eventos do computador local

```
PS C:\> Remove-EventLog -LogName "MyLog"
```

Esse comando exclui o log de eventos MyLog do computador local e cancela o registro das suas fontes de evento.

### Exemplo 2: remover um log de eventos de vários computadores

```
PS C:\> Remove-EventLog -LogName "MyLog", "TestLog" -ComputerName "Server01", "Server02", "localhost"
```

Esse comando exclui os logs de eventos MyLog e TestLog do computador local e os computadores remotos Server01 e Server02.
O comando também cancela o registro de fontes de evento para esses logs.

### Exemplo 3: excluir uma origem do evento

```
PS C:\> Remove-EventLog -Source "MyApp"
```

Esse comando exclui a origem do evento MyApp dos logs no computador local.
Quando o comando é concluído, o programa MyApp não pode gravar em nenhum log de eventos.

### Exemplo 4: remover um log de eventos e confirmar a ação

```
The first command lists the event logs on the local computer.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
15,168      7 OverwriteAsNeeded          12 ZapLog

The second command deletes the ZapLog event log.
PS C:\> Remove-EventLog -LogName "ZapLog"

The third command lists the event logs again. The ZapLog event log no longer appears in the list.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
```

Estes comandos mostram como listar os logs de eventos em um computador e verificar se um comando **Remove-EventLog** foi bem-sucedido.

### Exemplo 5: remover uma origem do evento e confirmar a ação

```
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'" | foreach {$_.sources}
MyApp
TestApp
PS C:\> Remove-Eventlog -Source "MyApp"
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'"} | foreach {$_.sources}
TestApp
```

Esses comandos usam o cmdlet Get-WmiObject para listar as fontes de evento no computador local.
É possível usar esses comandos para verificar o êxito de um comando ou para excluir uma fonte de evento.

O primeiro comando obtém as fontes de eventos do log de eventos TestLog no computador local.
MyApp é uma das fontes.

O segundo comando usa o parâmetro *Source* de **Remove-EventLog** para excluir a origem do evento MyApp.

O terceiro comando é idêntico ao primeiro.
Ele mostra que a fonte de evento MyApp foi excluída.

## PARAMETERS

### -ComputerName
Especifica um computador remoto.
O padrão é o computador local.

Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um computador remoto.
Para especificar o computador local, digite o nome do computador, um ponto (.) ou localhost.

Esse parâmetro não depende da comunicação remota do Windows PowerShell.
Você pode usar o parâmetro *ComputerName* de **Remove-EventLog** mesmo que o computador não esteja configurado para executar comandos remotos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName
Especifica os logs de evento.
Insira o nome do log de um ou mais logs de eventos, separados por vírgulas.
O nome do log é o valor da propriedade **log** , não o *LogDisplayName* , caracteres curinga não são permitidos.
Este parâmetro é necessário.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source
Especifica as origens de eventos que esse cmdlet cancela o registro.
Insira os nomes de origem, não o nome do executável, separados por vírgulas.

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: SRC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Solicita sua confirmação antes de executar o cmdlet.

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

### -WhatIf
Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

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

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Nenhum
Este cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

* Para usar **Remove-EventLog** no Windows Vista e em versões posteriores do sistema operacional Windows, inicie o Windows PowerShell usando a opção Executar como administrador.

  Se você remover um log de eventos e, em seguida, recriar o log, você não poderá registrar as mesmas fontes de evento.
Aplicativos que usavam as fontes de eventos para gravar entradas para o log original não serão capazes de gravar no novo log.

* Quando você cancela o registro de uma fonte de evento para um log específico, a origem do evento pode ser impedida de gravar entradas nos outros logs de eventos.

## LINKS RELACIONADOS

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
