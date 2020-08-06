---
title: Como criar um snap-in do Windows PowerShell | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- snap-ins [PowerShell SDK], examples
ms.openlocfilehash: 4150ba582544d1daa4a898f0ff20b169c24a0ee0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787318"
---
# <a name="how-to-create-a-windows-powershell-snap-in"></a><span data-ttu-id="8ce47-102">Como criar um snap-in do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ce47-102">How to Create a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="8ce47-103">Um snap-in do Windows PowerShell fornece um mecanismo para registrar conjuntos de cmdlets e outro provedor do Windows PowerShell com o Shell, estendendo assim a funcionalidade do Shell.</span><span class="sxs-lookup"><span data-stu-id="8ce47-103">A Windows PowerShell snap-in provides a mechanism for registering sets of cmdlets and another Windows PowerShell provider with the shell, thus extending the functionality of the shell.</span></span> <span data-ttu-id="8ce47-104">Um snap-in do Windows PowerShell pode registrar todos os cmdlets e provedores em um único assembly ou pode registrar uma lista específica de cmdlets e provedores.</span><span class="sxs-lookup"><span data-stu-id="8ce47-104">A Windows PowerShell snap-in can register all the cmdlets and providers in a single assembly, or it can register a specific list of cmdlets and providers.</span></span>

<span data-ttu-id="8ce47-105">Os assemblies de snap-in devem ser instalados em um diretório protegido, assim como seriam com outros sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="8ce47-105">Snap-in assemblies should be installed in a protected directory, just as they would be with other operating systems.</span></span> <span data-ttu-id="8ce47-106">Caso contrário, os usuários mal-intencionados podem substituir um assembly por código não seguro.</span><span class="sxs-lookup"><span data-stu-id="8ce47-106">Otherwise, malicious users can replace an assembly with unsafe code.</span></span>

## <a name="windows-powershell-snap-in-classes"></a><span data-ttu-id="8ce47-107">Classes de snap-in do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ce47-107">Windows PowerShell Snap-in Classes</span></span>

<span data-ttu-id="8ce47-108">Todas as classes de snap-in do Windows PowerShell derivam das classes [System. Management. Automation. PSSnapin](/dotnet/api/System.Management.Automation.PSSnapIn) ou [System. Management. Automation. CustomPSSnapIn](/dotnet/api/System.Management.Automation.CustomPSSnapIn) .</span><span class="sxs-lookup"><span data-stu-id="8ce47-108">All Windows PowerShell snap-in classes derive from the [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) or [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) classes.</span></span>

## <a name="examples"></a><span data-ttu-id="8ce47-109">Exemplos</span><span class="sxs-lookup"><span data-stu-id="8ce47-109">Examples</span></span>

<span data-ttu-id="8ce47-110">[Escrevendo um snap-in do Windows PowerShell](./writing-a-windows-powershell-snap-in.md): Este exemplo mostra como criar um snap-in que é usado para registrar todos os cmdlets e provedores em um assembly.</span><span class="sxs-lookup"><span data-stu-id="8ce47-110">[Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md): This example shows how to create a snap-in that is used to register all the cmdlets and providers in an assembly.</span></span>

<span data-ttu-id="8ce47-111">[Escrevendo um snap-in personalizado do Windows PowerShell](./writing-a-custom-windows-powershell-snap-in.md): Este exemplo mostra como criar um snap-in personalizado que é usado para registrar um conjunto específico de cmdlets e provedores que podem ou não existir em um único assembly.</span><span class="sxs-lookup"><span data-stu-id="8ce47-111">[Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md): This example shows how to create a custom snap-in that is used to register a specific set of cmdlets and providers that might or might not exist in a single assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ce47-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8ce47-112">See Also</span></span>

[<span data-ttu-id="8ce47-113">System. Management. Automation. PSSnapIn</span><span class="sxs-lookup"><span data-stu-id="8ce47-113">System.Management.Automation.PSSnapIn</span></span>](/dotnet/api/System.Management.Automation.PSSnapIn)

[<span data-ttu-id="8ce47-114">System. Management. Automation. CustomPSSnapIn</span><span class="sxs-lookup"><span data-stu-id="8ce47-114">System.Management.Automation.Custompssnapin</span></span>](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[<span data-ttu-id="8ce47-115">Registrar cmdlets</span><span class="sxs-lookup"><span data-stu-id="8ce47-115">Registering Cmdlets</span></span>](./registering-cmdlets.md)

[<span data-ttu-id="8ce47-116">SDK do shell do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ce47-116">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
