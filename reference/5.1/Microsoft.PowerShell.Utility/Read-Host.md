---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/18/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 7f8c8a71657d1d00beb4c6e22159fb2b4ad5dce4
ms.sourcegitcommit: 16a02ae47d1a85b01692101aa0aa6e91e1ba398e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104726359"
---
# Read-Host

## SINOPSE
Lê uma linha de entrada do console.

## SYNTAX

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## DESCRIPTION

O `Read-Host` cmdlet lê uma linha de entrada do console do (STDIN). Você pode usá-lo para solicitar uma entrada do usuário. Como você pode salvar a entrada como uma cadeia de caracteres segura, você pode usar esse cmdlet para solicitar aos usuários dados seguros, como senhas.

> [!NOTE]
> `Read-Host` tem um limite de 8190 caracteres que ele pode aceitar como entrada de um usuário.

## EXEMPLOS

### Exemplo 1: salvar a entrada do console em uma variável

Este exemplo exibe a cadeia de caracteres "Insira sua idade:" como um prompt. Quando um valor é inserido e a tecla Enter é pressionada, o valor é armazenado na `$Age` variável.

```powershell
$Age = Read-Host "Please enter your age"
```

### Exemplo 2: salvar a entrada do console como uma cadeia de caracteres segura

Este exemplo exibe a cadeia de caracteres "Insira uma senha:" como um prompt. Como um valor está sendo inserido, os asteriscos ( `*` ) aparecem no console no lugar da entrada. Quando a tecla Enter é pressionada, o valor é armazenado como um objeto **SecureString** na `$pwd_secure_string` variável.

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

## PARAMETERS

### -Assegurastring

Indica que o cmdlet exibe asteriscos ( `*` ) no lugar dos caracteres que o usuário digita como entrada. Quando você usa esse parâmetro, a saída do `Read-Host` cmdlet é um objeto **SecureString** (**System. Security. SecureString**).

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

### -Aviso

Especifica o texto do aviso. Digite uma cadeia de caracteres. Se a cadeia de caracteres incluir espaços, coloque-a entre aspas. O PowerShell acrescenta um sinal de dois-pontos ( `:` ) ao texto inserido.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Esse cmdlet não aceita a entrada do pipeline do PowerShell.

## SAÍDAS

### System. String ou System. Security. SecureString

Se o parâmetro **AsSecureString** for usado, `Read-Host` retornará uma **SecureString**. Caso contrário, ele retornará uma cadeia de caracteres.

## OBSERVAÇÕES

Esse cmdlet só lê a partir do fluxo stdin do processo de host. Normalmente, o fluxo stdin é conectado ao teclado do console do host.

## LINKS RELACIONADOS

[Clear-Host](../microsoft.powershell.core/clear-host.md)

[Get-Host](Get-Host.md)

[Write-Host](Write-Host.md)

[ConvertFrom-SecureString](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
