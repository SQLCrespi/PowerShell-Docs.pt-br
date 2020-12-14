---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/04/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-dscresource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-DscResource
ms.openlocfilehash: 2596bf1789f4eb8c7c3983bf64f99ff0c1132b67
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890038"
---
# Find-DscResource

## SINOPSE
Localiza recursos de DSC (configuração de estado desejado).

## SYNTAX

### Tudo

```
Find-DscResource [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Find-DscResource` cmdlet procura repositórios registrados para localizar recursos de DSC contidos em módulos. Por padrão, o `Find-DscResource` pesquisa todos os repositórios registrados.

Para cada módulo encontrado por `Find-DscResource` , um objeto **PSGetDscResourceInfo** é retornado.
Os objetos **PSGetDscResourceInfo** podem ser enviados ao pipeline para o `Install-Module` cmdlet.
`Install-Module` instala o módulo.

## EXEMPLOS

### Exemplo 1: localizar todos os recursos de DSC

`Find-DscResource` Retorna recursos de DSC de repositórios registrados. Para pesquisar um repositório específico, use o parâmetro **Repository** .

```powershell
Find-DscResource
```

```Output
Name                           Version    ModuleName                     Repository
----                           -------    ----------                     ----------
Carbon_Privilege               2.8.1      Carbon                         PSGallery
Carbon_ScheduledTask           2.8.1      Carbon                         PSGallery
Carbon_Service                 2.8.1      Carbon                         PSGallery
PackageManagement              1.4        PackageManagement              PSGallery
PackageManagementSource        1.4        PackageManagement              PSGallery
PSModule                       2.1.4      PowerShellGet                  PSGallery
PSRepository                   2.1.4      PowerShellGet                  PSGallery
xArchive                       8.7.0.0    xPSDesiredStateConfiguration   PSGallery
xDSCWebService                 8.7.0.0    xPSDesiredStateConfiguration   PSGallery
xEnvironment                   8.7.0.0    xPSDesiredStateConfiguration   PSGallery
```

### Exemplo 2: localizar um recurso de DSC por nome

`Find-DscResource` localiza recursos de DSC por nome. Use vírgulas para separar uma matriz de nomes de recursos.

```powershell
Find-DscResource -Name xWebsite, xWebApplication, xWebSiteDefaults
```

```Output
Name               Version    ModuleName            Repository
----               -------    ----------            ----------
xWebApplication    2.6.0.0    xWebAdministration    PSGallery
xWebsite           2.6.0.0    xWebAdministration    PSGallery
xWebSiteDefaults   2.6.0.0    xWebAdministration    PSGallery
```

`Find-DscResource` usa o parâmetro **Name** para localizar a matriz especificada de recursos de DSC.

### Exemplo 3: localizar um recurso de DSC e instalá-lo

`Find-DscResource` localiza um recurso de DSC e envia o objeto para baixo no pipeline a ser instalado.
Após a instalação, use `Get-InstalledModule` para exibir os resultados.

Vários recursos do mesmo módulo podem ser enviados para o pipeline para o `Install-Module` .
`Install-Module` tenta instalar o módulo apenas uma vez.

```powershell
Find-DscResource -Name xWebsite | Install-Module
```

`Find-DscResource` usa o parâmetro **Name** para localizar o recurso chamado **xWebsite**. O objeto é enviado ao pipeline para o `Install-Module` cmdlet. `Install-Module` instala o módulo **xWebAdministration** para o recurso.

### Exemplo 4: localizar todos os recursos de DSC em um módulo

`Find-DscResource` localiza todos os recursos de DSC contidos em um módulo especificado. Por padrão, a versão atual é exibida. Para exibir outras versões, use os parâmetros **RequiredVersions** ou **getversions** .

```powershell
Find-DscResource -ModuleName xWebAdministration
```

```Output
Name                                Version    ModuleName              Repository
----                                -------    ----------              ----------
WebApplicationHandler               2.6.0.0    xWebAdministration      PSGallery
xIisFeatureDelegation               2.6.0.0    xWebAdministration      PSGallery
xIisHandler                         2.6.0.0    xWebAdministration      PSGallery
xIisLogging                         2.6.0.0    xWebAdministration      PSGallery
```

`Find-DscResource` usa o parâmetro **ModuleName** para especificar o **xWebAdministration** e localizar os recursos de DSC contidos no módulo. A versão atual de cada recurso é exibida.

### Exemplo 5: localizar um recurso de DSC por marca e versão necessária

Os recursos de DSC podem ser localizados usando a **marca** de parâmetros e **RequiredVersion**. **Marca** exibe a versão atual de cada recurso que contém a marca especificada no repositório.
**RequiredVersion** precisa do parâmetro **ModuleName** e o parâmetro **Name** é opcional. Os parâmetros **Name** e **ModuleName** limitam a saída. Use o parâmetro **Perversions** para exibir as versões disponíveis de um recurso de DSC.

```powershell
Find-DscResource -ModuleName xWebAdministration -Tag DSC -RequiredVersion 1.20
```

```output
Name                    Version    ModuleName             Repository
----                    -------    ----------             ----------
xIisFeatureDelegation   1.20.0.0   xWebAdministration     PSGallery
xIisHandler             1.20.0.0   xWebAdministration     PSGallery
xIisLogging             1.20.0.0   xWebAdministration     PSGallery
xIisMimeTypeMapping     1.20.0.0   xWebAdministration     PSGallery
```

### Exemplo 6: localizar um recurso usando um filtro

`Find-DscResource` localiza todos os recursos e usa o parâmetro de **filtro** para especificar os resultados por **domínio**. O parâmetro **Filter** localiza o valor do filtro na descrição do objeto ou no nome do módulo. Use o `Select-Object` cmdlet para exibir as propriedades de um objeto.

```powershell
Find-DscResource -Filter Domain
```

```output
Name                    Version    ModuleName                 Repository
----                    -------    ----------                 ---------
xComputer               4.1.0.0    xComputerManagement        PSGallery
Computer                6.4.0.0    ComputerManagementDsc      PSGallery
xDSCDomainjoin          1.1        xDSCDomainjoin             PSGallery
xDisk                   1.0        xDisk                      PSGallery
xDSCFirewall            1.6.21     xDSCFirewall               PSGallery
dmAwsTagInstance        1.0.1      domainAwsDSCResources      PSGallery
```

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

O parâmetro **Perversions** exibe cada uma das versões disponíveis de um recurso de DSC. Você não pode usar o parâmetro de todas as **versões** com os parâmetros **MinimumVersion**, **MaximumVersion** ou **RequiredVersion** .

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

Especifica a versão máxima do recurso a ser incluído nos resultados. Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.

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

Especifica a versão mínima do recurso para incluir nos resultados. Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.

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

Especifica um módulo que contém o recurso de DSC.

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

Especifica o nome de um recurso. O padrão é todos os recursos. Use vírgulas para separar uma matriz de nomes de recursos.

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

Especifica um repositório para pesquisar recursos. Use vírgulas para separar uma matriz de nomes de repositório.

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

### PSGetDscResourceInfo

`Find-DscResource` Retorna um objeto **PSGetDscResourceInfo** .

## OBSERVAÇÕES

> [!IMPORTANT]
> A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS). Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell. Use o comando a seguir para garantir que você esteja usando o TLS 1,2:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.

## LINKS RELACIONADOS

[Get-InstalledModule](Get-InstalledModule.md)

[Install-Module](Install-Module.md)

[Register-PSRepository](Register-PSRepository.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Desinstalar-módulo](Uninstall-Module.md)
