---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Configurações DSC
description: As configurações DSC são scripts do PowerShell que definem um tipo especial de função.
ms.openlocfilehash: e59ad2791055ee3ff0150c342ec621d0228c4fc1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658568"
---
# <a name="dsc-configurations"></a><span data-ttu-id="4aa1a-104">Configurações DSC</span><span class="sxs-lookup"><span data-stu-id="4aa1a-104">DSC Configurations</span></span>

> <span data-ttu-id="4aa1a-105">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="4aa1a-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="4aa1a-106">As configurações DSC são scripts do PowerShell que definem um tipo especial de função.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-106">DSC configurations are PowerShell scripts that define a special type of function.</span></span> <span data-ttu-id="4aa1a-107">Para definir uma configuração utilize a palavra-chave do PowerShell **Configuration** .</span><span class="sxs-lookup"><span data-stu-id="4aa1a-107">To define a configuration, you use the PowerShell keyword **Configuration** .</span></span>

```powershell
Configuration MyDscConfiguration {
    Node "TEST-PC1" {
        WindowsFeature MyFeatureInstance {
            Ensure = 'Present'
            Name = 'RSAT'
        }
        WindowsFeature My2ndFeatureInstance {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}
MyDscConfiguration
```

<span data-ttu-id="4aa1a-108">Salve o script como um arquivo `.ps1`.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-108">Save the script as a `.ps1` file.</span></span>

## <a name="configuration-syntax"></a><span data-ttu-id="4aa1a-109">Sintaxe da configuração</span><span class="sxs-lookup"><span data-stu-id="4aa1a-109">Configuration syntax</span></span>

<span data-ttu-id="4aa1a-110">Um script de configuração é composto por estas partes:</span><span class="sxs-lookup"><span data-stu-id="4aa1a-110">A configuration script consists of the following parts:</span></span>

- <span data-ttu-id="4aa1a-111">O bloco **Configuration** .</span><span class="sxs-lookup"><span data-stu-id="4aa1a-111">The **Configuration** block.</span></span> <span data-ttu-id="4aa1a-112">É o bloco de script externo.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-112">This is the outermost script block.</span></span> <span data-ttu-id="4aa1a-113">Para defini-lo, use a palavra-chave **Configuration** e forneça um nome.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-113">You define it by using the **Configuration** keyword and providing a name.</span></span> <span data-ttu-id="4aa1a-114">Nesse caso, o nome da configuração é "MyDscConfiguration".</span><span class="sxs-lookup"><span data-stu-id="4aa1a-114">In this case, the name of the configuration is "MyDscConfiguration".</span></span>
- <span data-ttu-id="4aa1a-115">Um ou mais blocos de **Nó** .</span><span class="sxs-lookup"><span data-stu-id="4aa1a-115">One or more **Node** blocks.</span></span> <span data-ttu-id="4aa1a-116">Definem os nós (computadores ou máquinas virtuais) que você está configurando.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-116">These define the nodes (computers or VMs) that you are configuring.</span></span>
  <span data-ttu-id="4aa1a-117">Na configuração acima, há um bloco de **Nó** que tem como destino um computador denominado "TEST-PC1".</span><span class="sxs-lookup"><span data-stu-id="4aa1a-117">In the above configuration, there is one **Node** block that targets a computer named "TEST-PC1".</span></span>
  <span data-ttu-id="4aa1a-118">O bloco Nó pode aceitar vários nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-118">The Node block can accept multiple computer names.</span></span>
- <span data-ttu-id="4aa1a-119">Um ou mais blocos de recurso.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-119">One or more resource blocks.</span></span> <span data-ttu-id="4aa1a-120">É onde a configuração define as propriedades para os recursos que estão sendo configurados.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-120">This is where the configuration sets the properties for the resources that it is configuring.</span></span> <span data-ttu-id="4aa1a-121">Nesse caso, há dois blocos de recurso; cada um deles chama o recurso "WindowsFeature".</span><span class="sxs-lookup"><span data-stu-id="4aa1a-121">In this case, there are two resource blocks, each of which call the "WindowsFeature" resource.</span></span>

<span data-ttu-id="4aa1a-122">Dentro de um bloco de **configuração** , é possível fazer qualquer coisa que normalmente poderia ser feita em uma função do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-122">Within a **Configuration** block, you can do anything that you normally could in a PowerShell function.</span></span> <span data-ttu-id="4aa1a-123">No exemplo anterior, se você não quisesse embutir em código o nome do computador de destino na configuração, poderia adicionar um parâmetro para o nome do nó:</span><span class="sxs-lookup"><span data-stu-id="4aa1a-123">For example, in the previous example, if you didn't want to hard code the name of the target computer in the configuration, you could add a parameter for the node name:</span></span>

<span data-ttu-id="4aa1a-124">Neste exemplo, você especifica o nome do nó passando-o como o parâmetro **ComputerName** quando compila a configuração.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-124">In this example, you specify the name of the node by passing it as the **ComputerName** parameter when you compile the configuration.</span></span> <span data-ttu-id="4aa1a-125">O nome padrão é "localhost".</span><span class="sxs-lookup"><span data-stu-id="4aa1a-125">The name defaults to "localhost".</span></span>

```powershell
Configuration MyDscConfiguration
{
    param
    (
        [string[]]$ComputerName='localhost'
    )

    Node $ComputerName
    {
        WindowsFeature MyFeatureInstance
        {
            Ensure = 'Present'
            Name = 'RSAT'
        }

        WindowsFeature My2ndFeatureInstance
        {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}

MyDscConfiguration
```

<span data-ttu-id="4aa1a-126">O bloco **Nó** também pode aceitar vários nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-126">The **Node** block can also accept multiple computer names.</span></span> <span data-ttu-id="4aa1a-127">No exemplo acima, você pode usar o parâmetro `-ComputerName` ou passar uma lista de computadores separados por vírgula diretamente ao bloco **Nó** .</span><span class="sxs-lookup"><span data-stu-id="4aa1a-127">In the above example, you can either use the `-ComputerName` parameter, or pass a comma-separated list of computers directly to the **Node** block.</span></span>

```powershell
MyDscConfiguration -ComputerName "localhost", "Server01"
```

<span data-ttu-id="4aa1a-128">Ao especificar uma lista de computadores para o bloco **Nó** , dentro de uma configuração, você precisa usar a notação de matriz.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-128">When specifying a list of computers to the **Node** block, from within a Configuration, you need to use array-notation.</span></span>

```powershell
Configuration MyDscConfiguration
{
    Node @('localhost', 'Server01')
    {
        WindowsFeature MyFeatureInstance
        {
            Ensure = 'Present'
            Name = 'RSAT'
        }

        WindowsFeature My2ndFeatureInstance
        {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}

MyDscConfiguration
```

## <a name="compiling-the-configuration"></a><span data-ttu-id="4aa1a-129">Compilando a configuração</span><span class="sxs-lookup"><span data-stu-id="4aa1a-129">Compiling the configuration</span></span>

<span data-ttu-id="4aa1a-130">Para poder aplicar uma configuração, você precisa compilá-la em um documento MOF.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-130">Before you can enact a configuration, you have to compile it into a MOF document.</span></span> <span data-ttu-id="4aa1a-131">Faça isso chamando a configuração como você chamaria uma função do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-131">You do this by calling the configuration like you would call a PowerShell function.</span></span> <span data-ttu-id="4aa1a-132">A última linha do exemplo contendo somente o nome da configuração, chama a configuração.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-132">The last line of the example containing only the name of the configuration, calls the configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="4aa1a-133">Para chamar uma configuração, a função precisa estar no escopo global (como acontece com qualquer outra função do PowerShell).</span><span class="sxs-lookup"><span data-stu-id="4aa1a-133">To call a configuration, the function must be in global scope (as with any other PowerShell function).</span></span> <span data-ttu-id="4aa1a-134">Isso pode ser feito por meio de "dot-sourcing" do script ou ao executar o script de configuração usando F5 ou clicando no botão **Executar Script** no ISE.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-134">You can make this happen either by "dot-sourcing" the script, or by running the configuration script by using F5 or clicking on the **Run Script** button in the ISE.</span></span> <span data-ttu-id="4aa1a-135">Para fazer o dot-source do script, execute o comando `. .\myConfig.ps1`, em que `myConfig.ps1` é o nome do arquivo de script que contém sua configuração.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-135">To dot-source the script, run the command `. .\myConfig.ps1` where `myConfig.ps1` is the name of the script file that contains your configuration.</span></span>

<span data-ttu-id="4aa1a-136">Quando você chama a configuração, ela:</span><span class="sxs-lookup"><span data-stu-id="4aa1a-136">When you call the configuration, it:</span></span>

- <span data-ttu-id="4aa1a-137">Resolve todas as variáveis</span><span class="sxs-lookup"><span data-stu-id="4aa1a-137">Resolves all variables</span></span>
- <span data-ttu-id="4aa1a-138">Uma pasta no diretório atual com o mesmo nome que a configuração.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-138">Creates a folder in the current directory with the same name as the configuration.</span></span>
- <span data-ttu-id="4aa1a-139">Um arquivo chamado _NodeName_ .mof no novo diretório, em que _NodeName_ é o nome do nó de destino da configuração.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-139">Creates a file named _NodeName_ .mof in the new directory, where _NodeName_ is the name of the target node of the configuration.</span></span> <span data-ttu-id="4aa1a-140">Se houver mais de um nó, será criado um arquivo MOF para cada nó.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-140">If there is more than one node, a MOF file will be created for each node.</span></span>

> [!NOTE]
> <span data-ttu-id="4aa1a-141">O arquivo MOF contém todas as informações de configuração para o nó de destino.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-141">The MOF file contains all of the configuration information for the target node.</span></span> <span data-ttu-id="4aa1a-142">Por isso, é importante mantê-lo seguro.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-142">Because of this, it's important to keep it secure.</span></span> <span data-ttu-id="4aa1a-143">Para obter mais informações, consulte [Protegendo o arquivo MOF](../pull-server/secureMOF.md).</span><span class="sxs-lookup"><span data-stu-id="4aa1a-143">For more information, see [Securing the MOF file](../pull-server/secureMOF.md).</span></span>

<span data-ttu-id="4aa1a-144">A compilação da primeira configuração acima resulta na seguinte estrutura de pastas:</span><span class="sxs-lookup"><span data-stu-id="4aa1a-144">Compiling the first configuration above results in the following folder structure:</span></span>

```powershell
. .\MyDscConfiguration.ps1
MyDscConfiguration
```

```
    Directory: C:\users\default\Documents\DSC Configurations\MyDscConfiguration
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       10/23/2015   4:32 PM           2842 localhost.mof
```

<span data-ttu-id="4aa1a-145">Se a configuração utilizar um parâmetro, como no segundo exemplo, ele precisará ser fornecido no tempo de compilação.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-145">If the configuration takes a parameter, as in the second example, that has to be provided at compile time.</span></span> <span data-ttu-id="4aa1a-146">A aparência deveria ser esta:</span><span class="sxs-lookup"><span data-stu-id="4aa1a-146">Here's how that would look:</span></span>

```powershell
. .\MyDscConfiguration.ps1
MyDscConfiguration -ComputerName 'MyTestNode'
```

```
    Directory: C:\users\default\Documents\DSC Configurations\MyDscConfiguration
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       10/23/2015   4:32 PM           2842 MyTestNode.mof
```

## <a name="using-new-resources-in-your-configuration"></a><span data-ttu-id="4aa1a-147">Uso de novos recursos na sua configuração</span><span class="sxs-lookup"><span data-stu-id="4aa1a-147">Using new resources in Your configuration</span></span>

<span data-ttu-id="4aa1a-148">Se você executou os exemplos anteriores, talvez tenha notado que foi informado que estava usando um recurso sem importá-lo explicitamente.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-148">If you ran the previous examples, you might have noticed that you were warned that you were using a resource without explicitly importing it.</span></span> <span data-ttu-id="4aa1a-149">Atualmente, a DSC vem com 12 recursos como parte do módulo PSDesiredStateConfiguration.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-149">Today, DSC ships with 12 resources as part of the PSDesiredStateConfiguration module.</span></span>

<span data-ttu-id="4aa1a-150">O cmdlet [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) pode ser usado para determinar quais recursos estão instalados no sistema e disponíveis para uso pelo LCM.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-150">The cmdlet, [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), can be used to determine what resources are installed on the system and available for use by the LCM.</span></span>
<span data-ttu-id="4aa1a-151">Depois que esses módulos forem colocados em `$env:PSModulePath` e reconhecidos adequadamente pelo [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), ainda precisam ser carregados na sua configuração.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-151">Once these modules have been placed in `$env:PSModulePath` and are properly recognized by [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), they still need to be loaded within your configuration.</span></span>

<span data-ttu-id="4aa1a-152">**Import-DscResource** é uma palavra-chave dinâmica que pode ser reconhecida apenas dentro de um bloco **Configuração** , não se trata de um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-152">**Import-DscResource** is a dynamic keyword that can only be recognized within a **Configuration** block, it is not a cmdlet.</span></span> <span data-ttu-id="4aa1a-153">O **Import-DscResource** dá suporte a dois parâmetros:</span><span class="sxs-lookup"><span data-stu-id="4aa1a-153">**Import-DscResource** supports two parameters:</span></span>

- <span data-ttu-id="4aa1a-154">**ModuleName** é a forma recomendada de usar o **Import-DscResource** .</span><span class="sxs-lookup"><span data-stu-id="4aa1a-154">**ModuleName** is the recommended way of using **Import-DscResource** .</span></span> <span data-ttu-id="4aa1a-155">Aceita o nome do módulo que contém os recursos que serão importados (assim como uma matriz de cadeia de caracteres de nomes de módulos).</span><span class="sxs-lookup"><span data-stu-id="4aa1a-155">It accepts the name of the module that contains the resources to be imported (as well as a string array of module names).</span></span>
- <span data-ttu-id="4aa1a-156">**Name** é o nome do recurso que será importado.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-156">**Name** is the name of the resource to import.</span></span> <span data-ttu-id="4aa1a-157">Não é o nome amigável gerado como "Name" pelo [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), mas o nome de classe usado na hora de definir o esquema de recurso (gerado como **ResourceType** pelo [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)).</span><span class="sxs-lookup"><span data-stu-id="4aa1a-157">This is not the friendly name returned as "Name" by [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), but the class name used when defining the resource schema (returned as **ResourceType** by [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)).</span></span>

<span data-ttu-id="4aa1a-158">Para saber mais sobre como usar `Import-DSCResource`, confira [Usando Import-DSCResource](import-dscresource.md)</span><span class="sxs-lookup"><span data-stu-id="4aa1a-158">For more information on using `Import-DSCResource`, see [Using Import-DSCResource](import-dscresource.md)</span></span>

## <a name="powershell-v4-and-v5-differences"></a><span data-ttu-id="4aa1a-159">Diferenças entre o PowerShell v4 e v5</span><span class="sxs-lookup"><span data-stu-id="4aa1a-159">PowerShell v4 and v5 differences</span></span>

<span data-ttu-id="4aa1a-160">Há diferenças quanto ao local em que os recursos DSC precisam ser armazenados no PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-160">There are differences in where DSC resources need to be stored in PowerShell 4.0.</span></span> <span data-ttu-id="4aa1a-161">Para saber mais, confira [Local do recurso](import-dscresource.md#resource-location).</span><span class="sxs-lookup"><span data-stu-id="4aa1a-161">For more information, see [Resource location](import-dscresource.md#resource-location).</span></span>

## <a name="see-also"></a><span data-ttu-id="4aa1a-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4aa1a-162">See Also</span></span>

- [<span data-ttu-id="4aa1a-163">Visão geral da Desired State Configuration do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4aa1a-163">Windows PowerShell Desired State Configuration Overview</span></span>](../overview/overview.md)
- [<span data-ttu-id="4aa1a-164">Recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="4aa1a-164">DSC Resources</span></span>](../resources/resources.md)
- [<span data-ttu-id="4aa1a-165">Configurando o Gerenciador de Configurações Local</span><span class="sxs-lookup"><span data-stu-id="4aa1a-165">Configuring The Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)
