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
# <a name="dsc-resources"></a><span data-ttu-id="21238-105">Recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="21238-105">DSC Resources</span></span>

> <span data-ttu-id="21238-106">Aplica-se ao Windows PowerShell 4.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="21238-106">Applies to Windows PowerShell 4.0 and up.</span></span>

## <a name="overview"></a><span data-ttu-id="21238-107">Visão geral</span><span class="sxs-lookup"><span data-stu-id="21238-107">Overview</span></span>

<span data-ttu-id="21238-108">Os Recursos de Configuração de Estado Desejado (DSC) fornecem os blocos de construção para uma configuração DSC.</span><span class="sxs-lookup"><span data-stu-id="21238-108">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="21238-109">Um recurso expõe propriedades que podem ser configuradas (esquema) e contém as funções de script do PowerShell que o Gerenciador de Configurações Local (LCM) chama de "realizar".</span><span class="sxs-lookup"><span data-stu-id="21238-109">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="21238-110">Um recurso pode modelar algo tão genérico quanto um arquivo ou tão específico quanto uma configuração de servidor do IIS.</span><span class="sxs-lookup"><span data-stu-id="21238-110">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span> <span data-ttu-id="21238-111">Grupos de recursos semelhantes são combinados em um Módulo de DSC, que organiza todos os arquivos necessários em uma estrutura que é portátil e inclui metadados para identificar como os recursos devem ser usados.</span><span class="sxs-lookup"><span data-stu-id="21238-111">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>

<span data-ttu-id="21238-112">Cada recurso tem um \*esquema que determina a sintaxe necessária para usar o recurso em uma [Configuração](../configurations/configurations.md).</span><span class="sxs-lookup"><span data-stu-id="21238-112">Each resource has a \*schema that determines the syntax needed to use the resource in a [Configuration](../configurations/configurations.md).</span></span> <span data-ttu-id="21238-113">Um esquema de recurso pode ser definido das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="21238-113">A resource's schema can be defined in the following ways:</span></span>

- <span data-ttu-id="21238-114">Arquivo `Schema.Mof`: A maioria dos recursos define seus _esquemas_ em um arquivo `schema.mof` usando um [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span><span class="sxs-lookup"><span data-stu-id="21238-114">`Schema.Mof` file: Most resources define their _schema_ in a `schema.mof` file, using [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>
- <span data-ttu-id="21238-115">Arquivo `<Resource Name>.schema.psm1`: [Recursos de composição](../configurations/compositeConfigs.md) definem o _esquema_ em um arquivo `<ResourceName>.schema.psm1` usando um [bloco de parâmetro](/powershell/module/microsoft.powershell.core/about/about_functions#functions-with-parameters).</span><span class="sxs-lookup"><span data-stu-id="21238-115">`<Resource Name>.schema.psm1` file: [Composite Resources](../configurations/compositeConfigs.md) define their _schema_ in a `<ResourceName>.schema.psm1` file using a [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions#functions-with-parameters).</span></span>
- <span data-ttu-id="21238-116">Arquivo `<Resource Name>.psm1`: Recursos DSC baseado em classe definem seus _esquemas_ na definição da classe.</span><span class="sxs-lookup"><span data-stu-id="21238-116">`<Resource Name>.psm1` file: Class based DSC resources define their _schema_ in the class definition.</span></span> <span data-ttu-id="21238-117">Os itens de sintaxe são indicados como propriedades de Classe.</span><span class="sxs-lookup"><span data-stu-id="21238-117">Syntax items are denoted as Class properties.</span></span> <span data-ttu-id="21238-118">Para saber mais, confira [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span><span class="sxs-lookup"><span data-stu-id="21238-118">For more information, see [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span></span>

<span data-ttu-id="21238-119">Para recuperar a sintaxe para um recurso DSC, use o cmdlet [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) com o parâmetro **Syntax**.</span><span class="sxs-lookup"><span data-stu-id="21238-119">To retrieve the syntax for a DSC resource, use the [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet with the **Syntax** parameter.</span></span> <span data-ttu-id="21238-120">Esse uso é semelhante ao uso de [Get-Command](/powershell/module/microsoft.powershell.core/get-command) com o parâmetro **Syntax** para obter a sintaxe do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="21238-120">This usage is similar to using [Get-Command](/powershell/module/microsoft.powershell.core/get-command) with the **Syntax** parameter to get cmdlet syntax.</span></span> <span data-ttu-id="21238-121">A saída que você vê mostrará o modelo usado para um bloco de recursos do recurso que você especificar.</span><span class="sxs-lookup"><span data-stu-id="21238-121">The output you see will show the template used for a resource block for the resource you specify.</span></span>

```powershell
Get-DscResource -Syntax Service
```

<span data-ttu-id="21238-122">A saída que você vê deve ser semelhante à saída abaixo, embora a sintaxe deste recurso possa ser alterada no futuro.</span><span class="sxs-lookup"><span data-stu-id="21238-122">The output you see should be similar to the output below, though this resource's syntax could change in the future.</span></span> <span data-ttu-id="21238-123">Como a sintaxe do cmdlet, as _chaves_ vistas entre colchetes são opcionais.</span><span class="sxs-lookup"><span data-stu-id="21238-123">Like cmdlet syntax, the _keys_ seen in square brackets, are optional.</span></span> <span data-ttu-id="21238-124">Os tipos especificam o tipo de dados esperado de cada chave.</span><span class="sxs-lookup"><span data-stu-id="21238-124">The types specify the type of data each key expects.</span></span>

> [!NOTE]
> <span data-ttu-id="21238-125">A chave **Garantir** é opcional porque o padrão é "Presente".</span><span class="sxs-lookup"><span data-stu-id="21238-125">The **Ensure** key is optional because it defaults to "Present".</span></span>

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
> <span data-ttu-id="21238-126">Nas versões do PowerShell antes de 7.0, `Get-DscResource` não encontra recursos de DSC baseados em classe.</span><span class="sxs-lookup"><span data-stu-id="21238-126">In PowerShell versions below 7.0, `Get-DscResource` does not find Class based DSC resources.</span></span>

<span data-ttu-id="21238-127">Dentro de uma Configuração, um bloco de recursos de **Serviço** poderia se parecer com isso para **Garantir** que o serviço de Spooler está em execução.</span><span class="sxs-lookup"><span data-stu-id="21238-127">Inside a Configuration, a **Service** resource block might look like this to **Ensure** that the Spooler service is running.</span></span>

> [!NOTE]
> <span data-ttu-id="21238-128">Antes de usar um recurso em uma configuração, você deve importá-lo usando [Import-DSCResource](../configurations/import-dscresource.md).</span><span class="sxs-lookup"><span data-stu-id="21238-128">Before using a resource in a Configuration, you must import it using [Import-DSCResource](../configurations/import-dscresource.md).</span></span>

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

<span data-ttu-id="21238-129">Configurações podem conter várias instâncias do mesmo tipo de recurso.</span><span class="sxs-lookup"><span data-stu-id="21238-129">Configurations can contain multiple instances of the same resource type.</span></span> <span data-ttu-id="21238-130">Cada instância deve ter um nome exclusivo.</span><span class="sxs-lookup"><span data-stu-id="21238-130">Each instance must be uniquely named.</span></span> <span data-ttu-id="21238-131">No exemplo a seguir, um segundo bloco de recurso de **Serviço** é adicionado ao configurar o serviço "DHCP".</span><span class="sxs-lookup"><span data-stu-id="21238-131">In the following example, a second **Service** resource block is added to configure the "DHCP" service.</span></span>

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
> <span data-ttu-id="21238-132">A partir do PowerShell 5.0, o IntelliSense foi adicionado para DSC.</span><span class="sxs-lookup"><span data-stu-id="21238-132">Beginning in PowerShell 5.0, IntelliSense was added for DSC.</span></span> <span data-ttu-id="21238-133">Esse novo recurso permite que você use <kbd>TAB</kbd> e <kbd>Ctrl</kbd>+<kbd>Espaço</kbd> para preenchimento automático de nomes de chaves.</span><span class="sxs-lookup"><span data-stu-id="21238-133">This new feature allows you to use <kbd>TAB</kbd> and <kbd>Ctr</kbd>+<kbd>Space</kbd> to auto-complete key names.</span></span>

![Recurso IntelliSense usando o preenchimento com Tab](media/resources/resource-tabcompletion.png)

## <a name="types-of-resources"></a><span data-ttu-id="21238-135">Tipos de recursos</span><span class="sxs-lookup"><span data-stu-id="21238-135">Types of resources</span></span>

<span data-ttu-id="21238-136">O Windows vem com recursos internos, e o Linux tem recursos específicos do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="21238-136">Windows comes with built in resources and Linux has OS specific resources.</span></span> <span data-ttu-id="21238-137">Existem recursos de [dependências entre nós](../configurations/crossNodeDependencies.md), recursos de gerenciamento de pacotes e [recursos de propriedade e manutenção da comunidade](https://github.com/dsccommunity).</span><span class="sxs-lookup"><span data-stu-id="21238-137">There are resources for [cross-node dependencies](../configurations/crossNodeDependencies.md), package management resources, as well as [community owned and maintained resources](https://github.com/dsccommunity).</span></span> <span data-ttu-id="21238-138">Você pode usar as etapas acima para determinar as sintaxes desses recursos e como usá-las.</span><span class="sxs-lookup"><span data-stu-id="21238-138">You can use the above steps to determine the syntax of these resources and how to use them.</span></span> <span data-ttu-id="21238-139">As páginas que atendem a esses recursos foram arquivadas em **Referência**.</span><span class="sxs-lookup"><span data-stu-id="21238-139">The pages that serve these resources have been archived under **Reference**.</span></span>

### <a name="windows-built-in-resources"></a><span data-ttu-id="21238-140">Windows built-in resources (Recursos internos do Windows)</span><span class="sxs-lookup"><span data-stu-id="21238-140">Windows built-in resources</span></span>

- [<span data-ttu-id="21238-141">Recurso Archive</span><span class="sxs-lookup"><span data-stu-id="21238-141">Archive Resource</span></span>](../reference/resources/windows/archiveResource.md)
- [<span data-ttu-id="21238-142">Recurso Environment</span><span class="sxs-lookup"><span data-stu-id="21238-142">Environment Resource</span></span>](../reference/resources/windows/environmentResource.md)
- [<span data-ttu-id="21238-143">Recurso File</span><span class="sxs-lookup"><span data-stu-id="21238-143">File Resource</span></span>](../reference/resources/windows/fileResource.md)
- [<span data-ttu-id="21238-144">Recurso Group</span><span class="sxs-lookup"><span data-stu-id="21238-144">Group Resource</span></span>](../reference/resources/windows/groupResource.md)
- [<span data-ttu-id="21238-145">Recurso GroupSet</span><span class="sxs-lookup"><span data-stu-id="21238-145">GroupSet Resource</span></span>](../reference/resources/windows/groupSetResource.md)
- [<span data-ttu-id="21238-146">Recurso Log</span><span class="sxs-lookup"><span data-stu-id="21238-146">Log Resource</span></span>](../reference/resources/windows/logResource.md)
- [<span data-ttu-id="21238-147">Recurso Package</span><span class="sxs-lookup"><span data-stu-id="21238-147">Package Resource</span></span>](../reference/resources/windows/packageResource.md)
- [<span data-ttu-id="21238-148">Recurso ProcessSet</span><span class="sxs-lookup"><span data-stu-id="21238-148">ProcessSet Resource</span></span>](../reference/resources/windows/ProcessSetResource.md)
- [<span data-ttu-id="21238-149">Recurso Registry</span><span class="sxs-lookup"><span data-stu-id="21238-149">Registry Resource</span></span>](../reference/resources/windows/registryResource.md)
- [<span data-ttu-id="21238-150">Recurso Script</span><span class="sxs-lookup"><span data-stu-id="21238-150">Script Resource</span></span>](../reference/resources/windows/scriptResource.md)
- [<span data-ttu-id="21238-151">Recurso Service</span><span class="sxs-lookup"><span data-stu-id="21238-151">Service Resource</span></span>](../reference/resources/windows/serviceResource.md)
- [<span data-ttu-id="21238-152">Recurso ServiceSet</span><span class="sxs-lookup"><span data-stu-id="21238-152">ServiceSet Resource</span></span>](../reference/resources/windows/serviceSetResource.md)
- [<span data-ttu-id="21238-153">Recurso User</span><span class="sxs-lookup"><span data-stu-id="21238-153">User Resource</span></span>](../reference/resources/windows/userResource.md)
- [<span data-ttu-id="21238-154">Recurso WindowsFeature</span><span class="sxs-lookup"><span data-stu-id="21238-154">WindowsFeature Resource</span></span>](../reference/resources/windows/windowsFeatureResource.md)
- [<span data-ttu-id="21238-155">Recurso WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="21238-155">WindowsFeatureSet Resource</span></span>](../reference/resources/windows/windowsFeatureSetResource.md)
- [<span data-ttu-id="21238-156">Recurso WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="21238-156">WindowsOptionalFeature Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureResource.md)
- [<span data-ttu-id="21238-157">Recurso WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="21238-157">WindowsOptionalFeatureSet Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
- [<span data-ttu-id="21238-158">Recurso WindowsPackageCabResource</span><span class="sxs-lookup"><span data-stu-id="21238-158">WindowsPackageCabResource Resource</span></span>](../reference/resources/windows/windowsPackageCabResource.md)
- [<span data-ttu-id="21238-159">Recurso WindowsProcess</span><span class="sxs-lookup"><span data-stu-id="21238-159">WindowsProcess Resource</span></span>](../reference/resources/windows/windowsProcessResource.md)

### <a name="cross-node-dependency-resources"></a><span data-ttu-id="21238-160">Recursos de dependência entre nós</span><span class="sxs-lookup"><span data-stu-id="21238-160">Cross-Node dependency resources</span></span>

- [<span data-ttu-id="21238-161">Recurso WaitForAll</span><span class="sxs-lookup"><span data-stu-id="21238-161">WaitForAll Resource</span></span>](../reference/resources/windows/waitForAllResource.md)
- [<span data-ttu-id="21238-162">Recurso WaitForSome</span><span class="sxs-lookup"><span data-stu-id="21238-162">WaitForSome Resource</span></span>](../reference/resources/windows/waitForSomeResource.md)
- [<span data-ttu-id="21238-163">Recurso WaitForAny</span><span class="sxs-lookup"><span data-stu-id="21238-163">WaitForAny Resource</span></span>](../reference/resources/windows/waitForAnyResource.md)

### <a name="package-management-resources"></a><span data-ttu-id="21238-164">Recursos de Gerenciamento de Pacotes</span><span class="sxs-lookup"><span data-stu-id="21238-164">Package Management resources</span></span>

- [<span data-ttu-id="21238-165">Recurso PackageManagement</span><span class="sxs-lookup"><span data-stu-id="21238-165">PackageManagement Resource</span></span>](../reference/resources/packagemanagement/PackageManagementDscResource.md)
- [<span data-ttu-id="21238-166">Recurso PackageManagementSource</span><span class="sxs-lookup"><span data-stu-id="21238-166">PackageManagementSource Resource</span></span>](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

#### <a name="linux-resources"></a><span data-ttu-id="21238-167">Recursos Linux</span><span class="sxs-lookup"><span data-stu-id="21238-167">Linux resources</span></span>

- [<span data-ttu-id="21238-168">Recurso Archive do Linux</span><span class="sxs-lookup"><span data-stu-id="21238-168">Linux Archive Resource</span></span>](../reference/resources/linux/lnxArchiveResource.md)
- [<span data-ttu-id="21238-169">Recurso Environment do Linux</span><span class="sxs-lookup"><span data-stu-id="21238-169">Linux Environment Resource</span></span>](../reference/resources/linux/lnxEnvironmentResource.md)
- [<span data-ttu-id="21238-170">Recurso FileLine do Linux</span><span class="sxs-lookup"><span data-stu-id="21238-170">Linux FileLine Resource</span></span>](../reference/resources/linux/lnxFileLineResource.md)
- [<span data-ttu-id="21238-171">Recurso File do Linux</span><span class="sxs-lookup"><span data-stu-id="21238-171">Linux File Resource</span></span>](../reference/resources/linux/lnxFileResource.md)
- [<span data-ttu-id="21238-172">Recurso Group do Linux</span><span class="sxs-lookup"><span data-stu-id="21238-172">Linux Group Resource</span></span>](../reference/resources/linux/lnxGroupResource.md)
- [<span data-ttu-id="21238-173">Recurso Package do Linux</span><span class="sxs-lookup"><span data-stu-id="21238-173">Linux Package Resource</span></span>](../reference/resources/linux/lnxPackageResource.md)
- [<span data-ttu-id="21238-174">Recurso Script do Linux</span><span class="sxs-lookup"><span data-stu-id="21238-174">Linux Script Resource</span></span>](../reference/resources/linux/lnxScriptResource.md)
- [<span data-ttu-id="21238-175">Recurso Service do Linux</span><span class="sxs-lookup"><span data-stu-id="21238-175">Linux Service Resource</span></span>](../reference/resources/linux/lnxServiceResource.md)
- [<span data-ttu-id="21238-176">Recurso SshAuthorizedKeys do Linux</span><span class="sxs-lookup"><span data-stu-id="21238-176">Linux SshAuthorizedKeys Resource</span></span>](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
- [<span data-ttu-id="21238-177">Recurso User do Linux</span><span class="sxs-lookup"><span data-stu-id="21238-177">Linux User Resource</span></span>](../reference/resources/linux/lnxUserResource.md)
