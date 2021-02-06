---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 05/22/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Package
ms.openlocfilehash: c26365eb5b4833c4982fa54e742521cf72307e99
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99595562"
---
# Get-Package

## SINOPSE
Retorna uma lista de todos os pacotes de software que foram instalados com o **PackageManagement**.

## SYNTAX

### NuGet

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### PowerShellGet

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Scope <String>] [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions]
 [<CommonParameters>]
```

## DESCRIPTION

O `Get-Package` cmdlet retorna uma lista de todos os pacotes de software no computador local que foram instalados com o **PackageManagement**. Você pode executar `Get-Package` em computadores remotos executando-o como parte de `Invoke-Command` um `Enter-PSSession` comando ou script.

## EXEMPLOS

### Exemplo 1: obter todos os pacotes instalados

O `Get-Package` cmdlet obtém todos os pacotes que estão instalados no computador local.

```powershell
Get-Package
```

```Output
Name           Version      Source                                     ProviderName
----           -------      ------                                     ------------
posh-git       0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
```

### Exemplo 2: obter pacotes que estão instalados em um computador remoto

Esse comando obtém uma lista de pacotes que foram instalados pelo **PackageManagement** em um computador remoto. Esse comando solicita que você forneça a senha do usuário especificado.

```
PS> Invoke-Command -ComputerName Server01 -Credential CONTOSO\TestUser -ScriptBlock {Get-Package}
```

`Invoke-Command` usa o parâmetro **ComputerName** para especificar um computador remoto, **Server01**. O parâmetro **Credential** especifica um domínio e um nome de usuário com permissões para executar comandos no computador. O parâmetro **scriptblock** executa o `Get-Package` cmdlet no computador remoto.

### Exemplo 3: obter pacotes para um provedor especificado

Esse comando obtém os pacotes de software instalados no computador local a partir de um provedor específico.

```powershell
Get-Package -ProviderName PowerShellGet -AllVersions
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.2.2        https://www.powershellgallery.com/api/v2   PowerShellGet
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
posh-git              0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
PowerShellGet         2.0.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

`Get-Package` usa o parâmetro **ProviderName** para especificar um provedor específico, **PowerShellGet**.
O parâmetro **todas as versões** exibe cada versão instalada.

### Exemplo 4: obter uma versão exata de um pacote específico

Esse comando obtém uma versão específica de um pacote instalado. Mais de uma versão de um pacote pode ser instalada.

```powershell
Get-Package -Name PackageManagement -ProviderName PowerShellGet -RequiredVersion 1.3.1
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

`Get-Package` usa o parâmetro **Name** para especificar o nome do pacote, **PackageManagement**. O parâmetro **ProviderName** especifica o provedor, **PowerShellGet**. O parâmetro **-version obrigatório** especifica uma versão instalada.

### Exemplo 5: desinstalar um pacote

Este exemplo obtém informações do pacote e, em seguida, desinstala o pacote.

```powershell
Get-Package -Name posh-git -RequiredVersion 0.7.3 | Uninstall-Package
```

`Get-Package` usa o parâmetro **Name** para especificar o nome do pacote, **Posh-git**. O parâmetro **RequiredVersion** é uma versão específica do pacote. O objeto é enviado ao pipeline para o `Uninstall-Package` cmdlet. `Uninstall-Package` Remove o pacote.

## PARAMETERS

### -AllowClobber

Substitui mensagens de aviso sobre conflitos com comandos existentes. Substitui os comandos existentes que têm o mesmo nome que os comandos que estão sendo instalados por um módulo.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowPrereleaseVersions

Inclui pacotes marcados como um pré-lançamento nos resultados.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Próprias versões

Indica que o `Get-Package` retorna todas as versões disponíveis do pacote. Por padrão, `Get-Package` o retorna apenas a versão mais recente disponível.

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

### -Destino

Especifica o caminho para um diretório que contém arquivos de pacote extraídos.

```yaml
Type: System.String
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeVersion

Alterne para excluir o número de versão no caminho da pasta.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceBootstrap

Indica que `Get-Package` o **PackageManagement** é forçado a instalar automaticamente o provedor de pacotes.

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

### -InstallUpdate

Indica que esse cmdlet instala atualizações.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumVersion

Especifica a versão máxima do pacote que você deseja localizar.

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

Especifica a versão mínima do pacote que você deseja localizar. Se uma versão superior estiver disponível, essa versão será retornada.

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

Especifica um ou mais nomes de pacote ou nomes de pacote com caracteres curinga. Separe vários nomes de pacote com vírgulas.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -NoPathUpdate

**NoPathUpdate** se aplica somente ao `Install-Script` cmdlet. **NoPathUpdate** é um parâmetro dinâmico adicionado pelo provedor e não é suportado pelo `Get-Package` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageManagementProvider

Especifica o nome de um provedor de gerenciamento de pacotes.

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderName

Especifica um ou mais nomes de provedor de pacote. Separe vários nomes de provedor de pacote com vírgulas.
Use `Get-PackageProvider` para obter uma lista de provedores de pacotes disponíveis.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequiredVersion

Especifica a versão exata do pacote a ser localizado.

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

### -Escopo

Especifica o escopo de pesquisa para o pacote.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipDependencies

Opção que especifica para ignorar a localização de qualquer dependência de pacote.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipPublisherCheck

Permite obter uma versão de pacote mais nova do que a versão instalada. Por exemplo, um pacote instalado que é assinado digitalmente por um fornecedor confiável, mas uma nova versão não é assinada digitalmente.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type

Especifica se os pacotes devem ser pesquisados com um módulo, um script ou um.

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:
Accepted values: Module, Script, All

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

### SoftwareIdentity[]

## OBSERVAÇÕES

A inclusão de um provedor de pacote em um comando pode tornar os parâmetros dinâmicos disponíveis para um cmdlet. Parâmetros dinâmicos são específicos para um provedor de pacote. O `Get-Help` cmdlet lista os conjuntos de parâmetros de um cmdlet e inclui o conjunto de parâmetros do provedor. Por exemplo, `Get-Package` tem o conjunto de parâmetros **PowerShellGet** que inclui `-NoPathUpdate` , `AllowClobber` e `SkipPublisherCheck` .

> [!IMPORTANT]
> A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS. Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell. Use o seguinte comando para garantir que esteja usando o TLS 1.2:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.

## LINKS RELACIONADOS

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Enter-PSSession](../Microsoft.PowerShell.Core/Enter-PSSession.md)

[Find-Package](Find-Package.md)

[Get-Help](../Microsoft.PowerShell.Core/Get-Help.md)

[Get-PackageProvider](Get-PackageProvider.md)

[Get-PackageSource](Get-PackageSource.md)

[Install-Package](Install-Package.md)

[Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)

[Save-Package](Save-Package.md)

[Uninstall-Package](Uninstall-Package.md)
