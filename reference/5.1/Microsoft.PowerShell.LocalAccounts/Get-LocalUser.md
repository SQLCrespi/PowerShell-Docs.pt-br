---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalUser
ms.openlocfilehash: 2b1831a854c4c61d4c4631ae475a59d8240a926b
ms.sourcegitcommit: 4d6ed6f7d747a9bbb3fcfcf6c981c5aa8a973a08
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "106072257"
---
# Get-LocalUser

## SINOPSE
Obtém as contas de usuário local.

## SYNTAX

### Padrão (padrão)

```
Get-LocalUser [[-Name] <String[]>] [<CommonParameters>]
```

### SecurityIdentifier

```
Get-LocalUser [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-LocalUser` cmdlet obtém contas de usuário local. Esse cmdlet obtém as contas de usuário internas padrão, as contas de usuário locais que você criou e as contas locais que você conectou às contas da Microsoft.

> [!NOTE]
> O módulo Microsoft. PowerShell. LocalAccounts não está disponível no PowerShell de 32 bits em um sistema de 64 bits.

## EXEMPLOS

### Exemplo 1: obter uma conta usando seu nome

Este exemplo obtém uma conta de usuário chamada AdminContoso02.

```powershell
Get-LocalUser -Name "AdminContoso02"
```

```Output
Name             Enabled Description
----             ------- -----------
AdminContoso02   True    Description of this account.
```

### Exemplo 2: obter uma conta que está conectada a um conta Microsoft

Este exemplo obtém uma conta de usuário que está conectada a um conta Microsoft. Este exemplo usa um valor de espaço reservado para o nome de usuário de uma conta em Outlook.com.

```powershell
Get-LocalUser -Name "MicrosoftAccount\username@Outlook.com"
```

```Output
Name                                    Enabled  Description
----                                    -------  -----------
MicrosoftAccount\username@outlook.com  True     Description of this account.
```

### Exemplo 3: obter uma conta que tenha o SID especificado

Este exemplo obtém uma conta de usuário local que tem o SID especificado.

```powershell
Get-LocalUser -SID S-1-5-21-9526073513-1762370368-3942940353-500
```

```Output
Name          Enabled Description
----          ------- -----------
Administrator True    Built-in account for administering the computer/domain
```

## PARAMETERS

### -Name

Especifica uma matriz de nomes de contas de usuário que esse cmdlet obtém. Você pode usar o caractere curinga.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -SID

Especifica uma matriz de IDs de segurança (SIDs) de contas de usuário que esse cmdlet obtém.

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. String, System. Security. principal. SecurityIdentifier

É possível canalizar uma cadeia de caracteres ou um SID para esse cmdlet.

## SAÍDAS

### System. Management. Automation. SecurityAccountsManager. LocalUser []

Esse cmdlet retorna contas de usuário local.

## OBSERVAÇÕES

A propriedade **Principado** nos objetos **LocalUser**, **local** e **LocalPrincipal** descreve a origem do objeto. As fontes possíveis são as seguintes:

- Local
- Active Directory
- Grupo do Active Directory do Azure
- Conta da Microsoft

A **entidade de segurança** tem suporte apenas pelo Windows 10, windows Server 2016 e versões posteriores do sistema operacional Windows. Para versões anteriores, a propriedade fica em branco.

## LINKS RELACIONADOS

[Disable-LocalUser](Disable-LocalUser.md)

[Enable-LocalUser](Enable-LocalUser.md)

[New-LocalUser](New-LocalUser.md)

[Remove-LocalUser](Remove-LocalUser.md)

[Rename-LocalUser](Rename-LocalUser.md)

[Set-LocalUser](Set-LocalUser.md)
