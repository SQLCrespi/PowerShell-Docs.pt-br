---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: 2885b2624f8334e8699e0baea5fc41b3f025fe2a
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "93195342"
---
# Get-Clipboard

## SINOPSE
Obtém a entrada da área de transferência atual do Windows.

## SYNTAX

```
Get-Clipboard [-Format <ClipboardFormat>] [-TextFormatType <TextDataFormat>] [-Raw] [<CommonParameters>]
```

## DESCRIPTION

O `Get-Clipboard` cmdlet obtém a entrada da área de transferência atual do Windows. Várias linhas de texto são retornadas como uma matriz de cadeias de caracteres semelhantes a `Get-Content` .

## EXEMPLOS

### Exemplo 1: obter o conteúdo da área de transferência e exibi-lo para a linha de comando

Neste exemplo, clicamos com o botão direito do mouse em uma imagem em um navegador e escolhemos a ação de **cópia** . O comando a seguir exibe o link, como uma URL, da imagem que é armazenada na área de transferência.

```powershell
Get-Clipboard
```

```Output
https://en.wikipedia.org/wiki/PowerShell
```

### Exemplo 2: obter o conteúdo da área de transferência em um formato específico

Neste exemplo, copiamos arquivos para a área de transferência no Windows Explorerby selecionando-os e pressionando <kbd>Ctrl-C</kbd>. Usando o comando a seguir, você pode acessar o conteúdo da área de transferência como uma lista de arquivos:

```powershell
Get-Clipboard -Format FileDropList
```

```Output
    Directory: C:\Git\PS-Docs\PowerShell-Docs\wmf

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/7/2019   1:11 PM          10010 TOC.yml
-a----       11/18/2016  10:10 AM             53 md.style
-a----         5/6/2019   9:32 AM           4177 overview.md
-a----        6/28/2018   2:28 PM            345 README.md
```

## PARAMETERS

### -Formato

Especifica o tipo, ou formato, da área de transferência. Os valores aceitáveis para esse parâmetro são:

- Texto
- FileDropList
- Imagem
- Áudio

```yaml
Type: Microsoft.PowerShell.Commands.ClipboardFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, FileDropList, Image, Audio

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RAW

Obtém todo o conteúdo da área de transferência. O texto multilinha é retornado como uma única cadeia de caracteres de várias linhas em vez de uma matriz de cadeias de caracteres.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Textformatype

Especifica o tipo de formato de dados de texto da área de transferência. Os valores aceitáveis para esse parâmetro são:

- Texto
- UnicodeText
- RTF
- Html
- CommaSeparatedValue

```yaml
Type: System.Windows.Forms.TextDataFormat
Parameter Sets: (All)
Aliases:
Accepted values: Text, UnicodeText, Rtf, Html, CommaSeparatedValue

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

### System. String, System. IO. FileInfo, System. IO. Stream, System. Drawing. Image

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Set-Clipboard](Set-Clipboard.md)
