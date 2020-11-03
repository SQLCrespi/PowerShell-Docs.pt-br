---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-EventLog
ms.openlocfilehash: 695a13d4fbbf60caadeed994c1aa9c36432be917
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194207"
---
# Clear-EventLog

## SINOPSE
Limpa todas as entradas de logs de eventos especificados nos computadores locais ou remotos.

## SYNTAX

```
Clear-EventLog [-LogName] <String[]> [[-ComputerName] <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Clear-EventLog` cmdlet exclui todas as entradas dos logs de eventos especificados no computador local ou em computadores remotos.
Para usar `Clear-EventLog` o, você deve ser um membro do grupo Administradores no computador afetado.

Os cmdlets que contêm o substantivo **EventLog** (os cmdlets EventLog) só funcionam em logs de eventos clássicos.
Para obter eventos de logs que usam a tecnologia de log de eventos do Windows no Windows Vista e versões posteriores do Windows, use o cmdlet Get-WinEvent.

## EXEMPLOS

### Exemplo 1: limpar tipos de log de eventos específicos do computador local

```powershell
Clear-EventLog "Windows PowerShell"
```

Esse comando limpa as entradas do log de eventos do Windows PowerShell no computador local.

### Exemplo 2: limpar vários tipos de log específicos dos computadores locais e remotos

```powershell
Clear-EventLog -LogName ODiag, OSession -ComputerName localhost, Server02
```

Esse comando limpa todas as entradas nos logs de ODiag (diagnóstico de Microsoft Office) e Microsoft Office sessões (OSession) no computador local e no computador remoto Server02.

### Exemplo 3: limpar todos os logs nos computadores especificados e exibir a lista de log de eventos

```powershell
Clear-EventLog -LogName application, system -confirm
```

Este comando solicita sua confirmação antes de excluir as entradas nos logs de eventos especificados.

### Exemplo 4: limpar todos os logs nos computadores especificados e exibir a lista de log de eventos

```powershell
function clear-all-event-logs ($computerName="localhost")
{
   $logs = Get-EventLog -ComputerName $computername -List | ForEach-Object {$_.Log}
   $logs | ForEach-Object {Clear-EventLog -ComputerName $computername -LogName $_ }
   Get-EventLog -ComputerName $computername -list
}

clear-all-event-logs -ComputerName Server01
```

```Output
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded           0 Application
15,168      0 OverwriteAsNeeded           0 DFS Replication
512         7 OverwriteOlder              0 DxStudio
20,480      0 OverwriteAsNeeded           0 Hardware Events
512         7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
16,384      0 OverwriteAsNeeded           0 Microsoft Office Diagnostics
16,384      0 OverwriteAsNeeded           0 Microsoft Office Sessions
30,016      0 OverwriteAsNeeded           1 Security
15,168      0 OverwriteAsNeeded           2 System
15,360      0 OverwriteAsNeeded           0 Windows PowerShell
```

Essa função limpa todos os logs de eventos nos computadores especificados e, em seguida, exibe a lista do log de eventos resultante.

Observe que algumas entradas foram adicionadas aos logs System e Security depois de os logs serem limpos, mas antes de serem exibidos.

## PARAMETERS

### -ComputerName

Especifica um computador remoto.
O padrão é o computador local.

Digite o nome NetBIOS, um endereço IP (protocolo de Internet) ou um nome de domínio totalmente qualificado de um computador remoto.
Para especificar o computador local, digite o nome do computador, um ponto (.) ou "localhost".

Esse parâmetro não depende da comunicação remota do Windows PowerShell.
Você pode usar o parâmetro **ComputerName** de `Get-EventLog` mesmo que o computador não esteja configurado para executar comandos remotos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: 1
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### Nenhum

Não é possível canalizar objetos para `Clear-EventLog` .

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

- Para usar `Clear-EventLog` o Windows Vista e versões posteriores do Windows, inicie o Windows PowerShell com a opção "executar como administrador".

## LINKS RELACIONADOS

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
