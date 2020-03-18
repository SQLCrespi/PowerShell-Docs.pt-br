---
title: Contribuir para a documentação do PowerShell
description: Este artigo é uma visão geral de como começar como um colaborador da documentação do PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 5db78ae2805cb26aa79aa698cfb8b5d8ba8911dc
ms.sourcegitcommit: c97dcf1e00ef540e7464c36c88f841474060044c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2020
ms.locfileid: "79402623"
---
# <a name="contributing-to-powershell-documentation"></a><span data-ttu-id="24451-103">Contribuir para a documentação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="24451-103">Contributing to PowerShell documentation</span></span>

<span data-ttu-id="24451-104">Agradecemos pelo seu suporte ao PowerShell!</span><span class="sxs-lookup"><span data-stu-id="24451-104">Thank you for your support of PowerShell!</span></span>

<span data-ttu-id="24451-105">O Guia do colaborador é uma coleção de artigos que explicam as ferramentas e os processos que usamos para criar a documentação na Microsoft.</span><span class="sxs-lookup"><span data-stu-id="24451-105">The Contributor's Guide is a collection of articles that explain the tools and processes we use to create documentation at Microsoft.</span></span> <span data-ttu-id="24451-106">Alguns desses guias abrangem informações que são comuns a qualquer conjunto de documentação publicado no [docs.microsoft.com][docs].</span><span class="sxs-lookup"><span data-stu-id="24451-106">Some of these guides cover information that is common to any documentation set published to [docs.microsoft.com][docs].</span></span> <span data-ttu-id="24451-107">Alguns dos guias são específicos sobre como escrevemos a documentação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24451-107">Some of the guides are specific to how we write documentation for PowerShell.</span></span>

<span data-ttu-id="24451-108">Os artigos comuns estão disponíveis em nosso [Guia do colaborador][contribute] centralizado.</span><span class="sxs-lookup"><span data-stu-id="24451-108">The common articles are available in our centralized [Contributor's Guide][contribute].</span></span> <span data-ttu-id="24451-109">Os guias específicos do PowerShell estão disponíveis aqui.</span><span class="sxs-lookup"><span data-stu-id="24451-109">The PowerShell-specific guides are available here.</span></span>

## <a name="ways-to-contribute"></a><span data-ttu-id="24451-110">Formas de contribuição</span><span class="sxs-lookup"><span data-stu-id="24451-110">Ways to contribute</span></span>

<span data-ttu-id="24451-111">Há duas maneiras de contribuir.</span><span class="sxs-lookup"><span data-stu-id="24451-111">There are two ways to contribute.</span></span> <span data-ttu-id="24451-112">Ambas as contribuições são valiosas para nós.</span><span class="sxs-lookup"><span data-stu-id="24451-112">Both contributions are valuable to us.</span></span>

- <span data-ttu-id="24451-113">[Registrar problemas][file-an-issue] nos ajuda a identificar problemas e lacunas em nossa documentação.</span><span class="sxs-lookup"><span data-stu-id="24451-113">[Filing issues][file-an-issue] helps us identify problems and gaps in our documentation.</span></span> <span data-ttu-id="24451-114">Às vezes, os problemas são difíceis de resolver, exigindo mais investigação e pesquisa.</span><span class="sxs-lookup"><span data-stu-id="24451-114">Sometimes the issues are difficult to resolve, requiring more investigation and research.</span></span> <span data-ttu-id="24451-115">O processo do problema nos permite ter uma conversa sobre o problema e desenvolver uma resolução satisfatória.</span><span class="sxs-lookup"><span data-stu-id="24451-115">The issue process allows us to have a conversation about the problem and develop a satisfactory resolution.</span></span>

- <span data-ttu-id="24451-116">Enviar novo conteúdo ou alterar artigos existentes é um processo mais complexo.</span><span class="sxs-lookup"><span data-stu-id="24451-116">Submitting new content or changes to existing articles is a more involved process.</span></span> <span data-ttu-id="24451-117">As informações a seguir descrevem as ferramentas, os processos e os padrões para enviar conteúdo à documentação.</span><span class="sxs-lookup"><span data-stu-id="24451-117">The following information outlines the tools, processes, and standards for submitting content to the documentation.</span></span>

## <a name="prepare-to-make-a-contribution"></a><span data-ttu-id="24451-118">Preparar-se para fazer uma contribuição</span><span class="sxs-lookup"><span data-stu-id="24451-118">Prepare to make a contribution</span></span>

<span data-ttu-id="24451-119">Contribuir com a documentação requer uma conta do GitHub.</span><span class="sxs-lookup"><span data-stu-id="24451-119">Contributing to the documentation requires a GitHub account.</span></span> <span data-ttu-id="24451-120">Use a lista de verificação a seguir para obter as ferramentas e entender os processos que usamos para fazer contribuições.</span><span class="sxs-lookup"><span data-stu-id="24451-120">Use the following checklist to get the tools and understand the processes we use for making contributions.</span></span>

1. [<span data-ttu-id="24451-121">Inscrever-se no GitHub</span><span class="sxs-lookup"><span data-stu-id="24451-121">Sign up for GitHub</span></span>](/contribute/get-started-setup-github)
1. [<span data-ttu-id="24451-122">Instalar ferramentas do Markdown e do Git</span><span class="sxs-lookup"><span data-stu-id="24451-122">Install Git and Markdown tools</span></span>](/contribute/get-started-setup-tools)
1. [<span data-ttu-id="24451-123">Instalar o Pacote de criação de documentos</span><span class="sxs-lookup"><span data-stu-id="24451-123">Install the Docs Authoring Pack</span></span>](/contribute/how-to-write-docs-auth-pack)
1. <span data-ttu-id="24451-124">[Instalar o Posh-Git][posh-git] – não obrigatório, mas recomendado</span><span class="sxs-lookup"><span data-stu-id="24451-124">[Install Posh-Git][posh-git] - not required but recommended</span></span>
1. [<span data-ttu-id="24451-125">Configurar um repositório Git local</span><span class="sxs-lookup"><span data-stu-id="24451-125">Set up a local Git repository</span></span>](/contribute/get-started-setup-local)
1. [<span data-ttu-id="24451-126">Revisar os conceitos básicos do Git e do GitHub</span><span class="sxs-lookup"><span data-stu-id="24451-126">Review Git and GitHub fundamentals</span></span>](/contribute/git-github-fundamentals)

## <a name="get-started-writing-docs"></a><span data-ttu-id="24451-127">Comece a colaborar para a documentação</span><span class="sxs-lookup"><span data-stu-id="24451-127">Get started writing docs</span></span>

<span data-ttu-id="24451-128">Há duas maneiras de contribuir com alterações na documentação:</span><span class="sxs-lookup"><span data-stu-id="24451-128">There are two ways to contribute changes to the documentation:</span></span>

1. [<span data-ttu-id="24451-129">Edições rápidas em documentos existentes</span><span class="sxs-lookup"><span data-stu-id="24451-129">Quick edits to existing docs</span></span>](/contribute/#quick-edits-to-existing-documents)
   - <span data-ttu-id="24451-130">Correções secundárias, correção de erros de digitação ou pequenas adições</span><span class="sxs-lookup"><span data-stu-id="24451-130">Minor corrections, fixing typos, or small additions</span></span>
1. [<span data-ttu-id="24451-131">Fluxo de trabalho completo do GitHub para documentos</span><span class="sxs-lookup"><span data-stu-id="24451-131">Full GitHub workflow for docs</span></span>](/contribute/how-to-write-workflows-major)
   - <span data-ttu-id="24451-132">grandes alterações, várias versões, adição ou alteração de imagens ou colaboração em novos artigos</span><span class="sxs-lookup"><span data-stu-id="24451-132">large changes, multiple versions, adding or changing images, or contributing new articles</span></span>

<span data-ttu-id="24451-133">Além disso, leia a seção [Fundamentos da escrita](/contribute/style-quick-start) do Guia do colaborador centralizado.</span><span class="sxs-lookup"><span data-stu-id="24451-133">Also, read the [Writing essentials](/contribute/style-quick-start) section of the centralized Contributor's Guide.</span></span> <span data-ttu-id="24451-134">Outro recurso excelente é o [Guia de estilo de escrita da Microsoft][style-guide].</span><span class="sxs-lookup"><span data-stu-id="24451-134">Another excellent resource is the [Microsoft Writing Style Guide][style-guide].</span></span> <span data-ttu-id="24451-135">O objetivo do Guia de estilo de escrita da Microsoft é ajudar os editores, redatores técnicos, desenvolvedores, profissionais de marketing e qualquer outra pessoa em TI a escrever um conteúdo melhor.</span><span class="sxs-lookup"><span data-stu-id="24451-135">The goal of the Microsoft Writing Style Guide is to help editors, technical writers, developers, marketers, and anyone else in IT write better content.</span></span>

<span data-ttu-id="24451-136">As correções secundárias ou esclarecimentos na documentação e nos exemplos de código em repositórios públicos são cobertos pelos[Termos de Uso][terms-of-use] do docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="24451-136">Minor corrections or clarifications to documentation and code examples in public repositories are covered by the docs.microsoft.com [Terms of Use][terms-of-use].</span></span>

<span data-ttu-id="24451-137">Use o fluxo de trabalho completo do GitHub quando estiver fazendo alterações significativas.</span><span class="sxs-lookup"><span data-stu-id="24451-137">Use the full GitHub workflow when you're making significant changes.</span></span> <span data-ttu-id="24451-138">Se você não for um funcionário da Microsoft, as alterações significativas gerarão um comentário na solicitação de pull, pedindo o envio de um [CLA (Contrato de Licença de Contribuição)][cla] online.</span><span class="sxs-lookup"><span data-stu-id="24451-138">If you're not an employee of Microsoft, significant changes generate a comment in the pull request that asks you to submit an online [Contribution Licensing Agreement (CLA)][cla].</span></span> <span data-ttu-id="24451-139">Precisamos que você preencha o formulário online antes de revisarmos ou aceitarmos sua solicitação de pull.</span><span class="sxs-lookup"><span data-stu-id="24451-139">We need you to complete the online form before we can review or accept your pull request.</span></span>

## <a name="code-of-conduct"></a><span data-ttu-id="24451-140">Código de conduta</span><span class="sxs-lookup"><span data-stu-id="24451-140">Code of conduct</span></span>

<span data-ttu-id="24451-141">Todos os repositórios que publicam no docs.microsoft.com adotaram o [Código de conduta de software livre da Microsoft](https://opensource.microsoft.com/codeofconduct/) ou o [Código de conduta do .NET Foundation](https://dotnetfoundation.org/code-of-conduct).</span><span class="sxs-lookup"><span data-stu-id="24451-141">All repositories that publish to docs.microsoft.com have adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/) or the [.NET Foundation Code of Conduct](https://dotnetfoundation.org/code-of-conduct).</span></span> <span data-ttu-id="24451-142">Para obter mais informações, confira as [Perguntas frequentes sobre o Código de conduta](https://opensource.microsoft.com/codeofconduct/faq/).</span><span class="sxs-lookup"><span data-stu-id="24451-142">For more information, see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="24451-143">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="24451-143">Next steps</span></span>

<span data-ttu-id="24451-144">Os artigos a seguir abrangem informações específicas da documentação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24451-144">The following articles cover information specific to PowerShell documentation.</span></span> <span data-ttu-id="24451-145">Quando há sobreposição nas diretrizes do Guia do colaborador centralizado, destacamos como essas regras se diferem para o conteúdo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24451-145">Where there's overlap with the guidance in the centralized Contributor's Guide, we call out how those rules differ for the PowerShell content.</span></span>

<span data-ttu-id="24451-146">Examine os seguintes documentos:</span><span class="sxs-lookup"><span data-stu-id="24451-146">Review the following documents:</span></span>

- [<span data-ttu-id="24451-147">Como arquivar um problema</span><span class="sxs-lookup"><span data-stu-id="24451-147">How to file an issue</span></span>](file-an-issue.md)
- [<span data-ttu-id="24451-148">Introdução à escrita de documentos</span><span class="sxs-lookup"><span data-stu-id="24451-148">Get started writing docs</span></span>](get-started-writing.md)
- [<span data-ttu-id="24451-149">Enviar uma solicitação de pull</span><span class="sxs-lookup"><span data-stu-id="24451-149">Submitting a pull request</span></span>](pull-requests.md)
- [<span data-ttu-id="24451-150">Guia de estilo do PowerShell-Docs</span><span class="sxs-lookup"><span data-stu-id="24451-150">PowerShell-Docs style guide</span></span>](powershell-style-guide.md)
- [<span data-ttu-id="24451-151">Editar referência de cmdlet</span><span class="sxs-lookup"><span data-stu-id="24451-151">Editing cmdlet reference</span></span>](editing-cmdlet-ref.md)

<span data-ttu-id="24451-152">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="24451-152">Additional resources</span></span>

- [<span data-ttu-id="24451-153">Lista de verificação editorial</span><span class="sxs-lookup"><span data-stu-id="24451-153">Editorial checklist</span></span>](editorial-checklist.md)
- [<span data-ttu-id="24451-154">Como gerenciamos problemas</span><span class="sxs-lookup"><span data-stu-id="24451-154">How we manage issues</span></span>](managing-issues.md)
- [<span data-ttu-id="24451-155">Como gerenciamos solicitações de pull</span><span class="sxs-lookup"><span data-stu-id="24451-155">How we manage pull requests</span></span>](managing-pull-requests.md)

<!--link refs-->
[cla]: https://cla.microsoft.com/
[contribute]: /contribute/
[docs]: https://docs.microsoft.com/
[file-an-issue]: file-an-issue.md
[posh-git]: https://www.powershellgallery.com/packages/posh-git
[psdocs]: https://docs.microsoft.com/powershell
[style-guide]: https://docs.microsoft.com/style-guide/welcome/
[terms-of-use]: https://docs.microsoft.com/legal/termsofuse