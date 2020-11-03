---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-powershelldatafile?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PowerShellDataFile
ms.openlocfilehash: f83718f56a3c01ca59fcda697201ff4a3598b54a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193557"
---
# Import-PowerShellDataFile

## SINOPSE
Importa valores de um `.PSD1` arquivo sem invocar seu conteúdo.

## SYNTAX

### ByPath (padrão)

```
Import-PowerShellDataFile [-Path] <String[]> [<CommonParameters>]
```

### ByLiteralPath

```
Import-PowerShellDataFile [-LiteralPath] <String[]> [<CommonParameters>]
```

## DESCRIPTION

O `Import-PowerShellDataFile` cmdlet importa com segurança pares de chave-valor de Hashtables definidos em `.PSD1` um arquivo. Os valores podem ser importados usando `Invoke-Expression` o conteúdo do arquivo.
No entanto, o `Invoke-Expression` executa qualquer código contido no arquivo. Isso pode produzir resultados indesejados ou executar código não seguro. `Import-PowerShellDataFile` importa os dados sem invocar o código.

## EXEMPLOS

### Exemplo 1: recuperar valores de PSD1

Este exemplo recupera os pares chave-valor armazenados na tabela de hash mantidos dentro do `Configuration.psd1` arquivo. `Get-Content` é usado para mostrar o conteúdo do `Configuration.psd1` arquivo.

```powershell
Get-Content .\Configuration.psd1
$config = Import-PowerShellDataFile .\Configuration.psd1
$config.AllNodes
```

```Output
@{
    AllNodes = @(
        @{
            NodeName = 'DSC-01'
        }
        @{
            NodeName = 'DSC-02'
        }
    )
}

Name                           Value
----                           -----
NodeName                       DSC-01
NodeName                       DSC-02
```

## PARAMETERS

### -LiteralPath

O caminho para o arquivo que está sendo importado. Todos os caracteres no caminho são tratados como valores literais.
Os caracteres curinga não são processados.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

O caminho para o arquivo que está sendo importado. Caracteres curinga são permitidos, mas apenas o primeiro arquivo correspondente é importado.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

## SAÍDAS

### System.Collections.Hashtable

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Invoke-Expression](Invoke-Expression.md)

[Import-LocalizedData](Import-LocalizedData.md)

