---
ms.date: 12/31/2019
keywords: powershell, cmdlet
title: A hierarquia de modelo do objeto do ISE
ms.openlocfilehash: 1ec5810fc5e7b765c2a08af83bce0415dd61a54b
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75737025"
---
# <a name="the-ise-object-model-hierarchy"></a><span data-ttu-id="8a1b4-103">A hierarquia de modelo do objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="8a1b4-103">The ISE Object Model Hierarchy</span></span>

<span data-ttu-id="8a1b4-104">Este tópico mostra a hierarquia de objetos que fazem parte do ISE (Ambiente de Script Integrado) do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a1b4-104">This topic shows the hierarchy of objects that are part of Windows PowerShell Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="8a1b4-105">O ISE do Windows PowerShell está incluído no Windows PowerShell 3.0, 4.0 e 5.1.</span><span class="sxs-lookup"><span data-stu-id="8a1b4-105">Windows PowerShell ISE is included in Windows PowerShell 3.0, 4.0, and 5.1.</span></span> <span data-ttu-id="8a1b4-106">Clique um objeto para levá-lo até a documentação de referência da classe que define o objeto.</span><span class="sxs-lookup"><span data-stu-id="8a1b4-106">Click an object to take you to the reference documentation for the class that defines the object.</span></span>

## <a name="psise-object"></a><span data-ttu-id="8a1b4-107">Objeto $psISE</span><span class="sxs-lookup"><span data-stu-id="8a1b4-107">$psISE Object</span></span>

<span data-ttu-id="8a1b4-108">O objeto `$psISE` é o [objeto raiz](The-ObjectModelRoot-Object.md) da hierarquia de objeto ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a1b4-108">The `$psISE` object is the [root object](The-ObjectModelRoot-Object.md) of the Windows PowerShell ISE object hierarchy.</span></span> <span data-ttu-id="8a1b4-109">Localizado no nível superior, disponibiliza os seguintes objetos para script:</span><span class="sxs-lookup"><span data-stu-id="8a1b4-109">Located at the top level, it makes the following objects available for scripting:</span></span>

## <a name="psisecurrentfilethe-isefile-objectmd"></a>[<span data-ttu-id="8a1b4-110">$psISE.CurrentFile</span><span class="sxs-lookup"><span data-stu-id="8a1b4-110">$psISE.CurrentFile</span></span>](The-ISEFile-Object.md)

<span data-ttu-id="8a1b4-111">O objeto `$psISE.CurrentFile` é uma instância da classe [ISEFile](The-ISEFile-Object.md).</span><span class="sxs-lookup"><span data-stu-id="8a1b4-111">The `$psISE.CurrentFile` object is an instance of the [ISEFile](The-ISEFile-Object.md) class.</span></span>

## <a name="psisecurrentpowershelltabthe-powershelltab-objectmd"></a>[<span data-ttu-id="8a1b4-112">$psISE.CurrentPowerShellTab</span><span class="sxs-lookup"><span data-stu-id="8a1b4-112">$psISE.CurrentPowerShellTab</span></span>](The-PowerShellTab-Object.md)

<span data-ttu-id="8a1b4-113">O objeto `$psISE.CurrentPowerShellTab` é uma instância da classe [PowerShellTab](The-PowerShellTab-Object.md).</span><span class="sxs-lookup"><span data-stu-id="8a1b4-113">The `$psISE.CurrentPowerShellTab` object is an instance of the [PowerShellTab](The-PowerShellTab-Object.md) class.</span></span>

## <a name="psisecurrentvisiblehorizontaltool"></a><span data-ttu-id="8a1b4-114">$psISE.CurrentVisibleHorizontalTool</span><span class="sxs-lookup"><span data-stu-id="8a1b4-114">$psISE.CurrentVisibleHorizontalTool</span></span>

<span data-ttu-id="8a1b4-115">O objeto `$psISE.CurrentVisibleHorizontalTool` é uma instância da classe [ISEAddOnTool](The-ISEAddOnTool-Object.md).</span><span class="sxs-lookup"><span data-stu-id="8a1b4-115">The `$psISE.CurrentVisibleHorizontalTool` object is an instance of the [ISEAddOnTool](The-ISEAddOnTool-Object.md) class.</span></span> <span data-ttu-id="8a1b4-116">Ele representa a ferramenta complementar instalada que está encaixada atualmente na borda superior da janela do ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a1b4-116">It represents the installed add-on tool that is currently docked to the top edge of the Windows PowerShell ISE window.</span></span>

## <a name="psisecurrentvisibleverticaltool"></a><span data-ttu-id="8a1b4-117">$psISE.CurrentVisibleVerticalTool</span><span class="sxs-lookup"><span data-stu-id="8a1b4-117">$psISE.CurrentVisibleVerticalTool</span></span>

<span data-ttu-id="8a1b4-118">O objeto `$psISE.CurrentVisibleHorizontalTool` é uma instância da classe [ISEAddOnTool](The-ISEAddOnTool-Object.md).</span><span class="sxs-lookup"><span data-stu-id="8a1b4-118">The `$psISE.CurrentVisibleHorizontalTool` object is an instance of the [ISEAddOnTool](The-ISEAddOnTool-Object.md) class.</span></span> <span data-ttu-id="8a1b4-119">Ele representa a ferramenta complementar instalada que está encaixada atualmente na borda superior direita da janela do ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a1b4-119">It represents the installed add-on tool that is currently docked to the right-hand edge of the Windows PowerShell ISE window.</span></span>

## <a name="psiseoptionsthe-iseoptions-objectmd"></a>[<span data-ttu-id="8a1b4-120">$psISE.Options</span><span class="sxs-lookup"><span data-stu-id="8a1b4-120">$psISE.Options</span></span>](The-ISEOptions-Object.md)

<span data-ttu-id="8a1b4-121">O objeto `$psISE.Options` é uma instância da classe [ISEOptions](The-ISEOptions-Object.md).</span><span class="sxs-lookup"><span data-stu-id="8a1b4-121">The `$psISE.Options` object is an instance of the [ISEOptions](The-ISEOptions-Object.md) class.</span></span> <span data-ttu-id="8a1b4-122">O objeto ISEOptions representa várias configurações para o ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a1b4-122">The ISEOptions object represents various settings for Windows PowerShell ISE.</span></span> <span data-ttu-id="8a1b4-123">Ele é uma instância da classe Microsoft.PowerShell.Host.ISE.ISEOptions.</span><span class="sxs-lookup"><span data-stu-id="8a1b4-123">It is an instance of the Microsoft.PowerShell.Host.ISE.ISEOptions class.</span></span>

## <a name="psisepowershelltabsthe-powershelltabcollection-objectmd"></a>[<span data-ttu-id="8a1b4-124">$psISE.PowerShellTabs</span><span class="sxs-lookup"><span data-stu-id="8a1b4-124">$psISE.PowerShellTabs</span></span>](The-PowerShellTabCollection-Object.md)

<span data-ttu-id="8a1b4-125">O objeto `$psISE.PowerShellTabs` é uma instância da classe [PowerShellTabCollection](The-PowerShellTabCollection-Object.md).</span><span class="sxs-lookup"><span data-stu-id="8a1b4-125">The `$psISE.PowerShellTabs` object is an instance of the [PowerShellTabCollection](The-PowerShellTabCollection-Object.md) class.</span></span> <span data-ttu-id="8a1b4-126">É uma coleção de todas as guias do PowerShell abertas no momento que representam os ambientes de execução disponíveis do Windows PowerShell no computador local ou em computadores remotos conectados.</span><span class="sxs-lookup"><span data-stu-id="8a1b4-126">It is a collection of all the currently open PowerShell tabs that represent the available Windows PowerShell run environments on the local computer or on connected remote computers.</span></span> <span data-ttu-id="8a1b4-127">Cada membro da coleção é uma instância da classe [PowerShellTab](The-PowerShellTab-Object.md).</span><span class="sxs-lookup"><span data-stu-id="8a1b4-127">Each member in the collection is an instance of the [PowerShellTab](The-PowerShellTab-Object.md) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a1b4-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8a1b4-128">See Also</span></span>

- [<span data-ttu-id="8a1b4-129">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a1b4-129">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="8a1b4-130">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="8a1b4-130">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
