---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Chave do Registro de DSCAutomationHostEnabled
ms.openlocfilehash: 0f35a798e5b7d51fdfb66e4e79ceab0e36ccea5b
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808326"
---
# <a name="dscautomationhostenabled-registry-key"></a><span data-ttu-id="48353-103">Chave do Registro de DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="48353-103">DSCAutomationHostEnabled registry key</span></span>

> <span data-ttu-id="48353-104">Aplica-se a: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="48353-104">Applies to: Windows PowerShell 5.0</span></span>

<span data-ttu-id="48353-105">O DSC usa a chave de Registro **DSCAutomationHostEnabled** em **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** para habilitar a configuração do computador na inicialização.</span><span class="sxs-lookup"><span data-stu-id="48353-105">DSC uses the **DSCAutomationHostEnabled** registry key under **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System** to enable configuration of the machine at initial boot-up.</span></span>
<span data-ttu-id="48353-106">O **DSCAutomationHostEnabled** tem suporte para três modos:</span><span class="sxs-lookup"><span data-stu-id="48353-106">**DSCAutomationHostEnabled** supports three modes:</span></span>

|  <span data-ttu-id="48353-107">O valor de DSCAutomationHostEnabled</span><span class="sxs-lookup"><span data-stu-id="48353-107">DSCAutomationHostEnabled Value</span></span>  |  <span data-ttu-id="48353-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="48353-108">Description</span></span>   |
|---|---|
<span data-ttu-id="48353-109">0</span><span class="sxs-lookup"><span data-stu-id="48353-109">0</span></span> | <span data-ttu-id="48353-110">Desabilite a configuração do computador na inicialização.</span><span class="sxs-lookup"><span data-stu-id="48353-110">Disable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="48353-111">1</span><span class="sxs-lookup"><span data-stu-id="48353-111">1</span></span> | <span data-ttu-id="48353-112">Habilite a configuração do computador na inicialização.</span><span class="sxs-lookup"><span data-stu-id="48353-112">Enable configuring the machine at boot-up.</span></span> |
<span data-ttu-id="48353-113">2</span><span class="sxs-lookup"><span data-stu-id="48353-113">2</span></span> | <span data-ttu-id="48353-114">Habilite a configuração do computador somente se o DSC estiver no estado atual ou pendente.</span><span class="sxs-lookup"><span data-stu-id="48353-114">Enable configuring the machine only if DSC is in pending or current state.</span></span> <span data-ttu-id="48353-115">Esse é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="48353-115">This is the default value.</span></span> |

## <a name="see-also"></a><span data-ttu-id="48353-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48353-116">See Also</span></span>

<span data-ttu-id="48353-117">Para obter um exemplo de como usar esse recurso para executar as configurações na inicialização inicial, veja [Configurar uma máquina virtual na inicialização inicial usando a DSC](bootstrapDsc.md).</span><span class="sxs-lookup"><span data-stu-id="48353-117">For an example of how to use this feature to run configurations at initial boot-up, see [Configure a virtual machines at initial boot-up by using DSC](bootstrapDsc.md).</span></span>
