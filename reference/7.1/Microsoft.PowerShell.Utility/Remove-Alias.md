---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-alias?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Alias
ms.openlocfilehash: 7406b2cac771ae7a741af92cd362cce834c59a50
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194005"
---
# Remove-Alias

## SINOPSE
Remover um alias da sessão atual.

## SYNTAX

### Padrão (padrão)

```
Remove-Alias [-Name] <String[]> [-Scope <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

O `Remove-Alias` cmdlet Remove um alias da sessão atual do PowerShell. Para remover um alias com a propriedade **Option** definida como **ReadOnly** , use o parâmetro **Force** .

O `Remove-Alias` cmdlet foi introduzido no PowerShell 6,0.

## EXEMPLOS

### Exemplo 1-remover um alias

Este exemplo remove um alias chamado `del` que representa o `Remove-Item` cmdlet.

```powershell
Remove-Alias -Name del
```

### Exemplo 2-remover todos os aliases não constantes

Este exemplo remove todos os aliases da sessão atual do PowerShell, com exceção de aliases com a propriedade **Options** definida como **Constant** . Depois que o comando é executado, os aliases estão disponíveis em outras sessões do PowerShell ou novas sessões do PowerShell.

```powershell
Get-Alias | Where-Object { $_.Options -NE "Constant" } | Remove-Alias -Force
```

`Get-Alias` Obtém todos os aliases na sessão do PowerShell e envia os objetos por meio do pipeline.
`Where-Object` usa um bloco de script, e a propriedade de `$_` **Opções** e a variável automática () e as propriedades representam o objeto de pipeline atual. O parâmetro **ne** (diferente de), seleciona objetos que não têm um valor de **Opções** definido como **constante** . `Remove-Alias` usa o parâmetro **Force** para remover aliases, incluindo aliases somente leitura, da sessão do PowerShell.

## PARAMETERS

### -Force

Indica que o cmdlet Remove um alias, incluindo aliases com a propriedade **Option** definida como **ReadOnly** . O parâmetro **Force** não pode remover um alias com uma propriedade **Option** definida como **Constant** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica o nome do alias a ser removido.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Escopo

Afeta somente os aliases no escopo especificado. O escopo padrão é **local** . Para obter mais informações, consulte [about_Scopes](../microsoft.powershell.core/about/about_scopes.md).

Os valores aceitáveis para esse parâmetro são:

- Global
- Local
- script
- Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai)

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String[]

É possível canalizar um objeto de alias para **Remove-alias** .

## SAÍDAS

### Nenhum

Esse cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

As alterações afetam apenas o escopo atual. Para remover um alias de todas as sessões, adicione um comando **Remove-alias** ao seu perfil do PowerShell.

Para obter mais informações, consulte [about_Aliases](../microsoft.powershell.core/about/about_aliases.md).

## LINKS RELACIONADOS

[about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[Export-Alias](Export-Alias.md)

[Get-Alias](Get-Alias.md)

[Import-Alias](Import-Alias.md)

[New-Alias](New-Alias.md)

[Set-Alias](Set-Alias.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)

