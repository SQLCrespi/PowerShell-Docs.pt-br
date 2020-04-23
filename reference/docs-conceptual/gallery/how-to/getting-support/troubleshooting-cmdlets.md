---
ms.date: 06/12/2017
contributor: manikb
keywords: galeria,powershell,cmdlet,psget
title: Cmdlets de solução de problemas
ms.openlocfilehash: d87c680472c2588efbfe8b3c4d6f2dbee6883a0c
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "72352103"
---
# <a name="troubleshooting-cmdlets"></a><span data-ttu-id="44350-103">Cmdlets de solução de problemas</span><span class="sxs-lookup"><span data-stu-id="44350-103">Troubleshooting cmdlets</span></span>

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a><span data-ttu-id="44350-104">Como resolver o problema "AVISO: Falha ao baixar o pacote 'nome do seu pacote'"</span><span class="sxs-lookup"><span data-stu-id="44350-104">How to resolve "WARNING: Package 'your package name' failed to download" issue</span></span>

<span data-ttu-id="44350-105">Há relatos de que `Install-Module` ou `Update-Module` às vezes falha em alguns computadores.</span><span class="sxs-lookup"><span data-stu-id="44350-105">It is reported that `Install-Module` or `Update-Module` sometimes fails on some machines.</span></span> <span data-ttu-id="44350-106">Com base em nossa investigação, isso está relacionado à conexão de rede.</span><span class="sxs-lookup"><span data-stu-id="44350-106">Based on our investigation, it is something to do with the networking connection.</span></span> <span data-ttu-id="44350-107">Recentemente, atualizamos o provedor do NuGet para que ele possa baixar pacotes de forma confiável.</span><span class="sxs-lookup"><span data-stu-id="44350-107">Recently we updated NuGet provider so that it can reliably download packages.</span></span> <span data-ttu-id="44350-108">Siga as instruções abaixo para instalar o build mais recente do provedor do NuGet e instalar ou atualizar seu módulo.</span><span class="sxs-lookup"><span data-stu-id="44350-108">You can follow the instructions below to install the latest build of NuGet provider and then install or update your module.</span></span> <span data-ttu-id="44350-109">Vamos usar o módulo “Azure” como o exemplo abaixo.</span><span class="sxs-lookup"><span data-stu-id="44350-109">Let's use 'Azure' module as an example below.</span></span>

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

### <a name="required-network-endpoints"></a><span data-ttu-id="44350-110">Pontos de extremidade de rede necessários</span><span class="sxs-lookup"><span data-stu-id="44350-110">Required network endpoints</span></span>

<span data-ttu-id="44350-111">Os cmdlets de instalação e atualização exigem acesso à Internet para se conectar aos pontos de extremidade de rede usados pela Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44350-111">The Install and Update cmdlets require internet access to connect to the network endpoints used by by the PowerShell Gallery.</span></span> <span data-ttu-id="44350-112">Verifique se suas políticas de acesso à rede permitem a conexão aos pontos de extremidade a seguir.</span><span class="sxs-lookup"><span data-stu-id="44350-112">Ensure that your network access policies allow you to connect to the following endpoints.</span></span>

- <span data-ttu-id="44350-113">oneget.org</span><span class="sxs-lookup"><span data-stu-id="44350-113">oneget.org</span></span>
- <span data-ttu-id="44350-114">go.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="44350-114">go.microsoft.com</span></span>
- <span data-ttu-id="44350-115">az818661.vo.msecnd.net</span><span class="sxs-lookup"><span data-stu-id="44350-115">az818661.vo.msecnd.net</span></span>
- <span data-ttu-id="44350-116">www.powershellgallery.com</span><span class="sxs-lookup"><span data-stu-id="44350-116">www.powershellgallery.com</span></span>
- <span data-ttu-id="44350-117">devopsgallerystorage.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="44350-117">devopsgallerystorage.blob.core.windows.net</span></span>
