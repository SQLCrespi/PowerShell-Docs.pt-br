---
external help file: Microsoft.PowerShell.Archive-help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 07/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/expand-archive?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Expand-Archive
ms.openlocfilehash: a4cf8970156f524578f7c9747aef1ffbf9f3eb58
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598840"
---
# Expand-Archive

## SINOPSE
Extrai arquivos de um arquivo morto especificado (zipado).

## SYNTAX

### Caminho (padrão)

```
Expand-Archive [-Path] <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### LiteralPath

```
Expand-Archive -LiteralPath <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Expand-Archive` cmdlet extrai arquivos de um arquivo compactado especificado para uma pasta de destino especificada. Um arquivo morto permite que vários arquivos sejam empacotados e, opcionalmente, compactados em um único arquivo compactado para distribuição e armazenamento mais fáceis.

## EXEMPLOS

### Exemplo 1: extrair o conteúdo de um arquivo morto

Este exemplo extrai o conteúdo de um arquivo morto existente na pasta especificada pelo parâmetro **DestinationPath** .

```powershell
Expand-Archive -LiteralPath 'C:\Archives\Draft[v1].Zip' -DestinationPath C:\Reference
```

Neste exemplo, o parâmetro **LiteralPath** é usado porque o nome do arquivo contém caracteres que podem ser interpretados como curingas.

### Exemplo 2: extrair o conteúdo de um arquivo morto na pasta atual

Este exemplo extrai o conteúdo de um arquivo morto existente na pasta atual para a pasta especificada pelo parâmetro **DestinationPath** .

```powershell
Expand-Archive -Path Draftv2.Zip -DestinationPath C:\Reference
```

## PARAMETERS

### -DestinationPath

Por padrão, `Expand-Archive` o cria uma pasta no local atual que é do mesmo nome que o arquivo zip. O parâmetro permite que você especifique o caminho para uma pasta diferente. A pasta de destino será criada se não existir.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: A folder in the current location
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Força o comando a ser executado sem solicitar a confirmação do usuário.

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

### -LiteralPath

Especifica o caminho para um arquivo morto. Ao contrário do parâmetro **Path**, o valor de **LiteralPath** é usado exatamente como digitado. Não há suporte para caracteres curinga. Se o caminho incluir caracteres de escape, coloque cada caractere de escape entre aspas simples, para instruir o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Faz com que o cmdlet gere uma lista dos arquivos expandidos do arquivo morto.

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

### -Path

Especifica o caminho para o arquivo morto.

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

É possível canalizar uma cadeia de caracteres que contém um caminho para um arquivo morto existente.

## SAÍDAS

### System. IO. FileSystemInfo

Quando o `-PassThru` parâmetro é usado, o cmdlet gera uma lista de arquivos que foram expandidos do arquivo morto.

## OBSERVAÇÕES

A [especificação do arquivo zip](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) não especifica uma maneira padrão de codificar nomes de arquivos que contenham caracteres não ASCII. O `Compress-Archive` cmdlet usa a codificação UTF-8. Outras ferramentas de arquivo ZIP podem usar um esquema de codificação diferente. Ao extrair arquivos com nomes de arquivo não armazenados usando a codificação UTF-8, `Expand-Archive` o usa o valor bruto encontrado no arquivamento. Isso pode resultar em um nome de arquivo diferente do nome de arquivo de origem armazenado no arquivo morto.

## LINKS RELACIONADOS

[Compress-Archive](compress-archive.md)
