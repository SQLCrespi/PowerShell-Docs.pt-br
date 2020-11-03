---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-psbreakpoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSBreakpoint
ms.openlocfilehash: 9530e3bc15360245de334a6f45ff35883181a41e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193836"
---
# Enable-PSBreakpoint

## SINOPSE
Habilita os pontos de interrupção no console atual.

## SYNTAX

### ID (padrão)

```
Enable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Ponto de interrupção

```
Enable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

O `Enable-PSBreakpoint` cmdlet habilita novamente os pontos de interrupção desabilitados. Você pode usá-lo para habilitar todos os pontos de interrupção ou pontos de interrupção específicos fornecendo objetos ou IDs de ponto de interrupção.

Um ponto de interrupção é um Point em um script em que a execução é interrompida temporariamente para que você possa examinar o estado do script. Os pontos de interrupção recém-criados são habilitados automaticamente, mas podem ser desabilitados usando `Disable-PSBreakpoint` .

Tecnicamente, esse cmdlet altera o valor da propriedade **Enabled** de um objeto de ponto de interrupção para **true** .

`Enable-PSBreakpoint` é um dos vários cmdlets projetados para depurar scripts do PowerShell. Para obter mais informações sobre o depurador do PowerShell, consulte [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).

## EXEMPLOS

### Exemplo 1: habilitar todos os pontos de interrupção

Este exemplo habilita todos os pontos de interrupção na sessão atual.

```powershell
Get-PSBreakpoint | Enable-PSBreakpoint
```

Usando aliases, este exemplo pode ser abreviado como `gbp | ebp` .

### Exemplo 2: habilitar pontos de interrupção por ID

Este exemplo habilita vários pontos de interrupção usando suas IDs de ponto de interrupção.

```powershell
Enable-PSBreakpoint -Id 0, 1, 5
```

### Exemplo 3: habilitar um ponto de interrupção desabilitado

Este exemplo habilita novamente um ponto de interrupção que foi desabilitado.

```powershell
$B = Set-PSBreakpoint -Script "sample.ps1" -Variable Name -PassThru
$B | Enable-PSBreakpoint -PassThru
```

```Output
AccessMode : Write
Variable   : Name
Action     :
Enabled    : False
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1

AccessMode : Write
Variable   : Name
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

`Set-PSBreakpoint` Cria um ponto de interrupção na variável de **nome** no `Sample.ps1` script que salva o objeto de ponto de interrupção na `$B` variável. O parâmetro **PassThru** exibe o valor da propriedade **Enabled** do ponto de interrupção é **false** .

`Enable-PSBreakpoint` habilita novamente o ponto de interrupção. Novamente, usando o parâmetro **PassThru** , vemos que o valor da propriedade **Enabled** é **true** .

### Exemplo 4: habilitar pontos de interrupção usando uma variável

Este exemplo habilita um conjunto de pontos de interrupção usando os objetos de ponto de interrupção.

```powershell
$B = Get-PSBreakpoint -Id 3, 5
Enable-PSBreakpoint -Breakpoint $B
```

`Get-PSBreakpoint` Obtém os pontos de interrupção e salva-os na `$B` variável. Usando o parâmetro **Breakpoint** , `Enable-PSBreakpoint` habilita os pontos de interrupção.

Este exemplo é equivalente a executar `Enable-PSBreakpoint -Id 3, 5` .

## PARAMETERS

### -Ponto de interrupção

Especifica os pontos de interrupção para habilitar. Forneça uma variável que contém pontos de interrupção ou um comando que obtém objetos de ponto de interrupção, como `Get-PSBreakpoint` . Também é possível canalizar objetos de ponto de interrupção para `Enable-PSBreakpoint` .

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

Especifica os números de **ID** dos pontos de interrupção a serem habilitados. O valor padrão é todos os pontos de interrupção.
Forneça a **ID** por número ou em uma variável. Não é possível canalizar números de **ID** para `Enable-PSBreakpoint` . Para localizar a **ID** de um ponto de interrupção, use o `Get-PSBreakpoint` cmdlet.

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

Retorna um objeto que representa o ponto de interrupção que está sendo habilitado. Por padrão, esse cmdlet não gera nenhuma saída.

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

### System. Management. Automation. Breakpoint

É possível canalizar um objeto de ponto de interrupção para `Enable-PSBreakpoint` .

## SAÍDAS

### Nenhum ou System. Management. Automation. Breakpoint

Quando você usa o parâmetro **PassThru** , `Enable-PSBreakpoint` retorna um objeto de ponto de interrupção que representa o ponto de interrupção que foi habilitado. Caso contrário, esse cmdlet não gerará nenhuma saída.

## OBSERVAÇÕES

- O `Enable-PSBreakpoint` cmdlet não gerará um erro se você tentar habilitar um ponto de interrupção que já está habilitado. Dessa forma, você pode habilitar todos os pontos de interrupção sem erro, mesmo quando apenas alguns estão desabilitados.

- Os pontos de interrupção são habilitados quando você os cria usando o `Set-PSBreakpoint` cmdlet. Você não precisa habilitar pontos de interrupção recém-criados.

## LINKS RELACIONADOS

[Disable-PSBreakpoint](Disable-PSBreakpoint.md)

[Get-PSBreakpoint](Get-PSBreakpoint.md)

[Get-PSCallStack](Get-PSCallStack.md)

[Remove-PSBreakpoint](Remove-PSBreakpoint.md)

[Set-PSBreakpoint](Set-PSBreakpoint.md)
