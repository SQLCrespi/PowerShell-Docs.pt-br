---
title: Como gerenciamos solicitações de pull
description: Este artigo explica como a equipe do PowerShell-Docs gerencia solicitações de pull.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: af5280e91aa3744b6172dc3555df6989cb0ce1a2
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86158166"
---
# <a name="managing-pull-requests"></a><span data-ttu-id="b63c7-103">Gerenciar solicitações de pull</span><span class="sxs-lookup"><span data-stu-id="b63c7-103">Managing pull requests</span></span>

<span data-ttu-id="b63c7-104">Este artigo documenta como gerenciamos solicitações de pull no repositório do PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="b63c7-104">This article documents how we manage pull requests in the PowerShell-Docs repository.</span></span> <span data-ttu-id="b63c7-105">O artigo foi projetado para ser um auxílio de trabalho para membros da equipe do PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="b63c7-105">This article is designed to be a job aid for members of the PowerShell-Docs team.</span></span> <span data-ttu-id="b63c7-106">Publicamos aqui para fornecer transparência quanto ao processo para nossos colaboradores públicos.</span><span class="sxs-lookup"><span data-stu-id="b63c7-106">It is published here to provide process transparency for our public contributors.</span></span>

## <a name="best-practices"></a><span data-ttu-id="b63c7-107">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="b63c7-107">Best practices</span></span>

- <span data-ttu-id="b63c7-108">A pessoa que envia a PR (solicitação de pull) não deve mesclá-la sem uma revisão em pares.</span><span class="sxs-lookup"><span data-stu-id="b63c7-108">The person submitting the PR should not merge the PR without a peer review.</span></span>
- <span data-ttu-id="b63c7-109">Atribua o revisor em pares quando a PR for enviada.</span><span class="sxs-lookup"><span data-stu-id="b63c7-109">Assign the peer reviewer when the PR is submitted.</span></span> <span data-ttu-id="b63c7-110">A atribuição antecipada permite que o revisor responda mais cedo com comentários editoriais.</span><span class="sxs-lookup"><span data-stu-id="b63c7-110">Early assignment allows the reviewer to respond sooner with editorial remarks.</span></span>
- <span data-ttu-id="b63c7-111">Use os comentários para descrever a natureza da alteração ou o tipo de revisão solicitada.</span><span class="sxs-lookup"><span data-stu-id="b63c7-111">Use comments to describe the nature of the change or the type of review being requested.</span></span> <span data-ttu-id="b63c7-112">Mencione o revisor com @mention.</span><span class="sxs-lookup"><span data-stu-id="b63c7-112">Be sure to @mention the reviewer.</span></span> <span data-ttu-id="b63c7-113">Por exemplo, se a alteração for secundária, e você não precisar de uma revisão técnica completa, explique isso em um comentário.</span><span class="sxs-lookup"><span data-stu-id="b63c7-113">For example, if the change is minor and you don't need a full technical review, explain this in a comment.</span></span>

## <a name="pr-process-steps"></a><span data-ttu-id="b63c7-114">Etapas do processo de PR</span><span class="sxs-lookup"><span data-stu-id="b63c7-114">PR Process steps</span></span>

1. <span data-ttu-id="b63c7-115">Autor: criar a PR</span><span class="sxs-lookup"><span data-stu-id="b63c7-115">Writer: Create PR</span></span>
   - <span data-ttu-id="b63c7-116">Vincular quaisquer problemas resolvidos pela PR</span><span class="sxs-lookup"><span data-stu-id="b63c7-116">Link any issues resolved by the PR</span></span>
   - <span data-ttu-id="b63c7-117">Usar o recurso [autoclose](https://help.github.com/en/articles/closing-issues-using-keywords) do GitHub para fechar o problema</span><span class="sxs-lookup"><span data-stu-id="b63c7-117">Use GitHub's [autoclose](https://help.github.com/en/articles/closing-issues-using-keywords) feature to close the issue</span></span>
1. <span data-ttu-id="b63c7-118">Autor: atribuir revisor em pares</span><span class="sxs-lookup"><span data-stu-id="b63c7-118">Writer: Assign peer reviewer</span></span>
1. <span data-ttu-id="b63c7-119">Revisor: fazer a revisão e inserir comentários (conforme necessário)</span><span class="sxs-lookup"><span data-stu-id="b63c7-119">Reviewer: proofreads and comments (as necessary)</span></span>
1. <span data-ttu-id="b63c7-120">Autor: incorporar comentários da revisão</span><span class="sxs-lookup"><span data-stu-id="b63c7-120">Writer: Incorporate review feedback</span></span>
1. <span data-ttu-id="b63c7-121">Ambos: revisar a renderização de versão prévia</span><span class="sxs-lookup"><span data-stu-id="b63c7-121">Both: Review preview rendering</span></span>
1. <span data-ttu-id="b63c7-122">Ambos: revisar o relatório de validação, corrigir erros e avisos</span><span class="sxs-lookup"><span data-stu-id="b63c7-122">Both: Review validation report - fix warnings and errors</span></span>
1. <span data-ttu-id="b63c7-123">Autor: adicionar comentário de aprovação (incluir informações do Acrolinx)</span><span class="sxs-lookup"><span data-stu-id="b63c7-123">Writer: Add sign-off comment (include Acrolinx info)</span></span>
1. <span data-ttu-id="b63c7-124">Revisor: marcar a revisão como "Aprovada"</span><span class="sxs-lookup"><span data-stu-id="b63c7-124">Reviewer: Mark review "Approved"</span></span>
1. <span data-ttu-id="b63c7-125">Administrador do repositório: mesclar a PR (confira abaixo os critérios)</span><span class="sxs-lookup"><span data-stu-id="b63c7-125">Repo Admin: Merge PR (see below for criteria)</span></span>

## <a name="content-reviewer-checklist"></a><span data-ttu-id="b63c7-126">Lista de verificação do revisor de conteúdo</span><span class="sxs-lookup"><span data-stu-id="b63c7-126">Content Reviewer Checklist</span></span>

<span data-ttu-id="b63c7-127">Confira a [lista de verificação editorial](editorial-checklist.md) para obter uma listagem mais abrangente.</span><span class="sxs-lookup"><span data-stu-id="b63c7-127">See the [editorial checklist](editorial-checklist.md) for a more comprehensive list.</span></span>

- <span data-ttu-id="b63c7-128">Revisar gramática, estilo, concisão, precisão técnica</span><span class="sxs-lookup"><span data-stu-id="b63c7-128">Proofread for grammar, style, concision, technical accuracy</span></span>
- <span data-ttu-id="b63c7-129">Verificar se os exemplos ainda se aplicam à versão de destino</span><span class="sxs-lookup"><span data-stu-id="b63c7-129">Ensure examples still apply for the target version</span></span>
- <span data-ttu-id="b63c7-130">Conferir a renderização de versão prévia</span><span class="sxs-lookup"><span data-stu-id="b63c7-130">Check Preview rendering</span></span>
- <span data-ttu-id="b63c7-131">Conferir os metadados – ms.date, remover ms.assetid, garantir os campos obrigatórios</span><span class="sxs-lookup"><span data-stu-id="b63c7-131">Check metadata - ms.date, remove ms.assetid, ensure required fields</span></span>
- <span data-ttu-id="b63c7-132">Validar a correção de markdown</span><span class="sxs-lookup"><span data-stu-id="b63c7-132">Validate markdown correctness</span></span>
  - <span data-ttu-id="b63c7-133">Conferir o guia de estilo para a formatação de conteúdo específico</span><span class="sxs-lookup"><span data-stu-id="b63c7-133">See style guide for formatting specific content</span></span>
- <span data-ttu-id="b63c7-134">Reorganizar os exemplos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b63c7-134">Reorganize examples as follows:</span></span>
  - <span data-ttu-id="b63c7-135">Sentença(s) de introdução</span><span class="sxs-lookup"><span data-stu-id="b63c7-135">Intro sentence(s)</span></span>
  - <span data-ttu-id="b63c7-136">Código e saída</span><span class="sxs-lookup"><span data-stu-id="b63c7-136">Code and output</span></span>
  - <span data-ttu-id="b63c7-137">Explicação detalhada do código (conforme necessário)</span><span class="sxs-lookup"><span data-stu-id="b63c7-137">Detailed explanation of code (as necessary)</span></span>
- <span data-ttu-id="b63c7-138">Verificar a precisão dos hiperlinks</span><span class="sxs-lookup"><span data-stu-id="b63c7-138">Check hyperlinks for accuracy</span></span>
  - <span data-ttu-id="b63c7-139">Substituir ou remover links TechNet/MSDN</span><span class="sxs-lookup"><span data-stu-id="b63c7-139">Replace or remove TechNet/MSDN links</span></span>
  - <span data-ttu-id="b63c7-140">Garantir o número mínimo de redirecionamentos para o destino</span><span class="sxs-lookup"><span data-stu-id="b63c7-140">Ensure minimum number of redirects to target</span></span>
  - <span data-ttu-id="b63c7-141">Garantir o HTTPS</span><span class="sxs-lookup"><span data-stu-id="b63c7-141">Ensure HTTPS</span></span>
  - <span data-ttu-id="b63c7-142">Corrigir tipo de link</span><span class="sxs-lookup"><span data-stu-id="b63c7-142">Correct link type</span></span>
    - <span data-ttu-id="b63c7-143">Links para arquivos locais</span><span class="sxs-lookup"><span data-stu-id="b63c7-143">File links for local files</span></span>
    - <span data-ttu-id="b63c7-144">Links de URL para arquivos fora do docset</span><span class="sxs-lookup"><span data-stu-id="b63c7-144">URL links for files outside of the docset</span></span>
  - <span data-ttu-id="b63c7-145">Remover localidades de URLs</span><span class="sxs-lookup"><span data-stu-id="b63c7-145">Remove locales from URLs</span></span>
  - <span data-ttu-id="b63c7-146">Simplificar URLs que apontam para `docs.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="b63c7-146">Simplify URLs pointing to `docs.microsoft.com`</span></span>

## <a name="branch-merge-process"></a><span data-ttu-id="b63c7-147">Processo de mesclagem de branch</span><span class="sxs-lookup"><span data-stu-id="b63c7-147">Branch Merge Process</span></span>

<span data-ttu-id="b63c7-148">O branch de preparo é o único que deve ser mesclado no branch dinâmico.</span><span class="sxs-lookup"><span data-stu-id="b63c7-148">The staging branch is the only branch that should ever be merged into live.</span></span> <span data-ttu-id="b63c7-149">As mesclagens de branches de curta duração (trabalho) devem ser restringidas.</span><span class="sxs-lookup"><span data-stu-id="b63c7-149">Merges from short-lived (working) branches should be squashed.</span></span>

| <span data-ttu-id="b63c7-150">*Mesclar de/para*</span><span class="sxs-lookup"><span data-stu-id="b63c7-150">*Merge from/to*</span></span>  | <span data-ttu-id="b63c7-151">*branch-lançamento*</span><span class="sxs-lookup"><span data-stu-id="b63c7-151">*release-branch*</span></span> | <span data-ttu-id="b63c7-152">*staging*</span><span class="sxs-lookup"><span data-stu-id="b63c7-152">*staging*</span></span>        | <span data-ttu-id="b63c7-153">*dinâmico*</span><span class="sxs-lookup"><span data-stu-id="b63c7-153">*live*</span></span>      |
| ---------------- |:----------------:|:----------------:|:-----------:|
| <span data-ttu-id="b63c7-154">*branch-trabalho*</span><span class="sxs-lookup"><span data-stu-id="b63c7-154">*working-branch*</span></span> | <span data-ttu-id="b63c7-155">squash e mesclar</span><span class="sxs-lookup"><span data-stu-id="b63c7-155">squash and merge</span></span> | <span data-ttu-id="b63c7-156">squash e mesclar</span><span class="sxs-lookup"><span data-stu-id="b63c7-156">squash and merge</span></span> | <span data-ttu-id="b63c7-157">Não permitido</span><span class="sxs-lookup"><span data-stu-id="b63c7-157">Not allowed</span></span> |
| <span data-ttu-id="b63c7-158">*branch-lançamento*</span><span class="sxs-lookup"><span data-stu-id="b63c7-158">*release-branch*</span></span> | &mdash;          | <span data-ttu-id="b63c7-159">mesclar</span><span class="sxs-lookup"><span data-stu-id="b63c7-159">merge</span></span>            | <span data-ttu-id="b63c7-160">Não permitido</span><span class="sxs-lookup"><span data-stu-id="b63c7-160">Not allowed</span></span> |
| <span data-ttu-id="b63c7-161">*staging*</span><span class="sxs-lookup"><span data-stu-id="b63c7-161">*staging*</span></span>        | <span data-ttu-id="b63c7-162">trocar base</span><span class="sxs-lookup"><span data-stu-id="b63c7-162">rebase</span></span>           | &mdash;          | <span data-ttu-id="b63c7-163">mesclar</span><span class="sxs-lookup"><span data-stu-id="b63c7-163">merge</span></span>       |

### <a name="pr-merger-checklist"></a><span data-ttu-id="b63c7-164">Lista de verificação de mesclagem de PR</span><span class="sxs-lookup"><span data-stu-id="b63c7-164">PR Merger checklist</span></span>

- <span data-ttu-id="b63c7-165">Revisão de conteúdo concluída</span><span class="sxs-lookup"><span data-stu-id="b63c7-165">Content review complete</span></span>
- <span data-ttu-id="b63c7-166">Branch de destino correto para a alteração</span><span class="sxs-lookup"><span data-stu-id="b63c7-166">Correct target branch for the change</span></span>
- <span data-ttu-id="b63c7-167">Sem conflitos de mesclagem</span><span class="sxs-lookup"><span data-stu-id="b63c7-167">No merge conflicts</span></span>
- <span data-ttu-id="b63c7-168">Todas as validações e etapas de build aprovadas</span><span class="sxs-lookup"><span data-stu-id="b63c7-168">All validation and build step pass</span></span>
  - <span data-ttu-id="b63c7-169">Avisos e sugestões devem ser corrigidos (confira [Observações](#notes) para ver exceções)</span><span class="sxs-lookup"><span data-stu-id="b63c7-169">Warnings and suggestions should be fixed (see [Notes](#notes) for exceptions)</span></span>
  - <span data-ttu-id="b63c7-170">Nenhum link desfeito</span><span class="sxs-lookup"><span data-stu-id="b63c7-170">No broken links</span></span>
- <span data-ttu-id="b63c7-171">Mesclar de acordo com a tabela</span><span class="sxs-lookup"><span data-stu-id="b63c7-171">Merge according to table</span></span>

### <a name="notes"></a><span data-ttu-id="b63c7-172">Observações</span><span class="sxs-lookup"><span data-stu-id="b63c7-172">Notes</span></span>

<span data-ttu-id="b63c7-173">Os seguintes avisos podem ser ignorados:</span><span class="sxs-lookup"><span data-stu-id="b63c7-173">The following warnings can be ignored:</span></span>

```
Can't find service name for `<version>/<modulepath>/About/About.md`
```

```
Metadata with following name(s) are not allowed to be set in Yaml header, or as file level
metadata in docfx.json, or as global metadata in docfx.json: `locale`. They are generated by
Docs platform, so the values set in these 3 places will be ignored. Please remove them from all
3 places to resolve the warning.
```

<span data-ttu-id="b63c7-174">Quando uma PR é mesclada, o HEAD do branch de destino é alterado.</span><span class="sxs-lookup"><span data-stu-id="b63c7-174">When a PR is merged, the HEAD of the target branch is changed.</span></span> <span data-ttu-id="b63c7-175">Qualquer PR aberta com base no HEAD anterior agora está desatualizada.</span><span class="sxs-lookup"><span data-stu-id="b63c7-175">Any open PRs that were based on the previous HEAD are now outdated.</span></span> <span data-ttu-id="b63c7-176">A PR desatualizada pode ser mesclada usando direitos de administrador para substituir os avisos de mesclagem no GitHub.</span><span class="sxs-lookup"><span data-stu-id="b63c7-176">The outdated PR can be merged using Admin rights to override the merge warnings in GitHub.</span></span> <span data-ttu-id="b63c7-177">Isso é seguro caso as PRs mescladas anteriormente não tenham tocado os mesmos arquivos.</span><span class="sxs-lookup"><span data-stu-id="b63c7-177">This is safe to do if the previously merged PR(s) have not touched the same files.</span></span> <span data-ttu-id="b63c7-178">No entanto, a opção mais segura é clicar no botão **Atualizar Branch**.</span><span class="sxs-lookup"><span data-stu-id="b63c7-178">However, clicking the **Update Branch** button is the safest option.</span></span> <span data-ttu-id="b63c7-179">Você pode ter conflitos não resolvidos que precisam ser corrigidos.</span><span class="sxs-lookup"><span data-stu-id="b63c7-179">You may have unresolved conflicts that need to be fixed.</span></span>

## <a name="publishing-to-live"></a><span data-ttu-id="b63c7-180">Publicar no site dinâmico</span><span class="sxs-lookup"><span data-stu-id="b63c7-180">Publishing to Live</span></span>

<span data-ttu-id="b63c7-181">Periodicamente, as alterações acumuladas no branch `staging` precisam ser publicadas no site dinâmico.</span><span class="sxs-lookup"><span data-stu-id="b63c7-181">Periodically, the changes accumulated in the `staging` branch need to be published to the live website.</span></span> <span data-ttu-id="b63c7-182">Isso exige a mesclagem do branch `staging` no branch `live`.</span><span class="sxs-lookup"><span data-stu-id="b63c7-182">This require merging the `staging` branch into the `live` branch.</span></span>

- <span data-ttu-id="b63c7-183">O branch `staging` deve ser mesclado no `live` pelo menos uma vez por semana.</span><span class="sxs-lookup"><span data-stu-id="b63c7-183">The `staging` branch should be merged to `live` at least once per week.</span></span>
- <span data-ttu-id="b63c7-184">O branch `staging` deve ser mesclado no `live` após qualquer alteração significativa.</span><span class="sxs-lookup"><span data-stu-id="b63c7-184">The `staging` branch should be merged to `live` after any significant change.</span></span>
  - <span data-ttu-id="b63c7-185">Alterações em 50 ou mais arquivos</span><span class="sxs-lookup"><span data-stu-id="b63c7-185">Changes to 50 or more files</span></span>
  - <span data-ttu-id="b63c7-186">Depois de mesclar um branch de lançamento</span><span class="sxs-lookup"><span data-stu-id="b63c7-186">After merging a release branch</span></span>
  - <span data-ttu-id="b63c7-187">Alterações nas configurações de repositório ou docset (docfx.json, configurações OPS, scripts de compilação etc.)</span><span class="sxs-lookup"><span data-stu-id="b63c7-187">Changes to repo or docset configurations (docfx.json, OPS configs, build scripts, etc.)</span></span>
  - <span data-ttu-id="b63c7-188">Alterações no arquivo de redirecionamento</span><span class="sxs-lookup"><span data-stu-id="b63c7-188">Changes to the redirection file</span></span>
  - <span data-ttu-id="b63c7-189">Alterações no TOC</span><span class="sxs-lookup"><span data-stu-id="b63c7-189">Changes to the TOC</span></span>
  - <span data-ttu-id="b63c7-190">Depois de mesclar um branch de "projeto" (reorganização de conteúdo, atualização em massa etc.)</span><span class="sxs-lookup"><span data-stu-id="b63c7-190">After merging a "project" branch (content reorg, bulk update, etc.)</span></span>
