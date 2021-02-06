---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-debug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Debug
ms.openlocfilehash: 3d23f76dbf8e1c9a21805a4914038c8c4f319852
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597829"
---
# Write-Debug

## SINOPSE
Grava uma mensagem de depuração para o console.

## SYNTAX

```
Write-Debug [-Message] <String> [<CommonParameters>]
```

## DESCRIPTION

O `Write-Debug` cmdlet grava mensagens de depuração no host a partir de um script ou comando.

Por padrão, as mensagens de depuração não são exibidas no console do, mas você pode exibi-las usando o parâmetro de **depuração** ou a `$DebugPreference` variável.

## EXEMPLOS

### Exemplo 1: entender $DebugPreference

Este exemplo grava uma mensagem de depuração.

```powershell
Write-Debug "Cannot open file."
```

O valor padrão de `$DebugPreference` é **SilentlyContinue**. Portanto, a mensagem não é exibida no console do.

### Exemplo 2: alterar o valor de $DebugPreference

Este exemplo mostra o efeito da alteração do valor da `$DebugPreference` variável. Primeiro, exibimos o valor atual de `$DebugPreference` e tentamos gravar uma mensagem de depuração. Em seguida, alteramos o valor de `$DebugPreference` para **continuar**, o que permite que as mensagens de depuração sejam exibidas.

```
PS> $DebugPreference
SilentlyContinue
PS> Write-Debug "Cannot open file."
PS>
PS> $DebugPreference = "Continue"
PS> Write-Debug "Cannot open file."
DEBUG: Cannot open file.
```

Para obter mais informações sobre o `$DebugPreference` , consulte [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).

### Exemplo 3: usar o parâmetro de depuração para substituir $DebugPreference

A `Test-Debug` função grava o valor da `$DebugPreference` variável para o host do PowerShell e para o fluxo de depuração. Neste exemplo, usamos o parâmetro **debug** para substituir o `$DebugPreference` valor.

```powershell
function Test-Debug {
    [CmdletBinding()]
    param()
    Write-Debug ('$DebugPreference is ' + $DebugPreference)
    Write-Host ('$DebugPreference is ' + $DebugPreference)
}
```

```
PS> Test-Debug
$DebugPreference is SilentlyContinue

PS> Test-Debug -Debug
DEBUG: $DebugPreference is Continue
$DebugPreference is Continue
PS> $DebugPreference
SilentlyContinue
```

Observe que o valor de é `$DebugPreference` alterado quando você usa o parâmetro de **depuração** . Essa alteração afeta apenas o escopo da função. O valor não é afetado fora da função.

Para obter mais informações sobre o parâmetro comum de **depuração** , consulte [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## PARAMETERS

### -Mensagem

Especifica a mensagem de depuração para enviar para o console.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém uma mensagem de depuração para `Write-Debug` .

## SAÍDAS

### Nenhum

`Write-Debug` grava somente no fluxo de depuração. Ele não grava nenhum objeto no pipeline.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Write-Error](Write-Error.md)

[Write-Host](Write-Host.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)
