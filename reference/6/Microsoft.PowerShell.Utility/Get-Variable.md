---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-variable?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Variable
ms.openlocfilehash: eac42af069b5d1276105c16dd6e280c7c72cf558
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194462"
---
# Get-Variable

## SINOPSE
Obtém as variáveis no console atual.

## SYNTAX

```
Get-Variable [[-Name] <String[]>] [-ValueOnly] [-Include <String[]>] [-Exclude <String[]>] [-Scope <String>]
 [<CommonParameters>]
```

## DESCRIPTION

O `Get-Variable` cmdlet obtém as variáveis do PowerShell no console atual.
Você pode recuperar apenas os valores das variáveis especificando o parâmetro **ValueOnly** , além de filtrar por nome as variáveis retornadas.

## EXEMPLOS

### Exemplo 1: obter variáveis por letra

Esse comando obtém variáveis com nomes que começam com a letra m.
O comando também obtém o valor das variáveis.

```powershell
Get-Variable m*
```

### Exemplo 2: obter valores de variáveis por letra

Esse comando obtém somente os valores das variáveis que têm nomes que começam com m.

```powershell
Get-Variable m* -ValueOnly
```

### Exemplo 3: obter variáveis por duas letras

Esse comando obtém informações sobre as variáveis que começam com a letra M ou a letra P.

```powershell
Get-Variable -Include M*,P*
```

### Exemplo 4: obter variáveis por escopo

O primeiro comando obtém apenas as variáveis que estão definidas no escopo local.
É equivalente a `Get-Variable -Scope Local` e pode ser abreviado como `gv -s 0` .

O segundo comando usa o `Compare-Object` cmdlet para localizar as variáveis que são definidas no escopo pai (escopo 1), mas são visíveis apenas no escopo local (escopo 0).

```powershell
Get-Variable -Scope 0
Compare-Object (Get-Variable -Scope 0) (Get-Variable -Scope 1)
```

## PARAMETERS

### -Excluir

Especifica uma matriz de itens que esse cmdlet exclui da operação.
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Incluir

Especifica uma matriz de itens sobre a qual o cmdlet atuará, excluindo todos os outros.
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Name

Especifica o nome da variável.
Caracteres curinga são permitidos.
Também é possível canalizar um nome de variável para `Get-Variable` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Escopo

Especifica as variáveis no escopo. Os valores aceitáveis para esse parâmetro são:

- **Global**
- **Local**
- **script**
- Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai)

**Local** é o padrão.
Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

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

### -ValueOnly

Indica que esse cmdlet obtém apenas o valor da variável.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém o nome da variável para `Get-Variable` .

## SAÍDAS

### System. Management. Automation. PSVariable

Esse cmdlet retorna um objeto **System. Management. AutomationPSVariable** para cada variável obtida. O tipo de objeto depende da variável.

### System. Object []

Quando você especifica o parâmetro **valueonly** , se o valor da variável especificada for uma coleção, `Get-Variable` retornará um `[System.Object[]]` . Esse comportamento impede que a operação normal de pipeline processe os valores da variável um de cada vez. Uma solução alternativa para forçar a enumeração da coleção é colocar o `Get-Variable` comando entre parênteses.

## OBSERVAÇÕES

- Este cmdlet não gerencia as variáveis de ambiente. Para gerenciar variáveis de ambiente, você pode usar o provedor de variável de ambiente.

## LINKS RELACIONADOS

[Clear-Variable](Clear-Variable.md)

[New-Variable](New-Variable.md)

[Remove-Variable](Remove-Variable.md)

[Set-Variable](Set-Variable.md)
