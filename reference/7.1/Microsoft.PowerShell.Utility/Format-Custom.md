---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-custom?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Custom
ms.openlocfilehash: c8bf4dfa9077af04e4122672a15a7c768cb49ea2
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195149"
---
# Format-Custom

## SINOPSE
Usa um modo de exibição personalizado para formatar a saída.

## SYNTAX

```
Format-Custom [[-Property] <Object[]>] [-Depth <Int32>] [-GroupBy <Object>] [-View <String>]
 [-ShowError] [-DisplayError] [-Force] [-Expand <String>] [-InputObject <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION

O `Format-Custom` cmdlet formata a saída de um comando conforme definido em uma exibição alternativa.
`Format-Custom` foi projetado para exibir modos de exibição que não são apenas tabelas ou apenas listas. Você pode usar os modos de exibição definidos no PowerShell ou pode criar seus próprios modos de exibição em um novo `format.ps1xml` arquivo e usar o `Update-FormatData` cmdlet para adicioná-los ao PowerShell.

## EXEMPLOS

### Exemplo 1: Formatar a saída com uma exibição personalizada

```powershell
Get-Command Start-Transcript | Format-Custom -View MyView
```

Esse comando formata informações sobre o `Start-Transcript` cmdlet no formato definido pelo modo de exibição MyView, uma exibição personalizada criada pelo usuário. Para executar esse comando com êxito, você deve primeiro criar um novo arquivo PS1XML, definir o modo de exibição **MyView** e, em seguida, usar o `Update-FormatData` comando para adicionar o arquivo PS1XML ao PowerShell.

### Exemplo 2: Formatar a saída com a exibição padrão

```powershell
Get-Process Winlogon | Format-Custom
```

Esse comando formata informações sobre o processo **Winlogon** em uma exibição personalizada alternativa.
Como o comando não usa o parâmetro **View** , o `Format-Custom` usa uma exibição personalizada padrão para formatar os dados.

### Exemplo 3: Solucionando problemas de erros de formato

Os exemplos a seguir mostram os resultados da adição dos parâmetros **DisplayError** ou **exerror** com uma expressão.

```powershell
PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -DisplayError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  = #ERR
}


PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -ShowError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  =
}

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 8:01:04 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## PARAMETERS

### -Profundidade

Especifica o número de colunas a exibir.

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

Exibe eventuais erros na linha de comando. Esse parâmetro raramente é usado, mas pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-Custom` comando e as expressões não parecerem estar funcionando.

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

Formata o objeto da coleção, bem como os objetos presentes na coleção. Esse parâmetro é projetado para formatar objetos que dão suporte à interface **System. Collections. ICollection** . O valor padrão é **EnumOnly** .

Os valores válidos são:

- EnumOnly: exibe as propriedades dos objetos na coleção.
- CoreOnly: exibe as propriedades do objeto de coleção.
- Ambos: exibe as propriedades do objeto de coleção e os objetos na coleção.

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

Faz com que o cmdlet exiba todas as informações de erro. Use com os parâmetros **DisplayError** ou **exerror** . Por padrão, quando um objeto de erro é gravado para os fluxos de erro ou de exibição, apenas algumas das informações de erro são exibidas.

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

Se você omitir esse parâmetro, as propriedades a serem exibidas dependerão do objeto sendo exibido. A **Propriedade** nome do parâmetro é opcional. Você não pode usar os parâmetros **Property** e **View** no mesmo comando.

O valor do parâmetro **Property** pode ser uma nova propriedade calculada. A propriedade calculada pode ser um bloco de script ou uma tabela de hash. Os pares de chave-valor válidos são:

- Expressão- `<string>` ou `<script block>`
- Detalhado `<int32>`

Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Erro

Envia erros por meio do pipeline. Esse parâmetro raramente é usado, mas pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-Custom` comando e as expressões não parecerem estar funcionando.

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

Especifica o nome de um formato ou exibição alternativo. Se você omitir esse parâmetro, o `Format-Custom` usará uma exibição personalizada padrão. Você não pode usar os parâmetros **Property** e **View** no mesmo comando.

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

Você pode canalizar qualquer objeto para `Format-Custom` .

## SAÍDAS

### Microsoft. PowerShell. Commands. Internal. Format

`Format-Custom` Retorna os objetos de formato que representam a exibição.

## OBSERVAÇÕES

`Format-Custom` foi projetado para exibir modos de exibição que não são apenas tabelas ou apenas listas. Para exibir uma exibição de tabela alternativa, use `Format-Table` . Para exibir uma exibição de lista alternativa, use `Format-List` .

Você também pode consultar `Format-Custom` por seu alias interno, `fc` . Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

O parâmetro **GroupBy** pressupõe que os objetos são classificados. Antes `Format-Custom` de usar o para agrupar os objetos, use `Sort-Object` para classificá-los.

## LINKS RELACIONADOS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[Format-Hex](Format-Hex.md)

[Format-List](Format-List.md)

[Format-Table](Format-Table.md)

[Format-Wide](Format-Wide.md)

[Get-Process](../Microsoft.PowerShell.Management/Get-Process.md)
