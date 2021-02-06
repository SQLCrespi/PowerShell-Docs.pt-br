---
description: Notifica os usuários sobre a inicialização do PowerShell que uma nova versão do PowerShell foi lançada.
Locale: en-US
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_update_notifications?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Update_Notifications
ms.openlocfilehash: 1a9f8cfec15f83566fdb77175dcc1aed6d9e8c34
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598410"
---
# <a name="about-update-notifications"></a><span data-ttu-id="b3c23-103">Sobre notificações de atualização</span><span class="sxs-lookup"><span data-stu-id="b3c23-103">About Update Notifications</span></span>

## <a name="short-description"></a><span data-ttu-id="b3c23-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="b3c23-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="b3c23-105">Notifica os usuários sobre a inicialização do PowerShell que uma nova versão do PowerShell foi lançada.</span><span class="sxs-lookup"><span data-stu-id="b3c23-105">Notifies users on startup of PowerShell that a new version of PowerShell has been released.</span></span>

## <a name="long-description"></a><span data-ttu-id="b3c23-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="b3c23-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="b3c23-107">A partir do PowerShell 7,0, o PowerShell usa notificações de atualização para alertar os usuários sobre a existência de atualizações para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3c23-107">Beginning with PowerShell 7.0, PowerShell uses update notifications to alert users to the existence of updates to PowerShell.</span></span> <span data-ttu-id="b3c23-108">Uma vez por dia, o PowerShell consulta um serviço online para determinar se uma versão mais recente está disponível.</span><span class="sxs-lookup"><span data-stu-id="b3c23-108">Once per day, PowerShell queries an online service to determine if a newer version is available.</span></span>

> [!NOTE]
> <span data-ttu-id="b3c23-109">Enquanto a verificação de atualização ocorre durante a primeira sessão em um determinado período de 24 horas, por motivos de desempenho, a notificação só será mostrada no início das sessões subsequentes.</span><span class="sxs-lookup"><span data-stu-id="b3c23-109">While the update check happens during the first session in a given 24-hour period, for performance reasons, the notification will only be shown on the start of subsequent sessions.</span></span> <span data-ttu-id="b3c23-110">Além disso, por motivos de desempenho, a verificação não será iniciada até pelo menos 3 segundos após o início da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3c23-110">Also for performance reasons, the check will not start until at least 3 seconds after the session begins.</span></span>

<span data-ttu-id="b3c23-111">Por padrão, o PowerShell assina um dos dois canais de notificação diferentes dependendo de sua versão/branch.</span><span class="sxs-lookup"><span data-stu-id="b3c23-111">By default, PowerShell subscribes to one of two different notification channels depending on its version/branch.</span></span> <span data-ttu-id="b3c23-112">As versões GA (em disponibilidade geral) com suporte do PowerShell retornam apenas notificações para versões GA atualizadas.</span><span class="sxs-lookup"><span data-stu-id="b3c23-112">Supported, Generally Available (GA) versions of PowerShell only return notifications for updated GA releases.</span></span> <span data-ttu-id="b3c23-113">As versões RC (Release Candidate) e Versão prévia notificam atualizações para RC, GA e versão prévia.</span><span class="sxs-lookup"><span data-stu-id="b3c23-113">Preview and Release Candidate (RC) releases notify of updates to preview, RC, and GA releases.</span></span>

<span data-ttu-id="b3c23-114">O comportamento da notificação de atualização pode ser alterado usando a variável de ambiente `POWERSHELL_UPDATECHECK`.</span><span class="sxs-lookup"><span data-stu-id="b3c23-114">The update notification behavior can be changed using the `POWERSHELL_UPDATECHECK` environment variable.</span></span> <span data-ttu-id="b3c23-115">Os seguintes valores têm suporte:</span><span class="sxs-lookup"><span data-stu-id="b3c23-115">The following values are supported:</span></span>

- <span data-ttu-id="b3c23-116">`Off` desativa o recurso de notificação de atualização</span><span class="sxs-lookup"><span data-stu-id="b3c23-116">`Off` turns off the update notification feature</span></span>
- <span data-ttu-id="b3c23-117">`Default` é o mesmo que não definir `POWERSHELL_UPDATECHECK` :</span><span class="sxs-lookup"><span data-stu-id="b3c23-117">`Default` is the same as not defining `POWERSHELL_UPDATECHECK`:</span></span>
  - <span data-ttu-id="b3c23-118">As versões GA notificam atualizações de versões GA</span><span class="sxs-lookup"><span data-stu-id="b3c23-118">GA releases notify of updates to GA releases</span></span>
  - <span data-ttu-id="b3c23-119">As versões RC/Versão prévia notificam atualizações de GA e versão prévia</span><span class="sxs-lookup"><span data-stu-id="b3c23-119">Preview/RC releases notify of updates to GA and preview releases</span></span>
- <span data-ttu-id="b3c23-120">`LTS` Notifica apenas sobre atualizações de versões GA de manutenção de longo prazo (LTS)</span><span class="sxs-lookup"><span data-stu-id="b3c23-120">`LTS` only notifies of updates to long-term-servicing (LTS) GA releases</span></span>

<span data-ttu-id="b3c23-121">Os pontos de extremidade a seguir são usados no momento para determinar a versão mais recente de cada canal:</span><span class="sxs-lookup"><span data-stu-id="b3c23-121">The following endpoints are currently used for determining the latest version of each channel:</span></span>

- <span data-ttu-id="b3c23-122">`LTS`: https://aka.ms/pwsh-buildinfo-lts</span><span class="sxs-lookup"><span data-stu-id="b3c23-122">`LTS`: https://aka.ms/pwsh-buildinfo-lts</span></span>
- <span data-ttu-id="b3c23-123">`Stable`: https://aka.ms/pwsh-buildinfo-stable</span><span class="sxs-lookup"><span data-stu-id="b3c23-123">`Stable`: https://aka.ms/pwsh-buildinfo-stable</span></span>
- <span data-ttu-id="b3c23-124">`Preview`: https://aka.ms/pwsh-buildinfo-preview</span><span class="sxs-lookup"><span data-stu-id="b3c23-124">`Preview`: https://aka.ms/pwsh-buildinfo-preview</span></span>

<span data-ttu-id="b3c23-125">A notificação de atualização não fornece nenhuma maneira de atualizar automaticamente o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3c23-125">The update notification doesn't provide any way to automatically update PowerShell.</span></span> <span data-ttu-id="b3c23-126">No futuro, pode haver mais instruções ou recursos para atualizar de dentro do PowerShell, mas hoje em dia, você deve usar o mesmo mecanismo de instalação usado para instalar o PowerShell para atualizá-lo.</span><span class="sxs-lookup"><span data-stu-id="b3c23-126">In the future, there may be more instructions or capabilities to update from within PowerShell, but today, you should use the same install mechanism you used to install PowerShell to update it.</span></span>

