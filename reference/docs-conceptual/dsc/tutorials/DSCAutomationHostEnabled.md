---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Chave do Registro de DSCAutomationHostEnabled
ms.openlocfilehash: 2bccd2738b9f61efd656fdf0f98cf71affdbe781
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954263"
---
><span data-ttu-id="2e68e-103">Aplica-se a: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="2e68e-103">Applies to: Windows PowerShell 5.0</span></span>

# <a name="dscautomationhostenabled-registry-key"></a><span data-ttu-id="2e68e-104">Chave do Registro de DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="2e68e-104">DSCAutomationHostEnabled registry key</span></span>

<span data-ttu-id="2e68e-105">O DSC usa a chave de Registro **DSCAutomationHostEnabled** em **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** para habilitar a configuração do computador na inicialização.</span><span class="sxs-lookup"><span data-stu-id="2e68e-105">DSC uses the **DSCAutomationHostEnabled** registry key under **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** to enable configuration of the machine at initial boot-up.</span></span>
<span data-ttu-id="2e68e-106">O **DSCAutomationHostEnabled** tem suporte para três modos:</span><span class="sxs-lookup"><span data-stu-id="2e68e-106">**DSCAutomationHostEnabled** supports three modes:</span></span>

|  <span data-ttu-id="2e68e-107">O valor de DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="2e68e-107">DSCAutomationHostEnabled Value</span></span>  |  <span data-ttu-id="2e68e-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="2e68e-108">Description</span></span>   |
|---|---|
<span data-ttu-id="2e68e-109">0</span><span class="sxs-lookup"><span data-stu-id="2e68e-109">0</span></span> | <span data-ttu-id="2e68e-110">Desabilite a configuração do computador na inicialização.</span><span class="sxs-lookup"><span data-stu-id="2e68e-110">Disable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="2e68e-111">1</span><span class="sxs-lookup"><span data-stu-id="2e68e-111">1</span></span> | <span data-ttu-id="2e68e-112">Habilite a configuração do computador na inicialização.</span><span class="sxs-lookup"><span data-stu-id="2e68e-112">Enable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="2e68e-113">2</span><span class="sxs-lookup"><span data-stu-id="2e68e-113">2</span></span> | <span data-ttu-id="2e68e-114">Habilite a configuração do computador somente se o DSC estiver no estado atual ou pendente.</span><span class="sxs-lookup"><span data-stu-id="2e68e-114">Enable configuring the machine only if DSC is in pending or current state.</span></span> <span data-ttu-id="2e68e-115">Este é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="2e68e-115">This is the default value.</span></span> |

## <a name="see-also"></a><span data-ttu-id="2e68e-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2e68e-116">See Also</span></span>

<span data-ttu-id="2e68e-117">Para obter um exemplo de como usar esse recurso para executar as configurações na inicialização inicial, veja [Configurar uma máquina virtual na inicialização inicial usando a DSC](bootstrapDsc.md).</span><span class="sxs-lookup"><span data-stu-id="2e68e-117">For an example of how to use this feature to run configurations at initial boot-up, see [Configure a virtual machines at initial boot-up by using DSC](bootstrapDsc.md).</span></span>
