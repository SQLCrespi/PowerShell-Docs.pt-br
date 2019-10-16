---
title: Nomeando arquivos de ajuda | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf54eac7-88c6-4108-a5f6-2f0906d1662b
caps.latest.revision: 5
ms.openlocfilehash: f65a90023df88fceafae1d1875ddf46b9088e2b8
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367005"
---
# <a name="naming-help-files"></a><span data-ttu-id="fb897-102">Nomear arquivos de ajuda</span><span class="sxs-lookup"><span data-stu-id="fb897-102">Naming Help Files</span></span>

<span data-ttu-id="fb897-103">Este tópico explica como nomear um arquivo de ajuda baseado em XML para que o cmdlet [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) possa encontrá-lo.</span><span class="sxs-lookup"><span data-stu-id="fb897-103">This topic explains how to name an XML-based help file so that the [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet can find it.</span></span> <span data-ttu-id="fb897-104">Os requisitos de nome são diferentes para cada tipo de comando.</span><span class="sxs-lookup"><span data-stu-id="fb897-104">The name requirements differ for each command type.</span></span>

## <a name="cmdlet-help-files"></a><span data-ttu-id="fb897-105">Arquivos de ajuda de cmdlet</span><span class="sxs-lookup"><span data-stu-id="fb897-105">Cmdlet Help Files</span></span>

<span data-ttu-id="fb897-106">O arquivo de ajuda para C# um cmdlet deve ser nomeado para o assembly no qual o cmdlet é definido.</span><span class="sxs-lookup"><span data-stu-id="fb897-106">The help file for a C# cmdlet must be named for the assembly in which the cmdlet is defined.</span></span> <span data-ttu-id="fb897-107">Use o seguinte formato de nome de arquivo:</span><span class="sxs-lookup"><span data-stu-id="fb897-107">Use the following file name format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="fb897-108">O formato do nome do assembly é necessário mesmo quando o assembly é um módulo aninhado.</span><span class="sxs-lookup"><span data-stu-id="fb897-108">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="fb897-109">Por exemplo, o [Get-WinEvent; PSITPro5_Diagnostic;](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) o cmdlet é definido no assembly Microsoft. PowerShell. Diagnostics. dll.</span><span class="sxs-lookup"><span data-stu-id="fb897-109">For example, the [Get-WinEvent;PSITPro5_Diagnostic;](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) cmdlet is defined in the Microsoft.PowerShell.Diagnostics.dll assembly.</span></span> <span data-ttu-id="fb897-110">O cmdlet `Get-Help` procura um tópico de ajuda para o cmdlet `Get-WinEvent` somente no arquivo Microsoft. PowerShell. Diagnostics. dll-help. xml no diretório do módulo.</span><span class="sxs-lookup"><span data-stu-id="fb897-110">The `Get-Help` cmdlet looks for a help topic for the `Get-WinEvent` cmdlet only in the Microsoft.PowerShell.Diagnostics.dll-help.xml file in the module directory.</span></span>

## <a name="provider-help-files"></a><span data-ttu-id="fb897-111">Arquivos de ajuda do provedor</span><span class="sxs-lookup"><span data-stu-id="fb897-111">Provider Help files</span></span>

<span data-ttu-id="fb897-112">O arquivo de ajuda para um provedor do Windows PowerShell deve ser nomeado para o assembly no qual o provedor é definido.</span><span class="sxs-lookup"><span data-stu-id="fb897-112">The help file for a Windows PowerShell provider must be named for the assembly in which the provider is defined.</span></span> <span data-ttu-id="fb897-113">Use o seguinte formato de nome de arquivo:</span><span class="sxs-lookup"><span data-stu-id="fb897-113">Use the following file name format:</span></span>

```
<AssemblyName>.dll-help.xml
```

<span data-ttu-id="fb897-114">O formato do nome do assembly é necessário mesmo quando o assembly é um módulo aninhado.</span><span class="sxs-lookup"><span data-stu-id="fb897-114">The assembly name format is required even when the assembly is a nested module.</span></span>

<span data-ttu-id="fb897-115">Por exemplo, o provedor de certificado é definido no assembly Microsoft. PowerShell. Security. dll.</span><span class="sxs-lookup"><span data-stu-id="fb897-115">For example, the Certificate provider is defined in the Microsoft.PowerShell.Security.dll assembly.</span></span> <span data-ttu-id="fb897-116">O cmdlet `Get-Help` procura um tópico de ajuda para o provedor de certificado somente no arquivo Microsoft. PowerShell. Security. dll-help. xml no diretório do módulo.</span><span class="sxs-lookup"><span data-stu-id="fb897-116">The `Get-Help` cmdlet looks for a help topic for the Certificate provider only in the Microsoft.PowerShell.Security.dll-help.xml file in the module directory.</span></span>

## <a name="function-help-files"></a><span data-ttu-id="fb897-117">Arquivos de ajuda da função</span><span class="sxs-lookup"><span data-stu-id="fb897-117">Function Help Files</span></span>

<span data-ttu-id="fb897-118">As funções podem ser documentadas usando [a ajuda baseada em comentários](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) ou documentadas em um arquivo de ajuda XML.</span><span class="sxs-lookup"><span data-stu-id="fb897-118">Functions can be documented by using [comment-based help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) or documented in an XML help file.</span></span> <span data-ttu-id="fb897-119">Quando a função é documentada em um arquivo XML, a função deve ter uma palavra-chave de comentário `.ExternalHelp` que associa a função ao arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="fb897-119">When the function is documented in an XML file, the function must have an `.ExternalHelp` comment keyword that associates the function with the XML file.</span></span> <span data-ttu-id="fb897-120">Caso contrário, o cmdlet `Get-Help` não poderá localizar o arquivo de ajuda.</span><span class="sxs-lookup"><span data-stu-id="fb897-120">Otherwise, the `Get-Help` cmdlet cannot find the help file.</span></span>

<span data-ttu-id="fb897-121">Não há requisitos técnicos para o nome de um arquivo de ajuda de função.</span><span class="sxs-lookup"><span data-stu-id="fb897-121">There are no technical requirements for the name of a function help file.</span></span> <span data-ttu-id="fb897-122">No entanto, uma prática recomendada é nomear o arquivo de ajuda para o módulo de script no qual a função é definida.</span><span class="sxs-lookup"><span data-stu-id="fb897-122">However, a best practice is to name the help file for the script module in which the function is defined.</span></span> <span data-ttu-id="fb897-123">Por exemplo, a função a seguir é definida no arquivo MyModule. psm1.</span><span class="sxs-lookup"><span data-stu-id="fb897-123">For example, the following function is defined in the MyModule.psm1 file.</span></span>

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a><span data-ttu-id="fb897-124">Arquivos de ajuda do comando CIM</span><span class="sxs-lookup"><span data-stu-id="fb897-124">CIM Command Help Files</span></span>

<span data-ttu-id="fb897-125">O arquivo de ajuda para um comando CIM deve ser nomeado para o arquivo CDXML no qual o comando CIM está definido.</span><span class="sxs-lookup"><span data-stu-id="fb897-125">The help file for a CIM command must be named for the CDXML file in which the CIM command is defined.</span></span> <span data-ttu-id="fb897-126">Use o seguinte formato de nome de arquivo:</span><span class="sxs-lookup"><span data-stu-id="fb897-126">Use the following file name format:</span></span>

```
<FileName>.cdxml-help.xml
```

<span data-ttu-id="fb897-127">Os comandos CIM são definidos em arquivos CDXML que podem ser incluídos em módulos como módulos aninhados.</span><span class="sxs-lookup"><span data-stu-id="fb897-127">CIM commands are defined in CDXML files that can be included in modules as nested modules.</span></span> <span data-ttu-id="fb897-128">Quando o comando CIM é importado para a sessão como uma função, o Windows PowerShell adiciona uma palavra-chave de comentário `.ExternalHelp` à definição de função que associa a função a um arquivo de ajuda XML nomeado para o arquivo CDXML no qual o comando CIM é definido.</span><span class="sxs-lookup"><span data-stu-id="fb897-128">When the CIM command is imported into the session as a function, Windows PowerShell adds an `.ExternalHelp` comment keyword to the function definition that associates the function with an XML help file that is named for the CDXML file in which the CIM command is defined.</span></span>

## <a name="script-workflow-help-files"></a><span data-ttu-id="fb897-129">Arquivos de ajuda do fluxo de trabalho de script</span><span class="sxs-lookup"><span data-stu-id="fb897-129">Script Workflow Help Files</span></span>

<span data-ttu-id="fb897-130">Os fluxos de trabalho de script incluídos em módulos podem ser documentados em arquivos de ajuda baseados em XML.</span><span class="sxs-lookup"><span data-stu-id="fb897-130">Script workflows that are included in modules can be documented in XML-based help files.</span></span> <span data-ttu-id="fb897-131">Não há requisitos técnicos para o nome do arquivo de ajuda.</span><span class="sxs-lookup"><span data-stu-id="fb897-131">There are no technical requirements for the name of the help file.</span></span> <span data-ttu-id="fb897-132">No entanto, uma prática recomendada é nomear o arquivo de ajuda para o módulo de script no qual o fluxo de trabalho de script é definido.</span><span class="sxs-lookup"><span data-stu-id="fb897-132">However, a best practice is to name the help file for the script module in which the script workflow is defined.</span></span> <span data-ttu-id="fb897-133">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fb897-133">For example:</span></span>

```
<ScriptModule>.psm1-help.xml
```

<span data-ttu-id="fb897-134">Ao contrário de outros comandos com script, os fluxos de trabalho de script não exigem uma palavra-chave de comentário `.ExternalHelp` para associá-los a um arquivo de ajuda.</span><span class="sxs-lookup"><span data-stu-id="fb897-134">Unlike other scripted commands, script workflows do not require an `.ExternalHelp` comment keyword to associate them with a help file.</span></span> <span data-ttu-id="fb897-135">Em vez disso, o Windows PowerShell pesquisa os subdiretórios específicos da cultura da interface do diretório do módulo para arquivos de ajuda baseados em XML e procura ajuda para o fluxo de trabalho de script em todos os arquivos.</span><span class="sxs-lookup"><span data-stu-id="fb897-135">Instead, Windows PowerShell searches the UI-Culture-specific subdirectories of the module directory for XML-based help files and looks for help for the script workflow in all the files.</span></span> <span data-ttu-id="fb897-136">a palavra-chave de comentário `.ExternalHelp` é ignorada.</span><span class="sxs-lookup"><span data-stu-id="fb897-136">`.ExternalHelp` comment keyword are ignored.</span></span>

<span data-ttu-id="fb897-137">Como a palavra-chave comment de `.ExternalHelp` é ignorada, o cmdlet `Get-Help` pode encontrar ajuda para fluxos de trabalho de script somente quando eles são incluídos em módulos.</span><span class="sxs-lookup"><span data-stu-id="fb897-137">Because the `.ExternalHelp` comment keyword is ignored, the `Get-Help` cmdlet can find help for script workflows only when they are included in modules.</span></span>