---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-psbreakpoint?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSBreakpoint
ms.openlocfilehash: 2f89be6b2ae9973b060a8562b5815b4e44b56ad8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194279"
---
# Disable-PSBreakpoint

## SINOPSE
Desabilita os pontos de interrupção no console atual.

## SYNTAX

### Ponto de interrupção (padrão)

```
Disable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ID

```
Disable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Disable-PSBreakpoint** desabilita pontos de interrupção, o que garante que eles não sejam atingidos quando o script for executado.
Você pode usá-lo para desabilitar todos os pontos de interrupção ou pode especificar os pontos de interrupção enviando objetos de ponto de interrupção ou IDs de ponto de interrupção.

Tecnicamente, esse cmdlet altera o valor da propriedade Enabled de um objeto de ponto de interrupção para False.
Para reabilitar um ponto de interrupção, use o cmdlet Enable-PSBreakpoint.
Pontos de interrupção estão habilitados por padrão ao criá-los usando o cmdlet Set-PSBreakpoint.

Um ponto de interrupção é um ponto em um script onde a execução para temporariamente para que você possa examinar as instruções no script.
**Disable-PSBreakpoint** é um dos vários cmdlets projetados para depurar scripts do PowerShell.
Para obter mais informações sobre o depurador do PowerShell, consulte about_Debuggers.

## EXEMPLOS

### Exemplo 1: definir um ponto de interrupção e desabilitá-lo

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "name"
PS C:\> $B | Disable-PSBreakpoint
```

Esses comandos desabilitam um ponto de interrupção recém-criado.

O primeiro comando usa o cmdlet Set-PSBreakpoint para criar um ponto de interrupção na variável *Name* no script Sample.ps1.
Em seguida, ele salva o objeto de ponto de interrupção na variável $B.

O segundo comando usa o cmdlet **Disable-PSBreakpoint** para desabilitar o novo ponto de interrupção.
Ele usa um operador de pipeline (|) para enviar o objeto de ponto de interrupção em $B para o cmdlet **Disable-PSBreakpoint** .

Como resultado desse comando, o valor da propriedade Enabled do objeto de ponto de interrupção no $B é false.

### Exemplo 2: desabilitar um ponto de interrupção

```
PS C:\> Disable-PSBreakpoint -Id 0
```

Este comando desabilita o ponto de interrupção com a ID do ponto de interrupção 0.

### Exemplo 3: criar um ponto de interrupção desabilitado

```
PS C:\> Disable-PSBreakpoint -Breakpoint ($B = Set-PSBreakpoint -Script "sample.ps1" -Line 5)
PS C:\> $B
```

Este comando cria um novo ponto de interrupção que será desabilitado até você habilitá-lo.

Ele usa o cmdlet **Disable-PSBreakpoint** para desabilitar o ponto de interrupção.
O valor do parâmetro *Breakpoint* é um comando Set-PSBreakpoint que define um novo ponto de interrupção, gera um objeto de ponto de interrupção e salva o objeto na variável $B.

Parâmetros de cmdlet que usam objetos como seus valores podem aceitar uma variável que contém o objeto ou um comando que recebe ou gera o objeto.
Nesse caso, como **Set-PSBreakpoint** gera um objeto de ponto de interrupção, ele pode ser usado como o valor do parâmetro *Breakpoint* .

O segundo comando exibe o objeto de ponto de interrupção no valor da variável $B.

### Exemplo 4: desabilitar todos os pontos de interrupção no console atual

```
PS C:\> Get-PSBreakpoint | Disable-PSBreakpoint
```

Este comando desabilita todos os pontos de interrupção no console atual.
Você pode abreviar este comando como: "GBP | DBP ".

## PARAMETERS

### -Ponto de interrupção

Especifica os pontos de interrupção para desabilitar.
Insira uma variável que contém objetos de ponto de interrupção ou um comando que obtém os objetos de ponto de interrupção, como um comando Get-PSBreakpoint.
Você também pode canalizar objetos de ponto de interrupção para o cmdlet **Disable-PSBreakpoint** .

```yaml
Type: System.Management.Automation.Breakpoint[]
Parameter Sets: Breakpoint
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id

Desabilita os pontos de interrupção com as IDs de ponto de interrupção especificados.
Insira as IDs ou uma variável que contém as IDs.
Não é possível canalizar IDs para **Disable-PSBreakpoint** .

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto que representa os pontos de interrupção habilitados.
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

### System. Management. Automation. Breakpoint

É possível canalizar um objeto de ponto de interrupção para **Disable-PSBreakpoint** .

## SAÍDAS

### Nenhum ou System. Management. Automation. Breakpoint

Quando você usa o parâmetro *PassThru* , **Disable-PSBreakpoint** retorna um objeto que representa o ponto de interrupção desabilitado.
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Enable-PSBreakpoint](Enable-PSBreakpoint.md)

[Get-PSBreakpoint](Get-PSBreakpoint.md)

[Get-PSCallStack](Get-PSCallStack.md)

[Remove-PSBreakpoint](Remove-PSBreakpoint.md)

[Set-PSBreakpoint](Set-PSBreakpoint.md)

