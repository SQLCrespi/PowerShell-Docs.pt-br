---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-printer?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Printer
ms.openlocfilehash: 552ccc39cc19d625c5173df360fa20a10c6040c1
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192894"
---
# Out-Printer

## SINOPSE
Envia a saída para uma impressora.

## SYNTAX

```
Out-Printer [[-Name] <String>] [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

O `Out-Printer` cmdlet envia a saída para a impressora padrão ou para uma impressora alternativa, se uma for especificada.

> [!NOTE]
> Esse cmdlet foi reintroduzido no PowerShell 7. Esse cmdlet só está disponível em sistemas Windows que dão suporte à área de trabalho do Windows.

## EXEMPLOS

### Exemplo 1 – enviar um arquivo a ser impresso na impressora padrão

Este exemplo mostra como imprimir um arquivo, mesmo que não `Out-Printer` tenha um parâmetro de **caminho** .

```powershell
Get-Content -Path ./readme.txt | Out-Printer
```

`Get-Content`Obtém o conteúdo do `readme.txt` arquivo no diretório atual e o canaliza para `Out-Printer` o, que o envia para a impressora padrão.

### Exemplo 2: imprimir uma cadeia de caracteres em uma impressora remota

Este exemplo imprime na `Hello, World` impressora de **cores PRT-6B** em Server01.

```powershell
"Hello, World" | Out-Printer -Name "\\Server01\Prt-6B Color"
```

O parâmetro **Name** seleciona uma impressora específica, em vez do padrão.

### Exemplo 3-imprimir um tópico da ajuda para a impressora padrão

Este exemplo imprime a versão completa do tópico da ajuda para `Get-CimInstance` .

```powershell
$H = Get-Help -Full Get-CimInstance
Out-Printer -InputObject $H
```

`Get-Help` Obtém a versão completa do tópico da ajuda para `Get-CimInstance` e armazena-a na `$H` variável. O parâmetro **InputObject** passa o valor de `$H` para `Out-Printer` .

## PARAMETERS

### -InputObject

Especifica os objetos a serem enviados para a impressora. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

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

### -Name

Envia a saída para a impressora especificada. O **nome** do parâmetro é opcional.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PrinterName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

Você pode canalizar qualquer objeto para `Out-Printer` .

## SAÍDAS

### Nenhum

`Out-Printer` Não retorna nenhum objeto.

## OBSERVAÇÕES

Os cmdlets que contêm o `Out` verbo não formatam objetos. Eles apenas os renderizam e os enviam para o destino de exibição especificado. Se você enviar um objeto não formatado para um `Out` cmdlet, o cmdlet o enviará a um cmdlet de formatação antes de renderizá-lo.

`Out-Printer` envia dados para a impressora, mas não emite nenhum objeto de saída para o pipeline. Se você canalizar a saída de `Out-Printer` para `Get-Member` , o `Get-Member` relatará que nenhum objeto foi especificado.

## LINKS RELACIONADOS

[Out-File](Out-File.md)

[Out-String](Out-String.md)
