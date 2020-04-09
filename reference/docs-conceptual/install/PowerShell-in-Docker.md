---
title: Como usar o PowerShell no Docker
description: Como usar o PowerShell pré-instalado em uma imagem do Docker.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/03/2020
ms.openlocfilehash: b16a31a04ca863ab55c7c9718b1a1a973e61ee46
ms.sourcegitcommit: f55da6dea4b58a2cd13c7be7c24c07341f177b71
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "80646366"
---
# <a name="using-powershell-in-docker"></a><span data-ttu-id="c4faa-103">Como usar o PowerShell no Docker</span><span class="sxs-lookup"><span data-stu-id="c4faa-103">Using PowerShell in Docker</span></span>

<span data-ttu-id="c4faa-104">Publicamos imagens do Docker com o PowerShell pré-instalado.</span><span class="sxs-lookup"><span data-stu-id="c4faa-104">We publish Docker images with PowerShell preinstalled.</span></span> <span data-ttu-id="c4faa-105">Este artigo mostra como começar a usar o PowerShell no contêiner do Docker.</span><span class="sxs-lookup"><span data-stu-id="c4faa-105">This article shows you how to get started using PowerShell in the Docker container.</span></span>

## <a name="finding-available-images"></a><span data-ttu-id="c4faa-106">Localizar imagens disponíveis</span><span class="sxs-lookup"><span data-stu-id="c4faa-106">Finding available images</span></span>

<span data-ttu-id="c4faa-107">As imagens liberadas exigem o Docker 17.05 ou mais recente.</span><span class="sxs-lookup"><span data-stu-id="c4faa-107">The released images require Docker 17.05 or newer.</span></span> <span data-ttu-id="c4faa-108">Também é esperado que você possa executar o Docker sem `sudo` ou direitos administrativos locais.</span><span class="sxs-lookup"><span data-stu-id="c4faa-108">It is also expected that you are able to run Docker without `sudo` or local administrative rights.</span></span> <span data-ttu-id="c4faa-109">Siga as [instruções][install] oficiais do Docker para instalar o `docker` corretamente.</span><span class="sxs-lookup"><span data-stu-id="c4faa-109">Please follow Docker's official [instructions][install] to install `docker` correctly.</span></span>

<span data-ttu-id="c4faa-110">Os contêineres de versão derivam da imagem de distribuição oficial, como `centos:7`, instalam dependências e finalmente instalam o pacote do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4faa-110">The release containers derive from the official distribution image, such as `centos:7`, then install dependencies, and finally install the PowerShell package.</span></span>

<span data-ttu-id="c4faa-111">Esses contêineres residem em [hub.docker.com/r/microsoft/powershell][docker-release].</span><span class="sxs-lookup"><span data-stu-id="c4faa-111">These containers live at [hub.docker.com/r/microsoft/powershell][docker-release].</span></span>

<span data-ttu-id="c4faa-112">Para obter mais informações sobre essas imagens do Docker, visite o repositório [PowerShell-Docker][PowerShell-Docker] no GitHub.</span><span class="sxs-lookup"><span data-stu-id="c4faa-112">For more information about these Docker images, visit the [PowerShell-Docker][PowerShell-Docker] repository on GitHub.</span></span>

## <a name="using-powershell-in-a-container"></a><span data-ttu-id="c4faa-113">Usar o PowerShell em um contêiner</span><span class="sxs-lookup"><span data-stu-id="c4faa-113">Using PowerShell in a container</span></span>

<span data-ttu-id="c4faa-114">As etapas a seguir mostram os comandos do Docker necessários para baixar a imagem e iniciar uma sessão interativa do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4faa-114">The following steps show the Docker commands required to download the image and start an interactive PowerShell session.</span></span>

```console
docker run -it mcr.microsoft.com/powershell
```

### <a name="remove-the-image-when-no-longer-needed"></a><span data-ttu-id="c4faa-115">Remover a imagem quando não for mais necessária</span><span class="sxs-lookup"><span data-stu-id="c4faa-115">Remove the image when no longer needed</span></span>

<span data-ttu-id="c4faa-116">O comando a seguir é usado para excluir a imagem do Docker quando você não precisa mais dela.</span><span class="sxs-lookup"><span data-stu-id="c4faa-116">The following command is used to delete the Docker image when you no longer need it.</span></span>

```console
docker rmi mcr.microsoft.com/powershell
```

## <a name="legal-and-licensing"></a><span data-ttu-id="c4faa-117">Informações legais e licenciamento</span><span class="sxs-lookup"><span data-stu-id="c4faa-117">Legal and Licensing</span></span>

<span data-ttu-id="c4faa-118">O PowerShell está licenciado nos termos da [licença MIT][].</span><span class="sxs-lookup"><span data-stu-id="c4faa-118">PowerShell is licensed under the [MIT license][].</span></span>

### <a name="windows-docker-file-and-image-licenses"></a><span data-ttu-id="c4faa-119">Licenças de arquivo e imagem do Docker do Windows</span><span class="sxs-lookup"><span data-stu-id="c4faa-119">Windows Docker File and Image Licenses</span></span>

<span data-ttu-id="c4faa-120">Ao solicitar e usar os contêineres Imagem do Sistema Operacional do Contêiner para Windows, você reconhece, entende e concorda com os Termos de Licença Complementares disponíveis no hub do Docker:</span><span class="sxs-lookup"><span data-stu-id="c4faa-120">By requesting and using the Container OS Image for Windows containers, you acknowledge, understand, and consent to the Supplemental License Terms available on Docker hub:</span></span>

- <span data-ttu-id="c4faa-121">[Window Server Core][Window Server Core]</span><span class="sxs-lookup"><span data-stu-id="c4faa-121">[Window Server Core][Window Server Core]</span></span>
- <span data-ttu-id="c4faa-122">[Nano Server][Nano Server]</span><span class="sxs-lookup"><span data-stu-id="c4faa-122">[Nano Server][Nano Server]</span></span>

### <a name="telemetry"></a><span data-ttu-id="c4faa-123">Telemetria</span><span class="sxs-lookup"><span data-stu-id="c4faa-123">Telemetry</span></span>

<span data-ttu-id="c4faa-124">Por padrão, o PowerShell coleta telemetria limitada sem informações de identificação pessoal para ajudar no desenvolvimento de versões futuras do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4faa-124">By default, PowerShell collects limited telemetry without personally identifiable information to help aid development of future versions of PowerShell.</span></span> <span data-ttu-id="c4faa-125">Para desativar o envio de telemetria, crie uma variável de ambiente chamada `POWERSHELL_TELEMETRY_OPTOUT` definida como um valor de `1` antes de iniciar o PowerShell a partir do local instalado.</span><span class="sxs-lookup"><span data-stu-id="c4faa-125">To opt-out of sending telemetry, create an environment variable called `POWERSHELL_TELEMETRY_OPTOUT` set to a value of `1` before starting PowerShell from the installed location.</span></span> <span data-ttu-id="c4faa-126">A telemetria que coletamos se enquadra na [Política de Privacidade da Microsoft][privacy].</span><span class="sxs-lookup"><span data-stu-id="c4faa-126">The telemetry we collect falls under the [Microsoft Privacy Statement][privacy].</span></span>

<!-- link references -->
[install]: https://docs.docker.com/engine/installation/
[docker-release]: https://hub.docker.com/r/microsoft/powershell/
[appinsights]: https://azure.microsoft.com/services/application-insights/
[licença MIT]: https://github.com/PowerShell/PowerShell/tree/master/LICENSE.txt
[MIT license]: https://github.com/PowerShell/PowerShell/tree/master/LICENSE.txt
[PowerShell-Docker]: https://github.com/PowerShell/PowerShell-Docker
[Window Server Core]: https://hub.docker.com/r/microsoft/windowsservercore/
[Nano Server]: https://hub.docker.com/r/microsoft/nanoserver/
[privacy]: https://privacy.microsoft.com/privacystatement/
