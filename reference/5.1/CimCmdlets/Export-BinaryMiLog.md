---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/export-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-BinaryMiLog
ms.openlocfilehash: cf03ad884121c6cf8cf65cdb791cbdc4e587c3b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193430"
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
