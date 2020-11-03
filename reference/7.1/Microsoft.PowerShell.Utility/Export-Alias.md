---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-alias?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Alias
ms.openlocfilehash: 1ea81eb6875fa01d12899dffb4f99cbf910c14c9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194275"
---
# Export-Alias

## SINOPSE
Exporta as informações sobre aliases definidos atualmente para um arquivo.

## SYNTAX

### ByPath (padrão)

```
Export-Alias [-Path] <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append] [-Force]
 [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Export-Alias -LiteralPath <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append]
 [-Force] [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Export-Alias` cmdlet exporta os aliases na sessão atual para um arquivo.
Se o arquivo de saída não existe, o cmdlet o cria.

`Export-Alias` pode exportar os aliases em um escopo específico ou em todos os escopos, ele pode gerar os dados no formato CSV ou como uma série de comandos Set-Alias que você pode adicionar a uma sessão ou a um perfil do PowerShell.

## EXEMPLOS

### Exemplo 1: exportar um alias

```powershell
Export-Alias -Path "alias.csv"
```

Este comando exporta as informações atuais de alias em um arquivo chamado Alias.csv no diretório atual.

### Exemplo 2: exportar um alias, a menos que o arquivo de exportação já exista

```powershell
Export-Alias -Path "alias.csv" -NoClobber
```

Esse comando exporta os aliases na sessão atual para um arquivo Alias.csv.

Como o parâmetro **NoClobber** é especificado, o comando falhará se um arquivo de Alias.csv já existir no diretório atual.

### Exemplo 3: acrescentar aliases a um arquivo

```powershell
Export-Alias -Path "alias.csv" -Append -Description "Appended Aliases" -Force
```

Este comando anexa os aliases na sessão atual ao arquivo Alias.csv.

O comando usa o parâmetro **Description** para adicionar uma descrição aos comentários na parte superior do arquivo.

O comando também usa o parâmetro **Force** para substituir todos os arquivos de Alias.csv existentes, mesmo que eles tenham o atributo somente leitura.

### Exemplo 4: exportar aliases como um script

```powershell
Export-Alias -Path "alias.ps1" -As Script
Add-Content -Path $Profile -Value (Get-Content alias.ps1)
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -FilePath .\alias.ps1
```

Este exemplo mostra como usar o formato de arquivo de script que `Export-Alias` gera.

O primeiro comando exporta os aliases da sessão para o arquivo Alias.ps1.
Ele **usa o parâmetro as com** um valor de script para gerar um arquivo que contém um comando Set-Alias para cada alias.

O segundo comando adiciona os alias no arquivo Alias.ps1 ao perfil CurrentUser-CurrentHost.
O caminho para o perfil é salvo na `$Profile` variável.
O comando usa o `Get-Content` cmdlet para obter os aliases do arquivo de Alias.ps1 e o `Add-Content` cmdlet para adicioná-los ao perfil.
Para obter mais informações, consulte about_Profiles.

O terceiro e o quarto comandos adicionam os aliases no arquivo de Alias.ps1 a uma sessão remota no computador Server01.
O terceiro comando usa o `New-PSSession` cmdlet para criar a sessão.
O quarto comando usa o parâmetro **FilePath** do `Invoke-Command` cmdlet para executar o arquivo de Alias.ps1 na nova sessão.

## PARAMETERS

### -Acrescentar

Indica que esse cmdlet acrescenta a saída ao arquivo especificado, em vez de substituir o conteúdo existente desse arquivo.

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

### -Como

Especifica o formato de saída.
CSV é o padrão.
Os valores aceitáveis para esse parâmetro são:

- CSV.
Formato de valores separados por vírgulas (CSV).
- Script.
Cria um `Set-Alias` comando para cada alias exportado.
Se você nomear o arquivo de saída com uma extensão de nome de arquivo .ps1, poderá executá-lo como um script para adicionar os aliases a qualquer sessão.

```yaml
Type: Microsoft.PowerShell.Commands.ExportAliasFormat
Parameter Sets: (All)
Aliases:
Accepted values: Csv, Script

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

Especifica a descrição do arquivo exportado.
A descrição aparecerá como um comentário na parte superior do arquivo, após as informações de cabeçalho.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Força o comando a ser executado sem solicitar a confirmação do usuário.

Substitui o arquivo de saída, mesmo se o atributo somente leitura estiver definido no arquivo.

Por padrão, `Export-Alias` o substitui arquivos sem aviso, a menos que o atributo somente leitura ou oculto esteja definido ou o parâmetro **NoClobber** seja usado no comando.
O parâmetro **NoClobber** tem precedência sobre o parâmetro **Force** quando ambos são usados em um comando.

O parâmetro **Force** não pode forçar `Export-Alias` a substituição de arquivos pelo atributo Hidden.

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

Especifica o caminho para o arquivo de saída.
Ao contrário de **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado.
Nenhum caractere é interpretado como caractere curinga.
Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.
Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Especifica os nomes como uma matriz dos aliases a serem exportados.
Caracteres curinga são permitidos.

Por padrão, o `Export-Alias` exporta todos os aliases na sessão ou no escopo.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -NoClobber

Indica que esse cmdlet impede `Export-Alias` a substituição de todos os arquivos, mesmo se o parâmetro **Force** for usado no comando.

Se o parâmetro **NoClobber** for omitido, o `Export-Alias` substituirá um arquivo existente sem aviso, a menos que o atributo somente leitura esteja definido no arquivo.
*NoClobber* tem precedência sobre o parâmetro **Force** , que permite `Export-Alias` substituir um arquivo pelo atributo somente leitura.

*NoClobber* não impede que o parâmetro **Append** adicione conteúdo a um arquivo existente.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto que representa o item com que você está trabalhando.
Por padrão, este cmdlet não gera saída.

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

Especifica o caminho para o arquivo de saída.
Caracteres curinga são permitidos, mas o valor do caminho resultante deve ser resolvido para um único nome de arquivo.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Escopo

Especifica o escopo do qual os aliases devem ser exportados.
Os valores aceitáveis para esse parâmetro são:

- Global
- Local
- script
- Um número relativo ao escopo atual (0 até o número de escopos em que 0 é o escopo atual e 1 é seu pai)

O valor padrão é Local.
Para obter mais informações, consulte about_Scopes.

```yaml
Type: System.String
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

### nenhuma.

Não é possível transferir objetos para esse cmdlet.

## SAÍDAS

### Nenhum ou System. Management. Automation. AliasInfo

Quando você usa o parâmetro **PassThru** , `Export-Alias` retorna um objeto **System. Management. Automation. AliasInfo** que representa o alias.
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

* Somente é possível usar o Export-Alias para exportar aliases para um arquivo.

## LINKS RELACIONADOS

[Get-Alias](Get-Alias.md)

[Import-Alias](Import-Alias.md)

[New-Alias](New-Alias.md)

[Set-Alias](Set-Alias.md)

