---
description: Descreve a telemetria coletada no PowerShell e como recusar.
Locale: en-US
ms.date: 08/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_telemetry?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Telemetry
ms.openlocfilehash: 677d43b405fdc92e6b68d6e903847b11cb671a2c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603559"
---
# <a name="about-telemetry"></a><span data-ttu-id="ecfaf-103">Sobre a telemetria</span><span class="sxs-lookup"><span data-stu-id="ecfaf-103">About Telemetry</span></span>

## <a name="short-description"></a><span data-ttu-id="ecfaf-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="ecfaf-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="ecfaf-105">Descreve a telemetria coletada no PowerShell e como recusar.</span><span class="sxs-lookup"><span data-stu-id="ecfaf-105">Describes the telemetry collected in PowerShell and how to opt-out.</span></span>

## <a name="long-description"></a><span data-ttu-id="ecfaf-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="ecfaf-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="ecfaf-107">O PowerShell envia dados de telemetria básicos para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ecfaf-107">PowerShell sends basic telemetry data to Microsoft.</span></span>
<span data-ttu-id="ecfaf-108">Com esses dados, podemos entender melhor os ambientes nos quais o PowerShell é usado, além de priorizar novos recursos e correções.</span><span class="sxs-lookup"><span data-stu-id="ecfaf-108">This data allows us to better understand the environments where PowerShell is used and enables us to prioritize new features and fixes.</span></span>
<span data-ttu-id="ecfaf-109">Os seguintes pontos de telemetria são registrados:</span><span class="sxs-lookup"><span data-stu-id="ecfaf-109">The following telemetry points are recorded:</span></span>

- <span data-ttu-id="ecfaf-110">Contagem de inícios do PowerShell por tipo (API vs console)</span><span class="sxs-lookup"><span data-stu-id="ecfaf-110">Count of PowerShell Starts by type (API vs console)</span></span>
- <span data-ttu-id="ecfaf-111">Contagem de uso exclusivo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ecfaf-111">Count of unique PowerShell usage</span></span>
- <span data-ttu-id="ecfaf-112">Contagem dos seguintes tipos de execução:</span><span class="sxs-lookup"><span data-stu-id="ecfaf-112">Count of the following execution types:</span></span>
  - <span data-ttu-id="ecfaf-113">Aplicativo (comandos nativos)</span><span class="sxs-lookup"><span data-stu-id="ecfaf-113">Application (native commands)</span></span>
  - <span data-ttu-id="ecfaf-114">ExternalScript</span><span class="sxs-lookup"><span data-stu-id="ecfaf-114">ExternalScript</span></span>
  - <span data-ttu-id="ecfaf-115">Script</span><span class="sxs-lookup"><span data-stu-id="ecfaf-115">Script</span></span>
  - <span data-ttu-id="ecfaf-116">Função</span><span class="sxs-lookup"><span data-stu-id="ecfaf-116">Function</span></span>
  - <span data-ttu-id="ecfaf-117">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ecfaf-117">Cmdlet</span></span>
- <span data-ttu-id="ecfaf-118">Contagem de recursos experimentais da Microsoft habilitados ou recursos experimentais fornecidos com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ecfaf-118">Count of enabled Microsoft owned experimental features or experimental features shipped with PowerShell</span></span>
- <span data-ttu-id="ecfaf-119">Contagem de sessões hospedadas</span><span class="sxs-lookup"><span data-stu-id="ecfaf-119">Count of hosted sessions</span></span>
- <span data-ttu-id="ecfaf-120">Contagem de módulos de propriedade da Microsoft carregados</span><span class="sxs-lookup"><span data-stu-id="ecfaf-120">Count of Microsoft owned modules loaded</span></span>

<span data-ttu-id="ecfaf-121">Esses dados incluem o nome do sistema operacional, a versão do sistema operacional, a versão do PowerShell e o canal de distribuição.</span><span class="sxs-lookup"><span data-stu-id="ecfaf-121">This data includes the OS name, OS version, the PowerShell version, and the distribution channel.</span></span>

<span data-ttu-id="ecfaf-122">Para recusar essa telemetria, defina a variável de ambiente POWERSHELL_TELEMETRY_OPTOUT como true, Yes ou 1.</span><span class="sxs-lookup"><span data-stu-id="ecfaf-122">To opt-out of this telemetry, set the environment variable POWERSHELL_TELEMETRY_OPTOUT to true, yes, or 1.</span></span>

