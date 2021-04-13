---
title: Como gerenciamos problemas
description: Este artigo explica como a equipe do PowerShell-Docs gerencia problemas.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: c6cb38bc37260b14e2a7c728879e2fa2a036133f
ms.sourcegitcommit: f6cc3752463b254f6ba7fc14c1e4532ad33f06bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2021
ms.locfileid: "107216906"
---
# <a name="how-we-manage-issues"></a><span data-ttu-id="d7119-103">Como gerenciamos problemas</span><span class="sxs-lookup"><span data-stu-id="d7119-103">How we manage issues</span></span>

<span data-ttu-id="d7119-104">Este artigo documenta como gerenciamos problemas no repositório do PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="d7119-104">This article documents how we manage issues in the PowerShell-Docs repo.</span></span> <span data-ttu-id="d7119-105">O artigo foi projetado para ser um auxílio de trabalho para membros da equipe do PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="d7119-105">This article is designed to be a job aid for members of the PowerShell-Docs team.</span></span> <span data-ttu-id="d7119-106">Ele é publicado aqui para fornecer transparência de processo para nossos colaboradores públicos.</span><span class="sxs-lookup"><span data-stu-id="d7119-106">It's published here to provide process transparency for our public contributors.</span></span>

## <a name="sources-of-issues"></a><span data-ttu-id="d7119-107">Fontes de problemas</span><span class="sxs-lookup"><span data-stu-id="d7119-107">Sources of issues</span></span>

- <span data-ttu-id="d7119-108">Colaboradores da Comunidade</span><span class="sxs-lookup"><span data-stu-id="d7119-108">Community contributors</span></span>
- <span data-ttu-id="d7119-109">Colaboradores internos</span><span class="sxs-lookup"><span data-stu-id="d7119-109">Internal contributors</span></span>
- <span data-ttu-id="d7119-110">Transcrições de comentários de canais de mídia social</span><span class="sxs-lookup"><span data-stu-id="d7119-110">Transcriptions of comments from social media channels</span></span>
- <span data-ttu-id="d7119-111">Comentários por meio do formulário de comentários do Docs</span><span class="sxs-lookup"><span data-stu-id="d7119-111">Feedback via the Docs feedback form</span></span>

## <a name="response-time-targets"></a><span data-ttu-id="d7119-112">Metas de tempo de resposta</span><span class="sxs-lookup"><span data-stu-id="d7119-112">Response time targets</span></span>

<span data-ttu-id="d7119-113">80% dos novos problemas são fechados dentro de 3 dias úteis.</span><span class="sxs-lookup"><span data-stu-id="d7119-113">80% of new issues are closed within 3 business days.</span></span>

- <span data-ttu-id="d7119-114">Triantigos-1 dias úteis</span><span class="sxs-lookup"><span data-stu-id="d7119-114">Triaged - 1 business days</span></span>
- <span data-ttu-id="d7119-115">Corrigir ou alterar-10 dias úteis</span><span class="sxs-lookup"><span data-stu-id="d7119-115">Fix or change - 10 business days</span></span>

### <a name="labeling--milestones"></a><span data-ttu-id="d7119-116">Rótulos & marcos</span><span class="sxs-lookup"><span data-stu-id="d7119-116">Labeling & Milestones</span></span>

#### <a name="label-types"></a><span data-ttu-id="d7119-117">Tipos de rótulo</span><span class="sxs-lookup"><span data-stu-id="d7119-117">Label Types</span></span>

|   <span data-ttu-id="d7119-118">Type</span><span class="sxs-lookup"><span data-stu-id="d7119-118">Type</span></span>   | <span data-ttu-id="d7119-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7119-119">Description</span></span>                                                         |
| -------- | ------------------------------------------------------------------- |
| <span data-ttu-id="d7119-120">Área</span><span class="sxs-lookup"><span data-stu-id="d7119-120">Area</span></span>     | <span data-ttu-id="d7119-121">Usado para indicar qual parte do PowerShell ou os documentos que o problema está discutindo.</span><span class="sxs-lookup"><span data-stu-id="d7119-121">Used to indicate what part of PowerShell or the docs that the issue is discussing.</span></span><br><span data-ttu-id="d7119-122">Útil para os proprietários de recursos encontrarem problemas para seus recursos.</span><span class="sxs-lookup"><span data-stu-id="d7119-122">Useful for feature owners to find issues for their feature.</span></span> |
| <span data-ttu-id="d7119-123">Problema</span><span class="sxs-lookup"><span data-stu-id="d7119-123">Issue</span></span>    | <span data-ttu-id="d7119-124">Indica o tipo de problema</span><span class="sxs-lookup"><span data-stu-id="d7119-124">Indicates the type of issue</span></span>                                         |
| <span data-ttu-id="d7119-125">Prioridade</span><span class="sxs-lookup"><span data-stu-id="d7119-125">Priority</span></span> | <span data-ttu-id="d7119-126">Indica a prioridade do problema.</span><span class="sxs-lookup"><span data-stu-id="d7119-126">Indicates the priority of the issue.</span></span> <span data-ttu-id="d7119-127">Intervalo de valores 0 (alto)-4 (baixo)</span><span class="sxs-lookup"><span data-stu-id="d7119-127">Value range 0 (high) -4 (low)</span></span>  |
| <span data-ttu-id="d7119-128">Status</span><span class="sxs-lookup"><span data-stu-id="d7119-128">Status</span></span>   | <span data-ttu-id="d7119-129">Indica o status do item de trabalho ou por que ele foi fechado</span><span class="sxs-lookup"><span data-stu-id="d7119-129">Indicates the status of the work item or why it was closed</span></span>          |
| <span data-ttu-id="d7119-130">Marca</span><span class="sxs-lookup"><span data-stu-id="d7119-130">Tag</span></span>      | <span data-ttu-id="d7119-131">Rótulos usados para para classificação adicional</span><span class="sxs-lookup"><span data-stu-id="d7119-131">Labels used to for additional classification</span></span>                        |
| <span data-ttu-id="d7119-132">Aguardando</span><span class="sxs-lookup"><span data-stu-id="d7119-132">Waiting</span></span>  | <span data-ttu-id="d7119-133">Indica que estamos aguardando alguém ou algum outro evento</span><span class="sxs-lookup"><span data-stu-id="d7119-133">Indicates that we're waiting on someone or some other event</span></span>         |

#### <a name="milestones"></a><span data-ttu-id="d7119-134">Marcos</span><span class="sxs-lookup"><span data-stu-id="d7119-134">Milestones</span></span>

<span data-ttu-id="d7119-135">Os problemas e solicitações de pull devem ser marcados com o marco apropriado.</span><span class="sxs-lookup"><span data-stu-id="d7119-135">Issues and PRs should be tagged with the appropriate milestone.</span></span> <span data-ttu-id="d7119-136">Se o problema não se aplicar a uma versão específica, nenhuma etapa será usada.</span><span class="sxs-lookup"><span data-stu-id="d7119-136">If the issue doesn't apply to a specific version, then no milestone is used.</span></span> <span data-ttu-id="d7119-137">PRs e problemas relacionados a alterações que ainda precisam ser mescladas na base de código do PowerShell devem ser atribuídos à etapa **futura** .</span><span class="sxs-lookup"><span data-stu-id="d7119-137">PRs and related issues for changes that have yet to be merged into the PowerShell code base should be assigned to the **Future** milestone.</span></span> <span data-ttu-id="d7119-138">Após a alteração do código ter sido mesclada, altere o marco para a versão apropriada.</span><span class="sxs-lookup"><span data-stu-id="d7119-138">After the code change has been merged, change the milestone to the appropriate version.</span></span>

|    <span data-ttu-id="d7119-139">Marco</span><span class="sxs-lookup"><span data-stu-id="d7119-139">Milestone</span></span>     |                    <span data-ttu-id="d7119-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7119-140">Description</span></span>                     |
| ---------------- | -------------------------------------------------- |
| <span data-ttu-id="d7119-141">7.0.0</span><span class="sxs-lookup"><span data-stu-id="d7119-141">7.0.0</span></span>            | <span data-ttu-id="d7119-142">Itens de trabalho relacionados ao PowerShell 7.0</span><span class="sxs-lookup"><span data-stu-id="d7119-142">Work items related to PowerShell 7.0</span></span>               |
| <span data-ttu-id="d7119-143">7.1.0</span><span class="sxs-lookup"><span data-stu-id="d7119-143">7.1.0</span></span>            | <span data-ttu-id="d7119-144">Itens de trabalho relacionados ao PowerShell 7.1</span><span class="sxs-lookup"><span data-stu-id="d7119-144">Work items related to PowerShell 7.1</span></span>               |
| <span data-ttu-id="d7119-145">7.2.0</span><span class="sxs-lookup"><span data-stu-id="d7119-145">7.2.0</span></span>            | <span data-ttu-id="d7119-146">Itens de trabalho relacionados ao PowerShell 7,2</span><span class="sxs-lookup"><span data-stu-id="d7119-146">Work items related to PowerShell 7.2</span></span>               |
| <span data-ttu-id="d7119-147">Futuro</span><span class="sxs-lookup"><span data-stu-id="d7119-147">Future</span></span>           | <span data-ttu-id="d7119-148">Itens de trabalho relacionados a uma versão futura do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7119-148">Work items a future version of PowerShell</span></span>          |

## <a name="triage-process"></a><span data-ttu-id="d7119-149">Processo de triagem</span><span class="sxs-lookup"><span data-stu-id="d7119-149">Triage process</span></span>

<span data-ttu-id="d7119-150">Os membros da equipe do PowerShell revisam os problemas diários e fazem triagem de novos problemas à medida que chegam.</span><span class="sxs-lookup"><span data-stu-id="d7119-150">PowerShell docs team members review the issues daily and triage new issues as they arrive.</span></span> <span data-ttu-id="d7119-151">A equipe atende semanalmente para discutir problemas que precisam de triagem ou permanecem indefinidos.</span><span class="sxs-lookup"><span data-stu-id="d7119-151">The team meets weekly to discuss issues that need triage or remain unresolved.</span></span>

### <a name="misplaced-product-feedback"></a><span data-ttu-id="d7119-152">Comentários incorretos sobre o produto</span><span class="sxs-lookup"><span data-stu-id="d7119-152">Misplaced product feedback</span></span>

- <span data-ttu-id="d7119-153">Insira um comentário redirecionando o cliente para o canal de comentários correto.</span><span class="sxs-lookup"><span data-stu-id="d7119-153">Enter a comment redirecting the customer to the correct feedback channel.</span></span>
- <span data-ttu-id="d7119-154">Opcional: Copie o problema no local apropriado para comentários do produto, adicione um link ao item copiado e encerre o problema.</span><span class="sxs-lookup"><span data-stu-id="d7119-154">Optional: Copy the issue to the appropriate product feedback location, add a link to the copied item, and close the issue.</span></span> <span data-ttu-id="d7119-155">NÃO copie problemas para o UserVoice.</span><span class="sxs-lookup"><span data-stu-id="d7119-155">DO NOT copy issues to UserVoice.</span></span>

  <span data-ttu-id="d7119-156">O local padrão para problemas do PowerShell é [https://github.com/PowerShell/PowerShell/issues/new/choose](https://github.com/PowerShell/PowerShell/issues/new/choose) .</span><span class="sxs-lookup"><span data-stu-id="d7119-156">The default location for PowerShell issues is [https://github.com/PowerShell/PowerShell/issues/new/choose](https://github.com/PowerShell/PowerShell/issues/new/choose).</span></span>

  <span data-ttu-id="d7119-157">As seguintes áreas de assunto têm locais diferentes para problemas:</span><span class="sxs-lookup"><span data-stu-id="d7119-157">The following subject areas have different locations for issues:</span></span>

  | <span data-ttu-id="d7119-158">Entidades</span><span class="sxs-lookup"><span data-stu-id="d7119-158">Subjects</span></span> |                                                     <span data-ttu-id="d7119-159">URL de comentários do produto</span><span class="sxs-lookup"><span data-stu-id="d7119-159">Product Feedback URL</span></span>                                                     |
  | -------- | ---------------------------------------------------------------------------------------------------------------------------- |
  | <span data-ttu-id="d7119-160">dsc</span><span class="sxs-lookup"><span data-stu-id="d7119-160">dsc</span></span>      | [https://windowsserver.uservoice.com/forums/301869-powershell](https://windowsserver.uservoice.com/forums/301869-powershell) |
  | <span data-ttu-id="d7119-161">gallery</span><span class="sxs-lookup"><span data-stu-id="d7119-161">gallery</span></span>  | [https://github.com/powershell/powershellgallery/issues/new](https://github.com/powershell/powershellgallery/issues/new)     |
  | <span data-ttu-id="d7119-162">wmf</span><span class="sxs-lookup"><span data-stu-id="d7119-162">wmf</span></span>      | [https://windowsserver.uservoice.com/forums/301869-powershell](https://windowsserver.uservoice.com/forums/301869-powershell) |

### <a name="support-requests"></a><span data-ttu-id="d7119-163">Solicitações de suporte</span><span class="sxs-lookup"><span data-stu-id="d7119-163">Support requests</span></span>

- <span data-ttu-id="d7119-164">Se a pergunta de suporte for simples, responda-a educadamente e encerre o problema.</span><span class="sxs-lookup"><span data-stu-id="d7119-164">If the support question is simple, answer it politely and close the issue.</span></span>
- <span data-ttu-id="d7119-165">Se a pergunta for mais complicada ou se o emissor responder com mais perguntas, redirecione-as para fóruns e canais de suporte.</span><span class="sxs-lookup"><span data-stu-id="d7119-165">If the question is more complicated, or the submitter replies with more questions, redirect them to forums and support channels.</span></span> <span data-ttu-id="d7119-166">Texto sugerido para redirecionamento para fóruns:</span><span class="sxs-lookup"><span data-stu-id="d7119-166">Suggested text for redirecting to forums:</span></span>

  ```Markdown
  > This is not the right forum for these kinds of questions. Try posting your question in a
  > community support forum. For a list of community forums see:
  > https://docs.microsoft.com/powershell/scripting/community/community-support
  ```

### <a name="code-of-conduct-violations"></a><span data-ttu-id="d7119-167">Violações do código de conduta</span><span class="sxs-lookup"><span data-stu-id="d7119-167">Code of conduct violations</span></span>

- <span data-ttu-id="d7119-168">Edite o problema para remover qualquer conteúdo ofensivo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="d7119-168">Edit the issue to remove any offensive content, if necessary.</span></span>
- <span data-ttu-id="d7119-169">Insira um comentário indicando que o problema é spam, feche o problema e bloqueie-o para evitar mais comentários.</span><span class="sxs-lookup"><span data-stu-id="d7119-169">Enter a comment indicating the issue is spam, close the issue, and then lock it to prevent further comments.</span></span>
- <span data-ttu-id="d7119-170">Cada violação deve ser discutida na triagem semanal para determinar a necessidade de uma ação adicional (relatório para GitHub ou legal da Microsoft).</span><span class="sxs-lookup"><span data-stu-id="d7119-170">Each violation should be discussed in the weekly triage to determine the need for further action (report to GitHub or Microsoft Legal).</span></span>
