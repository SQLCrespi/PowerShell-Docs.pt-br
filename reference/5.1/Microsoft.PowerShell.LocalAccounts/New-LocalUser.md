---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/new-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-LocalUser
ms.openlocfilehash: d83f3ad12481df0849ff2fe3f61d553a9ffdcdde
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193984"
---
# New-LocalUser

## SINOPSE

Cria uma conta de usuário local.

## SYNTAX

### Senha (padrão)

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> -Password <SecureString> [-PasswordNeverExpires]
 [-UserMayNotChangePassword] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Senha não

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> [-NoPassword] [-UserMayNotChangePassword] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

O `New-LocalUser` cmdlet cria uma conta de usuário local. Esse cmdlet cria uma conta de usuário local ou uma conta de usuário local que está conectada a um conta Microsoft.

> [!NOTE]
> O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.

## EXEMPLOS

### Exemplo 1: criar uma conta de usuário

```
PS C:\> New-LocalUser -Name "User02" -Description "Description of this account." -NoPassword
Name    Enabled  Description
----    -------  -----------
User02  True     Description of this account.
```

Este comando cria uma conta de usuário local e não especifica os parâmetros de **AccountExpires** ou **senha** . Portanto, a conta não expira ou tem uma senha por padrão.

### Exemplo 2: criar uma conta de usuário que tenha uma senha

```
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> New-LocalUser "User03" -Password $Password -FullName "Third User" -Description "Description of this account."
Name    Enabled  Description
----    -------  -----------
User03  True     Description of this account.
```

O primeiro comando solicita uma senha usando o `Read-Host` cmdlet. O comando armazena a senha como uma cadeia de caracteres segura na `$Password` variável.

O segundo comando cria uma conta de usuário local usando a senha armazenada em `$Password` . O comando especifica um nome de usuário, nome completo e descrição para a conta de usuário.

## PARAMETERS

### -AccountExpires

Especifica quando a conta de usuário expira. Para obter um objeto **DateTime** , use o `Get-Date` cmdlet.
Se você não especificar esse parâmetro, a conta não expirará.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AccountNeverExpires

Indica que a conta não expira.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description

Especifica um comentário para a conta de usuário.
O comprimento máximo é de 48 caracteres.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Desabilitado

Indica que esse cmdlet cria a conta de usuário como desabilitada.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FullName

Especifica o nome completo da conta de usuário. O nome completo é diferente do nome de usuário da conta de usuário.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Especifica o nome de usuário para a conta de usuário.

Se você criar uma conta de usuário local para o sistema local, o nome de usuário poderá conter até 20 caracteres maiúsculos ou minúsculos. Um nome de usuário não pode conter os seguintes caracteres:

`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`

Um nome de usuário não pode consistir apenas em pontos `.` ou espaços.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Nosenha

Indica que a conta de usuário não tem uma senha.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoPassword
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password

Especifica uma senha para a conta de usuário. Você pode usar `Read-Host -GetCredential` , `Get-Credential` ou `ConvertTo-SecureString` para criar um objeto **SecureString** para a senha.

Se você omitir os parâmetros **password** e **NOPassword** , `New-LocalUser` o solicitará a senha do novo usuário.

```yaml
Type: System.Security.SecureString
Parameter Sets: Password
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PasswordNeverExpires

Indica se a senha expira.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Password
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserMayNotChangePassword

Indica que o usuário não pode alterar a senha na conta de usuário.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` . Para obter mais informações, confira [about_CommonParameters](/reference/6/Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System. String, System. DateTime, System. booliano, System. Security. SecureString

É possível canalizar uma cadeia de caracteres, um objeto **DateTime** , um valor booliano ou uma cadeia de caracteres segura para esse cmdlet.

## SAÍDAS

### System. Management. Automation. SecurityAccountsManager. LocalUser

Esse cmdlet retorna um objeto **LocalUser** .
Este objeto fornece informações sobre a conta de usuário.

## OBSERVAÇÕES

- Um nome de usuário não pode ser idêntico a nenhum outro nome de usuário ou nome de grupo no computador. Um nome de usuário não pode consistir apenas em pontos `.` ou espaços. Um nome de usuário pode conter até 20 caracteres maiúsculos ou minúsculos. Um nome de usuário não pode conter os seguintes caracteres:

`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`

- Uma senha pode conter até 127 caracteres.
- A propriedade **Principado** é uma propriedade em objetos **LocalUser** , **local** e **LocalPrincipal** que descreve a origem do objeto. As fontes possíveis são as seguintes:

  - Local
  - Active Directory
  - Grupo do Active Directory do Azure
  - Conta da Microsoft

> [!NOTE]
> A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows. Para versões anteriores, a propriedade fica em branco.

## LINKS RELACIONADOS

[Disable-LocalUser](Disable-LocalUser.md)

[Enable-LocalUser](Enable-LocalUser.md)

[Get-LocalUser](Get-LocalUser.md)

[Remove-LocalUser](Remove-LocalUser.md)

[Rename-LocalUser](Rename-LocalUser.md)

[Set-LocalUser](Set-LocalUser.md)
