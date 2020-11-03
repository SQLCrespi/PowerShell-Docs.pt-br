---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-alias?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Alias
ms.openlocfilehash: b004cae919c32078d7c2d79174637a0fa4130ab1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194688"
---
# New-Alias

## SINOPSE
Cria um novo alias.

## SYNTAX

```
New-Alias [-Name] <String> [-Value] <String> [-Description <String>] [-Option <ScopedItemOptions>] [-PassThru]
 [-Scope <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **New-Alias** cria um novo alias na sessão atual do PowerShell.
Os aliases criados com o uso **de New-Alias** não são salvos depois que você sai da sessão ou fecha o PowerShell.
Você pode usar o cmdlet Export-Alias para salvar as informações de alias em um arquivo.
Posteriormente, você poderá usar **Import-Alias** para recuperar as informações de alias salvas.

## EXEMPLOS

### Exemplo 1: criar um alias para um cmdlet

```
PS C:\> New-Alias -Name "List" Get-ChildItem
```

Este comando cria um alias chamado List para representar o cmdlet Get-ChildItem.

### Exemplo 2: criar um alias somente leitura para um cmdlet

```
PS C:\> New-Alias -Name "W" -Value Get-WmiObject -Description "quick wmi alias" -Option ReadOnly
PS C:\> Get-Alias -Name "W" | Format-List *
```

Esse comando cria um alias chamado W para representar o cmdlet Get-WmiObject.
Ele cria uma descrição, alias WMI rápido, para o alias e o torna somente leitura.
A última linha do comando usa o Get-Alias para obter o novo alias e o redireciona para Format-List para exibir todas as informações sobre ele.

## PARAMETERS

### -Description

Especifica uma descrição do alias.
Você pode digitar qualquer cadeia de caracteres.
Se a descrição incluir espaços, coloque-a entre aspas.

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

Indica que o cmdlet funciona como Set-Alias se o alias chamado já existe.

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

Especifica o novo alias.
Você pode usar qualquer caractere alfanumérico em um alias, mas o primeiro caractere não pode ser um número.

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

- Nenhum: o alias não tem restrições (valor padrão)
- ReadOnly: o alias pode ser excluído, mas não pode ser alterado com exceção do uso do parâmetro **Force**
- Constante: o alias não pode ser excluído ou alterado
- Particular: o alias está disponível somente no escopo atual
- Escopo: o alias é copiado para todos os novos escopos criados
- Não especificado: a opção não é especificada

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

### -Escopo

Especifica o escopo do novo alias.
Os valores aceitáveis para esse parâmetro são:

- Global
- Local
- script
- Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai).

Local é o padrão.
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

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Nenhum ou System. Management. Automation. AliasInfo

Quando você usa o parâmetro *PassThru* , **New-Alias** gera um objeto **System. Management. Automation. AliasInfo** que representa o novo alias.
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

* Para criar um novo alias, use `Set-Alias` ou `New-Alias` . Para alterar um alias, use `Set-Alias` . Para excluir um alias, use `Remove-Item` .

## LINKS RELACIONADOS

[Export-Alias](Export-Alias.md)

[Get-Alias](Get-Alias.md)

[Import-Alias](Import-Alias.md)

[Set-Alias](Set-Alias.md)

