---
ms.date: 12/12/2018
keywords: dsc,powershell,recurso,galeria,instalação
title: Adicionar parâmetros a uma configuração
ms.openlocfilehash: 72e6c15593d11ed39d7fe8ea79f794089f410cf8
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954193"
---
# <a name="add-parameters-to-a-configuration"></a><span data-ttu-id="9d780-103">Adicionar parâmetros a uma configuração</span><span class="sxs-lookup"><span data-stu-id="9d780-103">Add Parameters to a Configuration</span></span>

<span data-ttu-id="9d780-104">Como as Funções, as [Configurações](configurations.md) podem ter parâmetros que possibilitam configurações mais dinâmicas com base na inserção do usuário.</span><span class="sxs-lookup"><span data-stu-id="9d780-104">Like Functions, [Configurations](configurations.md) can be parameterized to allow more dynamic configurations based on user input.</span></span> <span data-ttu-id="9d780-105">As etapas são semelhantes às descritas em [Funções com parâmetros](/powershell/module/microsoft.powershell.core/about/about_functions).</span><span class="sxs-lookup"><span data-stu-id="9d780-105">The steps are similar to those described in [Functions with Parameters](/powershell/module/microsoft.powershell.core/about/about_functions).</span></span>

<span data-ttu-id="9d780-106">Este exemplo começa com uma Configuração básica que define o serviço "Spooler" como "Running".</span><span class="sxs-lookup"><span data-stu-id="9d780-106">This example starts with a basic Configuration that configures the "Spooler" service to be "Running".</span></span>

```powershell
Configuration TestConfig
{
    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node localhost
    {
        Service 'Spooler'
        {
            Name = 'Spooler'
            State = 'Running'
        }
    }
}
```

## <a name="built-in-configuration-parameters"></a><span data-ttu-id="9d780-107">Parâmetros de configuração internos</span><span class="sxs-lookup"><span data-stu-id="9d780-107">Built-in Configuration parameters</span></span>

<span data-ttu-id="9d780-108">Porém, diferente de uma Função, o atributo [CmdletBinding](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute) não adiciona funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="9d780-108">Unlike a Function though, the [CmdletBinding](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute) attribute adds no functionality.</span></span> <span data-ttu-id="9d780-109">Além de [Parâmetros Comuns](/powershell/module/microsoft.powershell.core/about/about_commonparameters), as Configurações também podem usar os parâmetros internos a seguir, sem exigir que você os defina.</span><span class="sxs-lookup"><span data-stu-id="9d780-109">In addition to [Common Parameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters), Configurations can also use the following built in parameters, without requiring you to define them.</span></span>

|<span data-ttu-id="9d780-110">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="9d780-110">Parameter</span></span>  |<span data-ttu-id="9d780-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="9d780-111">Description</span></span>  |
|---------|---------|
|`-InstanceName`|<span data-ttu-id="9d780-112">Usado na definição de [Configurações de Composição](compositeconfigs.md)</span><span class="sxs-lookup"><span data-stu-id="9d780-112">Used in defining [Composite Configurations](compositeconfigs.md)</span></span>|
|`-DependsOn`|<span data-ttu-id="9d780-113">Usado na definição de [Configurações de Composição](compositeconfigs.md)</span><span class="sxs-lookup"><span data-stu-id="9d780-113">Used in defining [Composite Configurations](compositeconfigs.md)</span></span>|
|`-PSDSCRunAsCredential`|<span data-ttu-id="9d780-114">Usado na definição de [Configurações de Composição](compositeconfigs.md)</span><span class="sxs-lookup"><span data-stu-id="9d780-114">Used in defining [Composite Configurations](compositeconfigs.md)</span></span>|
|`-ConfigurationData`|<span data-ttu-id="9d780-115">Usado para passar [Dados de Configuração](configData.md) estruturados para uso na Configuração.</span><span class="sxs-lookup"><span data-stu-id="9d780-115">Used to pass in structured [Configuration Data](configData.md) for use in the Configuration.</span></span>|
|`-OutputPath`|<span data-ttu-id="9d780-116">Usado para especificar onde o arquivo "\<nome_do_computador\>.mof" será compilado</span><span class="sxs-lookup"><span data-stu-id="9d780-116">Used to specify where your "\<computername\>.mof" file will be compiled</span></span>|

## <a name="adding-your-own-parameters-to-configurations"></a><span data-ttu-id="9d780-117">Adicionando seus próprios parâmetros às Configurações</span><span class="sxs-lookup"><span data-stu-id="9d780-117">Adding your own parameters to Configurations</span></span>

<span data-ttu-id="9d780-118">Além dos parâmetros internos, você também pode adicionar seus próprios parâmetros às Configurações.</span><span class="sxs-lookup"><span data-stu-id="9d780-118">In addition to the built-in parameters, you can also add your own parameters to your Configurations.</span></span> <span data-ttu-id="9d780-119">O bloco de parâmetro vai diretamente dentro da declaração da Configuração, assim como em uma Função.</span><span class="sxs-lookup"><span data-stu-id="9d780-119">The parameter block goes directly inside the Configuration declaration, just like a Function.</span></span> <span data-ttu-id="9d780-120">Um bloco de parâmetro de Configuração deve estar fora de qualquer declaração de **Nó** e acima de qualquer instrução de *importação*.</span><span class="sxs-lookup"><span data-stu-id="9d780-120">A Configuration parameter block should be outside any **Node** declarations, and above any *import* statements.</span></span> <span data-ttu-id="9d780-121">Ao adicionar parâmetros, você pode tornar suas Configurações mais robustas e dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="9d780-121">By adding parameters, you can make your Configurations more robust and dynamic.</span></span>

```powershell
Configuration TestConfig
{
    param
    (

    )
```

### <a name="add-a-computername-parameter"></a><span data-ttu-id="9d780-122">Adicionar um parâmetro ComputerName</span><span class="sxs-lookup"><span data-stu-id="9d780-122">Add a ComputerName parameter</span></span>

<span data-ttu-id="9d780-123">O primeiro parâmetro que pode ser adicionado é `-Computername`. Assim, é possível compilar dinamicamente um arquivo ".mof" para qualquer `-Computername` que você passa para sua configuração.</span><span class="sxs-lookup"><span data-stu-id="9d780-123">The first parameter you might add is a `-Computername` parameter so you can dynamically compile a ".mof" file for any `-Computername` you pass to your configuration.</span></span> <span data-ttu-id="9d780-124">Como em Funções, você também pode definir um valor padrão, caso o usuário não passe um valor para `-ComputerName`</span><span class="sxs-lookup"><span data-stu-id="9d780-124">Like Functions, you can also define a default value, in case the user does not pass in a value for `-ComputerName`</span></span>

```powershell
param
(
    [String]
    $ComputerName="localhost"
)
```

<span data-ttu-id="9d780-125">Em sua configuração, você pode especificar o parâmetro `-ComputerName` ao definir o bloco Nó.</span><span class="sxs-lookup"><span data-stu-id="9d780-125">Within your configuration, you can then specify your `-ComputerName` parameter when defining your Node block.</span></span>

```powershell
Node $ComputerName
{

}
```

### <a name="calling-your-configuration-with-parameters"></a><span data-ttu-id="9d780-126">Chamando sua Configuração com parâmetros</span><span class="sxs-lookup"><span data-stu-id="9d780-126">Calling your Configuration with parameters</span></span>

<span data-ttu-id="9d780-127">Depois de adicionar parâmetros à sua Configuração, você pode usá-los como faria com um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9d780-127">After you have added parameters to your Configuration, you can use them just like you would with a cmdlet.</span></span>

```powershell
TestConfig -ComputerName "server01"
```

### <a name="compiling-multiple-mof-files"></a><span data-ttu-id="9d780-128">Compilando vários arquivos .mof</span><span class="sxs-lookup"><span data-stu-id="9d780-128">Compiling multiple .mof files</span></span>

<span data-ttu-id="9d780-129">O bloco Nó também pode aceitar uma lista de nomes de computador separados por vírgula, gerando arquivos ".mof" para cada um.</span><span class="sxs-lookup"><span data-stu-id="9d780-129">The Node block can also accept a comma-separated list of computer names and will generate ".mof" files for each.</span></span> <span data-ttu-id="9d780-130">Você também pode executar o exemplo a seguir para gerar arquivos ".mof" para todos os computadores passados ao parâmetro `-ComputerName`.</span><span class="sxs-lookup"><span data-stu-id="9d780-130">You can run the following example to generate ".mof" files for all of the computers passed to the `-ComputerName` parameter.</span></span>

```powershell
Configuration TestConfig
{
    param
    (
        [String]
        $ComputerName="localhost"
    )

    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service 'Spooler'
        {
            Name = 'Spooler'
            State = 'Running'
        }
    }
}

TestConfig -ComputerName "server01", "server02", "server03"
```

## <a name="advanced-parameters-in-configurations"></a><span data-ttu-id="9d780-131">Parâmetros avançados em Configurações</span><span class="sxs-lookup"><span data-stu-id="9d780-131">Advanced parameters in Configurations</span></span>

<span data-ttu-id="9d780-132">Além de um parâmetro `-ComputerName`, podemos adicionar parâmetros para o nome e o estado do serviço.</span><span class="sxs-lookup"><span data-stu-id="9d780-132">In addition to a `-ComputerName` parameter, we can add parameters for the service name and state.</span></span> <span data-ttu-id="9d780-133">O exemplo a seguir adiciona um bloco de parâmetro com um parâmetro `-ServiceName` e o usa para definir dinamicamente o bloco de recurso **Service**.</span><span class="sxs-lookup"><span data-stu-id="9d780-133">The following example adds a parameter block with a `-ServiceName` parameter and uses it to dynamically define the **Service** resource block.</span></span> <span data-ttu-id="9d780-134">Também adiciona um parâmetro `-State` para definir dinamicamente o **State** no bloco de recurso **Service**.</span><span class="sxs-lookup"><span data-stu-id="9d780-134">It also adds a `-State` parameter to dynamically define the **State** in the **Service** resource block.</span></span>

```powershell
Configuration TestConfig
{
    param
    (
        [String]
        $ServiceName,

        [String]
        $State,

        [String]
        $ComputerName="localhost"
    )

    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node $ComputerName
    {
        Service $ServiceName
        {
            Name = $ServiceName
            State = $State
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="9d780-135">Em cenários mais avançados, pode fazer mais sentido mover seus dados dinâmicos para [Dados de Configuração](configData.md) estruturados.</span><span class="sxs-lookup"><span data-stu-id="9d780-135">In more advacned scenarios, it might make more sense to move your dynamic data into a structured [Configuration Data](configData.md).</span></span>

<span data-ttu-id="9d780-136">O exemplo Configuração agora usa um `$ServiceName` dinâmico, mas se um não for especificado, a compilação resultará em um erro.</span><span class="sxs-lookup"><span data-stu-id="9d780-136">The example Configuration now takes a dynamic `$ServiceName`, but if one is not specified, compiling results in an error.</span></span> <span data-ttu-id="9d780-137">Você pode adicionar um valor padrão como o deste exemplo.</span><span class="sxs-lookup"><span data-stu-id="9d780-137">You could add a default value like this example.</span></span>

```powershell
[String]
$ServiceName="Spooler"
```

<span data-ttu-id="9d780-138">Porém, nessa instância, faz mais sentido simplesmente forçar o usuário a especificar um valor para o parâmetro `$ServiceName`.</span><span class="sxs-lookup"><span data-stu-id="9d780-138">In this instance though, it makes more sense to simply force the user to specify a value for the `$ServiceName` parameter.</span></span> <span data-ttu-id="9d780-139">O atributo `parameter` permite adicionar mais suporte de validação e de pipeline aos parâmetros da Configuração.</span><span class="sxs-lookup"><span data-stu-id="9d780-139">The `parameter` attribute allows you to add further validation and pipeline support to your Configuration's parameters.</span></span>

<span data-ttu-id="9d780-140">Acima de qualquer declaração de parâmetro, adicione o bloco de atributo `parameter`, como no exemplo abaixo.</span><span class="sxs-lookup"><span data-stu-id="9d780-140">Above any parameter declaration, add the `parameter` attribute block as in the example below.</span></span>

```powershell
[parameter()]
[String]
$ServiceName
```

<span data-ttu-id="9d780-141">Você pode especificar argumentos para cada atributo `parameter`, de modo a controlar aspectos do parâmetro definido.</span><span class="sxs-lookup"><span data-stu-id="9d780-141">You can specify arguments to each `parameter` attribute, to control aspects of the defined parameter.</span></span> <span data-ttu-id="9d780-142">O exemplo a seguir transforma `$ServiceName` em um parâmetro **Mandatory**.</span><span class="sxs-lookup"><span data-stu-id="9d780-142">The following example makes the `$ServiceName` a **Mandatory** parameter.</span></span>

```powershell
[parameter(Mandatory)]
[String]
$ServiceName
```

<span data-ttu-id="9d780-143">Para o parâmetro `$State`, gostaríamos de impedir o usuário de especificar valores fora de um conjunto predefinido (como Running ou Stopped). O atributo `ValidationSet*` impediria o usuário de especificar esses valores.</span><span class="sxs-lookup"><span data-stu-id="9d780-143">For the `$State` parameter, we would like to prevent the user from specifying values outside of a predefined set (like Running, Stopped) the `ValidationSet*`attribute would prevent the user from specifying values outside of a predefined set (like Running, Stopped).</span></span> <span data-ttu-id="9d780-144">O exemplo a seguir adiciona o atributo `ValidationSet` ao parâmetro `$State`.</span><span class="sxs-lookup"><span data-stu-id="9d780-144">The following example adds the `ValidationSet` attribute to the `$State` parameter.</span></span> <span data-ttu-id="9d780-145">Uma vez que não queremos transformar o parâmetro `$State` como **Mandatory**, precisaremos adicionar um valor padrão para ele.</span><span class="sxs-lookup"><span data-stu-id="9d780-145">Since we do not want to make the `$State` parameter **Mandatory**, we will need to add a default value for it.</span></span>

```powershell
[ValidateSet("Running", "Stopped")]
[String]
$State="Running"
```

> [!NOTE]
> <span data-ttu-id="9d780-146">Não é preciso especificar um atributo `parameter` ao usar um atributo `validation`.</span><span class="sxs-lookup"><span data-stu-id="9d780-146">You do not need to specify a `parameter` attribute when using a `validation` attribute.</span></span>

<span data-ttu-id="9d780-147">Você pode saber mais sobre os atributos de validação e `parameter` em [about_Functions_Advanced_Parameters](/powershell/module/microsoft.powershell.core/about/about_Functions_Advanced_Parameters).</span><span class="sxs-lookup"><span data-stu-id="9d780-147">You can read more about the `parameter` and validation attributes in [about_Functions_Advanced_Parameters](/powershell/module/microsoft.powershell.core/about/about_Functions_Advanced_Parameters).</span></span>

## <a name="fully-parameterized-configuration"></a><span data-ttu-id="9d780-148">Configuração totalmente parametrizada</span><span class="sxs-lookup"><span data-stu-id="9d780-148">Fully parameterized Configuration</span></span>

<span data-ttu-id="9d780-149">Agora temos uma Configuração parametrizada que força o usuário a especificar um `-InstanceName`, `-ServiceName`, e valida o parâmetro `-State`.</span><span class="sxs-lookup"><span data-stu-id="9d780-149">We now have a parameterized Configuration that forces the user to specify an `-InstanceName`, `-ServiceName`, and validates the `-State` parameter.</span></span>

```powershell
Configuration TestConfig
{
    param
    (
        [parameter(Mandatory)]
        [String]
        $ServiceName,

        [ValidateSet("Running","Stopped")]
        [String]
        $State="Running",

        [String]
        $ComputerName="localhost",
    )

    # It is best practice to explicitly import any required resources or modules.
    Import-DSCResource -Module PSDesiredStateConfiguration

    Node localhost
    {
        Service $ServiceName
        {
            Name = $ServiceName
            State = $State
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="9d780-150">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9d780-150">See also</span></span>

- [<span data-ttu-id="9d780-151">Gravar ajuda para configurações de DSC</span><span class="sxs-lookup"><span data-stu-id="9d780-151">Write help for DSC configurations</span></span>](configHelp.md)
- [<span data-ttu-id="9d780-152">Configurações dinâmicas</span><span class="sxs-lookup"><span data-stu-id="9d780-152">Dynamic Configurations</span></span>](flow-control-in-configurations.md)
- [<span data-ttu-id="9d780-153">Usar Dados de Configuração em suas Configurações</span><span class="sxs-lookup"><span data-stu-id="9d780-153">Use Configuration Data in your Configurations</span></span>](configData.md)
- [<span data-ttu-id="9d780-154">Separar dados de configuração e de ambiente</span><span class="sxs-lookup"><span data-stu-id="9d780-154">Separate configuration and environment data</span></span>](separatingEnvData.md)
