---
ms.date: 09/12/2016
ms.topic: reference
title: Nomear arquivos de ajuda
description: Nomear arquivos de ajuda
ms.openlocfilehash: b77af8f9b9510785a4198fed9da1263184a27b99
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667582"
---
# <a name="naming-help-files"></a><span data-ttu-id="6f4ca-103">Nomear arquivos de ajuda</span><span class="sxs-lookup"><span data-stu-id="6f4ca-103">Naming Help Files</span></span>

<span data-ttu-id="6f4ca-104">Este tópico explica como nomear um arquivo de ajuda baseado em XML para que o cmdlet [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) possa encontrá-lo.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-104">This topic explains how to name an XML-based help file so that the [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet can find it.</span></span> <span data-ttu-id="6f4ca-105">Os requisitos de nome são diferentes para cada tipo de comando.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-105">The name requirements differ for each command type.</span></span>

## <a name="cmdlet-help-files"></a><span data-ttu-id="6f4ca-106">Arquivos de ajuda de cmdlet</span><span class="sxs-lookup"><span data-stu-id="6f4ca-106">Cmdlet Help Files</span></span>

<span data-ttu-id="6f4ca-107">O arquivo de ajuda para um cmdlet do C# deve ser nomeado para o assembly no qual o cmdlet é definido.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-107">The help file for a C# cmdlet must be named for the assembly in which the cmdlet is defined.</span></span> <span data-ttu-id="6f4ca-108">Use o seguinte formato de nome de arquivo:</span><span class="sxs-lookup"><span data-stu-id="6f4ca-108">Use the following filename format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="6f4ca-109">O formato do nome do assembly é necessário mesmo quando o assembly é um módulo aninhado.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-109">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="6f4ca-110">Por exemplo, o cmdlet [Get-WinEvent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) é definido no assembly Microsoft.PowerShell.Diagnostics.dll.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-110">For example, the [Get-WinEvent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) cmdlet is defined in the Microsoft.PowerShell.Diagnostics.dll assembly.</span></span> <span data-ttu-id="6f4ca-111">O `Get-Help` cmdlet procura um tópico de ajuda para o `Get-WinEvent` cmdlet somente no `Microsoft.PowerShell.Diagnostics.dll-help.xml` arquivo no diretório do módulo.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-111">The `Get-Help` cmdlet looks for a help topic for the `Get-WinEvent` cmdlet only in the `Microsoft.PowerShell.Diagnostics.dll-help.xml` file in the module directory.</span></span>

## <a name="provider-help-files"></a><span data-ttu-id="6f4ca-112">Arquivos de ajuda do provedor</span><span class="sxs-lookup"><span data-stu-id="6f4ca-112">Provider Help files</span></span>

<span data-ttu-id="6f4ca-113">O arquivo de ajuda para um provedor do PowerShell deve ser nomeado para o assembly no qual o provedor está definido.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-113">The help file for a PowerShell provider must be named for the assembly in which the provider is defined.</span></span> <span data-ttu-id="6f4ca-114">Use o seguinte formato de nome de arquivo:</span><span class="sxs-lookup"><span data-stu-id="6f4ca-114">Use the following filename format:</span></span>

`<AssemblyName>.dll-help.xml`

<span data-ttu-id="6f4ca-115">O formato do nome do assembly é necessário mesmo quando o assembly é um módulo aninhado.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-115">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="6f4ca-116">Por exemplo, o provedor de certificado é definido no `Microsoft.PowerShell.Security.dll` assembly.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-116">For example, the Certificate provider is defined in the `Microsoft.PowerShell.Security.dll` assembly.</span></span> <span data-ttu-id="6f4ca-117">O `Get-Help` cmdlet procura um tópico de ajuda para o provedor de certificado somente no `Microsoft.PowerShell.Security.dll-help.xml` arquivo no diretório do módulo.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-117">The `Get-Help` cmdlet looks for a help topic for the Certificate provider only in the `Microsoft.PowerShell.Security.dll-help.xml` file in the module directory.</span></span>

## <a name="function-help-files"></a><span data-ttu-id="6f4ca-118">Arquivos de ajuda da função</span><span class="sxs-lookup"><span data-stu-id="6f4ca-118">Function Help Files</span></span>

<span data-ttu-id="6f4ca-119">As funções podem ser documentadas usando [a ajuda baseada em comentários](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) ou documentadas em um arquivo de ajuda XML.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-119">Functions can be documented by using [comment-based help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) or documented in an XML help file.</span></span> <span data-ttu-id="6f4ca-120">Quando a função é documentada em um arquivo XML, a função deve ter uma `.ExternalHelp` palavra-chave comment que associa a função ao arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-120">When the function is documented in an XML file, the function must have an `.ExternalHelp` comment keyword that associates the function with the XML file.</span></span> <span data-ttu-id="6f4ca-121">Caso contrário, o `Get-Help` cmdlet não poderá localizar o arquivo de ajuda.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-121">Otherwise, the `Get-Help` cmdlet cannot find the help file.</span></span>

<span data-ttu-id="6f4ca-122">Não há requisitos técnicos para o nome de um arquivo de ajuda de função.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-122">There are no technical requirements for the name of a function help file.</span></span> <span data-ttu-id="6f4ca-123">No entanto, uma prática recomendada é nomear o arquivo de ajuda para o módulo de script no qual a função é definida.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-123">However, a best practice is to name the help file for the script module in which the function is defined.</span></span> <span data-ttu-id="6f4ca-124">Por exemplo, a função a seguir é definida no `MyModule.psm1` arquivo.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-124">For example, the following function is defined in the `MyModule.psm1` file.</span></span>

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a><span data-ttu-id="6f4ca-125">Arquivos de ajuda do comando CIM</span><span class="sxs-lookup"><span data-stu-id="6f4ca-125">CIM Command Help Files</span></span>

<span data-ttu-id="6f4ca-126">O arquivo de ajuda para um comando CIM deve ser nomeado para o arquivo CDXML no qual o comando CIM está definido.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-126">The help file for a CIM command must be named for the CDXML file in which the CIM command is defined.</span></span> <span data-ttu-id="6f4ca-127">Use o seguinte formato de nome de arquivo:</span><span class="sxs-lookup"><span data-stu-id="6f4ca-127">Use the following filename format:</span></span>

`<FileName>.cdxml-help.xml`

<span data-ttu-id="6f4ca-128">Os comandos CIM são definidos em arquivos CDXML que podem ser incluídos em módulos como módulos aninhados.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-128">CIM commands are defined in CDXML files that can be included in modules as nested modules.</span></span> <span data-ttu-id="6f4ca-129">Quando o comando CIM é importado para a sessão como uma função, o PowerShell adiciona uma `.ExternalHelp` palavra-chave comment à definição da função que associa a função a um arquivo de ajuda XML que é nomeado para o arquivo CDXML no qual o comando CIM é definido.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-129">When the CIM command is imported into the session as a function, PowerShell adds an `.ExternalHelp` comment keyword to the function definition that associates the function with an XML help file that is named for the CDXML file in which the CIM command is defined.</span></span>

## <a name="script-workflow-help-files"></a><span data-ttu-id="6f4ca-130">Arquivos de ajuda do fluxo de trabalho de script</span><span class="sxs-lookup"><span data-stu-id="6f4ca-130">Script Workflow Help Files</span></span>

<span data-ttu-id="6f4ca-131">Os fluxos de trabalho de script incluídos em módulos podem ser documentados em arquivos de ajuda baseados em XML.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-131">Script workflows that are included in modules can be documented in XML-based help files.</span></span> <span data-ttu-id="6f4ca-132">Não há requisitos técnicos para o nome do arquivo de ajuda.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-132">There are no technical requirements for the name of the help file.</span></span> <span data-ttu-id="6f4ca-133">No entanto, uma prática recomendada é nomear o arquivo de ajuda para o módulo de script no qual o fluxo de trabalho de script é definido.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-133">However, a best practice is to name the help file for the script module in which the script workflow is defined.</span></span> <span data-ttu-id="6f4ca-134">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6f4ca-134">For example:</span></span>

`<ScriptModule>.psm1-help.xml`

<span data-ttu-id="6f4ca-135">Ao contrário de outros comandos com script, os fluxos de trabalho de script não exigem uma `.ExternalHelp` palavra-chave de comentário para associá-los a um arquivo de ajuda.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-135">Unlike other scripted commands, script workflows do not require an `.ExternalHelp` comment keyword to associate them with a help file.</span></span> <span data-ttu-id="6f4ca-136">Em vez disso, o PowerShell pesquisa os subdiretórios específicos da cultura da interface do diretório do módulo para arquivos de ajuda baseados em XML e procura ajuda para o fluxo de trabalho do script em todos os arquivos.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-136">Instead, PowerShell searches the UI-Culture-specific subdirectories of the module directory for XML-based help files and looks for help for the script workflow in all the files.</span></span> <span data-ttu-id="6f4ca-137">`.ExternalHelp` a palavra-chave Comment é ignorada.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-137">`.ExternalHelp` comment keyword are ignored.</span></span>

<span data-ttu-id="6f4ca-138">Como a `.ExternalHelp` palavra-chave Comment é ignorada, o `Get-Help` cmdlet pode encontrar ajuda para fluxos de trabalho de script somente quando eles são incluídos em módulos.</span><span class="sxs-lookup"><span data-stu-id="6f4ca-138">Because the `.ExternalHelp` comment keyword is ignored, the `Get-Help` cmdlet can find help for script workflows only when they are included in modules.</span></span>
