---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: 57152e9f62c34600df63a2db8e9683928e825d93
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085789"
---
# <a name="detailed-information-about-lcm-state"></a><span data-ttu-id="25da9-102">Informações detalhadas sobre o estado do LCM</span><span class="sxs-lookup"><span data-stu-id="25da9-102">Detailed information about LCM state</span></span>

<span data-ttu-id="25da9-103">Fizemos melhorias na exposição de detalhes sobre o estado do LCM.</span><span class="sxs-lookup"><span data-stu-id="25da9-103">We have made improvements in exposing details about the LCM state.</span></span> <span data-ttu-id="25da9-104">O LCMState retornado por Get-DscLocalConfigurationManager agora pode conter os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="25da9-104">The LCMState that is returned by Get-DscLocalConfigurationManager can now contain the following values:</span></span>

* <span data-ttu-id="25da9-105">**Idle**</span><span class="sxs-lookup"><span data-stu-id="25da9-105">**Idle**</span></span>
* <span data-ttu-id="25da9-106">**Busy**</span><span class="sxs-lookup"><span data-stu-id="25da9-106">**Busy**</span></span>
* <span data-ttu-id="25da9-107">**PendingReboot**</span><span class="sxs-lookup"><span data-stu-id="25da9-107">**PendingReboot**</span></span>
* <span data-ttu-id="25da9-108">**PendingConfiguration**</span><span class="sxs-lookup"><span data-stu-id="25da9-108">**PendingConfiguration**</span></span>

<span data-ttu-id="25da9-109">Também adicionamos uma propriedade de LCMStateDetail que contém mais informações sobre o estado.</span><span class="sxs-lookup"><span data-stu-id="25da9-109">We have also added an LCMStateDetail property that contains more information about the state.</span></span>
