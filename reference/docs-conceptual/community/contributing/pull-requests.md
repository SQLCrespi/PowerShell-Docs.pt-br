---
title: Como enviar solicitações de pull
description: Este artigo explica como enviar solicitações de pull ao repositório do PowerShell-Docs.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 1a21c25e19189aec4f48ad034147b02f4f804f9d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "99598810"
---
# <a name="how-to-submit-pull-requests"></a><span data-ttu-id="60235-103">Como enviar solicitações de pull</span><span class="sxs-lookup"><span data-stu-id="60235-103">How to submit pull requests</span></span>

<span data-ttu-id="60235-104">Para fazer alterações no conteúdo, envie uma solicitação de pull do seu fork.</span><span class="sxs-lookup"><span data-stu-id="60235-104">To make changes to content, submit a pull request (PR) from your fork.</span></span> <span data-ttu-id="60235-105">Uma solicitação de pull deve ser revisada antes que possa ser mesclada.</span><span class="sxs-lookup"><span data-stu-id="60235-105">A pull request must be reviewed before it can be merged.</span></span> <span data-ttu-id="60235-106">Para obter melhores resultados, revise a [lista de verificação editorial](editorial-checklist.md) antes de enviar sua solicitação de pull.</span><span class="sxs-lookup"><span data-stu-id="60235-106">For best results, review the [editorial checklist](editorial-checklist.md) before submitting your pull request.</span></span>

## <a name="using-git-branches"></a><span data-ttu-id="60235-107">Usando ramificações git</span><span class="sxs-lookup"><span data-stu-id="60235-107">Using git branches</span></span>

<span data-ttu-id="60235-108">A ramificação padrão para PowerShell-Docs é a `staging` ramificação.</span><span class="sxs-lookup"><span data-stu-id="60235-108">The default branch for PowerShell-Docs is the `staging` branch.</span></span> <span data-ttu-id="60235-109">As alterações feitas em ramificações de trabalho são mescladas na `staging` ramificação antes de serem publicadas.</span><span class="sxs-lookup"><span data-stu-id="60235-109">Changes made in working branches are merged into the `staging` branch before then being published.</span></span> <span data-ttu-id="60235-110">A `staging` ramificação é mesclada na `live` ramificação a cada dia da semana às 3:00 PM (hora do Pacífico).</span><span class="sxs-lookup"><span data-stu-id="60235-110">The `staging` branch is merged into the `live` branch every weekday at 3:00 PM (Pacific Time).</span></span> <span data-ttu-id="60235-111">A `live` ramificação contém o conteúdo que é publicado em docs.Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="60235-111">The `live` branch contains the content that is published to docs.microsoft.com.</span></span>

<span data-ttu-id="60235-112">Antes de iniciar as alterações, crie um Branch de trabalho em sua cópia local do repositório de PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="60235-112">Before starting any changes, create a working branch in your local copy of the PowerShell-Docs repository.</span></span> <span data-ttu-id="60235-113">Ao trabalhar localmente, certifique-se de sincronizar seu repositório local antes de criar seu Branch de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60235-113">When working locally, be sure to synchronize your local repository before creating your working branch.</span></span> <span data-ttu-id="60235-114">A ramificação de trabalho deve ser criada a partir de uma cópia atualizada até a data do `staging` Branch.</span><span class="sxs-lookup"><span data-stu-id="60235-114">The working branch should be created from an update-to-date copy of the `staging` branch.</span></span>

<span data-ttu-id="60235-115">Todas as solicitações de pull devem ter como destino o branch `staging`.</span><span class="sxs-lookup"><span data-stu-id="60235-115">All pull requests should target the `staging` branch.</span></span> <span data-ttu-id="60235-116">Não envie alteração para a `live` ramificação.</span><span class="sxs-lookup"><span data-stu-id="60235-116">Don't submit change to the `live` branch.</span></span>
<span data-ttu-id="60235-117">As alterações realizadas no branch `staging` são mescladas no `live`, substituindo as alterações feitas no `live`.</span><span class="sxs-lookup"><span data-stu-id="60235-117">Changes made in the `staging` branch get merged into `live`, overwriting any changes made to `live`.</span></span>

## <a name="make-the-pull-request-process-work-better-for-everyone"></a><span data-ttu-id="60235-118">Melhorar o funcionamento do processo de solicitação de pull para todos</span><span class="sxs-lookup"><span data-stu-id="60235-118">Make the pull request process work better for everyone</span></span>

<span data-ttu-id="60235-119">Quanto mais simples e focada for a PR (solicitação de pull), mais rápido ela poderá ser revisada e mesclada.</span><span class="sxs-lookup"><span data-stu-id="60235-119">The simpler and more focused you can make your PR, the faster it can be reviewed and merged.</span></span>

### <a name="avoid-pull-requests-that-update-large-numbers-of-files-or-contain-unrelated-changes"></a><span data-ttu-id="60235-120">Evitar solicitações pull que atualizam um grande número de arquivos ou contêm alterações não relacionadas</span><span class="sxs-lookup"><span data-stu-id="60235-120">Avoid pull requests that update large numbers of files or contain unrelated changes</span></span>

<span data-ttu-id="60235-121">Evite criar PRs que contenham alterações não relacionadas.</span><span class="sxs-lookup"><span data-stu-id="60235-121">Avoid creating PRs that contain unrelated changes.</span></span> <span data-ttu-id="60235-122">Separe as pequenas atualizações feitas nos artigos existentes dos novos artigos ou das principais regravações.</span><span class="sxs-lookup"><span data-stu-id="60235-122">Separate minor updates to existing articles from new articles or major rewrites.</span></span> <span data-ttu-id="60235-123">Trabalhe nessas alterações em branches de trabalho separados.</span><span class="sxs-lookup"><span data-stu-id="60235-123">Work on these changes in separate working branches.</span></span>

<span data-ttu-id="60235-124">Alterações em massa criam PRs com um grande número de arquivos alterados.</span><span class="sxs-lookup"><span data-stu-id="60235-124">Bulk changes create PRs with large numbers of changed files.</span></span> <span data-ttu-id="60235-125">Limite as PRs a um máximo de 50 arquivos alterados.</span><span class="sxs-lookup"><span data-stu-id="60235-125">Limit your PRs to a maximum of 50 changed files.</span></span> <span data-ttu-id="60235-126">PRs grandes são difíceis de revisar e mais propensas a conter erros.</span><span class="sxs-lookup"><span data-stu-id="60235-126">Large PRs are difficult to review and are more prone to contain errors.</span></span>

### <a name="renaming-or-deleting-files"></a><span data-ttu-id="60235-127">Renomear ou excluir arquivos</span><span class="sxs-lookup"><span data-stu-id="60235-127">Renaming or deleting files</span></span>

<span data-ttu-id="60235-128">Ao renomear ou excluir arquivos, deve haver um problema associado à PR.</span><span class="sxs-lookup"><span data-stu-id="60235-128">When renaming or deleting files, there must be an issue associated with the PR.</span></span> <span data-ttu-id="60235-129">Esse problema deve discutir a necessidade de renomear ou excluir os arquivos.</span><span class="sxs-lookup"><span data-stu-id="60235-129">That issue must discuss the need to rename or delete the files.</span></span>

<span data-ttu-id="60235-130">Evite misturar adições ou alterações de conteúdo com renomeações e exclusões de arquivos.</span><span class="sxs-lookup"><span data-stu-id="60235-130">Avoid mixing content additions or change with file renames and deletes.</span></span> <span data-ttu-id="60235-131">Qualquer arquivo renomeado ou excluído deve ser adicionado ao arquivo de redirecionamento global.</span><span class="sxs-lookup"><span data-stu-id="60235-131">Any file that is renamed or deleted must be added to the global redirection file.</span></span> <span data-ttu-id="60235-132">Quando possível, atualize todos os arquivos vinculados ao conteúdo renomeado ou excluído, incluindo todos os arquivos de Sumário.</span><span class="sxs-lookup"><span data-stu-id="60235-132">When possible, update any files that link to the renamed or deleted content, including any TOC files.</span></span>

## <a name="docs-pr-validation-service"></a><span data-ttu-id="60235-133">Serviço de validação de PR do Docs</span><span class="sxs-lookup"><span data-stu-id="60235-133">Docs PR validation service</span></span>

<span data-ttu-id="60235-134">O serviço de validação docs PR é um aplicativo GitHub que executa regras de validação em suas alterações.</span><span class="sxs-lookup"><span data-stu-id="60235-134">The Docs PR validation service is a GitHub app that runs validation rules on your changes.</span></span> <span data-ttu-id="60235-135">Você deve corrigir todos os erros ou avisos relatados pelo serviço de validação.</span><span class="sxs-lookup"><span data-stu-id="60235-135">You must fix any errors or warnings reported by the validation service.</span></span>

<span data-ttu-id="60235-136">Você verá o seguinte comportamento:</span><span class="sxs-lookup"><span data-stu-id="60235-136">You'll see the following behavior:</span></span>

1. <span data-ttu-id="60235-137">Você envia uma PR.</span><span class="sxs-lookup"><span data-stu-id="60235-137">You submit a PR.</span></span>
1. <span data-ttu-id="60235-138">No comentário do GitHub que indica o status da PR, você verá o status de "verificações" habilitadas no repositório.</span><span class="sxs-lookup"><span data-stu-id="60235-138">In the GitHub comment that indicates the status of your PR, you'll see the status of "checks" enabled on the repository.</span></span> <span data-ttu-id="60235-139">Neste exemplo, há duas verificações habilitadas, "confirmar validação" e "OpenPublishing. Build":</span><span class="sxs-lookup"><span data-stu-id="60235-139">In this example, there are two checks enabled, "Commit Validation" and "OpenPublishing.Build":</span></span>

   ![Status de validação – Algumas verificações falharam](media/pull-requests/validation-failed.png)

   <span data-ttu-id="60235-141">O build poderá passar mesmo se a validação do commit falhar.</span><span class="sxs-lookup"><span data-stu-id="60235-141">The build can pass even if commit validation fails.</span></span>

1. <span data-ttu-id="60235-142">Clique em **Detalhes** para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="60235-142">Click **Details** for more information.</span></span>
1. <span data-ttu-id="60235-143">Na página Detalhes, você verá todas as verificações de validação que falharam, com informações sobre como corrigir os problemas.</span><span class="sxs-lookup"><span data-stu-id="60235-143">On the Details page, you'll see all the validation checks that failed, with information about how to fix the issues.</span></span>
1. <span data-ttu-id="60235-144">Quando a validação é bem-sucedida, o seguinte comentário é adicionado à PR:</span><span class="sxs-lookup"><span data-stu-id="60235-144">When validation succeeds, the following comment is added to the PR:</span></span>

   ![Status da validação: sucesso](media/pull-requests/build-validation.png)

> [!NOTE]
> <span data-ttu-id="60235-146">Se você for um colaborador externo (não funcionário da Microsoft), não terá acesso aos relatórios detalhados de build nem aos links de visualização.</span><span class="sxs-lookup"><span data-stu-id="60235-146">If you are an external (not a Microsoft employee) contributor you do not have access to the detailed build reports or preview links.</span></span>

<span data-ttu-id="60235-147">Quando a PR for revisada, você poderá ser solicitado a fazer alterações ou corrigir mensagens de aviso de validação.</span><span class="sxs-lookup"><span data-stu-id="60235-147">When the PR is reviewed, you may be asked to make changes or fix validation warning messages.</span></span> <span data-ttu-id="60235-148">A equipe de PowerShell-Docs pode ajudá-lo a entender os erros de validação e os requisitos editoriais.</span><span class="sxs-lookup"><span data-stu-id="60235-148">The PowerShell-Docs team can help you understand validation errors and editorial requirements.</span></span>

## <a name="next-steps"></a><span data-ttu-id="60235-149">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="60235-149">Next steps</span></span>

[<span data-ttu-id="60235-150">Guia de estilo do PowerShell-Docs</span><span class="sxs-lookup"><span data-stu-id="60235-150">PowerShell-Docs style guide</span></span>](powershell-style-guide.md)

## <a name="additional-resources"></a><span data-ttu-id="60235-151">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="60235-151">Additional resources</span></span>

[<span data-ttu-id="60235-152">Como gerenciamos solicitações de pull</span><span class="sxs-lookup"><span data-stu-id="60235-152">How we manage pull requests</span></span>](managing-pull-requests.md)

<!--link refs-->
[fork]: /contribute/get-started-setup-local#fork-the-repository
