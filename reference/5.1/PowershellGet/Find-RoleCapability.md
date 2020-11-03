---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/05/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-rolecapability?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-RoleCapability
ms.openlocfilehash: c7392423f4b915716ed1ef911fcfddd215337639
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193619"
---
# Find-RoleCapability

## SINOPSE
Localiza capacidades de função em módulos.

## SYNTAX

### Tudo

```
Find-RoleCapability [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>] 
[-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease] 
[-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] 
[-Repository <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Find-RoleCapability` cmdlet procura repositórios registrados para encontrar recursos e módulos de função do PowerShell.

Para cada recurso de função encontrado pelo `Find-RoleCapability` , um objeto **PSGetRoleCapabilityInfo** é retornado. Os objetos **PSGetRoleCapabilityInfo** podem ser enviados para o pipeline para `Install-Module` os `Save-Module` cmdlets ou.

Os recursos de função do PowerShell definem quais comandos e aplicativos estão disponíveis para um usuário em um ponto de extremidade de administração JEA (apenas suficiente). Os recursos de função são definidos por arquivos com uma `.psrc` extensão.

## EXEMPLOS

### Exemplo 1: localizar recursos de função

`Find-RoleCapability` localiza recursos de função em cada repositório registrado. Para pesquisar um repositório específico, use o parâmetro **Repository** .

```powershell
Find-RoleCapability
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
General-Lev2     1.0        JeaExamples    PSGallery
IIS-Lev1         1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### Exemplo 2: localizar recursos de função por nome

`Find-RoleCapability` localiza recursos de função por nome. Use vírgulas para separar uma matriz de nomes.

```powershell
Find-RoleCapability -Name General-Lev1, IIS-Lev2
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### Exemplo 3: localizar e salvar um módulo de capacidade de função

O `Find-RoleCapability` cmdlet encontra um recurso de função e envia o objeto para baixo do pipeline.
`Save-Module` salva o módulo da capacidade da função em um sistema de arquivos. `Get-ChildItem` exibe o conteúdo do diretório do módulo.

```
PS> Find-RoleCapability -Name General-Lev1 | Save-Module -Path C:\Test\Modules

PS> Get-ChildItem -Path C:\Test\Modules\JeaExamples\1.0\

    Directory: C:\Test\Modules\JeaExamples\1.0

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----          6/4/2019    16:37                RoleCapabilities
-a----          2/5/2019    18:46           1702 CreateRegisterPSSC.ps1
-a----          2/5/2019    18:46           7656 JeaExamples.psd1
-a----         10/1/2018    08:16            595 JeaExamples.psm1
```

`Find-RoleCapability` usa o parâmetro **Name** para especificar a capacidade de função **geral-Lev1** .
O objeto é enviado pelo pipeline. `Save-Module` usa o parâmetro **path** para o local do sistema de arquivos para salvar o módulo. Depois que o módulo é salvo, `Get-ChildItem` especifica o **caminho** do módulo e exibe o conteúdo do diretório do módulo **JeaExamples** .

### Exemplo 4: localizar e instalar um módulo de capacidade de função

`Find-RoleCapability` localiza o módulo e envia o objeto para baixo do pipeline. `Install-Module` instala o módulo. Após a instalação, use `Get-InstalledModule` para ver os resultados.

```
PS> Find-RoleCapability -Name General-Lev1 | Install-Module -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/JeaExamples/1.0.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/JeaExamples/1.0.0'.
VERBOSE: Completed downloading 'JeaExamples'.
VERBOSE: InstallPackageLocal' - name='JeaExamples', version='1.0',
VERBOSE: Validating the 'JeaExamples' module contents
VERBOSE: Test-ModuleManifest successfully validated the module manifest file
VERBOSE: Module 'JeaExamples' was installed successfully to path

PS> Get-InstalledModule

Version    Name            Repository     Description
-------    ----            ----------     -----------
1.0        JeaExamples     PSGallery      Some example Jea roles for general server maintenance...
```

`Find-RoleCapability` usa o parâmetro **Name** para especificar a capacidade de função **geral-Lev1** .
O objeto é enviado pelo pipeline. `Install-Module` usa o parâmetro **Verbose** para exibir mensagens de status durante a instalação. Após a conclusão da instalação, a `Get-InstalledModule` saída confirma que o módulo **JeaExamples** foi instalado.

## PARAMETERS

### -AllowPrerelease

Inclui recursos marcados como um pré-lançamento nos resultados.

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

### -Próprias versões

Indica que este cmdlet obtém todas as versões de um módulo. O **parâmetro** AllModules exibe cada uma das versões disponíveis de um módulo.

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

### -Filter

Localiza recursos com base na sintaxe de pesquisa do provedor de **PackageManagement** . Por exemplo, especifique as palavras a serem pesquisadas nas propriedades **ModuleName** e **Description** .

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

### -MaximumVersion

Especifica a versão máxima do módulo a ser incluída nos resultados. Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.

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

### -MinimumVersion

Especifica a versão mínima do módulo a ser incluída nos resultados. Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.

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

### -ModuleName

Especifica o nome do módulo no qual Pesquisar recursos de função. O padrão é todos os módulos.

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

### -Name

Especifica o nome de uma capacidade de função. O padrão é todos os recursos de função. Use vírgulas para separar uma matriz de nomes de recursos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxy

Especifica um servidor proxy para a solicitação, em vez de uma conexão direta com o recurso da Internet.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyCredential

Especifica uma conta de usuário com permissão para usar o servidor proxy especificado no parâmetro **proxy** .

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

### -Repositório

Especifica um repositório para procurar recursos de função. Use vírgulas para separar uma matriz de nomes de repositório.

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

### -RequiredVersion

Especifica o número de versão exato do módulo a ser incluído nos resultados. Os parâmetros **RequiredVersion** e **MinimumVersion** não podem ser usados no mesmo comando.

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

### -Tag

Especifica as marcas que categorizam os módulos em um repositório. Use vírgulas para separar uma matriz de marcas.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

## SAÍDAS

### PSGetRoleCapabilityInfo

O `Find-RoleCapability` cmdlet retorna um objeto **PSGetRoleCapabilityInfo** .

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[Get-InstalledModule](Get-InstalledModule.md)

[Install-Module](Install-Module.md)

[New-PSRoleCapabilityFile](../Microsoft.PowerShell.Core/New-PSRoleCapabilityFile.md)

[Save-Module](Save-Module.md)
