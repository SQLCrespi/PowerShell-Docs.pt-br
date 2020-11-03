---
description: O suporte de recursos experimentais no PowerShell fornece um mecanismo para que os recursos experimentais coexistam com os recursos estáveis existentes nos módulos PowerShell ou PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre os recursos experimentais
ms.openlocfilehash: 663b8bbd8659b972004499e0c8a247818b8ef311
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195752"
---
# <a name="experimental-features"></a><span data-ttu-id="a17b1-104">Recursos experimentais</span><span class="sxs-lookup"><span data-stu-id="a17b1-104">Experimental Features</span></span>

<span data-ttu-id="a17b1-105">O suporte de recursos experimentais no PowerShell fornece um mecanismo para que os recursos experimentais coexistam com os recursos estáveis existentes nos módulos PowerShell ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a17b1-105">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="a17b1-106">Um recurso experimental é aquele em que o design não está finalizado.</span><span class="sxs-lookup"><span data-stu-id="a17b1-106">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="a17b1-107">O recurso está disponível para os usuários testarem e fornecerem comentários.</span><span class="sxs-lookup"><span data-stu-id="a17b1-107">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="a17b1-108">Depois que um recurso experimental é finalizado, as alterações de design se tornam alterações interruptivas.</span><span class="sxs-lookup"><span data-stu-id="a17b1-108">Once an experimental feature is finalized, the design changes become breaking changes.</span></span> <span data-ttu-id="a17b1-109">Os recursos experimentais não devem ser usados na produção, já que as alterações podem causar problemas.</span><span class="sxs-lookup"><span data-stu-id="a17b1-109">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span>

<span data-ttu-id="a17b1-110">Os recursos experimentais são desabilitados por padrão e precisam ser explicitamente habilitados pelo usuário ou pelo administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="a17b1-110">Experimental features are disabled by default and need to be explicitly enabled by the user or administrator of the system.</span></span>

<span data-ttu-id="a17b1-111">Os recursos experimentais habilitados são listados no `powershell.config.json` arquivo em `$PSHOME` para todos os usuários ou no arquivo de configuração específico do usuário para um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="a17b1-111">Enabled experimental features are listed in the `powershell.config.json` file in `$PSHOME` for all users or the user-specific configuration file for a specific user.</span></span>

> [!NOTE]
> <span data-ttu-id="a17b1-112">Os recursos experimentais habilitados no arquivo de configuração do usuário têm precedência sobre os recursos experimentais listados no arquivo de configuração do sistema.</span><span class="sxs-lookup"><span data-stu-id="a17b1-112">Experimental features enabled in the user configuration file take precedence over experimental features listed in the system configuration file.</span></span>

## <a name="the-experimental-attribute"></a><span data-ttu-id="a17b1-113">O atributo experimental</span><span class="sxs-lookup"><span data-stu-id="a17b1-113">The Experimental Attribute</span></span>

<span data-ttu-id="a17b1-114">Use o `Experimental` atributo para declarar algum código como experimental.</span><span class="sxs-lookup"><span data-stu-id="a17b1-114">Use the `Experimental` attribute to declare some code as experimental.</span></span>

<span data-ttu-id="a17b1-115">Use a sintaxe a seguir para declarar o `Experimental` atributo que fornece o nome do recurso experimental e a ação a ser tomada se o recurso experimental estiver habilitado:</span><span class="sxs-lookup"><span data-stu-id="a17b1-115">Use the following syntax to declare the `Experimental` attribute providing the name of the experimental feature and the action to take if the experimental feature is enabled:</span></span>

```csharp
[Experimental(NameOfExperimentalFeature, ExperimentAction)]
```

<span data-ttu-id="a17b1-116">Para módulos, o `NameOfExperimentalFeature` deve seguir a forma de `<modulename>.<experimentname>` .</span><span class="sxs-lookup"><span data-stu-id="a17b1-116">For modules, the `NameOfExperimentalFeature` must follow the form of `<modulename>.<experimentname>`.</span></span> <span data-ttu-id="a17b1-117">O `ExperimentAction` parâmetro deve ser especificado e os únicos valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="a17b1-117">The `ExperimentAction` parameter must be specified and the only valid values are:</span></span>

- <span data-ttu-id="a17b1-118">`Show` significa mostrar este recurso experimental se o recurso estiver habilitado</span><span class="sxs-lookup"><span data-stu-id="a17b1-118">`Show` means to show this experimental feature if the feature is enabled</span></span>
- <span data-ttu-id="a17b1-119">`Hide` significa ocultar este recurso experimental se o recurso estiver habilitado</span><span class="sxs-lookup"><span data-stu-id="a17b1-119">`Hide` means to hide this experimental feature if the feature is enabled</span></span>

### <a name="declaring-experimental-features-in-modules-written-in-c"></a><span data-ttu-id="a17b1-120">Declarando recursos experimentais em módulos escritos em C\#</span><span class="sxs-lookup"><span data-stu-id="a17b1-120">Declaring Experimental Features in Modules Written in C\#</span></span>

<span data-ttu-id="a17b1-121">Os autores de módulo que desejam usar os sinalizadores de recursos experimentais podem declarar um cmdlet como experimental usando o `Experimental` atributo.</span><span class="sxs-lookup"><span data-stu-id="a17b1-121">Module authors who want to use the Experimental Feature flags can declare a cmdlet as experimental by using the `Experimental` attribute.</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }
```

### <a name="declaring-experimental-features-in-modules-written-in-powershell"></a><span data-ttu-id="a17b1-122">Declarando recursos experimentais em módulos escritos no PowerShell</span><span class="sxs-lookup"><span data-stu-id="a17b1-122">Declaring Experimental Features in Modules written in PowerShell</span></span>

<span data-ttu-id="a17b1-123">O módulo gravado no PowerShell também pode usar o `Experimental` atributo para declarar cmdlets experimentais:</span><span class="sxs-lookup"><span data-stu-id="a17b1-123">Module written in PowerShell can also use the `Experimental` attribute to declare experimental cmdlets:</span></span>

```powershell
function Enable-SSHRemoting {
    [Experimental("MyRemoting.PSSSHRemoting", "Show")]
    [CmdletBinding()]
    param()
    ...
}
```

### <a name="mutually-exclusive-experimental-features"></a><span data-ttu-id="a17b1-124">Recursos experimentais mutuamente exclusivos</span><span class="sxs-lookup"><span data-stu-id="a17b1-124">Mutually Exclusive Experimental Features</span></span>

<span data-ttu-id="a17b1-125">Há casos em que um recurso experimental não pode coexistir lado a lado com um recurso existente ou outro recurso experimental.</span><span class="sxs-lookup"><span data-stu-id="a17b1-125">There are cases where an experimental feature cannot co-exist side-by-side with an existing feature or another experimental feature.</span></span>

<span data-ttu-id="a17b1-126">Por exemplo, você pode ter um cmdlet experimental que substitui um cmdlet existente.</span><span class="sxs-lookup"><span data-stu-id="a17b1-126">For example, you can have an experimental cmdlet that overrides an existing cmdlet.</span></span> <span data-ttu-id="a17b1-127">As duas versões não podem coexistir lado a lado.</span><span class="sxs-lookup"><span data-stu-id="a17b1-127">The two versions can't coexist side by side.</span></span> <span data-ttu-id="a17b1-128">A `ExperimentAction.Hide` configuração permite que apenas um dos dois cmdlets seja habilitado ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="a17b1-128">The `ExperimentAction.Hide` setting allows only one of the two cmdlets to be enabled at one time.</span></span>

<span data-ttu-id="a17b1-129">Neste exemplo, criamos um novo cmdlet experimental `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="a17b1-129">In this example, we create a new experimental `Invoke-WebRequest` cmdlet.</span></span>
<span data-ttu-id="a17b1-130">`InvokeWebRequestCommand` contém a implementação não experimental.</span><span class="sxs-lookup"><span data-stu-id="a17b1-130">`InvokeWebRequestCommand` contains the non-experimental implementation.</span></span>
<span data-ttu-id="a17b1-131">`InvokeWebRequestCommandV2` contém a versão experimental do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a17b1-131">`InvokeWebRequestCommandV2` contains the experimental version of the cmdlet.</span></span>

<span data-ttu-id="a17b1-132">O uso do `ExperimentAction.Hide` permitirá que apenas um dos dois recursos seja habilitado ao mesmo tempo:</span><span class="sxs-lookup"><span data-stu-id="a17b1-132">The use of `ExperimentAction.Hide` will allow only one of the two features to be enabled at one time:</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }

[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Hide)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommand : WebCmdletBase { ... }
```

<span data-ttu-id="a17b1-133">Quando o `MyWebCmdlets.PSWebCmdletV2` recurso experimental é habilitado, a `InvokeWebRequestCommand` implementação existente é ocultada e o `InvokeWebRequestCommandV2` fornece a implementação de `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="a17b1-133">When the `MyWebCmdlets.PSWebCmdletV2` experimental feature is enabled, the existing `InvokeWebRequestCommand` implementation is hidden and the `InvokeWebRequestCommandV2` provides the implementation of `Invoke-WebRequest`.</span></span>

<span data-ttu-id="a17b1-134">Isso permite que os usuários experimentem o novo cmdlet e forneçam comentários e, em seguida, revertam para a versão não experimental quando necessário.</span><span class="sxs-lookup"><span data-stu-id="a17b1-134">This allows users to try out the new cmdlet and provide feedback then revert to the non-experimental version when needed.</span></span>

### <a name="experimental-parameters-in-cmdlets"></a><span data-ttu-id="a17b1-135">Parâmetros experimentais em cmdlets</span><span class="sxs-lookup"><span data-stu-id="a17b1-135">Experimental Parameters in Cmdlets</span></span>

<span data-ttu-id="a17b1-136">O `Experimental` atributo também pode ser aplicado a parâmetros individuais.</span><span class="sxs-lookup"><span data-stu-id="a17b1-136">The `Experimental` attribute can also be applied to individual parameters.</span></span> <span data-ttu-id="a17b1-137">Isso permite que você crie um conjunto experimental de parâmetros para um cmdlet existente em vez de um cmdlet totalmente novo.</span><span class="sxs-lookup"><span data-stu-id="a17b1-137">This allows you to create an experimental set of parameters for an existing cmdlet rather than an entirely new cmdlet.</span></span>

<span data-ttu-id="a17b1-138">Veja um exemplo em C#:</span><span class="sxs-lookup"><span data-stu-id="a17b1-138">Here is an example in C#:</span></span>

```csharp
[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Show)]
[Parameter(ParameterSet = "NewCompilation")]
public CompilationParameters CompileParameters { ... }

[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Hide)]
[Parameter()]
public CodeDom CodeDom { ... }
```

<span data-ttu-id="a17b1-139">Aqui está um exemplo diferente no script do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a17b1-139">Here is a different example in PowerShell script:</span></span>

```powershell
param(
    [Experimental("MyModule.PSNewFeature", "Show")]
    [string] $NewName,

    [Experimental("MyModule.PSNewFeature", "Hide")]
    [string] $OldName
)
```

## <a name="checking-if-an-experimental-feature-is-enabled"></a><span data-ttu-id="a17b1-140">Verificando se um recurso experimental está habilitado</span><span class="sxs-lookup"><span data-stu-id="a17b1-140">Checking if an Experimental Feature is Enabled</span></span>

<span data-ttu-id="a17b1-141">Em seu código, você precisará verificar se o seu recurso experimental está habilitado antes de tomar a ação apropriada.</span><span class="sxs-lookup"><span data-stu-id="a17b1-141">In your code, you will need to check if your experimental feature is enabled before taking appropriate action.</span></span> <span data-ttu-id="a17b1-142">Você pode determinar se um recurso experimental está habilitado usando o `IsEnabled()` método estático na `System.Management.Automation.ExperimentalFeature` classe.</span><span class="sxs-lookup"><span data-stu-id="a17b1-142">You can determine if an experimental feature is enabled using the static `IsEnabled()` method on the `System.Management.Automation.ExperimentalFeature` class.</span></span>

<span data-ttu-id="a17b1-143">Veja um exemplo em C#:</span><span class="sxs-lookup"><span data-stu-id="a17b1-143">Here is an example in C#:</span></span>

```csharp
if (ExperimentalFeature.IsEnabled("MyModule.MyExperimentalFeature"))
{
   // code specific to the experimental feature
}
```

<span data-ttu-id="a17b1-144">Veja um exemplo no script do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a17b1-144">Here is an example in PowerShell script:</span></span>

```powershell
if ([ExperimentalFeature]::IsEnabled("MyModule.MyExperimentalFeature"))
{
  # code specific to the experimental feature
}
```

## <a name="see-also"></a><span data-ttu-id="a17b1-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="a17b1-145">See also</span></span>

[<span data-ttu-id="a17b1-146">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="a17b1-146">Enable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Enable-ExperimentalFeature)

[<span data-ttu-id="a17b1-147">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="a17b1-147">Disable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Disable-ExperimentalFeature)

[<span data-ttu-id="a17b1-148">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="a17b1-148">Get-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Get-ExperimentalFeature)
