---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Chave do Registro de DSCAutomationHostEnabled
description: Este artigo define os valores que podem ser definidos na chave do Registro DSCAutomationHostEnabled
ms.openlocfilehash: 50f752dd882e9b0787ed4a4cbc22731fc1d608f5
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656179"
---
# <a name="dscautomationhostenabled-registry-key"></a><span data-ttu-id="b42f2-104">Chave do Registro de DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="b42f2-104">DSCAutomationHostEnabled registry key</span></span>

> <span data-ttu-id="b42f2-105">Aplica-se a: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="b42f2-105">Applies to: Windows PowerShell 5.0</span></span>

<span data-ttu-id="b42f2-106">O DSC usa a chave de Registro **DSCAutomationHostEnabled** em **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** para habilitar a configuração do computador na inicialização.</span><span class="sxs-lookup"><span data-stu-id="b42f2-106">DSC uses the **DSCAutomationHostEnabled** registry key under **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** to enable configuration of the machine at initial boot-up.</span></span> <span data-ttu-id="b42f2-107">O **DSCAutomationHostEnabled** tem suporte para três modos:</span><span class="sxs-lookup"><span data-stu-id="b42f2-107">**DSCAutomationHostEnabled** supports three modes:</span></span>

| <span data-ttu-id="b42f2-108">O valor de DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="b42f2-108">DSCAutomationHostEnabled Value</span></span> |                                              <span data-ttu-id="b42f2-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="b42f2-109">Description</span></span>                                              |
| ------------------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="b42f2-110">0</span><span class="sxs-lookup"><span data-stu-id="b42f2-110">0</span></span>                              | <span data-ttu-id="b42f2-111">Desabilite a configuração do computador na inicialização.</span><span class="sxs-lookup"><span data-stu-id="b42f2-111">Disable configuring the machine at boot-up.</span></span>                                                           |
| <span data-ttu-id="b42f2-112">1</span><span class="sxs-lookup"><span data-stu-id="b42f2-112">1</span></span>                              | <span data-ttu-id="b42f2-113">Habilite a configuração do computador na inicialização.</span><span class="sxs-lookup"><span data-stu-id="b42f2-113">Enable configuring the machine at boot-up.</span></span>                                                            |
| <span data-ttu-id="b42f2-114">2</span><span class="sxs-lookup"><span data-stu-id="b42f2-114">2</span></span>                              | <span data-ttu-id="b42f2-115">Habilite a configuração do computador somente se o DSC estiver no estado atual ou pendente.</span><span class="sxs-lookup"><span data-stu-id="b42f2-115">Enable configuring the machine only if DSC is in pending or current state.</span></span> <span data-ttu-id="b42f2-116">Esse é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="b42f2-116">This is the default value.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b42f2-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b42f2-117">See Also</span></span>

<span data-ttu-id="b42f2-118">Para obter um exemplo de como usar esse recurso para executar as configurações na inicialização inicial, veja [Configurar uma máquina virtual na inicialização inicial usando a DSC](bootstrapDsc.md).</span><span class="sxs-lookup"><span data-stu-id="b42f2-118">For an example of how to use this feature to run configurations at initial boot-up, see [Configure a virtual machines at initial boot-up by using DSC](bootstrapDsc.md).</span></span>
