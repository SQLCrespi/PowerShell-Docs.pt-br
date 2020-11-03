---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-null?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Null
ms.openlocfilehash: a9d5c47eaf189e37f7f16b11cd48101f7b0e584d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194415"
---
# Out-Null

## SINOPSE
Oculta a saída em vez de enviá-la pelo pipeline ou exibi-la.

## SYNTAX

```
Out-Null [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **out-null** envia sua saída para NULL, em vigor, removendo-a do pipeline e impedindo que a saída seja exibida na tela.

## EXEMPLOS

### Exemplo 1: excluir saída

```powershell
Get-ChildItem | Out-Null
```

Esse comando obtém itens no local/diretório atual, mas sua saída não é passada pelo pipeline nem exibida na linha de comando.
Isso é útil para ocultar a saída que você não precisa.

## PARAMETERS

### -InputObject

Especifica o objeto a ser enviado para NULL (removido do Pipeline).
Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

É possível canalizar qualquer objeto para esse cmdlet.

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

* Os cmdlets que contêm o verbo **out** (os cmdlets **out** ) não têm parâmetros para nomes ou caminhos de arquivo. Para enviar dados para um cmdlet **out** , use um operador de pipeline (|) para enviar a saída de um comando do PowerShell para o cmdlet. Você também pode armazenar dados em uma variável e usar o parâmetro *InputObject* para passar os dados para o cmdlet. Para obter mais informações, consulte os exemplos.
* **Out-null** não retorna nenhum objeto de saída. Se você canalizar a saída de **out-null** para o cmdlet Get-Member, **Get-Member** relatará que nenhum objeto foi especificado.

## LINKS RELACIONADOS

[Out-Default](Out-Default.md)

[Out-Host](Out-Host.md)
