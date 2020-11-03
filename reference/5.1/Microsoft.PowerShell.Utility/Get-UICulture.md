---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uiculture?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UICulture
ms.openlocfilehash: 098e98dec6733af036795e4decb633f59d40c633
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192598"
---
# Get-UICulture

## SINOPSE
Obtém as configurações de cultura da interface do usuário atuais no sistema operacional.

## SYNTAX

```
Get-UICulture [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Get-UICulture** Obtém informações sobre as configurações de cultura da interface do usuário (UI) atual para Windows.
A cultura da interface do usuário determina quais cadeias de caracteres de texto são usadas para elementos de interface do usuário, como menus e mensagens.

Você também pode usar o cmdlet Get-Culture, que obtém a cultura atual do sistema.
A cultura determina o formato de exibição de itens como números, moeda e datas.

## EXEMPLOS

### Exemplo 1: obter a cultura da interface do usuário

```
PS C:\> Get-UICulture
```

Esse comando obtém as informações de cultura da interface do usuário atuais.

### Exemplo 2: obter a cultura da interface do usuário e formatar os resultados

```
PS C:\> Get-UICulture | Format-List *
```

Esse comando exibe os valores de todas as propriedades da atual cultura da interface do usuário em uma lista.

### Exemplo 3: obter o valor da Propriedade Calendar

```
PS C:\> (Get-UICulture).Calendar
```

Esse comando exibe os valores atuais para a propriedade Calendar da cultura da interface do usuário atual.
Calendar é apenas uma propriedade da cultura da interface do usuário.
Para ver todas as propriedades, digite `Get-UICulture | Get-Member` .

### Exemplo 4: obter o padrão de data abreviada

```
PS C:\> (Get-UICulture).DateTimeFormat.ShortDatePattern
```

Esse comando exibe o padrão de data abreviada para a cultura da interface do usuário atual.
Para ver todas as subpropriedades da propriedade DateTimeFormat da cultura da interface do usuário, digite `(Get-UICulture).DateTimeFormat | gm` .

## PARAMETERS

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System. Globalization. CultureInfo, Microsoft. PowerShell. VistaCultureInfo
**Get-UICulture** retorna um objeto que representa a cultura da interface do usuário atual.
No Windows PowerShell 3,0, ele retorna um objeto **CultureInfo** .
No Windows PowerShell 2,0, ele retorna um objeto **VistaCultureInfo** .

## OBSERVAÇÕES

* Você também pode usar as variáveis $PsCulture e $PsUICulture. A variável $PsCulture armazena o nome da cultura atual, e a variável $PsUICulture armazena o nome da cultura da interface do usuário atual.

*

## LINKS RELACIONADOS

## LINKS RELACIONADOS
