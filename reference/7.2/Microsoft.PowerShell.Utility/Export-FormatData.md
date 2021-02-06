---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-formatdata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-FormatData
ms.openlocfilehash: d42b108d469ed8989628a6c0b4214af4afc0db00
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603328"
---
# Export-FormatData

## SINOPSE
Salva os dados de formatação da sessão atual em um arquivo de formatação.

## SYNTAX

### ByPath (padrão)

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -Path <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

### ByLiteralPath

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -LiteralPath <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

## DESCRIPTION

O `Export-FormatData` cmdlet cria arquivos de formatação do PowerShell (format.ps1XML) dos objetos de formatação na sessão atual. Ele usa os objetos **ExtendedTypeDefinition** que `Get-FormatData` retorna e salva-os em um arquivo em formato XML.

O PowerShell usa os dados em arquivos de formatação (format.ps1XML) para gerar a exibição padrão de objetos do Microsoft .NET Framework na sessão. Você pode exibir e editar os arquivos de formatação e usar o cmdlet Update-FormatData para adicionar os dados de formatação a uma sessão.

Para obter mais informações sobre como formatar arquivos no PowerShell, consulte [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).

## EXEMPLOS

### Exemplo 1: exportar dados de formato de sessão

```powershell
Get-FormatData -TypeName "*" | Export-FormatData -Path "allformat.ps1xml" -IncludeScriptBlock
```

Este comando exporta todos os dados de formato presentes na sessão para o arquivo AllFormat.ps1xml.

O comando usa o `Get-FormatData` cmdlet para obter os dados de formato na sessão. Um valor de `*` (All) para o parâmetro **TypeName** direciona o cmdlet para obter todos os dados na sessão.

O comando usa um operador de pipeline ( `|` ) para enviar os dados de formato do `Get-FormatData` comando para o `Export-FormatData` cmdlet, que exporta os dados de formato para o arquivo de AllFormat.ps1.

O `Export-FormatData` comando usa o parâmetro **IncludeScriptBlock** para incluir blocos de script no formato de dados no arquivo.

### Exemplo 2: exportar dados de formato para um tipo

```powershell
$F = Get-FormatData -TypeName "helpinfoshort"
Export-FormatData -InputObject $F -Path "c:\test\help.format.ps1xml" -IncludeScriptBlock
```

Esses comandos exportam os dados de formato para o tipo **HelpInfoShort** para o arquivo XML Help.format.ps1.

O primeiro comando usa o `Get-FormatData` cmdlet para obter os dados de formato para o tipo **HelpInfoShort** e o salva na `$F` variável.

O segundo comando usa o parâmetro **InputObject** do `Export-FormatData` cmdlet para inserir os dados de formato salvos na `$F` variável. Ele também usa o parâmetro **IncludeScriptBlock** para incluir blocos de script na saída.

### Exemplo 3: exportar dados de formato sem um bloco de script

```powershell
Get-FormatData -TypeName "System.Diagnostics.Process" | Export-FormatData -Path process.format.ps1xml
Update-FormatData -PrependPath ".\process.format.ps1xml"
Get-Process p*
```

```Output
Handles  NPM(K)  PM(K)  WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------  -----  ----- -----   ------    -- -----------
323                                       5600 powershell
336                                       3900 powershell_ise
138                                       4076 PresentationFontCache
```

Este exemplo mostra o efeito de omitir o parâmetro **IncludeScriptBlock** de um `Export-FormatData` comando.

O primeiro comando usa o `Get-FormatData` cmdlet para obter os dados de formato para o objeto **System. Diagnostics. Process** que o cmdlet Get-Process retorna. O comando usa um operador de pipeline ( `|` ) para enviar os dados de formatação para o `Export-FormatData` cmdlet, que exporta para o arquivo XML Process.format.ps1no diretório atual.

Nesse caso, o `Export-FormatData` comando não usa o parâmetro **IncludeScriptBlock** .

O segundo comando usa o `Update-FormatData` cmdlet para adicionar o Process.format.ps1arquivo XML à sessão atual. O comando usa o parâmetro **PrependPath** para garantir que os dados de formatação para objetos de processo no arquivo xml de Process.format.ps1sejam encontrados antes dos dados de formatação padrão para objetos de processo.

O terceiro comando mostra os efeitos dessa alteração. O comando usa o `Get-Process` cmdlet para obter processos com nomes que começam com P. A saída mostra que os valores de propriedade que são calculados usando blocos de script estão ausentes na exibição.

## PARAMETERS

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

### -IncludeScriptBlock

Indica se os blocos de script nos dados de formato são exportados.

Já que os blocos de script contêm código e podem ser usados de maneira mal intencionada, eles não são exportados por padrão.

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

### -InputObject

Especifica os objetos de dados de formato a serem exportados. Insira uma variável que contém os objetos ou um comando que obtém os objetos, como um `Get-FormatData` comando. Você também pode canalizar os objetos de `Get-FormatData` para `Export-FormatData` .

```yaml
Type: System.Management.Automation.ExtendedTypeDefinition[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Especifica um local para o arquivo de saída. Ao contrário do parâmetro **Path**, o valor de **LiteralPath** é usado exatamente como digitado. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-o entre aspas simples. Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoClobber

Indica que o cmdlet não substitui os arquivos existentes. Por padrão, `Export-FormatData` o substitui arquivos sem aviso, a menos que o arquivo tenha o atributo somente leitura.

Para direcionar `Export-FormatData` para substituir arquivos somente leitura, use o parâmetro **Force** .

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

### -Path

Especifica um local para o arquivo de saída.
Insira um caminho (opcional) e um nome de arquivo com uma extensão de nome de arquivo format.ps1xml.
Se você omitir o caminho, o `Export-FormatData` criará o arquivo no diretório atual.

Se você usar uma extensão de nome de arquivo diferente de. ps1xml, o `Update-FormatData` cmdlet não reconhecerá o arquivo.

Se você especificar um arquivo existente, o `Export-FormatData` substituirá o arquivo sem aviso, a menos que o arquivo tenha o atributo somente leitura. Para substituir um arquivo somente leitura, use o parâmetro **Force** . Para impedir que arquivos sejam substituídos, use o parâmetro **NoClobber** .

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: FilePath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. ExtendedTypeDefinition

Você pode canalizar objetos **ExtendedTypeDefinition** de `Get-FormatData` para `Export-FormatData` .

## SAÍDAS

### Nenhum

`Export-FormatData` Não retorna nenhum objeto.
Ele gera um arquivo e o salva-o no caminho especificado.

## OBSERVAÇÕES

- Para usar qualquer arquivo de formatação, incluindo um arquivo de formatação exportado, a diretriz de execução para a sessão deve permitir a execução de scripts e de arquivos de configuração. Para obter mais informações, consulte [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).

## LINKS RELACIONADOS

[Get-FormatData](Get-FormatData.md)

[Update-FormatData](Update-FormatData.md)
