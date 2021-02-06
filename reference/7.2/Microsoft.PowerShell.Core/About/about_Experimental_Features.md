---
description: O suporte de recursos experimentais no PowerShell fornece um mecanismo para que os recursos experimentais coexistam com os recursos estáveis existentes nos módulos PowerShell ou PowerShell.
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_experimental_features?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre os recursos experimentais
ms.openlocfilehash: 82f5ef9838fcbb98e71e362ad00b1ec68f9a9f67
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598033"
---
# <a name="experimental-features"></a><span data-ttu-id="0c3b9-103">Recursos experimentais</span><span class="sxs-lookup"><span data-stu-id="0c3b9-103">Experimental Features</span></span>

<span data-ttu-id="0c3b9-104">O suporte de recursos experimentais no PowerShell fornece um mecanismo para que os recursos experimentais coexistam com os recursos estáveis existentes nos módulos PowerShell ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-104">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="0c3b9-105">Um recurso experimental é aquele em que o design não está finalizado.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-105">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="0c3b9-106">O recurso está disponível para os usuários testarem e fornecerem comentários.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-106">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="0c3b9-107">Depois que um recurso experimental é finalizado, as alterações de design se tornam alterações interruptivas.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-107">Once an experimental feature is finalized, the design changes become breaking changes.</span></span> <span data-ttu-id="0c3b9-108">Os recursos experimentais não devem ser usados na produção, já que as alterações podem causar problemas.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-108">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span>

<span data-ttu-id="0c3b9-109">Os recursos experimentais são desabilitados por padrão e precisam ser explicitamente habilitados pelo usuário ou pelo administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-109">Experimental features are disabled by default and need to be explicitly enabled by the user or administrator of the system.</span></span>

<span data-ttu-id="0c3b9-110">Os recursos experimentais habilitados são listados no `powershell.config.json` arquivo em `$PSHOME` para todos os usuários ou no arquivo de configuração específico do usuário para um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-110">Enabled experimental features are listed in the `powershell.config.json` file in `$PSHOME` for all users or the user-specific configuration file for a specific user.</span></span>

> [!NOTE]
> <span data-ttu-id="0c3b9-111">Os recursos experimentais habilitados no arquivo de configuração do usuário têm precedência sobre os recursos experimentais listados no arquivo de configuração do sistema.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-111">Experimental features enabled in the user configuration file take precedence over experimental features listed in the system configuration file.</span></span>

## <a name="the-experimental-attribute"></a><span data-ttu-id="0c3b9-112">O atributo experimental</span><span class="sxs-lookup"><span data-stu-id="0c3b9-112">The Experimental Attribute</span></span>

<span data-ttu-id="0c3b9-113">Use o `Experimental` atributo para declarar algum código como experimental.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-113">Use the `Experimental` attribute to declare some code as experimental.</span></span>

<span data-ttu-id="0c3b9-114">Use a sintaxe a seguir para declarar o `Experimental` atributo que fornece o nome do recurso experimental e a ação a ser tomada se o recurso experimental estiver habilitado:</span><span class="sxs-lookup"><span data-stu-id="0c3b9-114">Use the following syntax to declare the `Experimental` attribute providing the name of the experimental feature and the action to take if the experimental feature is enabled:</span></span>

```csharp
[Experimental(NameOfExperimentalFeature, ExperimentAction)]
```

<span data-ttu-id="0c3b9-115">Para módulos, o `NameOfExperimentalFeature` deve seguir a forma de `<modulename>.<experimentname>` .</span><span class="sxs-lookup"><span data-stu-id="0c3b9-115">For modules, the `NameOfExperimentalFeature` must follow the form of `<modulename>.<experimentname>`.</span></span> <span data-ttu-id="0c3b9-116">O `ExperimentAction` parâmetro deve ser especificado e os únicos valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="0c3b9-116">The `ExperimentAction` parameter must be specified and the only valid values are:</span></span>

- <span data-ttu-id="0c3b9-117">`Show` significa mostrar este recurso experimental se o recurso estiver habilitado</span><span class="sxs-lookup"><span data-stu-id="0c3b9-117">`Show` means to show this experimental feature if the feature is enabled</span></span>
- <span data-ttu-id="0c3b9-118">`Hide` significa ocultar este recurso experimental se o recurso estiver habilitado</span><span class="sxs-lookup"><span data-stu-id="0c3b9-118">`Hide` means to hide this experimental feature if the feature is enabled</span></span>

### <a name="declaring-experimental-features-in-modules-written-in-c"></a><span data-ttu-id="0c3b9-119">Declarando recursos experimentais em módulos escritos em C\#</span><span class="sxs-lookup"><span data-stu-id="0c3b9-119">Declaring Experimental Features in Modules Written in C\#</span></span>

<span data-ttu-id="0c3b9-120">Os autores de módulo que desejam usar os sinalizadores de recursos experimentais podem declarar um cmdlet como experimental usando o `Experimental` atributo.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-120">Module authors who want to use the Experimental Feature flags can declare a cmdlet as experimental by using the `Experimental` attribute.</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }
```

### <a name="declaring-experimental-features-in-modules-written-in-powershell"></a><span data-ttu-id="0c3b9-121">Declarando recursos experimentais em módulos escritos no PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c3b9-121">Declaring Experimental Features in Modules written in PowerShell</span></span>

<span data-ttu-id="0c3b9-122">O módulo gravado no PowerShell também pode usar o `Experimental` atributo para declarar cmdlets experimentais:</span><span class="sxs-lookup"><span data-stu-id="0c3b9-122">Module written in PowerShell can also use the `Experimental` attribute to declare experimental cmdlets:</span></span>

```powershell
function Enable-SSHRemoting {
    [Experimental("MyRemoting.PSSSHRemoting", "Show")]
    [CmdletBinding()]
    param()
    ...
}
```

### <a name="mutually-exclusive-experimental-features"></a><span data-ttu-id="0c3b9-123">Recursos experimentais mutuamente exclusivos</span><span class="sxs-lookup"><span data-stu-id="0c3b9-123">Mutually Exclusive Experimental Features</span></span>

<span data-ttu-id="0c3b9-124">Há casos em que um recurso experimental não pode coexistir lado a lado com um recurso existente ou outro recurso experimental.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-124">There are cases where an experimental feature cannot co-exist side-by-side with an existing feature or another experimental feature.</span></span>

<span data-ttu-id="0c3b9-125">Por exemplo, você pode ter um cmdlet experimental que substitui um cmdlet existente.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-125">For example, you can have an experimental cmdlet that overrides an existing cmdlet.</span></span> <span data-ttu-id="0c3b9-126">As duas versões não podem coexistir lado a lado.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-126">The two versions can't coexist side by side.</span></span> <span data-ttu-id="0c3b9-127">A `ExperimentAction.Hide` configuração permite que apenas um dos dois cmdlets seja habilitado ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-127">The `ExperimentAction.Hide` setting allows only one of the two cmdlets to be enabled at one time.</span></span>

<span data-ttu-id="0c3b9-128">Neste exemplo, criamos um novo cmdlet experimental `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="0c3b9-128">In this example, we create a new experimental `Invoke-WebRequest` cmdlet.</span></span>
<span data-ttu-id="0c3b9-129">`InvokeWebRequestCommand` contém a implementação não experimental.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-129">`InvokeWebRequestCommand` contains the non-experimental implementation.</span></span>
<span data-ttu-id="0c3b9-130">`InvokeWebRequestCommandV2` contém a versão experimental do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-130">`InvokeWebRequestCommandV2` contains the experimental version of the cmdlet.</span></span>

<span data-ttu-id="0c3b9-131">O uso do `ExperimentAction.Hide` permitirá que apenas um dos dois recursos seja habilitado ao mesmo tempo:</span><span class="sxs-lookup"><span data-stu-id="0c3b9-131">The use of `ExperimentAction.Hide` will allow only one of the two features to be enabled at one time:</span></span>

```csharp
[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Show)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommandV2 : WebCmdletBaseV2 { ... }

[Experimental("MyWebCmdlets.PSWebCmdletV2", ExperimentAction.Hide)]
[Cmdlet(Verbs.Invoke, "WebRequest")]
public class InvokeWebRequestCommand : WebCmdletBase { ... }
```

<span data-ttu-id="0c3b9-132">Quando o `MyWebCmdlets.PSWebCmdletV2` recurso experimental é habilitado, a `InvokeWebRequestCommand` implementação existente é ocultada e o `InvokeWebRequestCommandV2` fornece a implementação de `Invoke-WebRequest` .</span><span class="sxs-lookup"><span data-stu-id="0c3b9-132">When the `MyWebCmdlets.PSWebCmdletV2` experimental feature is enabled, the existing `InvokeWebRequestCommand` implementation is hidden and the `InvokeWebRequestCommandV2` provides the implementation of `Invoke-WebRequest`.</span></span>

<span data-ttu-id="0c3b9-133">Isso permite que os usuários experimentem o novo cmdlet e forneçam comentários e, em seguida, revertam para a versão não experimental quando necessário.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-133">This allows users to try out the new cmdlet and provide feedback then revert to the non-experimental version when needed.</span></span>

### <a name="experimental-parameters-in-cmdlets"></a><span data-ttu-id="0c3b9-134">Parâmetros experimentais em cmdlets</span><span class="sxs-lookup"><span data-stu-id="0c3b9-134">Experimental Parameters in Cmdlets</span></span>

<span data-ttu-id="0c3b9-135">O `Experimental` atributo também pode ser aplicado a parâmetros individuais.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-135">The `Experimental` attribute can also be applied to individual parameters.</span></span> <span data-ttu-id="0c3b9-136">Isso permite que você crie um conjunto experimental de parâmetros para um cmdlet existente em vez de um cmdlet totalmente novo.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-136">This allows you to create an experimental set of parameters for an existing cmdlet rather than an entirely new cmdlet.</span></span>

<span data-ttu-id="0c3b9-137">Veja um exemplo em C#:</span><span class="sxs-lookup"><span data-stu-id="0c3b9-137">Here is an example in C#:</span></span>

```csharp
[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Show)]
[Parameter(ParameterSet = "NewCompilation")]
public CompilationParameters CompileParameters { ... }

[Experimental("MyModule.PSNewAddTypeCompilation", ExperimentAction.Hide)]
[Parameter()]
public CodeDom CodeDom { ... }
```

<span data-ttu-id="0c3b9-138">Aqui está um exemplo diferente no script do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0c3b9-138">Here is a different example in PowerShell script:</span></span>

```powershell
param(
    [Experimental("MyModule.PSNewFeature", "Show")]
    [string] $NewName,

    [Experimental("MyModule.PSNewFeature", "Hide")]
    [string] $OldName
)
```

## <a name="checking-if-an-experimental-feature-is-enabled"></a><span data-ttu-id="0c3b9-139">Verificando se um recurso experimental está habilitado</span><span class="sxs-lookup"><span data-stu-id="0c3b9-139">Checking if an Experimental Feature is Enabled</span></span>

<span data-ttu-id="0c3b9-140">Em seu código, você precisará verificar se o seu recurso experimental está habilitado antes de tomar a ação apropriada.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-140">In your code, you will need to check if your experimental feature is enabled before taking appropriate action.</span></span> <span data-ttu-id="0c3b9-141">Você pode determinar se um recurso experimental está habilitado usando o `IsEnabled()` método estático na `System.Management.Automation.ExperimentalFeature` classe.</span><span class="sxs-lookup"><span data-stu-id="0c3b9-141">You can determine if an experimental feature is enabled using the static `IsEnabled()` method on the `System.Management.Automation.ExperimentalFeature` class.</span></span>

<span data-ttu-id="0c3b9-142">Veja um exemplo em C#:</span><span class="sxs-lookup"><span data-stu-id="0c3b9-142">Here is an example in C#:</span></span>

```csharp
if (ExperimentalFeature.IsEnabled("MyModule.MyExperimentalFeature"))
{
   // code specific to the experimental feature
}
```

<span data-ttu-id="0c3b9-143">Veja um exemplo no script do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0c3b9-143">Here is an example in PowerShell script:</span></span>

```powershell
if ([ExperimentalFeature]::IsEnabled("MyModule.MyExperimentalFeature"))
{
  # code specific to the experimental feature
}
```

## <a name="see-also"></a><span data-ttu-id="0c3b9-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0c3b9-144">See also</span></span>

[<span data-ttu-id="0c3b9-145">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="0c3b9-145">Enable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Enable-ExperimentalFeature)

[<span data-ttu-id="0c3b9-146">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="0c3b9-146">Disable-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Disable-ExperimentalFeature)

[<span data-ttu-id="0c3b9-147">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="0c3b9-147">Get-ExperimentalFeature</span></span>](xref:Microsoft.PowerShell.Core.Get-ExperimentalFeature)

