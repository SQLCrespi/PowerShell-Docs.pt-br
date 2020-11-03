---
description: O Instrumentação de Gerenciamento do Windows (WMI) usa o modelo CIM (CIM) para representar sistemas, aplicativos, redes, dispositivos e outros componentes gerenciáveis da empresa moderna.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI
ms.openlocfilehash: d24b952ee167e51815d6d9920e95bbc9a6bb9608
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196136"
---
# <a name="about-wmi"></a><span data-ttu-id="97db9-104">Sobre o WMI</span><span class="sxs-lookup"><span data-stu-id="97db9-104">About WMI</span></span>

## <a name="short-description"></a><span data-ttu-id="97db9-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="97db9-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="97db9-106">O Instrumentação de Gerenciamento do Windows (WMI) usa o modelo CIM (CIM) para representar sistemas, aplicativos, redes, dispositivos e outros componentes gerenciáveis da empresa moderna.</span><span class="sxs-lookup"><span data-stu-id="97db9-106">Windows Management Instrumentation (WMI) uses the Common Information Model (CIM) to represent systems, applications, networks, devices, and other manageable components of the modern enterprise.</span></span>

## <a name="long-description"></a><span data-ttu-id="97db9-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="97db9-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="97db9-108">Instrumentação de Gerenciamento do Windows (WMI) é a implementação da Microsoft do WBEM (Web-Based Enterprise Management), o padrão do setor.</span><span class="sxs-lookup"><span data-stu-id="97db9-108">Windows Management Instrumentation (WMI) is Microsoft's implementation of Web-Based Enterprise Management (WBEM), the industry standard.</span></span>

<span data-ttu-id="97db9-109">O WMI clássico usa DCOM para se comunicar com dispositivos de rede para gerenciar sistemas remotos.</span><span class="sxs-lookup"><span data-stu-id="97db9-109">Classic WMI uses DCOM to communicate with networked devices to manage remote systems.</span></span> <span data-ttu-id="97db9-110">O Windows PowerShell 3,0 apresenta um modelo de provedor CIM que usa o WinRM para remover a dependência no DCOM.</span><span class="sxs-lookup"><span data-stu-id="97db9-110">Windows PowerShell 3.0 introduces a CIM provider model that uses WinRM to remove the dependency on DCOM.</span></span> <span data-ttu-id="97db9-111">Esse modelo de provedor CIM também usa novas APIs de provedor de WMI que permitem aos desenvolvedores escrever cmdlets do Windows PowerShell em código nativo (C \+ \+ ).</span><span class="sxs-lookup"><span data-stu-id="97db9-111">This CIM provider model also uses new WMI provider APIs that enable developers to write Windows PowerShell cmdlets in native code (C\+\+).</span></span>

<span data-ttu-id="97db9-112">Não confunda provedores WMI com provedores do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97db9-112">Do not confuse WMI providers with Windows PowerShell providers.</span></span> <span data-ttu-id="97db9-113">Muitos recursos do Windows têm um provedor WMI associado que expõe seus recursos de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="97db9-113">Many Windows features have an associated WMI provider that exposes their management capabilities.</span></span> <span data-ttu-id="97db9-114">Para obter provedores WMI, execute uma consulta WMI que obtém instâncias da classe __Provider WMI, como a consulta a seguir.</span><span class="sxs-lookup"><span data-stu-id="97db9-114">To get WMI providers, run a WMI query that gets instances of the __Provider WMI class, such as the following query.</span></span>

```powershell
Get-WmiObject -Class __Provider
```

## <a name="three-components-of-wmi"></a><span data-ttu-id="97db9-115">TRÊS COMPONENTES DO WMI</span><span class="sxs-lookup"><span data-stu-id="97db9-115">THREE COMPONENTS OF WMI</span></span>

<span data-ttu-id="97db9-116">Os três componentes do WMI a seguir interagem com o Windows PowerShell: namespaces, provedores e classes.</span><span class="sxs-lookup"><span data-stu-id="97db9-116">The following three components of WMI interact with Windows PowerShell: Namespaces, Providers, and Classes.</span></span>

<span data-ttu-id="97db9-117">Os namespaces do WMI organizam provedores WMI e classes WMI em grupos de componentes relacionados.</span><span class="sxs-lookup"><span data-stu-id="97db9-117">WMI Namespaces organize WMI providers and WMI classes into groups of related components.</span></span> <span data-ttu-id="97db9-118">Dessa forma, eles são semelhantes aos namespaces .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="97db9-118">In this way, they are similar to .NET Framework namespaces.</span></span>
<span data-ttu-id="97db9-119">Os namespaces não são locais físicos, mas são mais semelhantes aos bancos de dados lógicos.</span><span class="sxs-lookup"><span data-stu-id="97db9-119">Namespaces are not physical locations, but are more like logical databases.</span></span>
<span data-ttu-id="97db9-120">Todos os namespaces WMI são instâncias da classe de sistema __Namespace.</span><span class="sxs-lookup"><span data-stu-id="97db9-120">All WMI namespaces are instances of the __Namespace system class.</span></span> <span data-ttu-id="97db9-121">O namespace WMI padrão é raiz \/ CIMV2 (desde o Microsoft Windows 2000).</span><span class="sxs-lookup"><span data-stu-id="97db9-121">The default WMI namespace is Root\/CIMV2 (since Microsoft Windows 2000).</span></span> <span data-ttu-id="97db9-122">Para usar o Windows PowerShell para obter namespaces WMI na sessão atual, use um comando com o formato a seguir.</span><span class="sxs-lookup"><span data-stu-id="97db9-122">To use Windows PowerShell to get WMI namespaces in the current session, use a command with the following format.</span></span>

```powershell
Get-WmiObject -Class __Namespace
```

<span data-ttu-id="97db9-123">Para obter namespaces WMI em outros namespaces, use o parâmetro namespace para alterar o local da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="97db9-123">To get WMI namespaces in other namespaces, use the Namespace parameter to change the location of the search.</span></span> <span data-ttu-id="97db9-124">O comando a seguir localiza namespaces WMI que residem no namespace root/Cimv2/Applications.</span><span class="sxs-lookup"><span data-stu-id="97db9-124">The following command finds WMI namespaces that reside in the Root/Cimv2/Applications namespace.</span></span>

```powershell
Get-WmiObject -Class __Namespace -Namespace root/CIMv2/applications
```

<span data-ttu-id="97db9-125">Os namespaces do WMI são hierárquicos.</span><span class="sxs-lookup"><span data-stu-id="97db9-125">WMI namespaces are hierarchical.</span></span> <span data-ttu-id="97db9-126">Portanto, a obtenção de uma lista de todos os namespaces em um sistema específico requer a execução de uma consulta recursiva começando no namespace raiz.</span><span class="sxs-lookup"><span data-stu-id="97db9-126">Therefore, obtaining a list of all namespaces on a particular system requires performing a recursive query starting at the root namespace.</span></span>

<span data-ttu-id="97db9-127">Os provedores WMI expõem informações sobre objetos gerenciáveis do Windows.</span><span class="sxs-lookup"><span data-stu-id="97db9-127">WMI Providers expose information about Windows manageable objects.</span></span> <span data-ttu-id="97db9-128">Um provedor recupera dados de um componente e passa esses dados por meio do WMI para um aplicativo de gerenciamento, como o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97db9-128">A provider retrieves data from a component, and passes that data through WMI to a management application, such as Windows PowerShell.</span></span> <span data-ttu-id="97db9-129">A maioria dos provedores de WMI são provedores dinâmicos, o que significa que eles obtêm os dados dinamicamente quando solicitados por meio do aplicativo de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="97db9-129">Most WMI providers are dynamic providers, which means that they obtain the data dynamically when it is requested through the management application.</span></span>

## <a name="finding-wmi-classes"></a><span data-ttu-id="97db9-130">LOCALIZANDO CLASSES WMI</span><span class="sxs-lookup"><span data-stu-id="97db9-130">FINDING WMI CLASSES</span></span>

<span data-ttu-id="97db9-131">Em uma instalação padrão do Windows 8, há mais de 1.100 classes WMI na raiz \/ Cimv2.</span><span class="sxs-lookup"><span data-stu-id="97db9-131">In a default installation of Windows 8, there are more than 1,100 WMI classes in Root\/Cimv2.</span></span> <span data-ttu-id="97db9-132">Com essas muitas classes WMI, o desafio torna-se a identificação da classe WMI apropriada a ser usada para executar uma tarefa específica.</span><span class="sxs-lookup"><span data-stu-id="97db9-132">With this many WMI classes, the challenge becomes identifying the appropriate WMI class to use to perform a specific task.</span></span> <span data-ttu-id="97db9-133">O Windows PowerShell 3,0 fornece duas maneiras de localizar classes WMI relacionadas a um tópico específico.</span><span class="sxs-lookup"><span data-stu-id="97db9-133">Windows PowerShell 3.0 provides two ways to find WMI classes that are related to a specific topic.</span></span>

<span data-ttu-id="97db9-134">Por exemplo, para localizar classes WMI no \\ namespace WMI cimv2 raiz que estão relacionadas a discos, você pode usar uma consulta como a mostrada aqui.</span><span class="sxs-lookup"><span data-stu-id="97db9-134">For example,to find WMI classes in the root\\CIMV2 WMI namespace that are related to disks, you can use a query such as the one shown here.</span></span>

```powershell
Get-WmiObject -List *disk*
```

<span data-ttu-id="97db9-135">Para localizar classes WMI relacionadas à memória, você pode usar uma consulta como a mostrada aqui.</span><span class="sxs-lookup"><span data-stu-id="97db9-135">To find WMI classes that are related to memory, you might use a query such as the one shown here.</span></span>

```powershell
Get-WmiObject -List *memory*
```

<span data-ttu-id="97db9-136">Os cmdlets do CIM também fornecem a capacidade de descobrir classes WMI.</span><span class="sxs-lookup"><span data-stu-id="97db9-136">The CIM cmdlets also provide the ability to discover WMI classes.</span></span> <span data-ttu-id="97db9-137">Para fazer isso, use o cmdlet Get-CIMClass.</span><span class="sxs-lookup"><span data-stu-id="97db9-137">To do this, use the Get-CIMClass cmdlet.</span></span> <span data-ttu-id="97db9-138">O comando mostrado aqui lista as classes WMI relacionadas ao vídeo.</span><span class="sxs-lookup"><span data-stu-id="97db9-138">The command shown here lists WMI classes related to video.</span></span>

```powershell
Get-CimClass *video*
```

<span data-ttu-id="97db9-139">A expansão de tabulação funciona quando os namespaces WMI são alterados e, portanto, o uso da expansão de tabulação torna os namespaces de subwmi facilmente detectáveis.</span><span class="sxs-lookup"><span data-stu-id="97db9-139">Tab expansion works when changing WMI namespaces, and therefore use of tab expansion makes sub-WMI namespaces easily discoverable.</span></span> <span data-ttu-id="97db9-140">No exemplo a seguir, o cmdlet Get-CimClass lista as classes WMI relacionadas às configurações de energia.</span><span class="sxs-lookup"><span data-stu-id="97db9-140">In the following example, the Get-CimClass cmdlet lists WMI classes related to power settings.</span></span>
<span data-ttu-id="97db9-141">Para encontrá-lo, digite o `root/CIMV2/` namespace e pressione a tecla Tab várias vezes até que o namespace de energia seja exibido.</span><span class="sxs-lookup"><span data-stu-id="97db9-141">To find it, type the `root/CIMV2/` namespace and then press the Tab key several times until the power namespace appears.</span></span> <span data-ttu-id="97db9-142">Veja o código:</span><span class="sxs-lookup"><span data-stu-id="97db9-142">Here is the command:</span></span>

```powershell
Get-CimClass *power* -Namespace root/cimv2/power
```
