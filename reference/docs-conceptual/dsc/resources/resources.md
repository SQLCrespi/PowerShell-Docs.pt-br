---
ms.date: 02/28/2020
keywords: DSC,powershell,configuração,instalação
title: Recursos de DSC
ms.openlocfilehash: 863898d910cc3c75c3e5977a5b6b0657ba7ed512
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "78278232"
---
# <a name="dsc-resources"></a><span data-ttu-id="9ee6e-103">Recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="9ee6e-103">DSC Resources</span></span>

> <span data-ttu-id="9ee6e-104">Aplica-se ao Windows PowerShell 4.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-104">Applies to Windows PowerShell 4.0 and up.</span></span>

## <a name="overview"></a><span data-ttu-id="9ee6e-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="9ee6e-105">Overview</span></span>

<span data-ttu-id="9ee6e-106">Os Recursos de Configuração de Estado Desejado (DSC) fornecem os blocos de construção para uma configuração DSC.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-106">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="9ee6e-107">Um recurso expõe propriedades que podem ser configuradas (esquema) e contém as funções de script do PowerShell que o Gerenciador de Configurações Local (LCM) chama de "realizar".</span><span class="sxs-lookup"><span data-stu-id="9ee6e-107">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="9ee6e-108">Um recurso pode modelar algo tão genérico quanto um arquivo ou tão específico quanto uma configuração de servidor do IIS.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-108">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span> <span data-ttu-id="9ee6e-109">Grupos de recursos semelhantes são combinados em um Módulo de DSC, que organiza todos os arquivos necessários em uma estrutura que é portátil e inclui metadados para identificar como os recursos devem ser usados.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-109">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>

<span data-ttu-id="9ee6e-110">Cada recurso tem um \*esquema que determina a sintaxe necessária para usar o recurso em uma [Configuração](../configurations/configurations.md).</span><span class="sxs-lookup"><span data-stu-id="9ee6e-110">Each resource has a \*schema that determines the syntax needed to use the resource in a [Configuration](../configurations/configurations.md).</span></span>
<span data-ttu-id="9ee6e-111">Um esquema de recurso pode ser definido das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="9ee6e-111">A resource's schema can be defined in the following ways:</span></span>

- <span data-ttu-id="9ee6e-112">Arquivo **'Schema.Mof'** : A maioria dos recursos define seus _esquemas_ em um arquivo 'schema.mof' usando o [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span><span class="sxs-lookup"><span data-stu-id="9ee6e-112">**'Schema.Mof'** file: Most resources define their _schema_ in a 'schema.mof' file, using [Managed Object Format](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>
- <span data-ttu-id="9ee6e-113">Arquivo **'\<Resource Name\>.schema.psm1'** : [Recursos de Composição](../configurations/compositeConfigs.md) definem seus *esquemas* em um arquivo '<ResourceName>.schema.psm1' usando um [Bloco de Parâmetro](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span><span class="sxs-lookup"><span data-stu-id="9ee6e-113">**'\<Resource Name\>.schema.psm1'** file: [Composite Resources](../configurations/compositeConfigs.md) define their *schema* in a '<ResourceName>.schema.psm1' file using a [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters).</span></span>
- <span data-ttu-id="9ee6e-114">Arquivo **'\<Resource Name\>.psm1'** : Recursos DSC baseado em classe definem seus _esquemas_ na definição da classe.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-114">**'\<Resource Name\>.psm1'** file: Class based DSC resources define their _schema_ in the class definition.</span></span> <span data-ttu-id="9ee6e-115">Os itens de sintaxe são indicados como propriedades de Classe.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-115">Syntax items are denoted as Class properties.</span></span> <span data-ttu-id="9ee6e-116">Para saber mais, confira [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span><span class="sxs-lookup"><span data-stu-id="9ee6e-116">For more information, see [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc).</span></span>

<span data-ttu-id="9ee6e-117">Para recuperar a sintaxe para um recurso DSC, use o cmdlet [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) com o parâmetro `-Syntax`.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-117">To retrieve the syntax for a DSC resource, use the [Get-DSCResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet with the `-Syntax` parameter.</span></span> <span data-ttu-id="9ee6e-118">Esse uso é semelhante ao uso de [Get-Command](/powershell/module/microsoft.powershell.core/get-command) com o parâmetro `-Syntax` para obter a sintaxe do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-118">This usage is similar to using [Get-Command](/powershell/module/microsoft.powershell.core/get-command) with the `-Syntax` parameter to get cmdlet syntax.</span></span> <span data-ttu-id="9ee6e-119">A saída que você vê mostrará o modelo usado para um bloco de recursos do recurso que você especificar.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-119">The output you see will show the template used for a resource block for the resource you specify.</span></span>

```powershell
Get-DscResource -Syntax Service
```

<span data-ttu-id="9ee6e-120">A saída que você vê deve ser semelhante à saída abaixo, embora a sintaxe deste recurso possa ser alterada no futuro.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-120">The output you see should be similar to the output below, though this resource's syntax could change in the future.</span></span> <span data-ttu-id="9ee6e-121">Como a sintaxe do cmdlet, as _chaves_ vistas entre colchetes são opcionais.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-121">Like cmdlet syntax, the _keys_ seen in square brackets, are optional.</span></span> <span data-ttu-id="9ee6e-122">Os tipos especificam o tipo de dados esperado de cada chave.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-122">The types specify the type of data each key expects.</span></span>

> [!NOTE]
> <span data-ttu-id="9ee6e-123">A chave **Garantir** é opcional porque o padrão é "Presente".</span><span class="sxs-lookup"><span data-stu-id="9ee6e-123">The **Ensure** key is optional because it defaults to "Present".</span></span>

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

<span data-ttu-id="9ee6e-124">Dentro de uma Configuração, um bloco de recursos de **Serviço** poderia se parecer com isso para **Garantir** que o serviço de Spooler está em execução.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-124">Inside a Configuration, a **Service** resource block might look like this to **Ensure** that the Spooler service is running.</span></span>

> [!NOTE]
> <span data-ttu-id="9ee6e-125">Antes de usar um recurso em uma configuração, você deve importá-lo usando [Import-DSCResource](../configurations/import-dscresource.md).</span><span class="sxs-lookup"><span data-stu-id="9ee6e-125">Before using a resource in a Configuration, you must import it using [Import-DSCResource](../configurations/import-dscresource.md).</span></span>

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

<span data-ttu-id="9ee6e-126">Configurações podem conter várias instâncias do mesmo tipo de recurso.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-126">Configurations can contain multiple instances of the same resource type.</span></span> <span data-ttu-id="9ee6e-127">Cada instância deve ter um nome exclusivo.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-127">Each instance must be uniquely named.</span></span> <span data-ttu-id="9ee6e-128">No exemplo a seguir, um segundo bloco de recurso de **Serviço** é adicionado ao configurar o serviço "DHCP".</span><span class="sxs-lookup"><span data-stu-id="9ee6e-128">In the following example, a second **Service** resource block is added to configure the "DHCP" service.</span></span>

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
> <span data-ttu-id="9ee6e-129">A partir do PowerShell 5.0, o IntelliSense foi adicionado para DSC.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-129">Beginning in PowerShell 5.0, intellisense was added for DSC.</span></span> <span data-ttu-id="9ee6e-130">Esse novo recurso permite que você use <kbd>TAB</kbd> e <kbd>Ctrl</kbd>+<kbd>Espaço</kbd> para preenchimento automático de nomes de chaves.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-130">This new feature allows you to use <kbd>TAB</kbd> and <kbd>Ctr</kbd>+<kbd>Space</kbd> to auto-complete key names.</span></span>

![Preenchimento de Recursos com Tab](media/resources/resource-tabcompletion.png)

## <a name="types-of-resources"></a><span data-ttu-id="9ee6e-132">Tipos de recursos</span><span class="sxs-lookup"><span data-stu-id="9ee6e-132">Types of resources</span></span>

<span data-ttu-id="9ee6e-133">O Windows vem com recursos internos, e o Linux tem recursos específicos do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-133">Windows comes with built in resources and Linux has OS specific resources.</span></span> <span data-ttu-id="9ee6e-134">Existem recursos de [dependências entre nós](../configurations/crossNodeDependencies.md), recursos de gerenciamento de pacotes e [recursos de propriedade e manutenção da comunidade](https://github.com/dsccommunity).</span><span class="sxs-lookup"><span data-stu-id="9ee6e-134">There are resources for [cross-node dependencies](../configurations/crossNodeDependencies.md), package management resources, as well as[community owned and maintained resources](https://github.com/dsccommunity).</span></span> <span data-ttu-id="9ee6e-135">Você pode usar as etapas acima para determinar as sintaxes desses recursos e como usá-las.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-135">You can use the above steps to determine the syntax of these resources and how to use them.</span></span> <span data-ttu-id="9ee6e-136">As páginas que atendem a esses recursos foram arquivadas em **Referência**.</span><span class="sxs-lookup"><span data-stu-id="9ee6e-136">The pages that serve these resources have been archived under **Reference**.</span></span>

### <a name="windows-built-in-resources"></a><span data-ttu-id="9ee6e-137">Windows built-in resources (Recursos internos do Windows)</span><span class="sxs-lookup"><span data-stu-id="9ee6e-137">Windows built-in resources</span></span>

- [<span data-ttu-id="9ee6e-138">Recurso Archive</span><span class="sxs-lookup"><span data-stu-id="9ee6e-138">Archive Resource</span></span>](../reference/resources/windows/archiveResource.md)
- [<span data-ttu-id="9ee6e-139">Recurso Environment</span><span class="sxs-lookup"><span data-stu-id="9ee6e-139">Environment Resource</span></span>](../reference/resources/windows/environmentResource.md)
- [<span data-ttu-id="9ee6e-140">Recurso File</span><span class="sxs-lookup"><span data-stu-id="9ee6e-140">File Resource</span></span>](../reference/resources/windows/fileResource.md)
- [<span data-ttu-id="9ee6e-141">Recurso Group</span><span class="sxs-lookup"><span data-stu-id="9ee6e-141">Group Resource</span></span>](../reference/resources/windows/groupResource.md)
- [<span data-ttu-id="9ee6e-142">Recurso GroupSet</span><span class="sxs-lookup"><span data-stu-id="9ee6e-142">GroupSet Resource</span></span>](../reference/resources/windows/groupSetResource.md)
- [<span data-ttu-id="9ee6e-143">Recurso Log</span><span class="sxs-lookup"><span data-stu-id="9ee6e-143">Log Resource</span></span>](../reference/resources/windows/logResource.md)
- [<span data-ttu-id="9ee6e-144">Recurso Package</span><span class="sxs-lookup"><span data-stu-id="9ee6e-144">Package Resource</span></span>](../reference/resources/windows/packageResource.md)
- [<span data-ttu-id="9ee6e-145">Recurso ProcessSet</span><span class="sxs-lookup"><span data-stu-id="9ee6e-145">ProcessSet Resource</span></span>](../reference/resources/windows/ProcessSetResource.md)
- [<span data-ttu-id="9ee6e-146">Recurso Registry</span><span class="sxs-lookup"><span data-stu-id="9ee6e-146">Registry Resource</span></span>](../reference/resources/windows/registryResource.md)
- [<span data-ttu-id="9ee6e-147">Recurso Script</span><span class="sxs-lookup"><span data-stu-id="9ee6e-147">Script Resource</span></span>](../reference/resources/windows/scriptResource.md)
- [<span data-ttu-id="9ee6e-148">Recurso Service</span><span class="sxs-lookup"><span data-stu-id="9ee6e-148">Service Resource</span></span>](../reference/resources/windows/serviceResource.md)
- [<span data-ttu-id="9ee6e-149">Recurso ServiceSet</span><span class="sxs-lookup"><span data-stu-id="9ee6e-149">ServiceSet Resource</span></span>](../reference/resources/windows/serviceSetResource.md)
- [<span data-ttu-id="9ee6e-150">Recurso User</span><span class="sxs-lookup"><span data-stu-id="9ee6e-150">User Resource</span></span>](../reference/resources/windows/userResource.md)
- [<span data-ttu-id="9ee6e-151">Recurso WindowsFeature</span><span class="sxs-lookup"><span data-stu-id="9ee6e-151">WindowsFeature Resource</span></span>](../reference/resources/windows/windowsFeatureResource.md)
- [<span data-ttu-id="9ee6e-152">Recurso WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="9ee6e-152">WindowsFeatureSet Resource</span></span>](../reference/resources/windows/windowsFeatureSetResource.md)
- [<span data-ttu-id="9ee6e-153">Recurso WindowsOptionalFeature</span><span class="sxs-lookup"><span data-stu-id="9ee6e-153">WindowsOptionalFeature Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureResource.md)
- [<span data-ttu-id="9ee6e-154">Recurso WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="9ee6e-154">WindowsOptionalFeatureSet Resource</span></span>](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
- [<span data-ttu-id="9ee6e-155">Recurso WindowsPackageCabResource</span><span class="sxs-lookup"><span data-stu-id="9ee6e-155">WindowsPackageCabResource Resource</span></span>](../reference/resources/windows/windowsPackageCabResource.md)
- [<span data-ttu-id="9ee6e-156">Recurso WindowsProcess</span><span class="sxs-lookup"><span data-stu-id="9ee6e-156">WindowsProcess Resource</span></span>](../reference/resources/windows/windowsProcessResource.md)

### <a name="cross-node-dependency-resources"></a><span data-ttu-id="9ee6e-157">Recursos de dependência entre nós</span><span class="sxs-lookup"><span data-stu-id="9ee6e-157">Cross-Node dependency resources</span></span>

- [<span data-ttu-id="9ee6e-158">Recurso WaitForAll</span><span class="sxs-lookup"><span data-stu-id="9ee6e-158">WaitForAll Resource</span></span>](../reference/resources/windows/waitForAllResource.md)
- [<span data-ttu-id="9ee6e-159">Recurso WaitForSome</span><span class="sxs-lookup"><span data-stu-id="9ee6e-159">WaitForSome Resource</span></span>](../reference/resources/windows/waitForSomeResource.md)
- [<span data-ttu-id="9ee6e-160">Recurso WaitForAny</span><span class="sxs-lookup"><span data-stu-id="9ee6e-160">WaitForAny Resource</span></span>](../reference/resources/windows/waitForAnyResource.md)

### <a name="package-management-resources"></a><span data-ttu-id="9ee6e-161">Recursos de Gerenciamento de Pacotes</span><span class="sxs-lookup"><span data-stu-id="9ee6e-161">Package Management resources</span></span>

- [<span data-ttu-id="9ee6e-162">Recurso PackageManagement</span><span class="sxs-lookup"><span data-stu-id="9ee6e-162">PackageManagement Resource</span></span>](../reference/resources/packagemanagement/PackageManagementDscResource.md)
- [<span data-ttu-id="9ee6e-163">Recurso PackageManagementSource</span><span class="sxs-lookup"><span data-stu-id="9ee6e-163">PackageManagementSource Resource</span></span>](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

#### <a name="linux-resources"></a><span data-ttu-id="9ee6e-164">Recursos Linux</span><span class="sxs-lookup"><span data-stu-id="9ee6e-164">Linux resources</span></span>

- [<span data-ttu-id="9ee6e-165">Recurso Archive do Linux</span><span class="sxs-lookup"><span data-stu-id="9ee6e-165">Linux Archive Resource</span></span>](../reference/resources/linux/lnxArchiveResource.md)
- [<span data-ttu-id="9ee6e-166">Recurso Environment do Linux</span><span class="sxs-lookup"><span data-stu-id="9ee6e-166">Linux Environment Resource</span></span>](../reference/resources/linux/lnxEnvironmentResource.md)
- [<span data-ttu-id="9ee6e-167">Recurso FileLine do Linux</span><span class="sxs-lookup"><span data-stu-id="9ee6e-167">Linux FileLine Resource</span></span>](../reference/resources/linux/lnxFileLineResource.md)
- [<span data-ttu-id="9ee6e-168">Recurso File do Linux</span><span class="sxs-lookup"><span data-stu-id="9ee6e-168">Linux File Resource</span></span>](../reference/resources/linux/lnxFileResource.md)
- [<span data-ttu-id="9ee6e-169">Recurso Group do Linux</span><span class="sxs-lookup"><span data-stu-id="9ee6e-169">Linux Group Resource</span></span>](../reference/resources/linux/lnxGroupResource.md)
- [<span data-ttu-id="9ee6e-170">Recurso Package do Linux</span><span class="sxs-lookup"><span data-stu-id="9ee6e-170">Linux Package Resource</span></span>](../reference/resources/linux/lnxPackageResource.md)
- [<span data-ttu-id="9ee6e-171">Recurso Script do Linux</span><span class="sxs-lookup"><span data-stu-id="9ee6e-171">Linux Script Resource</span></span>](../reference/resources/linux/lnxScriptResource.md)
- [<span data-ttu-id="9ee6e-172">Recurso Service do Linux</span><span class="sxs-lookup"><span data-stu-id="9ee6e-172">Linux Service Resource</span></span>](../reference/resources/linux/lnxServiceResource.md)
- [<span data-ttu-id="9ee6e-173">Recurso SshAuthorizedKeys do Linux</span><span class="sxs-lookup"><span data-stu-id="9ee6e-173">Linux SshAuthorizedKeys Resource</span></span>](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
- [<span data-ttu-id="9ee6e-174">Recurso User do Linux</span><span class="sxs-lookup"><span data-stu-id="9ee6e-174">Linux User Resource</span></span>](../reference/resources/linux/lnxUserResource.md)
