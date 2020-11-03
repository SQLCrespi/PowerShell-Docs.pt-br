---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/test-scriptfileinfo?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ScriptFileInfo
ms.openlocfilehash: c773b247d5f0da4071517134b7187ba674bfbfbd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194456"
---
# Test-ScriptFileInfo

## SINOPSE
Valida um bloco de comentário para um script.

## SYNTAX

### PathParameterSet (padrão)

```
Test-ScriptFileInfo [-Path] <String> [<CommonParameters>]
```

### LiteralPathParameterSet

```
Test-ScriptFileInfo -LiteralPath <String> [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Test-ScriptFileInfo** valida o bloco de comentário no início de um script que será publicado com o cmdlet Publish-Script.
Se o bloco de comentários tiver um erro, esse cmdlet retornará informações sobre onde o erro está localizado ou como corrigi-lo.

## EXEMPLOS

### Exemplo 1: testar um arquivo de script

```
PS C:\> Test-ScriptFileInfo -Path "C:\temp\temp_scripts\New-ScriptFile.ps1"
Version    Name                      Author               Description
-------    ----                      ------               -----------
1.0        New-ScriptFile            pattif               my new script file test
```

Esse comando testa o arquivo de script New-ScriptFile.ps1 e exibe os resultados.
O arquivo de script inclui metadados válidos.

### Exemplo 2: testar um arquivo de script que tem valores para todas as propriedades de metadados

```
PS C:\> Test-ScriptFileInfo -Path "D:\code\Test-Runbook.ps1" | Format-List *
Name                       : Test-Runbook
Path                       : D:\code\Test-Runbook.ps1
ScriptBase                 : D:\code
ReleaseNotes               : {contoso script now supports following features, Feature 1, Feature 2, Feature 3...}
Version                    : 1.0
Guid                       : eb246b19-17da-4392-8c89-7c280f69ad0e
Author                     : pattif
CompanyName                : Microsoft Corporation
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
Tags                       : {Tag1, Tag2, Tag3}
LicenseUri                 : https://contoso.com/License
ProjectUri                 : https://contoso.com/
IconUri                    : https://contoso.com/MyScriptIcon
ExternalModuleDependencies : ExternalModule1
RequiredScripts            : {Start-WFContosoServer, Stop-ContosoServerScript}
ExternalScriptDependencies : Stop-ContosoServerScript
Description                : Contoso Script example
RequiredModules            : {RequiredModule1, @{ ModuleName = 'RequiredModule2'; ModuleVersion = '1.0' }, @{ ModuleName = 'RequiredModule3'; RequiredVersion = '2.0' }, ExternalModule1}
ExportedCommands           : {Test-WebUri, ValidateAndAdd-PSScriptInfoEntry, Get-PSScriptInfo, My-Workflow...}
ExportedFunctions          : {Test-WebUri, ValidateAndAdd-PSScriptInfoEntry, Get-PSScriptInfo, My-AdvPSCmdlet}
ExportedWorkflows          : My-Workflow
```

Esse comando testa o arquivo de script Test-Runbook.ps1 e usa o operador de pipeline para passar os resultados para o cmdlet Format-List para formatar os resultados.

### Exemplo 3: testar um arquivo de script que não tem metadados

```
PS C:\> Test-ScriptFileInfo -Path "D:\code\Hello-World.ps1"
Test-ScriptFileInfo : Script 'D:\code\Hello-World.ps1' is missing required metadata properties. Verify that the script file has Version, Description
and Author properties. You can use the Update-ScriptFileInfo or New-ScriptFileInfo cmdlet to add or update the PSScriptInfo to the script file.
At line:1 char:1
+ Test-ScriptFileInfo D:\code\Hello-World.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidArgument: (D:\code\Hello-World.ps1:String) [Test-ScriptFileInfo], ArgumentException

+ FullyQualifiedErrorId : MissingRequiredPSScriptInfoProperties,Test-ScriptFile
```

Este comando testa o arquivo de script Hello-World.ps1, que não tem metadados associados a ele.

## PARAMETERS

### -LiteralPath

Especifica um caminho para um ou mais locais.
Ao contrário do parâmetro *path* , o valor do parâmetro *LiteralPath* é usado exatamente como ele é inserido.
Nenhum caractere é interpretado como caractere curinga.
Se o caminho incluir caracteres de escape, coloque-os entre aspas simples.
Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.

```yaml
Type: System.String
Parameter Sets: LiteralPathParameterSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Especifica um caminho para um ou mais locais.
Caracteres curinga são permitidos.
O local padrão é o diretório atual (.).

```yaml
Type: System.String
Parameter Sets: PathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

## SAÍDAS

### System.Object

## OBSERVAÇÕES

## LINKS RELACIONADOS

[New-ScriptFileInfo](New-ScriptFileInfo.md)

[Publish-Script](Publish-Script.md)

[Update-ScriptFileInfo](Update-ScriptFileInfo.md)
