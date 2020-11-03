---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/limit-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Limit-EventLog
ms.openlocfilehash: 3ec3214103dc6151e148f7482b0be8b821871e3c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193982"
---
# Limit-EventLog

## SINOPSE
Define as propriedades de log de eventos que limitam o tamanho do log de eventos e a idade de suas entradas.

## SYNTAX

```
Limit-EventLog [-LogName] <String[]> [-ComputerName <String[]>] [-RetentionDays <Int32>]
 [-OverflowAction <OverflowAction>] [-MaximumSize <Int64>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Limit-EventLog** define o tamanho máximo de um log de eventos clássico, quanto tempo cada evento deve ser retido e o que acontece quando o log atinge seu tamanho máximo.
Você pode usá-lo para limitar os logs de eventos em computadores locais ou remotos.

Os cmdlets que contêm o substantivo EventLog (os cmdlets EventLog) funcionam somente em logs de eventos clássicos.
Para obter eventos de logs que usam a tecnologia de log de eventos do Windows no Windows Vista e em versões posteriores do Windows, use o Get-WinEvent.

## EXEMPLOS

### Exemplo 1: aumentar o tamanho de um log de eventos

```
PS C:\> Limit-EventLog -LogName "Windows PowerShell" -MaximumSize 20KB
```

Este comando aumenta o tamanho máximo do log de eventos do Windows PowerShell no computador local para 20480 bytes (20 KB).

### Exemplo 2: manter um log de eventos durante uma duração especificada

```
PS C:\> Limit-EventLog -LogName Security -ComputerName "Server01", "Server02" -RetentionDays 7
```

Este comando garante que os eventos no log de segurança nos computadores Server01 e Server02 sejam mantidos por pelo menos 7 dias.

### Exemplo 3: alterar a ação de estouro de todos os logs de eventos

```
PS C:\> $Logs = Get-EventLog -List | ForEach {$_.log}
PS C:\> Limit-EventLog -OverflowAction OverwriteOlder -LogName $Logs
PS C:\> Get-EventLog -List

Max(K) Retain OverflowAction     Entries  Log
------ ------ --------------     -------  ---
15,168      0 OverwriteOlder       3,412  Application
512         0 OverwriteOlder           0  DFS Replication
512         0 OverwriteOlder          17  DxStudio
10,240      7 OverwriteOlder           0  HardwareEvents
512         0 OverwriteOlder           0  Internet Explorer
512         0 OverwriteOlder           0  Key Management Service
16,384      0 OverwriteOlder           4  ODiag
16,384      0 OverwriteOlder         389  OSession Security
15,168      0 OverwriteOlder      19,360  System
15,360      0 OverwriteOlder      15,828  Windows PowerShell
```

Este exemplo altera a ação de estouro de todos os logs de eventos no computador local para OverwriteOlder.

O primeiro comando obtém os nomes de log de todos os logs no computador local.
O segundo comando define a ação de estouro.
O terceiro comando exibe os resultados.

## PARAMETERS

### -ComputerName
Especifica computadores remotos.
O padrão é o computador local.

Digite o nome NetBIOS, um endereço IP (Internet Protocol) ou um FQDN (nome de domínio totalmente qualificado) de um computador remoto.
Para especificar o computador local, digite o nome do computador, um ponto (.) ou localhost.

Esse parâmetro não depende da comunicação remota do Windows PowerShell.
Você pode usar o parâmetro *ComputerName* de **Limit-EventLog** mesmo que o computador não esteja configurado para executar comandos remotos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName
Especifica os logs de evento.
Insira o nome do log (o valor da propriedade Log; não o LogDisplayName) de um ou mais logs de eventos, separados por vírgulas.
Caracteres curinga não são permitidos.
Este parâmetro é necessário.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumSize
Especifica o tamanho máximo dos logs de eventos em bytes.
Insira um valor entre 64 quilobytes (KB) e 4 gigabytes (GB).
O valor deve ser divisível por 64 KB (65536).

Esse parâmetro especifica o valor da propriedade **MaximumKilobytes** do objeto **System. Diagnostics. EventLog** que representa um log de eventos clássico.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Estouro deaction
Especifica o que acontece quando o log de eventos atingir seu tamanho máximo.

Os valores aceitáveis para esse parâmetro são:

- DoNotOverwrite: as entradas existentes são retidas e novas entradas são descartadas.
- OverwriteAsNeeded: cada nova entrada substitui a entrada mais antiga.
- OverwriteOlder: novos eventos substituem eventos mais antigos que o valor especificado pela propriedade **MinimumRetentionDays** . Se não houver eventos mais antigos do que o especificado pelo valor da propriedade **MinimumRetentionDays** , novos eventos serão descartados.

Esse parâmetro especifica o valor da propriedade **estouraction** do objeto **System. Diagnostics. EventLog** que representa um log de eventos clássico.

```yaml
Type: System.Diagnostics.OverflowAction
Parameter Sets: (All)
Aliases: OFA
Accepted values: OverwriteOlder, OverwriteAsNeeded, DoNotOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionDays
Especifica o número mínimo de dias que um evento deve permanecer no log de eventos.

Esse parâmetro especifica o valor da propriedade **MinimumRetentionDays** do objeto **System. Diagnostics. EventLog** que representa um log de eventos clássico.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: MRD

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
Este cmdlet não gera saída.

## OBSERVAÇÕES

* Para usar esse cmdlet no Windows Vista e em versões posteriores do Windows, abra o Windows PowerShell com a opção Executar como administrador.

  Esse cmdlet altera as propriedades do objeto **System. Diagnostics. EventLog** que representa um log de eventos clássico.
Para ver as configurações atuais das propriedades do log de eventos, digite `Get-EventLog -List` .

*

## LINKS RELACIONADOS

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
