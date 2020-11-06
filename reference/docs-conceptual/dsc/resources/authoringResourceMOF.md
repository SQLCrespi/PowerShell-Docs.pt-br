---
ms.date: 07/08/2020
keywords: DSC,powershell,configuração,instalação
title: Escrevendo um recurso personalizado de DSC com MOF
description: Este artigo define o esquema para um recurso de DSC personalizado em um arquivo MOF e implementa o recurso em um arquivo de script do PowerShell.
ms.openlocfilehash: e79a37699c468b2c55c307c96f1c193a2c1595b3
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92667174"
---
# <a name="writing-a-custom-dsc-resource-with-mof"></a><span data-ttu-id="b5354-104">Escrevendo um recurso personalizado de DSC com MOF</span><span class="sxs-lookup"><span data-stu-id="b5354-104">Writing a custom DSC resource with MOF</span></span>

> <span data-ttu-id="b5354-105">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="b5354-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="b5354-106">Neste artigo, definiremos o esquema para um recurso personalizado de DSC (Desired State Configuration) do Windows PowerShell em um arquivo MOF e implementaremos o recurso em um arquivo de script do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5354-106">In this article, we will define the schema for a Windows PowerShell Desired State Configuration (DSC) custom resource in a MOF file, and implement the resource in a Windows PowerShell script file.</span></span>
<span data-ttu-id="b5354-107">Esse recurso personalizado serve para criar e manter um site da web.</span><span class="sxs-lookup"><span data-stu-id="b5354-107">This custom resource is for creating and maintaining a web site.</span></span>

## <a name="creating-the-mof-schema"></a><span data-ttu-id="b5354-108">Criando o esquema MOF</span><span class="sxs-lookup"><span data-stu-id="b5354-108">Creating the MOF schema</span></span>

<span data-ttu-id="b5354-109">O esquema define as propriedades do recurso que pode ser configurado por um script de configuração DSC.</span><span class="sxs-lookup"><span data-stu-id="b5354-109">The schema defines the properties of your resource that can be configured by a DSC configuration script.</span></span>

### <a name="folder-structure-for-a-mof-resource"></a><span data-ttu-id="b5354-110">Estrutura de pastas para um recurso MOF</span><span class="sxs-lookup"><span data-stu-id="b5354-110">Folder structure for a MOF resource</span></span>

<span data-ttu-id="b5354-111">Para implementar um recurso personalizado de DSC com esquema MOF, crie a seguinte estrutura de pastas.</span><span class="sxs-lookup"><span data-stu-id="b5354-111">To implement a DSC custom resource with a MOF schema, create the following folder structure.</span></span> <span data-ttu-id="b5354-112">O esquema MOF é definido no arquivo `Demo_IISWebsite.schema.mof`, e o script de recurso é definido em `Demo_IISWebsite.psm1`.</span><span class="sxs-lookup"><span data-stu-id="b5354-112">The MOF schema is defined in the file `Demo_IISWebsite.schema.mof`, and the resource script is defined in `Demo_IISWebsite.psm1`.</span></span> <span data-ttu-id="b5354-113">Opcionalmente, você pode criar um arquivo de manifesto do módulo (psd1).</span><span class="sxs-lookup"><span data-stu-id="b5354-113">Optionally, you can create a module manifest (psd1) file.</span></span>

```
$env:ProgramFiles\WindowsPowerShell\Modules (folder)
    |- MyDscResources (folder)
        |- DSCResources (folder)
            |- Demo_IISWebsite (folder)
                |- Demo_IISWebsite.psd1 (file, optional)
                |- Demo_IISWebsite.psm1 (file, required)
                |- Demo_IISWebsite.schema.mof (file, required)
```

> [!NOTE]
> <span data-ttu-id="b5354-114">É necessário criar uma pasta chamada DSCResources na pasta de nível superior e que a pasta para cada recurso tenha o mesmo nome que o recurso.</span><span class="sxs-lookup"><span data-stu-id="b5354-114">It is necessary to create a folder named DSCResources under the top-level folder, and that the folder for each resource must have the same name as the resource.</span></span>

### <a name="the-contents-of-the-mof-file"></a><span data-ttu-id="b5354-115">O conteúdo do arquivo MOF</span><span class="sxs-lookup"><span data-stu-id="b5354-115">The contents of the MOF file</span></span>

<span data-ttu-id="b5354-116">Segue um exemplo de arquivo MOF que pode ser usado para um recurso de sites personalizados.</span><span class="sxs-lookup"><span data-stu-id="b5354-116">Following is an example MOF file that can be used for a custom website resource.</span></span> <span data-ttu-id="b5354-117">Para seguir esse exemplo, salve o esquema em um arquivo e chame o arquivo de `Demo_IISWebsite.schema.mof`.</span><span class="sxs-lookup"><span data-stu-id="b5354-117">To follow this example, save this schema to a file, and call the file `Demo_IISWebsite.schema.mof`.</span></span>

```
[ClassVersion("1.0.0"), FriendlyName("Website")]
class Demo_IISWebsite : OMI_BaseResource
{
  [Key] string Name;
  [Required] string PhysicalPath;
  [write,ValueMap{"Present", "Absent"},Values{"Present", "Absent"}] string Ensure;
  [write,ValueMap{"Started","Stopped"},Values{"Started", "Stopped"}] string State;
  [write] string Protocol[];
  [write] string BindingInfo[];
  [write] string ApplicationPool;
  [read] string ID;
};
```

<span data-ttu-id="b5354-118">Observe o seguinte sobre o código anterior:</span><span class="sxs-lookup"><span data-stu-id="b5354-118">Note the following about the previous code:</span></span>

- <span data-ttu-id="b5354-119">`FriendlyName` define o nome que você pode usar para se referir a esse recurso personalizado em scripts de configuração DSC.</span><span class="sxs-lookup"><span data-stu-id="b5354-119">`FriendlyName` defines the name you can use to refer to this custom resource in DSC configuration scripts.</span></span> <span data-ttu-id="b5354-120">Neste exemplo, `Website` é equivalente ao nome amigável `Archive` para o recurso interno Archive.</span><span class="sxs-lookup"><span data-stu-id="b5354-120">In this example, `Website` is equivalent to the friendly name `Archive` for the built-in Archive resource.</span></span>
- <span data-ttu-id="b5354-121">A classe que você define para o recurso personalizado deve derivar de `OMI_BaseResource`.</span><span class="sxs-lookup"><span data-stu-id="b5354-121">The class you define for your custom resource must derive from `OMI_BaseResource`.</span></span>
- <span data-ttu-id="b5354-122">O qualificador de tipo, `[Key]`, em uma propriedade indica que essa propriedade identificará exclusivamente a instância do recurso.</span><span class="sxs-lookup"><span data-stu-id="b5354-122">The type qualifier, `[Key]`, on a property indicates that this property will uniquely identify the resource instance.</span></span> <span data-ttu-id="b5354-123">Pelo menos uma propriedade `[Key]` é necessária.</span><span class="sxs-lookup"><span data-stu-id="b5354-123">At least one `[Key]` property is required.</span></span>
- <span data-ttu-id="b5354-124">O qualificador `[Required]` indica que a propriedade é necessária (um valor deve ser especificado em qualquer script de configuração que usa esse recurso).</span><span class="sxs-lookup"><span data-stu-id="b5354-124">The `[Required]` qualifier indicates that the property is required (a value must be specified in any configuration script that uses this resource).</span></span>
- <span data-ttu-id="b5354-125">O qualificador `[write]` indica que essa propriedade é opcional ao usar o recurso personalizado em um script de configuração.</span><span class="sxs-lookup"><span data-stu-id="b5354-125">The `[write]` qualifier indicates that this property is optional when using the custom resource in a configuration script.</span></span> <span data-ttu-id="b5354-126">O qualificador `[read]` indica que uma propriedade não pode ser definida por uma configuração e destina-se apenas para fins de relatório.</span><span class="sxs-lookup"><span data-stu-id="b5354-126">The `[read]` qualifier indicates that a property cannot be set by a configuration, and is for reporting purposes only.</span></span>
- <span data-ttu-id="b5354-127">`Values` restringe os valores que podem ser atribuídos à propriedade para a lista de valores definidos em `ValueMap`.</span><span class="sxs-lookup"><span data-stu-id="b5354-127">`Values` restricts the values that can be assigned to the property to the list of values defined in `ValueMap`.</span></span> <span data-ttu-id="b5354-128">Para obter mais informações, consulte [ValueMap e Qualificadores de Valor](/windows/desktop/WmiSdk/value-map).</span><span class="sxs-lookup"><span data-stu-id="b5354-128">For more information, see [ValueMap and Value Qualifiers](/windows/desktop/WmiSdk/value-map).</span></span>
- <span data-ttu-id="b5354-129">É recomendável incluir uma propriedade chamada `Ensure` com os valores `Present` e `Absent` em seu recurso como uma maneira de manter um estilo consistente com recursos internos de DSC.</span><span class="sxs-lookup"><span data-stu-id="b5354-129">Including a property called `Ensure` with values `Present` and `Absent` in your resource is recommended as a way to maintain a consistent style with built-in DSC resources.</span></span>
- <span data-ttu-id="b5354-130">Nomeie o arquivo de esquema para o recurso personalizado da seguinte maneira: `classname.schema.mof`, em que `classname` é o identificador que segue a palavra-chave `class` na definição do esquema.</span><span class="sxs-lookup"><span data-stu-id="b5354-130">Name the schema file for your custom resource as follows: `classname.schema.mof`, where `classname` is the identifier that follows the `class` keyword in your schema definition.</span></span>

### <a name="writing-the-resource-script"></a><span data-ttu-id="b5354-131">Escrevendo o script de recurso</span><span class="sxs-lookup"><span data-stu-id="b5354-131">Writing the resource script</span></span>

<span data-ttu-id="b5354-132">O script de recurso implementa a lógica do recurso.</span><span class="sxs-lookup"><span data-stu-id="b5354-132">The resource script implements the logic of the resource.</span></span> <span data-ttu-id="b5354-133">Neste módulo, você deve incluir três funções chamadas `Get-TargetResource`, `Set-TargetResource` e `Test-TargetResource`.</span><span class="sxs-lookup"><span data-stu-id="b5354-133">In this module, you must include three functions called `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource`.</span></span> <span data-ttu-id="b5354-134">As três funções precisam usar um conjunto de parâmetros que seja idêntico ao conjunto de propriedades definidas no esquema MOF criado para seu recurso.</span><span class="sxs-lookup"><span data-stu-id="b5354-134">All three functions must take a parameter set that is identical to the set of properties defined in the MOF schema that you created for your resource.</span></span> <span data-ttu-id="b5354-135">Neste documento, esse conjunto de propriedades é chamado de "propriedades de recursos".</span><span class="sxs-lookup"><span data-stu-id="b5354-135">In this document, this set of properties is referred to as the "resource properties."</span></span> <span data-ttu-id="b5354-136">Armazene essas três funções em um arquivo chamado `<ResourceName>.psm1`.</span><span class="sxs-lookup"><span data-stu-id="b5354-136">Store these three functions in a file called `<ResourceName>.psm1`.</span></span> <span data-ttu-id="b5354-137">No exemplo a seguir, as funções são armazenadas em um arquivo chamado `Demo_IISWebsite.psm1`.</span><span class="sxs-lookup"><span data-stu-id="b5354-137">In the following example, the functions are stored in a file called `Demo_IISWebsite.psm1`.</span></span>

> [!NOTE]
> <span data-ttu-id="b5354-138">Ao executar o mesmo script de configuração no recurso mais de uma vez, você não receberá erros e o recurso permanecerá no mesmo estado do script executado uma vez.</span><span class="sxs-lookup"><span data-stu-id="b5354-138">When you run the same configuration script on your resource more than once, you should receive no errors and the resource should remain in the same state as running the script once.</span></span> <span data-ttu-id="b5354-139">Para fazer isso, verifique se suas funções `Get-TargetResource` e `Test-TargetResource` deixam o recurso inalterado e se chamar a função `Set-TargetResource` mais de uma vez em uma sequência com os mesmos valores de parâmetro é sempre equivalente a chamá-la uma vez.</span><span class="sxs-lookup"><span data-stu-id="b5354-139">To accomplish this, ensure that your `Get-TargetResource` and `Test-TargetResource` functions leave the resource unchanged, and that invoking the `Set-TargetResource` function more than once in a sequence with the same parameter values is always equivalent to invoking it once.</span></span>

<span data-ttu-id="b5354-140">Na implementação da função `Get-TargetResource`, utilize os valores da propriedade de recurso de chave que são fornecidos como parâmetros para verificar o status da instância do recurso especificado.</span><span class="sxs-lookup"><span data-stu-id="b5354-140">In the `Get-TargetResource` function implementation, use the key resource property values that are provided as parameters to check the status of the specified resource instance.</span></span> <span data-ttu-id="b5354-141">Essa função deve gerar uma tabela de hash que liste todas as propriedades de recursos como chaves e os valores reais dessas propriedades como valores correspondentes.</span><span class="sxs-lookup"><span data-stu-id="b5354-141">This function must return a hash table that lists all the resource properties as keys and the actual values of these properties as the corresponding values.</span></span> <span data-ttu-id="b5354-142">O código a seguir fornece um exemplo.</span><span class="sxs-lookup"><span data-stu-id="b5354-142">The following code provides an example.</span></span>

```powershell
# DSC uses the Get-TargetResource function to fetch the status of the resource instance
# specified in the parameters for the target machine
function Get-TargetResource
{
    param
    (
        [ValidateSet("Present", "Absent")]
        [string]$Ensure = "Present",

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$Name,

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$PhysicalPath,

        [ValidateSet("Started", "Stopped")]
        [string]$State = "Started",

        [string]$ApplicationPool,

        [string[]]$BindingInfo,

        [string[]]$Protocol
    )

        $getTargetResourceResult = $null;

        <#
          Insert logic that uses the mandatory parameter values to get the website and
          assign it to a variable called $Website
          Set $ensureResult to "Present" if the requested website exists and to "Absent" otherwise
        #>

        # Add all Website properties to the hash table
        # This simple example assumes that $Website is not null
        $getTargetResourceResult = @{
            Name = $Website.Name
            Ensure = $ensureResult
            PhysicalPath = $Website.physicalPath
            State = $Website.state
            ID = $Website.id
            ApplicationPool = $Website.applicationPool
            Protocol = $Website.bindings.Collection.protocol
            Binding = $Website.bindings.Collection.bindingInformation
        }

        $getTargetResourceResult
}
```

<span data-ttu-id="b5354-143">Dependendo dos valores especificados para as propriedades do recurso no script de configuração, a função `Set-TargetResource` deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b5354-143">Depending on the values that are specified for the resource properties in the configuration script, the `Set-TargetResource` must do one of the following:</span></span>

- <span data-ttu-id="b5354-144">Criar um novo site da web</span><span class="sxs-lookup"><span data-stu-id="b5354-144">Create a new website</span></span>
- <span data-ttu-id="b5354-145">Atualizar um site da web existente</span><span class="sxs-lookup"><span data-stu-id="b5354-145">Update an existing website</span></span>
- <span data-ttu-id="b5354-146">Excluir um site da web existente</span><span class="sxs-lookup"><span data-stu-id="b5354-146">Delete an existing website</span></span>

<span data-ttu-id="b5354-147">O exemplo a seguir ilustra isto.</span><span class="sxs-lookup"><span data-stu-id="b5354-147">The following example illustrates this.</span></span>

```powershell
# The Set-TargetResource function is used to create, delete or configure a website on the target machine.
function Set-TargetResource
{
    [CmdletBinding(SupportsShouldProcess=$true)]
    param
    (
        [ValidateSet("Present", "Absent")]
        [string]$Ensure = "Present",

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$Name,

        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [string]$PhysicalPath,

        [ValidateSet("Started", "Stopped")]
        [string]$State = "Started",

        [string]$ApplicationPool,

        [string[]]$BindingInfo,

        [string[]]$Protocol
    )

    <#
        If Ensure is set to "Present" and the website specified in the mandatory input parameters
          does not exist, then create it using the specified parameter values
        Else, if Ensure is set to "Present" and the website does exist, then update its properties
          to match the values provided in the non-mandatory parameter values
        Else, if Ensure is set to "Absent" and the website does not exist, then do nothing
        Else, if Ensure is set to "Absent" and the website does exist, then delete the website
    #>
}
```

<span data-ttu-id="b5354-148">Por fim, a função `Test-TargetResource` precisa utilizar o mesmo parâmetro configurado como `Get-TargetResource` e `Set-TargetResource`.</span><span class="sxs-lookup"><span data-stu-id="b5354-148">Finally, the `Test-TargetResource` function must take the same parameter set as `Get-TargetResource` and `Set-TargetResource`.</span></span> <span data-ttu-id="b5354-149">Na implementação de `Test-TargetResource`, verifique o status da instância do recurso que está especificada nos parâmetros de chave.</span><span class="sxs-lookup"><span data-stu-id="b5354-149">In your implementation of `Test-TargetResource`, check the status of the resource instance that is specified in the key parameters.</span></span> <span data-ttu-id="b5354-150">Se o estado real da instância do recurso não coincidir com os valores especificados no conjunto de parâmetros, gere `$false`.</span><span class="sxs-lookup"><span data-stu-id="b5354-150">If the actual status of the resource instance does not match the values specified in the parameter set, return `$false`.</span></span> <span data-ttu-id="b5354-151">Caso contrário, gere `$true`.</span><span class="sxs-lookup"><span data-stu-id="b5354-151">Otherwise, return `$true`.</span></span>

<span data-ttu-id="b5354-152">O código a seguir implementa a função `Test-TargetResource`.</span><span class="sxs-lookup"><span data-stu-id="b5354-152">The following code implements the `Test-TargetResource` function.</span></span>

```powershell
function Test-TargetResource
{
    [CmdletBinding()]
    [OutputType([System.Boolean])]
    param
    (
        [ValidateSet("Present","Absent")]
        [System.String]
        $Ensure,

        [parameter(Mandatory = $true)]
        [System.String]
        $Name,

        [parameter(Mandatory = $true)]
        [System.String]
        $PhysicalPath,

        [ValidateSet("Started","Stopped")]
        [System.String]
        $State,

        [System.String[]]
        $Protocol,

        [System.String[]]
        $BindingData,

        [System.String]
        $ApplicationPool
    )

    # Get the current state
    $currentState = Get-TargetResource -Ensure $Ensure -Name $Name -PhysicalPath $PhysicalPath -State $State -ApplicationPool $ApplicationPool -BindingInfo $BindingInfo -Protocol $Protocol

    # Write-Verbose "Use this cmdlet to deliver information about command processing."

    # Write-Debug "Use this cmdlet to write debug information while troubleshooting."

    # Include logic to
    $result = [System.Boolean]
    # Add logic to test whether the website is present and its status matches the supplied
    # parameter values. If it does, return true. If it does not, return false.
    $result
}
```

> [!NOTE]
> <span data-ttu-id="b5354-153">Para uma depuração mais fácil, use o cmdlet `Write-Verbose` na implementação das três funções anteriores.</span><span class="sxs-lookup"><span data-stu-id="b5354-153">For easier debugging, use the `Write-Verbose` cmdlet in your implementation of the previous three functions.</span></span> <span data-ttu-id="b5354-154">Esse cmdlet escreve o texto para o fluxo de mensagem detalhada.</span><span class="sxs-lookup"><span data-stu-id="b5354-154">This cmdlet writes text to the verbose message stream.</span></span> <span data-ttu-id="b5354-155">Por padrão, o fluxo de mensagem detalhada não é exibido, mas você pode exibi-lo alterando o valor da variável **$VerbosePreference** ou usando o parâmetro **Verbose** nos cmdlets DSC = novo.</span><span class="sxs-lookup"><span data-stu-id="b5354-155">By default, the verbose message stream is not displayed, but you can display it by changing the value of the **$VerbosePreference** variable or by using the **Verbose** parameter in the DSC cmdlets = new.</span></span>

### <a name="creating-the-module-manifest"></a><span data-ttu-id="b5354-156">Criando o manifesto de módulo</span><span class="sxs-lookup"><span data-stu-id="b5354-156">Creating the module manifest</span></span>

<span data-ttu-id="b5354-157">Por fim, use o cmdlet `New-ModuleManifest` para definir um arquivo `<ResourceName>.psd1` para o módulo de recurso personalizado.</span><span class="sxs-lookup"><span data-stu-id="b5354-157">Finally, use the `New-ModuleManifest` cmdlet to define a `<ResourceName>.psd1` file for your custom resource module.</span></span> <span data-ttu-id="b5354-158">Quando invocar esse cmdlet, faça referência ao arquivo de módulo do script (.psm1) descrito na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="b5354-158">When you invoke this cmdlet, reference the script module (.psm1) file described in the previous section.</span></span> <span data-ttu-id="b5354-159">Inclua `Get-TargetResource`, `Set-TargetResource` e `Test-TargetResource` na lista de funções para exportar.</span><span class="sxs-lookup"><span data-stu-id="b5354-159">Include `Get-TargetResource`, `Set-TargetResource`, and `Test-TargetResource` in the list of functions to export.</span></span> <span data-ttu-id="b5354-160">Segue um exemplo de arquivo de manifesto.</span><span class="sxs-lookup"><span data-stu-id="b5354-160">Following is an example manifest file.</span></span>

```powershell
# Module manifest for module 'Demo.IIS.Website'
#
# Generated on: 1/10/2013
#

@{

# Script module or binary module file associated with this manifest.
# RootModule = ''

# Version number of this module.
ModuleVersion = '1.0'

# ID used to uniquely identify this module
GUID = '6AB5ED33-E923-41d8-A3A4-5ADDA2B301DE'

# Author of this module
Author = 'Contoso'

# Company or vendor of this module
CompanyName = 'Contoso'

# Copyright statement for this module
Copyright = 'Contoso. All rights reserved.'

# Description of the functionality provided by this module
Description = 'This Module is used to support the creation and configuration of IIS Websites through Get, Set and Test API on the DSC managed nodes.'

# Minimum version of the Windows PowerShell engine required by this module
PowerShellVersion = '4.0'

# Minimum version of the common language runtime (CLR) required by this module
CLRVersion = '4.0'

# Modules that must be imported into the global environment prior to importing this module
RequiredModules = @("WebAdministration")

# Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
NestedModules = @("Demo_IISWebsite.psm1")

# Functions to export from this module
FunctionsToExport = @("Get-TargetResource", "Set-TargetResource", "Test-TargetResource")

# Cmdlets to export from this module
#CmdletsToExport = '*'

# HelpInfo URI of this module
# HelpInfoURI = ''
}
```

## <a name="supporting-psdscrunascredential"></a><span data-ttu-id="b5354-161">Dando suporte a PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="b5354-161">Supporting PsDscRunAsCredential</span></span>

> [!Note]
> <span data-ttu-id="b5354-162">**PsDscRunAsCredential** tem suporte no PowerShell 5.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="b5354-162">**PsDscRunAsCredential** is supported in PowerShell 5.0 and later.</span></span>

<span data-ttu-id="b5354-163">A propriedade **PsDscRunAsCredential** pode ser usada no bloco de recurso [Configurações DSC](../configurations/configurations.md) para especificar que o recurso deve ser executado em um conjunto de credenciais específico.</span><span class="sxs-lookup"><span data-stu-id="b5354-163">The **PsDscRunAsCredential** property can be used in [DSC configurations](../configurations/configurations.md) resource block to specify that the resource should be run under a specified set of credentials.</span></span> <span data-ttu-id="b5354-164">Para obter mais informações, veja [Executando o DSC com as credenciais do usuário](../configurations/runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="b5354-164">For more information, see [Running DSC with user credentials](../configurations/runAsUser.md).</span></span>

<span data-ttu-id="b5354-165">Para acessar o contexto do usuário de dentro de um recurso personalizado, você pode usar a variável automática `$PsDscContext`.</span><span class="sxs-lookup"><span data-stu-id="b5354-165">To access the user context from within a custom resource, you can use the automatic variable `$PsDscContext`.</span></span>

<span data-ttu-id="b5354-166">Por exemplo, o código a seguir escreveria o contexto do usuário em que o recurso está em execução para o fluxo de saída detalhada:</span><span class="sxs-lookup"><span data-stu-id="b5354-166">For example the following code would write the user context under which the resource is running to the verbose output stream:</span></span>

```powershell
if (PsDscContext.RunAsUser) {
    Write-Verbose "User: $PsDscContext.RunAsUser";
}
```

## <a name="rebooting-the-node"></a><span data-ttu-id="b5354-167">Reinicializar o nó</span><span class="sxs-lookup"><span data-stu-id="b5354-167">Rebooting the Node</span></span>

<span data-ttu-id="b5354-168">Se as ações executadas em sua função `Set-TargetResource` exigirem uma reinicialização, você poderá usar um sinalizador global para instruir o LCM a reinicializar o nó.</span><span class="sxs-lookup"><span data-stu-id="b5354-168">If the actions taken in your `Set-TargetResource` function require a reboot, you can use a global flag to tell the LCM to reboot the Node.</span></span> <span data-ttu-id="b5354-169">Essa reinicialização ocorre logo após a conclusão da função `Set-TargetResource`.</span><span class="sxs-lookup"><span data-stu-id="b5354-169">This reboot occurs directly after the `Set-TargetResource` function completes.</span></span>

<span data-ttu-id="b5354-170">Dentro de sua função `Set-TargetResource`, adicione a seguinte linha de código.</span><span class="sxs-lookup"><span data-stu-id="b5354-170">Inside your `Set-TargetResource` function, add the following line of code.</span></span>

```powershell
# Include this line if the resource requires a system reboot.
$global:DSCMachineStatus = 1
```

<span data-ttu-id="b5354-171">Para que o LCM reinicialize o nó, o sinalizador **RebootNodeIfNeeded** precisa ser definido como `$true`.</span><span class="sxs-lookup"><span data-stu-id="b5354-171">In order for the LCM to reboot the Node, the **RebootNodeIfNeeded** flag needs to be set to `$true`.</span></span>
<span data-ttu-id="b5354-172">A configuração **ActionAfterReboot** também deve ser definida como **ContinueConfiguration** , que é o padrão.</span><span class="sxs-lookup"><span data-stu-id="b5354-172">The **ActionAfterReboot** setting should also be set to **ContinueConfiguration** , which is the default.</span></span> <span data-ttu-id="b5354-173">Para obter mais informações sobre como configurar o LCM, confira [Configurando o Configuration Manager Local](../managing-nodes/metaConfig.md) ou [Configurando o Configuration Manager Local (v4)](../managing-nodes/metaConfig4.md).</span><span class="sxs-lookup"><span data-stu-id="b5354-173">For more information on configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md), or [Configuring the Local Configuration Manager (v4)](../managing-nodes/metaConfig4.md).</span></span>
