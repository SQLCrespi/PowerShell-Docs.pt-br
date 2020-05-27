---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Usando o Import-DSCResource
ms.openlocfilehash: 1b066e231d158fb5b6333e42c91d24690e9b0223
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692466"
---
# <a name="using-import-dscresource"></a><span data-ttu-id="1aad5-103">Usando o Import-DSCResource</span><span class="sxs-lookup"><span data-stu-id="1aad5-103">Using Import-DSCResource</span></span>

<span data-ttu-id="1aad5-104">`Import-DScResource` é uma palavra-chave dinâmica, que só pode ser usada dentro do bloco de script de Configuração.</span><span class="sxs-lookup"><span data-stu-id="1aad5-104">`Import-DScResource` is a dynamic keyword, which can only be used inside a Configuration script block.</span></span> <span data-ttu-id="1aad5-105">A palavra-chave `Import-DSCResource` para importar todos os recursos necessários em sua Configuração.</span><span class="sxs-lookup"><span data-stu-id="1aad5-105">The `Import-DSCResource` keyword to import any resources needed in your Configuration.</span></span> <span data-ttu-id="1aad5-106">Os recursos em `$pshome` são importados automaticamente, mas ainda consideramos que a melhor prática é importar explicitamente todos os recursos usados na sua [Configuração](Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="1aad5-106">Resources under `$pshome` are imported automatically, but it is still considered best practice to explicitly import all resources used in your [Configuration](Configurations.md).</span></span>

<span data-ttu-id="1aad5-107">A sintaxe para `Import-DSCResource` é mostrada abaixo.</span><span class="sxs-lookup"><span data-stu-id="1aad5-107">The syntax for `Import-DSCResource` is shown below.</span></span>  <span data-ttu-id="1aad5-108">Ao especificar os módulos por nome, é necessário listar cada um deles em uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="1aad5-108">When specifying modules by name, it is a requirement to list each on a new line.</span></span>

```syntax
Import-DscResource [-Name <ResourceName(s)>] [-ModuleName <ModuleName>] [-ModuleVersion <ModuleVersion>]
```

|<span data-ttu-id="1aad5-109">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="1aad5-109">Parameter</span></span>  |<span data-ttu-id="1aad5-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="1aad5-110">Description</span></span>  |
|---------|---------|
|`-Name`|<span data-ttu-id="1aad5-111">Os nomes do recurso DSC que você deve importar.</span><span class="sxs-lookup"><span data-stu-id="1aad5-111">The DSC resource name(s) that you must import.</span></span> <span data-ttu-id="1aad5-112">Se o nome do módulo for especificado, o comando procurará pelos recursos DSC neste módulo; caso contrário, o comando procurará os recursos DSC em todos os caminhos de recursos DSC.</span><span class="sxs-lookup"><span data-stu-id="1aad5-112">If the module name is specified, the command searches for these DSC resources within this module; otherwise the command searches the DSC resources in all DSC resource paths.</span></span> <span data-ttu-id="1aad5-113">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="1aad5-113">Wildcards are supported.</span></span>|
|`-ModuleName`|<span data-ttu-id="1aad5-114">O nome ou a especificação do módulo.</span><span class="sxs-lookup"><span data-stu-id="1aad5-114">The module name, or module specification.</span></span>  <span data-ttu-id="1aad5-115">Se você especificar os recursos a importar de um módulo, o comando tentará importar apenas os recursos.</span><span class="sxs-lookup"><span data-stu-id="1aad5-115">If you specify resources to import from a module, the command will try to import only those resources.</span></span> <span data-ttu-id="1aad5-116">Se você especificar apenas o módulo, o comando importará todos os recursos DSC no módulo.</span><span class="sxs-lookup"><span data-stu-id="1aad5-116">If you specify the module only, the command imports all the DSC resources in the module.</span></span>|
|`-ModuleVersion`|<span data-ttu-id="1aad5-117">A partir do PowerShell 5.0, é possível especificar qual versão de um módulo a configuração deve usar.</span><span class="sxs-lookup"><span data-stu-id="1aad5-117">Beginning in PowerShell 5.0, you can specify which version of a module a configuration should use.</span></span> <span data-ttu-id="1aad5-118">Para saber mais, confira [Importar uma versão específica de um recurso instalado](sxsresource.md).</span><span class="sxs-lookup"><span data-stu-id="1aad5-118">For more information, see [Import a specific version of an installed resource](sxsresource.md).</span></span>|

```powershell
Import-DscResource -ModuleName xActiveDirectory
```

## <a name="example-use-import-dscresource-within-a-configuration"></a><span data-ttu-id="1aad5-119">Exemplo: Usar Import-DSCResource dentro de uma configuração</span><span class="sxs-lookup"><span data-stu-id="1aad5-119">Example: Use Import-DSCResource within a configuration</span></span>

```powershell
Configuration MSDSCConfiguration
{
    # Search for and imports Service, File, and Registry from the module PSDesiredStateConfiguration.
    Import-DSCResource -ModuleName PSDesiredStateConfiguration -Name Service, File, Registry

    # Search for and import Resource1 from the module that defines it.
    # If only –Name parameter is used then resources can belong to different PowerShell modules as well.
    # TimeZone resource is from the ComputerManagementDSC module which is not installed by default.
    # As a best practice, list each requirement on a different line if possible.  This makes reviewing
    # multiple changes in source control a bit easier.
    Import-DSCResource -Name File
    Import-DSCResource -Name TimeZone

    # Search for and import all DSC resources inside the module PSDesiredStateConfiguration.
    # When specifying the modulename parameter, it is a requirement to list each on a new line.
    Import-DSCResource -ModuleName PSDesiredStateConfiguration
    # In PowerShell 5.0 and later, you can specify a ModuleVersion parameter
    Import-DSCResource -ModuleName ComputerManagementDsc -ModuleVersion 6.0.0.0
...
```

> [!NOTE]
> <span data-ttu-id="1aad5-120">Não há suporte para especificar vários valores para os nomes de recursos e módulos no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="1aad5-120">Specifying multiple values for Resource names and modules names in same command are not supported.</span></span> <span data-ttu-id="1aad5-121">Pode haver um comportamento não determinístico sobre qual recurso deve ser carregado de qual módulo, caso o mesmo recurso exista em vários módulos.</span><span class="sxs-lookup"><span data-stu-id="1aad5-121">It can have non-deterministic behavior about which resource to load from which module in case same resource exists in multiple modules.</span></span> <span data-ttu-id="1aad5-122">O comando abaixo resultará em erro durante a compilação.</span><span class="sxs-lookup"><span data-stu-id="1aad5-122">Below command will result in error during compilation.</span></span>
>
> ```powershell
> Import-DscResource -Name UserConfigProvider*,TestLogger1 -ModuleName UserConfigProv,PsModuleForTestLogger
> ```

<span data-ttu-id="1aad5-123">Ao usar somente o parâmetro Nome, considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1aad5-123">Things to consider when using only the Name parameter:</span></span>

- <span data-ttu-id="1aad5-124">É uma operação de uso intensivo de recursos, dependendo do número de módulos instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="1aad5-124">It is a resource-intensive operation depending on the number of modules installed on machine.</span></span>
- <span data-ttu-id="1aad5-125">Ele carregará o primeiro recurso encontrado com o nome fornecido.</span><span class="sxs-lookup"><span data-stu-id="1aad5-125">It will load the first resource found with the given name.</span></span> <span data-ttu-id="1aad5-126">Caso haja mais de um recurso com o mesmo nome instalado, ele poderá carregar o recurso incorreto.</span><span class="sxs-lookup"><span data-stu-id="1aad5-126">In the case where there is more than one resource with same name installed, it could load the wrong resource.</span></span>

<span data-ttu-id="1aad5-127">O uso recomendado é especificar `–ModuleName` com o parâmetro `-Name`, como descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="1aad5-127">The recommended usage is to specify `–ModuleName` with the `-Name` parameter, as described below.</span></span>

<span data-ttu-id="1aad5-128">Esse uso oferece os seguintes benefícios:</span><span class="sxs-lookup"><span data-stu-id="1aad5-128">This usage has the following benefits:</span></span>

- <span data-ttu-id="1aad5-129">Reduz o impacto no desempenho ao limitar o escopo da pesquisa ao recurso especificado.</span><span class="sxs-lookup"><span data-stu-id="1aad5-129">It reduces the performance impact by limiting the search scope for the specified resource.</span></span>
- <span data-ttu-id="1aad5-130">Define explicitamente o módulo de definição do recurso, garantindo que o recurso correto seja carregado.</span><span class="sxs-lookup"><span data-stu-id="1aad5-130">It explicitly defines the module defining the resource, ensuring the correct resource is loaded.</span></span>

> [!NOTE]
> <span data-ttu-id="1aad5-131">No PowerShell 5.0, recursos de DSC podem ter várias versões e as versões podem ser instaladas em um computador lado a lado.</span><span class="sxs-lookup"><span data-stu-id="1aad5-131">In PowerShell 5.0, DSC resources can have multiple versions, and versions can be installed on a computer side-by-side.</span></span> <span data-ttu-id="1aad5-132">Isso é implementado por ter várias versões de um módulo de recursos que estão contidas na mesma pasta de módulo.</span><span class="sxs-lookup"><span data-stu-id="1aad5-132">This is implemented by having multiple versions of a resource module that are contained in the same module folder.</span></span>
> <span data-ttu-id="1aad5-133">Para obter mais informações, veja [Usando recursos com várias versões](sxsresource.md).</span><span class="sxs-lookup"><span data-stu-id="1aad5-133">For more information, see [Using resources with multiple versions](sxsresource.md).</span></span>

## <a name="intellisense-with-import-dscresource"></a><span data-ttu-id="1aad5-134">IntelliSense com Import-DSCResource</span><span class="sxs-lookup"><span data-stu-id="1aad5-134">Intellisense with Import-DSCResource</span></span>

<span data-ttu-id="1aad5-135">Ao criar a configuração DSC no ISE, o PowerShell fornece o IntelliSence para recursos e propriedades do recurso.</span><span class="sxs-lookup"><span data-stu-id="1aad5-135">When authoring the DSC configuration in ISE, PowerShell provides IntelliSence for resources and resource properties.</span></span> <span data-ttu-id="1aad5-136">Definições de recurso sob o caminho do módulo `$pshome` são carregados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1aad5-136">Resource definitions under the `$pshome` module path are loaded automatically.</span></span> <span data-ttu-id="1aad5-137">Quando você importa os recursos usando a palavra-chave `Import-DSCResource`, as definições de recursos especificadas são adicionadas e o Intellisense é expandido para incluir o esquema de recurso importado.</span><span class="sxs-lookup"><span data-stu-id="1aad5-137">When you import resources using the `Import-DSCResource` keyword, the specified resource definitions are added and Intellisense is expanded to include the imported resource's schema.</span></span>

![Recurso Intellisense](media/import-dscresource/resource-intellisense.png)

> [!NOTE]
> <span data-ttu-id="1aad5-139">A partir do PowerShell 5.0, o preenchimento com Tab foi adicionado ao ISE para recursos DSC e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="1aad5-139">Beginning in PowerShell 5.0, tab completion was added to the ISE for DSC resources and their properties.</span></span> <span data-ttu-id="1aad5-140">Para saber mais, confira [Recursos](../resources/resources.md).</span><span class="sxs-lookup"><span data-stu-id="1aad5-140">For more information, see [Resources](../resources/resources.md).</span></span>

<span data-ttu-id="1aad5-141">Ao compilar a configuração, o PowerShell usa as definições de recurso importadas para validar todos os blocos de recursos na configuração.</span><span class="sxs-lookup"><span data-stu-id="1aad5-141">When compiling the Configuration, PowerShell uses the imported resource definitions to validate all resource blocks in the configuration.</span></span>
<span data-ttu-id="1aad5-142">Cada bloco de recurso é validado, usando a definição de esquema do recurso, para as regras a seguir.</span><span class="sxs-lookup"><span data-stu-id="1aad5-142">Each resource block is validated, using the resource's schema definition, for the following rules.</span></span>

- <span data-ttu-id="1aad5-143">Apenas as propriedades definidas no esquema são usadas.</span><span class="sxs-lookup"><span data-stu-id="1aad5-143">Only properties defined in schema are used.</span></span>
- <span data-ttu-id="1aad5-144">Os tipos de dados de cada propriedade estão corretos.</span><span class="sxs-lookup"><span data-stu-id="1aad5-144">The data types for each property are correct.</span></span>
- <span data-ttu-id="1aad5-145">As propriedades-chave estão especificadas.</span><span class="sxs-lookup"><span data-stu-id="1aad5-145">Keys properties are specified.</span></span>
- <span data-ttu-id="1aad5-146">Nenhuma propriedade somente leitura é usada.</span><span class="sxs-lookup"><span data-stu-id="1aad5-146">No read-only property is used.</span></span>
- <span data-ttu-id="1aad5-147">Validação em tipos de mapas de valor.</span><span class="sxs-lookup"><span data-stu-id="1aad5-147">Validation on value maps types.</span></span>

<span data-ttu-id="1aad5-148">Considere a configuração a seguir:</span><span class="sxs-lookup"><span data-stu-id="1aad5-148">Consider the following configuration:</span></span>

```powershell
Configuration SchemaValidationInCorrectEnumValue
{
    # It is best practice to explicitly import all resources used in your Configuration.
    # This includes resources that are imported automatically, like WindowsFeature.
    Import-DSCResource -Name WindowsFeature
    Node localhost
    {
        WindowsFeature ROLE1
        {
            Name = "Telnet-Client"
            Ensure = "Invalid"
        }
    }
}
```

<span data-ttu-id="1aad5-149">Compilar essa configuração resulta em um erro.</span><span class="sxs-lookup"><span data-stu-id="1aad5-149">Compiling this Configuration results in an error.</span></span>

```output
PSDesiredStateConfiguration\WindowsFeature: At least one of the values 'Invalid' is not supported or valid for property 'Ensure' on class 'WindowsFeature'. Please specify only supported values: Present, Absent.
```

<span data-ttu-id="1aad5-150">O IntelliSense e a validação de esquema permitem capturar mais erros durante o tempo de análise e compilação, evitando complicações no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="1aad5-150">Intellisense and schema validation allow you to catch more errors during parse and compilation time, avoiding complications at run time.</span></span>

> [!NOTE]
> <span data-ttu-id="1aad5-151">Cada recurso DSC pode ter um nome e um **FriendlyName** definidos pelo esquema do recurso.</span><span class="sxs-lookup"><span data-stu-id="1aad5-151">Each DSC resource can have a name, and a **FriendlyName** defined by the resource's schema.</span></span> <span data-ttu-id="1aad5-152">Abaixo estão as duas primeiras linhas de "MSFT_ServiceResource.shema.mof".</span><span class="sxs-lookup"><span data-stu-id="1aad5-152">Below are the first two lines of "MSFT_ServiceResource.shema.mof".</span></span>
>
> ```syntax
> [ClassVersion("1.0.0"),FriendlyName("Service")]
> class MSFT_ServiceResource : OMI_BaseResource
> ```
>
> <span data-ttu-id="1aad5-153">Ao usar esse recurso em uma configuração, você pode especificar **MSFT_ServiceResource** ou **Serviço**.</span><span class="sxs-lookup"><span data-stu-id="1aad5-153">When using this resource in a Configuration, you can specify **MSFT_ServiceResource** or **Service**.</span></span>

## <a name="powershell-v4-and-v5-differences"></a><span data-ttu-id="1aad5-154">Diferenças entre o PowerShell v4 e v5</span><span class="sxs-lookup"><span data-stu-id="1aad5-154">PowerShell v4 and v5 differences</span></span>

<span data-ttu-id="1aad5-155">Há várias diferenças que você vê ao criar configurações no PowerShell v. 4.0. PowerShell 5.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="1aad5-155">There are multiple differences you see when authoring Configurations in PowerShell 4.0 vs. PowerShell 5.0 and later.</span></span> <span data-ttu-id="1aad5-156">Esta seção realça as diferenças que são relevantes para este artigo.</span><span class="sxs-lookup"><span data-stu-id="1aad5-156">This section will highlight the differences that you see relevant to this article.</span></span>

### <a name="multiple-resource-versions"></a><span data-ttu-id="1aad5-157">Várias versões de recursos</span><span class="sxs-lookup"><span data-stu-id="1aad5-157">Multiple Resource Versions</span></span>

<span data-ttu-id="1aad5-158">Não havia suporte para instalar e usar várias versões de recursos lado a lado no PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="1aad5-158">Installing and using multiple versions of resources side by side was not supported in PowerShell 4.0.</span></span> <span data-ttu-id="1aad5-159">Se você perceber problemas de importação de recursos em sua configuração, certifique-se de que só há uma versão instalada do recurso.</span><span class="sxs-lookup"><span data-stu-id="1aad5-159">If you notice issues importing resources into your Configuration, ensure that you only have one version of the resource installed.</span></span>

<span data-ttu-id="1aad5-160">Na imagem abaixo, estão instaladas duas versões do módulo **xPSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1aad5-160">In the image below, two versions of the **xPSDesiredStateConfiguration** module are installed.</span></span>

![Várias versões fixas de recurso](media/import-dscresource/multiple-resource-versions-broken.png)

<span data-ttu-id="1aad5-162">Copie o conteúdo da sua versão de módulo desejada para o nível superior do diretório do módulo.</span><span class="sxs-lookup"><span data-stu-id="1aad5-162">Copy the contents of your desired module version to the top level of the module directory.</span></span>

![Várias versões fixas de recurso](media/import-dscresource/multiple-resource-versions-fixed.png)

### <a name="resource-location"></a><span data-ttu-id="1aad5-164">Localização do recurso</span><span class="sxs-lookup"><span data-stu-id="1aad5-164">Resource location</span></span>

<span data-ttu-id="1aad5-165">Ao criar e compilar configurações, seus recursos podem ser armazenados em qualquer diretório especificado por seu [PSModulePath](/powershell/scripting/developer/module/modifying-the-psmodulepath-installation-path).</span><span class="sxs-lookup"><span data-stu-id="1aad5-165">When authoring and compiling Configurations, your resources can be stored in any directory specified by your [PSModulePath](/powershell/scripting/developer/module/modifying-the-psmodulepath-installation-path).</span></span> <span data-ttu-id="1aad5-166">No PowerShell 4.0, o LCM requer que todos os módulos de recursos DSC sejam armazenados em "Arquivos de Programa\WindowsPowerShell\Modules" ou `$pshome\Modules`.</span><span class="sxs-lookup"><span data-stu-id="1aad5-166">In PowerShell 4.0, the LCM requires all DSC resource modules to be stored under "Program Files\WindowsPowerShell\Modules" or `$pshome\Modules`.</span></span> <span data-ttu-id="1aad5-167">A partir do PowerShell 5.0, esse requisito foi removido e os módulos de recursos podem ser armazenados em qualquer diretório especificado por `PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="1aad5-167">Beginning in PowerShell 5.0, this requirement was removed, and resource modules can be stored in any directory specified by `PSModulePath`.</span></span>

### <a name="moduleversion-added"></a><span data-ttu-id="1aad5-168">ModuleVersion adicionado</span><span class="sxs-lookup"><span data-stu-id="1aad5-168">ModuleVersion added</span></span>

<span data-ttu-id="1aad5-169">A partir do PowerShell 5.0, o parâmetro `-ModuleVersion` permite especificar qual versão de um módulo deve ser usada na configuração.</span><span class="sxs-lookup"><span data-stu-id="1aad5-169">Beginning in PowerShell 5.0, the `-ModuleVersion` parameter allows you to specify which version of a module to use within your configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="1aad5-170">Confira também</span><span class="sxs-lookup"><span data-stu-id="1aad5-170">See also</span></span>

- [<span data-ttu-id="1aad5-171">Recursos</span><span class="sxs-lookup"><span data-stu-id="1aad5-171">Resources</span></span>](../resources/resources.md)
