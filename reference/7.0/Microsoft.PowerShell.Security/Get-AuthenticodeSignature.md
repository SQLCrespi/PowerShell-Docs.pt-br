---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-authenticodesignature?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AuthenticodeSignature
ms.openlocfilehash: 723b374d8623ff8437a27a48933057e457108eb1
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193182"
---
# Get-AuthenticodeSignature

## SINOPSE
Obtém informações sobre a assinatura Authenticode de um arquivo.

## SYNTAX

### ByPath (padrão)

```
Get-AuthenticodeSignature [-FilePath] <String[]> [<CommonParameters>]
```

### ByLiteralPath

```
Get-AuthenticodeSignature -LiteralPath <String[]> [<CommonParameters>]
```

### ByContent

```
Get-AuthenticodeSignature -SourcePathOrExtension <String[]> -Content <Byte[]> [<CommonParameters>]
```

## DESCRIPTION

O `Get-AuthenticodeSignature` cmdlet obtém informações sobre a assinatura Authenticode para um conteúdo de arquivo ou arquivo como uma matriz de bytes. Se o arquivo não estiver assinado as informações serão recuperadas, mas os campos ficarão vazios.

## EXEMPLOS

### Exemplo 1: obter a assinatura Authenticode para um arquivo

```powershell
Get-AuthenticodeSignature -FilePath "C:\Test\NewScript.ps1"
```

Este comando obtém informações sobre a assinatura Authenticode no arquivo NewScript.ps1. Ele usa o parâmetro **FilePath** para especificar o arquivo.

### Exemplo 2: obter a assinatura Authenticode para vários arquivos

```powershell
Get-AuthenticodeSignature test.ps1, test1.ps1, sign-file.ps1, makexml.ps1
```

Este comando obtém informações sobre a assinatura Authenticode para os quatro arquivos listados na linha de comando. Neste exemplo, o nome do parâmetro **FilePath** , que é opcional, é omitido.

### Exemplo 3: obter apenas assinaturas de Authenticode válidas para vários arquivos

```powershell
Get-ChildItem $PSHOME\*.* | ForEach-object {Get-AuthenticodeSignature $_} | Where-Object {$_.status -eq "Valid"}
```

Esse comando lista todos os arquivos no `$PSHOME` diretório que têm uma assinatura Authenticode válida. A `$PSHOME` variável automática contém o caminho para o diretório de instalação do PowerShell.

O comando usa o `Get-ChildItem` cmdlet para obter os arquivos no `$PSHOME` diretório. Ele usa um padrão de *.* para excluir diretórios (embora também exclua arquivos sem um ponto no nome do arquivo).

O comando usa um operador de pipeline ( `|` ) para enviar os arquivos `$PSHOME` para o `ForEach-Object` cmdlet, onde `Get-AuthenticodeSignature` é chamado para cada arquivo.

Os resultados do `Get-AuthenticodeSignature` comando são enviados para um `Where-Object` comando que seleciona apenas os objetos de assinatura com um status válido.

### Exemplo 4: obter a assinatura Authenticode para um conteúdo de arquivo especificado como matriz de bytes

```powershell
Get-AuthenticodeSignature -Content (Get-Content foo.ps1 -AsByteStream) -SourcePathorExtension ps1
```

Esse comando obtém informações sobre a assinatura Authenticode para o conteúdo de um arquivo. Neste exemplo, a extensão de arquivo é especificada junto com o conteúdo do arquivo.

## PARAMETERS

### -Conteúdo

Conteúdo de um arquivo como uma matriz de bytes para a qual a assinatura Authenticode é recuperada. Esse parâmetro deve ser usado com o parâmetro **SourcePathOrExtension** . O conteúdo do arquivo deve estar no formato Unicode (UTF-16LE).

```yaml
Type: System.Byte[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FilePath

Especifica o caminho para o arquivo a ser examinado. Caracteres curinga são permitidos, mas eles devem levar a um único arquivo. Não é necessário digitar **FilePath** na linha de comando quando você especifica um valor para esse parâmetro.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -LiteralPath

Especifica o caminho para o arquivo que está sendo examinado. Ao contrário de **FilePath** , o valor do parâmetro **LiteralPath** é usado exatamente como é digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir um caractere de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como caracteres de escape.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourcePathOrExtension

Caminho para o arquivo ou tipo de arquivo do conteúdo para o qual a assinatura Authenticode é recuperada. Esse parâmetro é usado com o **conteúdo** em que o conteúdo do arquivo é passado como uma matriz de bytes.

```yaml
Type: System.String[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém um caminho de arquivo para `Get-AuthenticodeSignature` .

## SAÍDAS

### System. Management. Automation. Signature

`Get-AuthenticodeSignature` Retorna um objeto de assinatura para cada assinatura obtida.

## OBSERVAÇÕES

Para obter informações sobre assinaturas Authenticode no PowerShell, consulte [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md).

## LINKS RELACIONADOS

[Get-ExecutionPolicy](Get-ExecutionPolicy.md)

[Set-AuthenticodeSignature](Set-AuthenticodeSignature.md)

[Set-ExecutionPolicy](Set-ExecutionPolicy.md)

[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md)
