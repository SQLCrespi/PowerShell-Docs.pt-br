---
title: Como resolver conflitos de dependência de assembly de módulo do PowerShell
description: Ao escrever um módulo do PowerShell binário em C#, é natural assumir dependências de outros pacotes ou bibliotecas para fornecer funcionalidade.
ms.date: 06/25/2020
ms.custom: rjmholt
ms.openlocfilehash: 536bcfd1ced536faccde0d6c5bc483cdaf31ce68
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87775176"
---
# <a name="resolving-powershell-module-assembly-dependency-conflicts"></a><span data-ttu-id="77e53-103">Como resolver conflitos de dependência de assembly de módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="77e53-103">Resolving PowerShell module assembly dependency conflicts</span></span>

<span data-ttu-id="77e53-104">Ao escrever um módulo do PowerShell binário em C#, é natural assumir dependências de outros pacotes ou bibliotecas para fornecer funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="77e53-104">When writing a binary PowerShell module in C#, it's natural to take dependencies on other packages or libraries to provide functionality.</span></span> <span data-ttu-id="77e53-105">A obtenção de dependências em outras bibliotecas é desejável para reutilização de código.</span><span class="sxs-lookup"><span data-stu-id="77e53-105">Taking dependencies on other libraries is desirable for code reuse.</span></span> <span data-ttu-id="77e53-106">O PowerShell sempre carrega assemblies no mesmo contexto.</span><span class="sxs-lookup"><span data-stu-id="77e53-106">PowerShell always loads assemblies into the same context.</span></span> <span data-ttu-id="77e53-107">Isso apresenta problemas quando as dependências de um módulo entram em conflito com DLLs já carregadas e podem impedir o uso de dois módulos não relacionados na mesma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77e53-107">This presents issues when a module's dependencies conflict with already-loaded DLLs and may prevent using two otherwise unrelated modules in the same PowerShell session.</span></span>

<span data-ttu-id="77e53-108">Se você teve esse problema, você viu uma mensagem de erro como esta:</span><span class="sxs-lookup"><span data-stu-id="77e53-108">If you've had this problem, you've seen an error message like this:</span></span>

![Mensagem de erro de conflito de carregamento de assembly](./media/resolving-dependency-conflicts/moduleconflict.png)

<span data-ttu-id="77e53-110">Este artigo analisa algumas das maneiras como os conflitos de dependência ocorrem no PowerShell e como mitigar problemas de conflito de dependência.</span><span class="sxs-lookup"><span data-stu-id="77e53-110">This article looks at some of the ways dependency conflicts occur in PowerShell and ways to mitigate dependency conflict issues.</span></span> <span data-ttu-id="77e53-111">Mesmo que você não seja um autor do módulo, há alguns truques que podem ser úteis com conflitos de dependência que ocorrem em módulos que você usa.</span><span class="sxs-lookup"><span data-stu-id="77e53-111">Even if you're not a module author, there are some tricks in here that might help you with dependency conflicts occurring in modules that you use.</span></span>

## <a name="why-do-dependency-conflicts-occur"></a><span data-ttu-id="77e53-112">Por que conflitos de dependência ocorrem?</span><span class="sxs-lookup"><span data-stu-id="77e53-112">Why do dependency conflicts occur?</span></span>

<span data-ttu-id="77e53-113">No .NET, os conflitos de dependência ocorrem quando duas versões do mesmo assembly são carregadas no mesmo _Contexto de Carregamento do Assembly_.</span><span class="sxs-lookup"><span data-stu-id="77e53-113">In .NET, dependency conflicts occur when two versions of the same assembly are loaded into the same _Assembly Load Context_.</span></span> <span data-ttu-id="77e53-114">Esse termo tem significados ligeiramente diferentes em diferentes plataformas .NET, o que é explicado [mais tarde](#powershell-and-net).</span><span class="sxs-lookup"><span data-stu-id="77e53-114">This term means slightly different things on different .NET platforms, which is covered [later](#powershell-and-net).</span></span> <span data-ttu-id="77e53-115">Esse conflito é um problema comum que ocorre em qualquer software no qual as dependências com controle de versão são usadas.</span><span class="sxs-lookup"><span data-stu-id="77e53-115">This conflict is a common problem that occurs in any software where versioned dependencies are used.</span></span> <span data-ttu-id="77e53-116">Como não há soluções simples e como muitas estruturas de resolução de dependências tentam resolver o problema de diferentes maneiras, essa situação costuma ser chamada de "inferno de dependências".</span><span class="sxs-lookup"><span data-stu-id="77e53-116">Because there are no simple solutions, and because many dependency-resolution frameworks try to solve the problem in different ways, this situation is often called "dependency hell".</span></span>

<span data-ttu-id="77e53-117">Os problemas de conflito ocorrem porque um projeto quase nunca deliberadamente ou diretamente depende de duas versões da mesma dependência.</span><span class="sxs-lookup"><span data-stu-id="77e53-117">Conflict issues are compounded by the fact that a project almost never deliberately or directly depends on two versions of the same dependency.</span></span> <span data-ttu-id="77e53-118">Em vez disso, o projeto tem duas ou mais dependências que exigem uma versão diferente da mesma dependência.</span><span class="sxs-lookup"><span data-stu-id="77e53-118">Instead, the project has two or more dependencies that each require a different version of the same dependency.</span></span>

<span data-ttu-id="77e53-119">Por exemplo, digamos que o seu aplicativo .NET, `DuckBuilder`, traga duas dependências para executar partes da funcionalidade dele e que isso seja semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="77e53-119">For example, say your .NET application, `DuckBuilder`, brings in two dependencies, to perform parts of its functionality and looks like this:</span></span>

![Duas dependências de DuckBuilder dependem de versões diferentes do Newtonsoft.Json](./media/resolving-dependency-conflicts/dep-conflict.jpg)

<span data-ttu-id="77e53-121">Como `Contoso.ZipTools` e `Fabrikam.FileHelpers` dependem de versões diferentes do `Newtonsoft.Json`, pode haver um conflito de dependência dependendo de como cada dependência é carregada.</span><span class="sxs-lookup"><span data-stu-id="77e53-121">Because `Contoso.ZipTools` and `Fabrikam.FileHelpers` both depend on different versions of `Newtonsoft.Json`, there may be a dependency conflict depending on how each dependency is loaded.</span></span>

### <a name="conflicting-with-powershells-dependencies"></a><span data-ttu-id="77e53-122">Conflito com as dependências do PowerShell</span><span class="sxs-lookup"><span data-stu-id="77e53-122">Conflicting with PowerShell's dependencies</span></span>

<span data-ttu-id="77e53-123">No PowerShell, o problema de conflito de dependência é ampliado porque os módulos do PowerShell e as dependências do PowerShell são carregados no mesmo contexto compartilhado.</span><span class="sxs-lookup"><span data-stu-id="77e53-123">In PowerShell, the dependency conflict issue is magnified because PowerShell modules and PowerShell's own dependencies are loaded into the same shared context.</span></span> <span data-ttu-id="77e53-124">Isso significa que o mecanismo do PowerShell e todos os módulos do PowerShell carregados não podem ter dependências conflitantes.</span><span class="sxs-lookup"><span data-stu-id="77e53-124">This means the PowerShell engine and all loaded PowerShell modules must not have conflicting dependencies.</span></span> <span data-ttu-id="77e53-125">Um exemplo clássico disso é `Newtonsoft.Json`:</span><span class="sxs-lookup"><span data-stu-id="77e53-125">A classic example of this is `Newtonsoft.Json`:</span></span>

![O módulo FictionalTools depende da versão mais recente do Newtonsoft.Json do que o PowerShell](./media/resolving-dependency-conflicts/engine-conflict.jpg)

<span data-ttu-id="77e53-127">Neste exemplo, o módulo `FictionalTools` depende do `Newtonsoft.Json` versão `12.0.3`, que é uma versão mais recente de `Newtonsoft.Json` do que a `11.0.2` fornecida no PowerShell de exemplo.</span><span class="sxs-lookup"><span data-stu-id="77e53-127">In this example, the module `FictionalTools` depends on `Newtonsoft.Json` version `12.0.3`, which is a newer version of `Newtonsoft.Json` than `11.0.2` that ships in the example PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="77e53-128">Este é um exemplo e, no momento, o PowerShell 7 é fornecido com `Newtonsoft.Json 12.0.3`.</span><span class="sxs-lookup"><span data-stu-id="77e53-128">This is an example and PowerShell 7 currently ships with `Newtonsoft.Json 12.0.3`.</span></span>

<span data-ttu-id="77e53-129">Como o módulo depende de uma versão mais recente do assembly, ele não aceitará a versão que o PowerShell já carregou.</span><span class="sxs-lookup"><span data-stu-id="77e53-129">Because the module depends on a newer version of the assembly, it won't accept the version that PowerShell already has loaded.</span></span> <span data-ttu-id="77e53-130">Mas, como o PowerShell já carregou uma versão do assembly, o módulo não pode carregar a própria versão usando o mecanismo de carregamento convencional.</span><span class="sxs-lookup"><span data-stu-id="77e53-130">But because PowerShell has already loaded a version of the assembly, the module can't load its own version using the conventional load mechanism.</span></span>

### <a name="conflicting-with-another-modules-dependencies"></a><span data-ttu-id="77e53-131">Conflito com as dependências de outro módulo</span><span class="sxs-lookup"><span data-stu-id="77e53-131">Conflicting with another module's dependencies</span></span>

<span data-ttu-id="77e53-132">Outro cenário comum no PowerShell é que um módulo que depende de uma versão de um assembly é carregado e outro módulo que depende de uma versão diferente desse assembly é carregado mais tarde.</span><span class="sxs-lookup"><span data-stu-id="77e53-132">Another common scenario in PowerShell is that a module is loaded that depends on one version of an assembly, and then another module is loaded later that depends on a different version of that assembly.</span></span>

<span data-ttu-id="77e53-133">Isso frequentemente se parece com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="77e53-133">This often looks like the following:</span></span>

![Dois módulos do PowerShell exigem versões diferentes da dependência Microsoft.Extensions.Logging](./media/resolving-dependency-conflicts/mod-conflict.jpg)

<span data-ttu-id="77e53-135">Nesse caso, o módulo `FictionalTools` requer uma versão mais recente de `Microsoft.Extensions.Logging` do que o módulo `FilesystemManager`.</span><span class="sxs-lookup"><span data-stu-id="77e53-135">In this case, the `FictionalTools` module requires a newer version of `Microsoft.Extensions.Logging` than the `FilesystemManager` module.</span></span>

<span data-ttu-id="77e53-136">Imagine que esses módulos carregam as dependências deles colocando os assemblies de dependência no mesmo diretório que o assembly do módulo raiz.</span><span class="sxs-lookup"><span data-stu-id="77e53-136">Imagine these modules load their dependencies by placing the dependency assemblies in the same directory as the root module assembly.</span></span> <span data-ttu-id="77e53-137">Isso permite que o .NET carregue-os implicitamente por nome.</span><span class="sxs-lookup"><span data-stu-id="77e53-137">This allows .NET to implicitly load them by name.</span></span> <span data-ttu-id="77e53-138">Se estivermos executando o PowerShell 7 (além do .NET Core 3.1), poderemos carregar e executar o `FictionalTools` e, em seguida, carregar e executar o `FilesystemManager` sem problemas.</span><span class="sxs-lookup"><span data-stu-id="77e53-138">If we're running PowerShell 7 (on top of .NET Core 3.1), we can load and run `FictionalTools`, then load and run `FilesystemManager` without issue.</span></span> <span data-ttu-id="77e53-139">No entanto, em uma nova sessão, se carregarmos e executarmos o `FilesystemManager` e, em seguida, carregarmos o `FictionalTools`, obteremos um `FileLoadException` do comando `FictionalTools` porque ele requer uma versão mais recente de `Microsoft.Extensions.Logging` do que a carregada.</span><span class="sxs-lookup"><span data-stu-id="77e53-139">However, in a new session, if we load and run `FilesystemManager`, then load `FictionalTools`, we get a `FileLoadException` from the `FictionalTools` command because it requires a newer version of `Microsoft.Extensions.Logging` than the one loaded.</span></span>
<span data-ttu-id="77e53-140">O `FictionalTools` não consegue carregar a versão necessária porque um assembly de mesmo nome já foi carregado.</span><span class="sxs-lookup"><span data-stu-id="77e53-140">`FictionalTools` can't load the version needed because an assembly of the same name has already been loaded.</span></span>

## <a name="powershell-and-net"></a><span data-ttu-id="77e53-141">PowerShell e .NET</span><span class="sxs-lookup"><span data-stu-id="77e53-141">PowerShell and .NET</span></span>

<span data-ttu-id="77e53-142">O PowerShell é executado na plataforma .NET.</span><span class="sxs-lookup"><span data-stu-id="77e53-142">PowerShell runs on the .NET platform.</span></span> <span data-ttu-id="77e53-143">O NET e é, em última instância, responsável por resolver e carregar dependências de assembly. Portanto, precisamos entender como o .NET opera aqui para entender os conflitos de dependência.</span><span class="sxs-lookup"><span data-stu-id="77e53-143">NET is ultimately responsible for resolving and loading assembly dependencies, so we must understand how .NET operates here to understand dependency conflicts.</span></span>

<span data-ttu-id="77e53-144">Também precisamos ter em mente que diferentes versões do PowerShell são executadas em diferentes implementações do .NET.</span><span class="sxs-lookup"><span data-stu-id="77e53-144">We must also confront the fact that different versions of PowerShell run on different .NET implementations.</span></span> <span data-ttu-id="77e53-145">Em geral, o PowerShell 5.1 e versões anteriores são executados no .NET Framework, enquanto o PowerShell 6 e versões posteriores são executados no .NET Core.</span><span class="sxs-lookup"><span data-stu-id="77e53-145">In general, PowerShell 5.1 and below run on .NET Framework, while PowerShell 6 and above run on .NET Core.</span></span> <span data-ttu-id="77e53-146">Essas duas implementações do .NET carregam e administram assemblies de modo diferente.</span><span class="sxs-lookup"><span data-stu-id="77e53-146">These two implementations of .NET load and handle assemblies differently.</span></span>
<span data-ttu-id="77e53-147">Isso significa que a resolução de conflitos de dependência pode variar dependendo da plataforma .NET subjacente.</span><span class="sxs-lookup"><span data-stu-id="77e53-147">This means that resolving dependency conflicts can vary depending on the underlying .NET platform.</span></span>

### <a name="assembly-load-contexts"></a><span data-ttu-id="77e53-148">Contextos de carregamento de assembly</span><span class="sxs-lookup"><span data-stu-id="77e53-148">Assembly Load Contexts</span></span>

<span data-ttu-id="77e53-149">No .NET, um _ALC_ (Contexto de Carregamento de Assembly) que é um namespace do runtime no qual os assemblies são carregados.</span><span class="sxs-lookup"><span data-stu-id="77e53-149">In .NET, an _Assembly Load Context_ (ALC) that is a runtime namespace into which assemblies are loaded.</span></span> <span data-ttu-id="77e53-150">Os nomes dos assemblies precisam ser exclusivos.</span><span class="sxs-lookup"><span data-stu-id="77e53-150">The assemblies' names must be unique.</span></span> <span data-ttu-id="77e53-151">Esse conceito permite que os assemblies sejam resolvidos exclusivamente pelo nome em cada ALC.</span><span class="sxs-lookup"><span data-stu-id="77e53-151">This concept allows assemblies to be uniquely resolved by name in each ALC.</span></span>

### <a name="assembly-reference-loading-in-net"></a><span data-ttu-id="77e53-152">Carregamento de referência de assembly no .NET</span><span class="sxs-lookup"><span data-stu-id="77e53-152">Assembly reference loading in .NET</span></span>

<span data-ttu-id="77e53-153">A semântica do carregamento do assembly depende da implementação do .NET (.NET Core vs .NET Framework) e da API do .NET usada para carregar um determinado assembly.</span><span class="sxs-lookup"><span data-stu-id="77e53-153">The semantics of assembly loading depend on both the .NET implementation (.NET Core vs .NET Framework) and the .NET API used to load a particular assembly.</span></span> <span data-ttu-id="77e53-154">Em vez de entrar em detalhes aqui, há links na seção [Leitura adicional](#further-reading) que se aprofundam sobre como o carregamento do assembly do .NET funciona em cada implementação do .NET.</span><span class="sxs-lookup"><span data-stu-id="77e53-154">Rather than go into detail here, there are links in the [Further reading](#further-reading) section that go into great detail on how .NET assembly loading works in each .NET implementation.</span></span>

<span data-ttu-id="77e53-155">Neste artigo, vamos nos referir aos seguintes mecanismos:</span><span class="sxs-lookup"><span data-stu-id="77e53-155">In this article we'll refer to the following mechanisms:</span></span>

- <span data-ttu-id="77e53-156">Carregamento de assembly implícito (efetivamente `Assembly.Load(AssemblyName)`), que ocorre quando o .NET tenta, implicitamente, carregar um assembly por nome usando uma referência de assembly estática no código .NET.</span><span class="sxs-lookup"><span data-stu-id="77e53-156">Implicit assembly loading (effectively `Assembly.Load(AssemblyName)`), when .NET implicitly tries to load an assembly by name from a static assembly reference in .NET code.</span></span>
- <span data-ttu-id="77e53-157">`Assembly.LoadFrom()`, uma API de carregamento orientada por plug-in que adiciona manipuladores para resolver as dependências da DLL carregada.</span><span class="sxs-lookup"><span data-stu-id="77e53-157">`Assembly.LoadFrom()`, a plugin-oriented loading API that adds handlers to resolve dependencies of the loaded DLL.</span></span> <span data-ttu-id="77e53-158">Esse método pode não resolver dependências da maneira que desejamos.</span><span class="sxs-lookup"><span data-stu-id="77e53-158">This method may not resolve dependencies the way we want.</span></span>
- <span data-ttu-id="77e53-159">`Assembly.LoadFile()`, uma API de carregamento básica destinada a carregar apenas o assembly solicitado e que não trata de nenhuma dependência.</span><span class="sxs-lookup"><span data-stu-id="77e53-159">`Assembly.LoadFile()`, a basic loading API intended to load only the assembly asked for and does not handle any dependencies.</span></span>

### <a name="differences-in-net-framework-vs-net-core"></a><span data-ttu-id="77e53-160">Diferenças entre o .NET Framework e o .NET Core</span><span class="sxs-lookup"><span data-stu-id="77e53-160">Differences in .NET Framework vs .NET Core</span></span>

<span data-ttu-id="77e53-161">A maneira como essas APIs funcionam passou por mudanças sutis entre o .NET Core e o .NET Framework, portanto, vale a pena ler os [links](#further-reading) incluídos.</span><span class="sxs-lookup"><span data-stu-id="77e53-161">The way these APIs work has changed in subtle ways between .NET Core and .NET Framework, so it's worth reading through the included [links](#further-reading).</span></span> <span data-ttu-id="77e53-162">Importante: os Contextos de Carregamento de Assembly e outros mecanismos de resolução de assembly foram alterados entre o .NET Framework e o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="77e53-162">Importantly, Assembly Load Contexts and other assembly resolution mechanisms have changed between .NET Framework and .NET Core.</span></span>

<span data-ttu-id="77e53-163">Em particular, o .NET Framework tem os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="77e53-163">In particular, .NET Framework has the following features:</span></span>

- <span data-ttu-id="77e53-164">O Cache de Assembly Global, para resolução de assembly em todo o computador</span><span class="sxs-lookup"><span data-stu-id="77e53-164">The Global Assembly Cache, for machine-wide assembly resolution</span></span>
- <span data-ttu-id="77e53-165">Domínios do Aplicativo, que funcionam como áreas restritas em processo para isolamento de assembly, mas também apresentam uma camada de serialização com a qual lidar</span><span class="sxs-lookup"><span data-stu-id="77e53-165">Application Domains, which work like in-process sandboxes for assembly isolation, but also present a serialization layer to contend with</span></span>
- <span data-ttu-id="77e53-166">Um modelo de contexto de carregamento de assembly limitado, explicado em detalhes [aqui](/dotnet/framework/deployment/best-practices-for-assembly-loading), que tem um conjunto fixo de contextos de carregamento de assembly, cada um com o próprio comportamento:</span><span class="sxs-lookup"><span data-stu-id="77e53-166">A limited assembly load context model, explained in depth [here](/dotnet/framework/deployment/best-practices-for-assembly-loading), that has a fixed set of assembly load contexts, each with their own behavior:</span></span>
  - <span data-ttu-id="77e53-167">O contexto de carregamento padrão, em que os assemblies são carregados por padrão</span><span class="sxs-lookup"><span data-stu-id="77e53-167">The default load context, where assemblies are loaded by default</span></span>
  - <span data-ttu-id="77e53-168">O contexto de origem de carregamento, para carregar assemblies manualmente no runtime</span><span class="sxs-lookup"><span data-stu-id="77e53-168">The load-from context, for loading assemblies manually at runtime</span></span>
  - <span data-ttu-id="77e53-169">O contexto somente para reflexão, usado para carregar assemblies com segurança a fim de ler os metadados sem executá-los</span><span class="sxs-lookup"><span data-stu-id="77e53-169">The reflection-only context, for safely loading assemblies to read their metadata without running them</span></span>
  - <span data-ttu-id="77e53-170">O valor nulo misterioso nos quais os assemblies carregados com `Assembly.LoadFile(string path)` e `Assembly.Load(byte[] asmBytes)` residem</span><span class="sxs-lookup"><span data-stu-id="77e53-170">The mysterious void that assemblies loaded with `Assembly.LoadFile(string path)` and `Assembly.Load(byte[] asmBytes)` live in</span></span>

<span data-ttu-id="77e53-171">O .NET Core (e o .NET 5+) substituiu essa complexidade por um modelo mais simples:</span><span class="sxs-lookup"><span data-stu-id="77e53-171">.NET Core (and .NET 5+) has replaced this complexity with a simpler model:</span></span>

- <span data-ttu-id="77e53-172">Nenhum Cache de Assembly Global.</span><span class="sxs-lookup"><span data-stu-id="77e53-172">No Global Assembly Cache.</span></span> <span data-ttu-id="77e53-173">Os aplicativos trazem todas as próprias dependências.</span><span class="sxs-lookup"><span data-stu-id="77e53-173">Applications bring all their own dependencies.</span></span> <span data-ttu-id="77e53-174">Isso remove um fator externo para a resolução de dependência em aplicativos, tornando-a mais reproduzível.</span><span class="sxs-lookup"><span data-stu-id="77e53-174">This removes an external factor for dependency resolution in applications, making dependency resolution more reproducible.</span></span>
  <span data-ttu-id="77e53-175">O PowerShell, como o host do plug-in, torna isso um pouco mais complicado nos módulos.</span><span class="sxs-lookup"><span data-stu-id="77e53-175">PowerShell, as the plugin host, complicates this slightly for modules.</span></span> <span data-ttu-id="77e53-176">As dependências dele no `$PSHOME` são compartilhadas com todos os módulos.</span><span class="sxs-lookup"><span data-stu-id="77e53-176">Its dependencies in `$PSHOME` are shared with all modules.</span></span>
- <span data-ttu-id="77e53-177">Apenas um Domínio do Aplicativo e nenhuma capacidade de criar outros.</span><span class="sxs-lookup"><span data-stu-id="77e53-177">Only one Application Domain, and no ability to create new ones.</span></span> <span data-ttu-id="77e53-178">O conceito de Domínio do Aplicativo é mantido no .NET Core apenas para ser o estado global do processo do .NET.</span><span class="sxs-lookup"><span data-stu-id="77e53-178">The Application Domain concept is maintained in .NET Core purely to be the global state of the .NET process.</span></span>
- <span data-ttu-id="77e53-179">Um novo modelo de Contexto de Carregamento de Assembly extensível.</span><span class="sxs-lookup"><span data-stu-id="77e53-179">A new, extensible Assembly Load Context model.</span></span> <span data-ttu-id="77e53-180">A resolução de assembly pode ser armazenada em namespace colocando-a em um novo ALC.</span><span class="sxs-lookup"><span data-stu-id="77e53-180">Assembly resolution can be namespaced by putting it in a new ALC.</span></span> <span data-ttu-id="77e53-181">Os processos do .NET Core começam com um único ALC padrão no qual todos os assemblies são carregados.</span><span class="sxs-lookup"><span data-stu-id="77e53-181">.NET Core processes begin with a single default ALC into which all assemblies are loaded.</span></span> <span data-ttu-id="77e53-182">(exceto aqueles carregados com `Assembly.LoadFile(string)` e `Assembly.Load(byte[])`). Entretanto, o processo pode criar e definir os próprios ALCs personalizados com a própria lógica de carregamento.</span><span class="sxs-lookup"><span data-stu-id="77e53-182">(except for those loaded with `Assembly.LoadFile(string)` and `Assembly.Load(byte[])`) But the process can create and define its own custom ALCs with its own loading logic.</span></span> <span data-ttu-id="77e53-183">Quando um assembly for carregado, o primeiro ALC no qual ele é carregado será responsável por resolver as dependências dele.</span><span class="sxs-lookup"><span data-stu-id="77e53-183">When an assembly is loaded, the first ALC it is loaded into is responsible for resolving its dependencies.</span></span> <span data-ttu-id="77e53-184">Isso cria oportunidades para implementar mecanismos avançados de carregamento de plug-in do .NET.</span><span class="sxs-lookup"><span data-stu-id="77e53-184">This creates opportunities to implement powerful .NET plugin loading mechanisms.</span></span>

<span data-ttu-id="77e53-185">Em ambas as implementações, os assemblies são carregados lentamente.</span><span class="sxs-lookup"><span data-stu-id="77e53-185">In both implementations, assemblies are loaded lazily.</span></span> <span data-ttu-id="77e53-186">Isso significa que eles serão carregados quando um método que exige o tipo for executado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="77e53-186">This means that they are loaded when a method requiring their type is run for the first time.</span></span>

<span data-ttu-id="77e53-187">Por exemplo, a seguir estão duas versões do mesmo código que carregam uma dependência em momentos diferentes.</span><span class="sxs-lookup"><span data-stu-id="77e53-187">For example, here are two versions of the same code that load a dependency at different times.</span></span>

<span data-ttu-id="77e53-188">A primeira sempre carrega a dependência dela quando `Program.GetRange()` é chamado, porque a referência de dependência está presente em forma lexical no método:</span><span class="sxs-lookup"><span data-stu-id="77e53-188">The first always loads its dependency when `Program.GetRange()` is called, because the dependency reference is lexically present within the method:</span></span>

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetRange(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library will be loaded when GetRange is run
                // because the dependency call occurs directly within the method
                DependencyApi.Use();
            }

            list.Add(i);
        }
        return list;
    }
}
```

<span data-ttu-id="77e53-189">A segunda carregará a dependência somente se o parâmetro `limit` for 20 ou mais, devido à indireção interna por meio de um método:</span><span class="sxs-lookup"><span data-stu-id="77e53-189">The second will load its dependency only if the `limit` parameter is 20 or more, because of the internal indirection through a method:</span></span>

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetNumbers(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library is only referenced within
                // the UseDependencyApi() method,
                // so will only be loaded when limit >= 20
                UseDependencyApi();
            }

            list.Add(i);
        }
        return list;
    }

    private static void UseDependencyApi()
    {
        // Once UseDependencyApi() is called, Dependency.Library is loaded
        DependencyApi.Use();
    }
}
```

<span data-ttu-id="77e53-190">Essa é uma prática recomendada, pois minimiza a memória e a E/S do sistema de arquivos, além de usar os recursos com mais eficiência.</span><span class="sxs-lookup"><span data-stu-id="77e53-190">This is a good practice since it minimizes the memory and filesystem I/O and uses the resources more efficiently.</span></span> <span data-ttu-id="77e53-191">Um efeito colateral indesejado disso é que não sabemos se o assembly teve uma falha ao ser carregado até chegarmos ao caminho do código que tenta carregar o assembly.</span><span class="sxs-lookup"><span data-stu-id="77e53-191">The unfortunate a side effect of this is that we won't know that the assembly fails to load until we reach the code path that tries to load the assembly.</span></span>

<span data-ttu-id="77e53-192">Isso também pode criar uma condição de tempo para conflitos de carregamento de assembly.</span><span class="sxs-lookup"><span data-stu-id="77e53-192">It can also create a timing condition for assembly load conflicts.</span></span> <span data-ttu-id="77e53-193">Se duas partes do mesmo programa tentarem carregar versões diferentes do mesmo assembly, a versão carregada dependerá de qual caminho do código foi executado primeiro.</span><span class="sxs-lookup"><span data-stu-id="77e53-193">If two parts of the same program try to load different versions of the same assembly, the version loaded depends on which code path is run first.</span></span>

<span data-ttu-id="77e53-194">Para o PowerShell, isso significa que os seguintes fatores podem afetar um conflito de carregamento de assembly:</span><span class="sxs-lookup"><span data-stu-id="77e53-194">For PowerShell, this means that the following factors can affect an assembly load conflict:</span></span>

- <span data-ttu-id="77e53-195">Qual módulo foi carregado primeiro?</span><span class="sxs-lookup"><span data-stu-id="77e53-195">Which module was loaded first?</span></span>
- <span data-ttu-id="77e53-196">O caminho do código que usa a biblioteca de dependências foi executado?</span><span class="sxs-lookup"><span data-stu-id="77e53-196">Was the code path that uses the dependency library run?</span></span>
- <span data-ttu-id="77e53-197">O PowerShell carrega uma dependência conflitante na inicialização ou somente em determinados caminhos do código?</span><span class="sxs-lookup"><span data-stu-id="77e53-197">Does PowerShell load a conflicting dependency at startup or only under certain code paths?</span></span>

## <a name="quick-fixes-and-their-limitations"></a><span data-ttu-id="77e53-198">Correções rápidas e limitações</span><span class="sxs-lookup"><span data-stu-id="77e53-198">Quick fixes and their limitations</span></span>

<span data-ttu-id="77e53-199">Em alguns casos, é possível fazer pequenos ajustes no seu módulo e consertar problemas com o mínimo de esforço.</span><span class="sxs-lookup"><span data-stu-id="77e53-199">In some cases, it's possible to make small adjustments to your module and fix things with minimal effort.</span></span> <span data-ttu-id="77e53-200">Mas essas soluções tendem a surgir com ressalvas.</span><span class="sxs-lookup"><span data-stu-id="77e53-200">But these solutions tend to come with caveats.</span></span> <span data-ttu-id="77e53-201">Embora elas possam se aplicar ao seu módulo, elas não funcionam em todos os módulos.</span><span class="sxs-lookup"><span data-stu-id="77e53-201">While they may apply to your module, they won't work for every module.</span></span>

### <a name="change-your-dependency-version"></a><span data-ttu-id="77e53-202">Alterar a sua versão de dependência</span><span class="sxs-lookup"><span data-stu-id="77e53-202">Change your dependency version</span></span>

<span data-ttu-id="77e53-203">A maneira mais simples de evitar conflitos de dependência é concordar com uma dependência.</span><span class="sxs-lookup"><span data-stu-id="77e53-203">The simplest way to avoid dependency conflicts is to agree on a dependency.</span></span> <span data-ttu-id="77e53-204">Isso pode ser possível quando:</span><span class="sxs-lookup"><span data-stu-id="77e53-204">This may be possible when:</span></span>

- <span data-ttu-id="77e53-205">O seu conflito ocorre com uma dependência direta do módulo e você controla a versão.</span><span class="sxs-lookup"><span data-stu-id="77e53-205">Your conflict is with a direct dependency of your module and you control the version.</span></span>
- <span data-ttu-id="77e53-206">O seu conflito ocorre com uma dependência indireta, mas você pode configurar as dependências diretas para usar uma versão de dependência indireta viável.</span><span class="sxs-lookup"><span data-stu-id="77e53-206">Your conflict is with an indirect dependency, but you can configure your direct dependencies to use a workable indirect dependency version.</span></span>
- <span data-ttu-id="77e53-207">Você sabe a versão conflitante e pode confiar que ela não mudará.</span><span class="sxs-lookup"><span data-stu-id="77e53-207">You know the conflicting version and can rely on it not changing.</span></span>

<span data-ttu-id="77e53-208">O pacote `Newtonsoft.Json` é um bom exemplo desse último cenário.</span><span class="sxs-lookup"><span data-stu-id="77e53-208">The `Newtonsoft.Json` package is a good example of this last scenario.</span></span> <span data-ttu-id="77e53-209">Ele é uma dependência do PowerShell 6 e versões posteriores e não é usado no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77e53-209">This is a dependency of PowerShell 6 and above, and isn't used in Windows PowerShell.</span></span> <span data-ttu-id="77e53-210">Isso significa que uma forma simples de resolver conflitos de controle de versão é direcionar a versão mais antiga do `Newtonsoft.Json` nas versões do PowerShell que você deseja direcionar.</span><span class="sxs-lookup"><span data-stu-id="77e53-210">Meaning a simple way to resolve versioning conflicts is to target the lowest version of `Newtonsoft.Json` across the PowerShell versions you wish to target.</span></span>

<span data-ttu-id="77e53-211">Por exemplo, o PowerShell 6.2.6 e o PowerShell 7.0.2 atualmente usam o `Newtonsoft.Json` versão 12.0.3.</span><span class="sxs-lookup"><span data-stu-id="77e53-211">For example, PowerShell 6.2.6 and PowerShell 7.0.2 both currently use `Newtonsoft.Json` version 12.0.3.</span></span> <span data-ttu-id="77e53-212">Portanto, para criar um módulo que seja direcionado ao Windows PowerShell, ao PowerShell 6 e ao PowerShell 7, você deve direcionar `Newtonsoft.Json 12.0.3` como uma dependência e incluí-lo no seu módulo criado.</span><span class="sxs-lookup"><span data-stu-id="77e53-212">So, to create a module targeting Windows PowerShell, PowerShell 6, and PowerShell 7, you would target `Newtonsoft.Json 12.0.3` as a dependency and include it in your built module.</span></span> <span data-ttu-id="77e53-213">Quando o módulo for carregado no PowerShell 6 ou 7, o assembly `Newtonsoft.Json` próprio do PowerShell já estará carregado.</span><span class="sxs-lookup"><span data-stu-id="77e53-213">When the module is loaded in PowerShell 6 or 7, PowerShell's own `Newtonsoft.Json` assembly is already loaded.</span></span> <span data-ttu-id="77e53-214">Além disso, ele terá no mínimo a versão necessária para o seu módulo, portanto a resolução será bem sucedida.</span><span class="sxs-lookup"><span data-stu-id="77e53-214">Also, it is at least the version required for your module, so resolution succeeds.</span></span> <span data-ttu-id="77e53-215">No Windows PowerShell, o assembly ainda não está presente no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77e53-215">In Windows PowerShell, the assembly isn't already present in PowerShell.</span></span> <span data-ttu-id="77e53-216">Portanto, em vez disso, ele será carregado da sua pasta de módulo.</span><span class="sxs-lookup"><span data-stu-id="77e53-216">So, it's loaded from your module folder instead.</span></span>

<span data-ttu-id="77e53-217">Geralmente, ao direcionar um pacote do PowerShell concreto, como `Microsoft.PowerShell.Sdk` ou `System.Management.Automation`, o NuGet deve ser capaz de resolver as versões de dependência corretas necessárias.</span><span class="sxs-lookup"><span data-stu-id="77e53-217">Generally, when targeting a concrete PowerShell package, like `Microsoft.PowerShell.Sdk` or `System.Management.Automation`, NuGet should be able to resolve the right dependency versions required.</span></span> <span data-ttu-id="77e53-218">Direcionar tanto o Windows PowerShell quanto o PowerShell 6+ se torna mais difícil, pois você precisa escolher entre direcionar várias estruturas ou o `PowerShellStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="77e53-218">Targeting both Windows PowerShell and PowerShell 6+ becomes more difficult because you must choose between targeting multiple frameworks or `PowerShellStandard.Library`.</span></span>

<span data-ttu-id="77e53-219">As circunstâncias em que anexar uma versão de dependência comum não funciona incluem:</span><span class="sxs-lookup"><span data-stu-id="77e53-219">Circumstances where pinning to a common dependency version won't work include:</span></span>

- <span data-ttu-id="77e53-220">O conflito ocorre com uma dependência indireta e nenhuma das suas dependências pode ser configurada para usar uma versão comum.</span><span class="sxs-lookup"><span data-stu-id="77e53-220">The conflict is with an indirect dependency, and none of your dependencies can be configured to use a common version.</span></span>
- <span data-ttu-id="77e53-221">A outra versão de dependência provavelmente será alterada com frequência, portanto, escolher uma versão comum é apenas um conserto (fix) de curto prazo.</span><span class="sxs-lookup"><span data-stu-id="77e53-221">The other dependency version is likely to change often, so settling on a common version is only a short-term fix.</span></span>

### <a name="add-an-assemblyresolve-event-handler-to-create-a-dynamic-binding-redirect"></a><span data-ttu-id="77e53-222">Adicionar um manipulador de eventos AssemblyResolve para criar um redirecionamento de associação dinâmica</span><span class="sxs-lookup"><span data-stu-id="77e53-222">Add an AssemblyResolve event handler to create a dynamic binding redirect</span></span>

<span data-ttu-id="77e53-223">Às vezes, alterar a própria versão de dependência não é possível ou é muito difícil.</span><span class="sxs-lookup"><span data-stu-id="77e53-223">Sometimes changing your own dependency version isn't possible or is too difficult.</span></span> <span data-ttu-id="77e53-224">Outra opção é configurar um redirecionamento de associação dinâmica registrando um manipulador de eventos para o evento `AssemblyResolve`.</span><span class="sxs-lookup"><span data-stu-id="77e53-224">Another option is to set up a dynamic binding redirect by registering an event handler for the `AssemblyResolve` event.</span></span>

<span data-ttu-id="77e53-225">Assim como em um redirecionamento de associação estático, o objetivo é forçar todos os consumidores de uma dependência a usar o mesmo assembly real.</span><span class="sxs-lookup"><span data-stu-id="77e53-225">As with a static binding redirect, the point is to force all consumers of a dependency to use the same actual assembly.</span></span> <span data-ttu-id="77e53-226">Você intercepta as chamadas para carregar a dependência e sempre as redireciona para a versão desejada.</span><span class="sxs-lookup"><span data-stu-id="77e53-226">You intercept calls to load the dependency and always redirect them to the version you want.</span></span>

<span data-ttu-id="77e53-227">Você obterá algo semelhante isto:</span><span class="sxs-lookup"><span data-stu-id="77e53-227">This looks something like this:</span></span>

```csharp
// Register the event handler as early as you can in your code.
// A good option is to use the IModuleAssemblyInitializer interface
// that PowerShell provides to run code early on when your module is loaded.

// This class will be instantiated on module import and the OnImport() method run.
// Make sure that:
//  - the class is public
//  - the class has a public, parameterless constructor
//  - the class implements IModuleAssemblyInitializer
public class MyModuleInitializer : IModuleAssemblyInitializer
{
    public void OnImport()
    {
        AppDomain.CurrentDomain.AssemblyResolve += DependencyResolution.ResolveNewtonsoftJson;
    }
}

// Clean up the event handler when the the module is removed
// to prevent memory leaks.
//
// Like IModuleAssemblyInitializer, IModuleAssemblyCleanup allows
// you to register code to run when a module is removed (with Remove-Module).
// Make sure it is also public with a public parameterless contructor
// and implements IModuleAssemblyCleanup.
public class MyModuleCleanup : IModuleAssemblyCleanup
{
    public void OnRemove()
    {
        AppDomain.CurrentDomain.AssemblyResolve -= DependencyResolution.ResolveNewtonsoftJson;
    }
}

internal static class DependencyResolution
{
    private static readonly string s_modulePath = Path.GetDirectoryName(
        Assembly.GetExecutingAssembly().Location);

    public static Assembly ResolveNewtonsoftJson(object sender, ResolveEventArgs args)
    {
        // Parse the assembly name
        var assemblyName = new AssemblyName(args.Name);

        // We only want to handle the dependency we care about.
        // In this example it's Newtonsoft.Json.
        if (!assemblyName.Name.Equals("Newtonsoft.Json"))
        {
            return null;
        }

        // Generally the version of the dependency you want to load is the higher one,
        // since it's the most likely to be compatible with all dependent assemblies.
        // The logic here assumes our module always has the version we want to load.
        // Also note the use of Assembly.LoadFrom() here rather than Assembly.LoadFile().
        return Assembly.LoadFrom(Path.Combine(s_modulePath, "Newtonsoft.Json.dll"));
    }
}
```

<span data-ttu-id="77e53-228">Tecnicamente, você pode registrar um scriptblock no PowerShell para administrar um evento `AssemblyResolve`, mas:</span><span class="sxs-lookup"><span data-stu-id="77e53-228">You can technically register a scriptblock within PowerShell to handle an `AssemblyResolve` event, but:</span></span>

- <span data-ttu-id="77e53-229">Um evento `AssemblyResolve` pode ser disparado em qualquer thread. Isso é algo que o PowerShell não poderá administrar.</span><span class="sxs-lookup"><span data-stu-id="77e53-229">An `AssemblyResolve` event may be triggered on any thread, something that PowerShell will be unable to handle.</span></span>
- <span data-ttu-id="77e53-230">Mesmo quando os eventos são administrados no thread correto, os conceitos de escopo do PowerShell significam que o scriptblock do manipulador de eventos precisa ser escrito com cuidado para não depender de variáveis definidas fora dele.</span><span class="sxs-lookup"><span data-stu-id="77e53-230">Even when events are handled on the right thread, PowerShell's scoping concepts mean that the event handler scriptblock must be written carefully to not depend on variables defined outside it.</span></span>

<span data-ttu-id="77e53-231">Há situações em que o redirecionamento para uma versão comum não funcionará:</span><span class="sxs-lookup"><span data-stu-id="77e53-231">There are situations where redirecting to a common version won't work:</span></span>

- <span data-ttu-id="77e53-232">Quando a dependência fez alterações da falha entre as versões ou quando o código dependente precisa de uma funcionalidade que não está disponível na versão para a qual ela será redirecionada.</span><span class="sxs-lookup"><span data-stu-id="77e53-232">When the dependency has made breaking changes between versions, or when dependent code relies on a functionality otherwise not available in the version you redirect to.</span></span>
- <span data-ttu-id="77e53-233">Quando o seu módulo não é carregado antes da dependência conflitante.</span><span class="sxs-lookup"><span data-stu-id="77e53-233">When your module isn't loaded before the conflicting dependency.</span></span> <span data-ttu-id="77e53-234">Se você registrar um manipulador de eventos `AssemblyResolve` depois que a dependência tiver sido carregada, ela nunca será acionada.</span><span class="sxs-lookup"><span data-stu-id="77e53-234">If you register an `AssemblyResolve` event handler after the dependency has been loaded, it will never be fired.</span></span> <span data-ttu-id="77e53-235">Se você está tentando evitar conflitos de dependência com outro módulo, isso pode ser um problema, já que o outro módulo pode ser carregado primeiro.</span><span class="sxs-lookup"><span data-stu-id="77e53-235">If you're trying to prevent dependency conflicts with another module, this may be an issue, since the other module may be loaded first.</span></span>

### <a name="use-the-dependency-out-of-process"></a><span data-ttu-id="77e53-236">Usar a dependência fora do processo</span><span class="sxs-lookup"><span data-stu-id="77e53-236">Use the dependency out of process</span></span>

<span data-ttu-id="77e53-237">Essa solução é direcionada especialmente para os usuários de módulo, em vez dos autores de módulo.</span><span class="sxs-lookup"><span data-stu-id="77e53-237">This solution is more for module users than module authors.</span></span> <span data-ttu-id="77e53-238">Essa é uma solução a ser usada quando confrontada com um módulo que não funcionará devido a um conflito de dependência existente.</span><span class="sxs-lookup"><span data-stu-id="77e53-238">This is a solution to use when confronted with a module that won't work due to an existing dependency conflict.</span></span>

<span data-ttu-id="77e53-239">Os conflitos de dependência ocorrem porque duas versões do mesmo assembly são carregadas no mesmo processo do .NET.</span><span class="sxs-lookup"><span data-stu-id="77e53-239">Dependency conflicts occur because two versions of the same assembly are loaded into the same .NET process.</span></span> <span data-ttu-id="77e53-240">Uma solução simples é carregá-las em processos diferentes, desde que você ainda possa usar a funcionalidade de ambos juntos.</span><span class="sxs-lookup"><span data-stu-id="77e53-240">A simple solution is to load them into different processes, as long as you can still use the functionality from both together.</span></span>

<span data-ttu-id="77e53-241">No PowerShell, há várias maneiras de conseguir isso:</span><span class="sxs-lookup"><span data-stu-id="77e53-241">In PowerShell, there are several ways to achieve this:</span></span>

- <span data-ttu-id="77e53-242">Invocar o PowerShell como um subprocesso</span><span class="sxs-lookup"><span data-stu-id="77e53-242">Invoke PowerShell as a subprocess</span></span>

  <span data-ttu-id="77e53-243">Uma forma simples de executar um comando do PowerShell fora do processo atual é simplesmente iniciar um novo processo do PowerShell diretamente na chamada de comando:</span><span class="sxs-lookup"><span data-stu-id="77e53-243">A simple way to run a PowerShell command out of the current process is to just start a new PowerShell process directly with the command call:</span></span>

  ```powershell
  pwsh -c 'Invoke-ConflictingCommand'
  ```

  <span data-ttu-id="77e53-244">A principal limitação aqui é que a reestruturação do resultado pode ser mais complicada ou mais propensa a erros do que outras opções.</span><span class="sxs-lookup"><span data-stu-id="77e53-244">The main limitation here is that restructuring the result can be trickier or more error prone than other options.</span></span>

- <span data-ttu-id="77e53-245">O sistema de trabalho do PowerShell</span><span class="sxs-lookup"><span data-stu-id="77e53-245">The PowerShell job system</span></span>

  <span data-ttu-id="77e53-246">O sistema de trabalho do PowerShell também executa comandos fora do processo, enviando comandos para um novo processo do PowerShell e retornando os resultados:</span><span class="sxs-lookup"><span data-stu-id="77e53-246">The PowerShell job system also runs commands out of process, by sending commands to a new PowerShell process and returning the results:</span></span>

  ```powershell
  $result = Start-Job { Invoke-ConflictingCommand } | Receive-Job -Wait
  ```

  <span data-ttu-id="77e53-247">Nesse caso, você só precisa ter certeza de que todas as variáveis e estados sejam passados corretamente.</span><span class="sxs-lookup"><span data-stu-id="77e53-247">In this case, you just need to be sure that any variables and state are passed in correctly.</span></span>

  <span data-ttu-id="77e53-248">O sistema de trabalho também pode ser um pouco complicado ao executar comandos pequenos.</span><span class="sxs-lookup"><span data-stu-id="77e53-248">The job system can also be slightly cumbersome when running small commands.</span></span>

- <span data-ttu-id="77e53-249">Comunicação remota do PowerShell</span><span class="sxs-lookup"><span data-stu-id="77e53-249">PowerShell remoting</span></span>

  <span data-ttu-id="77e53-250">Quando estiver disponível, a comunicação remota do PowerShell poderá ser uma forma útil de executar comandos fora do processo.</span><span class="sxs-lookup"><span data-stu-id="77e53-250">When it's available, PowerShell remoting can be a useful way to run commands out of process.</span></span> <span data-ttu-id="77e53-251">Com a comunicação remota, você pode criar uma **PSSession** em um novo processo, chamar os comandos dela por meio da comunicação remota do PowerShell e, em seguida, usar os resultados localmente com os outros módulos que contêm as dependências conflitantes.</span><span class="sxs-lookup"><span data-stu-id="77e53-251">With remoting, you can create a fresh **PSSession** in a new process, call its commands over PowerShell remoting, then use the results locally with the other modules containing the conflicting dependencies.</span></span>

  <span data-ttu-id="77e53-252">Veja o exemplo de como seria essa aparência:</span><span class="sxs-lookup"><span data-stu-id="77e53-252">An example might look like this:</span></span>

  ```powershell
  # Create a local PowerShell session
  # where the module with conflicting assemblies will be loaded
  $s = New-PSSession

  # Import the module with the conflicting dependency via remoting,
  # exposing the commands locally
  Import-Module -PSSession $s -Name ConflictingModule

  # Run a command from the module with the conflicting dependencies
  Invoke-ConflictingCommand
  ```

- <span data-ttu-id="77e53-253">Comunicação remota implícita com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="77e53-253">Implicit remoting to Windows PowerShell</span></span>

  <span data-ttu-id="77e53-254">Outra opção no PowerShell 7 é usar o sinalizador `-UseWindowsPowerShell` no `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="77e53-254">Another option in PowerShell 7 is to use the `-UseWindowsPowerShell` flag on `Import-Module`.</span></span> <span data-ttu-id="77e53-255">Isso importará o módulo por meio de uma sessão de comunicação remota local no Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="77e53-255">This will import the module through a local remoting session into Windows PowerShell:</span></span>

  ```powershell
  Import-Module -Name ConflictingModule -UseWindowsPowerShell
  ```

  <span data-ttu-id="77e53-256">Lembre-se de que os módulos podem não funcionar com o Windows PowerShell ou funcionar de maneira diferente.</span><span class="sxs-lookup"><span data-stu-id="77e53-256">Be aware that modules may not work with, or work differently with Windows PowerShell.</span></span>

#### <a name="when-out-of-process-invocation-should-not-be-used"></a><span data-ttu-id="77e53-257">Quando a invocação fora do processo não deve ser usada</span><span class="sxs-lookup"><span data-stu-id="77e53-257">When out-of-process invocation should not be used</span></span>

<span data-ttu-id="77e53-258">Como um autor de módulo, é difícil fazer o bake de uma invocação de comando fora do processo em um módulo e alguns casos de borda podem causar problemas.</span><span class="sxs-lookup"><span data-stu-id="77e53-258">As a module author, out-of-process command invocation is difficult to bake into a module and may have edge cases that cause issues.</span></span> <span data-ttu-id="77e53-259">Em especial, a comunicação remota e os trabalhos podem não estar disponíveis em todos os ambientes nos quais o módulo precisa funcionar.</span><span class="sxs-lookup"><span data-stu-id="77e53-259">In particular, remoting and jobs may not be available in all environments where your module needs to work.</span></span> <span data-ttu-id="77e53-260">No entanto, o princípio geral de mover a implementação para fora do processo e permitir que o módulo do PowerShell seja um cliente mais fino ainda pode ser aplicável.</span><span class="sxs-lookup"><span data-stu-id="77e53-260">However, the general principle of moving the implementation out of process and allowing the PowerShell module to be a thinner client, may still be applicable.</span></span>

<span data-ttu-id="77e53-261">Como um usuário de módulo, há casos em que a invocação fora do processo não funcionará:</span><span class="sxs-lookup"><span data-stu-id="77e53-261">As a module user, there are cases where out-of-process invocation won't work:</span></span>

- <span data-ttu-id="77e53-262">Quando a comunicação remota do PowerShell estiver indisponível porque você não tem privilégios para usá-la ou ela não estiver habilitada.</span><span class="sxs-lookup"><span data-stu-id="77e53-262">When PowerShell remoting is unavailable because you don't have privileges to use it or it is not enabled.</span></span>
- <span data-ttu-id="77e53-263">Quando um tipo de .NET específico for necessário na saída como uma entrada para um método ou outro comando.</span><span class="sxs-lookup"><span data-stu-id="77e53-263">When a particular .NET type is needed from output as input to a method or another command.</span></span>
  <span data-ttu-id="77e53-264">Os comandos em execução na comunicação remota do PowerShell emitem objetos desserializados em vez de objetos .NET fortemente tipados.</span><span class="sxs-lookup"><span data-stu-id="77e53-264">Commands running over PowerShell remoting emit deserialized objects rather than strongly-typed .NET objects.</span></span> <span data-ttu-id="77e53-265">Isso significa que as chamadas de método e APIs fortemente tipadas não funcionam com a saída de comandos importados pela comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="77e53-265">This means that method calls and strongly typed APIs do not work with the output of commands imported over remoting.</span></span>

## <a name="more-robust-solutions"></a><span data-ttu-id="77e53-266">Soluções mais robustas</span><span class="sxs-lookup"><span data-stu-id="77e53-266">More robust solutions</span></span>

<span data-ttu-id="77e53-267">Todas as soluções anteriores tinham cenários e módulos que não funcionam.</span><span class="sxs-lookup"><span data-stu-id="77e53-267">The previous solutions all had scenarios and modules that don't work.</span></span> <span data-ttu-id="77e53-268">No entanto, elas também tinham a vantagem de serem relativamente simples de implementar corretamente.</span><span class="sxs-lookup"><span data-stu-id="77e53-268">However, they also have the virtue of being relatively simple to implement correctly.</span></span> <span data-ttu-id="77e53-269">As soluções a seguir são mais robustas, mas exigem mais esforço para serem implementadas corretamente e poderão causar bugs sutis se não forem escritas com cuidado.</span><span class="sxs-lookup"><span data-stu-id="77e53-269">The following solutions are more robust, but require more effort to implement correctly and can introduce subtle bugs if not written carefully.</span></span>

### <a name="loading-through-net-core-assembly-load-contexts"></a><span data-ttu-id="77e53-270">Carregamento por meio de Contextos de Carregamento de Assembly do .NET Core</span><span class="sxs-lookup"><span data-stu-id="77e53-270">Loading through .NET Core Assembly Load Contexts</span></span>

<span data-ttu-id="77e53-271">Os [ALCs](/dotnet/api/system.runtime.loader.assemblyloadcontext) (Contextos de Carregamento de Assembly) como uma API implementável foram introduzidos no .NET Core 1.0 para resolver especificamente a necessidade de carregar várias versões do mesmo assembly no mesmo runtime.</span><span class="sxs-lookup"><span data-stu-id="77e53-271">[Assembly Load Contexts](/dotnet/api/system.runtime.loader.assemblyloadcontext) (ALCs) as an implementable API were introduced in .NET Core 1.0 to specifically address the need to load multiple versions of the same assembly into the same runtime.</span></span>

<span data-ttu-id="77e53-272">No .NET Core e no .NET 5, eles oferecem a solução mais robusta para o problema de carregar versões conflitantes de um assembly.</span><span class="sxs-lookup"><span data-stu-id="77e53-272">Within .NET Core and .NET 5, they offer the most robust solution to the problem of loading conflicting versions of an assembly.</span></span> <span data-ttu-id="77e53-273">No entanto, os ALCs personalizados não estão disponíveis no .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="77e53-273">However, custom ALCs are not available in .NET Framework.</span></span> <span data-ttu-id="77e53-274">Isso significa que essa solução só funciona no PowerShell 6 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="77e53-274">This means that this solution only works in PowerShell 6 and above.</span></span>

<span data-ttu-id="77e53-275">Atualmente, o melhor exemplo de uso de um ALC para isolamento de dependência no PowerShell está nos Serviços do Editor do PowerShell, no servidor de idioma da extensão do PowerShell para Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="77e53-275">Currently, the best example of using an ALC for dependency isolation in PowerShell is in PowerShell Editor Services, the language server for the PowerShell extension for Visual Studio Code.</span></span> <span data-ttu-id="77e53-276">Um [ALC é usado](https://github.com/PowerShell/PowerShellEditorServices/blob/master/src/PowerShellEditorServices.Hosting/Internal/PsesLoadContext.cs) para impedir que as próprias dependências dos Serviços do Editor do PowerShell entrem em conflito com aquelas nos módulos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77e53-276">An [ALC is used](https://github.com/PowerShell/PowerShellEditorServices/blob/master/src/PowerShellEditorServices.Hosting/Internal/PsesLoadContext.cs) to prevent PowerShell Editor Services' own dependencies from clashing with those in PowerShell modules.</span></span>

<span data-ttu-id="77e53-277">A implementação do isolamento de dependência de módulo com um ALC é conceitualmente difícil, mas vamos trabalhar com um exemplo simples.</span><span class="sxs-lookup"><span data-stu-id="77e53-277">Implementing module dependency isolation with an ALC is conceptually difficult, but we will work through a minimal example.</span></span> <span data-ttu-id="77e53-278">Imagine que temos um módulo simples que se destina apenas a funcionar no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="77e53-278">Imagine we have a simple module that is only intended to work in PowerShell 7.</span></span>
<span data-ttu-id="77e53-279">O código-fonte é organizado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="77e53-279">The source code is organized as follows:</span></span>

```
+ AlcModule.psd1
+ src/
    + TestAlcModuleCommand.cs
    + AlcModule.csproj
```

<span data-ttu-id="77e53-280">A implementação do cmdlet se parece com esta:</span><span class="sxs-lookup"><span data-stu-id="77e53-280">The cmdlet implementation looks like this:</span></span>

```csharp
using Shared.Dependency;

namespace AlcModule
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            // Here's where our dependency gets used
            Dependency.Use();
            // Something trivial to make our cmdlet do *something*
            WriteObject("done!");
        }
    }
}
```

<span data-ttu-id="77e53-281">O manifesto (muito simplificado), tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="77e53-281">The (heavily simplified) manifest, looks like this:</span></span>

```powershell
@{
    Author = 'Me'
    ModuleVersion = '0.0.1'
    RootModule = 'AlcModule.dll'
    CmdletsToExport = @('Test-AlcModule')
    PowerShellVersion = '7.0'
}
```

<span data-ttu-id="77e53-282">E o `csproj` tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="77e53-282">And the `csproj` looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="77e53-283">Quando criamos esse módulo, a saída gerada tem o seguinte layout:</span><span class="sxs-lookup"><span data-stu-id="77e53-283">When we build this module, the generated output has the following layout:</span></span>

```
AlcModule/
  + AlcModule.psd1
  + AlcModule.dll
  + Shared.Dependency.dll
```

<span data-ttu-id="77e53-284">Neste exemplo, nosso problema está no assembly `Shared.Dependency.dll`, que é a nossa dependência conflitante imaginária.</span><span class="sxs-lookup"><span data-stu-id="77e53-284">In this example, our problem is in the `Shared.Dependency.dll` assembly, which is our imaginary conflicting dependency.</span></span> <span data-ttu-id="77e53-285">Essa é a dependência que precisamos ignorar em um ALC para que possamos usar a versão específica do módulo.</span><span class="sxs-lookup"><span data-stu-id="77e53-285">This is the dependency that we need to put behind an ALC so that we can use the module-specific version.</span></span>

<span data-ttu-id="77e53-286">Precisamos refazer a engenharia do módulo para que:</span><span class="sxs-lookup"><span data-stu-id="77e53-286">We need to re-engineer the module so that:</span></span>

- <span data-ttu-id="77e53-287">As dependências do módulo sejam carregadas apenas no nosso ALC personalizado e não no ALC do PowerShell. Portanto, não pode haver nenhum conflito.</span><span class="sxs-lookup"><span data-stu-id="77e53-287">Module dependencies are only loaded into our custom ALC, and not into PowerShell's ALC, so there can be no conflict.</span></span> <span data-ttu-id="77e53-288">Além disso, à medida que adicionamos mais dependências ao nosso projeto, não é desejável adicionar mais código continuamente para continuar carregando o trabalho.</span><span class="sxs-lookup"><span data-stu-id="77e53-288">Moreover, as we add more dependencies to our project, we don't want to continuously add more code to keep loading working.</span></span> <span data-ttu-id="77e53-289">Em vez disso, queremos uma lógica de resolução de dependência genérica e reutilizável.</span><span class="sxs-lookup"><span data-stu-id="77e53-289">Instead, we want reusable, generic dependency resolution logic.</span></span>
- <span data-ttu-id="77e53-290">Carregar o módulo ainda funciona normalmente no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77e53-290">Loading the module still works as normal in PowerShell.</span></span> <span data-ttu-id="77e53-291">Os cmdlets e outros tipos que o sistema de módulo do PowerShell precisa são definidos no ALC do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77e53-291">Cmdlets and other types that the PowerShell module system needs are defined within PowerShell's own ALC.</span></span>

<span data-ttu-id="77e53-292">Para mediar esses dois requisitos, precisamos dividir nosso módulo em dois assemblies:</span><span class="sxs-lookup"><span data-stu-id="77e53-292">To mediate these two requirements, we must break up our module into two assemblies:</span></span>

- <span data-ttu-id="77e53-293">Um assembly de cmdlets, `AlcModule.Cmdlets.dll`, que contém definições de todos os tipos que o sistema de módulo do PowerShell precisa para carregar o nosso módulo corretamente.</span><span class="sxs-lookup"><span data-stu-id="77e53-293">A cmdlets assembly, `AlcModule.Cmdlets.dll`, that contains definitions of all the types that PowerShell's module system needs to load our module correctly.</span></span> <span data-ttu-id="77e53-294">Ou seja, todas as implementações da classe base `Cmdlet` e da classe que implementa `IModuleAssemblyInitializer`, que configuram o manipulador de eventos do `AssemblyLoadContext.Default.Resolving` para carregar corretamente o `AlcModule.Engine.dll` por meio de nosso ALC personalizado.</span><span class="sxs-lookup"><span data-stu-id="77e53-294">Namely, any implementations of the `Cmdlet` base class and the class that implements `IModuleAssemblyInitializer`, which sets up the event handler for `AssemblyLoadContext.Default.Resolving` to properly load `AlcModule.Engine.dll` through our custom ALC.</span></span> <span data-ttu-id="77e53-295">Como o PowerShell 7 oculta deliberadamente os tipos definidos em assemblies carregados em outros ALCs, todos os tipos que devem ser expostos publicamente no PowerShell também precisam ser definidos aqui.</span><span class="sxs-lookup"><span data-stu-id="77e53-295">Since PowerShell 7 deliberately hides types defined in assemblies loaded in other ALCs, any types that are meant to be publicly exposed to PowerShell must also be defined here.</span></span> <span data-ttu-id="77e53-296">Por fim, a nossa definição de ALC personalizada precisa ser definida nesse assembly.</span><span class="sxs-lookup"><span data-stu-id="77e53-296">Finally, our custom ALC definition needs to be defined in this assembly.</span></span> <span data-ttu-id="77e53-297">Além disso, o mínimo de código possível deve residir nesse assembly.</span><span class="sxs-lookup"><span data-stu-id="77e53-297">Beyond that, as little code as possible should live in this assembly.</span></span>
- <span data-ttu-id="77e53-298">Um assembly de mecanismo, `AlcModule.Engine.dll`, que administra a implementação real do módulo.</span><span class="sxs-lookup"><span data-stu-id="77e53-298">An engine assembly, `AlcModule.Engine.dll`, that handles the actual implementation of the module.</span></span>
  <span data-ttu-id="77e53-299">Os tipos dele estão disponíveis no ALC do PowerShell, mas inicialmente serão carregados por meio do nosso ALC personalizado.</span><span class="sxs-lookup"><span data-stu-id="77e53-299">Types from this are available in the PowerShell ALC, but it will initially be loaded through our custom ALC.</span></span> <span data-ttu-id="77e53-300">As dependências são carregadas somente no ALC personalizado.</span><span class="sxs-lookup"><span data-stu-id="77e53-300">Its dependencies are only loaded into the custom ALC.</span></span> <span data-ttu-id="77e53-301">Na prática, isso se torna uma _ponte_ entre os dois ALCs.</span><span class="sxs-lookup"><span data-stu-id="77e53-301">Effectively, this becomes a _bridge_ between the two ALCs.</span></span>

<span data-ttu-id="77e53-302">Usando esse conceito de ponte, a nossa nova situação de assembly tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="77e53-302">Using this bridge concept, our new assembly situation looks like this:</span></span>

![Diagrama que representa o AlcModule.Engine.dll realizando a ponte entre os dois ALCs](./media/resolving-dependency-conflicts/alc-diagram.jpg)

<span data-ttu-id="77e53-304">Para garantir que a lógica de investigação de dependência do ALC padrão não resolva as dependências a serem carregadas no ALC personalizado, precisamos separar essas duas partes do módulo em diretórios diferentes.</span><span class="sxs-lookup"><span data-stu-id="77e53-304">To make sure the default ALC's dependency probing logic does not resolve the dependencies to be loaded into the custom ALC, we need to separate these two parts of the module in different directories.</span></span> <span data-ttu-id="77e53-305">O novo layout de módulo tem a seguinte estrutura:</span><span class="sxs-lookup"><span data-stu-id="77e53-305">The new module layout has the following structure:</span></span>

```
AlcModule/
  AlcModule.Cmdlets.dll
  AlcModule.psd1
  Dependencies/
  | + AlcModule.Engine.dll
  | + Shared.Dependency.dll
```

<span data-ttu-id="77e53-306">Para ver como a implementação muda, começaremos com a implementação do `AlcModule.Engine.dll`:</span><span class="sxs-lookup"><span data-stu-id="77e53-306">To see how the implementation changes, we'll start with the implementation of `AlcModule.Engine.dll`:</span></span>

```csharp
using Shared.Dependency;

namespace AlcModule.Engine
{
    public class AlcEngine
    {
        public static void Use()
        {
            Dependency.Use();
        }
    }
}
```

<span data-ttu-id="77e53-307">Esse é um contêiner simples da dependência, `Shared.Dependency.dll`, mas você deve considerá-lo como a API do .NET da sua funcionalidade que os cmdlets no outro assembly encapsulam para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77e53-307">This is a simple container for the dependency, `Shared.Dependency.dll`, but you should think of it as the .NET API for your functionality that the cmdlets in the other assembly wrap for PowerShell.</span></span>

<span data-ttu-id="77e53-308">O cmdlet em `AlcModule.Cmdlets.dll` tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="77e53-308">The cmdlet in `AlcModule.Cmdlets.dll` looks like this:</span></span>

```csharp
// Reference our module's Engine implementation here
using AlcModule.Engine;

namespace AlcModule.Cmdlets
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            AlcEngine.Use();
            WriteObject("done!");
        }
    }
}
```

<span data-ttu-id="77e53-309">Neste ponto, se carregássemos o **AlcModule** e executássemos o `Test-AlcModule`, obteríamos um `FileNotFoundException` quando o ALC padrão tentasse carregar o `Alc.Engine.dll` para executar o `EndProcessing()`.</span><span class="sxs-lookup"><span data-stu-id="77e53-309">At this point, if we were to load **AlcModule** and run `Test-AlcModule`, we get a `FileNotFoundException` when the default ALC tries to load `Alc.Engine.dll` to run `EndProcessing()`.</span></span> <span data-ttu-id="77e53-310">Isso é bom, pois significa que o ALC padrão não conseguiu localizar as dependências que queríamos ocultar.</span><span class="sxs-lookup"><span data-stu-id="77e53-310">This is good, since it means the default ALC can't find the dependencies we want to hide.</span></span>

<span data-ttu-id="77e53-311">Agora, precisamos adicionar o código ao `AlcModule.Cmdlets.dll` para que ele saiba como resolver o `AlcModule.Engine.dll`.</span><span class="sxs-lookup"><span data-stu-id="77e53-311">Now we need to add code to `AlcModule.Cmdlets.dll` so that it knows how to resolve `AlcModule.Engine.dll`.</span></span> <span data-ttu-id="77e53-312">Primeiro, precisamos definir nosso ALC personalizado que resolverá assemblies do diretório `Dependencies` do módulo:</span><span class="sxs-lookup"><span data-stu-id="77e53-312">First we must define our custom ALC that will resolve assemblies from our module's `Dependencies` directory:</span></span>

```csharp
namespace AlcModule.Cmdlets
{
    internal class AlcModuleAssemblyLoadContext : AssemblyLoadContext
    {
        private readonly string _dependencyDirPath;

        public AlcModuleAssemblyLoadContext(string dependencyDirPath)
        {
            _depdendencyDirPath = dependencyDirPath;
        }

        protected override Assembly Load(AssemblyName assemblyName)
        {
            // We do the simple logic here of
            // looking for an assembly of the given name
            // in the configured dependency directory
            string assemblyPath = Path.Combine(
                s_dependencyDirPath,
                $"{assemblyName.Name}.dll");

            // The ALC must use inherited methods to load assemblies
            // Assembly.Load*() won't work here
            return LoadFromAssemblyPath(assemblyPath);
        }
    }
}
```

<span data-ttu-id="77e53-313">Em seguida, precisamos conectar o ALC personalizado ao evento `Resolving` do ALC padrão, que é a versão do ALC do evento `AssemblyResolve` nos Domínios do Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="77e53-313">Then we need to hook up our custom ALC to the default ALC's `Resolving` event, which is the ALC version of the `AssemblyResolve` event on Application Domains.</span></span> <span data-ttu-id="77e53-314">Esse evento será acionado para localizar o `AlcModule.Engine.dll` quando o `EndProcessing()` for chamado.</span><span class="sxs-lookup"><span data-stu-id="77e53-314">This event is fired to find `AlcModule.Engine.dll` when `EndProcessing()` is called.</span></span>

```csharp
namespace AlcModule.Cmdlets
{
    public class AlcModuleResolveEventHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // Get the path of the dependency directory.
        // In this case we find it relative to the AlcModule.Cmdlets.dll location
        private static readonly string s_dependencyDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        private static readonly AlcModuleAssemblyLoadContext s_dependencyAlc = new AlcModuleAssemblyLoadContext(s_dependencyDirPath);

        public void OnImport()
        {
            // Add the Resolving event handler here
            AssemblyLoadContext.Default.Resolving += ResolveAlcEngine;
        }

        public void OnRemove()
        {
          // Remove the Resolving event handler here
          AssemblyLoadContext.Default.Resolving -= ResolveAlcEngine;
        }

        private static Assembly ResolveAlcEngine(
            AssemblyLoadContext defaultAlc,
            AssemblyName assemblyToResolve)
        {
            // We only want to resolve the Alc.Engine.dll assembly here.
            // Because this will be loaded into the custom ALC,
            // all of *its* dependencies will be resolved
            // by the logic we defined for that ALC's implementation.
            //
            // Note that we are safe in our assumption that the name is enough
            // to distinguish our assembly here,
            // since it's unique to our module.
            // There should be no other AlcModule.Engine.dll on the system.
            if (!assemblyToResolve.Name.Equals("AlcModule.Engine"))
            {
                return null;
            }

            // Allow our ALC to handle the directory discovery concept
            //
            // This is where Alc.Engine.dll is loaded into our custom ALC
            // and then passed through into PowerShell's ALC,
            // becoming the bridge between both
            return s_dependencyAlc.LoadFromAssemblyName(assemblyToResolve);
        }
    }
}
```

<span data-ttu-id="77e53-315">Com a nova implementação, dê uma olhada na sequência de chamadas que ocorre quando o módulo é carregado e o `Test-AlcModule` é executado:</span><span class="sxs-lookup"><span data-stu-id="77e53-315">With the new implementation, take a look at the sequence of calls that occurs when the module is loaded and `Test-AlcModule` is run:</span></span>

![Diagrama da sequência de chamadas usando o ALC personalizado para carregar dependências](./media/resolving-dependency-conflicts/alc-sequence.png)

<span data-ttu-id="77e53-317">Alguns pontos de interesse são:</span><span class="sxs-lookup"><span data-stu-id="77e53-317">Some points of interest are:</span></span>

- <span data-ttu-id="77e53-318">O `IModuleAssemblyInitializer` é executado primeiro quando o módulo é carregado e configura o evento `Resolving`.</span><span class="sxs-lookup"><span data-stu-id="77e53-318">The `IModuleAssemblyInitializer` is run first when the module loads and sets the `Resolving` event.</span></span>
- <span data-ttu-id="77e53-319">Nós não carregamos as dependências até que `Test-AlcModule` seja executado e o método `EndProcessing()` seja chamado.</span><span class="sxs-lookup"><span data-stu-id="77e53-319">We don't load the dependencies until `Test-AlcModule` is run and its `EndProcessing()` method is called.</span></span>
- <span data-ttu-id="77e53-320">Quando `EndProcessing()` é chamado, o ALC padrão falha ao localizar `AlcModule.Engine.dll` e aciona o evento `Resolving`.</span><span class="sxs-lookup"><span data-stu-id="77e53-320">When `EndProcessing()` is called, the default ALC fails to find `AlcModule.Engine.dll` and fires the `Resolving` event.</span></span>
- <span data-ttu-id="77e53-321">Nosso manipulador de eventos conecta o ALC personalizado ao ALC padrão e carrega somente o `AlcModule.Engine.dll`.</span><span class="sxs-lookup"><span data-stu-id="77e53-321">Our event handler hooks up the custom ALC to the default ALC and loads `AlcModule.Engine.dll` only.</span></span>
- <span data-ttu-id="77e53-322">Quando o `AlcEngine.Use()` é chamado no `AlcModule.Engine.dll`, o ALC personalizado é ativado novamente para resolver o `Shared.Dependency.dll`.</span><span class="sxs-lookup"><span data-stu-id="77e53-322">When `AlcEngine.Use()` is called within `AlcModule.Engine.dll`, the custom ALC again kicks in to resolve `Shared.Dependency.dll`.</span></span> <span data-ttu-id="77e53-323">Especificamente, ele sempre carrega o _nosso_ `Shared.Dependency.dll`, já que nunca entra em conflito com nada no ALC padrão e só procura no diretório `Dependencies`.</span><span class="sxs-lookup"><span data-stu-id="77e53-323">Specifically, it always loads _our_ `Shared.Dependency.dll` since it never conflicts with anything in the default ALC and only looks in our `Dependencies` directory.</span></span>

<span data-ttu-id="77e53-324">Ao montar a implementação, nosso novo layout de código-fonte tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="77e53-324">Assembling the implementation, our new source code layout looks like this:</span></span>

```
+ AlcModule.psd1
+ src/
  + AlcModule.Cmdlets/
  | + AlcModule.Cmdlets.csproj
  | + TestAlcModuleCommand.cs
  | + AlcModuleAssemblyLoadContext.cs
  | + AlcModuleInitializer.cs
  |
  + AlcModule.Engine/
  | + AlcModule.Engine.csproj
  | + AlcEngine.cs
```

<span data-ttu-id="77e53-325">O AlcModule.Cmdlets.csproj tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="77e53-325">AlcModule.Cmdlets.csproj looks like:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <ProjectReference Include="..\AlcModule.Engine\AlcModule.Engine.csproj" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="77e53-326">O AlcModule.Engine.csproj tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="77e53-326">AlcModule.Engine.csproj looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="77e53-327">Então, quando criamos o módulo, nossa estratégia é:</span><span class="sxs-lookup"><span data-stu-id="77e53-327">So, when we build the module, our strategy is:</span></span>

- <span data-ttu-id="77e53-328">Criar `AlcModule.Engine`</span><span class="sxs-lookup"><span data-stu-id="77e53-328">Build `AlcModule.Engine`</span></span>
- <span data-ttu-id="77e53-329">Criar `AlcModule.Cmdlets`</span><span class="sxs-lookup"><span data-stu-id="77e53-329">Build `AlcModule.Cmdlets`</span></span>
- <span data-ttu-id="77e53-330">Copiar tudo de `AlcModule.Engine` para o diretório `Dependencies` e lembrar-se do que foi copiado</span><span class="sxs-lookup"><span data-stu-id="77e53-330">Copy everything from `AlcModule.Engine` into the `Dependencies` directory, and remember what we copied</span></span>
- <span data-ttu-id="77e53-331">Copiar tudo de `AlcModule.Cmdlets` que não estava em `AlcModule.Engine` no diretório do módulo base</span><span class="sxs-lookup"><span data-stu-id="77e53-331">Copy everything from `AlcModule.Cmdlets` that wasn't in `AlcModule.Engine` into the base module directory</span></span>

<span data-ttu-id="77e53-332">Como aqui o layout do módulo é crucial para a separação de dependência, veja o seguinte script de build a ser usado na raiz de origem:</span><span class="sxs-lookup"><span data-stu-id="77e53-332">Since the module layout here is so crucial to dependency separation, here's a build script to use from the source root:</span></span>

```powershell
param(
    # The .NET build configuration
    [ValidateSet('Debug', 'Release')]
    [string]
    $Configuration = 'Debug'
)

# Convenient reusable constants
$mod = "AlcModule"
$netcore = "netcoreapp3.1"
$copyExtensions = @('.dll', '.pdb')

# Source code locations
$src = "$PSScriptRoot/src"
$engineSrc = "$src/$mod.Engine"
$cmdletsSrc = "$src/$mod.Cmdlets"

# Generated output locations
$outDir = "$PSScriptRoot/out/$mod"
$outDeps = "$outDir/Dependencies"

# Build AlcModule.Engine
Push-Location $engineSrc
dotnet publish -c $Configuration
Pop-Location

# Build AlcModule.Cmdlets
Push-Location $cmdletsSrc
dotnet publish -c $Configuration
Pop-Location

# Ensure out directory exists and is clean
Remove-Item -Path $outDir -Recurse -ErrorAction Ignore
New-Item -Path $outDir -ItemType Directory
New-Item -Path $outDeps -ItemType Directory

# Copy manifest
Copy-Item -Path "$PSScriptRoot/$mod.psd1"

# Copy each Engine asset and remember it
$deps = [System.Collections.Generic.Hashtable[string]]::new()
Get-ChildItem -Path "$engineSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { $_.Extension -in $copyExtensions } |
    ForEach-Object { [void]$deps.Add($_.Name); Copy-Item -Path $_.FullName -Destination $outDeps }

# Now copy each Cmdlets asset, not taking any found in Engine
Get-ChildItem -Path "$cmdletsSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { -not $deps.Contains($_.Name) -and $_.Extension -in $copyExtensions } |
    ForEach-Object { Copy-Item -Path $_.FullName -Destination $outDir }
```

<span data-ttu-id="77e53-333">Por fim, temos uma forma geral de usar um Contexto de Carregamento de Assembly para isolar as dependências do módulo que permanecem robustas ao longo do tempo à medida que mais dependências são adicionadas.</span><span class="sxs-lookup"><span data-stu-id="77e53-333">Finally, we have a general way to use an Assembly Load Context to isolate our module's dependencies that remains robust over time as more dependencies are added.</span></span>

<span data-ttu-id="77e53-334">Para obter um exemplo mais detalhado, acesse este [repositório GitHub](https://github.com/rjmholt/ModuleDependencyIsolationExample).</span><span class="sxs-lookup"><span data-stu-id="77e53-334">For a more detailed example, go to this [GitHub repository](https://github.com/rjmholt/ModuleDependencyIsolationExample).</span></span> <span data-ttu-id="77e53-335">Esse exemplo demonstra como migrar um módulo para usar um ALC e ao mesmo tempo manter o módulo funcionando no .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="77e53-335">This example demonstrates how to migrate a module to use an ALC, while keeping that module working in .NET Framework.</span></span> <span data-ttu-id="77e53-336">Ele também mostra como usar o .NET Standard e o PowerShell Standard para simplificar a implementação principal.</span><span class="sxs-lookup"><span data-stu-id="77e53-336">It also show how to use .NET Standard and PowerShell Standard to simplify the core implementation.</span></span>

### <a name="assembly-resolve-handler-for-side-by-side-loading-with-assemblyloadfile"></a><span data-ttu-id="77e53-337">Manipulador de resolução de assembly para carregamento lado a lado com `Assembly.LoadFile()`</span><span class="sxs-lookup"><span data-stu-id="77e53-337">Assembly resolve handler for side-by-side loading with `Assembly.LoadFile()`</span></span>

<span data-ttu-id="77e53-338">Outra maneira, possivelmente mais simples, de obter o carregamento lado a lado do assembly é vincular um evento `AssemblyResolve` a `Assembly.LoadFile()`.</span><span class="sxs-lookup"><span data-stu-id="77e53-338">Another, possibly simpler, way to achieve side-by-side assembly loading is to hook up an `AssemblyResolve` event to `Assembly.LoadFile()`.</span></span> <span data-ttu-id="77e53-339">O uso de `Assembly.LoadFile()` tem a vantagem de ser a solução mais simples de implementar, além de funcionar com o .NET Core e o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="77e53-339">Using `Assembly.LoadFile()` has the advantage of being the simplest solution to implement and works with both .NET Core and .NET Framework.</span></span>

<span data-ttu-id="77e53-340">Para mostrar isso, vamos dar uma olhada em um exemplo rápido de uma implementação que combina ideias do exemplo de redirecionamento de associação dinâmica e do exemplo de Contexto de Carregamento de Assembly acima.</span><span class="sxs-lookup"><span data-stu-id="77e53-340">To show this, let's take a look at a quick example of an implementation that combines ideas from our dynamic binding redirect example, and the Assembly Load Context example above.</span></span>

<span data-ttu-id="77e53-341">Chamaremos esse módulo de **LoadFileModule**, que tem um comando trivial `Test-LoadFile [-Path] <path>`.</span><span class="sxs-lookup"><span data-stu-id="77e53-341">We'll call this module **LoadFileModule**, which has a trivial command `Test-LoadFile [-Path] <path>`.</span></span> <span data-ttu-id="77e53-342">Esse módulo usa uma dependência no assembly `CsvHelper` (versão 15.0.5).</span><span class="sxs-lookup"><span data-stu-id="77e53-342">This module takes a dependency on the `CsvHelper` assembly (version 15.0.5).</span></span>

<span data-ttu-id="77e53-343">Assim como no módulo do ALC, precisamos primeiro dividir o módulo em duas partes.</span><span class="sxs-lookup"><span data-stu-id="77e53-343">As with the ALC module, we must first split up the module into two pieces.</span></span>

<span data-ttu-id="77e53-344">A primeira parte faz a implementação real, `LoadFileModule.Engine`:</span><span class="sxs-lookup"><span data-stu-id="77e53-344">The first part does the actual implementation, `LoadFileModule.Engine`:</span></span>

```csharp
using CsvHelper;

namespace LoadFileModule.Engine
{
    public class Runner
    {
        public void Use(string path)
        {
            // Here's where we use the CsvHelper dependency
            using (var reader = new StreamReader(path))
            using (var csvReader = new CsvReader(reader, CultureInfo.InvariantCulture))
            {
                // Imagine we do something useful here...
            }
        }
    }
}
```

<span data-ttu-id="77e53-345">A segunda parte é a que o PowerShell carrega diretamente, `LoadFileModule.Cmdlets`.</span><span class="sxs-lookup"><span data-stu-id="77e53-345">The second part is what PowerShell loads directly, `LoadFileModule.Cmdlets`.</span></span> <span data-ttu-id="77e53-346">Usamos uma estratégia semelhante ao módulo do ALC, na qual isolamos as dependências em um diretório separado.</span><span class="sxs-lookup"><span data-stu-id="77e53-346">We use a strategy similar to the ALC module, where we isolate dependencies in a separate directory.</span></span> <span data-ttu-id="77e53-347">Mas, desta vez, carregamos todos os assemblies com um evento de resolução, em vez de apenas com o `LoadFileModule.Engine.dll`.</span><span class="sxs-lookup"><span data-stu-id="77e53-347">But this time, we load all assemblies in with a resolve event rather than just `LoadFileModule.Engine.dll`.</span></span>

```csharp
using LoadFileModule.Engine;

namespace LoadFileModule.Cmdlets
{
    // Actual cmdlet definition
    [Cmdlet(VerbsDiagnostic.Test, "LoadFile")]
    public class TestLoadFileCommand : Cmdlet
    {
        [Parameter(Mandatory = true)]
        public string Path { get; set; }

        protected override void EndProcessing()
        {
            // Here's where we use LoadFileModule.Engine
            new Runner().Use(Path);
        }
    }

    // This class controls our dependency resolution
    public class ModuleContextHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // We catalog our dependencies here to ensure we don't load anything else
        private static IReadOnlyDictionary<string, int> s_dependencies = new Dictionary<string, int>
        {
            { "CsvHelper", 15 },
        };

        // Set up the path to our dependency directory within the module
        private static string s_dependenciesDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        // This makes sure we only try to resolve dependencies when the module is loaded
        private static bool s_engineLoaded = false;

        public void OnImport()
          {
            // Set up our event when the module is loaded
            AppDomain.CurrentDomain.AssemblyResolve += HandleResolveEvent;
        }

        public void OnRemove(PSModuleInfo psModuleInfo)
        {
            // Unset the event when the module is unloaded
            AppDomain.CurrentDomain.AssemblyResolve -= HandleResolveEvent;
        }

        private static Assembly HandleResolveEvent(object sender, ResolveEventArgs args)
        {
            var asmName = new AssemblyName(args.Name);

            // First we want to know if this is the top-level assembly
            if (asmName.Name.Equals("LoadFileModule.Engine"))
            {
                s_engineLoaded = true;
                return Assembly.LoadFile(Path.Combine(s_dependenciesDirPath, "Unrelated.Engine.dll"));
            }

            // Otherwise, if that assembly has been loaded, we must try to resolve its dependencies too
            if (s_engineLoaded
                && s_dependencies.TryGetValue(asmName.Name, out int requiredMajorVersion)
                && asmName.Version.Major == requiredMajorVersion)
            {
                string asmPath = Path.Combine(s_dependenciesDirPath, $"{asmName.Name}.dll");
                return Assembly.LoadFile(asmPath);
            }

            return null;
        }
    }
}
```

<span data-ttu-id="77e53-348">Por fim, o layout do módulo também é semelhante ao módulo do ALC:</span><span class="sxs-lookup"><span data-stu-id="77e53-348">Finally, the layout of the module is also similar to the ALC module:</span></span>

```
LoadFileModule/
  + LoadFileModule.Cmdlets.dll
  + LoadFileModule.psd1
  + Dependencies/
  |  + LoadFileModule.Engine.dll
  |  + CsvHelper.dll
```

<span data-ttu-id="77e53-349">Com essa estrutura em vigor, o **LoadFileModule** agora dá suporte ao carregamento com outros módulos com uma dependência no **CsvHelper**.</span><span class="sxs-lookup"><span data-stu-id="77e53-349">With this structure in place, **LoadFileModule** now supports being loaded alongside other modules with a dependency on **CsvHelper**.</span></span>

<span data-ttu-id="77e53-350">Como o nosso manipulador se aplica a **todos** os eventos `AssemblyResolve` no Domínio do Aplicativo, precisamos fazer algumas escolhas de design específicas aqui:</span><span class="sxs-lookup"><span data-stu-id="77e53-350">Because our handler applies to **all** `AssemblyResolve` events across the Application Domain, we need to make some specific design choices here:</span></span>

- <span data-ttu-id="77e53-351">Para restringir a janela na qual o nosso evento pode interferir com outro carregamento, começamos a tratar o carregamento de dependência geral apenas depois que `LoadFileModule.Engine.dll` foi carregado.</span><span class="sxs-lookup"><span data-stu-id="77e53-351">To narrow the window in which our event may interfere with other loading, we only start handling general dependency loading after `LoadFileModule.Engine.dll` has been loaded.</span></span>
- <span data-ttu-id="77e53-352">Enviamos por push o `LoadFileModule.Engine.dll` para o diretório Dependencies, para que ele seja carregado por uma chamada `LoadFile()` em vez de pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77e53-352">We push `LoadFileModule.Engine.dll` out into the Dependencies directory, so that it's loaded by a `LoadFile()` call rather than by PowerShell.</span></span> <span data-ttu-id="77e53-353">Isso significa que as próprias cargas de dependência sempre acionarão um evento `AssemblyResolve`, mesmo se outro `CsvHelper.dll` (por exemplo) for carregado no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77e53-353">This means its own dependency loads always raise an `AssemblyResolve` event, even if another `CsvHelper.dll` (for example) is loaded in PowerShell.</span></span>
  <span data-ttu-id="77e53-354">Isso nos dá a oportunidade de encontrar a dependência correta.</span><span class="sxs-lookup"><span data-stu-id="77e53-354">This gives us the opportunity to find the correct dependency.</span></span>
- <span data-ttu-id="77e53-355">Como só precisamos resolver as dependências específicas do nosso módulo, somos forçados a codificar um dicionário de nomes e versões de dependência no nosso manipulador.</span><span class="sxs-lookup"><span data-stu-id="77e53-355">Since we must only resolve the specific dependencies for our module, we're forced to code a dictionary of dependency names and versions into our handler.</span></span> <span data-ttu-id="77e53-356">No nosso caso específico, seria possível usar a propriedade `ResolveEventArgs.RequestingAssembly` para descobrir se `CsvHelper` está sendo solicitado pelo nosso módulo.</span><span class="sxs-lookup"><span data-stu-id="77e53-356">In our particular case, it would be possible to use the `ResolveEventArgs.RequestingAssembly` property to work out whether `CsvHelper` is being requested by our module.</span></span> <span data-ttu-id="77e53-357">Mas isso não funcionará para dependências de dependências; por exemplo, se o próprio `CsvHelper` tiver gerado um evento `AssemblyResolve`.</span><span class="sxs-lookup"><span data-stu-id="77e53-357">But this doesn't work for dependencies of dependencies; for example, if `CsvHelper` itself raised an `AssemblyResolve` event.</span></span> <span data-ttu-id="77e53-358">Há outras maneiras mais difíceis de fazer isso, como comparar assemblies solicitados aos metadados de assemblies no diretório `Dependencies`.</span><span class="sxs-lookup"><span data-stu-id="77e53-358">There are other, harder ways to do this, such as comparing requested assemblies to the metadata of assemblies in the `Dependencies` directory.</span></span> <span data-ttu-id="77e53-359">Mas, neste exemplo, fizemos essa verificação mais explícita para realçar o problema e simplificar o exemplo.</span><span class="sxs-lookup"><span data-stu-id="77e53-359">But, in this example, we've made this checking more explicit to both highlight the issue and simplify the example.</span></span>

<span data-ttu-id="77e53-360">Essa é a principal diferença entre a estratégia de `LoadFile()` e a estratégia de ALC: o evento `AssemblyResolve` precisa atender a todas as cargas no Domínio do Aplicativo, fazendo com que seja muito mais difícil evitar que a nossa resolução de dependência seja agrupada com outros módulos.</span><span class="sxs-lookup"><span data-stu-id="77e53-360">This is the key difference between the `LoadFile()` strategy and the ALC strategy: the `AssemblyResolve` event must service all loads in the Application Domain, making it much harder to keep our dependency resolution from being tangled with other modules.</span></span> <span data-ttu-id="77e53-361">No entanto, a falta de ALCs no .NET Framework faz com que valha a pena entender essa opção.</span><span class="sxs-lookup"><span data-stu-id="77e53-361">However, the lack of ALCs in .NET Framework makes this option worth understanding.</span></span>

### <a name="custom-application-domains"></a><span data-ttu-id="77e53-362">Domínios do Aplicativo personalizados</span><span class="sxs-lookup"><span data-stu-id="77e53-362">Custom Application Domains</span></span>

<span data-ttu-id="77e53-363">A opção final e mais extrema para o isolamento de assembly é usar Domínios do Aplicativo personalizados.</span><span class="sxs-lookup"><span data-stu-id="77e53-363">The final and most extreme option for assembly isolation is to use custom Application Domains.</span></span>
<span data-ttu-id="77e53-364">Os Domínios do Aplicativo (usados no plural) só estão disponíveis no .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="77e53-364">Application Domains (used in the plural) are only available in .NET Framework.</span></span> <span data-ttu-id="77e53-365">Eles são usados para fornecer isolamento em processo entre as partes de um aplicativo .NET.</span><span class="sxs-lookup"><span data-stu-id="77e53-365">They are used to provide in-process isolation between parts of a .NET application.</span></span> <span data-ttu-id="77e53-366">Um dos usos é isolar as cargas de assembly umas das outras no mesmo processo.</span><span class="sxs-lookup"><span data-stu-id="77e53-366">One of the uses is to isolate assembly loads from each other within the same process.</span></span>

<span data-ttu-id="77e53-367">No entanto, os Domínios do Aplicativo são limites de serialização.</span><span class="sxs-lookup"><span data-stu-id="77e53-367">However, Application Domains are serialization boundaries.</span></span> <span data-ttu-id="77e53-368">Os objetos em um Domínio do Aplicativo não podem ser referenciados e usados diretamente por objetos em outro Domínio do Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="77e53-368">Objects in one Application Domain can't be referenced and used directly by objects in another Application Domain.</span></span> <span data-ttu-id="77e53-369">Você pode contornar esse problema implementando `MarshalByRefObject`.</span><span class="sxs-lookup"><span data-stu-id="77e53-369">You can work around this by implementing `MarshalByRefObject`.</span></span> <span data-ttu-id="77e53-370">Mas quando você não controla os tipos, como costuma ser o caso com dependências, não é possível forçar uma implementação aqui.</span><span class="sxs-lookup"><span data-stu-id="77e53-370">But when you don't control the types, as is often the case with dependencies, it's not possible to force an implementation here.</span></span> <span data-ttu-id="77e53-371">A única solução é fazer grandes alterações na arquitetura.</span><span class="sxs-lookup"><span data-stu-id="77e53-371">The only solution is to make large architectural changes.</span></span> <span data-ttu-id="77e53-372">O limite de serialização também tem sérias implicações para o desempenho.</span><span class="sxs-lookup"><span data-stu-id="77e53-372">The serialization boundary also has serious performance implications.</span></span>

<span data-ttu-id="77e53-373">Como os Domínios do Aplicativo têm essa limitação séria (são difíceis de implementar e só funcionam no .NET Framework) não daremos um exemplo de como usá-los aqui.</span><span class="sxs-lookup"><span data-stu-id="77e53-373">Because Application Domains have this serious limitation, are complicated to implement, and only work in .NET Framework, we won't give an example of how you might use them here.</span></span> <span data-ttu-id="77e53-374">Embora é válido mencioná-los como uma possibilidade, eles não são recomendados.</span><span class="sxs-lookup"><span data-stu-id="77e53-374">While they're worth mentioning as a possibility, they're not recommended.</span></span>

<span data-ttu-id="77e53-375">Se você está interessado em tentar usar um Domínio do Aplicativo personalizado, os seguintes links podem ser úteis:</span><span class="sxs-lookup"><span data-stu-id="77e53-375">If you're interested in trying to use a custom Application Domain, the following links might help:</span></span>

- [<span data-ttu-id="77e53-376">Documentação conceitual sobre os Domínios do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="77e53-376">Conceptual documentation on Application Domains</span></span>](/dotnet/framework/app-domains/application-domains)
- [<span data-ttu-id="77e53-377">Exemplos de uso dos Domínios do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="77e53-377">Examples for using Application Domains</span></span>](/dotnet/framework/app-domains/use)

## <a name="solutions-for-dependency-conflicts-that-dont-work-for-powershell"></a><span data-ttu-id="77e53-378">Soluções para conflitos de dependência que não funcionam para o PowerShell</span><span class="sxs-lookup"><span data-stu-id="77e53-378">Solutions for dependency conflicts that don't work for PowerShell</span></span>

<span data-ttu-id="77e53-379">Por fim, abordaremos algumas possibilidades que surgem ao pesquisar no .NET conflitos de dependência que podem parecer promissores, mas normalmente não funcionarão no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77e53-379">Finally, we'll address some possibilities that come up when researching .NET dependency conflicts in .NET that can look promising, but generally won't work for PowerShell.</span></span>

<span data-ttu-id="77e53-380">Todas essas soluções são alteradas para as configurações de implantação de um ambiente no qual você controla o aplicativo e, possivelmente, o computador inteiro.</span><span class="sxs-lookup"><span data-stu-id="77e53-380">These solutions have the common theme that they are changes to deployment configurations for an environment where you control the application and possibly the entire machine.</span></span> <span data-ttu-id="77e53-381">Essas soluções são orientadas para cenários como servidores Web e outros aplicativos implantados em ambientes de servidor, nos quais o ambiente destina-se a hospedar o aplicativo e pode ser configurado pelo usuário de implantação.</span><span class="sxs-lookup"><span data-stu-id="77e53-381">These solutions are oriented toward scenarios like web servers and other applications deployed to server environments, where the environment is intended to host the application and is free to be configured by the deploying user.</span></span> <span data-ttu-id="77e53-382">Elas também tendem a ser muito orientadas para .NET Framework, o que significa que eles não funcionam com o PowerShell 6 ou versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="77e53-382">They also tend to be very much .NET Framework oriented, meaning they do not work with PowerShell 6 or above.</span></span>

<span data-ttu-id="77e53-383">Se você sabe que o seu módulo só é usado em ambientes do Windows PowerShell 5.1 dos quais você tem controle total, algumas dessas opções podem ser usadas.</span><span class="sxs-lookup"><span data-stu-id="77e53-383">If you know that your module is only used in Windows PowerShell 5.1 environments that you have total control over, some of these may be options.</span></span> <span data-ttu-id="77e53-384">No entanto, em geral, **os módulos não devem modificar o estado do computador global dessa forma**.</span><span class="sxs-lookup"><span data-stu-id="77e53-384">In general however, **modules should not modify global machine state like this**.</span></span> <span data-ttu-id="77e53-385">Isso pode interromper as configurações que causam problemas em `powershell.exe`, em outros módulos ou em outros aplicativos dependentes o que faz com que o módulo falhe de maneiras inesperadas.</span><span class="sxs-lookup"><span data-stu-id="77e53-385">It can break configurations that cause problems in `powershell.exe`, other modules, or other dependent applications that cause your module to fail in unexpected ways.</span></span>

### <a name="static-binding-redirect-with-appconfig-to-force-using-the-same-dependency-version"></a><span data-ttu-id="77e53-386">Redirecionamento de associação estática com app.config para forçar o uso da mesma versão de dependência</span><span class="sxs-lookup"><span data-stu-id="77e53-386">Static binding redirect with app.config to force using the same dependency version</span></span>

<span data-ttu-id="77e53-387">Os aplicativos .NET Framework podem aproveitar um arquivo `app.config` para configurar alguns dos comportamentos do aplicativo de modo declarativo.</span><span class="sxs-lookup"><span data-stu-id="77e53-387">.NET Framework applications can take advantage of an `app.config` file to configure some of the application's behaviors declaratively.</span></span> <span data-ttu-id="77e53-388">É possível gravar uma entrada de `app.config` que configura a associação de assembly para redirecionar o carregamento de assembly para uma versão específica.</span><span class="sxs-lookup"><span data-stu-id="77e53-388">It's possible to write an `app.config` entry that configures assembly binding to redirect assembly loading to a particular version.</span></span>

<span data-ttu-id="77e53-389">Essa solução no PowerShell tem dois problemas:</span><span class="sxs-lookup"><span data-stu-id="77e53-389">Two issues with this for PowerShell are:</span></span>

- <span data-ttu-id="77e53-390">O .NET Core não dá suporte a `app.config`, portanto, essa solução só se aplica a `powershell.exe`.</span><span class="sxs-lookup"><span data-stu-id="77e53-390">.NET Core does not support `app.config`, so this solution only applies to `powershell.exe`.</span></span>
- <span data-ttu-id="77e53-391">`powershell.exe` é um aplicativo compartilhado que reside no diretório `System32`.</span><span class="sxs-lookup"><span data-stu-id="77e53-391">`powershell.exe` is a shared application that lives in the `System32` directory.</span></span> <span data-ttu-id="77e53-392">É provável que o seu módulo não seja capaz de modificar o conteúdo dele em muitos sistemas.</span><span class="sxs-lookup"><span data-stu-id="77e53-392">It's likely that your module won't be able to modify its contents on many systems.</span></span> <span data-ttu-id="77e53-393">Mesmo que ele seja, modificar o `app.config` pode interromper uma configuração existente ou afetar o carregamento de outros módulos.</span><span class="sxs-lookup"><span data-stu-id="77e53-393">Even if it can, modifying the `app.config` could break an existing configuration or affect the loading of other modules.</span></span>

### <a name="setting-codebase-with-appconfig"></a><span data-ttu-id="77e53-394">Configurar o `codebase` com app.config</span><span class="sxs-lookup"><span data-stu-id="77e53-394">Setting `codebase` with app.config</span></span>

<span data-ttu-id="77e53-395">Pelos mesmos motivos, tentar definir a configuração de `codebase` em `app.config` não funcionará nos módulos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77e53-395">For the same reasons, trying to configure the `codebase` setting in `app.config` is not going to work in PowerShell modules.</span></span>

### <a name="installing-dependencies-to-the-global-assembly-cache-gac"></a><span data-ttu-id="77e53-396">Instalar dependências no GAC (Cache de Assembly Global)</span><span class="sxs-lookup"><span data-stu-id="77e53-396">Installing dependencies to the Global Assembly Cache (GAC)</span></span>

<span data-ttu-id="77e53-397">Outra maneira de resolver conflitos de versão de dependência no .NET Framework é instalar dependências no GAC, de modo que versões diferentes possam ser carregadas lado a lado no GAC.</span><span class="sxs-lookup"><span data-stu-id="77e53-397">Another way to resolve dependency version conflicts in .NET Framework is to install dependencies to the GAC, so that different versions can be loaded side-by-side from the GAC.</span></span>

<span data-ttu-id="77e53-398">Novamente, nos módulos do PowerShell os principais problemas são:</span><span class="sxs-lookup"><span data-stu-id="77e53-398">Again, for PowerShell modules, the chief issues here are:</span></span>

- <span data-ttu-id="77e53-399">O GAC aplica-se somente ao .NET Framework, portanto, isso não funciona no PowerShell 6 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="77e53-399">The GAC only applies to .NET Framework, so this does not help in PowerShell 6 and above.</span></span>
- <span data-ttu-id="77e53-400">A instalação de assemblies no GAC é uma modificação do estado do computador global e pode causar efeitos colaterais em outros aplicativos ou em outros módulos.</span><span class="sxs-lookup"><span data-stu-id="77e53-400">Installing assemblies to the GAC is a modification of global machine state and may cause side-effects in other applications or to other modules.</span></span> <span data-ttu-id="77e53-401">Ela também pode ser difícil realizar corretamente, mesmo quando o módulo tem os privilégios de acesso necessários.</span><span class="sxs-lookup"><span data-stu-id="77e53-401">It may also be difficult to do correctly, even when your module has the required access privileges.</span></span> <span data-ttu-id="77e53-402">Fazer algo errado pode causar problemas sérios e em todo o computador em outros aplicativos .NET.</span><span class="sxs-lookup"><span data-stu-id="77e53-402">Getting it wrong could cause serious, machine-wide issues in other .NET applications.</span></span>

## <a name="further-reading"></a><span data-ttu-id="77e53-403">Leitura adicional</span><span class="sxs-lookup"><span data-stu-id="77e53-403">Further reading</span></span>

<span data-ttu-id="77e53-404">Há muitos outros artigos sobre conflitos de dependência de versão do assembly do .NET que você pode ler.</span><span class="sxs-lookup"><span data-stu-id="77e53-404">There's plenty more to read on .NET assembly version dependency conflicts.</span></span> <span data-ttu-id="77e53-405">Veja alguns pontos de partida interessantes:</span><span class="sxs-lookup"><span data-stu-id="77e53-405">Here are some nice jumping off points:</span></span>

- [<span data-ttu-id="77e53-406">.NET: Assemblies no .NET</span><span class="sxs-lookup"><span data-stu-id="77e53-406">.NET: Assemblies in .NET</span></span>](/dotnet/standard/assembly/)
- [<span data-ttu-id="77e53-407">.NET Core: O algoritmo de carregamento de assembly gerenciado</span><span class="sxs-lookup"><span data-stu-id="77e53-407">.NET Core: The managed assembly loading algorithm</span></span>](/dotnet/core/dependency-loading/loading-managed)
- [<span data-ttu-id="77e53-408">.NET Core: Compreendendo o System.Runtime.Loader.AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="77e53-408">.NET Core: Understanding System.Runtime.Loader.AssemblyLoadContext</span></span>](/dotnet/core/dependency-loading/understanding-assemblyloadcontext)
- [<span data-ttu-id="77e53-409">.NET Core: Discussão sobre soluções de carregamento lado a lado do assembly</span><span class="sxs-lookup"><span data-stu-id="77e53-409">.NET Core: Discussion about side-by-side assembly loading solutions</span></span>](https://github.com/dotnet/runtime/issues/13471)
- [<span data-ttu-id="77e53-410">.NET Framework: Como redirecionar versões de assembly</span><span class="sxs-lookup"><span data-stu-id="77e53-410">.NET Framework: Redirecting assembly versions</span></span>](/dotnet/framework/configure-apps/redirect-assembly-versions)
- [<span data-ttu-id="77e53-411">.NET Framework: Práticas recomendadas para carregamento de assembly</span><span class="sxs-lookup"><span data-stu-id="77e53-411">.NET Framework: Best practices for assembly loading</span></span>](/dotnet/framework/deployment/best-practices-for-assembly-loading)
- [<span data-ttu-id="77e53-412">.NET Framework: Como o runtime localiza os assemblies</span><span class="sxs-lookup"><span data-stu-id="77e53-412">.NET Framework: How the runtime locates assemblies</span></span>](/dotnet/framework/deployment/how-the-runtime-locates-assemblies)
- [<span data-ttu-id="77e53-413">.NET Framework: Resolver carregamentos de assembly</span><span class="sxs-lookup"><span data-stu-id="77e53-413">.NET Framework: Resolve assembly loads</span></span>](/dotnet/standard/assembly/resolve-loads)
- [<span data-ttu-id="77e53-414">Stack Overflow: Como e por que realizar o redirecionamento da associação de assembly?</span><span class="sxs-lookup"><span data-stu-id="77e53-414">StackOverflow: Assembly binding redirect, how and why?</span></span>](https://stackoverflow.com/questions/43365736/assembly-binding-redirect-how-and-why)
- [<span data-ttu-id="77e53-415">PowerShell: Discussão sobre a implementação do AssemblyLoadContexts</span><span class="sxs-lookup"><span data-stu-id="77e53-415">PowerShell: Discussion about implementing AssemblyLoadContexts</span></span>](https://github.com/PowerShell/PowerShell/issues/11571)
- [<span data-ttu-id="77e53-416">PowerShell: `Assembly.LoadFile()` não carrega no AssemblyLoadContext padrão</span><span class="sxs-lookup"><span data-stu-id="77e53-416">PowerShell: `Assembly.LoadFile()` doesn't load into default AssemblyLoadContext</span></span>](https://github.com/PowerShell/PowerShell/issues/12052)
- [<span data-ttu-id="77e53-417">Rick Strahl: Quando uma dependência de assembly do .NET é carregada?</span><span class="sxs-lookup"><span data-stu-id="77e53-417">Rick Strahl: When does a .NET assembly dependency get loaded?</span></span>](https://weblog.west-wind.com/posts/2012/Nov/03/Back-to-Basics-When-does-a-NET-Assembly-Dependency-get-loaded)
- [<span data-ttu-id="77e53-418">Jon Skeet: Resumo do controle de versão no .NET</span><span class="sxs-lookup"><span data-stu-id="77e53-418">Jon Skeet: Summary of versioning in .NET</span></span>](https://codeblog.jonskeet.uk/2019/06/30/versioning-limitations-in-net/)
- [<span data-ttu-id="77e53-419">Nate McMaster: Saiba mais sobre os primitivos do .NET Core</span><span class="sxs-lookup"><span data-stu-id="77e53-419">Nate McMaster: Deep dive into .NET Core primitives</span></span>](https://natemcmaster.com/blog/2017/12/21/netcore-primitives/)
