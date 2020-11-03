---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-history?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-History
ms.openlocfilehash: baedf2be8bb3fca2223c65c33beb21f01ed84969
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193134"
---
# Invoke-History

## SINOPSE
Executa comandos do histórico de sessão.

## SYNTAX

```
Invoke-History [[-Id] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Invoke-History` cmdlet executa comandos do histórico da sessão. Você pode passar objetos que representam os comandos de Get-History para `Invoke-History` , ou pode identificar comandos no histórico atual usando seu número de **ID** . Para localizar o número de identificação de um comando, use o `Get-History` cmdlet.

O histórico de sessão é gerenciado separadamente do histórico mantido pelo módulo **PSReadLine** .
Ambos os históricos estão disponíveis em sessões em que **PSReadLine** é carregado. Esse cmdlet funciona apenas com o histórico de sessão. Para obter mais informações, consulte [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).

## EXEMPLOS

### Exemplo 1: executar o comando mais recente no histórico

Este exemplo executa o comando Last, ou mais recente, no histórico da sessão. Você pode abreviar este comando como `r` , o alias para `Invoke-History` .

```powershell
Invoke-History
```

### Exemplo 2: executar o comando que tem uma ID especificada

Este exemplo executa o comando no histórico de sessão com **Id** 132. Como o nome do parâmetro **ID** é opcional, você pode abreviar este comando como o seguinte: `Invoke-History 132` , `ihy 132` ou `r 132` .

```powershell
Invoke-History -Id 132
```

### Exemplo 3: executar o comando mais recente usando o texto do comando

Este exemplo executa o comando mais recente `Get-Process` no histórico de sessão. Quando você digita caracteres para o parâmetro **ID** , `Invoke-History` o executa o primeiro comando que ele encontra que corresponde ao padrão, começando com os comandos mais recentes.

```powershell
Invoke-History -Id get-pr
```

> [!NOTE]
> A correspondência de padrões não diferencia maiúsculas de minúsculas, mas o padrão corresponde ao início da linha.

### Exemplo 4: executar uma sequência de comandos do histórico

Este exemplo executa os comandos 16 a 24. Como você pode listar apenas um valor de **ID** , o comando usa o `ForEach-Object` cmdlet para executar o `Invoke-History` comando uma vez para cada valor de **ID** .

```powershell
16..24 | ForEach {Invoke-History -Id $_ }
```

### Exemplo 5

Este exemplo executa os sete comandos no histórico que terminam com o comando 255 (249 a 255). Ele usa o `Get-History` cmdlet para recuperar os comandos. Como você pode listar apenas um valor de **ID** , o comando usa o `ForEach-Object` cmdlet para executar o `Invoke-History` comando uma vez para cada valor de **ID** .

```powershell
Get-History -Id 255 -Count 7 | ForEach {Invoke-History -Id $_.Id}
```

## PARAMETERS

### -Id

Especifica a **ID** de um comando no histórico. Você pode digitar o número de **ID** do comando ou os primeiros caracteres do comando.

Se você digitar caracteres, `Invoke-History` o corresponderá primeiro aos comandos mais recentes. Se você omitir esse parâmetro, `Invoke-History` o executará o último comando ou o mais recente. Para localizar o número de **ID** de um comando, use o `Get-History` cmdlet.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
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

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

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

### System.String

É possível canalizar uma **ID** de histórico para esse cmdlet.

## SAÍDAS

### Nenhum

Esse cmdlet não gera nenhuma saída, mas a saída pode ser gerada pelos comandos que são `Invoke-History` executados.

## OBSERVAÇÕES

O histórico da sessão é uma lista dos comandos inseridos durante a sessão. O histórico da sessão representa a ordem de execução, o status e os horários de início e término do comando. À medida que você insere cada comando, o PowerShell o adiciona ao histórico para que você possa reutilizá-lo. Para obter mais informações sobre o histórico de sessão, consulte [about_History](About/about_History.md).

Você também pode consultar `Invoke-History` por seus aliases internos `r` e `ihy` . Para obter mais informações, consulte [about_Aliases](About/about_Aliases.md).

## LINKS RELACIONADOS

[Add-History](Add-History.md)

[Clear-History](Clear-History.md)

[Get-History](Get-History.md)
