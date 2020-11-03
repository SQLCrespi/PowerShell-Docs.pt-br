---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 07/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-variable?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Variable
ms.openlocfilehash: 2e0e9388c592cb83dd7609fed663ae220e380750
ms.sourcegitcommit: 84fcc90bd018ab76ac4e964d53e7c9c2b5a7b6c6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93195057"
---
# Remove-Variable

## SINOPSE
Exclui uma variável e seu valor.

## SYNTAX

```
Remove-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Scope <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Remove-Variable` cmdlet exclui uma variável e seu valor do escopo no qual ela é definida, como a sessão atual. Não é possível utilizar este cmdlet para excluir as variáveis que são definidas como constantes ou aqueles que são de propriedade do sistema.

## EXEMPLOS

### Exemplo 1: remover uma variável

```powershell
Remove-Variable Smp
```

Esse comando exclui a `$Smp` variável.

## PARAMETERS

### -Excluir

Especifica uma matriz de itens que esse cmdlet omite da operação. O valor desse parâmetro qualifica o parâmetro de **nome** . Insira um elemento Name ou padrão, como "*s". Caracteres curinga são permitidos.

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

### -Force

Indica que o cmdlet Remove uma variável, mesmo se for somente leitura. Mesmo usando o parâmetro **Force** , o cmdlet não pode remover uma constante.

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

### -Incluir

Especifica uma matriz de itens que esse cmdlet exclui na operação. O valor desse parâmetro qualifica o parâmetro de **nome** . Insira um elemento de nome ou padrão, como s *. Caracteres curinga são permitidos.

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

Especifica o nome da variável a ser removida. O nome do parâmetro ( **Name** ) é opcional.
Caracteres curinga são permitidos

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Escopo

Ele obtém somente as variáveis no escopo especificado. Os valores aceitáveis para esse parâmetro são:

- Global
- Local
- script
- Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai)

Local é o padrão. Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

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

### System. Management. Automation. PSVariable

É possível canalizar um objeto de variável para `Remove-Variable` .

## SAÍDAS

### Nenhum

Este cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

- As alterações afetam apenas o escopo atual como uma sessão. Para excluir uma variável de todas as sessões, adicione um `Remove-Variable` comando ao seu perfil do PowerShell.

- Você também pode consultar `Remove-Variable` por seu alias interno, `rv` . Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

## LINKS RELACIONADOS

[Clear-Variable](Clear-Variable.md)

[Get-Variable](Get-Variable.md)

[New-Variable](New-Variable.md)

[Set-Variable](Set-Variable.md)
