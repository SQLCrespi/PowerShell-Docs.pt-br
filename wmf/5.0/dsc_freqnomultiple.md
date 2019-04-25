---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: 23a5c8832f7c2888880a1ee846d75feaa95ebe47
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058396"
---
# <a name="frequencies-for-refreshmode-and-configurationmode-dont-need-to-be-multiples-of-each-other"></a><span data-ttu-id="7fc52-102">As frequências de RefreshMode e ConfigurationMode não precisam ser múltiplos um do outro</span><span class="sxs-lookup"><span data-stu-id="7fc52-102">Frequencies for RefreshMode and ConfigurationMode don't need to be multiples of each other</span></span>

<span data-ttu-id="7fc52-103">Na versão anterior do DSC, o LCM trataria `RefreshFrequencyMins` e `ConfigurationModeFrequencyMins` como múltiplos um do outro.</span><span class="sxs-lookup"><span data-stu-id="7fc52-103">In the previous version of DSC, the LCM would treat `RefreshFrequencyMins` and `ConfigurationModeFrequencyMins` as multiples of each other.</span></span> <span data-ttu-id="7fc52-104">No WMF 5.0 RTM, essas propriedades são processadas de forma independente uma da outra.</span><span class="sxs-lookup"><span data-stu-id="7fc52-104">In WMF 5.0 RTM, these properties are processed independent of each other.</span></span>

<span data-ttu-id="7fc52-105">Para obter mais informações, veja [Configurando o Gerenciador de Configurações Local](https://msdn.microsoft.com/powershell/dsc/metaconfig).</span><span class="sxs-lookup"><span data-stu-id="7fc52-105">For more information, see [Configuring the Local Configuration Manager](https://msdn.microsoft.com/powershell/dsc/metaconfig).</span></span>
