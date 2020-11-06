---
ms.date: 08/25/2017
title: O objeto ObjectModelRoot
description: O objeto $psISE, que é o objeto raiz da entidade de segurança no ISE do PowerShell, é uma instância da classe Microsoft.PowerShell.Host.ISE.ObjectModelRoot. Este tópico descreve as propriedades do objeto ObjectModelRoot.
ms.openlocfilehash: c8ae703c2663256ca037090fd3b1eb239cfc431a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660939"
---
# <a name="the-objectmodelroot-object"></a><span data-ttu-id="606da-104">O objeto ObjectModelRoot</span><span class="sxs-lookup"><span data-stu-id="606da-104">The ObjectModelRoot Object</span></span>

<span data-ttu-id="606da-105">O objeto `$psISE`, que é o objeto raiz da entidade de segurança no ISE (Ambiente de Script Integrado) do Windows PowerShell&reg;, é uma instância da classe Microsoft.PowerShell.Host.ISE.ObjectModelRoot.</span><span class="sxs-lookup"><span data-stu-id="606da-105">The `$psISE` object, which is the principal root object in Windows PowerShell&reg; Integrated Scripting Environment (ISE) is an instance of the Microsoft.PowerShell.Host.ISE.ObjectModelRoot class.</span></span> <span data-ttu-id="606da-106">Este tópico descreve as propriedades do objeto **ObjectModelRoot**.</span><span class="sxs-lookup"><span data-stu-id="606da-106">This topic describes the properties of the **ObjectModelRoot** object.</span></span>

## <a name="properties"></a><span data-ttu-id="606da-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="606da-107">Properties</span></span>

### <a name="currentfile"></a><span data-ttu-id="606da-108">CurrentFile</span><span class="sxs-lookup"><span data-stu-id="606da-108">CurrentFile</span></span>

> <span data-ttu-id="606da-109">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="606da-109">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="606da-110">A propriedade somente leitura que obtém o arquivo, que é associada ao objeto host que atualmente tem o foco.</span><span class="sxs-lookup"><span data-stu-id="606da-110">The read-only property that gets the file, which is associated with this host object that currently has the focus.</span></span>

### <a name="currentpowershelltab"></a><span data-ttu-id="606da-111">CurrentPowerShellTab</span><span class="sxs-lookup"><span data-stu-id="606da-111">CurrentPowerShellTab</span></span>

> <span data-ttu-id="606da-112">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="606da-112">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="606da-113">A propriedade somente leitura que obtém a guia do PowerShell que tem o foco.</span><span class="sxs-lookup"><span data-stu-id="606da-113">The read-only property that gets the PowerShell tab that has the focus.</span></span>

### <a name="currentvisiblehorizontaltool"></a><span data-ttu-id="606da-114">CurrentVisibleHorizontalTool</span><span class="sxs-lookup"><span data-stu-id="606da-114">CurrentVisibleHorizontalTool</span></span>

> <span data-ttu-id="606da-115">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="606da-115">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="606da-116">A propriedade somente leitura que obtém a ferramenta complementar do ISE do Windows PowerShell visível no momento que está localizada no painel de ferramentas horizontal na parte inferior do editor.</span><span class="sxs-lookup"><span data-stu-id="606da-116">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the horizontal tool pane at the bottom of the editor.</span></span>

### <a name="currentvisibleverticaltool"></a><span data-ttu-id="606da-117">CurrentVisibleVerticalTool</span><span class="sxs-lookup"><span data-stu-id="606da-117">CurrentVisibleVerticalTool</span></span>

> <span data-ttu-id="606da-118">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="606da-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="606da-119">A propriedade somente leitura que obtém a ferramenta complementar do ISE do Windows PowerShell visível no momento que está localizada no painel de ferramentas vertical no lado direito do editor.</span><span class="sxs-lookup"><span data-stu-id="606da-119">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the vertical tool pane on the right side of the editor.</span></span>

### <a name="options"></a><span data-ttu-id="606da-120">Opções</span><span class="sxs-lookup"><span data-stu-id="606da-120">Options</span></span>

> <span data-ttu-id="606da-121">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="606da-121">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="606da-122">A propriedade somente leitura que obtém as várias opções que podem alterar as configurações no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="606da-122">The read-only property that gets the various options that can change settings in Windows PowerShell ISE.</span></span>

### <a name="powershelltabs"></a><span data-ttu-id="606da-123">PowerShellTabs</span><span class="sxs-lookup"><span data-stu-id="606da-123">PowerShellTabs</span></span>

> <span data-ttu-id="606da-124">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="606da-124">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="606da-125">A propriedade somente leitura que obtém a coleção de guias do PowerShell, que está aberta no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="606da-125">The read-only property that gets the collection of the PowerShell tabs, which are open in Windows PowerShell ISE.</span></span> <span data-ttu-id="606da-126">Por padrão, esse objeto contém uma guia do PowerShell. No entanto, é possível adicionar mais guias do PowerShell a esse objeto usando scripts ou usando os menus no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="606da-126">By default, this object contains one PowerShell tab. However, you can add more PowerShell tabs to this object by using scripts or by using the menus in Windows PowerShell ISE.</span></span>

## <a name="see-also"></a><span data-ttu-id="606da-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="606da-127">See Also</span></span>

- [<span data-ttu-id="606da-128">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="606da-128">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="606da-129">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="606da-129">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
