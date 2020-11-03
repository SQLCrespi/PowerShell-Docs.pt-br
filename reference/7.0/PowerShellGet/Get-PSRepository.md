---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-psrepository?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSRepository
ms.openlocfilehash: cc92188384497b5e7534e3dc7daa4fc73c314a36
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192874"
---
# Get-PSRepository

## SINOPSE
Obtém repositórios do PowerShell.

## SYNTAX

```
Get-PSRepository [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Get-PSRepository** Obtém repositórios de módulo do PowerShell que são registrados para o usuário atual.

## EXEMPLOS

### Exemplo 1: obter todos os repositórios de módulo

```
PS C:\> Get-PSRepository
Name                                     SourceLocation                                     OneGetProvider       InstallationPolicy
----                                     --------------                                     --------------       ------------------
PSGallery                                http://go.micro...                                 NuGet                Untrusted
myNuGetSource                            https://myget.c...                                 NuGet                Trusted
```

Esse comando obtém todos os repositórios de módulo registrados para o usuário atual.

### Exemplo 2: obter repositórios de módulo por nome

```
PS C:\> Get-PSRepository -Name "*NuGet*"
```

Esse comando obtém todos os repositórios de módulo que incluem o NuGet em seus nomes.

### Exemplo 3: obter um repositório de módulo e formatar a saída

```
PS C:\> Get-PSRepository -Name "Local01" | Format-List * -Force
Name                      : local01
SourceLocation            : http://manikb-dev:8765/api/v2/
Trusted                   : True
Registered                : True
InstallationPolicy        : Trusted
PackageManagementProvider : NuGet
PublishLocation           : http://pattif-dev:8765/api/v2/package/
ScriptSourceLocation      : http://pattif-dev:8765/api/v2/artifacts/psscript
ScriptPublishLocation     : http://pattif-dev:8765/api/v2/package/
ProviderOptions           : {}
```

Esse comando obtém o repositório chamado Local01 e usa o operador de pipeline para passar esse objeto para o cmdlet Format-List.

## PARAMETERS

### -Name

Especifica os nomes dos repositórios a serem obtidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String[]

## SAÍDAS

### System.Object

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Register-PSRepository](Register-PSRepository.md)

[Set-PSRepository](Set-PSRepository.md)

[Unregister-PSRepository](Unregister-PSRepository.md)
