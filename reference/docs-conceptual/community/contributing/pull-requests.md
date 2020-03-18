---
title: Como enviar solicitações de pull
description: Este artigo explica como enviar solicitações de pull ao repositório do PowerShell-Docs.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 2600049b06da5ad4869b6ff335f00bc40c2d1c22
ms.sourcegitcommit: 18d832858a7b8ea094763afa753e0f48f01372e7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2020
ms.locfileid: "79060231"
---
# <a name="how-to-submit-pull-requests"></a><span data-ttu-id="5d6b3-103">Como enviar solicitações de pull</span><span class="sxs-lookup"><span data-stu-id="5d6b3-103">How to submit pull requests</span></span>

<span data-ttu-id="5d6b3-104">Para fazer alterações no conteúdo, envie uma solicitação de pull do seu fork.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-104">To make changes to content, submit a pull request (PR) from your fork.</span></span> <span data-ttu-id="5d6b3-105">Uma solicitação de pull deve ser revisada antes de ser mesclada.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-105">A pull request must be reviewed before it can merged.</span></span> <span data-ttu-id="5d6b3-106">Para obter melhores resultados, revise a [lista de verificação editorial](editorial-checklist.md) antes de enviar sua solicitação de pull.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-106">For best results, review the [editorial checklist](editorial-checklist.md) before submitting your pull request.</span></span>

## <a name="target-the-correct-branch"></a><span data-ttu-id="5d6b3-107">Direcionar para o branch correto</span><span class="sxs-lookup"><span data-stu-id="5d6b3-107">Target the correct branch</span></span>

<span data-ttu-id="5d6b3-108">Todas as solicitações de pull devem ter como destino o branch `staging`.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-108">All pull requests should target the `staging` branch.</span></span> <span data-ttu-id="5d6b3-109">As alterações nunca devem ser enviadas para o branch `live`.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-109">Changes should never be submitted to the `live` branch.</span></span> <span data-ttu-id="5d6b3-110">As alterações realizadas no branch `staging` são mescladas no `live`, substituindo as alterações feitas no `live`.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-110">Changes made in the `staging` branch get merged into `live`, overwriting any changes made to `live`.</span></span>

<span data-ttu-id="5d6b3-111">Se você estiver enviando uma alteração que se aplica somente a uma versão não lançada do PowerShell, verifique se há um branch de lançamento para essa versão.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-111">If you are submitting a change that only applies to an unreleased version of PowerShell, check for a release branch for that version.</span></span> <span data-ttu-id="5d6b3-112">Sua solicitação de pull deve ser direcionada ao branch de lançamento.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-112">Your PR should be targeted at the release branch.</span></span> <span data-ttu-id="5d6b3-113">Os branches de lançamento têm o seguinte padrão de nome: `release-<version>`.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-113">Release branches have the following name pattern: `release-<version>`.</span></span>

## <a name="make-the-pull-request-process-work-better-for-everyone"></a><span data-ttu-id="5d6b3-114">Melhorar o funcionamento do processo de solicitação de pull para todos</span><span class="sxs-lookup"><span data-stu-id="5d6b3-114">Make the pull request process work better for everyone</span></span>

<span data-ttu-id="5d6b3-115">Quanto mais simples e focada for a PR (solicitação de pull), mais rápido ela poderá ser revisada e mesclada.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-115">The simpler and more focused you can make your PR, the faster it can be reviewed and merged.</span></span>

### <a name="avoid-branches-that-update-large-numbers-of-files-or-contain-unrelated-changes"></a><span data-ttu-id="5d6b3-116">Evitar branches que atualizam um grande número de arquivos ou contêm alterações não relacionadas</span><span class="sxs-lookup"><span data-stu-id="5d6b3-116">Avoid branches that update large numbers of files or contain unrelated changes</span></span>

<span data-ttu-id="5d6b3-117">Evite criar PRs que contenham alterações não relacionadas.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-117">Avoid creating PRs that contain unrelated changes.</span></span> <span data-ttu-id="5d6b3-118">Separe as pequenas atualizações feitas nos artigos existentes dos novos artigos ou das principais regravações.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-118">Separate minor updates to existing articles from new articles or major rewrites.</span></span> <span data-ttu-id="5d6b3-119">Trabalhe nessas alterações em branches de trabalho separados.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-119">Work on these changes in separate working branches.</span></span>

<span data-ttu-id="5d6b3-120">Alterações em massa criam PRs com um grande número de arquivos alterados.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-120">Bulk changes create PRs with large numbers of changed files.</span></span> <span data-ttu-id="5d6b3-121">Limite as PRs a um máximo de 50 arquivos alterados.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-121">Limit your PRs to a maximum of 50 changed files.</span></span> <span data-ttu-id="5d6b3-122">PRs grandes são difíceis de revisar e mais propensas a conter erros.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-122">Large PRs are difficult to review and are more prone to contain errors.</span></span>

### <a name="renaming-or-deleting-files"></a><span data-ttu-id="5d6b3-123">Renomear ou excluir arquivos</span><span class="sxs-lookup"><span data-stu-id="5d6b3-123">Renaming or deleting files</span></span>

<span data-ttu-id="5d6b3-124">Caso você esteja renomeando ou excluindo arquivos, deve haver um problema associado à PR.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-124">If you are renaming or deleting files, there must be an issue associated with the PR.</span></span> <span data-ttu-id="5d6b3-125">Esse problema deve discutir a necessidade de renomear ou excluir os arquivos.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-125">That issue must discuss the need to rename or delete the files.</span></span>

<span data-ttu-id="5d6b3-126">Evite misturar adições ou alterações de conteúdo com renomeações e exclusões de arquivos.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-126">Avoid mixing content additions or change with file renames and deletes.</span></span> <span data-ttu-id="5d6b3-127">Qualquer arquivo que seja renomeado ou excluído deve ser adicionado ao arquivo de redirecionamento mestre.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-127">Any file that is renamed or deleted must be added to the master redirection file.</span></span> <span data-ttu-id="5d6b3-128">Quando possível, você também deve atualizar todos os arquivos vinculados ao conteúdo renomeado ou excluído.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-128">When possible, you should also update any files that link to the renamed or deleted content.</span></span> <span data-ttu-id="5d6b3-129">Isso inclui todos os arquivos do sumário.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-129">This includes any TOC files.</span></span>

## <a name="docs-pr-validation-service"></a><span data-ttu-id="5d6b3-130">Serviço de validação de PR do Docs</span><span class="sxs-lookup"><span data-stu-id="5d6b3-130">Docs PR validation service</span></span>

<span data-ttu-id="5d6b3-131">O serviço de validação de PR do Docs é um aplicativo do GitHub que executa regras de validação nos arquivos em uma PR.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-131">The Docs PR validation service is a GitHub app that runs validation rules on the files in a PR.</span></span> <span data-ttu-id="5d6b3-132">Você precisa corrigir quaisquer erros ou avisos (confira as exceções) relatados pelo serviço de validação.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-132">You must fix any errors or warnings (see exceptions) reported by the validation service.</span></span>

<span data-ttu-id="5d6b3-133">Os seguintes avisos podem ser ignorados:</span><span class="sxs-lookup"><span data-stu-id="5d6b3-133">The following warnings can be ignored:</span></span>

```
Can't find service name for `<version>/<modulepath>/About/About.md`
```

```
Metadata with following name(s) are not allowed to be set in Yaml header, or as file level
metadata in docfx.json, or as global metadata in docfx.json: `locale`. They are generated by
Docs platform, so the values set in these 3 places will be ignored. Please remove them from all
3 places to resolve the warning.
```

<span data-ttu-id="5d6b3-134">Você verá o seguinte comportamento:</span><span class="sxs-lookup"><span data-stu-id="5d6b3-134">You'll see the following behavior:</span></span>

1. <span data-ttu-id="5d6b3-135">Você envia uma PR.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-135">You submit a PR.</span></span>
1. <span data-ttu-id="5d6b3-136">No comentário do GitHub que indica o status da PR, você verá o status de "verificações" habilitadas no repositório.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-136">In the GitHub comment that indicates the status of your PR, you'll see the status of "checks" enabled on the repo.</span></span> <span data-ttu-id="5d6b3-137">Neste exemplo, há duas verificações habilitadas, "Validação do Commit" e "OpenPublishing.Build":</span><span class="sxs-lookup"><span data-stu-id="5d6b3-137">Note that in this example, there are two checks enabled, "Commit Validation" and "OpenPublishing.Build":</span></span>

   ![algumas verificações falharam](media/pull-requests/validation-failed.png)

   <span data-ttu-id="5d6b3-139">O build poderá passar mesmo se a validação do commit falhar.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-139">The build can pass even if commit validation fails.</span></span>

1. <span data-ttu-id="5d6b3-140">Clique em **Detalhes** para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-140">Click **Details** for more information.</span></span>
1. <span data-ttu-id="5d6b3-141">Na página Detalhes, você verá todas as verificações de validação que falharam, com informações sobre como corrigir os problemas.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-141">On the Details page, you'll see all the validation checks that failed, with information about how to fix the issues.</span></span>
1. <span data-ttu-id="5d6b3-142">Quando a validação é bem-sucedida, o seguinte comentário é adicionado à PR:</span><span class="sxs-lookup"><span data-stu-id="5d6b3-142">When validation succeeds, the following comment is added to the PR:</span></span>

   ![validação de build](media/pull-requests/build-validation.png)

> [!NOTE]
> <span data-ttu-id="5d6b3-144">Se você for um colaborador externo (não funcionário da Microsoft), não terá acesso aos relatórios detalhados de build nem aos links de visualização.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-144">If you are an external (not a Microsoft employee) contributor you do not have access to the detailed build reports or preview links.</span></span>

<span data-ttu-id="5d6b3-145">Quando a PR é revisada por um membro da equipe do PowerShell-Docs, você pode ser solicitado a fazer alterações ou corrigir problemas sinalizados pelo relatório de validação.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-145">When the PR is reviewed by a member of the PowerShell-Docs team, you may be asked to make changes or fix problems flagged by the validation report.</span></span> <span data-ttu-id="5d6b3-146">A equipe do PowerShell-Docs pode ajudar você a entender como corrigir e evitar esses problemas para envios futuros.</span><span class="sxs-lookup"><span data-stu-id="5d6b3-146">The PowerShell-Docs team can help you understand how to fix and avoid these problems for future submissions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5d6b3-147">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5d6b3-147">Next steps</span></span>

[<span data-ttu-id="5d6b3-148">Guia de estilo do PowerShell-Docs</span><span class="sxs-lookup"><span data-stu-id="5d6b3-148">PowerShell-Docs style guide</span></span>](powershell-style-guide.md)

## <a name="additional-resources"></a><span data-ttu-id="5d6b3-149">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5d6b3-149">Additional resources</span></span>

[<span data-ttu-id="5d6b3-150">Como gerenciamos solicitações de pull</span><span class="sxs-lookup"><span data-stu-id="5d6b3-150">How we manage pull requests</span></span>](managing-pull-requests.md)
