---
title: Como criar um snap-in do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- snap-ins [PowerShell SDK], examples
ms.assetid: 71bd9b2c-5f2e-4aa8-b5fe-08c956540d37
caps.latest.revision: 10
ms.openlocfilehash: 43199544dc02ccae4b61053c30d6ed36576adfcf
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811325"
---
# <a name="how-to-create-a-windows-powershell-snap-in"></a><span data-ttu-id="6ef64-102">Como criar um snap-in do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ef64-102">How to Create a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="6ef64-103">Um snap-in do Windows PowerShell fornece um mecanismo para registrar conjuntos de cmdlets e outro provedor do Windows PowerShell com o Shell, estendendo assim a funcionalidade do Shell.</span><span class="sxs-lookup"><span data-stu-id="6ef64-103">A Windows PowerShell snap-in provides a mechanism for registering sets of cmdlets and another Windows PowerShell provider with the shell, thus extending the functionality of the shell.</span></span> <span data-ttu-id="6ef64-104">Um snap-in do Windows PowerShell pode registrar todos os cmdlets e provedores em um único assembly ou pode registrar uma lista específica de cmdlets e provedores.</span><span class="sxs-lookup"><span data-stu-id="6ef64-104">A Windows PowerShell snap-in can register all the cmdlets and providers in a single assembly, or it can register a specific list of cmdlets and providers.</span></span>

<span data-ttu-id="6ef64-105">Os assemblies de snap-in devem ser instalados em um diretório protegido, assim como seriam com outros sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="6ef64-105">Snap-in assemblies should be installed in a protected directory, just as they would be with other operating systems.</span></span> <span data-ttu-id="6ef64-106">Caso contrário, os usuários mal-intencionados podem substituir um assembly por código não seguro.</span><span class="sxs-lookup"><span data-stu-id="6ef64-106">Otherwise, malicious users can replace an assembly with unsafe code.</span></span>

## <a name="windows-powershell-snap-in-classes"></a><span data-ttu-id="6ef64-107">Classes de snap-in do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ef64-107">Windows PowerShell Snap-in Classes</span></span>

<span data-ttu-id="6ef64-108">Todas as classes de snap-in do Windows PowerShell derivam das classes [System. Management. Automation. PSSnapin](/dotnet/api/System.Management.Automation.PSSnapIn) ou [System. Management. Automation. CustomPSSnapIn](/dotnet/api/System.Management.Automation.CustomPSSnapIn) .</span><span class="sxs-lookup"><span data-stu-id="6ef64-108">All Windows PowerShell snap-in classes derive from the [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) or [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) classes.</span></span>

## <a name="examples"></a><span data-ttu-id="6ef64-109">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6ef64-109">Examples</span></span>

<span data-ttu-id="6ef64-110">[Escrevendo um snap-in do Windows PowerShell](./writing-a-windows-powershell-snap-in.md): Este exemplo mostra como criar um snap-in que é usado para registrar todos os cmdlets e provedores em um assembly.</span><span class="sxs-lookup"><span data-stu-id="6ef64-110">[Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md): This example shows how to create a snap-in that is used to register all the cmdlets and providers in an assembly.</span></span>

<span data-ttu-id="6ef64-111">[Escrevendo um snap-in personalizado do Windows PowerShell](./writing-a-custom-windows-powershell-snap-in.md): Este exemplo mostra como criar um snap-in personalizado que é usado para registrar um conjunto específico de cmdlets e provedores que podem ou não existir em um único assembly.</span><span class="sxs-lookup"><span data-stu-id="6ef64-111">[Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md): This example shows how to create a custom snap-in that is used to register a specific set of cmdlets and providers that might or might not exist in a single assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ef64-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6ef64-112">See Also</span></span>

[<span data-ttu-id="6ef64-113">System. Management. Automation. PSSnapIn</span><span class="sxs-lookup"><span data-stu-id="6ef64-113">System.Management.Automation.PSSnapIn</span></span>](/dotnet/api/System.Management.Automation.PSSnapIn)

[<span data-ttu-id="6ef64-114">System. Management. Automation. CustomPSSnapIn</span><span class="sxs-lookup"><span data-stu-id="6ef64-114">System.Management.Automation.Custompssnapin</span></span>](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[<span data-ttu-id="6ef64-115">Registrar cmdlets</span><span class="sxs-lookup"><span data-stu-id="6ef64-115">Registering Cmdlets</span></span>](./registering-cmdlets.md)

[<span data-ttu-id="6ef64-116">SDK do shell do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ef64-116">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
