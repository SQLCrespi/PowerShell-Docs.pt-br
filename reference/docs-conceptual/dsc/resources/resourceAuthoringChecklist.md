---
ms.date: 07/08/2020
keywords: DSC,powershell,configuração,instalação
title: Lista de verificação da criação de recursos
description: Este artigo contém uma lista de verificação com melhores práticas que devem ser usadas ao criar um recurso de DSC.
ms.openlocfilehash: 5b618511f730c80104620c84e693c13ae4f536ac
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656328"
---
# <a name="resource-authoring-checklist"></a><span data-ttu-id="40979-104">Lista de verificação da criação de recursos</span><span class="sxs-lookup"><span data-stu-id="40979-104">Resource authoring checklist</span></span>

<span data-ttu-id="40979-105">Esta lista de verificação é uma lista de melhores práticas ao criar um novo Recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="40979-105">This checklist is a list of best practices when authoring a new DSC Resource.</span></span>

## <a name="resource-module-contains-psd1-file-and-schemamof-for-every-resource"></a><span data-ttu-id="40979-106">O módulo de recurso contém os arquivos .psd1 e schema.mof de cada um dos recursos</span><span class="sxs-lookup"><span data-stu-id="40979-106">Resource module contains .psd1 file and schema.mof for every resource</span></span>

<span data-ttu-id="40979-107">Verifique se o recurso tem a estrutura correta e se ele contém todos os arquivos necessários.</span><span class="sxs-lookup"><span data-stu-id="40979-107">Check that your resource has correct structure and contains all required files.</span></span> <span data-ttu-id="40979-108">Cada módulo de recurso deve conter um arquivo .psd1 e cada recurso de não composição deve ter o arquivo schema.mof.</span><span class="sxs-lookup"><span data-stu-id="40979-108">Every resource module should contain a .psd1 file and every non-composite resource should have schema.mof file.</span></span>
<span data-ttu-id="40979-109">Os recursos que não contêm o esquema não serão listados por `Get-DscResource`, e os usuários não poderão usar o IntelliSense ao gravar código nesses módulos no ISE.</span><span class="sxs-lookup"><span data-stu-id="40979-109">Resources that do not contain schema will not be listed by `Get-DscResource` and users will not be able to use the IntelliSense when writing code against those modules in ISE.</span></span> <span data-ttu-id="40979-110">A estrutura de diretório para o recurso xRemoteFile, que faz parte do módulo de recurso [xPSDesiredStateConfiguration](https://github.com/PowerShell/xPSDesiredStateConfiguration), tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="40979-110">The directory structure for xRemoteFile resource, which is part of the [xPSDesiredStateConfiguration resource module](https://github.com/PowerShell/xPSDesiredStateConfiguration), looks as follows:</span></span>

```
xPSDesiredStateConfiguration
    DSCResources
        MSFT_xRemoteFile
            MSFT_xRemoteFile.psm1
            MSFT_xRemoteFile.schema.mof
    Examples
        xRemoteFile_DownloadFile.ps1
    ResourceDesignerScripts
        GenerateXRemoteFileSchema.ps1
    Tests
        ResourceDesignerTests.ps1
    xPSDesiredStateConfiguration.psd1
```

## <a name="resource-and-schema-are-correct"></a><span data-ttu-id="40979-111">Os recursos e esquema estão corretos</span><span class="sxs-lookup"><span data-stu-id="40979-111">Resource and schema are correct</span></span>

<span data-ttu-id="40979-112">Verifique o arquivo de esquema do recurso (`*.schema.mof`).</span><span class="sxs-lookup"><span data-stu-id="40979-112">Verify the resource schema (`*.schema.mof`) file.</span></span> <span data-ttu-id="40979-113">Você pode usar o [Designer de Recursos da DSC](https://www.powershellgallery.com/packages/xDSCResourceDesigner/1.12.0.0) para ajudar a desenvolver e testar seu esquema.</span><span class="sxs-lookup"><span data-stu-id="40979-113">You can use the [DSC Resource Designer](https://www.powershellgallery.com/packages/xDSCResourceDesigner/1.12.0.0) to help develop and test your schema.</span></span> <span data-ttu-id="40979-114">Certifique-se de que:</span><span class="sxs-lookup"><span data-stu-id="40979-114">Make sure that:</span></span>

- <span data-ttu-id="40979-115">Os tipos de propriedade estão corretos (por exemplo, não use Cadeia de caracteres para propriedades que aceitam valores numéricos; em vez disso, use UInt32 ou outros tipos numéricos)</span><span class="sxs-lookup"><span data-stu-id="40979-115">Property types are correct (e.g. don't use String for properties which accept numeric values, you should use UInt32 or other numeric types instead)</span></span>
- <span data-ttu-id="40979-116">Os atributos de propriedade foram especificados corretamente como: ([key], [required], [write] e [read])</span><span class="sxs-lookup"><span data-stu-id="40979-116">Property attributes are specified correctly as: ([key], [required], [write], [read])</span></span>
- <span data-ttu-id="40979-117">Pelo menos, um parâmetro no esquema deve estar marcado como [key]</span><span class="sxs-lookup"><span data-stu-id="40979-117">At least one parameter in the schema has to be marked as [key]</span></span>
- <span data-ttu-id="40979-118">A propriedade [read] não coexiste com nenhuma dessas: [required], [key] e [write]</span><span class="sxs-lookup"><span data-stu-id="40979-118">[read] property does not coexist together with any of: [required], [key], [write]</span></span>
- <span data-ttu-id="40979-119">Se forem especificados vários qualificadores, exceto [read], [key] terá precedência</span><span class="sxs-lookup"><span data-stu-id="40979-119">If multiple qualifiers are specified except [read], then [key] takes precedence</span></span>
- <span data-ttu-id="40979-120">Se [write] e [required] forem especificados, [required] terá precedência</span><span class="sxs-lookup"><span data-stu-id="40979-120">If [write] and [required] are specified, then [required] takes precedence</span></span>
- <span data-ttu-id="40979-121">O ValueMap é especificado quando apropriado. Exemplo:</span><span class="sxs-lookup"><span data-stu-id="40979-121">ValueMap is specified where appropriate Example:</span></span>

  ```
  [Read, ValueMap{"Present", "Absent"}, Values{"Present", "Absent"}, Description("Says whether DestinationPath exists on the machine")] String Ensure;
  ```

- <span data-ttu-id="40979-122">O nome amigável é especificado e está em conformidade com as convenções de nomenclatura do DSC</span><span class="sxs-lookup"><span data-stu-id="40979-122">Friendly name is specified and confirms to DSC naming conventions</span></span>

  <span data-ttu-id="40979-123">Exemplo: `[ClassVersion("1.0.0.0"), FriendlyName("xRemoteFile")]`</span><span class="sxs-lookup"><span data-stu-id="40979-123">Example: `[ClassVersion("1.0.0.0"), FriendlyName("xRemoteFile")]`</span></span>

- <span data-ttu-id="40979-124">Cada campo contém uma descrição significativa.</span><span class="sxs-lookup"><span data-stu-id="40979-124">Every field has meaningful description.</span></span> <span data-ttu-id="40979-125">O repositório do PowerShell no GitHub tem bons exemplos, como o [.schema.mof para xRemoteFile](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/DSCResources/DSC_xRemoteFile/DSC_xRemoteFile.schema.mof)</span><span class="sxs-lookup"><span data-stu-id="40979-125">The PowerShell GitHub repository has good examples, such as the [.schema.mof for xRemoteFile](https://github.com/dsccommunity/xPSDesiredStateConfiguration/blob/master/source/DSCResources/DSC_xRemoteFile/DSC_xRemoteFile.schema.mof)</span></span>

<span data-ttu-id="40979-126">Além disso, você deve usar os cmdlets `Test-xDscResource` e `Test-xDscSchema` do [Designer de Recursos da DSC](https://www.powershellgallery.com/packages/xDSCResourceDesigner/1.12.0.0) para verificar automaticamente o recurso e o esquema:</span><span class="sxs-lookup"><span data-stu-id="40979-126">Additionally, you should use `Test-xDscResource` and `Test-xDscSchema` cmdlets from [DSC Resource Designer](https://www.powershellgallery.com/packages/xDSCResourceDesigner/1.12.0.0) to automatically verify the resource and schema:</span></span>

```
Test-xDscResource <Resource_folder>
Test-xDscSchema <Path_to_resource_schema_file>
```

<span data-ttu-id="40979-127">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="40979-127">For example:</span></span>

```powershell
Test-xDscResource ..\DSCResources\MSFT_xRemoteFile
Test-xDscSchema ..\DSCResources\MSFT_xRemoteFile\MSFT_xRemoteFile.schema.mof
```

## <a name="resource-loads-without-errors"></a><span data-ttu-id="40979-128">O recurso é carregado sem erros</span><span class="sxs-lookup"><span data-stu-id="40979-128">Resource loads without errors</span></span>

<span data-ttu-id="40979-129">Verifique se o módulo de recurso poderá ser carregado com êxito.</span><span class="sxs-lookup"><span data-stu-id="40979-129">Check whether the resource module can be successfully loaded.</span></span> <span data-ttu-id="40979-130">Isso pode ser feito manualmente executando `Import-Module <resource_module> -force` e confirmando se não ocorreu nenhum erro, ou ainda escrevendo uma automação de teste.</span><span class="sxs-lookup"><span data-stu-id="40979-130">This can be achieved manually, by running `Import-Module <resource_module> -force` and confirming that no errors occurred, or by writing test automation.</span></span> <span data-ttu-id="40979-131">No caso do último, é possível seguir esta estrutura em seu caso de teste:</span><span class="sxs-lookup"><span data-stu-id="40979-131">In case of the latter, you can follow this structure in your test case:</span></span>

```powershell
$error = $null
Import-Module <resource_module> –force
If ($error.count –ne 0) {
    Throw "Module was not imported correctly. Errors returned: $error"
}
```

## <a name="resource-is-idempotent-in-the-positive-case"></a><span data-ttu-id="40979-132">O recurso é idempotente no caso positivo</span><span class="sxs-lookup"><span data-stu-id="40979-132">Resource is idempotent in the positive case</span></span>

<span data-ttu-id="40979-133">Uma das características fundamentais dos recursos da DSC é a idempotência.</span><span class="sxs-lookup"><span data-stu-id="40979-133">One of the fundamental characteristics of DSC resources is idempotence.</span></span> <span data-ttu-id="40979-134">Isso significa que aplicar várias vezes uma configuração de DSC que contém esse recurso fará com que o mesmo resultado seja obtido sempre.</span><span class="sxs-lookup"><span data-stu-id="40979-134">It means that applying a DSC configuration containing that resource multiple times will always achieve the same result.</span></span> <span data-ttu-id="40979-135">Por exemplo, se criarmos uma configuração que contém o seguinte recurso File:</span><span class="sxs-lookup"><span data-stu-id="40979-135">For example, if we create a configuration which contains the following File resource:</span></span>

```powershell
File file {
    DestinationPath = "C:\test\test.txt"
    Contents = "Sample text"
}
```

<span data-ttu-id="40979-136">Depois de aplicá-la pela primeira vez, o arquivo test.txt deve aparecer na pasta `C:\test`.</span><span class="sxs-lookup"><span data-stu-id="40979-136">After applying it for the first time, file test.txt should appear in `C:\test` folder.</span></span> <span data-ttu-id="40979-137">No entanto, execuções posteriores da mesma configuração não devem alterar o estado do computador (por exemplo, nenhuma cópia do arquivo `test.txt` deve ser criada).</span><span class="sxs-lookup"><span data-stu-id="40979-137">However, subsequent runs of the same configuration should not change the state of the machine (e.g. no copies of the `test.txt` file should be created).</span></span> <span data-ttu-id="40979-138">Para garantir que um recurso é idempotente, você pode chamar repetidamente `Set-TargetResource` ao testar o recurso diretamente, ou chamar `Start-DscConfiguration`várias vezes ao realizar testes de ponta a ponta.</span><span class="sxs-lookup"><span data-stu-id="40979-138">To ensure a resource is idempotent you can repeatedly call `Set-TargetResource` when testing the resource directly, or call `Start-DscConfiguration` multiple times when doing end to end testing.</span></span> <span data-ttu-id="40979-139">O resultado deve ser o mesmo após cada execução.</span><span class="sxs-lookup"><span data-stu-id="40979-139">The result should be the same after every run.</span></span>

## <a name="test-user-modification-scenario"></a><span data-ttu-id="40979-140">Cenário de modificação de usuário de teste</span><span class="sxs-lookup"><span data-stu-id="40979-140">Test user modification scenario</span></span>

<span data-ttu-id="40979-141">Ao alterar o estado do computador e, em seguida, executar a DSC novamente, você poderá verificar se `Set-TargetResource` e `Test-TargetResource` funcionam corretamente.</span><span class="sxs-lookup"><span data-stu-id="40979-141">By changing the state of the machine and then rerunning DSC, you can verify that `Set-TargetResource` and `Test-TargetResource` function properly.</span></span> <span data-ttu-id="40979-142">Aqui estão as etapas que devem ser seguidas:</span><span class="sxs-lookup"><span data-stu-id="40979-142">Here are steps you should take:</span></span>

1. <span data-ttu-id="40979-143">Inicie com o recurso fora do estado desejado.</span><span class="sxs-lookup"><span data-stu-id="40979-143">Start with the resource not in the desired state.</span></span>
1. <span data-ttu-id="40979-144">Executar a configuração com o recurso</span><span class="sxs-lookup"><span data-stu-id="40979-144">Run configuration with your resource</span></span>
1. <span data-ttu-id="40979-145">Verificar `Test-DscConfiguration` retorna True</span><span class="sxs-lookup"><span data-stu-id="40979-145">Verify `Test-DscConfiguration` returns True</span></span>
1. <span data-ttu-id="40979-146">Modificar o item configurado para ficar fora do estado desejado</span><span class="sxs-lookup"><span data-stu-id="40979-146">Modify the configured item to be out of the desired state</span></span>
1. <span data-ttu-id="40979-147">Verificar `Test-DscConfiguration` retorna False</span><span class="sxs-lookup"><span data-stu-id="40979-147">Verify `Test-DscConfiguration` returns false</span></span>

<span data-ttu-id="40979-148">Aqui está um exemplo mais concreto usando o recurso do Registro:</span><span class="sxs-lookup"><span data-stu-id="40979-148">Here's a more concrete example using Registry resource:</span></span>

1. <span data-ttu-id="40979-149">Inicie com a chave do Registro fora do estado desejado</span><span class="sxs-lookup"><span data-stu-id="40979-149">Start with registry key not in the desired state</span></span>
1. <span data-ttu-id="40979-150">Executar `Start-DscConfiguration` com uma configuração para colocá-la no estado desejado e verificar se ela é passada.</span><span class="sxs-lookup"><span data-stu-id="40979-150">Run `Start-DscConfiguration` with a configuration to put it in the desired state and verify it passes.</span></span>
1. <span data-ttu-id="40979-151">Executar `Test-DscConfiguration` e verificar se ela retorna true</span><span class="sxs-lookup"><span data-stu-id="40979-151">Run `Test-DscConfiguration` and verify it returns true</span></span>
1. <span data-ttu-id="40979-152">Modificar o valor da chave para que ela não esteja no estado desejado</span><span class="sxs-lookup"><span data-stu-id="40979-152">Modify the value of the key so that it is not in the desired state</span></span>
1. <span data-ttu-id="40979-153">Executar `Test-DscConfiguration` e verificar se ela retorna false</span><span class="sxs-lookup"><span data-stu-id="40979-153">Run `Test-DscConfiguration` and verify it returns false</span></span>
1. <span data-ttu-id="40979-154">A funcionalidade `Get-TargetResource` foi verificada usando `Get-DscConfiguration`</span><span class="sxs-lookup"><span data-stu-id="40979-154">`Get-TargetResource` functionality was verified using `Get-DscConfiguration`</span></span>

<span data-ttu-id="40979-155">`Get-TargetResource` deve retornar detalhes do estado atual do recurso.</span><span class="sxs-lookup"><span data-stu-id="40979-155">`Get-TargetResource` should return details of the current state of the resource.</span></span> <span data-ttu-id="40979-156">Certifique-se de testá-lo chamando `Get-DscConfiguration` depois de aplicar a configuração e verificar se a saída reflete corretamente o estado atual do computador.</span><span class="sxs-lookup"><span data-stu-id="40979-156">Make sure to test it by calling `Get-DscConfiguration` after you apply the configuration and verifying that output correctly reflects the current state of the machine.</span></span> <span data-ttu-id="40979-157">É importante testá-lo separadamente, pois quaisquer problemas nesta área não aparecerão ao chamar `Start-DscConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="40979-157">It's important to test it separately, since any issues in this area won't appear when calling `Start-DscConfiguration`.</span></span>

## <a name="call-getsettest-targetresource-functions-directly"></a><span data-ttu-id="40979-158">Chame as funções **Get/Set/Test-TargetResource** diretamente</span><span class="sxs-lookup"><span data-stu-id="40979-158">Call **Get/Set/Test-TargetResource** functions directly</span></span>

<span data-ttu-id="40979-159">Lembre-se de testar as funções `Get/Set/Test-TargetResource` implementadas em seu recurso chamando-as diretamente e verificando se funcionam como esperado.</span><span class="sxs-lookup"><span data-stu-id="40979-159">Make sure you test the `Get/Set/Test-TargetResource` functions implemented in your resource by calling them directly and verifying that they work as expected.</span></span>

## <a name="verify-end-to-end-using-start-dscconfiguration"></a><span data-ttu-id="40979-160">Faça uma verificação completa usando Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="40979-160">Verify End to End using Start-DscConfiguration</span></span>

<span data-ttu-id="40979-161">É importante testar as funções `Get/Set/Test-TargetResource` chamando-as diretamente; no entanto, nem todos os problemas serão descobertos dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="40979-161">Testing `Get/Set/Test-TargetResource` functions by calling them directly is important, but not all issues will be discovered this way.</span></span> <span data-ttu-id="40979-162">Você deve concentrar uma parte significativa do teste no uso de `Start-DscConfiguration` ou no servidor de pull.</span><span class="sxs-lookup"><span data-stu-id="40979-162">You should focus significant part of your testing on using `Start-DscConfiguration` or the pull server.</span></span> <span data-ttu-id="40979-163">Na verdade, essa é a forma como os usuários usarão o recurso. Portanto, não subestime a importância desse tipo de testes.</span><span class="sxs-lookup"><span data-stu-id="40979-163">In fact, this is how users will use the resource, so don't underestimate the significance of this type of tests.</span></span> <span data-ttu-id="40979-164">Possíveis tipos de problemas:</span><span class="sxs-lookup"><span data-stu-id="40979-164">Possible types of issues:</span></span>

- <span data-ttu-id="40979-165">A Credencial/Sessão podem se comportar de maneira diferente, porque o agente do DSC é executado como um serviço.</span><span class="sxs-lookup"><span data-stu-id="40979-165">Credential/Session may behave differently because the DSC agent runs as a service.</span></span> <span data-ttu-id="40979-166">Certifique-se de testar quaisquer recursos aqui de ponta a ponta.</span><span class="sxs-lookup"><span data-stu-id="40979-166">Be sure to test any features here end to end.</span></span>
- <span data-ttu-id="40979-167">Os erros gerados por `Start-DscConfiguration` podem ser diferentes daqueles exibidos ao chamar diretamente a função `Set-TargetResource`.</span><span class="sxs-lookup"><span data-stu-id="40979-167">Errors output by `Start-DscConfiguration` may be different than those displayed when calling the `Set-TargetResource` function directly.</span></span>

## <a name="test-compatibility-on-all-dsc-supported-platforms"></a><span data-ttu-id="40979-168">Teste a compatibilidade em todas as plataformas com suporte para DSC</span><span class="sxs-lookup"><span data-stu-id="40979-168">Test compatibility on all DSC supported platforms</span></span>

<span data-ttu-id="40979-169">O recurso deve funcionar em todas as plataformas do DSC com suporte (Windows Server 2008 R2 e mais recente).</span><span class="sxs-lookup"><span data-stu-id="40979-169">Resource should work on all DSC supported platforms (Windows Server 2008 R2 and newer).</span></span> <span data-ttu-id="40979-170">Instale o WMF (Windows Management Framework) mais recente em seu sistema operacional para obter a versão mais recente da DSC.</span><span class="sxs-lookup"><span data-stu-id="40979-170">Install the latest WMF (Windows Management Framework) on your OS to get the latest version of DSC.</span></span> <span data-ttu-id="40979-171">Se seu recurso não funcionar em algumas dessas plataformas por design, uma mensagem de erro específica deverá ser retornada.</span><span class="sxs-lookup"><span data-stu-id="40979-171">If your resource does not work on some of these platforms by design, a specific error message should be returned.</span></span> <span data-ttu-id="40979-172">Além disso, certifique-se de que o recurso verifica se os cmdlets que estão sendo chamados estão presentes em um computador específico.</span><span class="sxs-lookup"><span data-stu-id="40979-172">Also, make sure your resource checks whether cmdlets you are calling are present on particular machine.</span></span> <span data-ttu-id="40979-173">O Windows Server 2012 adicionou um grande número de novos cmdlets que não estão disponíveis no Windows Server 2008R2, mesmo com o WMF instalado.</span><span class="sxs-lookup"><span data-stu-id="40979-173">Windows Server 2012 added a large number of new cmdlets that are not available on Windows Server 2008R2, even with WMF installed.</span></span>

## <a name="verify-on-windows-client-if-applicable"></a><span data-ttu-id="40979-174">Verifique no Windows Client (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="40979-174">Verify on Windows Client (if applicable)</span></span>

<span data-ttu-id="40979-175">Um intervalo de teste muito comum é verificar o recurso somente nas versões do servidor do Windows.</span><span class="sxs-lookup"><span data-stu-id="40979-175">One very common test gap is verifying the resource only on server versions of Windows.</span></span> <span data-ttu-id="40979-176">Muitos recursos também foram projetados para funcionar em SKUs do Cliente. Portanto, se esse for o seu caso, não se esqueça de testá-lo nessas plataformas também.</span><span class="sxs-lookup"><span data-stu-id="40979-176">Many resources are also designed to work on Client SKUs, so if that's true in your case, don't forget to test it on those platforms as well.</span></span>

## <a name="get-dscresource-lists-the-resource"></a><span data-ttu-id="40979-177">Get-DSCResource lista os recursos</span><span class="sxs-lookup"><span data-stu-id="40979-177">Get-DSCResource lists the resource</span></span>

<span data-ttu-id="40979-178">Depois de implantar o módulo, uma chamada a `Get-DscResource` deverá listar seu recurso, entre outros, como resultado.</span><span class="sxs-lookup"><span data-stu-id="40979-178">After deploying the module, calling `Get-DscResource` should list your resource among others as a result.</span></span> <span data-ttu-id="40979-179">Se não encontrar seu recurso na lista, verifique se o arquivo schema.mof para esse recurso existe.</span><span class="sxs-lookup"><span data-stu-id="40979-179">If you can't find your resource in the list, make sure that schema.mof file for that resource exists.</span></span>

## <a name="resource-module-contains-examples"></a><span data-ttu-id="40979-180">O módulo de recurso contém exemplos</span><span class="sxs-lookup"><span data-stu-id="40979-180">Resource module contains examples</span></span>

<span data-ttu-id="40979-181">Criando exemplos de qualidade que ajudarão outros a entender como usá-los.</span><span class="sxs-lookup"><span data-stu-id="40979-181">Creating quality examples which will help others understand how to use it.</span></span> <span data-ttu-id="40979-182">Isso é crucial, especialmente porque muitos usuários tratam o código de exemplo como documentação.</span><span class="sxs-lookup"><span data-stu-id="40979-182">This is crucial, especially since many users treat sample code as documentation.</span></span>

- <span data-ttu-id="40979-183">Primeiro, é necessário determinar os exemplos que serão incluídos com o módulo – no mínimo, deve-se abranger os casos de uso mais importantes para o recurso:</span><span class="sxs-lookup"><span data-stu-id="40979-183">First, you should determine the examples that will be included with the module – at minimum, you should cover most important use cases for your resource:</span></span>
- <span data-ttu-id="40979-184">Se o módulo contiver vários recursos que precisam funcionar juntos para um cenário de ponta a ponta, o exemplo de ponta a ponta básico seria, teoricamente, o primeiro.</span><span class="sxs-lookup"><span data-stu-id="40979-184">If your module contains several resources that need to work together for an end-to-end scenario, the basic end-to-end example would ideally be first.</span></span>
- <span data-ttu-id="40979-185">Os exemplos inicias devem ser bem simples – como começar a usar seus recursos em partes gerenciáveis pequenas (por exemplo, criar um novo VHD)</span><span class="sxs-lookup"><span data-stu-id="40979-185">The initial examples should be very simple -- how to get started with your resources in small manageable chunks (e.g. creating a new VHD)</span></span>
- <span data-ttu-id="40979-186">Os exemplos posteriores devem se basear nesses exemplos (por exemplo, criar uma VM desde um VHD, remover a VM e modificá-la) e mostrar a funcionalidade avançada (por exemplo, criar uma VM com memória dinâmica)</span><span class="sxs-lookup"><span data-stu-id="40979-186">Subsequent examples should build on those examples (e.g. creating a VM from a VHD, removing VM, modifying VM), and show advanced functionality (e.g. creating a VM with dynamic memory)</span></span>
- <span data-ttu-id="40979-187">Os exemplos de configurações devem ser parametrizados (todos os valores devem ser passados para a configuração como parâmetros e não deve haver nenhum valor fixo):</span><span class="sxs-lookup"><span data-stu-id="40979-187">Example configurations should be parameterized (all values should be passed to the configuration as parameters and there should be no hardcoded values):</span></span>

```powershell
configuration Sample_xRemoteFile_DownloadFile
{
    param
    (
        [string[]] $nodeName = 'localhost',

        [parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String] $destinationPath,

        [parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String] $uri,

        [String] $userAgent,

        [Hashtable] $headers
    )

    Import-DscResource -Name MSFT_xRemoteFile -ModuleName xPSDesiredStateConfiguration

    Node $nodeName
    {
        xRemoteFile DownloadFile
        {
            DestinationPath = $destinationPath
            Uri = $uri
            UserAgent = $userAgent
            Headers = $headers
        }
    }
}
```

- <span data-ttu-id="40979-188">É uma prática recomendada incluir um exemplo (comentado) de como chamar a configuração com os valores reais no final do script de exemplo.</span><span class="sxs-lookup"><span data-stu-id="40979-188">It's a good practice to include (commented out) example of how to call the configuration with the actual values at the end of the example script.</span></span> <span data-ttu-id="40979-189">Por exemplo, na configuração acima, não é absolutamente óbvio que a melhor maneira de especificar o UserAgent é:</span><span class="sxs-lookup"><span data-stu-id="40979-189">For example, in the configuration above it isn't necessarily obvious that the best way to specify UserAgent is:</span></span>

  <span data-ttu-id="40979-190">`UserAgent = [Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer` Nesse caso, um comentário pode esclarecer a execução pretendida da configuração:</span><span class="sxs-lookup"><span data-stu-id="40979-190">`UserAgent = [Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer` In which case a comment can clarify the intended execution of the configuration:</span></span>

```powershell
<#
Sample use (parameter values need to be changed according to your scenario):

Sample_xRemoteFile_DownloadFile -destinationPath "$env:SystemDrive\fileName.jpg" -uri "http://www.contoso.com/image.jpg"

Sample_xRemoteFile_DownloadFile -destinationPath "$env:SystemDrive\fileName.jpg" -uri "http://www.contoso.com/image.jpg" `
-userAgent [Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer -headers @{"Accept-Language" = "en-US"}
#>
```

- <span data-ttu-id="40979-191">Para cada exemplo, escreva uma breve descrição que explica o que ele faz e o significado dos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="40979-191">For each example, write a short description which explains what it does, and the meaning of the parameters.</span></span>
- <span data-ttu-id="40979-192">Certifique-se de que os exemplos abrangem a maioria dos cenários importantes para o recurso e que nada está faltando, verifique se todos eles são executados e coloque o computador no estado desejado.</span><span class="sxs-lookup"><span data-stu-id="40979-192">Make sure examples cover most the important scenarios for your resource and if there's nothing missing, verify that they all execute and put machine in the desired state.</span></span>

## <a name="error-messages-are-easy-to-understand-and-help-users-solve-problems"></a><span data-ttu-id="40979-193">Mensagens de erro são fáceis de entender e ajudam os usuários a resolver problemas</span><span class="sxs-lookup"><span data-stu-id="40979-193">Error messages are easy to understand and help users solve problems</span></span>

<span data-ttu-id="40979-194">Mensagens de erro úteis devem ser:</span><span class="sxs-lookup"><span data-stu-id="40979-194">Good error messages should be:</span></span>

- <span data-ttu-id="40979-195">Existentes: o maior problema com mensagens de erro é que elas geralmente não existem; portanto, certifique-se de que elas existem.</span><span class="sxs-lookup"><span data-stu-id="40979-195">There: The biggest problem with error messages is that they often don't exist, so make sure they are there.</span></span>
- <span data-ttu-id="40979-196">Fácil de entender: legíveis por humanos e sem códigos de erro obscuros</span><span class="sxs-lookup"><span data-stu-id="40979-196">Easy to understand: Human readable, no obscure error codes</span></span>
- <span data-ttu-id="40979-197">Precisas: descrevem qual é exatamente o problema</span><span class="sxs-lookup"><span data-stu-id="40979-197">Precise: Describe what's exactly the problem</span></span>
- <span data-ttu-id="40979-198">Construtivas: fazem recomendações sobre como corrigir o problema</span><span class="sxs-lookup"><span data-stu-id="40979-198">Constructive: Advice how to fix the issue</span></span>
- <span data-ttu-id="40979-199">Educadas: não culpam o usuário ou os fazem sentir-se mal</span><span class="sxs-lookup"><span data-stu-id="40979-199">Polite: Don't blame user or make them feel bad</span></span>

<span data-ttu-id="40979-200">Certifique-se de verificar erros nos cenários de ponta a ponta (usando `Start-DscConfiguration`), pois eles podem ser diferentes daqueles retornados ao executar as funções de recurso diretamente.</span><span class="sxs-lookup"><span data-stu-id="40979-200">Make sure you verify errors in End to End scenarios (using `Start-DscConfiguration`), because they may differ from those returned when running resource functions directly.</span></span>

## <a name="log-messages-are-easy-to-understand-and-informative-including-verbose-debug-and-etw-logs"></a><span data-ttu-id="40979-201">Mensagens de log são informativas e fáceis de entender (incluindo –verbose, –debug e logs do ETW)</span><span class="sxs-lookup"><span data-stu-id="40979-201">Log messages are easy to understand and informative (including –verbose, –debug and ETW logs)</span></span>

<span data-ttu-id="40979-202">Certifique-se de que logs gerados pelo recurso são fáceis de entender e fornecem valor ao usuário.</span><span class="sxs-lookup"><span data-stu-id="40979-202">Ensure that logs outputted by the resource are easy to understand and provide value to the user.</span></span>
<span data-ttu-id="40979-203">Os recursos devem gerar todas as informações que podem ser úteis para o usuário; contudo, mais logs nem sempre são o melhor.</span><span class="sxs-lookup"><span data-stu-id="40979-203">Resources should output all information which might be helpful to the user, but more logs is not always better.</span></span> <span data-ttu-id="40979-204">É necessário evitar a redundância e gerar dados que não fornecem valor adicional – não faça alguém percorrer centenas de entradas de log para encontrar o que está procurando.</span><span class="sxs-lookup"><span data-stu-id="40979-204">You should avoid redundancy and outputting data which does not provide additional value – don't make someone go through hundreds of log entries in order to find what they're looking for.</span></span> <span data-ttu-id="40979-205">Obviamente, não fornecer nenhum log também não é uma solução aceitável para esse problema.</span><span class="sxs-lookup"><span data-stu-id="40979-205">Of course, no logs is not an acceptable solution for this problem either.</span></span>

<span data-ttu-id="40979-206">Durante o teste, também é necessário analisar logs detalhados e de depuração (executando `Start-DscConfiguration` com as opções `–Verbose` e `–Debug` de maneira adequada), bem como os logs do ETW.</span><span class="sxs-lookup"><span data-stu-id="40979-206">When testing, you should also analyze verbose and debug logs (by running `Start-DscConfiguration` with `–Verbose` and `–Debug` switches appropriately), as well as ETW logs.</span></span> <span data-ttu-id="40979-207">Para ver os logs do ETW do DSC, vá para Visualizador de Eventos e abra a pasta a seguir: Aplicativos e Serviços – Microsoft – Windows – Desired State Configuration.</span><span class="sxs-lookup"><span data-stu-id="40979-207">To see DSC ETW logs, go to Event Viewer and open the following folder: Applications and Services- Microsoft - Windows - Desired State Configuration.</span></span> <span data-ttu-id="40979-208">Por padrão, haverá o canal Operacional, mas lembre-se de habilitar os canais Analítico e de Depuração antes de executar a configuração.</span><span class="sxs-lookup"><span data-stu-id="40979-208">By default there will be Operational channel, but make sure you enable Analytic and Debug channels before running the configuration.</span></span> <span data-ttu-id="40979-209">Para habilitar os canais Analítico/de Depuração, é possível executar o script abaixo:</span><span class="sxs-lookup"><span data-stu-id="40979-209">To enable Analytic/Debug channels, you can execute script below:</span></span>

```powershell
$statusEnabled = $true
# Use "Analytic" to enable Analytic channel
$eventLogFullName = "Microsoft-Windows-Dsc/Debug"
$commandToExecute = "wevtutil set-log $eventLogFullName /e:$statusEnabled /q:$statusEnabled   "
$log = New-Object System.Diagnostics.Eventing.Reader.EventLogConfiguration $eventLogFullName
if($statusEnabled -eq $log.IsEnabled)
{
    Write-Host -Verbose "The channel event log is already enabled"
    return
}
Invoke-Expression $commandToExecute
```

## <a name="resource-implementation-does-not-contain-hardcoded-paths"></a><span data-ttu-id="40979-210">A implementação de recurso não contêm caminhos fixos</span><span class="sxs-lookup"><span data-stu-id="40979-210">Resource implementation does not contain hardcoded paths</span></span>

<span data-ttu-id="40979-211">Assegure-se de que não há nenhum caminho fixo na implementação de recurso, especialmente, se ele assume um idioma (en-us) ou quando houver variáveis do sistema que podem ser usadas.</span><span class="sxs-lookup"><span data-stu-id="40979-211">Ensure there are no hardcoded paths in the resource implementation, particularly if they assume language (en-us), or when there are system variables that can be used.</span></span> <span data-ttu-id="40979-212">Se o recurso precisar acessar caminhos específicos, use variáveis de ambiente em vez de fixar o caminho no código, pois ele pode ser diferente em outros computadores.</span><span class="sxs-lookup"><span data-stu-id="40979-212">If your resource need to access specific paths, use environment variables instead of hardcoding the path, as it may differ on other machines.</span></span>

<span data-ttu-id="40979-213">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="40979-213">Example:</span></span>

<span data-ttu-id="40979-214">Em vez de:</span><span class="sxs-lookup"><span data-stu-id="40979-214">Instead of:</span></span>

```powershell
$tempPath = "C:\Users\kkaczma\AppData\Local\Temp\MyResource"
$programFilesPath = "C:\Program Files (x86)"
```

<span data-ttu-id="40979-215">É possível escrever:</span><span class="sxs-lookup"><span data-stu-id="40979-215">You can write:</span></span>

```powershell
$tempPath = Join-Path $env:temp "MyResource"
$programFilesPath = ${env:ProgramFiles(x86)}
```

## <a name="resource-implementation-does-not-contain-user-information"></a><span data-ttu-id="40979-216">A implementação de recurso não contêm informações do usuário</span><span class="sxs-lookup"><span data-stu-id="40979-216">Resource implementation does not contain user information</span></span>

<span data-ttu-id="40979-217">Assegure-se de que não há nenhum nome de email, informações de conta ou nome de pessoas no código.</span><span class="sxs-lookup"><span data-stu-id="40979-217">Make sure there are no email names, account information, or names of people in the code.</span></span>

## <a name="resource-was-tested-with-validinvalid-credentials"></a><span data-ttu-id="40979-218">O recurso foi testado com credenciais válidas/inválidas</span><span class="sxs-lookup"><span data-stu-id="40979-218">Resource was tested with valid/invalid credentials</span></span>

<span data-ttu-id="40979-219">Caso o recurso use uma credencial como parâmetro:</span><span class="sxs-lookup"><span data-stu-id="40979-219">If your resource takes a credential as parameter:</span></span>

- <span data-ttu-id="40979-220">Verifique se o recurso funciona quando o Sistema Local (ou a conta de computador de recursos remotos) não tem acesso.</span><span class="sxs-lookup"><span data-stu-id="40979-220">Verify the resource works when Local System (or the computer account for remote resources) does not have access.</span></span>
- <span data-ttu-id="40979-221">Verifique se o recurso funciona com uma credencial especificada para Get, Set e Test</span><span class="sxs-lookup"><span data-stu-id="40979-221">Verify the resource works with a credential specified for Get, Set and Test</span></span>
- <span data-ttu-id="40979-222">Caso o recurso acesse os compartilhamentos, teste todas as variantes para as quais é necessário dar suporte, como:</span><span class="sxs-lookup"><span data-stu-id="40979-222">If your resource accesses shares, test all the variants you need to support, such as:</span></span>
  - <span data-ttu-id="40979-223">Compartilhamentos de janelas padrão.</span><span class="sxs-lookup"><span data-stu-id="40979-223">Standard windows shares.</span></span>
  - <span data-ttu-id="40979-224">Compartilhamentos DFS.</span><span class="sxs-lookup"><span data-stu-id="40979-224">DFS shares.</span></span>
  - <span data-ttu-id="40979-225">Compartilhamentos SAMBA (se desejar dar suporte ao Linux).</span><span class="sxs-lookup"><span data-stu-id="40979-225">SAMBA shares (if you want to support Linux.)</span></span>

## <a name="resource-does-not-require-interactive-input"></a><span data-ttu-id="40979-226">O recurso não requer entrada interativa</span><span class="sxs-lookup"><span data-stu-id="40979-226">Resource does not require interactive input</span></span>

<span data-ttu-id="40979-227">As funções `Get/Set/Test-TargetResource` devem ser executadas automaticamente e não devem aguardar pela entrada do usuário em nenhum estágio de execução (por exemplo, não se deve usar `Get-Credential` dentro dessas funções).</span><span class="sxs-lookup"><span data-stu-id="40979-227">`Get/Set/Test-TargetResource` functions should be executed automatically and must not wait for user's input at any stage of execution (e.g. you should not use `Get-Credential` inside these functions).</span></span> <span data-ttu-id="40979-228">Se for necessário fornecer a entrada do usuário, passe-a para a configuração como um parâmetro durante a fase de compilação.</span><span class="sxs-lookup"><span data-stu-id="40979-228">If you need to provide user's input, you should pass it to the configuration as parameter during the compilation phase.</span></span>

## <a name="resource-functionality-was-thoroughly-tested"></a><span data-ttu-id="40979-229">A funcionalidade do recurso foi totalmente testada</span><span class="sxs-lookup"><span data-stu-id="40979-229">Resource functionality was thoroughly tested</span></span>

<span data-ttu-id="40979-230">Esta lista de verificação contém itens cujo teste é importante e/ou que, frequentemente, estão ausentes.</span><span class="sxs-lookup"><span data-stu-id="40979-230">This checklist contains items which are important to be tested and/or are often missed.</span></span> <span data-ttu-id="40979-231">Haverá vários testes, principalmente, aqueles funcionais que serão específicos ao recurso que está sendo testado e que não são mencionados aqui.</span><span class="sxs-lookup"><span data-stu-id="40979-231">There will be bunch of tests, mainly functional ones which will be specific to the resource you are testing and are not mentioned here.</span></span> <span data-ttu-id="40979-232">Não se esqueça dos casos de teste negativos.</span><span class="sxs-lookup"><span data-stu-id="40979-232">Don't forget about negative test cases.</span></span>

## <a name="best-practice-resource-module-contains-tests-folder-with-resourcedesignertestsps1-script"></a><span data-ttu-id="40979-233">Prática recomendada: o módulo de recurso contém a pasta Tests com o script ResourceDesignerTests.ps1</span><span class="sxs-lookup"><span data-stu-id="40979-233">Best practice: Resource module contains Tests folder with ResourceDesignerTests.ps1 script</span></span>

<span data-ttu-id="40979-234">É uma boa prática criar a pasta "Testes" em um módulo de recurso. Criar o arquivo `ResourceDesignerTests.ps1` e adicionar testes usando `Test-xDscResource` e `Test-xDscSchema` para todos os recursos em um determinado módulo.</span><span class="sxs-lookup"><span data-stu-id="40979-234">It's a good practice to create folder "Tests" inside resource module, create `ResourceDesignerTests.ps1` file and add tests using `Test-xDscResource` and `Test-xDscSchema` for all resources in given module.</span></span> <span data-ttu-id="40979-235">Dessa forma, você pode validar rapidamente os esquemas de todos os recursos de determinado módulo e fazer a verificação de integridade antes da publicação.</span><span class="sxs-lookup"><span data-stu-id="40979-235">This way you can quickly validate schemas of all resources from the given modules and do a sanity check before publishing.</span></span> <span data-ttu-id="40979-236">Para xRemoteFile, `ResourceTests.ps1` poderá ser bem simples, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="40979-236">For xRemoteFile, `ResourceTests.ps1` could look as simple as:</span></span>

```powershell
Test-xDscResource ..\DSCResources\MSFT_xRemoteFile
Test-xDscSchema ..\DSCResources\MSFT_xRemoteFile\MSFT_xRemoteFile.schema.mof
```

## <a name="best-practice-resource-supports--whatif"></a><span data-ttu-id="40979-237">Melhor prática: o recurso dá suporte a -WhatIf</span><span class="sxs-lookup"><span data-stu-id="40979-237">Best practice: Resource supports -WhatIf</span></span>

<span data-ttu-id="40979-238">Se o recurso estiver executando operações "perigosas", será uma boa prática implementar a funcionalidade `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="40979-238">If your resource is performing "dangerous" operations, it's a good practice to implement `-WhatIf` functionality.</span></span> <span data-ttu-id="40979-239">Após a conclusão, verifique se a saída de `-WhatIf` descreve corretamente o que aconteceria se o comando tivesse sido executado sem a opção `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="40979-239">After it's done, make sure that `-WhatIf` output correctly describes operations which would happen if command was executed without `-WhatIf` switch.</span></span> <span data-ttu-id="40979-240">Além disso, verifique se as operações não executam (sem alterações no estado do nó) quando a opção `–WhatIf` está presente.</span><span class="sxs-lookup"><span data-stu-id="40979-240">Also, verify that operations does not execute (no changes to the node's state are made) when `–WhatIf` switch is present.</span></span> <span data-ttu-id="40979-241">Por exemplo, suponha que vamos testar o recurso do arquivo.</span><span class="sxs-lookup"><span data-stu-id="40979-241">For example, let's assume we are testing File resource.</span></span> <span data-ttu-id="40979-242">Veja abaixo uma simples configuração que criar o arquivo `test.txt` com o conteúdo "teste":</span><span class="sxs-lookup"><span data-stu-id="40979-242">Below is simple configuration which creates file `test.txt` with contents "test":</span></span>

```powershell
configuration config
{
    node localhost
    {
        File file
        {
            Contents="test"
            DestinationPath="C:\test\test.txt"
        }
    }
}
config
```

<span data-ttu-id="40979-243">Se compilarmos e, em seguida, executarmos a configuração com a opção `-WhatIf`, a saída nos informará exatamente o que aconteceria quando a configuração fosse executada.</span><span class="sxs-lookup"><span data-stu-id="40979-243">If we compile and then execute the configuration with the `-WhatIf` switch, the output is telling us exactly what would happen when we run the configuration.</span></span> <span data-ttu-id="40979-244">Todavia, a configuração propriamente dita não foi executada (o arquivo `test.txt` não foi criado).</span><span class="sxs-lookup"><span data-stu-id="40979-244">The configuration itself however was not executed (`test.txt` file was not created).</span></span>

```powershell
Start-DscConfiguration -Path .\config -ComputerName localhost -Wait -Verbose -WhatIf
```

```Output
VERBOSE: Perform operation 'Invoke CimMethod' with following parameters, ''methodName' =
SendConfigurationApply,'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' =
root/Microsoft/Windows/DesiredStateConfiguration'.
VERBOSE: An LCM method call arrived from computer CHARLESX1 with user sid
S-1-5-21-397955417-626881126-188441444-5179871.
What if: [X]: LCM:  [ Start  Set      ]
What if: [X]: LCM:  [ Start  Resource ]  [[File]file]
What if: [X]: LCM:  [ Start  Test     ]  [[File]file]
What if: [X]:                            [[File]file] The system cannot find the file specified.
What if: [X]:                            [[File]file] The related file/directory is: C:\test\test.txt.
What if: [X]: LCM:  [ End    Test     ]  [[File]file]  in 0.0270 seconds.
What if: [X]: LCM:  [ Start  Set      ]  [[File]file]
What if: [X]:                            [[File]file] The system cannot find the file specified.
What if: [X]:                            [[File]file] The related file/directory is: C:\test\test.txt.
What if: [X]:                            [C:\test\test.txt] Creating and writing contents and setting attributes.
What if: [X]: LCM:  [ End    Set      ]  [[File]file]  in 0.0180 seconds.
What if: [X]: LCM:  [ End    Resource ]  [[File]file]
What if: [X]: LCM:  [ End    Set      ]
VERBOSE: [X]: LCM:  [ End    Set      ]    in  0.1050 seconds.
VERBOSE: Operation 'Invoke CimMethod' complete.
```

<span data-ttu-id="40979-245">Esta lista não é completa, mas abrange muitos problemas importantes que podem ser encontrados durante a criação, o desenvolvimento e o teste dos recursos da DSC.</span><span class="sxs-lookup"><span data-stu-id="40979-245">This list is not exhaustive, but it covers many important issues which can be encountered while designing, developing and testing DSC resources.</span></span>
