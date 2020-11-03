---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-psbreakpoint?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSBreakpoint
ms.openlocfilehash: 0d50fe8359f54b8aaac9482d162cc0865b1824fe
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193602"
---
# Remove-PSBreakpoint

## SINOPSE
Exclui os pontos de interrupção do console atual.

## SYNTAX

### Ponto de interrupção (padrão)

```
Remove-PSBreakpoint [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ID

```
Remove-PSBreakpoint [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Remove-PSBreakpoint** exclui um ponto de interrupção.
Insira um objeto de ponto de interrupção ou uma ID de ponto de interrupção.

Quando você remove um ponto de interrupção, o objeto de ponto de interrupção não está mais disponível ou funcional.
Se você salvou um objeto de ponto de interrupção em uma variável, a referência ainda existe, mas o ponto de interrupção não funciona.

**Remove-PSBreakpoint** é um dos vários cmdlets projetados para depurar scripts do PowerShell.
Para obter mais informações sobre o depurador do PowerShell, consulte about_Debuggers.

## EXEMPLOS

### Exemplo 1: remover todos os pontos de interrupção

```
PS C:\> Get-PSBreakpoint | Remove-PSBreakpoint
```

Esta função exclui todos os pontos de interrupção no console atual.

### Exemplo 2: remover um ponto de interrupção especificado

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "Name"
PS C:\> $B | Remove-PSBreakpoint
```

Esse comando exclui um ponto de interrupção.

O primeiro comando usa o cmdlet Set-PSBreakpoint para criar um ponto de interrupção na variável Name no script Sample.ps1.
Em seguida, ele salva o objeto de ponto de interrupção na variável $B.

O segundo comando usa o cmdlet **Remove-PSBreakpoint** para excluir o novo ponto de interrupção.
Ele usa um operador de pipeline (|) para enviar o objeto de ponto de interrupção na variável $B para o cmdlet **Remove-PSBreakpoint** .

Como resultado desse comando, se você executar o script, ele é executado sem parar até a conclusão.
Além disso, o cmdlet **Get-PSBreakpoint** não retorna esse ponto de interrupção.

### Exemplo 3: remover um ponto de interrupção por ID

```
PS C:\> Remove-PSBreakpoint -Id 2
```

Este comando exclui o ponto de interrupção com a ID do ponto de interrupção 2.

### Exemplo 4: usar uma função para remover todos os pontos de interrupção

```
PS C:\> function del-psb { get-psbreakpoint | remove-psbreakpoint }
```

Esta função simples exclui todos os pontos de interrupção no console atual.
Ele usa o cmdlet Get-PSBreakpoint para obter os pontos de interrupção.
Em seguida, ele usa um operador de pipeline (|) para enviar os pontos de interrupção para o cmdlet **Remove-PSBreakpoint** , que os exclui.

Como resultado, você pode digitar `del-psb` em vez do comando mais longo.

Para salvar a função, adicione-a ao seu perfil do PowerShell.

## PARAMETERS

### -Ponto de interrupção
Especifica os pontos de interrupção a excluir.
Insira uma variável que contenha objetos de ponto de interrupção ou um comando que obtém objetos de ponto de interrupção, como um comando **Get-PSBreakpoint** .
Você também pode canalizar objetos de ponto de interrupção para **Remove-PSBreakpoint** .

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
Especifica as IDs de ponto de interrupção para os quais esse cmdlet exclui pontos de interrupção.

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
É possível canalizar objetos de ponto de interrupção para **Remove-PSBreakpoint** .

## SAÍDAS

### Nenhum
O cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Disable-PSBreakpoint](Disable-PSBreakpoint.md)

[Enable-PSBreakpoint](Enable-PSBreakpoint.md)

[Get-PSBreakpoint](Get-PSBreakpoint.md)

[Get-PSCallStack](Get-PSCallStack.md)

[Set-PSBreakpoint](Set-PSBreakpoint.md)
