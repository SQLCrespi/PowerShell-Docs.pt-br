---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/import-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-BinaryMiLog
ms.openlocfilehash: 646f3e0990ce451300a28ca0de58576c70c55a9b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597191"
---
# Import-BinaryMiLog

## SINOPSE
Usado para recriar os objetos salvos com base no conteúdo de um arquivo de exportação.

## SYNTAX

```
Import-BinaryMiLog [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION

Use este cmdlet para recriar objetos salvos com base no conteúdo de um arquivo de exportação criado pelo `Export-BinaryMILog` . Esse cmdlet é semelhante a `Import-Clixml` , exceto que `Export-BinaryMILog` armazena o objeto resultante em um arquivo binário codificado.

## EXEMPLOS

### Exemplo 1-restaurar objetos exportados para um arquivo

```powershell
Import-BinaryMiLog -Path "Processes.bmil"
```

## PARAMETERS

### -Path

Especifica o caminho do arquivo no qual armazenar a representação binária do objeto. O parâmetro **path** dá suporte a curingas e caminhos relativos. Esse cmdlet gera um erro se o caminho for resolvido para mais de um arquivo.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

## SAÍDAS

### System.Object

## OBSERVAÇÕES

## LINKS RELACIONADOS
