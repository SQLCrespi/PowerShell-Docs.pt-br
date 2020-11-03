---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-wide?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Wide
ms.openlocfilehash: f26fc996b7fd029ed5994432080e51a1d83ec20e
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195175"
---
# Format-Wide

## SINOPSE
Formata objetos como uma tabela ampla que exibe apenas uma propriedade de cada objeto.

## SYNTAX

```
Format-Wide [[-Property] <Object>] [-AutoSize] [-Column <int>] [-GroupBy <Object>] [-View <string>]
  [-ShowError] [-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>]
  [<CommonParameters>]
```

## DESCRIPTION

O `Format-Wide` cmdlet formata objetos como uma tabela larga que exibe apenas uma propriedade de cada objeto. Você pode usar o parâmetro **Property** para determinar qual propriedade é exibida.

## EXEMPLOS

### Exemplo 1: Formatar nomes de arquivos no diretório atual

Esse comando exibe os nomes dos arquivos no diretório atual em três colunas na tela.

```powershell
Get-ChildItem | Format-Wide -Column 3
```

O cmdlet Get-ChildItem obtém os objetos que representam cada arquivo no diretório. O operador de pipeline (|) passa os objetos de arquivo por meio do pipeline para `Format-Wide` , que os formata para saída. O parâmetro **Column** especifica o número de colunas.

### Exemplo 2: Formatar nomes de chaves do registro

Esse comando exibe os nomes das chaves do registro na chave HKEY_CURRENT_USER\Software\Microsoft.

```powershell
Get-ChildItem HKCU:\software\microsoft | Format-Wide -Property pschildname -AutoSize
```

O cmdlet Get-ChildItem obtém os objetos que representam as chaves. O caminho é especificado como HKCU:, uma das unidades expostas pelo provedor de registro do PowerShell, seguido pelo caminho da chave. O operador de pipeline (|) passa os objetos de chave do registro por meio do pipeline para `Format-Wide` , que os formata para saída. O parâmetro **Property** especifica o nome da propriedade e o parâmetro **AutoSize** ajusta as colunas para facilitar a leitura.

### Exemplo 3: Solucionando problemas de erros de formato

Os exemplos a seguir mostram os resultados da adição dos parâmetros **DisplayError** ou **exerror** com uma expressão.

```powershell
PS /> Get-Date | Format-Wide { $_ / $null } -DisplayError


#ERR

PS /> Get-Date | Format-Wide { $_ / $null } -ShowError


Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 8:18:01 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## PARAMETERS

### -AutoSize

Ajusta o tamanho da coluna e o número de colunas com base na largura dos dados. Por padrão, o número de colunas e seu tamanho são determinados pelo modo de exibição. Você não pode usar os parâmetros **AutoSize** e **Column** no mesmo comando.

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

### -Coluna

Especifica o número de colunas a exibir. Você não pode usar os parâmetros **AutoSize** e **Column** no mesmo comando.

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

### -DisplayError

Exibe eventuais erros na linha de comando. Esse parâmetro raramente é usado, mas pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-Wide` comando e as expressões não parecerem estar funcionando.

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

### -Expandir

Formata o objeto da coleção, bem como os objetos presentes na coleção. Este parâmetro é projetado para formatar objetos que dão suporte à interface ICollection (System. Collections). O valor padrão é **EnumOnly** .

Os valores válidos são:

- EnumOnly: exibe as propriedades dos objetos na coleção.
- CoreOnly: exibe as propriedades do objeto de coleção.
- Ambos: exibe as propriedades do objeto de coleção e as propriedades de objetos na coleção.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: EnumOnly
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Indica que esse cmdlet substitui as restrições que impedem o sucesso do comando, apenas para que as alterações não comprometam a segurança. Por exemplo, o **Force** substituirá o atributo somente leitura ou criar diretórios para concluir um caminho de arquivo, mas não tentará alterar permissões de arquivo.

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

### -GroupBy

Formata a saída em grupos com base em uma propriedade ou valor compartilhado. Insira uma expressão ou uma propriedade da saída.

O valor do parâmetro **GroupBy** pode ser uma nova propriedade calculada. A propriedade calculada pode ser um bloco de script ou uma tabela de hash. Os pares de chave-valor válidos são:

- Nome (ou rótulo)- `<string>`
- Expressão- `<string>` ou `<script block>`
- FormatString `<string>`

Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica os objetos a serem formatados. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Propriedade

Especifica as propriedades do objeto que aparecem na exibição e a ordem em que aparecem.
Caracteres curinga são permitidos.

Se você omitir esse parâmetro, as propriedades a serem exibidas dependerão do objeto sendo exibido. O nome do parâmetro "Property" é opcional. Você não pode usar os parâmetros **Property** e **View** no mesmo comando.

O valor do parâmetro **Property** pode ser uma nova propriedade calculada. A propriedade calculada pode ser um bloco de script ou uma tabela de hash. Os pares de chave-valor válidos são:

- Expressão- `<string>` ou `<script block>`
- FormatString `<string>`

Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Erro

Envia erros por meio do pipeline. Esse parâmetro raramente é usado, mas pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-Wide` comando e as expressões não parecerem estar funcionando.

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

### -Exibição

Especifica o nome de um formato ou exibição de tabela alternativa. Você não pode usar os parâmetros **Property** e **View** no mesmo comando.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

Você pode canalizar qualquer objeto para `Format-Wide` .

## SAÍDAS

### Microsoft. PowerShell. Commands. Internal. Format

`Format-Wide` retorna objetos de formato que representam a tabela.

## OBSERVAÇÕES

Você também pode consultar `Format-Wide` por seu alias interno, `fw` . Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

O parâmetro **GroupBy** pressupõe que os objetos são classificados. Use `Sort-Object` antes `Format-Custom` de usar o para agrupar os objetos.

O parâmetro **View** permite especificar um formato alternativo para a tabela. Você pode usar as exibições definidas nos `*.format.PS1XML` arquivos no diretório do PowerShell ou pode criar suas próprias exibições em novos arquivos ps1xml e usar o `Update-FormatData` cmdlet para incluí-las no PowerShell.

A exibição alternativa para o parâmetro de **exibição** deve usar o formato de tabela; caso contrário, o comando falhará. Se a exibição alternativa for uma lista, use `Format-List` . Se o modo de exibição alternativo não é uma lista nem uma tabela, use o Format-Custom.

## LINKS RELACIONADOS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[Format-Custom](Format-Custom.md)

[Format-Hex](Format-Hex.md)

[Format-List](Format-List.md)

[Format-Table](Format-Table.md)
