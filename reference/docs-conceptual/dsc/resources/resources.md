---
ms.date: 07/23/2020
keywords: DSC,powershell,configuração,instalação
title: Recursos de DSC
description: Os recursos de DSC fornecem os blocos de construção para uma configuração DSC. Um recurso expõe propriedades que podem ser configuradas (esquema) e contém as funções de script do PowerShell usadas pelo LCM para aplicar a configuração.
ms.openlocfilehash: 33268c68638bb581e0b2235a53aee9d186dff6be
ms.sourcegitcommit: 0f003644684422e425a59b7361121e05ac772e15
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98771792"
---
# <a name="dsc-resources"></a>Recursos de DSC

> Aplica-se ao Windows PowerShell 4.0 e posterior.

## <a name="overview"></a>Visão geral

Os Recursos de Configuração de Estado Desejado (DSC) fornecem os blocos de construção para uma configuração DSC. Um recurso expõe propriedades que podem ser configuradas (esquema) e contém as funções de script do PowerShell que o Gerenciador de Configurações Local (LCM) chama de "realizar".

Um recurso pode modelar algo tão genérico quanto um arquivo ou tão específico quanto uma configuração de servidor do IIS. Grupos de recursos semelhantes são combinados em um Módulo de DSC, que organiza todos os arquivos necessários em uma estrutura que é portátil e inclui metadados para identificar como os recursos devem ser usados.

Cada recurso tem um *esquema que determina a sintaxe necessária para usar o recurso em uma [Configuração](../configurations/configurations.md). Um esquema de recurso pode ser definido das seguintes maneiras:

- Arquivo `Schema.Mof`: A maioria dos recursos define seus _esquemas_ em um arquivo `schema.mof` usando um [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).
- Arquivo `<Resource Name>.schema.psm1`: [Recursos de composição](../configurations/compositeConfigs.md) definem o _esquema_ em um arquivo `<ResourceName>.schema.psm1` usando um [bloco de parâmetro](/powershell/module/microsoft.powershell.core/about/about_functions#functions-with-parameters).
- Arquivo `<Resource Name>.psm1`: Recursos DSC baseado em classe definem seus _esquemas_ na definição da classe. Os itens de sintaxe são indicados como propriedades de Classe. Para saber mais, confira [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).

Para recuperar a sintaxe para um recurso DSC, use o cmdlet [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) com o parâmetro **Syntax**. Esse uso é semelhante ao uso de [Get-Command](/powershell/module/microsoft.powershell.core/get-command) com o parâmetro **Syntax** para obter a sintaxe do cmdlet. A saída que você vê mostrará o modelo usado para um bloco de recursos do recurso que você especificar.

```powershell
Get-DscResource -Syntax Service
```

A saída que você vê deve ser semelhante à saída abaixo, embora a sintaxe deste recurso possa ser alterada no futuro. Como a sintaxe do cmdlet, as _chaves_ vistas entre colchetes são opcionais. Os tipos especificam o tipo de dados esperado de cada chave.

> [!NOTE]
> A chave **Garantir** é opcional porque o padrão é "Presente".

```output
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

> [!NOTE]
> Nas versões do PowerShell antes de 7.0, `Get-DscResource` não encontra recursos de DSC baseados em classe.

Dentro de uma Configuração, um bloco de recursos de **Serviço** poderia se parecer com isso para **Garantir** que o serviço de Spooler está em execução.

> [!NOTE]
> Antes de usar um recurso em uma configuração, você deve importá-lo usando [Import-DSCResource](../configurations/import-dscresource.md).

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the
    # resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as l
        # ong as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }
    }
}
```

Configurações podem conter várias instâncias do mesmo tipo de recurso. Cada instância deve ter um nome exclusivo. No exemplo a seguir, um segundo bloco de recurso de **Serviço** é adicionado ao configurar o serviço "DHCP".

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the
    # resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as
        # long as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }

        # To configure a second service resource block, add another Service
        # resource block and use a unique name.
        Service "DHCP:Running"
        {
            Name = "DHCP"
            State = "Running"
        }
    }
}
```

> [!NOTE]
> A partir do PowerShell 5.0, o IntelliSense foi adicionado para DSC. Esse novo recurso permite que você use <kbd>TAB</kbd> e <kbd>Ctrl</kbd>+<kbd>Espaço</kbd> para preenchimento automático de nomes de chaves.

![Recurso IntelliSense usando o preenchimento com Tab](media/resources/resource-tabcompletion.png)

## <a name="types-of-resources"></a>Tipos de recursos

O Windows vem com recursos internos, e o Linux tem recursos específicos do sistema operacional. Existem recursos de [dependências entre nós](../configurations/crossNodeDependencies.md), recursos de gerenciamento de pacotes e [recursos de propriedade e manutenção da comunidade](https://github.com/dsccommunity). Você pode usar as etapas acima para determinar as sintaxes desses recursos e como usá-las. As páginas que atendem a esses recursos foram arquivadas em **Referência**.

### <a name="windows-built-in-resources"></a>Windows built-in resources (Recursos internos do Windows)

- [Recurso Archive](../reference/resources/windows/archiveResource.md)
- [Recurso Environment](../reference/resources/windows/environmentResource.md)
- [Recurso File](../reference/resources/windows/fileResource.md)
- [Recurso Group](../reference/resources/windows/groupResource.md)
- [Recurso GroupSet](../reference/resources/windows/groupSetResource.md)
- [Recurso Log](../reference/resources/windows/logResource.md)
- [Recurso Package](../reference/resources/windows/packageResource.md)
- [Recurso ProcessSet](../reference/resources/windows/ProcessSetResource.md)
- [Recurso Registry](../reference/resources/windows/registryResource.md)
- [Recurso Script](../reference/resources/windows/scriptResource.md)
- [Recurso Service](../reference/resources/windows/serviceResource.md)
- [Recurso ServiceSet](../reference/resources/windows/serviceSetResource.md)
- [Recurso User](../reference/resources/windows/userResource.md)
- [Recurso WindowsFeature](../reference/resources/windows/windowsFeatureResource.md)
- [Recurso WindowsFeatureSet](../reference/resources/windows/windowsFeatureSetResource.md)
- [Recurso WindowsOptionalFeature](../reference/resources/windows/windowsOptionalFeatureResource.md)
- [Recurso WindowsOptionalFeatureSet](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
- [Recurso WindowsPackageCabResource](../reference/resources/windows/windowsPackageCabResource.md)
- [Recurso WindowsProcess](../reference/resources/windows/windowsProcessResource.md)

### <a name="cross-node-dependency-resources"></a>Recursos de dependência entre nós

- [Recurso WaitForAll](../reference/resources/windows/waitForAllResource.md)
- [Recurso WaitForSome](../reference/resources/windows/waitForSomeResource.md)
- [Recurso WaitForAny](../reference/resources/windows/waitForAnyResource.md)

### <a name="package-management-resources"></a>Recursos de Gerenciamento de Pacotes

- [Recurso PackageManagement](../reference/resources/packagemanagement/PackageManagementDscResource.md)
- [Recurso PackageManagementSource](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

#### <a name="linux-resources"></a>Recursos Linux

- [Recurso Archive do Linux](../reference/resources/linux/lnxArchiveResource.md)
- [Recurso Environment do Linux](../reference/resources/linux/lnxEnvironmentResource.md)
- [Recurso FileLine do Linux](../reference/resources/linux/lnxFileLineResource.md)
- [Recurso File do Linux](../reference/resources/linux/lnxFileResource.md)
- [Recurso Group do Linux](../reference/resources/linux/lnxGroupResource.md)
- [Recurso Package do Linux](../reference/resources/linux/lnxPackageResource.md)
- [Recurso Script do Linux](../reference/resources/linux/lnxScriptResource.md)
- [Recurso Service do Linux](../reference/resources/linux/lnxServiceResource.md)
- [Recurso SshAuthorizedKeys do Linux](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
- [Recurso User do Linux](../reference/resources/linux/lnxUserResource.md)
