---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-sddlstring?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SddlString
ms.openlocfilehash: 8552bec8029210553a8d4e51dcecb88948eb353e
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "93195282"
---
# ConvertFrom-SddlString

## SINOPSE
Converte uma cadeia de caracteres SDDL em um objeto personalizado.

## SYNTAX

### Tudo

```
ConvertFrom-SddlString [-Sddl] <String> [-Type <AccessRightTypeNames>] [<CommonParameters>]
```

## DESCRIPTION

O `ConvertFrom-SddlString` cmdlet converte uma cadeia de caracteres de linguagem de definição de descritor de segurança em um objeto **PSCustomObject** personalizado com as seguintes propriedades: Owner, Group, DiscretionaryAcl, SystemAcl e RawDescriptor.

As propriedades Owner, Group, DiscretionaryAcl e SystemAcl contêm uma representação de texto legível dos direitos de acesso especificados em uma cadeia de caracteres SDDL.

Esse cmdlet foi introduzido no PowerShell 5,0.

## EXEMPLOS

### Exemplo 1: converter o SDDL de direitos de acesso do sistema de arquivos em um PSCustomObject

```powershell
$acl = Get-Acl -Path C:\Windows
ConvertFrom-SddlString -Sddl $acl.Sddl
```

O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança para a pasta C:\Windows e salva-o na variável.

O segundo comando usa o `ConvertFrom-SddlString` cmdlet para obter a representação de texto da cadeia de caracteres SDDL, contida na propriedade SDDL do objeto que representa o descritor de segurança.

### Exemplo 2: converter o SDDL de direitos de acesso do registro em um PSCustomObject

```powershell
$acl = Get-Acl HKLM:\SOFTWARE\Microsoft\
ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights
```

O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança para a chave HKLM: \ SOFTWARE\Microsoft\ e salva-o na variável.

O segundo comando usa o `ConvertFrom-SddlString` cmdlet para obter a representação de texto da cadeia de caracteres SDDL, contida na propriedade SDDL do objeto que representa o descritor de segurança.

Ele usa o `-Type` parâmetro para especificar que a cadeia de caracteres SDDL representa um descritor de segurança do registro.

### Exemplo 3: converter o SDDL de direitos de acesso do registro em um PSCustomObject usando ConvertFrom-SddlString com e sem o `-Type` parâmetro

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Microsoft\

ConvertFrom-SddlString -Sddl $acl.Sddl | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateDirectories, Delete, ExecuteKey, FullControl, GenericExecute, GenericWrite, ListDirectory, ReadExtendedAttributes, ReadPermissions, TakeOwnership, Traverse, WriteData, WriteExtendedAttributes, WriteKey)

ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateLink, CreateSubKey, Delete, EnumerateSubKeys, ExecuteKey, FullControl, GenericExecute, GenericWrite, Notify, QueryValues, ReadPermissions, SetValue, TakeOwnership, WriteKey)
```

O primeiro comando usa o `Get-Acl` cmdlet para obter o descritor de segurança para a chave HKLM: \ SOFTWARE\Microsoft\ e salva-o na variável.

O segundo comando usa o `ConvertFrom-SddlString` cmdlet para obter a representação de texto da cadeia de caracteres SDDL, contida na propriedade SDDL do objeto que representa o descritor de segurança.

Ele não usa o `-Type` parâmetro, portanto, os direitos de acesso mostrados são para o sistema de arquivos.

O terceiro comando usa o `ConvertFrom-SddlString` cmdlet com o `-Type` parâmetro, de modo que os direitos de acesso retornados são para o registro.

## PARAMETERS

### -SDDL

Especifica a cadeia de caracteres que representa o descritor de segurança na sintaxe SDDL.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Type

Especifica o tipo de direitos que a cadeia de caracteres SDDL representa.

Os valores aceitáveis para esse parâmetro são:

- FileSystemRights
- RegistryRights
- ActiveDirectoryRights
- MutexRights
- SemaphoreRights
- CryptoKeyRights
- EventWaitHandleRights

Por padrão, o cmdlet usa direitos de sistema de arquivos.

Não há suporte para CryptoKeyRights e ActiveDirectoryRights no PowerShell Core.

```yaml
Type: Microsoft.PowerShell.Commands.ConvertFromSddlStringCommand+AccessRightTypeNames
Parameter Sets: (All)
Aliases:
Accepted values: FileSystemRights, RegistryRights, ActiveDirectoryRights, MutexRights, SemaphoreRights, CryptoKeyRights, EventWaitHandleRights

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

É possível canalizar uma cadeia de caracteres SDDL para `ConvertFrom-SddlString` .

## SAÍDAS

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Linguagem de definição do descritor de segurança](/windows/win32/secauthz/security-descriptor-definition-language)
