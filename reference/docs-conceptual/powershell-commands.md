---
title: O que é um comando do PowerShell?
description: O PowerShell permite executar qualquer comando disponível no sistema e inclui o comando específico do PowerShell conhecido como cmdlets.
ms.date: 03/31/2021
ms.openlocfilehash: b6e54349ec15df3327c1f0525dce1a30ad35a6ac
ms.sourcegitcommit: eeedd4472b6cc6158494296c355579791e688baa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "106104007"
---
# <a name="powershell-commands"></a><span data-ttu-id="204ac-103">Comandos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="204ac-103">PowerShell commands</span></span>

<span data-ttu-id="204ac-104">O PowerShell permite executar qualquer comando disponível no sistema, incluindo comandos específicos do PowerShell conhecidos como cmdlets (pronunciado "command-lets").</span><span class="sxs-lookup"><span data-stu-id="204ac-104">PowerShell allows you to run any command available on your system including PowerShell-specific commands known as cmdlets (pronounced command-lets).</span></span>

## <a name="what-is-a-cmdlet"></a><span data-ttu-id="204ac-105">O que é um cmdlet?</span><span class="sxs-lookup"><span data-stu-id="204ac-105">What is a cmdlet?</span></span>

<span data-ttu-id="204ac-106">O cmdlet é um comando único que participa da semântica de pipeline do PowerShell e geralmente retorna um objeto .NET.</span><span class="sxs-lookup"><span data-stu-id="204ac-106">A cmdlet is a single command that participates in the pipeline semantics of PowerShell and typically returns a .NET object.</span></span> <span data-ttu-id="204ac-107">Os cmdlets são comandos nativos do PowerShell, não executáveis autônomos.</span><span class="sxs-lookup"><span data-stu-id="204ac-107">Cmdlets are native PowerShell commands, not stand-alone executables.</span></span> <span data-ttu-id="204ac-108">Eles são coletados em módulos do PowerShell que podem ser carregados sob demanda.</span><span class="sxs-lookup"><span data-stu-id="204ac-108">Cmdlets are collected into PowerShell modules that can be loaded on demand.</span></span> <span data-ttu-id="204ac-109">Os cmdlets podem ser gravados em qualquer linguagem .NET compilada ou na própria linguagem de script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="204ac-109">Cmdlets can be written in any compiled .NET language or in the PowerShell scripting language itself.</span></span>

## <a name="cmdlet-names"></a><span data-ttu-id="204ac-110">Nomes dos cmdlets</span><span class="sxs-lookup"><span data-stu-id="204ac-110">Cmdlet names</span></span>

<span data-ttu-id="204ac-111">O PowerShell usa um par de nomes _verbo-substantivo_ para nomear cmdlets.</span><span class="sxs-lookup"><span data-stu-id="204ac-111">PowerShell uses a _Verb-Noun_ name pair to name cmdlets.</span></span> <span data-ttu-id="204ac-112">Por exemplo, o cmdlet `Get-Command` incluído no PowerShell é usado para obter todos os cmdlets registrados no shell de comando.</span><span class="sxs-lookup"><span data-stu-id="204ac-112">For example, the `Get-Command` cmdlet included in PowerShell is used to get all the cmdlets that are registered in the command shell.</span></span> <span data-ttu-id="204ac-113">O verbo identifica a ação que o cmdlet executa, e o substantivo identifica o recurso no qual o cmdlet realiza sua ação.</span><span class="sxs-lookup"><span data-stu-id="204ac-113">The verb identifies the action that the cmdlet performs, and the noun identifies the resource on which the cmdlet performs its action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="204ac-114">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="204ac-114">Next steps</span></span>

<span data-ttu-id="204ac-115">Para saber mais sobre o PowerShell e como encontrar outros cmdlets, confira o tutorial do PowerShell Bits [Descobrir o PowerShell](learn/tutorials/01-discover-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="204ac-115">To learn more about PowerShell and how to find other cmdlets, see the PowerShell Bits tutorial [Discover PowerShell](learn/tutorials/01-discover-powershell.md).</span></span>

<span data-ttu-id="204ac-116">Para saber mais sobre como criar seus cmdlets, confira os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="204ac-116">For more information about creating your own cmdlets, see the following resources:</span></span>

<span data-ttu-id="204ac-117">Cmdlets baseados em script</span><span class="sxs-lookup"><span data-stu-id="204ac-117">Script-based cmdlets</span></span>

- [<span data-ttu-id="204ac-118">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="204ac-118">about_Functions_Advanced</span></span>](/powershell/module/microsoft.powershell.core/about/about_functions_advanced)
- [<span data-ttu-id="204ac-119">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="204ac-119">about_Functions_CmdletBindingAttribute</span></span>](/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute)
- [<span data-ttu-id="204ac-120">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="204ac-120">about_Functions_Advanced_Methods</span></span>](/powershell/module/microsoft.powershell.core/about/about_functions_advanced_methods)

<span data-ttu-id="204ac-121">Cmdlets compilados (documentos do SDK do PowerShell)</span><span class="sxs-lookup"><span data-stu-id="204ac-121">Compiled cmdlets (PowerShell SDK docs)</span></span>

- [<span data-ttu-id="204ac-122">Visão geral do cmdlet</span><span class="sxs-lookup"><span data-stu-id="204ac-122">Cmdlet overview</span></span>](developer/cmdlet/cmdlet-overview.md)
