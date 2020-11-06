---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Usando o Import-DSCResource
description: O Import-DSCResource é uma palavra-chave dinâmica que só pode ser usada dentro do bloco de script de Configuração. Ele é usado para importar os módulos de recursos necessários em sua Configuração.
ms.openlocfilehash: f6dcad2c56848ec25eb79332c96fe6b0d438fe95
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658513"
---
# <a name="using-import-dscresource"></a><span data-ttu-id="16cab-105">Usando o Import-DSCResource</span><span class="sxs-lookup"><span data-stu-id="16cab-105">Using Import-DSCResource</span></span>

<span data-ttu-id="16cab-106">`Import-DSCResource` é uma palavra-chave dinâmica que só pode ser usada dentro de um bloco de script de Configuração para importar os recursos necessários em sua Configuração.</span><span class="sxs-lookup"><span data-stu-id="16cab-106">`Import-DSCResource` is a dynamic keyword, which can only be used inside a Configuration script block to import any resources needed in your Configuration.</span></span> <span data-ttu-id="16cab-107">Os recursos em `$PSHOME` são importados automaticamente, mas ainda consideramos que a melhor prática é importar explicitamente todos os recursos usados na sua [Configuração](Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="16cab-107">Resources under `$PSHOME` are imported automatically, but it is still considered best practice to explicitly import all resources used in your [Configuration](Configurations.md).</span></span>

<span data-ttu-id="16cab-108">A sintaxe para `Import-DSCResource` é mostrada abaixo.</span><span class="sxs-lookup"><span data-stu-id="16cab-108">The syntax for `Import-DSCResource` is shown below.</span></span> <span data-ttu-id="16cab-109">Ao especificar os módulos por nome, é necessário listar cada um deles em uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="16cab-109">When specifying modules by name, it is a requirement to list each on a new line.</span></span>

```syntax
Import-DscResource [-Name <ResourceName(s)>] [-ModuleName <ModuleName>] [-ModuleVersion <ModuleVersion>]
```

|    <span data-ttu-id="16cab-110">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="16cab-110">Parameter</span></span>     |                                                                                                                      <span data-ttu-id="16cab-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="16cab-111">Description</span></span>                                                                                                                      |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `-Name`          | <span data-ttu-id="16cab-112">Os nomes do recurso DSC que você deve importar.</span><span class="sxs-lookup"><span data-stu-id="16cab-112">The DSC resource name(s) that you must import.</span></span> <span data-ttu-id="16cab-113">Se o nome do módulo for especificado, o comando procurará pelos recursos DSC neste módulo; caso contrário, o comando procurará os recursos DSC em todos os caminhos de recursos DSC.</span><span class="sxs-lookup"><span data-stu-id="16cab-113">If the module name is specified, the command searches for these DSC resources within this module; otherwise the command searches the DSC resources in all DSC resource paths.</span></span> <span data-ttu-id="16cab-114">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="16cab-114">Wildcards are supported.</span></span> |
| `-ModuleName`    | <span data-ttu-id="16cab-115">O nome ou a especificação do módulo.</span><span class="sxs-lookup"><span data-stu-id="16cab-115">The module name, or module specification.</span></span>  <span data-ttu-id="16cab-116">Se você especificar os recursos a importar de um módulo, o comando tentará importar apenas os recursos.</span><span class="sxs-lookup"><span data-stu-id="16cab-116">If you specify resources to import from a module, the command will try to import only those resources.</span></span> <span data-ttu-id="16cab-117">Se você especificar apenas o módulo, o comando importará todos os recursos DSC no módulo.</span><span class="sxs-lookup"><span data-stu-id="16cab-117">If you specify the module only, the command imports all the DSC resources in the module.</span></span>            |
| `-ModuleVersion` | <span data-ttu-id="16cab-118">A partir do PowerShell 5.0, é possível especificar qual versão de um módulo a configuração deve usar.</span><span class="sxs-lookup"><span data-stu-id="16cab-118">Beginning in PowerShell 5.0, you can specify which version of a module a configuration should use.</span></span> <span data-ttu-id="16cab-119">Para saber mais, confira [Importar uma versão específica de um recurso instalado](sxsresource.md).</span><span class="sxs-lookup"><span data-stu-id="16cab-119">For more information, see [Import a specific version of an installed resource](sxsresource.md).</span></span>                                                    |

```powershell
Import-DscResource -ModuleName xActiveDirectory
```

## <a name="example-use-import-dscresource-within-a-configuration"></a><span data-ttu-id="16cab-120">Exemplo: Usar Import-DSCResource dentro de uma configuração</span><span class="sxs-lookup"><span data-stu-id="16cab-120">Example: Use Import-DSCResource within a configuration</span></span>

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
> <span data-ttu-id="16cab-121">Não há suporte para especificar vários valores para os nomes de recursos e módulos no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="16cab-121">Specifying multiple values for Resource names and modules names in same command are not supported.</span></span>
> <span data-ttu-id="16cab-122">Pode haver um comportamento não determinístico sobre qual recurso deve ser carregado de qual módulo, caso o mesmo recurso exista em vários módulos.</span><span class="sxs-lookup"><span data-stu-id="16cab-122">It can have non-deterministic behavior about which resource to load from which module in case same resource exists in multiple modules.</span></span> <span data-ttu-id="16cab-123">O comando abaixo resultará em erro durante a compilação.</span><span class="sxs-lookup"><span data-stu-id="16cab-123">Below command will result in error during compilation.</span></span>
>
> ```powershell
> Import-DscResource -Name UserConfigProvider*,TestLogger1 -ModuleName UserConfigProv,PsModuleForTestLogger
> ```

<span data-ttu-id="16cab-124">Ao usar somente o parâmetro Nome, considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="16cab-124">Things to consider when using only the Name parameter:</span></span>

- <span data-ttu-id="16cab-125">É uma operação de uso intensivo de recursos, dependendo do número de módulos instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="16cab-125">It is a resource-intensive operation depending on the number of modules installed on machine.</span></span>
- <span data-ttu-id="16cab-126">Ele carregará o primeiro recurso encontrado com o nome fornecido.</span><span class="sxs-lookup"><span data-stu-id="16cab-126">It will load the first resource found with the given name.</span></span> <span data-ttu-id="16cab-127">Caso haja mais de um recurso com o mesmo nome instalado, ele poderá carregar o recurso incorreto.</span><span class="sxs-lookup"><span data-stu-id="16cab-127">In the case where there is more than one resource with same name installed, it could load the wrong resource.</span></span>

<span data-ttu-id="16cab-128">O uso recomendado é especificar `–ModuleName` com o parâmetro `-Name`, como descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="16cab-128">The recommended usage is to specify `–ModuleName` with the `-Name` parameter, as described below.</span></span>

<span data-ttu-id="16cab-129">Esse uso oferece os seguintes benefícios:</span><span class="sxs-lookup"><span data-stu-id="16cab-129">This usage has the following benefits:</span></span>

- <span data-ttu-id="16cab-130">Reduz o impacto no desempenho ao limitar o escopo da pesquisa ao recurso especificado.</span><span class="sxs-lookup"><span data-stu-id="16cab-130">It reduces the performance impact by limiting the search scope for the specified resource.</span></span>
- <span data-ttu-id="16cab-131">Define explicitamente o módulo de definição do recurso, garantindo que o recurso correto seja carregado.</span><span class="sxs-lookup"><span data-stu-id="16cab-131">It explicitly defines the module defining the resource, ensuring the correct resource is loaded.</span></span>

> [!NOTE]
> <span data-ttu-id="16cab-132">No PowerShell 5.0, recursos de DSC podem ter várias versões e as versões podem ser instaladas em um computador lado a lado.</span><span class="sxs-lookup"><span data-stu-id="16cab-132">In PowerShell 5.0, DSC resources can have multiple versions, and versions can be installed on a computer side-by-side.</span></span> <span data-ttu-id="16cab-133">Isso é implementado por ter várias versões de um módulo de recursos que estão contidas na mesma pasta de módulo.</span><span class="sxs-lookup"><span data-stu-id="16cab-133">This is implemented by having multiple versions of a resource module that are contained in the same module folder.</span></span> <span data-ttu-id="16cab-134">Para obter mais informações, veja [Usando recursos com várias versões](sxsresource.md).</span><span class="sxs-lookup"><span data-stu-id="16cab-134">For more information, see [Using resources with multiple versions](sxsresource.md).</span></span>

## <a name="intellisense-with-import-dscresource"></a><span data-ttu-id="16cab-135">IntelliSense com Import-DSCResource</span><span class="sxs-lookup"><span data-stu-id="16cab-135">Intellisense with Import-DSCResource</span></span>

<span data-ttu-id="16cab-136">Ao criar a configuração DSC no ISE, o PowerShell fornece o IntelliSence para recursos e propriedades do recurso.</span><span class="sxs-lookup"><span data-stu-id="16cab-136">When authoring the DSC configuration in ISE, PowerShell provides IntelliSence for resources and resource properties.</span></span> <span data-ttu-id="16cab-137">Definições de recurso sob o caminho do módulo `$pshome` são carregados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="16cab-137">Resource definitions under the `$pshome` module path are loaded automatically.</span></span>
<span data-ttu-id="16cab-138">Quando você importa os recursos usando a palavra-chave `Import-DSCResource`, as definições de recursos especificadas são adicionadas e o Intellisense é expandido para incluir o esquema de recurso importado.</span><span class="sxs-lookup"><span data-stu-id="16cab-138">When you import resources using the `Import-DSCResource` keyword, the specified resource definitions are added and Intellisense is expanded to include the imported resource's schema.</span></span>

![IntelliSense no ISE para um recurso de DSC](media/import-dscresource/resource-intellisense.png)

> [!NOTE]
> <span data-ttu-id="16cab-140">A partir do PowerShell 5.0, o preenchimento com Tab foi adicionado ao ISE para recursos DSC e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="16cab-140">Beginning in PowerShell 5.0, tab completion was added to the ISE for DSC resources and their properties.</span></span> <span data-ttu-id="16cab-141">Para saber mais, confira [Recursos](../resources/resources.md).</span><span class="sxs-lookup"><span data-stu-id="16cab-141">For more information, see [Resources](../resources/resources.md).</span></span>

<span data-ttu-id="16cab-142">Ao compilar a configuração, o PowerShell usa as definições de recurso importadas para validar todos os blocos de recursos na configuração.</span><span class="sxs-lookup"><span data-stu-id="16cab-142">When compiling the Configuration, PowerShell uses the imported resource definitions to validate all resource blocks in the configuration.</span></span> <span data-ttu-id="16cab-143">Cada bloco de recurso é validado, usando a definição de esquema do recurso, para as regras a seguir.</span><span class="sxs-lookup"><span data-stu-id="16cab-143">Each resource block is validated, using the resource's schema definition, for the following rules.</span></span>

- <span data-ttu-id="16cab-144">Apenas as propriedades definidas no esquema são usadas.</span><span class="sxs-lookup"><span data-stu-id="16cab-144">Only properties defined in schema are used.</span></span>
- <span data-ttu-id="16cab-145">Os tipos de dados de cada propriedade estão corretos.</span><span class="sxs-lookup"><span data-stu-id="16cab-145">The data types for each property are correct.</span></span>
- <span data-ttu-id="16cab-146">As propriedades-chave estão especificadas.</span><span class="sxs-lookup"><span data-stu-id="16cab-146">Keys properties are specified.</span></span>
- <span data-ttu-id="16cab-147">Nenhuma propriedade somente leitura é usada.</span><span class="sxs-lookup"><span data-stu-id="16cab-147">No read-only property is used.</span></span>
- <span data-ttu-id="16cab-148">Validação em tipos de mapas de valor.</span><span class="sxs-lookup"><span data-stu-id="16cab-148">Validation on value maps types.</span></span>

<span data-ttu-id="16cab-149">Considere a configuração a seguir:</span><span class="sxs-lookup"><span data-stu-id="16cab-149">Consider the following configuration:</span></span>

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

<span data-ttu-id="16cab-150">Compilar essa configuração resulta em um erro.</span><span class="sxs-lookup"><span data-stu-id="16cab-150">Compiling this Configuration results in an error.</span></span>

```Output
PSDesiredStateConfiguration\WindowsFeature: At least one of the values 'Invalid' is not supported or
valid for property 'Ensure' on class 'WindowsFeature'. Please specify only supported values:
Present, Absent.
```

<span data-ttu-id="16cab-151">O IntelliSense e a validação de esquema permitem capturar mais erros durante o tempo de análise e compilação, evitando complicações no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="16cab-151">Intellisense and schema validation allow you to catch more errors during parse and compilation time, avoiding complications at run time.</span></span>

> [!NOTE]
> <span data-ttu-id="16cab-152">Cada recurso DSC pode ter um nome e um **FriendlyName** definidos pelo esquema do recurso.</span><span class="sxs-lookup"><span data-stu-id="16cab-152">Each DSC resource can have a name, and a **FriendlyName** defined by the resource's schema.</span></span> <span data-ttu-id="16cab-153">Abaixo estão as duas primeiras linhas de "MSFT_ServiceResource.shema.mof".</span><span class="sxs-lookup"><span data-stu-id="16cab-153">Below are the first two lines of "MSFT_ServiceResource.shema.mof".</span></span>
>
> ```syntax
> [ClassVersion("1.0.0"),FriendlyName("Service")]
> class MSFT_ServiceResource : OMI_BaseResource
> ```
>
> <span data-ttu-id="16cab-154">Ao usar esse recurso em uma configuração, você pode especificar **MSFT_ServiceResource** ou **Serviço**.</span><span class="sxs-lookup"><span data-stu-id="16cab-154">When using this resource in a Configuration, you can specify **MSFT_ServiceResource** or **Service**.</span></span>

## <a name="powershell-v4-and-v5-differences"></a><span data-ttu-id="16cab-155">Diferenças entre o PowerShell v4 e v5</span><span class="sxs-lookup"><span data-stu-id="16cab-155">PowerShell v4 and v5 differences</span></span>

<span data-ttu-id="16cab-156">Há várias diferenças que você vê ao criar configurações no PowerShell v. 4.0. PowerShell 5.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="16cab-156">There are multiple differences you see when authoring Configurations in PowerShell 4.0 vs. PowerShell 5.0 and later.</span></span> <span data-ttu-id="16cab-157">Esta seção realça as diferenças que são relevantes para este artigo.</span><span class="sxs-lookup"><span data-stu-id="16cab-157">This section will highlight the differences that you see relevant to this article.</span></span>

### <a name="multiple-resource-versions"></a><span data-ttu-id="16cab-158">Várias versões de recursos</span><span class="sxs-lookup"><span data-stu-id="16cab-158">Multiple Resource Versions</span></span>

<span data-ttu-id="16cab-159">Não havia suporte para instalar e usar várias versões de recursos lado a lado no PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="16cab-159">Installing and using multiple versions of resources side by side was not supported in PowerShell 4.0.</span></span> <span data-ttu-id="16cab-160">Se você perceber problemas de importação de recursos em sua configuração, certifique-se de que só há uma versão instalada do recurso.</span><span class="sxs-lookup"><span data-stu-id="16cab-160">If you notice issues importing resources into your Configuration, ensure that you only have one version of the resource installed.</span></span>

<span data-ttu-id="16cab-161">Na imagem abaixo, estão instaladas duas versões do módulo **xPSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="16cab-161">In the image below, two versions of the **xPSDesiredStateConfiguration** module are installed.</span></span>

![Várias versões de recurso instaladas na pasta](media/import-dscresource/multiple-resource-versions-broken.png)

<span data-ttu-id="16cab-163">Copie o conteúdo da sua versão de módulo desejada para o nível superior do diretório do módulo.</span><span class="sxs-lookup"><span data-stu-id="16cab-163">Copy the contents of your desired module version to the top level of the module directory.</span></span>

![Copie a versão desejada para o diretório de módulo de nível superior](media/import-dscresource/multiple-resource-versions-fixed.png)

### <a name="resource-location"></a><span data-ttu-id="16cab-165">Localização do recurso</span><span class="sxs-lookup"><span data-stu-id="16cab-165">Resource location</span></span>

<span data-ttu-id="16cab-166">Ao criar e compilar configurações, seus recursos podem ser armazenados em qualquer diretório especificado por seu [PSModulePath](/powershell/scripting/developer/module/modifying-the-psmodulepath-installation-path).</span><span class="sxs-lookup"><span data-stu-id="16cab-166">When authoring and compiling Configurations, your resources can be stored in any directory specified by your [PSModulePath](/powershell/scripting/developer/module/modifying-the-psmodulepath-installation-path).</span></span>
<span data-ttu-id="16cab-167">No PowerShell 4.0, o LCM requer que todos os módulos de recursos DSC sejam armazenados em "Arquivos de Programa\WindowsPowerShell\Modules" ou `$pshome\Modules`.</span><span class="sxs-lookup"><span data-stu-id="16cab-167">In PowerShell 4.0, the LCM requires all DSC resource modules to be stored under "Program Files\WindowsPowerShell\Modules" or `$pshome\Modules`.</span></span> <span data-ttu-id="16cab-168">A partir do PowerShell 5.0, esse requisito foi removido e os módulos de recursos podem ser armazenados em qualquer diretório especificado por `PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="16cab-168">Beginning in PowerShell 5.0, this requirement was removed, and resource modules can be stored in any directory specified by `PSModulePath`.</span></span>

### <a name="moduleversion-added"></a><span data-ttu-id="16cab-169">ModuleVersion adicionado</span><span class="sxs-lookup"><span data-stu-id="16cab-169">ModuleVersion added</span></span>

<span data-ttu-id="16cab-170">A partir do PowerShell 5.0, o parâmetro `-ModuleVersion` permite especificar qual versão de um módulo deve ser usada na configuração.</span><span class="sxs-lookup"><span data-stu-id="16cab-170">Beginning in PowerShell 5.0, the `-ModuleVersion` parameter allows you to specify which version of a module to use within your configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="16cab-171">Confira também</span><span class="sxs-lookup"><span data-stu-id="16cab-171">See also</span></span>

- [<span data-ttu-id="16cab-172">Recursos</span><span class="sxs-lookup"><span data-stu-id="16cab-172">Resources</span></span>](../resources/resources.md)
