---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/clear-variable?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Variable
ms.openlocfilehash: e42371a58b49a25a9aaf0cc60551ff4bf27e2ec4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194744"
---
# Clear-Variable

## SINOPSE
Excluir o valor de uma variável.

## SYNTAX

```
Clear-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-PassThru]
 [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Clear-Variable** exclui os dados armazenados em uma variável, mas não exclui a variável.
Como resultado, o valor da variável é NULL (vazio).
Se a variável tiver um tipo de dados ou objeto especificado, esse cmdlet preservará o tipo do objeto armazenado na variável.

## EXEMPLOS

### Exemplo 1: remover o valor de variáveis globais que começam com uma cadeia de caracteres de pesquisa

```
PS C:\> Clear-Variable my* -Scope Global
```

Esse comando Remove o valor de variáveis globais que têm nomes que começam com My.

### Exemplo 2: limpar uma variável em um escopo filho, mas não no escopo pai

```
PS C:\> $a=3
PS C:\> &{ Clear-Variable a }
PS C:\> $a
3
```

Esses comandos demonstram que apagar uma variável em um escopo filho não apaga o valor no escopo pai.
O primeiro comando define o valor da variável $A como 3.
O segundo comando usa o operador Invoke (&) para executar o comando **Clear-Variable** em um novo escopo.
A variável é apagada no escopo filho (embora ela não exista), mas não será apagada no escopo local.
O terceiro comando, que obtém o valor de $A, mostra que o valor 3 não é afetado.

### Exemplo 3: excluir o valor da variável especificada

```
PS C:\> Clear-Variable -Name "Processes"
```

Esse comando exclui o valor da variável chamada Processes.
Depois que o cmdlet concluir a operação, a variável denominada processos ainda existirá, mas o valor será NULL.

## PARAMETERS

### -Excluir

Especifica uma matriz de itens que esse cmdlet omite na operação.
O valor desse parâmetro qualifica o parâmetro de *nome* .
Insira um elemento Name ou padrão, como "*s".
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

### -Force

Permite que o cmdlet apaga uma variável, mesmo se for somente leitura.
Mesmo usando o parâmetro Force, o cmdlet não pode remover uma constante.

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

Especifica uma matriz de itens que esse cmdlet inclui na operação.
O valor desse parâmetro qualifica o parâmetro de *nome* .
Insira um elemento Name ou padrão, como "*s".
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

Especifica o nome da variável a ser apagada.
Caracteres curinga são permitidos.
Este parâmetro é obrigatório, mas o nome do parâmetro ("Name") é opcional.

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

Especifica o escopo no qual esse alias é válido.

Os valores aceitáveis para esse parâmetro são:

- Global
- Local
- script

Você também pode usar um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai).
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

Não é possível transferir objetos para esse cmdlet.

## SAÍDAS

### Nenhum ou System. Management. Automation. PSVariable

Quando você usa o parâmetro *PassThru* , esse cmdlet gera um objeto **System. Management. Automation. PSVariable** que representa a variável limpa.
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

* Para excluir uma variável, juntamente com seus valores, use Remove-Variable ou Remove-Item.

  Esse cmdlet não exclui os valores de variáveis que são definidas como constantes ou pertencentes ao sistema, mesmo que você use o parâmetro *Force* .

  Se a variável que você está limpando não existir, o cmdlet não terá nenhum efeito.
Ele não cria uma variável com um valor nulo.

  Você também pode se referir a **Clear-Variable** por seu alias interno, CLV.
Para obter mais informações, consulte about_Aliases.

*

## LINKS RELACIONADOS

[Get-Variable](Get-Variable.md)

[New-Variable](New-Variable.md)

[Remove-Variable](Remove-Variable.md)

[Set-Variable](Set-Variable.md)

