---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-warning?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Warning
ms.openlocfilehash: 7e74e53bd056a452917d2f2380b817fc6925f0fe
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "93196424"
---
# Write-Warning

## SINOPSE
Grava uma mensagem de aviso.

## SYNTAX

```
Write-Warning [-Message] <String> [<CommonParameters>]
```

## DESCRIPTION

O `Write-Warning` cmdlet grava uma mensagem de aviso no host do PowerShell. A resposta ao aviso depende do valor da variável do usuário `$WarningPreference` e do uso do parâmetro de **aviso** comum.

## EXEMPLOS

### Exemplo 1: gravar uma mensagem de aviso

Esse comando exibe a mensagem "aviso: Este é apenas um aviso de teste".

```powershell
Write-Warning "This is only a test warning."
```

### Exemplo 2: passar uma cadeia de caracteres para Write-Warning

Esse comando mostra que você pode usar um operador de pipeline ( `|` ) para enviar uma cadeia de caracteres para `Write-Warning` .
Você pode salvar a cadeia de caracteres em uma variável, conforme mostrado neste comando, ou canalizar a cadeia de caracteres diretamente para `Write-Warning` .

```powershell
$w = "This is only a test warning."
$w | Write-Warning
```

### Exemplo 3: definir a variável $WarningPreference e gravar um aviso

Este exemplo mostra o efeito do valor da `$WarningPreference` variável em um `Write-Warning` comando.

```powershell
PS> $WarningPreference
Continue
PS> Write-Warning "This is only a test warning."
This is only a test warning.
PS> $WarningPreference = "SilentlyContinue"
PS> Write-Warning "This is only a test warning."
PS> $WarningPreference = "Stop"
PS> Write-Warning "This is only a test warning."
WARNING: This is only a test message.
Write-Warning : Command execution stopped because the shell variable "WarningPreference" is set to Stop.
At line:1 char:14
     + Write-Warning <<<<  "This is only a test message."
```

O primeiro comando exibe o valor padrão da `$WarningPreference` variável, que é `Continue` . Como resultado, quando você escreve um aviso, a mensagem de aviso será exibida e a execução continuará.

Quando você altera o valor da `$WarningPreference` variável, o efeito do comando é `Write-Warning` alterado novamente. Um valor de `SilentlyContinue` suprime o aviso. Um valor `Stop` exibe o aviso e, em seguida, interrompe a execução do comando.

Para obter mais informações sobre a `$WarningPreference` variável, consulte [about_Preference_Variables](../Microsoft.Powershell.Core/About/about_Preference_Variables.md).

### Exemplo 4: definir o parâmetro WarningAction e gravar um aviso

Este exemplo mostra o efeito do parâmetro comum **WarningAction** em um `Write-Warning` comando. Você pode usar o parâmetro de **aviso** comum com qualquer cmdlet para determinar como o PowerShell responde a avisos resultantes desse comando. O parâmetro de **aviso** comum substitui o valor do `$WarningPreference` somente para esse comando específico.

```powershell
PS> Write-Warning "This is only a test warning." -WarningAction Inquire
WARNING: This is only a test warning.
Confirm
Continue with this operation?
 [Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

Esse comando usa o `Write-Warning` cmdlet para exibir um aviso. O parâmetro de **aviso** comum com um valor de consulta instrui o sistema a solicitar o usuário quando o comando exibir um aviso.

Para obter mais informações sobre o parâmetro de **aviso** comum, consulte [about_CommonParameters](../Microsoft.Powershell.Core/About/about_CommonParameters.md).

## PARAMETERS

### -Mensagem
Especifica a mensagem de aviso.

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

É possível canalizar uma cadeia de caracteres que contém o aviso para `Write-Warning` .

## SAÍDAS

### Nenhum

`Write-Warning` grava somente no fluxo de aviso. Ele não gera outras saídas.

## OBSERVAÇÕES

O valor padrão para a `$WarningPreference` variável é `Continue` , que exibe o aviso e, em seguida, continua executando o comando. Para determinar os valores válidos para uma variável de preferência, como `$WarningPreference` , defina-o como uma cadeia de caracteres aleatórios, como "ABC". A mensagem de erro resultante lista os valores válidos.

## LINKS RELACIONADOS

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Write-Debug](Write-Debug.md)

[Erro de gravação](Write-Error.md)

[Write-Host](Write-Host.md)

[Write-Information](Write-Information.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)
