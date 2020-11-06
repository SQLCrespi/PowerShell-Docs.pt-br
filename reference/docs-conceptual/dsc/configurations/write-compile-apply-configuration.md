---
ms.date: 06/22/2020
keywords: DSC,powershell,configuração,serviço,instalação
title: Escrever, compilar e aplicar uma configuração
description: Este exercício oferece instruções de como criar e aplicar uma configuração DSC do início ao fim. No exemplo a seguir, você aprenderá como escrever e aplicar uma Configuração muito simples
ms.openlocfilehash: f173fe0dc6cd73e2b49bb8c44a9ee1a53eab475f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645023"
---
# <a name="write-compile-and-apply-a-configuration"></a><span data-ttu-id="fa319-105">Escrever, compilar e aplicar uma configuração</span><span class="sxs-lookup"><span data-stu-id="fa319-105">Write, Compile, and Apply a Configuration</span></span>

> <span data-ttu-id="fa319-106">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="fa319-106">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="fa319-107">Este exercício oferece instruções de como criar e aplicar uma configuração para a Configuração Estado Desejado (DSC) do início ao fim.</span><span class="sxs-lookup"><span data-stu-id="fa319-107">This exercise walks through creating and applying a Desired State Configuration (DSC) configuration from start to finish.</span></span> <span data-ttu-id="fa319-108">No exemplo a seguir, você aprenderá como escrever e aplicar uma configuração muito simples.</span><span class="sxs-lookup"><span data-stu-id="fa319-108">In the following example, you will learn how to write and apply a very simple Configuration.</span></span> <span data-ttu-id="fa319-109">A configuração garantirá que um arquivo "HelloWorld.txt" existe em seu computador local.</span><span class="sxs-lookup"><span data-stu-id="fa319-109">The Configuration will ensure a "HelloWorld.txt" file exists on your local machine.</span></span>
<span data-ttu-id="fa319-110">Se você excluir o arquivo, a DSC o criará novamente em sua próxima atualização.</span><span class="sxs-lookup"><span data-stu-id="fa319-110">If you delete the file, DSC will recreate it the next time it updates.</span></span>

<span data-ttu-id="fa319-111">Para ter uma visão geral sobre o que é a DSC e como ela funciona, confira [Visão geral da Desired State Configuration para desenvolvedores](../overview/overview.md).</span><span class="sxs-lookup"><span data-stu-id="fa319-111">For an overview of what DSC is and how it works, see [Desired State Configuration Overview for Developers](../overview/overview.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="fa319-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa319-112">Requirements</span></span>

<span data-ttu-id="fa319-113">Para executar este exemplo, você precisará de um computador com o PowerShell 4.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="fa319-113">To run this example, you will need a computer running PowerShell 4.0 or later.</span></span>

## <a name="write-the-configuration"></a><span data-ttu-id="fa319-114">Gravar a configuração</span><span class="sxs-lookup"><span data-stu-id="fa319-114">Write the configuration</span></span>

<span data-ttu-id="fa319-115">Uma [Configuração](configurations.md) DSC é uma função especial do PowerShell que define como você deseja configurar um ou mais computadores de destino (nós).</span><span class="sxs-lookup"><span data-stu-id="fa319-115">A DSC [Configuration](configurations.md) is a special PowerShell function that defines how you want to configure one or more target computers (Nodes).</span></span>

<span data-ttu-id="fa319-116">No ISE do PowerShell ou em outro editor do PowerShell, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fa319-116">In the PowerShell ISE, or other PowerShell editor, type the following:</span></span>

```powershell
Configuration HelloWorld {

    # Import the module that contains the File resource.
    Import-DscResource -ModuleName PsDesiredStateConfiguration

    # The Node statement specifies which targets to compile MOF files for, when
    # this configuration is executed.
    Node 'localhost' {

        # The File resource can ensure the state of files, or copy them from a
        # source to a destination with persistent updates.
        File HelloWorld {
            DestinationPath = "C:\Temp\HelloWorld.txt"
            Ensure = "Present"
            Contents   = "Hello World from DSC!"
        }
    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="fa319-117">Em cenários mais avançados, nos quais vários módulos precisam ser importados, para que você possa trabalhar com muitos Recursos de DSC na mesma configuração, coloque cada módulo em uma linha separada usando `Import-DscResource`.</span><span class="sxs-lookup"><span data-stu-id="fa319-117">In more advanced scenarios where multiple modules need to be imported so you can work with many DSC Resources in the same configuration, make sure to put each module in a separate line using `Import-DscResource`.</span></span> <span data-ttu-id="fa319-118">Assim é mais fácil manter no controle do código-fonte e é necessário ao trabalhar com a DSC na Configuração de Estado do Azure.</span><span class="sxs-lookup"><span data-stu-id="fa319-118">This is easier to maintain in source control and required when working with DSC in Azure State Configuration.</span></span>
>
> ```powershell
>  Configuration HelloWorld {
>
>   # Import the module that contains the File resource.
>   Import-DscResource -ModuleName PsDesiredStateConfiguration
>   Import-DscResource -ModuleName xWebAdministration
>
> ```

<span data-ttu-id="fa319-119">Salve o arquivo como "HelloWorld.ps1".</span><span class="sxs-lookup"><span data-stu-id="fa319-119">Save the file as "HelloWorld.ps1".</span></span>

<span data-ttu-id="fa319-120">Definir uma configuração é semelhante a definir uma função.</span><span class="sxs-lookup"><span data-stu-id="fa319-120">Defining a Configuration is like defining a Function.</span></span> <span data-ttu-id="fa319-121">O bloco **Nó** especifica o nó de destino a ser configurado, neste caso `localhost`.</span><span class="sxs-lookup"><span data-stu-id="fa319-121">The **Node** block specifies the target node to be configured, in this case `localhost`.</span></span>

<span data-ttu-id="fa319-122">A configuração chama um [recurso](../resources/resources.md), o recurso `File`.</span><span class="sxs-lookup"><span data-stu-id="fa319-122">The configuration calls one [resources](../resources/resources.md), the `File` resource.</span></span> <span data-ttu-id="fa319-123">Os recursos fazem o trabalho de garantir que o nó de destino está no estado definido pela configuração.</span><span class="sxs-lookup"><span data-stu-id="fa319-123">Resources do the work of ensuring that the target node is in the state defined by the configuration.</span></span>

## <a name="compile-the-configuration"></a><span data-ttu-id="fa319-124">Compilar a configuração</span><span class="sxs-lookup"><span data-stu-id="fa319-124">Compile the configuration</span></span>

<span data-ttu-id="fa319-125">Para que uma configuração DSC seja aplicada a um nó, ela deve primeiro ser compilada em um arquivo MOF.</span><span class="sxs-lookup"><span data-stu-id="fa319-125">For a DSC configuration to be applied to a node, it must first be compiled into a MOF file.</span></span> <span data-ttu-id="fa319-126">A execução da configuração, como no caso de uma função, compilará um arquivo `.mof` para cada Nó definido pelo bloco `Node`.</span><span class="sxs-lookup"><span data-stu-id="fa319-126">Running the configuration, like a function, will compile one `.mof` file for every Node defined by the `Node` block.</span></span> <span data-ttu-id="fa319-127">Para executar a configuração, você precisa executar _dot source_ no script `HelloWorld.ps1` para o escopo atual.</span><span class="sxs-lookup"><span data-stu-id="fa319-127">In order to run the configuration, you need to _dot source_ your `HelloWorld.ps1` script into the current scope.</span></span> <span data-ttu-id="fa319-128">Para obter mais informações, confira [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts#script-scope-and-dot-sourcing).</span><span class="sxs-lookup"><span data-stu-id="fa319-128">For more information, see [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts#script-scope-and-dot-sourcing).</span></span>

<!-- markdownlint-disable MD038 -->
<span data-ttu-id="fa319-129">Execute _dot source_ no script `HelloWorld.ps1` digitando o caminho em que você o armazenou, após o `. ` (ponto, espaço).</span><span class="sxs-lookup"><span data-stu-id="fa319-129">_Dot source_ your `HelloWorld.ps1` script by typing in the path where you stored it, after the `. ` (dot, space).</span></span> <span data-ttu-id="fa319-130">Em seguida, você poderá executar a configuração chamando-a como uma função.</span><span class="sxs-lookup"><span data-stu-id="fa319-130">You may then, run your configuration by calling it like a function.</span></span> <span data-ttu-id="fa319-131">Você também pode invocar a função de configuração na parte inferior do script para que não seja necessário executar dot source.</span><span class="sxs-lookup"><span data-stu-id="fa319-131">You could also invoke the configuration function at the bottom of the script so that you don't need to dot-source.</span></span>
<!-- markdownlint-enable MD038 -->

```powershell
. C:\Scripts\HelloWorld.ps1
HelloWorld
```

<span data-ttu-id="fa319-132">Isso gerará os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="fa319-132">This generates the following output:</span></span>

```Output
Directory: C:\Scripts\HelloWorld


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

## <a name="apply-the-configuration"></a><span data-ttu-id="fa319-133">Aplicar a configuração</span><span class="sxs-lookup"><span data-stu-id="fa319-133">Apply the configuration</span></span>

<span data-ttu-id="fa319-134">Agora que você tem o MOF compilado, é possível aplicar a configuração ao nó de destino (neste caso, o computador local) chamando o cmdlet [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="fa319-134">Now that you have the compiled MOF, you can apply the configuration to the target node (in this case, the local computer) by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

<span data-ttu-id="fa319-135">O cmdlet `Start-DscConfiguration` instrui o [LCM (Gerenciador de Configurações Local)](../managing-nodes/metaConfig.md), que é o mecanismo da DSC, a aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="fa319-135">The `Start-DscConfiguration` cmdlet tells the [Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md), the engine of DSC, to apply the configuration.</span></span> <span data-ttu-id="fa319-136">O LCM realiza o trabalho de chamar os recursos de DSC para aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="fa319-136">The LCM does the work of calling the DSC resources to apply the configuration.</span></span>

<span data-ttu-id="fa319-137">Use o código a seguir para executar o cmdlet `Start-DSCConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="fa319-137">Use the code below to execute the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="fa319-138">Especifique o caminho do diretório no qual o `localhost.mof` está armazenado para o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="fa319-138">Specify the directory path where your `localhost.mof` is stored to the **Path** parameter.</span></span> <span data-ttu-id="fa319-139">O cmdlet `Start-DSCConfiguration` examina o diretório especificado para qualquer arquivo `<computername>.mof`.</span><span class="sxs-lookup"><span data-stu-id="fa319-139">The `Start-DSCConfiguration` cmdlet looks through the directory specified for any `<computername>.mof` files.</span></span> <span data-ttu-id="fa319-140">O cmdlet `Start-DSCConfiguration` tenta aplicar cada arquivo `.mof` encontrado ao `computername` especificado pelo nome do ("localhost", "server01", "dc-02" etc.).</span><span class="sxs-lookup"><span data-stu-id="fa319-140">The `Start-DSCConfiguration` cmdlet attempts to apply each `.mof` file it finds to the `computername` specified by the filename ("localhost", "server01", "dc-02", etc.).</span></span>

> [!NOTE]
> <span data-ttu-id="fa319-141">Se o parâmetro `-Wait` não for especificado, `Start-DSCConfiguration` criará um trabalho em segundo plano para executar a operação.</span><span class="sxs-lookup"><span data-stu-id="fa319-141">If the `-Wait` parameter is not specified, `Start-DSCConfiguration` creates a background job to perform the operation.</span></span> <span data-ttu-id="fa319-142">Especificar o parâmetro `-Verbose` permite que você inspecione a saída **Detalhada** da operação.</span><span class="sxs-lookup"><span data-stu-id="fa319-142">Specifying the `-Verbose` parameter allows you to watch the **Verbose** output of the operation.</span></span> <span data-ttu-id="fa319-143">`-Wait` e `-Verbose` são parâmetros opcionais.</span><span class="sxs-lookup"><span data-stu-id="fa319-143">`-Wait`, and `-Verbose` are both optional parameters.</span></span>

```powershell
Start-DscConfiguration -Path C:\Scripts\HelloWorld -Verbose -Wait
```

## <a name="test-the-configuration"></a><span data-ttu-id="fa319-144">Testar a configuração</span><span class="sxs-lookup"><span data-stu-id="fa319-144">Test the configuration</span></span>

<span data-ttu-id="fa319-145">Quando o cmdlet `Start-DSCConfiguration` for concluído, o arquivo `HelloWorld.txt` deverá estar no local especificado.</span><span class="sxs-lookup"><span data-stu-id="fa319-145">Once the `Start-DSCConfiguration` cmdlet is complete, you should see a `HelloWorld.txt` file in the location you specified.</span></span> <span data-ttu-id="fa319-146">Você pode verificar o conteúdo com o cmdlet [Get-Content](/powershell/module/microsoft.powershell.management/get-content).</span><span class="sxs-lookup"><span data-stu-id="fa319-146">You can verify the contents with the [Get-Content](/powershell/module/microsoft.powershell.management/get-content) cmdlet.</span></span>

<span data-ttu-id="fa319-147">Você também pode _testar_ o status atual usando [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span><span class="sxs-lookup"><span data-stu-id="fa319-147">You can also _test_ the current status using [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span></span>

<span data-ttu-id="fa319-148">A saída deverá ser `True` se o Nó estiver em conformidade no momento com a configuração aplicada.</span><span class="sxs-lookup"><span data-stu-id="fa319-148">The output should be `True` if the Node is currently compliant with the applied Configuration.</span></span>

```powershell
Test-DSCConfiguration
```

```Output
True
```

```powershell
Get-Content -Path C:\Temp\HelloWorld.txt
```

```Output
Hello World from DSC!
```

## <a name="re-applying-the-configuration"></a><span data-ttu-id="fa319-149">Reaplicando a configuração</span><span class="sxs-lookup"><span data-stu-id="fa319-149">Re-applying the configuration</span></span>

<span data-ttu-id="fa319-150">Para ver sua configuração ser aplicada novamente, você pode remover o arquivo de texto criado por ela.</span><span class="sxs-lookup"><span data-stu-id="fa319-150">To see your configuration get applied again, you can remove the text file created by your Configuration.</span></span> <span data-ttu-id="fa319-151">Em seguida, use o cmdlet `Start-DSCConfiguration` com o parâmetro `-UseExisting`.</span><span class="sxs-lookup"><span data-stu-id="fa319-151">The use the `Start-DSCConfiguration` cmdlet with the `-UseExisting` parameter.</span></span> <span data-ttu-id="fa319-152">O parâmetro `-UseExisting` instrui `Start-DSCConfiguration` a reaplicar o arquivo "current.mof", que representa a configuração aplicada com sucesso mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="fa319-152">The `-UseExisting` parameter instructs `Start-DSCConfiguration` to re-apply the "current.mof" file, which represents the most recently successfully applied configuration.</span></span>

```powershell
Remove-Item -Path C:\Temp\HelloWorld.txt
```

## <a name="next-steps"></a><span data-ttu-id="fa319-153">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="fa319-153">Next steps</span></span>

- <span data-ttu-id="fa319-154">Saiba mais sobre configurações de DSC em [Configurações de DSC](configurations.md).</span><span class="sxs-lookup"><span data-stu-id="fa319-154">Find out more about DSC configurations at [DSC configurations](configurations.md).</span></span>
- <span data-ttu-id="fa319-155">Veja quais recursos de DSC estão disponíveis e como criar recursos personalizados de DSC em [Recursos de DSC](../resources/resources.md).</span><span class="sxs-lookup"><span data-stu-id="fa319-155">See what DSC resources are available, and how to create custom DSC resources at [DSC resources](../resources/resources.md).</span></span>
- <span data-ttu-id="fa319-156">Localize as configurações e recursos de DSC na [Galeria do PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="fa319-156">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
