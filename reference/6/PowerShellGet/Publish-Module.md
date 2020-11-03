---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Module
ms.openlocfilehash: dd7721fbf482bca78823d9bad5b8f40f76b7d8bf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194301"
---
# Publish-Module

## SINOPSE
Publica um módulo especificado do computador local em uma galeria online.

## SYNTAX

### ModuleNameParameterSet (padrão)

```
Publish-Module -Name <String> [-RequiredVersion <String>] [-NuGetApiKey <String>]
 [-Repository <String>] [-Credential <PSCredential>] [-FormatVersion <Version>]
 [-ReleaseNotes <String[]>] [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>]
 [-ProjectUri <Uri>] [-Exclude <String[]>] [-Force] [-AllowPrerelease] [-SkipAutomaticTags]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ModulePathParameterSet

```
Publish-Module -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-FormatVersion <Version>] [-ReleaseNotes <String[]>]
 [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ProjectUri <Uri>] [-Force]
 [-SkipAutomaticTags] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Publish-Module` cmdlet publica um módulo em uma galeria online baseada em NuGet usando uma chave de API, armazenada como parte do perfil de um usuário na galeria. Você pode especificar o módulo a ser publicado usando o nome do módulo ou o caminho para a pasta que contém o módulo.

Quando você especifica um módulo por nome, `Publish-Module` o publica o primeiro módulo que seria encontrado executando `Get-Module -ListAvailable <Name>` . Se você especificar uma versão mínima de um módulo a ser publicado, `Publish-Module` o publicará o primeiro módulo com uma versão maior ou igual à versão mínima que você especificou.

A publicação de um módulo requer metadados que são exibidos na página da galeria para o módulo. Os metadados necessários incluem o nome, a versão, a descrição e o autor do módulo. Embora a maioria dos metadados seja obtida do manifesto do módulo, alguns metadados devem ser especificados em `Publish-Module` parâmetros, como **tag** , **ReleaseNote** , **IconUri** , **ProjectUri** e **LicenseUri** , porque esses parâmetros correspondem aos campos em uma galeria baseada em NuGet.

## EXEMPLOS

### Exemplo 1: publicar um módulo

Neste exemplo, MyDscModule é publicado na galeria online usando a chave de API para indicar a conta da galeria online do proprietário do módulo. Se MyDscModule não for um módulo de manifesto válido que especifica um nome, versão, descrição e autor, ocorrerá um erro.

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73"
```

### Exemplo 2: publicar um módulo com metadados da Galeria

Neste exemplo, MyDscModule é publicado na galeria online usando a chave de API para indicar a conta da galeria do proprietário do módulo. Os metadados adicionais fornecidos são exibidos na página da Web para o módulo na galeria. O proprietário adiciona duas marcas de pesquisa para o módulo, relacionando-o a Active Directory; uma breve nota de versão é adicionada. Se MyDscModule não for um módulo de manifesto válido que especifica um nome, versão, descrição e autor, ocorrerá um erro.

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73" -LicenseUri "http://contoso.com/license" -Tag "Active Directory","DSC" -ReleaseNote "Updated the ActiveDirectory DSC Resources to support adding users."
```

## PARAMETERS

### -AllowPrerelease

Permite que os módulos marcados como pré-lançamento sejam publicados.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Solicita a confirmação antes de executar o `Publish-Module` .

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

Especifica uma conta de usuário que tem direitos para publicar um módulo para um provedor de pacote ou origem especificado.

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

### -Excluir

Define os arquivos a serem excluídos do módulo publicado.

```yaml
Type: System.String[]
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FormatVersion

Aceita somente valores válidos especificados pelo atributo **ValidateSet** .

Para obter mais informações, consulte [declaração de atributo ValidateSet](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) e [ValidateSetAttribute](/dotnet/api/system.management.automation.validatesetattribute).

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:
Accepted values: 2.0

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IconUri

Especifica a URL de um ícone para o módulo. O ícone especificado é exibido na página da Web Galeria do módulo.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LicenseUri

Especifica a URL dos termos de licenciamento para o módulo que você deseja publicar.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica o nome do módulo que você deseja publicar. `Publish-Module` pesquisa o nome do módulo especificado em `$Env:PSModulePath` .

```yaml
Type: System.String
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NuGetApiKey

Especifica a chave de API que você deseja usar para publicar um módulo na galeria online. A chave de API é parte do seu perfil na galeria online e pode ser encontrada na página da sua conta de usuário na galeria. A chave de API é uma funcionalidade específica do NuGet.

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

Especifica o caminho para o módulo que você deseja publicar. Esse parâmetro aceita o caminho para a pasta que contém o módulo.

```yaml
Type: System.String
Parameter Sets: ModulePathParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProjectUri

Especifica a URL de uma página da Web sobre este projeto.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReleaseNotes

Especifica uma cadeia de caracteres contendo notas de versão ou comentários que você deseja disponibilizar para os usuários desta versão do módulo.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Repositório

Especifica o nome amigável de um repositório que foi registrado pela execução `Register-PSRepository` . O repositório deve ter um **PublishLocation** , que é um URI NuGet válido.
O **PublishLocation** pode ser definido executando `Set-PSRepository` .

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

### -RequiredVersion

Especifica a versão exata de um único módulo a ser publicado.

```yaml
Type: System.String
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipAutomaticTags

Remove comandos e recursos de serem incluídos como marcas. Ignora a adição automática de marcas a um módulo.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Marcas

Adiciona uma ou mais marcas ao módulo que você está publicando. As marcas de exemplo incluem DesiredStateConfiguration, DSC, DSCResourceKit ou PSModule. Separe várias marcas com vírgulas.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o `Publish-Module` for executado. O cmdlet não é executado.

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

`Publish-Module` é executado no PowerShell 3,0 ou versões posteriores do PowerShell, no Windows 7 ou Windows 2008 R2 e versões posteriores do Windows.

A publicação de um módulo requer metadados que são exibidos na página da galeria para o módulo. Os metadados necessários incluem o nome, a versão, a descrição e o autor do módulo. A maioria dos metadados é obtida do manifesto do módulo, mas alguns metadados podem ser especificados em `Publish-Module` parâmetros, como **tag** , **ReleaseNote** , **IconUri** , **ProjectUri** e **LicenseUri** . Para obter mais informações, veja [valores de manifesto de pacote que afetam a interface do usuário do Galeria do PowerShell](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui).

## LINKS RELACIONADOS

[Find-Module](Find-Module.md)

[Install-Module](Install-Module.md)

[Register-PSRepository](Register-PSRepository.md)

[Set-PSRepository](Set-PSRepository.md)

[Uninstall-Module](Uninstall-Module.md)

[Update-Module](Update-Module.md)
