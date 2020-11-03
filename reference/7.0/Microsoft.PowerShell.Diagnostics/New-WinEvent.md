---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/new-winevent?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WinEvent
ms.openlocfilehash: 8e64c3e3a782fadf1669f1310d1615f3a014ccee
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192817"
---
# New-WinEvent

## SINOPSE
Cria um novo evento do Windows para o provedor de eventos especificado.

## SYNTAX

```
New-WinEvent [-ProviderName] <String> [-Id] <Int32> [-Version <Byte>] [[-Payload] <Object[]>]
 [<CommonParameters>]
```

## DESCRIPTION

O **New-WinEvent** cria um evento de rastreamento de eventos do Windows (ETW) para um provedor de eventos.
Você pode usar este cmdlet para adicionar eventos a canais ETW do PowerShell.

## EXEMPLOS

### Exemplo 1

```powershell
PS C:\> New-WinEvent -ProviderName Microsoft-Windows-PowerShell -Id 45090 -Payload @("Workflow", "Running")
```

Este comando usa o cmdlet **New-WinEvent** para criar o evento 45090 para o provedor Microsoft-Windows-PowerShell.

## PARAMETERS

### -Id

Especifica um identificador de evento que foi registrado por meio de um manifesto de instrumentação.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Conteúdo

Especifica a mensagem para o evento. Quando os eventos são gravados em um log de eventos, a carga é armazenada na propriedade **Message** do objeto de evento.

Quando a carga especificada não corresponder à carga na definição de evento, o PowerShell gerará um aviso, mas o comando ainda terá sucesso.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderName

Especifica o provedor de eventos que grava o evento em um log de eventos, como "Microsoft-Windows-PowerShell". Um provedor de eventos ETW é uma entidade lógica que grava eventos em sessões de ETW.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version

Especifica o número de versão do evento. Digite o número do evento. O PowerShell converte o número para o tipo de byte necessário.

Este parâmetro permite que você especifique um evento quando versões diferentes do mesmo evento são definidas.

```yaml
Type: System.Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Este cmdlet não recebe entrada do pipeline.

## SAÍDAS

### Nenhum

Este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

* Depois que o provedor grava o mesmo em um EventLog, você pode usar o cmdlet Get-WinEvent para obter o evento do log de eventos.

## LINKS RELACIONADOS

[Get-WinEvent](Get-WinEvent.md)
