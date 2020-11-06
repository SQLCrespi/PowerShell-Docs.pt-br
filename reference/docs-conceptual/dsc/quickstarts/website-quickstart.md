---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: 'Início Rápido: Criar um site com o DSC'
description: Este Início Rápido mostra como criar um site usando uma configuração DSC.
ms.openlocfilehash: ece1ae964bce00a4102de4b13d99d6ee1259117a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650901"
---
# <a name="quickstart---create-a-website-with-desired-state-configuration-dsc"></a><span data-ttu-id="45ec6-104">Início Rápido: Criar um site com DSC (Desired State Configuration)</span><span class="sxs-lookup"><span data-stu-id="45ec6-104">Quickstart - Create a website with Desired State Configuration (DSC)</span></span>

> <span data-ttu-id="45ec6-105">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="45ec6-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="45ec6-106">Este exercício oferece instruções de como criar e aplicar uma configuração para a Configuração Estado Desejado (DSC) do início ao fim.</span><span class="sxs-lookup"><span data-stu-id="45ec6-106">This exercise walks through creating and applying a Desired State Configuration (DSC) configuration from start to finish.</span></span> <span data-ttu-id="45ec6-107">O exemplo que usaremos garante que o recurso `Web-Server` (IIS) do servidor esteja habilitado e que o conteúdo para um site "Hello World" simples esteja presente no diretório do `inetpub\wwwroot` desse servidor.</span><span class="sxs-lookup"><span data-stu-id="45ec6-107">The example we'll use ensures that a server has the `Web-Server` (IIS) feature enabled, and that the content for a simple "Hello World" website is present in the `inetpub\wwwroot` directory of that server.</span></span>

<span data-ttu-id="45ec6-108">Para obter uma visão geral sobre o que é a DSC e como ela funciona, confira [Visão Geral da Configuração do Estado Desejado para Tomadores de Decisão](../overview/decisionMaker.md).</span><span class="sxs-lookup"><span data-stu-id="45ec6-108">For an overview of what DSC is and how it works, see [Desired State Configuration Overview for Decision Makers](../overview/decisionMaker.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="45ec6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45ec6-109">Requirements</span></span>

<span data-ttu-id="45ec6-110">Para executar este exemplo, você precisará de um computador com o Windows Server 2012 ou posterior e o PowerShell 4.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="45ec6-110">To run this example, you will need a computer running Windows Server 2012 or later and PowerShell 4.0 or later.</span></span>

## <a name="write-and-place-the-indexhtm-file"></a><span data-ttu-id="45ec6-111">Gravar e posicionar o arquivo index.htm</span><span class="sxs-lookup"><span data-stu-id="45ec6-111">Write and place the index.htm file</span></span>

<span data-ttu-id="45ec6-112">Primeiro, vamos criar o arquivo HTML que usaremos como o conteúdo do site.</span><span class="sxs-lookup"><span data-stu-id="45ec6-112">First, we'll create the HTML file that we will use as the website content.</span></span>

<span data-ttu-id="45ec6-113">Na pasta-raiz, crie uma pasta chamada `test`.</span><span class="sxs-lookup"><span data-stu-id="45ec6-113">In your root folder, create a folder named `test`.</span></span>

<span data-ttu-id="45ec6-114">Em um editor de texto, digite o texto a seguir:</span><span class="sxs-lookup"><span data-stu-id="45ec6-114">In a text editor, type the following text:</span></span>

```html
<head></head>
<body>
<p>Hello World!</p>
</body>
```

<span data-ttu-id="45ec6-115">Salve-o como `index.htm` na pasta `test` que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="45ec6-115">Save this as `index.htm` in the `test` folder you created earlier.</span></span>

## <a name="write-the-configuration"></a><span data-ttu-id="45ec6-116">Gravar a configuração</span><span class="sxs-lookup"><span data-stu-id="45ec6-116">Write the configuration</span></span>

<span data-ttu-id="45ec6-117">Uma [Configuração DSC](../configurations/configurations.md) é uma função especial do PowerShell que define como você deseja configurar um ou mais computadores de destino (nós).</span><span class="sxs-lookup"><span data-stu-id="45ec6-117">A [DSC configuration](../configurations/configurations.md) is a special PowerShell function that defines how you want to configure one or more target computers (nodes).</span></span>

<span data-ttu-id="45ec6-118">No ISE do PowerShell, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="45ec6-118">In the PowerShell ISE, type the following:</span></span>

```powershell
Configuration WebsiteTest {

    # Import the module that contains the resources we're using.
    Import-DscResource -ModuleName PsDesiredStateConfiguration

    # The Node statement specifies which targets this configuration will be applied to.
    Node 'localhost' {

        # The first resource block ensures that the Web-Server (IIS) feature is enabled.
        WindowsFeature WebServer {
            Ensure = "Present"
            Name   = "Web-Server"
        }

        # The second resource block ensures that the website content copied to the website root folder.
        File WebsiteContent {
            Ensure = 'Present'
            SourcePath = 'c:\test\index.htm'
            DestinationPath = 'c:\inetpub\wwwroot'
        }
    }
}
```

<span data-ttu-id="45ec6-119">Salve o arquivo como `WebsiteTest.ps1`.</span><span class="sxs-lookup"><span data-stu-id="45ec6-119">Save the file as `WebsiteTest.ps1`.</span></span>

<span data-ttu-id="45ec6-120">Você pode ver que ele parece uma função do PowerShell, com a adição da palavra-chave **Configuração** usada antes do nome da função.</span><span class="sxs-lookup"><span data-stu-id="45ec6-120">You can see that it looks like a PowerShell function, with the addition of the keyword **Configuration** used before the name of the function.</span></span>

<span data-ttu-id="45ec6-121">O bloco **Nó** especifica o nó de destino a ser configurado.</span><span class="sxs-lookup"><span data-stu-id="45ec6-121">The **Node** block specifies the target node to be configured.</span></span> <span data-ttu-id="45ec6-122">Nesse caso, `localhost`.</span><span class="sxs-lookup"><span data-stu-id="45ec6-122">In this case, `localhost`.</span></span>

<span data-ttu-id="45ec6-123">A configuração chama dois [recursos](../resources/resources.md), **WindowsFeature** e **Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="45ec6-123">The configuration calls two [resources](../resources/resources.md), **WindowsFeature** and **File**.</span></span>
<span data-ttu-id="45ec6-124">Os recursos fazem o trabalho de garantir que o nó de destino está no estado definido pela configuração.</span><span class="sxs-lookup"><span data-stu-id="45ec6-124">Resources do the work of ensuring that the target node is in the state defined by the configuration.</span></span>

## <a name="compile-the-configuration"></a><span data-ttu-id="45ec6-125">Compilar a configuração</span><span class="sxs-lookup"><span data-stu-id="45ec6-125">Compile the configuration</span></span>

<span data-ttu-id="45ec6-126">Para que uma configuração DSC seja aplicada a um nó, ela deve primeiro ser compilada em um arquivo MOF.</span><span class="sxs-lookup"><span data-stu-id="45ec6-126">For a DSC configuration to be applied to a node, it must first be compiled into a MOF file.</span></span> <span data-ttu-id="45ec6-127">Para fazer isso, você deve executar a configuração como uma função.</span><span class="sxs-lookup"><span data-stu-id="45ec6-127">To do this, you run the configuration like a function.</span></span> <span data-ttu-id="45ec6-128">Em um console do PowerShell, navegue até a mesma pasta em que você salvou sua configuração e execute os seguintes comandos para compilar a configuração em um arquivo MOF:</span><span class="sxs-lookup"><span data-stu-id="45ec6-128">In a PowerShell console, navigate to the same folder where you saved your configuration and run the following commands to compile the configuration into a MOF file:</span></span>

```powershell
. .\WebsiteTest.ps1
WebsiteTest
```

<span data-ttu-id="45ec6-129">Isso gerará os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="45ec6-129">This generates the following output:</span></span>

```
Directory: C:\ConfigurationTest\WebsiteTest


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

<span data-ttu-id="45ec6-130">A primeira linha torna a função de configuração disponível no console.</span><span class="sxs-lookup"><span data-stu-id="45ec6-130">The first line makes the configuration function available in the console.</span></span> <span data-ttu-id="45ec6-131">A segunda linha executa a configuração.</span><span class="sxs-lookup"><span data-stu-id="45ec6-131">The second line runs the configuration.</span></span> <span data-ttu-id="45ec6-132">O resultado é que uma nova pasta, chamada `WebsiteTest`, é criada como uma subpasta da pasta atual.</span><span class="sxs-lookup"><span data-stu-id="45ec6-132">The result is that a new folder, named `WebsiteTest` is created as a subfolder of the current folder.</span></span> <span data-ttu-id="45ec6-133">A pasta `WebsiteTest` contém um arquivo chamado `localhost.mof`.</span><span class="sxs-lookup"><span data-stu-id="45ec6-133">The `WebsiteTest` folder contains a file named `localhost.mof`.</span></span> <span data-ttu-id="45ec6-134">É o arquivo que pode ser aplicado ao nó de destino.</span><span class="sxs-lookup"><span data-stu-id="45ec6-134">This is the file that can then be applied to the target node.</span></span>

## <a name="apply-the-configuration"></a><span data-ttu-id="45ec6-135">Aplicar a configuração</span><span class="sxs-lookup"><span data-stu-id="45ec6-135">Apply the configuration</span></span>

<span data-ttu-id="45ec6-136">Agora que você tem o MOF compilado, é possível aplicar a configuração ao nó de destino (neste caso, o computador local) chamando o cmdlet [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="45ec6-136">Now that you have the compiled MOF, you can apply the configuration to the target node (in this case, the local computer) by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

<span data-ttu-id="45ec6-137">O cmdlet `Start-DscConfiguration` indica ao [Gerenciador de Configurações Local (LCM)](../managing-nodes/metaConfig.md), qual é o mecanismo de DSC a aplicar à configuração.</span><span class="sxs-lookup"><span data-stu-id="45ec6-137">The `Start-DscConfiguration` cmdlet tells the [Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md), which is the engine of DSC, to apply the configuration.</span></span> <span data-ttu-id="45ec6-138">O LCM realiza o trabalho de chamar os recursos de DSC para aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="45ec6-138">The LCM does the work of calling the DSC resources to apply the configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="45ec6-139">Para permitir que a DSC seja executada, o Windows precisa ser configurado para receber comandos remotos do PowerShell, mesmo quando você estiver executando uma configuração de `localhost`.</span><span class="sxs-lookup"><span data-stu-id="45ec6-139">To allow DSC to run, Windows needs to be configured to receive PowerShell remote commands, even when you're running a `localhost` configuration.</span></span> <span data-ttu-id="45ec6-140">Para configurar seu ambiente corretamente de forma simples, basta executar `Set-WsManQuickConfig -Force` em um Terminal do PowerShell elevado.</span><span class="sxs-lookup"><span data-stu-id="45ec6-140">To easily configure your environment correctly, just run `Set-WsManQuickConfig -Force` in an elevated PowerShell Terminal.</span></span>

<span data-ttu-id="45ec6-141">Em um console do PowerShell, navegue até a mesma pasta em que você salvou sua configuração e execute o mesmo comando:</span><span class="sxs-lookup"><span data-stu-id="45ec6-141">In a PowerShell console, navigate to the same folder where you saved your configuration and run the following command:</span></span>

```powershell
Start-DscConfiguration .\WebsiteTest
```

## <a name="test-the-configuration"></a><span data-ttu-id="45ec6-142">Testar a configuração</span><span class="sxs-lookup"><span data-stu-id="45ec6-142">Test the configuration</span></span>

<span data-ttu-id="45ec6-143">Você pode chamar o cmdlet [Get-DscConfigurationStatus](/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus) para ver se a configuração foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="45ec6-143">You can call the [Get-DscConfigurationStatus](/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus) cmdlet to see whether the configuration succeeded.</span></span>

<span data-ttu-id="45ec6-144">Você também pode testar os resultados diretamente, neste caso, pesquisando o `http://localhost/` em um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="45ec6-144">You can also test the results directly, in this case by browsing to `http://localhost/` in a web browser.</span></span> <span data-ttu-id="45ec6-145">Você deve ver a página de HTML "Hello World" que criou como a primeira etapa deste exemplo.</span><span class="sxs-lookup"><span data-stu-id="45ec6-145">You should see the "Hello World" HTML page you created as the first step in this example.</span></span>

## <a name="next-steps"></a><span data-ttu-id="45ec6-146">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="45ec6-146">Next steps</span></span>

- <span data-ttu-id="45ec6-147">Saiba mais sobre configurações de DSC em [Configurações de DSC](../configurations/configurations.md).</span><span class="sxs-lookup"><span data-stu-id="45ec6-147">Find out more about DSC configurations at [DSC configurations](../configurations/configurations.md).</span></span>
- <span data-ttu-id="45ec6-148">Veja quais recursos de DSC estão disponíveis e como criar recursos personalizados de DSC em [Recursos de DSC](../resources/resources.md).</span><span class="sxs-lookup"><span data-stu-id="45ec6-148">See what DSC resources are available, and how to create custom DSC resources at [DSC resources](../resources/resources.md).</span></span>
- <span data-ttu-id="45ec6-149">Localize as configurações e recursos de DSC na [Galeria do PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="45ec6-149">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
