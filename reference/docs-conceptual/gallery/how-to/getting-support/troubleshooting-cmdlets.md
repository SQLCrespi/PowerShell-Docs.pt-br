---
ms.date: 01/25/2021
title: Cmdlets de solução de problemas
description: Este artigo fornece informações e etapas para solucionar erros usando a Galeria do PowerShell
ms.openlocfilehash: 8139147683b655b5f8532c3068387db6df12a98f
ms.sourcegitcommit: 0f003644684422e425a59b7361121e05ac772e15
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98771811"
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="d47fb-103">Cmdlets de solução de problemas</span><span class="sxs-lookup"><span data-stu-id="d47fb-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="d47fb-104">Como resolver o problema "AVISO: Falha ao baixar o pacote 'nome do seu pacote'"</span><span class="sxs-lookup"><span data-stu-id="d47fb-104">How to resolve "WARNING: Package 'your package name' failed to download" issue</span></span>

<span data-ttu-id="d47fb-105">Há relatos de que `Install-Module` ou `Update-Module` às vezes falha em alguns computadores.</span><span class="sxs-lookup"><span data-stu-id="d47fb-105">It is reported that `Install-Module` or `Update-Module` sometimes fails on some machines.</span></span> <span data-ttu-id="d47fb-106">Com base em nossa investigação, isso está relacionado à conexão de rede.</span><span class="sxs-lookup"><span data-stu-id="d47fb-106">Based on our investigation, it is something to do with the networking connection.</span></span> <span data-ttu-id="d47fb-107">Recentemente, atualizamos o provedor do NuGet para que ele possa baixar pacotes de forma confiável.</span><span class="sxs-lookup"><span data-stu-id="d47fb-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span> <span data-ttu-id="d47fb-108">Siga as instruções abaixo para instalar o build mais recente do provedor do NuGet e instalar ou atualizar seu módulo.</span><span class="sxs-lookup"><span data-stu-id="d47fb-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span> <span data-ttu-id="d47fb-109">Vamos usar o módulo “Azure” como o exemplo abaixo.</span><span class="sxs-lookup"><span data-stu-id="d47fb-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

## <a name="required-network-endpoints"></a><span data-ttu-id="d47fb-110">Pontos de extremidade de rede necessários</span><span class="sxs-lookup"><span data-stu-id="d47fb-110">Required network endpoints</span></span>

<span data-ttu-id="d47fb-111">Os cmdlets de instalação e atualização exigem acesso à Internet para se conectar aos pontos de extremidade de rede usados pela Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d47fb-111">The Install and Update cmdlets require internet access to connect to the network endpoints used by by the PowerShell Gallery.</span></span> <span data-ttu-id="d47fb-112">Verifique se suas políticas de acesso à rede permitem a conexão aos pontos de extremidade a seguir.</span><span class="sxs-lookup"><span data-stu-id="d47fb-112">Ensure that your network access policies allow you to connect to the following endpoints.</span></span>

- <span data-ttu-id="d47fb-113">`psg-prod-eastus.azureedge.net` – nome do host CDN</span><span class="sxs-lookup"><span data-stu-id="d47fb-113">`psg-prod-eastus.azureedge.net` - CDN hostname</span></span>
- <span data-ttu-id="d47fb-114">`az818661.vo.msecnd.net` – nome do host CDN</span><span class="sxs-lookup"><span data-stu-id="d47fb-114">`az818661.vo.msecnd.net` - CDN hostname</span></span>
- <span data-ttu-id="d47fb-115">`devopsgallerystorage.blob.core.windows.net` – nome do host da conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="d47fb-115">`devopsgallerystorage.blob.core.windows.net` - storage account hostname</span></span>
- <span data-ttu-id="d47fb-116">`*.powershellgallery.com` – site</span><span class="sxs-lookup"><span data-stu-id="d47fb-116">`*.powershellgallery.com` - website</span></span>
- <span data-ttu-id="d47fb-117">`go.microsoft.com` – serviço de redirecionamento</span><span class="sxs-lookup"><span data-stu-id="d47fb-117">`go.microsoft.com` - redirection service</span></span>
- <span data-ttu-id="d47fb-118">`onegetcdn.azureedge.net` – inicialize o provedor do NuGet no `PowerShellGet/PackageManagement`</span><span class="sxs-lookup"><span data-stu-id="d47fb-118">`onegetcdn.azureedge.net` - bootstrap the NuGet Provider in `PowerShellGet/PackageManagement`</span></span>

> [!NOTE]
> <span data-ttu-id="d47fb-119">Os cmdlets que interagem com a Galeria do PowerShell podem falhar com erros inesperados quando há uma interrupção dos serviços dessa Galeria.</span><span class="sxs-lookup"><span data-stu-id="d47fb-119">Cmdlets that interact with the PowerShell Gallery can fail with unexpected errors when there is an outage of the PowerShell Gallery services.</span></span> <span data-ttu-id="d47fb-120">Para ver o status atual da Galeria do PowerShell, confira a página [Status da Galeria do PowerShell](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) no GitHub.</span><span class="sxs-lookup"><span data-stu-id="d47fb-120">To see the current status of the PowerShell Gallery, see the [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) page on GitHub.</span></span>
