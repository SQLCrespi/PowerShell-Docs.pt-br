---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-verbose?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Verbose
ms.openlocfilehash: e16e002ab9e803900712542c329723f6a44a880f
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "93196407"
---
# Write-Verbose

## SINOPSE
Grava o texto para o fluxo de mensagem detalhada.

## SYNTAX

```
Write-Verbose [-Message] <String> [<CommonParameters>]
```

## DESCRIPTION

O `Write-Verbose` cmdlet grava o texto no fluxo de mensagens detalhadas no PowerShell. Normalmente, o fluxo de mensagens detalhados é usado para fornecer informações mais detalhadas sobre o processamento de comandos.

Por padrão, o fluxo de mensagens detalhadas não é exibido, mas você pode exibi-lo alterando o valor da `$VerbosePreference` variável ou usando o parâmetro comum **detalhado** em qualquer comando.

## EXEMPLOS

### Exemplo 1: gravar uma mensagem de status

```powershell
Write-Verbose -Message "Searching the Application Event Log."
Write-Verbose -Message "Searching the Application Event Log." -Verbose
```

Esses comandos usam o `Write-Verbose` cmdlet para exibir uma mensagem de status. Por padrão, a mensagem não é exibida.

O segundo comando usa o parâmetro comum **Verbose** , que exibe todas as mensagens detalhadas, independentemente do valor da `$VerbosePreference` variável.

### Exemplo 2: definir $VerbosePreference e gravar uma mensagem de status

```powershell
$VerbosePreference = "Continue"
Write-Verbose "Copying file $filename"
```

Esses comandos usam o `Write-Verbose` cmdlet para exibir uma mensagem de status. Por padrão, a mensagem não é exibida.

O primeiro comando atribui um valor de continuar à `$VerbosePreference` variável de preferência. O valor padrão, `SilentlyContinue` , suprime as mensagens detalhadas. O segundo comando grava uma mensagem detalhada.

## PARAMETERS

### -Mensagem

Especifica a mensagem a ser exibida. Este parâmetro é necessário. Você também pode canalizar uma cadeia de caracteres de mensagem para `Write-Verbose` .

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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres que contém a mensagem para `Write-Verbose` .

## SAÍDAS

### Nenhum

`Write-Verbose` grava somente no fluxo de mensagens detalhadas.

## OBSERVAÇÕES

- As mensagens detalhadas são retornadas somente quando o comando usa o parâmetro **Verbose** comum. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).
- Em trabalhos em segundo plano do Windows PowerShell e em comandos remotos, a `$VerbosePreference` variável na sessão de trabalho e na sessão remota determinam se a mensagem detalhada é exibida por padrão.
  Para obter mais informações sobre a `$VerbosePreference` variável, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

## LINKS RELACIONADOS

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Write-Debug](Write-Debug.md)

[Erro de gravação](Write-Error.md)

[Write-Host](Write-Host.md)

[Write-Information](Write-Information.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Warning](Write-Warning.md)
