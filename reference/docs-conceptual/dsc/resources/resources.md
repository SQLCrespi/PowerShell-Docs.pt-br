---
ms.date: 07/23/2020
keywords: DSC,powershell,configuração,instalação
title: Recursos de DSC
ms.openlocfilehash: 6ab831c9d423c6189951b43bfab92f800366ceca
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87777932"
---
# <a name="dsc-resources"></a><span data-ttu-id="4d8d0-103">Recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="4d8d0-103">DSC Resources</span></span>

> <span data-ttu-id="4d8d0-104">Aplica-se ao Windows PowerShell 4.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-104">Applies to Windows PowerShell 4.0 and up.</span></span>

## <a name="overview"></a><span data-ttu-id="4d8d0-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="4d8d0-105">Overview</span></span>

<span data-ttu-id="4d8d0-106">Os Recursos de Configuração de Estado Desejado (DSC) fornecem os blocos de construção para uma configuração DSC.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-106">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="4d8d0-107">Um recurso expõe propriedades que podem ser configuradas (esquema) e contém as funções de script do PowerShell que o Gerenciador de Configurações Local (LCM) chama de "realizar".</span><span class="sxs-lookup"><span data-stu-id="4d8d0-107">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="4d8d0-108">Um recurso pode modelar algo tão genérico quanto um arquivo ou tão específico quanto uma configuração de servidor do IIS.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-108">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span> <span data-ttu-id="4d8d0-109">Grupos de recursos semelhantes são combinados em um Módulo de DSC, que organiza todos os arquivos necessários em uma estrutura que é portátil e inclui metadados para identificar como os recursos devem ser usados.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-109">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>

<span data-ttu-id="4d8d0-110">Cada recurso tem um \*esquema que determina a sintaxe necessária para usar o recurso em uma [Configuração](../configurations/configurations.md).</span><span class="sxs-lookup"><span data-stu-id="4d8d0-110">Each resource has a \*schema that determines the syntax needed to use the resource in a [Configuration](../configurations/configurations.md).</span></span>
<span data-ttu-id="4d8d0-111">Um esquema de recurso pode ser definido das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="4d8d0-111">A resource's schema can be defined in the following ways:</span></span>

- <span data-ttu-id="4d8d0-112">Arquivo `Schema.Mof`: A maioria dos recursos define seus _esquemas_ em um arquivo `schema.mof` usando um [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span><span class="sxs-lookup"><span data-stu-id="4d8d0-112">`Schema.Mof` file: Most resources define their _schema_ in a `schema.mof` file, using [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>
- <span data-ttu-id="4d8d0-113">Arquivo `<Resource Name>.schema.psm1`: [Recursos de composição](../configurations/compositeConfigs.md) definem o _esquema_ em um arquivo `<ResourceName>.schema.psm1` usando um [bloco de parâmetro](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span><span class="sxs-lookup"><span data-stu-id="4d8d0-113">`<Resource Name>.schema.psm1` file: [Composite Resources](../configurations/compositeConfigs.md) define their _schema_ in a `<ResourceName>.schema.psm1` file using a [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span></span>
- <span data-ttu-id="4d8d0-114">Arquivo `<Resource Name>.psm1`: Recursos DSC baseado em classe definem seus _esquemas_ na definição da classe.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-114">`<Resource Name>.psm1` file: Class based DSC resources define their _schema_ in the class definition.</span></span> <span data-ttu-id="4d8d0-115">Os itens de sintaxe são indicados como propriedades de Classe.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-115">Syntax items are denoted as Class properties.</span></span> <span data-ttu-id="4d8d0-116">Para saber mais, confira [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span><span class="sxs-lookup"><span data-stu-id="4d8d0-116">For more information, see [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span></span>

<span data-ttu-id="4d8d0-117">Para recuperar a sintaxe para um recurso DSC, use o cmdlet [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) com o parâmetro **Syntax**.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-117">To retrieve the syntax for a DSC resource, use the [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet with the **Syntax** parameter.</span></span> <span data-ttu-id="4d8d0-118">Esse uso é semelhante ao uso de [Get-Command](/powershell/module/microsoft.powershell.core/get-command) com o parâmetro **Syntax** para obter a sintaxe do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-118">This usage is similar to using [Get-Command](/powershell/module/microsoft.powershell.core/get-command) with the **Syntax** parameter to get cmdlet syntax.</span></span> <span data-ttu-id="4d8d0-119">A saída que você vê mostrará o modelo usado para um bloco de recursos do recurso que você especificar.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-119">The output you see will show the template used for a resource block for the resource you specify.</span></span>

```powershell
Get-DscResource -Syntax Service
```

<span data-ttu-id="4d8d0-120">A saída que você vê deve ser semelhante à saída abaixo, embora a sintaxe deste recurso possa ser alterada no futuro.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-120">The output you see should be similar to the output below, though this resource's syntax could change in the future.</span></span> <span data-ttu-id="4d8d0-121">Como a sintaxe do cmdlet, as _chaves_ vistas entre colchetes são opcionais.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-121">Like cmdlet syntax, the _keys_ seen in square brackets, are optional.</span></span> <span data-ttu-id="4d8d0-122">Os tipos especificam o tipo de dados esperado de cada chave.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-122">The types specify the type of data each key expects.</span></span>

> [!NOTE]
> <span data-ttu-id="4d8d0-123">A chave **Garantir** é opcional porque o padrão é "Presente".</span><span class="sxs-lookup"><span data-stu-id="4d8d0-123">The **Ensure** key is optional because it defaults to "Present".</span></span>

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
> <span data-ttu-id="4d8d0-124">Nas versões do PowerShell antes de 7.0, `Get-DscResource` não encontra recursos de DSC baseados em classe.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-124">In PowerShell versions below 7.0, `Get-DscResource` does not find Class based DSC resources.</span></span>

<span data-ttu-id="4d8d0-125">Dentro de uma Configuração, um bloco de recursos de **Serviço** poderia se parecer com isso para **Garantir** que o serviço de Spooler está em execução.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-125">Inside a Configuration, a **Service** resource block might look like this to **Ensure** that the Spooler service is running.</span></span>

> [!NOTE]
> <span data-ttu-id="4d8d0-126">Antes de usar um recurso em uma configuração, você deve importá-lo usando [Import-DSCResource](../configurations/import-dscresource.md).</span><span class="sxs-lookup"><span data-stu-id="4d8d0-126">Before using a resource in a Configuration, you must import it using [Import-DSCResource](../configurations/import-dscresource.md).</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as long as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }
    }
}
```

<span data-ttu-id="4d8d0-127">Configurações podem conter várias instâncias do mesmo tipo de recurso.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-127">Configurations can contain multiple instances of the same resource type.</span></span> <span data-ttu-id="4d8d0-128">Cada instância deve ter um nome exclusivo.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-128">Each instance must be uniquely named.</span></span> <span data-ttu-id="4d8d0-129">No exemplo a seguir, um segundo bloco de recurso de **Serviço** é adicionado ao configurar o serviço "DHCP".</span><span class="sxs-lookup"><span data-stu-id="4d8d0-129">In the following example, a second **Service** resource block is added to configure the "DHCP" service.</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as long as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }

        # To configure a second service resource block, add another Service resource block and use a unique name.
        Service "DHCP:Running"
        {
            Name = "DHCP"
            State = "Running"
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="4d8d0-130">A partir do PowerShell 5.0, o IntelliSense foi adicionado para DSC.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-130">Beginning in PowerShell 5.0, IntelliSense was added for DSC.</span></span> <span data-ttu-id="4d8d0-131">Esse novo recurso permite que você use <kbd>TAB</kbd> e <kbd>Ctrl</kbd>+<kbd>Espaço</kbd> para preenchimento automático de nomes de chaves.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-131">This new feature allows you to use <kbd>TAB</kbd> and <kbd>Ctr</kbd>+<kbd>Space</kbd> to auto-complete key names.</span></span>

![Recurso IntelliSense usando o preenchimento com Tab](media/resources/resource-tabcompletion.png)

## <a name="types-of-resources"></a><span data-ttu-id="4d8d0-133">Tipos de recursos</span><span class="sxs-lookup"><span data-stu-id="4d8d0-133">Types of resources</span></span>

<span data-ttu-id="4d8d0-134">O Windows vem com recursos internos, e o Linux tem recursos específicos do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-134">Windows comes with built in resources and Linux has OS specific resources.</span></span> <span data-ttu-id="4d8d0-135">Existem recursos de [dependências entre nós](../configurations/crossNodeDependencies.md), recursos de gerenciamento de pacotes e [recursos de propriedade e manutenção da comunidade](https://github.com/dsccommunity).</span><span class="sxs-lookup"><span data-stu-id="4d8d0-135">There are resources for [cross-node dependencies](../configurations/crossNodeDependencies.md), package management resources, as well as[community owned and maintained resources](https://github.com/dsccommunity).</span></span> <span data-ttu-id="4d8d0-136">Você pode usar as etapas acima para determinar as sintaxes desses recursos e como usá-las.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-136">You can use the above steps to determine the syntax of these resources and how to use them.</span></span> <span data-ttu-id="4d8d0-137">As páginas que atendem a esses recursos foram arquivadas em **Referência**.</span><span class="sxs-lookup"><span data-stu-id="4d8d0-137">The pages that serve these resources have been archived under **Reference**.</span></span>

### <a name="windows-built-in-resources"></a><span data-ttu-id="4d8d0-138">Windows built-in resources (Recursos internos do Windows)</span><span class="sxs-lookup"><span data-stu-id="4d8d0-138">Windows built-in resources</span></span>

- [<span data-ttu-id="4d8d0-139">Recurso Archive</span><span class="sxs-lookup"><span data-stu-id="4d8d0-139">Archive Resource</span></span>](../reference/resources/windows/archiveResource.md)
- [<span data-ttu-id="4d8d0-140">Recurso Environment</span><span class="sxs-lookup"><span data-stu-id="4d8d0-140">Environment Resource</span></span>](../reference/resources/windows/environmentResource.md)
- [<span data-ttu-id="4d8d0-141">Recurso File</span><span class="sxs-lookup"><span data-stu-id="4d8d0-141">File Resource</span></span>](../reference/resources/windows/fileResource.md)
- [<span data-ttu-id="4d8d0-142">Recurso Group</span><span class="sxs-lookup"><span data-stu-id="4d8d0-142">Group Resource</span></span>](../reference/resources/windows/groupResource.md)
- [<span data-ttu-id="4d8d0-143">Recurso GroupSet</span><span class="sxs-lookup"><span data-stu-id="4d8d0-143">GroupSet Resource</span></span>](../reference/resources/windows/groupSetResource.md)
- [<span data-ttu-id="4d8d0-144">Recurso Log</span><span class="sxs-lookup"><span data-stu-id="4d8d0-144">Log Resource</span></span>](../reference/resources/windows/logResource.md)
- [<span data-ttu-id="4d8d0-145">Recurso Package</span><span class="sxs-lookup"><span data-stu-id="4d8d0-145">Package Resource</span></span>](../reference/resources/windows/packageResource.md)
- [<span data-ttu-id="4d8d0-146">Recurso ProcessSet</span><span class="sxs-lookup"><span data-stu-id="4d8d0-146">ProcessSet Resource</span></span>](../reference/resources/windows/ProcessSetResource.md)
- [<span data-ttu-id="4d8d0-147">Recurso Registry</span><span class="sxs-lookup"><span data-stu-id="4d8d0-147">Registry Resource</span></span>](../reference/resources/windows/registryResource.md)
- [<span data-ttu-id="4d8d0-148">Recurso Script</span><span class="sxs-lookup"><span data-stu-id="4d8d0-148">Script Resource</span></span>](../reference/resources/windows/scriptResource.md)
- [<span data-ttu-id="4d8d0-149">Recurso Service</span><span class="sxs-lookup"><span data-stu-id="4d8d0-149">Service Resource</span></span>](../reference/resources/windows/serviceResource.md)
- [<span data-ttu-id="4d8d0-150">Recurso ServiceSet</span><span class="sxs-lookup"><span data-stu-id="4d8d0-150">ServiceSet Resource</span></span>](../reference/resources/windows/serviceSetResource.md)
- [<span data-ttu-id="4d8d0-151">Recurso User</span><span class="sxs-lookup"><span data-stu-id="4d8d0-151">User Resource</span></span>](../reference/resources/windows/userResource.md)
- [<span data-ttu-id="4d8d0-152">Recurso WindowsFeature</span><span class="sxs-lookup"><span data-stu-id="4d8d0-152">WindowsFeature Resource</span></span>](../reference/resources/windows/windowsFeatureResource.md)
- [<span data-ttu-id="4d8d0-153">Recurso WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="4d8d0-153">WindowsFeatureSet Resource</span></span>](../reference/resources/windows/windowsFeatureSetResource.md)
- [<span data-ttu-id="4d8d0-154">Recurso WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="4d8d0-154">WindowsOptionalFeature Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureResource.md)
- [<span data-ttu-id="4d8d0-155">Recurso WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="4d8d0-155">WindowsOptionalFeatureSet Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
- [<span data-ttu-id="4d8d0-156">Recurso WindowsPackageCabResource</span><span class="sxs-lookup"><span data-stu-id="4d8d0-156">WindowsPackageCabResource Resource</span></span>](../reference/resources/windows/windowsPackageCabResource.md)
- [<span data-ttu-id="4d8d0-157">Recurso WindowsProcess</span><span class="sxs-lookup"><span data-stu-id="4d8d0-157">WindowsProcess Resource</span></span>](../reference/resources/windows/windowsProcessResource.md)

### <a name="cross-node-dependency-resources"></a><span data-ttu-id="4d8d0-158">Recursos de dependência entre nós</span><span class="sxs-lookup"><span data-stu-id="4d8d0-158">Cross-Node dependency resources</span></span>

- [<span data-ttu-id="4d8d0-159">Recurso WaitForAll</span><span class="sxs-lookup"><span data-stu-id="4d8d0-159">WaitForAll Resource</span></span>](../reference/resources/windows/waitForAllResource.md)
- [<span data-ttu-id="4d8d0-160">Recurso WaitForSome</span><span class="sxs-lookup"><span data-stu-id="4d8d0-160">WaitForSome Resource</span></span>](../reference/resources/windows/waitForSomeResource.md)
- [<span data-ttu-id="4d8d0-161">Recurso WaitForAny</span><span class="sxs-lookup"><span data-stu-id="4d8d0-161">WaitForAny Resource</span></span>](../reference/resources/windows/waitForAnyResource.md)

### <a name="package-management-resources"></a><span data-ttu-id="4d8d0-162">Recursos de Gerenciamento de Pacotes</span><span class="sxs-lookup"><span data-stu-id="4d8d0-162">Package Management resources</span></span>

- [<span data-ttu-id="4d8d0-163">Recurso PackageManagement</span><span class="sxs-lookup"><span data-stu-id="4d8d0-163">PackageManagement Resource</span></span>](../reference/resources/packagemanagement/PackageManagementDscResource.md)
- [<span data-ttu-id="4d8d0-164">Recurso PackageManagementSource</span><span class="sxs-lookup"><span data-stu-id="4d8d0-164">PackageManagementSource Resource</span></span>](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

#### <a name="linux-resources"></a><span data-ttu-id="4d8d0-165">Recursos Linux</span><span class="sxs-lookup"><span data-stu-id="4d8d0-165">Linux resources</span></span>

- [<span data-ttu-id="4d8d0-166">Recurso Archive do Linux</span><span class="sxs-lookup"><span data-stu-id="4d8d0-166">Linux Archive Resource</span></span>](../reference/resources/linux/lnxArchiveResource.md)
- [<span data-ttu-id="4d8d0-167">Recurso Environment do Linux</span><span class="sxs-lookup"><span data-stu-id="4d8d0-167">Linux Environment Resource</span></span>](../reference/resources/linux/lnxEnvironmentResource.md)
- [<span data-ttu-id="4d8d0-168">Recurso FileLine do Linux</span><span class="sxs-lookup"><span data-stu-id="4d8d0-168">Linux FileLine Resource</span></span>](../reference/resources/linux/lnxFileLineResource.md)
- [<span data-ttu-id="4d8d0-169">Recurso File do Linux</span><span class="sxs-lookup"><span data-stu-id="4d8d0-169">Linux File Resource</span></span>](../reference/resources/linux/lnxFileResource.md)
- [<span data-ttu-id="4d8d0-170">Recurso Group do Linux</span><span class="sxs-lookup"><span data-stu-id="4d8d0-170">Linux Group Resource</span></span>](../reference/resources/linux/lnxGroupResource.md)
- [<span data-ttu-id="4d8d0-171">Recurso Package do Linux</span><span class="sxs-lookup"><span data-stu-id="4d8d0-171">Linux Package Resource</span></span>](../reference/resources/linux/lnxPackageResource.md)
- [<span data-ttu-id="4d8d0-172">Recurso Script do Linux</span><span class="sxs-lookup"><span data-stu-id="4d8d0-172">Linux Script Resource</span></span>](../reference/resources/linux/lnxScriptResource.md)
- [<span data-ttu-id="4d8d0-173">Recurso Service do Linux</span><span class="sxs-lookup"><span data-stu-id="4d8d0-173">Linux Service Resource</span></span>](../reference/resources/linux/lnxServiceResource.md)
- [<span data-ttu-id="4d8d0-174">Recurso SshAuthorizedKeys do Linux</span><span class="sxs-lookup"><span data-stu-id="4d8d0-174">Linux SshAuthorizedKeys Resource</span></span>](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
- [<span data-ttu-id="4d8d0-175">Recurso User do Linux</span><span class="sxs-lookup"><span data-stu-id="4d8d0-175">Linux User Resource</span></span>](../reference/resources/linux/lnxUserResource.md)
