---
ms.date: 09/13/2016
ms.topic: reference
title: Como criar um snap-in do Windows PowerShell
description: Como criar um snap-in do Windows PowerShell
ms.openlocfilehash: 29394ebcd2f7c4a547aabcb88685ff494b2c381d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657266"
---
# <a name="how-to-create-a-windows-powershell-snap-in"></a><span data-ttu-id="f59c3-103">Como criar um snap-in do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f59c3-103">How to Create a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="f59c3-104">Um snap-in do Windows PowerShell fornece um mecanismo para registrar conjuntos de cmdlets e outro provedor do Windows PowerShell com o Shell, estendendo assim a funcionalidade do Shell.</span><span class="sxs-lookup"><span data-stu-id="f59c3-104">A Windows PowerShell snap-in provides a mechanism for registering sets of cmdlets and another Windows PowerShell provider with the shell, thus extending the functionality of the shell.</span></span> <span data-ttu-id="f59c3-105">Um snap-in do Windows PowerShell pode registrar todos os cmdlets e provedores em um único assembly ou pode registrar uma lista específica de cmdlets e provedores.</span><span class="sxs-lookup"><span data-stu-id="f59c3-105">A Windows PowerShell snap-in can register all the cmdlets and providers in a single assembly, or it can register a specific list of cmdlets and providers.</span></span>

<span data-ttu-id="f59c3-106">Os assemblies de snap-in devem ser instalados em um diretório protegido, assim como seriam com outros sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="f59c3-106">Snap-in assemblies should be installed in a protected directory, just as they would be with other operating systems.</span></span> <span data-ttu-id="f59c3-107">Caso contrário, os usuários mal-intencionados podem substituir um assembly por código não seguro.</span><span class="sxs-lookup"><span data-stu-id="f59c3-107">Otherwise, malicious users can replace an assembly with unsafe code.</span></span>

## <a name="windows-powershell-snap-in-classes"></a><span data-ttu-id="f59c3-108">Classes de snap-in do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f59c3-108">Windows PowerShell Snap-in Classes</span></span>

<span data-ttu-id="f59c3-109">Todas as classes de snap-in do Windows PowerShell derivam das classes [System. Management. Automation. PSSnapin](/dotnet/api/System.Management.Automation.PSSnapIn) ou [System. Management. Automation. CustomPSSnapIn](/dotnet/api/System.Management.Automation.CustomPSSnapIn) .</span><span class="sxs-lookup"><span data-stu-id="f59c3-109">All Windows PowerShell snap-in classes derive from the [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) or [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) classes.</span></span>

## <a name="examples"></a><span data-ttu-id="f59c3-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="f59c3-110">Examples</span></span>

<span data-ttu-id="f59c3-111">[Escrevendo um snap-in do Windows PowerShell](./writing-a-windows-powershell-snap-in.md): Este exemplo mostra como criar um snap-in que é usado para registrar todos os cmdlets e provedores em um assembly.</span><span class="sxs-lookup"><span data-stu-id="f59c3-111">[Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md): This example shows how to create a snap-in that is used to register all the cmdlets and providers in an assembly.</span></span>

<span data-ttu-id="f59c3-112">[Escrevendo um snap-in personalizado do Windows PowerShell](./writing-a-custom-windows-powershell-snap-in.md): Este exemplo mostra como criar um snap-in personalizado que é usado para registrar um conjunto específico de cmdlets e provedores que podem ou não existir em um único assembly.</span><span class="sxs-lookup"><span data-stu-id="f59c3-112">[Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md): This example shows how to create a custom snap-in that is used to register a specific set of cmdlets and providers that might or might not exist in a single assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="f59c3-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f59c3-113">See Also</span></span>

[<span data-ttu-id="f59c3-114">System. Management. Automation. PSSnapIn</span><span class="sxs-lookup"><span data-stu-id="f59c3-114">System.Management.Automation.PSSnapIn</span></span>](/dotnet/api/System.Management.Automation.PSSnapIn)

[<span data-ttu-id="f59c3-115">System. Management. Automation. CustomPSSnapIn</span><span class="sxs-lookup"><span data-stu-id="f59c3-115">System.Management.Automation.Custompssnapin</span></span>](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[<span data-ttu-id="f59c3-116">Registrar cmdlets</span><span class="sxs-lookup"><span data-stu-id="f59c3-116">Registering Cmdlets</span></span>](./registering-cmdlets.md)

[<span data-ttu-id="f59c3-117">SDK do Shell do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f59c3-117">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
