---
ms.date: 12/01/2020
title: A Galeria do PowerShell
description: A Galeria do PowerShell é o repositório central de módulos do PowerShell, scripts e recursos de DSC.
ms.openlocfilehash: f1ce6a8e2d5d72ac14cf3e4854626ef612d27891
ms.sourcegitcommit: 62282bb9c36fea3b4290b9263c1cd8e9ac216e29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96470308"
---
# <a name="the-powershell-gallery"></a><span data-ttu-id="cb4e3-103">A Galeria do PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb4e3-103">The PowerShell Gallery</span></span>

<span data-ttu-id="cb4e3-104">A Galeria do PowerShell é o repositório central de conteúdo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb4e3-104">The PowerShell Gallery is the central repository for PowerShell content.</span></span> <span data-ttu-id="cb4e3-105">Nela, você pode encontrar módulos úteis do PowerShell que contêm comandos do PowerShell e recursos de DSC (Configuração de Estado Desejado).</span><span class="sxs-lookup"><span data-stu-id="cb4e3-105">In it, you can find useful PowerShell modules containing PowerShell commands and Desired State Configuration (DSC) resources.</span></span>
<span data-ttu-id="cb4e3-106">Você também pode encontrar scripts do PowerShell, alguns dos quais podem conter fluxos de trabalho do PowerShell e que descrevem um conjunto de tarefas e fornecem o sequenciamento para essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="cb4e3-106">You can also find PowerShell scripts, some of which may contain PowerShell workflows, and which outline a set of tasks and provide sequencing for those tasks.</span></span> <span data-ttu-id="cb4e3-107">Alguns desses pacotes são criados pela Microsoft e outros são criados pela comunidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb4e3-107">Some of these packages are authored by Microsoft, and others are authored by the PowerShell community.</span></span>

## <a name="powershellget-overview"></a><span data-ttu-id="cb4e3-108">Visão geral do PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="cb4e3-108">PowerShellGet Overview</span></span>

<span data-ttu-id="cb4e3-109">O módulo do PowerShellGet contém cmdlets para descoberta, instalação, atualização e publicação de pacotes PowerShell que contêm artefatos como Módulos, Recursos de DSC, Funcionalidades de Função e Scripts da [Galeria do PowerShell](https://www.PowerShellGallery.com) e outros repositórios privados.</span><span class="sxs-lookup"><span data-stu-id="cb4e3-109">The PowerShellGet module contains cmdlets for discovering, installing, updating and publishing PowerShell packages which contain artifacts such as Modules, DSC Resources, Role Capabilities and Scripts from the [PowerShell Gallery](https://www.PowerShellGallery.com) and other private repositories.</span></span>

## <a name="getting-started-with-the-gallery"></a><span data-ttu-id="cb4e3-110">Introdução à Galeria</span><span class="sxs-lookup"><span data-stu-id="cb4e3-110">Getting Started with the Gallery</span></span>

<span data-ttu-id="cb4e3-111">A instalação de pacotes da Galeria requer a versão mais recente do módulo PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="cb4e3-111">Installing packages from the Gallery requires the latest version of the PowerShellGet module.</span></span> <span data-ttu-id="cb4e3-112">Confira [Instalando o PowerShellGet](installing-psget.md) para obter instruções completas.</span><span class="sxs-lookup"><span data-stu-id="cb4e3-112">See [Installing PowerShellGet](installing-psget.md) for complete instructions.</span></span>

<span data-ttu-id="cb4e3-113">Confira a página [Introdução](getting-started.md) para obter mais informações sobre como usar os comandos PowerShellGet com a Galeria.</span><span class="sxs-lookup"><span data-stu-id="cb4e3-113">Check out the [Getting Started](getting-started.md) page for more information on how to use PowerShellGet commands with the Gallery.</span></span> <span data-ttu-id="cb4e3-114">Também é possível executar *Update-Help -Module PowerShellGet* para instalar a ajuda local para esses comandos.</span><span class="sxs-lookup"><span data-stu-id="cb4e3-114">You can also run *Update-Help -Module PowerShellGet* to install local help for these commands.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="cb4e3-115">Sistemas operacionais com suporte</span><span class="sxs-lookup"><span data-stu-id="cb4e3-115">Supported Operating Systems</span></span>

<span data-ttu-id="cb4e3-116">O módulo **PowerShellGet** exige o **PowerShell 3.0 ou mais recente**.</span><span class="sxs-lookup"><span data-stu-id="cb4e3-116">The **PowerShellGet** module requires **PowerShell 3.0 or newer**.</span></span>

<span data-ttu-id="cb4e3-117">O **PowerShellGet** requer o .NET Framework 4.5 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="cb4e3-117">**PowerShellGet** requires .NET Framework 4.5 or above.</span></span> <span data-ttu-id="cb4e3-118">Para obter mais informações, confira [Instalar o .NET Framework para desenvolvedores](/dotnet/framework/install/guide-for-developers).</span><span class="sxs-lookup"><span data-stu-id="cb4e3-118">For more information, see [Install the .NET Framework for developers](/dotnet/framework/install/guide-for-developers).</span></span>

<span data-ttu-id="cb4e3-119">Como **PowerShell Core** é uma plataforma cruzada, o que significa que funciona no Windows, Linux e MacOS, ele também deixa **PowerShellGet** disponível nesses sistemas.</span><span class="sxs-lookup"><span data-stu-id="cb4e3-119">Since **PowerShell Core** is cross-platform and that means it works on Windows, Linux and MacOS, that also makes **PowerShellGet** available on those systems.</span></span> <span data-ttu-id="cb4e3-120">Para obter uma lista completa de sistemas compatíveis com **PowerShell Core**, consulte [Instalação do PowerShell](/powershell/scripting/install/installing-powershell).</span><span class="sxs-lookup"><span data-stu-id="cb4e3-120">For a full list of systems supported by **PowerShell Core** see [Installing PowerShell](/powershell/scripting/install/installing-powershell).</span></span>

<span data-ttu-id="cb4e3-121">Muitos módulos hospedados na galeria darão suporte a sistemas operacionais diferentes e têm outros requisitos.</span><span class="sxs-lookup"><span data-stu-id="cb4e3-121">Many modules hosted in the gallery will support different OSes and have additional requirements.</span></span>
<span data-ttu-id="cb4e3-122">Consulte a documentação dos módulos para saber mais.</span><span class="sxs-lookup"><span data-stu-id="cb4e3-122">Please refer to the documentation for the modules for more information.</span></span>

## <a name="got-a-question-have-feedback"></a><span data-ttu-id="cb4e3-123">Tem alguma pergunta?</span><span class="sxs-lookup"><span data-stu-id="cb4e3-123">Got a question?</span></span> <span data-ttu-id="cb4e3-124">Tem comentários?</span><span class="sxs-lookup"><span data-stu-id="cb4e3-124">Have feedback?</span></span>

<span data-ttu-id="cb4e3-125">Encontre mais informações sobre a Galeria do PowerShell e o PowerShellGet na página [Introdução](getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="cb4e3-125">More information about the PowerShell Gallery and PowerShellGet can be found in the [Getting Started](getting-started.md) page.</span></span>

<span data-ttu-id="cb4e3-126">Para ver o status atual dos serviços da Galeria do PowerShell, confira a página [Status da Galeria do PowerShell](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) no GitHub.</span><span class="sxs-lookup"><span data-stu-id="cb4e3-126">To see the current status of the PowerShell Gallery services, see the [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) page on GitHub.</span></span>

<span data-ttu-id="cb4e3-127">Forneça comentários e relate problemas usando o [repositório GitHub](https://github.com/PowerShell/PowerShellGallery/issues).</span><span class="sxs-lookup"><span data-stu-id="cb4e3-127">Please provide feedback and report issues the [GitHub repository](https://github.com/PowerShell/PowerShellGallery/issues).</span></span>
