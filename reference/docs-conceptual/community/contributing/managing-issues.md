---
title: Como gerenciamos problemas
description: Este artigo explica como a equipe do PowerShell-Docs gerencia solicitações de pull.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 018200f1a9384f1ea956c9b27a7605db21f2da9e
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692533"
---
# <a name="how-we-manage-issues"></a><span data-ttu-id="c448f-103">Como gerenciamos problemas</span><span class="sxs-lookup"><span data-stu-id="c448f-103">How we manage issues</span></span>

<span data-ttu-id="c448f-104">Este artigo documenta como gerenciamos problemas no repositório do PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="c448f-104">This article documents how we manage issues in the PowerShell-Docs repo.</span></span> <span data-ttu-id="c448f-105">O artigo foi projetado para ser um auxílio de trabalho para membros da equipe do PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="c448f-105">This article is designed to be a job aid for members of the PowerShell-Docs team.</span></span> <span data-ttu-id="c448f-106">Publicamos aqui para fornecer transparência quanto ao processo para nossos colaboradores públicos.</span><span class="sxs-lookup"><span data-stu-id="c448f-106">It is published here to provide process transparency for our public contributors.</span></span>

## <a name="sources-of-issues"></a><span data-ttu-id="c448f-107">Fontes de problemas</span><span class="sxs-lookup"><span data-stu-id="c448f-107">Sources of issues</span></span>

- <span data-ttu-id="c448f-108">Colaboradores da Comunidade</span><span class="sxs-lookup"><span data-stu-id="c448f-108">Community contributors</span></span>
- <span data-ttu-id="c448f-109">Colaboradores internos</span><span class="sxs-lookup"><span data-stu-id="c448f-109">Internal contributors</span></span>
- <span data-ttu-id="c448f-110">Transcrições de comentários de canais de mídia social</span><span class="sxs-lookup"><span data-stu-id="c448f-110">Transcriptions of comments from social media channels</span></span>
- <span data-ttu-id="c448f-111">Comentários por meio do formulário de comentários do Docs</span><span class="sxs-lookup"><span data-stu-id="c448f-111">Feedback via the Docs feedback form</span></span>

## <a name="response-time-targets"></a><span data-ttu-id="c448f-112">Metas de tempo de resposta</span><span class="sxs-lookup"><span data-stu-id="c448f-112">Response time targets</span></span>

- <span data-ttu-id="c448f-113">Triagem - 5 dias úteis</span><span class="sxs-lookup"><span data-stu-id="c448f-113">Triaged - 5 business days</span></span>
- <span data-ttu-id="c448f-114">Correção ou alteração - nenhuma meta específica - melhor esforço</span><span class="sxs-lookup"><span data-stu-id="c448f-114">Fix or change - no specific target - best effort only</span></span>

### <a name="labeling--milestones"></a><span data-ttu-id="c448f-115">Rótulos & marcos</span><span class="sxs-lookup"><span data-stu-id="c448f-115">Labeling & Milestones</span></span>

#### <a name="label-types"></a><span data-ttu-id="c448f-116">Tipos de rótulo</span><span class="sxs-lookup"><span data-stu-id="c448f-116">Label Types</span></span>

|<span data-ttu-id="c448f-117">Prefixo</span><span class="sxs-lookup"><span data-stu-id="c448f-117">Prefix</span></span>  | <span data-ttu-id="c448f-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="c448f-118">Description</span></span>                                                         |
|------- | --------------------------------------------------------------------|
|<span data-ttu-id="c448f-119">Área</span><span class="sxs-lookup"><span data-stu-id="c448f-119">Area</span></span>    | <span data-ttu-id="c448f-120">Usado para indicar qual parte do PowerShell ou os documentos que o problema está discutindo.</span><span class="sxs-lookup"><span data-stu-id="c448f-120">Used to indicate what part of PowerShell or the docs that the issue is discussing.</span></span><br><span data-ttu-id="c448f-121">Útil para os proprietários de recursos encontrarem problemas para seus recursos.</span><span class="sxs-lookup"><span data-stu-id="c448f-121">Useful for feature owners to find issues for their feature.</span></span>|
|<span data-ttu-id="c448f-122">Pri</span><span class="sxs-lookup"><span data-stu-id="c448f-122">Pri</span></span>     | <span data-ttu-id="c448f-123">Usado para indicar a prioridade do problema.</span><span class="sxs-lookup"><span data-stu-id="c448f-123">Used to indicate the priority of the issue.</span></span> <span data-ttu-id="c448f-124">Intervalo de valores de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="c448f-124">Value range 0-4.</span></span>        |
|<span data-ttu-id="c448f-125">Problema</span><span class="sxs-lookup"><span data-stu-id="c448f-125">Issue</span></span>   | <span data-ttu-id="c448f-126">Usado para classificar o tipo de comentário para o problema</span><span class="sxs-lookup"><span data-stu-id="c448f-126">Used to classify the type of feedback for issue</span></span>                     |
|<span data-ttu-id="c448f-127">Revisão</span><span class="sxs-lookup"><span data-stu-id="c448f-127">Review</span></span>  | <span data-ttu-id="c448f-128">Usado para problemas que exigem uma análise adicional da equipe</span><span class="sxs-lookup"><span data-stu-id="c448f-128">Used for issue that require further review by the team</span></span>              |
|<span data-ttu-id="c448f-129">Status</span><span class="sxs-lookup"><span data-stu-id="c448f-129">Status</span></span>  | <span data-ttu-id="c448f-130">Usado para indicar o status do item de trabalho</span><span class="sxs-lookup"><span data-stu-id="c448f-130">Used to indicate the status of the work item</span></span>                        |
|<span data-ttu-id="c448f-131">Aguardando</span><span class="sxs-lookup"><span data-stu-id="c448f-131">Waiting</span></span> | <span data-ttu-id="c448f-132">Usado para indicar que estamos aguardando algo</span><span class="sxs-lookup"><span data-stu-id="c448f-132">Used to indicate that we are waiting on something</span></span>                   |

#### <a name="milestones"></a><span data-ttu-id="c448f-133">Marcos</span><span class="sxs-lookup"><span data-stu-id="c448f-133">Milestones</span></span>

<span data-ttu-id="c448f-134">Os problemas e solicitações de pull devem ser marcados com o marco apropriado.</span><span class="sxs-lookup"><span data-stu-id="c448f-134">Issues and PRs should be tagged with the appropriate milestone.</span></span> <span data-ttu-id="c448f-135">Se o problema não for direcionado a uma versão específica, nenhum marco será usado.</span><span class="sxs-lookup"><span data-stu-id="c448f-135">If the issue is not targeted for a specific version then no milestone is used.</span></span> <span data-ttu-id="c448f-136">Os problemas para solicitações de pulls de documentação para alterações que ainda precisam ser mescladas na base de código do PowerShell devem ser atribuídos ao marco **Futuro**.</span><span class="sxs-lookup"><span data-stu-id="c448f-136">Issues for Docs PRs for changes that have yet to be merged into the PowerShell code base should be assigned to the **Future** milestone.</span></span> <span data-ttu-id="c448f-137">Após a alteração do código ter sido mesclada, altere o marco para a versão apropriada.</span><span class="sxs-lookup"><span data-stu-id="c448f-137">After the code change has been merged, change the milestone to the appropriate version.</span></span>

|    <span data-ttu-id="c448f-138">Marco</span><span class="sxs-lookup"><span data-stu-id="c448f-138">Milestone</span></span>     |                    <span data-ttu-id="c448f-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="c448f-139">Description</span></span>                     |
| ---------------- | -------------------------------------------------- |
| <span data-ttu-id="c448f-140">6.x</span><span class="sxs-lookup"><span data-stu-id="c448f-140">6.x</span></span>              | <span data-ttu-id="c448f-141">Itens de trabalho relacionados ao PowerShell 6.0 a 6.2. x</span><span class="sxs-lookup"><span data-stu-id="c448f-141">Work items related to PowerShell 6.0 through 6.2.x</span></span> |
| <span data-ttu-id="c448f-142">7.0.0</span><span class="sxs-lookup"><span data-stu-id="c448f-142">7.0.0</span></span>            | <span data-ttu-id="c448f-143">Itens de trabalho relacionados ao PowerShell 7.0</span><span class="sxs-lookup"><span data-stu-id="c448f-143">Work items related to PowerShell 7.0</span></span>               |
| <span data-ttu-id="c448f-144">7.1.0</span><span class="sxs-lookup"><span data-stu-id="c448f-144">7.1.0</span></span>            | <span data-ttu-id="c448f-145">Itens de trabalho relacionados ao PowerShell 7.1</span><span class="sxs-lookup"><span data-stu-id="c448f-145">Work items related to PowerShell 7.1</span></span>               |
| <span data-ttu-id="c448f-146">Futuro</span><span class="sxs-lookup"><span data-stu-id="c448f-146">Future</span></span>           | <span data-ttu-id="c448f-147">Itens de trabalho relacionados a uma versão futura do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c448f-147">Work items a future version of PowerShell</span></span>          |
| <span data-ttu-id="c448f-148">PSReadline-vNext</span><span class="sxs-lookup"><span data-stu-id="c448f-148">PSReadline-vNext</span></span> | <span data-ttu-id="c448f-149">Itens de trabalho relacionados a uma versão futura do PSReadline</span><span class="sxs-lookup"><span data-stu-id="c448f-149">Work items a future version of PSReadline</span></span>          |

## <a name="triage-process"></a><span data-ttu-id="c448f-150">Processo de triagem</span><span class="sxs-lookup"><span data-stu-id="c448f-150">Triage process</span></span>

<span data-ttu-id="c448f-151">A equipe de documentação do PowerShell se reúne uma vez por semana para discutir os problemas adicionados desde a última reunião.</span><span class="sxs-lookup"><span data-stu-id="c448f-151">The PowerShell docs team meets once per week to discuss any issues added since last meeting.</span></span> <span data-ttu-id="c448f-152">Considera-se que um problema passou por triagem quando os rótulos foram atribuídos ou um proprietário foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="c448f-152">An issue is considered to have been triaged when labels have been assigned or an owner has been assigned.</span></span> <span data-ttu-id="c448f-153">Os membros da equipe de documentação do PowerShell são incentivados a revisar os problemas diariamente e fazer a triagem de novos problemas à medida que chegam.</span><span class="sxs-lookup"><span data-stu-id="c448f-153">PowerShell docs team members are encouraged to review the issues daily and triage new issues as they arrive.</span></span> <span data-ttu-id="c448f-154">A reunião semanal de triagem pode ser usada para discutir os novos problemas em mais detalhes, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c448f-154">The weekly triage meeting can then be used to discuss the new issues in more detail, as needed.</span></span>

### <a name="misplaced-product-feedback"></a><span data-ttu-id="c448f-155">Comentários incorretos sobre o produto</span><span class="sxs-lookup"><span data-stu-id="c448f-155">Misplaced product feedback</span></span>

- <span data-ttu-id="c448f-156">Insira um comentário para o cliente indicando que são comentários sobre o produto e forneça um link para o canal de comentários apropriado.</span><span class="sxs-lookup"><span data-stu-id="c448f-156">Enter a comment for the customer indicating it is product feedback and provide a link to the appropriate feedback channel.</span></span>
- <span data-ttu-id="c448f-157">Opcional: Copie o problema no local apropriado para comentários do produto, adicione um link ao item copiado e encerre o problema.</span><span class="sxs-lookup"><span data-stu-id="c448f-157">Optional: Copy the issue to the appropriate product feedback location, add a link to the copied item, and close the issue.</span></span> <span data-ttu-id="c448f-158">NÃO copie problemas para o UserVoice.</span><span class="sxs-lookup"><span data-stu-id="c448f-158">DO NOT copy issues to UserVoice.</span></span>

  | <span data-ttu-id="c448f-159">DocSet</span><span class="sxs-lookup"><span data-stu-id="c448f-159">DocSet</span></span>    | <span data-ttu-id="c448f-160">URL de comentários do produto</span><span class="sxs-lookup"><span data-stu-id="c448f-160">Product Feedback URL</span></span>                                           |
  | --------- | -------------------------------------------------------------- |
  | <span data-ttu-id="c448f-161">developer</span><span class="sxs-lookup"><span data-stu-id="c448f-161">developer</span></span> | `https://github.com/PowerShell/PowerShell/issues/new/choose`   |
  | <span data-ttu-id="c448f-162">dsc</span><span class="sxs-lookup"><span data-stu-id="c448f-162">dsc</span></span>       | `https://windowsserver.uservoice.com/forums/301869-powershell` |
  | <span data-ttu-id="c448f-163">gallery</span><span class="sxs-lookup"><span data-stu-id="c448f-163">gallery</span></span>   | `https://github.com/powershell/powershellgallery/issues/new`   |
  | <span data-ttu-id="c448f-164">jea</span><span class="sxs-lookup"><span data-stu-id="c448f-164">jea</span></span>       | `https://github.com/powershell/jea/issues/new`                 |
  | <span data-ttu-id="c448f-165">reference</span><span class="sxs-lookup"><span data-stu-id="c448f-165">reference</span></span> | `https://github.com/PowerShell/PowerShell/issues/new/choose`   |
  | <span data-ttu-id="c448f-166">wmf</span><span class="sxs-lookup"><span data-stu-id="c448f-166">wmf</span></span>       | `https://windowsserver.uservoice.com/forums/301869-powershell` |

### <a name="support-requests"></a><span data-ttu-id="c448f-167">Solicitações de suporte</span><span class="sxs-lookup"><span data-stu-id="c448f-167">Support requests</span></span>

- <span data-ttu-id="c448f-168">Se a pergunta de suporte for simples, responda-a educadamente e encerre o problema.</span><span class="sxs-lookup"><span data-stu-id="c448f-168">If the support question is simple, answer it politely and close the issue.</span></span>
- <span data-ttu-id="c448f-169">Se a pergunta for mais complicada ou se o emissor responder com mais perguntas, redirecione-as para fóruns e canais de suporte.</span><span class="sxs-lookup"><span data-stu-id="c448f-169">If the question is more complicated, or the submitter replies with more questions, redirect them to forums and support channels.</span></span> <span data-ttu-id="c448f-170">Texto sugerido para redirecionamento para fóruns:</span><span class="sxs-lookup"><span data-stu-id="c448f-170">Suggested text for redirecting to forums:</span></span>

  ```Markdown
  > This is not the right forum for these kinds of questions. Try posting your question in a
  > community support forum. For a list of community forums see:
  > https://docs.microsoft.com/powershell/scripting/community/community-support
  ```

### <a name="code-of-conduct-violations"></a><span data-ttu-id="c448f-171">Violações do código de conduta</span><span class="sxs-lookup"><span data-stu-id="c448f-171">Code of conduct violations</span></span>

- <span data-ttu-id="c448f-172">Edite o problema para remover qualquer conteúdo ofensivo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="c448f-172">Edit the issue to remove any offensive content, if necessary.</span></span>
- <span data-ttu-id="c448f-173">Insira um comentário indicando que o problema é spam, feche o problema e bloqueie-o para evitar mais comentários.</span><span class="sxs-lookup"><span data-stu-id="c448f-173">Enter a comment indicating the issue is spam, close the issue, and then lock it to prevent further comments.</span></span>
- <span data-ttu-id="c448f-174">Cada ocorrência disso deve ser discutida na triagem semanal para determinar a necessidade de mais ações (relatório no GitHub ou Jurídico da Microsoft).</span><span class="sxs-lookup"><span data-stu-id="c448f-174">Each occurrence of this should be discussed in the weekly triage to determine the need for further action (report to GitHub or Microsoft Legal).</span></span>
