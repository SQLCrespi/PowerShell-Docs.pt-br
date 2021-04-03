---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Alias
ms.openlocfilehash: f3f5f58060fb3ad0b5102eb46fe07859b426ed9c
ms.sourcegitcommit: c91f79576bc54e162bcc7adf78026417b2776687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2021
ms.locfileid: "106273889"
---
# New-Alias

## Sinopse
Cria um novo alias.

## Sintaxe

```
New-Alias [-Name] <String> [-Value] <String> [-Description <String>] [-Option <ScopedItemOptions>] [-PassThru]
 [-Scope <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Descrição

O `New-Alias` cmdlet cria um novo alias na sessão atual do PowerShell. Os aliases criados por meio `New-Alias` do não são salvos depois que você sai da sessão ou fecha o PowerShell.
Você pode usar o `Export-Alias` cmdlet para salvar suas informações de alias em um arquivo. Posteriormente, você pode usar `Import-Alias` para recuperar as informações de alias salvas.

## Exemplos

### Exemplo 1: criar um alias para um cmdlet

```
New-Alias -Name "List" Get-ChildItem
```

Este comando cria um alias chamado List para representar o cmdlet Get-ChildItem.

### Exemplo 2: criar um alias somente leitura para um cmdlet

```
New-Alias -Name "C" -Value Get-ChildItem -Description "quick gci alias" -Option ReadOnly
Get-Alias -Name "C" | Format-List *
```

Este comando cria um alias chamado `C` para representar o `Get-ChildItem` cmdlet. Ele cria uma descrição, alias WMI rápido, para o alias e o torna somente leitura. A última linha do comando usa `Get-Alias` para obter o novo alias e o canaliza para Format-List para exibir todas as informações sobre ele.

## Parâmetros

### -Description

Especifica uma descrição do alias. Você pode digitar qualquer cadeia de caracteres. Se a descrição incluir espaços, coloque-a entre aspas.

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

Indica que o cmdlet funciona como `Set-Alias` se o alias chamado já existir.

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

### -Name

Especifica o novo alias. Você pode usar qualquer caractere alfanumérico em um alias, mas o primeiro caractere não pode ser um número.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Opção

Especifica o valor da propriedade **Options** do alias.
Os valores válidos são:

- `None`: O alias não tem restrições (valor padrão)
- `ReadOnly`: O alias pode ser excluído, mas não pode ser alterado com exceção do uso do parâmetro **Force**
- `Constant`: O alias não pode ser excluído ou alterado
- `Private`: O alias está disponível somente no escopo atual
- `AllScope`: O alias é copiado para todos os novos escopos criados
- `Unspecified`: A opção não foi especificada

Esses valores são definidos como uma enumeração baseada em sinalizador. Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro. Os valores podem ser passados para o parâmetro de **opção** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores. O cmdlet combinará os valores usando uma operação binary ou. Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.

Para ver a propriedade **Options** de todos os aliases na sessão, digite `Get-Alias | Format-Table -Property Name, Options -AutoSize` .

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: [System.Management.Automation.ScopedItemOptions]::None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto que representa o item com que você está trabalhando. Por padrão, este cmdlet não gera saída.

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

### -Escopo

Especifica o escopo do novo alias. Os valores aceitáveis para esse parâmetro são:

- `Global`
- `Local`
- `Script`
- Um número relativo ao escopo atual (0 até o número de escopos, em que `0` é o escopo atual e `1` é seu pai).

`Local` é o padrão. Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

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

### -Value

Especifica o nome do elemento de comando ou de cmdlet que está recebendo o alias.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## Entradas

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## Saídas

### Nenhum ou System. Management. Automation. AliasInfo

Quando você usa o parâmetro **PassThru** , o `New-Alias` gera um objeto **System. Management. Automation. AliasInfo** que representa o novo alias. Caso contrário, este cmdlet não gera nenhuma saída.

## Observações

- Para criar um novo alias, use `Set-Alias` ou `New-Alias` . Para alterar um alias, use `Set-Alias` . Para excluir um alias, use `Remove-Item` .

## Links Relacionados

[Export-Alias](Export-Alias.md)

[Get-Alias](Get-Alias.md)

[Import-Alias](Import-Alias.md)

[Set-Alias](Set-Alias.md)
