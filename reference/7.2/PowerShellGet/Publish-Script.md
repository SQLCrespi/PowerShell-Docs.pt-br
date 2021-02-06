---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Script
ms.openlocfilehash: 344a789c9daced51b549d562b7fd74677fe403dc
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99597183"
---
# Publish-Script

## SINOPSE
Publica um script.

## SYNTAX

### PathParameterSet (padrão)

```
Publish-Script -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPathParameterSet

```
Publish-Script -LiteralPath <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Publish-Script` cmdlet publica o script especificado na galeria online.

## EXEMPLOS

### Exemplo 1: criar um arquivo de script, adicionar conteúdo a ele e publicá-lo

O `New-ScriptFileInfo` cmdlet cria um arquivo de script chamado `Demo-Script.ps1` . `Get-Content` exibe o conteúdo de `Demo-Script.ps1` . O `Add-Content` cmdlet adiciona uma função e um fluxo de trabalho ao `Demo-Script.ps1` .

```powershell
$newScriptInfo = @{
  Path = 'D:\ScriptSharingDemo\Demo-Script.ps1'
  Version = '1.0'
  Author = 'author@contoso.com'
  Description = "my test script file description goes here"
}
New-ScriptFileInfo @newScriptInfo
Get-Content -Path $newScriptInfo.Path
```

```Output
<#PSScriptInfo

.VERSION 1.0

.AUTHOR pattif@microsoft.com

.COMPANYNAME

.COPYRIGHT

.TAGS

.LICENSEURI

.PROJECTURI

.ICONURI

.EXTERNALMODULEDEPENDENCIES

.REQUIREDSCRIPTS

.EXTERNALSCRIPTDEPENDENCIES

.RELEASENOTES
#>

<#
.DESCRIPTION
 my test script file description goes here
#>
Param()
```

```powershell
Add-Content -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Value @"

Function Demo-ScriptFunction { 'Demo-ScriptFunction' }

Workflow Demo-ScriptWorkflow { 'Demo-ScriptWorkflow' }

Demo-ScriptFunction
Demo-ScriptWorkflow
"@
Test-ScriptFileInfo -Path D:\ScriptSharingDemo\Demo-Script.ps1
```

```Output
Version    Name                 Author                   Description
-------    ----                 ------                   -----------
1.0        Demo-Script          author@contoso.com       my test script file description goes here
```

```powershell
Publish-Script -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Repository LocalRepo1
Find-Script -Repository LocalRepo1 -Name "Demo-Script"
```

```Output
Version    Name                 Type       Repository    Description
-------    ----                 ----       ----------    -----------
1.0        Demo-Script          Script     LocalRepo1    my test script file description goes here
```

O `Test-ScriptFileInfo` cmdlet é validado `Demo-Script.ps1` . O `Publish-Script` cmdlet publica o script no repositório **LocalRepo1** . Por fim. `Find-Script` é usado para pesquisar `Demo-Script.ps1` no repositório **LocalRepo1** .

## PARAMETERS

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

### -Credential

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

Força o comando a ser executado sem solicitar a confirmação do usuário.

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

### -LiteralPath

Especifica um caminho para um ou mais locais. Ao contrário do parâmetro **path** , o valor do parâmetro **LiteralPath** é usado exatamente como inserido. Nenhum caractere é interpretado como caractere curinga. Se o caminho incluir caracteres de escape, coloque-os entre aspas simples. As aspas simples instruem o Windows PowerShell a nunca interpretar caracteres como sequências de escape.

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

### -NuGetApiKey

Especifica a chave de API que você deseja usar para publicar um script na galeria online. A chave de API é parte do seu perfil na galeria online. Para obter mais informações, consulte [Gerenciando chaves de API](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica um caminho para um ou mais locais. Caracteres curinga são permitidos. O local padrão é o diretório atual.

```yaml
Type: System.String
Parameter Sets: PathParameterSet
Aliases:

Required: True
Position: Named
Default value: <Current location>
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Repositório

Especifica o nome amigável de um repositório que foi registrado pela execução `Register-PSRepository` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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

### System.String

### System. Management. Automation. PSCredential

## SAÍDAS

### System.Object

## OBSERVAÇÕES

> [!IMPORTANT]
> A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS. Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell. Use o seguinte comando para garantir que esteja usando o TLS 1.2:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.

## LINKS RELACIONADOS

[Find-Script](Find-Script.md)

[Install-Script](Install-Script.md)

[Publish-Script](Publish-Script.md)

[Save-Script](Save-Script.md)

[Update-Script](Update-Script.md)
