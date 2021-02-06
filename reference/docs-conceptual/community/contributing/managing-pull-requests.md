---
title: Como gerenciamos solicitações de pull
description: Este artigo explica como a equipe do PowerShell-Docs gerencia solicitações de pull.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 7050db6ad30963d0a75b2a083daace494d703027
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "99596566"
---
# <a name="managing-pull-requests"></a><span data-ttu-id="dbc88-103">Gerenciar solicitações de pull</span><span class="sxs-lookup"><span data-stu-id="dbc88-103">Managing pull requests</span></span>

<span data-ttu-id="dbc88-104">Este artigo documenta como gerenciamos solicitações de pull no repositório do PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="dbc88-104">This article documents how we manage pull requests in the PowerShell-Docs repository.</span></span> <span data-ttu-id="dbc88-105">O artigo foi projetado para ser um auxílio de trabalho para membros da equipe do PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="dbc88-105">This article is designed to be a job aid for members of the PowerShell-Docs team.</span></span> <span data-ttu-id="dbc88-106">Ele é publicado aqui para fornecer transparência de processo para nossos colaboradores públicos.</span><span class="sxs-lookup"><span data-stu-id="dbc88-106">It's published here to provide process transparency for our public contributors.</span></span>

## <a name="best-practices"></a><span data-ttu-id="dbc88-107">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="dbc88-107">Best practices</span></span>

- <span data-ttu-id="dbc88-108">A pessoa que envia a PR não deve mesclar a PR sem uma revisão de par.</span><span class="sxs-lookup"><span data-stu-id="dbc88-108">The person submitting the PR shouldn't merge the PR without a peer review.</span></span>
- <span data-ttu-id="dbc88-109">Atribua o revisor em pares quando a PR for enviada.</span><span class="sxs-lookup"><span data-stu-id="dbc88-109">Assign the peer reviewer when the PR is submitted.</span></span> <span data-ttu-id="dbc88-110">A atribuição antecipada permite que o revisor responda mais cedo com comentários editoriais.</span><span class="sxs-lookup"><span data-stu-id="dbc88-110">Early assignment allows the reviewer to respond sooner with editorial remarks.</span></span>
- <span data-ttu-id="dbc88-111">Use os comentários para descrever a natureza da alteração ou o tipo de revisão solicitada.</span><span class="sxs-lookup"><span data-stu-id="dbc88-111">Use comments to describe the nature of the change or the type of review being requested.</span></span> <span data-ttu-id="dbc88-112">Mencione o revisor com @mention.</span><span class="sxs-lookup"><span data-stu-id="dbc88-112">Be sure to @mention the reviewer.</span></span> <span data-ttu-id="dbc88-113">Por exemplo, se a alteração for secundária, e você não precisar de uma revisão técnica completa, explique isso em um comentário.</span><span class="sxs-lookup"><span data-stu-id="dbc88-113">For example, if the change is minor and you don't need a full technical review, explain this in a comment.</span></span>

## <a name="pr-process-steps"></a><span data-ttu-id="dbc88-114">Etapas do processo de PR</span><span class="sxs-lookup"><span data-stu-id="dbc88-114">PR Process steps</span></span>

1. <span data-ttu-id="dbc88-115">Autor: criar a PR</span><span class="sxs-lookup"><span data-stu-id="dbc88-115">Writer: Create PR</span></span>
   - <span data-ttu-id="dbc88-116">Vincular quaisquer problemas resolvidos pela PR</span><span class="sxs-lookup"><span data-stu-id="dbc88-116">Link any issues resolved by the PR</span></span>
   - <span data-ttu-id="dbc88-117">Usar o recurso [autoclose](https://help.github.com/en/articles/closing-issues-using-keywords) do GitHub para fechar o problema</span><span class="sxs-lookup"><span data-stu-id="dbc88-117">Use GitHub's [autoclose](https://help.github.com/en/articles/closing-issues-using-keywords) feature to close the issue</span></span>
1. <span data-ttu-id="dbc88-118">Autor: atribuir revisor em pares</span><span class="sxs-lookup"><span data-stu-id="dbc88-118">Writer: Assign peer reviewer</span></span>
1. <span data-ttu-id="dbc88-119">Revisor: fazer a revisão e inserir comentários (conforme necessário)</span><span class="sxs-lookup"><span data-stu-id="dbc88-119">Reviewer: proofreads and comments (as necessary)</span></span>
1. <span data-ttu-id="dbc88-120">Autor: incorporar comentários da revisão</span><span class="sxs-lookup"><span data-stu-id="dbc88-120">Writer: Incorporate review feedback</span></span>
1. <span data-ttu-id="dbc88-121">Ambos: revisar a renderização de versão prévia</span><span class="sxs-lookup"><span data-stu-id="dbc88-121">Both: Review preview rendering</span></span>
1. <span data-ttu-id="dbc88-122">Ambos: revisar o relatório de validação, corrigir erros e avisos</span><span class="sxs-lookup"><span data-stu-id="dbc88-122">Both: Review validation report - fix warnings and errors</span></span>
1. <span data-ttu-id="dbc88-123">Autor: adicionar comentário de aprovação (incluir informações do Acrolinx)</span><span class="sxs-lookup"><span data-stu-id="dbc88-123">Writer: Add sign-off comment (include Acrolinx info)</span></span>
1. <span data-ttu-id="dbc88-124">Revisor: marcar a revisão como "Aprovada"</span><span class="sxs-lookup"><span data-stu-id="dbc88-124">Reviewer: Mark review "Approved"</span></span>
1. <span data-ttu-id="dbc88-125">Administrador do repositório: mesclar a PR (confira abaixo os critérios)</span><span class="sxs-lookup"><span data-stu-id="dbc88-125">Repo Admin: Merge PR (see below for criteria)</span></span>

## <a name="content-reviewer-checklist"></a><span data-ttu-id="dbc88-126">Lista de verificação do revisor de conteúdo</span><span class="sxs-lookup"><span data-stu-id="dbc88-126">Content Reviewer Checklist</span></span>

<span data-ttu-id="dbc88-127">Confira a [lista de verificação editorial](editorial-checklist.md) para obter uma listagem mais abrangente.</span><span class="sxs-lookup"><span data-stu-id="dbc88-127">See the [editorial checklist](editorial-checklist.md) for a more comprehensive list.</span></span>

- <span data-ttu-id="dbc88-128">Revisar gramática, estilo, concisão, precisão técnica</span><span class="sxs-lookup"><span data-stu-id="dbc88-128">Proofread for grammar, style, concision, technical accuracy</span></span>
- <span data-ttu-id="dbc88-129">Verificar se os exemplos ainda se aplicam à versão de destino</span><span class="sxs-lookup"><span data-stu-id="dbc88-129">Ensure examples still apply for the target version</span></span>
- <span data-ttu-id="dbc88-130">Conferir a renderização de versão prévia</span><span class="sxs-lookup"><span data-stu-id="dbc88-130">Check Preview rendering</span></span>
- <span data-ttu-id="dbc88-131">Conferir os metadados – ms.date, remover ms.assetid, garantir os campos obrigatórios</span><span class="sxs-lookup"><span data-stu-id="dbc88-131">Check metadata - ms.date, remove ms.assetid, ensure required fields</span></span>
- <span data-ttu-id="dbc88-132">Validar a correção de markdown</span><span class="sxs-lookup"><span data-stu-id="dbc88-132">Validate markdown correctness</span></span>
  - <span data-ttu-id="dbc88-133">Consulte Guia de estilo para regras de formatação específicas do conteúdo</span><span class="sxs-lookup"><span data-stu-id="dbc88-133">See style guide for content-specific formatting rules</span></span>
- <span data-ttu-id="dbc88-134">Reorganizar os exemplos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="dbc88-134">Reorganize examples as follows:</span></span>
  - <span data-ttu-id="dbc88-135">Sentença(s) de introdução</span><span class="sxs-lookup"><span data-stu-id="dbc88-135">Intro sentence(s)</span></span>
  - <span data-ttu-id="dbc88-136">Código e saída</span><span class="sxs-lookup"><span data-stu-id="dbc88-136">Code and output</span></span>
  - <span data-ttu-id="dbc88-137">Explicação detalhada do código (conforme necessário)</span><span class="sxs-lookup"><span data-stu-id="dbc88-137">Detailed explanation of code (as necessary)</span></span>
- <span data-ttu-id="dbc88-138">Verificar a precisão dos hiperlinks</span><span class="sxs-lookup"><span data-stu-id="dbc88-138">Check hyperlinks for accuracy</span></span>
  - <span data-ttu-id="dbc88-139">Substituir ou remover links TechNet/MSDN</span><span class="sxs-lookup"><span data-stu-id="dbc88-139">Replace or remove TechNet/MSDN links</span></span>
  - <span data-ttu-id="dbc88-140">Garantir o número mínimo de redirecionamentos para o destino</span><span class="sxs-lookup"><span data-stu-id="dbc88-140">Ensure minimum number of redirects to target</span></span>
  - <span data-ttu-id="dbc88-141">Garantir o HTTPS</span><span class="sxs-lookup"><span data-stu-id="dbc88-141">Ensure HTTPS</span></span>
  - <span data-ttu-id="dbc88-142">Corrigir tipo de link</span><span class="sxs-lookup"><span data-stu-id="dbc88-142">Correct link type</span></span>
    - <span data-ttu-id="dbc88-143">Links para arquivos locais</span><span class="sxs-lookup"><span data-stu-id="dbc88-143">File links for local files</span></span>
    - <span data-ttu-id="dbc88-144">Links de URL para arquivos fora do docset</span><span class="sxs-lookup"><span data-stu-id="dbc88-144">URL links for files outside of the docset</span></span>
  - <span data-ttu-id="dbc88-145">Remover localidades de URLs</span><span class="sxs-lookup"><span data-stu-id="dbc88-145">Remove locales from URLs</span></span>
  - <span data-ttu-id="dbc88-146">Simplificar URLs que apontam para `docs.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="dbc88-146">Simplify URLs pointing to `docs.microsoft.com`</span></span>

## <a name="branch-merge-process"></a><span data-ttu-id="dbc88-147">Processo de mesclagem de branch</span><span class="sxs-lookup"><span data-stu-id="dbc88-147">Branch Merge Process</span></span>

<span data-ttu-id="dbc88-148">O `staging` Branch é o único Branch que é mesclado no `live` .</span><span class="sxs-lookup"><span data-stu-id="dbc88-148">The `staging` branch is the only branch that is merged into `live`.</span></span> <span data-ttu-id="dbc88-149">As mesclagens de branches de curta duração (trabalho) devem ser restringidas.</span><span class="sxs-lookup"><span data-stu-id="dbc88-149">Merges from short-lived (working) branches should be squashed.</span></span>

| <span data-ttu-id="dbc88-150">*Mesclar de/para*</span><span class="sxs-lookup"><span data-stu-id="dbc88-150">*Merge from/to*</span></span>  | <span data-ttu-id="dbc88-151">*branch-lançamento*</span><span class="sxs-lookup"><span data-stu-id="dbc88-151">*release-branch*</span></span> | <span data-ttu-id="dbc88-152">*staging*</span><span class="sxs-lookup"><span data-stu-id="dbc88-152">*staging*</span></span>        | <span data-ttu-id="dbc88-153">*dinâmico*</span><span class="sxs-lookup"><span data-stu-id="dbc88-153">*live*</span></span>      |
| ---------------- |:----------------:|:----------------:|:-----------:|
| <span data-ttu-id="dbc88-154">*branch-trabalho*</span><span class="sxs-lookup"><span data-stu-id="dbc88-154">*working-branch*</span></span> | <span data-ttu-id="dbc88-155">squash e mesclar</span><span class="sxs-lookup"><span data-stu-id="dbc88-155">squash and merge</span></span> | <span data-ttu-id="dbc88-156">squash e mesclar</span><span class="sxs-lookup"><span data-stu-id="dbc88-156">squash and merge</span></span> | <span data-ttu-id="dbc88-157">Não permitido</span><span class="sxs-lookup"><span data-stu-id="dbc88-157">Not allowed</span></span> |
| <span data-ttu-id="dbc88-158">*branch-lançamento*</span><span class="sxs-lookup"><span data-stu-id="dbc88-158">*release-branch*</span></span> | &mdash;          | <span data-ttu-id="dbc88-159">mesclar</span><span class="sxs-lookup"><span data-stu-id="dbc88-159">merge</span></span>            | <span data-ttu-id="dbc88-160">Não permitido</span><span class="sxs-lookup"><span data-stu-id="dbc88-160">Not allowed</span></span> |
| <span data-ttu-id="dbc88-161">*staging*</span><span class="sxs-lookup"><span data-stu-id="dbc88-161">*staging*</span></span>        | <span data-ttu-id="dbc88-162">trocar base</span><span class="sxs-lookup"><span data-stu-id="dbc88-162">rebase</span></span>           | &mdash;          | <span data-ttu-id="dbc88-163">mesclar</span><span class="sxs-lookup"><span data-stu-id="dbc88-163">merge</span></span>       |

### <a name="pr-merger-checklist"></a><span data-ttu-id="dbc88-164">Lista de verificação de mesclagem de PR</span><span class="sxs-lookup"><span data-stu-id="dbc88-164">PR Merger checklist</span></span>

- <span data-ttu-id="dbc88-165">Revisão de conteúdo concluída</span><span class="sxs-lookup"><span data-stu-id="dbc88-165">Content review complete</span></span>
- <span data-ttu-id="dbc88-166">Branch de destino correto para a alteração</span><span class="sxs-lookup"><span data-stu-id="dbc88-166">Correct target branch for the change</span></span>
- <span data-ttu-id="dbc88-167">Sem conflitos de mesclagem</span><span class="sxs-lookup"><span data-stu-id="dbc88-167">No merge conflicts</span></span>
- <span data-ttu-id="dbc88-168">Todas as validações e etapas de build aprovadas</span><span class="sxs-lookup"><span data-stu-id="dbc88-168">All validation and build step pass</span></span>
  - <span data-ttu-id="dbc88-169">Avisos e sugestões devem ser corrigidos (confira [Observações](#notes) para ver exceções)</span><span class="sxs-lookup"><span data-stu-id="dbc88-169">Warnings and suggestions should be fixed (see [Notes](#notes) for exceptions)</span></span>
  - <span data-ttu-id="dbc88-170">Nenhum link desfeito</span><span class="sxs-lookup"><span data-stu-id="dbc88-170">No broken links</span></span>
- <span data-ttu-id="dbc88-171">Mesclar de acordo com a tabela</span><span class="sxs-lookup"><span data-stu-id="dbc88-171">Merge according to table</span></span>

### <a name="notes"></a><span data-ttu-id="dbc88-172">Observações</span><span class="sxs-lookup"><span data-stu-id="dbc88-172">Notes</span></span>

<span data-ttu-id="dbc88-173">Os seguintes avisos podem ser ignorados:</span><span class="sxs-lookup"><span data-stu-id="dbc88-173">The following warnings can be ignored:</span></span>

```
Can't find service name for `<version>/<modulepath>/About/About.md`
```

```
Metadata with following name(s) are not allowed to be set in Yaml header, or as file level
metadata in docfx.json, or as global metadata in docfx.json: `locale`. They are generated by
Docs platform, so the values set in these 3 places will be ignored. Please remove them from all
3 places to resolve the warning.
```

<span data-ttu-id="dbc88-174">Quando uma PR é mesclada, o HEAD do branch de destino é alterado.</span><span class="sxs-lookup"><span data-stu-id="dbc88-174">When a PR is merged, the HEAD of the target branch is changed.</span></span> <span data-ttu-id="dbc88-175">Qualquer PR aberta com base no HEAD anterior agora está desatualizada.</span><span class="sxs-lookup"><span data-stu-id="dbc88-175">Any open PRs that were based on the previous HEAD are now outdated.</span></span> <span data-ttu-id="dbc88-176">A PR desatualizada pode ser mesclada usando direitos de administrador para substituir os avisos de mesclagem no GitHub.</span><span class="sxs-lookup"><span data-stu-id="dbc88-176">The outdated PR can be merged using Admin rights to override the merge warnings in GitHub.</span></span> <span data-ttu-id="dbc88-177">Isso é seguro caso as PRs mescladas anteriormente não tenham tocado os mesmos arquivos.</span><span class="sxs-lookup"><span data-stu-id="dbc88-177">This is safe to do if the previously merged PR(s) have not touched the same files.</span></span> <span data-ttu-id="dbc88-178">No entanto, a opção mais segura é clicar no botão **Atualizar Branch**.</span><span class="sxs-lookup"><span data-stu-id="dbc88-178">However, clicking the **Update Branch** button is the safest option.</span></span> <span data-ttu-id="dbc88-179">Você pode ter conflitos não resolvidos que precisam ser corrigidos.</span><span class="sxs-lookup"><span data-stu-id="dbc88-179">You may have unresolved conflicts that need to be fixed.</span></span>

## <a name="publishing-to-live"></a><span data-ttu-id="dbc88-180">Publicar no site dinâmico</span><span class="sxs-lookup"><span data-stu-id="dbc88-180">Publishing to Live</span></span>

<span data-ttu-id="dbc88-181">Periodicamente, as alterações acumuladas no branch `staging` precisam ser publicadas no site dinâmico.</span><span class="sxs-lookup"><span data-stu-id="dbc88-181">Periodically, the changes accumulated in the `staging` branch need to be published to the live website.</span></span>

- <span data-ttu-id="dbc88-182">A `staging` ramificação é mesclada a `live` cada dia da semana em 15h PST.</span><span class="sxs-lookup"><span data-stu-id="dbc88-182">The `staging` branch is merged to `live` each weekday at 3pm PST.</span></span>
- <span data-ttu-id="dbc88-183">O branch `staging` deve ser mesclado no `live` após qualquer alteração significativa.</span><span class="sxs-lookup"><span data-stu-id="dbc88-183">The `staging` branch should be merged to `live` after any significant change.</span></span>
  - <span data-ttu-id="dbc88-184">Alterações em 50 ou mais arquivos</span><span class="sxs-lookup"><span data-stu-id="dbc88-184">Changes to 50 or more files</span></span>
  - <span data-ttu-id="dbc88-185">Depois de mesclar um branch de lançamento</span><span class="sxs-lookup"><span data-stu-id="dbc88-185">After merging a release branch</span></span>
  - <span data-ttu-id="dbc88-186">Alterações nas configurações de repositório ou docset (docfx.json, configurações OPS, scripts de compilação etc.)</span><span class="sxs-lookup"><span data-stu-id="dbc88-186">Changes to repo or docset configurations (docfx.json, OPS configs, build scripts, etc.)</span></span>
  - <span data-ttu-id="dbc88-187">Alterações no arquivo de redirecionamento</span><span class="sxs-lookup"><span data-stu-id="dbc88-187">Changes to the redirection file</span></span>
  - <span data-ttu-id="dbc88-188">Alterações no TOC</span><span class="sxs-lookup"><span data-stu-id="dbc88-188">Changes to the TOC</span></span>
  - <span data-ttu-id="dbc88-189">Depois de mesclar um branch de "projeto" (reorganização de conteúdo, atualização em massa etc.)</span><span class="sxs-lookup"><span data-stu-id="dbc88-189">After merging a "project" branch (content reorg, bulk update, etc.)</span></span>
