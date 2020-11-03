---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-EventLog
ms.openlocfilehash: e8dbcf1aa4280c0481714a8a9fb24f2e5ef79ffe
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193918"
---
# Show-EventLog

## SINOPSE
Exibe os logs de eventos do local ou de um computador remoto no Visualizador de eventos.

## SYNTAX

```
Show-EventLog [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Show-EventLog** abre Visualizador de eventos no computador local e exibe todos os logs de eventos clássicos no computador local ou em um computador remoto.

Para abrir Visualizador de Eventos no Windows Vista e versões posteriores do sistema operacional Windows, o usuário atual deve ser um membro do grupo Administradores no computador local.

Os cmdlets que contêm o substantivo **EventLog** (os cmdlets **EventLog** ) só funcionam em logs de eventos clássicos.
Para obter eventos de logs que usam a tecnologia de log de eventos do Windows no Windows Vista e versões posteriores do sistema operacional Windows, use o cmdlet Get-WinEvent.

## EXEMPLOS

### Exemplo 1: Exibir logs de eventos para o computador local

```
PS C:\> Show-EventLog
```

Esse comando abre o Visualizador de eventos e exibe nos logs de eventos clássicos no computador local.

### Exemplo 2: Exibir logs de eventos para um computador remoto

```
PS C:\> Show-EventLog -ComputerName "Server01"
```

Esse comando abre o Visualizador de eventos e exibe os logs de eventos clássicos no computador Server01.

## PARAMETERS

### -ComputerName
Especifica um computador remoto.
**Show-EventLog** exibe os logs de eventos do computador especificado em Visualizador de eventos no computador local.
O padrão é o computador local.

Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um computador remoto.

Esse parâmetro não depende da comunicação remota do Windows PowerShell.
Você pode usar o parâmetro *ComputerName* , mesmo que seu computador não esteja configurado para executar comandos remotos.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
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

### Nenhum
Este cmdlet não gera saída.

## OBSERVAÇÕES

* O prompt de comando do Windows PowerShell retorna assim que o Visualizador de eventos é aberto. É possível trabalhar na sessão atual enquanto o Visualizador de eventos está aberto.

  Como esse cmdlet exige uma interface do usuário, ele não funciona em instalações Server Core do Windows Server.

*

## LINKS RELACIONADOS

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Write-EventLog](Write-EventLog.md)
