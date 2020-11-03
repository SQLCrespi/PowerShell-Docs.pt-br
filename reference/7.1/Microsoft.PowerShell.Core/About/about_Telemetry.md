---
description: Descreve a telemetria coletada no PowerShell e como recusar.
keywords: powershell
Locale: en-US
ms.date: 08/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_telemetry?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Telemetry
ms.openlocfilehash: ef921d0feefe277c2832c0a459ae150c9a6b4acb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195919"
---
# <a name="about-telemetry"></a><span data-ttu-id="33575-104">Sobre a telemetria</span><span class="sxs-lookup"><span data-stu-id="33575-104">About Telemetry</span></span>

## <a name="short-description"></a><span data-ttu-id="33575-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="33575-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="33575-106">Descreve a telemetria coletada no PowerShell e como recusar.</span><span class="sxs-lookup"><span data-stu-id="33575-106">Describes the telemetry collected in PowerShell and how to opt-out.</span></span>

## <a name="long-description"></a><span data-ttu-id="33575-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="33575-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="33575-108">O PowerShell envia dados de telemetria básicos para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="33575-108">PowerShell sends basic telemetry data to Microsoft.</span></span>
<span data-ttu-id="33575-109">Com esses dados, podemos entender melhor os ambientes nos quais o PowerShell é usado, além de priorizar novos recursos e correções.</span><span class="sxs-lookup"><span data-stu-id="33575-109">This data allows us to better understand the environments where PowerShell is used and enables us to prioritize new features and fixes.</span></span>
<span data-ttu-id="33575-110">Os seguintes pontos de telemetria são registrados:</span><span class="sxs-lookup"><span data-stu-id="33575-110">The following telemetry points are recorded:</span></span>

- <span data-ttu-id="33575-111">Contagem de inícios do PowerShell por tipo (API vs console)</span><span class="sxs-lookup"><span data-stu-id="33575-111">Count of PowerShell Starts by type (API vs console)</span></span>
- <span data-ttu-id="33575-112">Contagem de uso exclusivo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="33575-112">Count of unique PowerShell usage</span></span>
- <span data-ttu-id="33575-113">Contagem dos seguintes tipos de execução:</span><span class="sxs-lookup"><span data-stu-id="33575-113">Count of the following execution types:</span></span>
  - <span data-ttu-id="33575-114">Aplicativo (comandos nativos)</span><span class="sxs-lookup"><span data-stu-id="33575-114">Application (native commands)</span></span>
  - <span data-ttu-id="33575-115">ExternalScript</span><span class="sxs-lookup"><span data-stu-id="33575-115">ExternalScript</span></span>
  - <span data-ttu-id="33575-116">script</span><span class="sxs-lookup"><span data-stu-id="33575-116">Script</span></span>
  - <span data-ttu-id="33575-117">Função</span><span class="sxs-lookup"><span data-stu-id="33575-117">Function</span></span>
  - <span data-ttu-id="33575-118">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="33575-118">Cmdlet</span></span>
- <span data-ttu-id="33575-119">Contagem de recursos experimentais da Microsoft habilitados ou recursos experimentais fornecidos com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="33575-119">Count of enabled Microsoft owned experimental features or experimental features shipped with PowerShell</span></span>
- <span data-ttu-id="33575-120">Contagem de sessões hospedadas</span><span class="sxs-lookup"><span data-stu-id="33575-120">Count of hosted sessions</span></span>
- <span data-ttu-id="33575-121">Contagem de módulos de propriedade da Microsoft carregados</span><span class="sxs-lookup"><span data-stu-id="33575-121">Count of Microsoft owned modules loaded</span></span>

<span data-ttu-id="33575-122">Esses dados incluem o nome do sistema operacional, a versão do sistema operacional, a versão do PowerShell e o canal de distribuição.</span><span class="sxs-lookup"><span data-stu-id="33575-122">This data includes the OS name, OS version, the PowerShell version, and the distribution channel.</span></span>

<span data-ttu-id="33575-123">Para recusar essa telemetria, defina a variável de ambiente POWERSHELL_TELEMETRY_OPTOUT como true, Yes ou 1.</span><span class="sxs-lookup"><span data-stu-id="33575-123">To opt-out of this telemetry, set the environment variable POWERSHELL_TELEMETRY_OPTOUT to true, yes, or 1.</span></span>

