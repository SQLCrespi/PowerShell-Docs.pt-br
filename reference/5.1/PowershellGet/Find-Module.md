---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Module
ms.openlocfilehash: b30e233eb9c4f4f9191ac6470f2821536dda6dc3
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94889820"
---
# Find-Module

## SINOPSE
Localiza módulos em um repositório que corresponde aos critérios especificados.

## SYNTAX

### Tudo

```
Find-Module [[-Name] <string[]>] [-MinimumVersion <string>] [-MaximumVersion <string>]
 [-RequiredVersion <string>] [-AllVersions] [-IncludeDependencies] [-Filter <string>]
 [-Tag <string[]>] [-Includes <string[]>] [-DscResource <string[]>] [-RoleCapability <string[]>]
 [-Command <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Repository <string[]>]
 [-Credential <pscredential>] [-AllowPrerelease] [<CommonParameters>]
```

## DESCRIPTION

O `Find-Module` cmdlet localiza módulos em um repositório que corresponde aos critérios especificados.
`Find-Module` Retorna um objeto **PSRepositoryItemInfo** para cada módulo que encontrar. Os objetos podem ser enviados ao pipeline para cmdlets como `Install-Module` .

Na primeira vez que o `Find-Module` tentar usar um repositório, você poderá ser solicitado a instalar atualizações.
Se a origem do repositório não estiver registrada com o `Register-PSRepository` cmdlet, um erro será retornado.

`Find-Module` Retorna a versão mais recente de um módulo se nenhum parâmetro for usado para limitar a versão. Para obter uma lista de um repositório de versões de um módulo, use o **parâmetro AllModules**.

Se o parâmetro **MinimumVersion** for especificado, `Find-Module` retornará a versão do módulo que é igual ou maior que o mínimo. Se houver uma versão mais recente disponível no repositório, a versão mais recente será retornada.

Se o parâmetro **MaximumVersion** for especificado, `Find-Module` retornará a versão mais recente do módulo que não exceda a versão especificada.

Se o parâmetro **RequiredVersion** for especificado, `Find-Module` retornará apenas a versão do módulo que é uma correspondência exata com a versão especificada. `Find-Module` pesquisa todos os módulos disponíveis, pois podem ocorrer conflitos de nome entre origens.

Os exemplos a seguir usam o [Galeria do PowerShell](https://www.powershellgallery.com/) como o único repositório registrado. `Get-PSRepository` exibe os repositórios registrados. Se você tiver vários repositórios registrados, use o `-Repository` parâmetro para especificar o nome do repositório.

## EXEMPLOS

### Exemplo 1: localizar um módulo por nome

Este exemplo localiza um módulo no repositório padrão.

```powershell
Find-Module -Name PowerShellGet
```

```Output
Version   Name              Repository           Description
-------   ----              ----------           -----------
2.1.0     PowerShellGet     PSGallery            PowerShell module with commands for discovering...
```

O `Find-Module` cmdlet usa o parâmetro **Name** para especificar o módulo **PowerShellGet** .

### Exemplo 2: localizar módulos com nomes semelhantes

Este exemplo usa o curinga asterisco ( `*` ) para localizar módulos com nomes semelhantes.

```powershell
Find-Module -Name PowerShell*
```

```Output
Version   Name                            Repository    Description
-------   ----                            ----------    -----------
0.4.0     powershell-yaml                 PSGallery     Powershell module for serializing and...
2.1.0     PowerShellGet                   PSGallery     PowerShell module with commands for...
1.9       Powershell.Helper.Extension     PSGallery     # Powershell.Helper.Extension...
3.1       PowerShellHumanizer             PSGallery     PowerShell Humanizer wraps Humanizer...
4.0       PowerShellISEModule             PSGallery     a module that adds capability to the ISE
```

O `Find-Module` cmdlet usa o parâmetro **Name** com o curinga asterisco ( `*` ) para localizar todos os módulos que contêm o **PowerShell**.

### Exemplo 3: localizar um módulo por versão mínima

Este exemplo pesquisa a versão mínima de um módulo. Se o repositório contiver uma versão mais recente do módulo, a versão mais recente será retornada.

```powershell
Find-Module -Name PowerShellGet -MinimumVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

O `Find-Module` cmdlet usa o parâmetro **Name** para especificar o módulo **PowerShellGet** . **MinimumVersion** especifica a versão **1.6.5**. `Find-Module` Retorna o PowerShellGet versão **2.1.0** porque ele excede a versão mínima e é a versão mais atual.

### Exemplo 4: localizar um módulo por versão específica

Este exemplo retorna um objeto que representa a versão específica de um módulo. Se a versão especificada não for encontrada, um erro será retornado.

```powershell
Find-Module -Name PowerShellGet -RequiredVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
1.6.5     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

O `Find-Module` cmdlet usa o parâmetro **Name** para especificar o módulo **PowerShellGet** . O parâmetro **RequiredVersion** especifica a versão **1.6.5**.

### Exemplo 5: localizar um módulo em um repositório específico

Este exemplo usa o parâmetro **Repository** para localizar um módulo em um repositório específico.

```powershell
Find-Module -Name PowerShellGet -Repository PSGallery
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

O `Find-Module` cmdlet usa o parâmetro **Name** para especificar o módulo **PowerShellGet** . O parâmetro **Repository** especifica a pesquisa no repositório **PSGallery** .

### Exemplo 6: localizar um módulo em vários repositórios

Este exemplo usa o `Register-PSRepository` para especificar um repositório. `Find-Module` usa o repositório para pesquisar um módulo.

```powershell
Register-PSRepository -Name MySource -SourceLocation https://www.myget.org/F/powershellgetdemo/
Find-Module -Name Contoso* -Repository PSGallery, MySource
```

```Output
Repository    Version   Name             Description
----------    -------   ----             -----------
PSGallery     2.0.0.0   ContosoServer    Cmdlets and DSC resources for managing Contoso Server...
MySource      1.2.0.0   ContosoClient    Cmdlets and DSC resources for managing Contoso Client...
```

O `Register-PSRepository` cmdlet registra um novo repositório. O parâmetro **Name** atribui o nome **MySource**. O parâmetro **SourceLocation** especifica o endereço do repositório.

O `Find-Module` cmdlet usa o parâmetro **Name** com o curinga asterisco ( `*` ) para especificar o módulo **contoso** . O parâmetro **Repository** especifica a pesquisa de dois repositórios, **PSGallery** e **MySource**.

### Exemplo 7: localizar um módulo que contém um recurso de DSC

Esse comando retorna módulos que contêm recursos de DSC. O parâmetro **includes** tem quatro funcionalidades predefinidas que são usadas para pesquisar o repositório. Use Tab-Complete para exibir as quatro funcionalidades com suporte no parâmetro **includes** .

```powershell
Find-Module -Repository PSGallery -Includes DscResource
```

```Output
Version     Name                            Repository    Description
-------     ----                            ----------    -----------
2.7.0       Carbon                          PSGallery     Carbon is a PowerShell module...
8.5.0.0     xPSDesiredStateConfiguration    PSGallery     The xPSDesiredStateConfiguration module...
1.3.1       PackageManagement               PSGallery     PackageManagement (a.k.a. OneGet) is...
2.7.0.0     xWindowsUpdate                  PSGallery     Module with DSC Resources...
3.2.0.0     xCertificate                    PSGallery     This module includes DSC resources...
3.1.0.0     xPowerShellExecutionPolicy      PSGallery     This DSC resource can change the user...
```

O `Find-Module` cmdlet usa o parâmetro **Repository** para pesquisar o repositório, **PSGallery**.
O parâmetro **includes** especifica **DscResource**, que é uma funcionalidade que o parâmetro pode pesquisar no repositório.

### Exemplo 8: localizar um módulo com um filtro

Neste exemplo, para localizar módulos, um filtro é usado para pesquisar o repositório.

Para um repositório baseado em NuGet, o parâmetro de **filtro** pesquisa o nome, a descrição e as marcas do argumento.

```powershell
Find-Module -Filter AppDomain
```

```Output
Version    Name              Repository           Description
-------    ----              ----------           -----------
1.0.0.0  AppDomainConfig     PSGallery            Manipulate AppDomain configuration...
1.1.0    ClassExplorer       PSGallery            Quickly search the AppDomain for classes...
```

O `Find-Module` cmdlet usa o parâmetro **Filter** para pesquisar no repositório o **AppDomain**.

## PARAMETERS

### -AllowPrerelease

Inclui nos módulos de resultados marcados como um pré-lançamento.

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

Especifica para incluir todas as versões de um módulo nos resultados. Você não pode usar o parâmetro de todas as **versões** com os parâmetros **MinimumVersion**, **MaximumVersion** ou **RequiredVersion** .

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

### -Command

Especifica uma matriz de comandos para localizar em módulos. Um comando pode ser uma função ou um fluxo de trabalho.

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

### -Credential

Especifica uma conta de usuário que tem direitos para instalar um módulo para um provedor de pacote ou origem especificado.

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

### -DscResource

Especifica o nome, ou parte do nome, dos módulos que contêm recursos de DSC. Por convenções do PowerShell, o executa uma pesquisa **ou** quando você fornece vários argumentos.

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

### -Filter

Especifica um filtro com base na sintaxe de pesquisa específica do provedor **PackageManagement** . Para módulos NuGet, esse parâmetro é o equivalente de Pesquisar usando a barra de pesquisa no site [Galeria do PowerShell](https://www.powershellgallery.com/) .

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

### -IncludeDependencies

Indica que essa operação inclui todos os módulos que dependem do módulo especificado no parâmetro **Name** .

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

### -Inclui

Retorna somente os módulos que incluem tipos específicos de funcionalidade do PowerShell. Por exemplo, talvez você queira apenas localizar módulos que incluem **DSCResource**. Os valores aceitáveis para esse parâmetro são os seguintes:

- Cmdlet
- DscResource
- Função
- RoleCapability

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: DscResource, Cmdlet, Function, RoleCapability

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumVersion

Especifica a versão máxima ou mais recente do módulo a ser incluída nos resultados da pesquisa.
**MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.

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

### -MinimumVersion

Especifica a versão mínima do módulo a ser incluída nos resultados. **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.

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

Especifica os nomes dos módulos a serem pesquisados no repositório. Uma lista separada por vírgulas de nomes de módulo é aceita. Caracteres curinga são aceitos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Proxy

Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.

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

Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**.

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

Use o parâmetro **Repository** para especificar qual repositório procurar um módulo. Usado quando vários repositórios são registrados. Aceita uma lista separada por vírgulas de repositórios. Para registrar um repositório, use `Register-PSRepository` . Para exibir repositórios registrados, use `Get-PSRepository` .

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

Especifica o número de versão exato do módulo a ser incluído nos resultados. **RequiredVersion** não pode ser usado no mesmo comando que **MinimumVersion** ou **MaximumVersion**.

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

### -RoleCapability

Especifica uma matriz de recursos de função.

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

### -Tag

Especifica uma matriz de marcas. As marcas de exemplo incluem **DesiredStateConfiguration**, **DSC**, **DSCResourceKit** ou **PSModule**.

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

### PSRepositoryItemInfo

`Find-Module` cria objetos **PSRepositoryItemInfo** que podem ser enviados ao pipeline para cmdlets como `Install-Module` .

## OBSERVAÇÕES

> [!IMPORTANT]
> A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS). Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell. Use o comando a seguir para garantir que você esteja usando o TLS 1,2:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.

## LINKS RELACIONADOS

[Get-PSRepository](Get-PSRepository.md)

[Install-Module](Install-Module.md)

[Publish-Module](Publish-Module.md)

[Save-Module](Save-Module.md)

[Uninstall-Module](Uninstall-Module.md)

[Update-Module](Update-Module.md)

[Register-PSRepository](Register-PSRepository.md)
