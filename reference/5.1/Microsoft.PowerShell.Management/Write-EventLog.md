---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/write-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-EventLog
ms.openlocfilehash: 4044453cb46b407344619f1edd3227213bf67250
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388239"
---
# Write-EventLog

## SINOPSE
Grava um evento em um log de eventos.

## SYNTAX

```
Write-EventLog [-LogName] <String> [-Source] <String> [[-EntryType] <EventLogEntryType>] [-Category <Int16>]
 [-EventId] <Int32> [-Message] <String> [-RawData <Byte[]>] [-ComputerName <String>] [<CommonParameters>]
```

## DESCRIPTION
O `Write-EventLog` cmdlet grava um evento em um log de eventos.

Para gravar um evento em um log de eventos, o log de eventos deve existir no computador, e a origem deve ser registrada para o log de eventos.

Os cmdlets que contêm o substantivo **EventLog** (os cmdlets **EventLog** ) só funcionam em logs de eventos clássicos. Para obter eventos de logs que usam a tecnologia de log de eventos do Windows no Windows Vista e versões posteriores do sistema operacional Windows, use o `Get-WinEvent` cmdlet.

## EXEMPLOS

### Exemplo 1: gravar um evento no log de eventos do aplicativo

```
PS C:\> Write-EventLog -LogName "Application" -Source "MyApp" -EventID 3001 -EntryType Information -Message "MyApp added a user-requested feature to the display." -Category 1 -RawData 10,20
```

Este comando grava um evento no log de eventos de aplicativo da origem MyApp.

### Exemplo 2: gravar um evento no log de eventos do aplicativo de um computador remoto

```
PS C:\> Write-EventLog -ComputerName "Server01" -LogName Application -Source "MyApp" -EventID 3001 -Message "MyApp added a user-requested feature to the display."
```

Este comando grava um evento da origem MyApp no log de eventos do aplicativo no computador remoto Server01.

## PARAMETERS

### -Categoria

Especifica uma categoria de tarefa para o evento. Insira um número inteiro que está associado às cadeias de caracteres no arquivo de mensagem de categoria para o log de eventos.

```yaml
Type: System.Int16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Especifica um computador remoto. O padrão é o computador local.

Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um computador remoto.

Esse parâmetro não depende da comunicação remota do Windows PowerShell. Você pode usar o parâmetro **ComputerName** do `Get-EventLog` cmdlet, mesmo se o computador não estiver configurado para executar comandos remotos.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntryType

Especifica o tipo de entrada do evento. Os valores aceitáveis para esse parâmetro são: erro, aviso, informações, SuccessAudit e FailureAudit. O valor padrão é Information.

Para obter uma descrição dos valores, consulte [Enumeração EventLogEntryType](/dotnet/api/system.diagnostics.eventlogentrytype).

```yaml
Type: System.Diagnostics.EventLogEntryType
Parameter Sets: (All)
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventId

Especifica o identificador do evento. Este parâmetro é necessário. O valor máximo para o parâmetro **EventID** é 65535.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: ID, EID

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName

Especifica o nome do log no qual o evento será gravado. Insira o nome do log. O nome do log é o valor da propriedade **log** , não o **LogDisplayName**. Caracteres curinga não são permitidos.
Este parâmetro é necessário.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mensagem

Especifica a mensagem do evento. Este parâmetro é necessário.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MSG

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RawData

Especifica os dados binários associados ao evento, em bytes.

```yaml
Type: System.Byte[]
Parameter Sets: (All)
Aliases: RD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Especifica a origem do evento, que normalmente é o nome do aplicativo que está gravando o evento no log.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System. Diagnostics. EventLogEntry
Esse cmdlet retorna objetos que representam os eventos nos logs.

## OBSERVAÇÕES

Para usar `Write-EventLog` o, inicie o Windows PowerShell usando a opção Executar como administrador.

## LINKS RELACIONADOS

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
