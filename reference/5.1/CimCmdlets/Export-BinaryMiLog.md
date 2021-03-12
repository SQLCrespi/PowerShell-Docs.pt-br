---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/export-binarymilog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-BinaryMiLog
ms.openlocfilehash: 1d202b7bbda359f859838475eb9f37730506bd1f
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194356"
---
# Export-BinaryMiLog

## SINOPSE
Cria uma representação binária codificada de um objeto ou objetos e a armazena em um arquivo.

## SYNTAX

```
Export-BinaryMiLog [-InputObject <CimInstance>] [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION

O `Export-BinaryMILog` cmdlet cria uma representação baseada em binário de um objeto ou objetos e o armazena em um arquivo. Você pode usar o `Import-BinaryMiLog` cmdlet para recriar o objeto salvo com base no conteúdo desse arquivo.

Esse cmdlet é semelhante a `Import-Clixml` , exceto que `Export-BinaryMILog` armazena o objeto resultante em um arquivo binário codificado.

## EXEMPLOS

### Exemplo 1-criar uma representação binária de CimInstances

```powershell
Get-CimInstance Win32_Process | Export-BinaryMiLog -Path "Processes.bmil"
```

Esse comando exporta **CimInstances** para um arquivo de log mi binário especificado pelo parâmetro Path. Consulte o exemplo de Import-BinaryMiLog para ver como recriar o **CimInstances** importando esse arquivo.

## PARAMETERS

### -InputObject

Especifica a entrada para esse cmdlet. Você pode usar esse parâmetro ou é possível canalizar a entrada para esse cmdlet.

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### Microsoft. Management. Infrastructure. CimInstance

## SAÍDAS

### System.Object

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-CimInstance](get-ciminstance.md)

[Import-BinaryMiLog](import-binarymilog.md)

[Import-Clixml](../microsoft.powershell.utility/import-clixml.md)
