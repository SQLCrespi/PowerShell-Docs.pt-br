---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/new-filecatalog?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-FileCatalog
ms.openlocfilehash: aef0f6e63be07f0568927f8e65df675ff4f9eba7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192861"
---
# New-FileCatalog

## SINOPSE
`New-FileCatalog` Cria um arquivo de catálogo de hashes de arquivo que pode ser usado para validar a autenticidade de um arquivo.

## SYNTAX

```
New-FileCatalog [-CatalogVersion <Int32>] [-CatalogFilePath] <String> [[-Path] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`New-FileCatalog` Cria um [arquivo de catálogo do Windows](/windows-hardware/drivers/install/catalog-files) para um conjunto de pastas e arquivos.
Esse arquivo de catálogo contém hashes para todos os arquivos nos caminhos fornecidos.
Os usuários podem então distribuir o catálogo com seus arquivos para que os usuários possam validar se alguma alteração foi feita nas pastas desde a hora de criação do catálogo.

Há suporte para as versões 1 e 2 do catálogo. A versão 1 usa o algoritmo de hash SHA1 (preterido) para criar hashes de arquivo, e a versão 2 usa SHA256.
Não há suporte para a versão 2 do catálogo no Windows Server 2008 R2 ou no Windows 7.
Você deve usar a versão 2 do catálogo no Windows 8, no Windows Server 2012 e nos sistemas operacionais posteriores.

## EXEMPLOS

### Exemplo 1: criar um catálogo de arquivos para `Microsoft.PowerShell.Utility`

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         11/2/2018 11:58 AM            950 Microsoft.PowerShell.Utility.cat
```

## PARAMETERS

### -CatalogFilePath

Um caminho para um arquivo ou pasta onde o arquivo de catálogo (. cat) deve ser colocado.
Se um caminho de pasta for especificado, o nome de arquivo padrão `catalog.cat` será usado.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -CatalogVersion

Aceita `1.0` ou `2.0` como valores possíveis para especificar a versão do catálogo.
`1.0` deve ser usado evitado sempre que possível, pois ele usa o algoritmo de hash SHA-1 inseguro, enquanto `2.0` usa o algoritmo Secure SHA-256 no entanto, `1.0` é o único algoritmo com suporte no Windows 7 e no Server 2008r2.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -Path

Aceita um caminho ou uma matriz de caminhos para arquivos ou pastas que devem ser incluídos no arquivo de catálogo.
Se uma pasta for especificada, todos os arquivos na pasta também serão incluídos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

O pipeline usa uma cadeia de caracteres que é usada como o nome de arquivo do catálogo.

## SAÍDAS

### System. IO. FileInfo

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Test-FileCatalog](Test-FileCatalog.md)

[PowerShellGet](/powerShell/module/powershellget)
