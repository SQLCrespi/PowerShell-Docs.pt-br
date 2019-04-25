---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: a1e90a0b96f74decb55343292b97befaf1a85f8a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058107"
---
# <a name="class-based-dsc-resources"></a><span data-ttu-id="0d9f5-102">Recursos DSC baseados em classe</span><span class="sxs-lookup"><span data-stu-id="0d9f5-102">Class-based DSC Resources</span></span>

## <a name="defining-dsc-resources-with-classes"></a><span data-ttu-id="0d9f5-103">Definindo recursos DSC com classes</span><span class="sxs-lookup"><span data-stu-id="0d9f5-103">Defining DSC resources with classes</span></span>

<span data-ttu-id="0d9f5-104">Com base nos comentários, tornamos a criação de recursos DSC baseados em classe mais simples e mais fácil de entender.</span><span class="sxs-lookup"><span data-stu-id="0d9f5-104">Based on feedback, we’ve made authoring class-based DSC resources simpler and easier to understand.</span></span>
<span data-ttu-id="0d9f5-105">As principais diferenças entre um recurso DSC baseado em classe e um provedor de recursos DSC de cmdlet são:</span><span class="sxs-lookup"><span data-stu-id="0d9f5-105">The major differences between a class-based DSC resource and a cmdlet DSC resource provider are:</span></span>

* <span data-ttu-id="0d9f5-106">Um arquivo MOF para o esquema não é necessário.</span><span class="sxs-lookup"><span data-stu-id="0d9f5-106">A MOF file for the schema is not required.</span></span>
* <span data-ttu-id="0d9f5-107">Uma subpasta **DSCResource** na pasta do módulo não é necessária.</span><span class="sxs-lookup"><span data-stu-id="0d9f5-107">A **DSCResource** subfolder in the module folder is not required.</span></span>
* <span data-ttu-id="0d9f5-108">Um arquivo de módulo do PowerShell pode conter várias classes de recursos DSC.</span><span class="sxs-lookup"><span data-stu-id="0d9f5-108">A PowerShell module file can contain multiple DSC resource classes.</span></span>

<span data-ttu-id="0d9f5-109">Para obter mais informações, veja [Escrevendo um recurso personalizado de DSC com classes do PowerShell](https://msdn.microsoft.com/powershell/dsc/authoringresource).</span><span class="sxs-lookup"><span data-stu-id="0d9f5-109">For more information, see [Writing a custom DSC resource with PowerShell classes](https://msdn.microsoft.com/powershell/dsc/authoringresource).</span></span>
