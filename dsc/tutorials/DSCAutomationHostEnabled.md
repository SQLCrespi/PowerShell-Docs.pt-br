---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Chave do Registro de DSCAutomationHostEnabled
ms.openlocfilehash: 2bccd2738b9f61efd656fdf0f98cf71affdbe781
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076459"
---
><span data-ttu-id="ba7a3-103">Aplica-se a: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="ba7a3-103">Applies to: Windows PowerShell 5.0</span></span>

# <a name="dscautomationhostenabled-registry-key"></a><span data-ttu-id="ba7a3-104">Chave do Registro de DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="ba7a3-104">DSCAutomationHostEnabled registry key</span></span>

<span data-ttu-id="ba7a3-105">O DSC usa a chave de Registro **DSCAutomationHostEnabled** em **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** para habilitar a configuração do computador na inicialização.</span><span class="sxs-lookup"><span data-stu-id="ba7a3-105">DSC uses the **DSCAutomationHostEnabled** registry key under **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** to enable configuration of the machine at initial boot-up.</span></span>
<span data-ttu-id="ba7a3-106">O **DSCAutomationHostEnabled** tem suporte para três modos:</span><span class="sxs-lookup"><span data-stu-id="ba7a3-106">**DSCAutomationHostEnabled** supports three modes:</span></span>

|  <span data-ttu-id="ba7a3-107">O valor de DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="ba7a3-107">DSCAutomationHostEnabled Value</span></span>  |  <span data-ttu-id="ba7a3-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="ba7a3-108">Description</span></span>   |
|---|---|
<span data-ttu-id="ba7a3-109">0</span><span class="sxs-lookup"><span data-stu-id="ba7a3-109">0</span></span> | <span data-ttu-id="ba7a3-110">Desabilite a configuração do computador na inicialização.</span><span class="sxs-lookup"><span data-stu-id="ba7a3-110">Disable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="ba7a3-111">1</span><span class="sxs-lookup"><span data-stu-id="ba7a3-111">1</span></span> | <span data-ttu-id="ba7a3-112">Habilite a configuração do computador na inicialização.</span><span class="sxs-lookup"><span data-stu-id="ba7a3-112">Enable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="ba7a3-113">2</span><span class="sxs-lookup"><span data-stu-id="ba7a3-113">2</span></span> | <span data-ttu-id="ba7a3-114">Habilite a configuração do computador somente se o DSC estiver no estado atual ou pendente.</span><span class="sxs-lookup"><span data-stu-id="ba7a3-114">Enable configuring the machine only if DSC is in pending or current state.</span></span> <span data-ttu-id="ba7a3-115">Este é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="ba7a3-115">This is the default value.</span></span> |

## <a name="see-also"></a><span data-ttu-id="ba7a3-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ba7a3-116">See Also</span></span>

<span data-ttu-id="ba7a3-117">Para obter um exemplo de como usar esse recurso para executar as configurações na inicialização inicial, veja [Configurar uma máquina virtual na inicialização inicial usando a DSC](bootstrapDsc.md).</span><span class="sxs-lookup"><span data-stu-id="ba7a3-117">For an example of how to use this feature to run configurations at initial boot-up, see [Configure a virtual machines at initial boot-up by using DSC](bootstrapDsc.md).</span></span>
