---
description: Descreve a atividade de Checkpoint-Workflow, que usa um ponto de verificação em um fluxo de trabalho.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_checkpoint-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Fluxo de trabalho about_Checkpoint
ms.openlocfilehash: 223deb07ff6ed387cf04736116ea0ce3f998bb59
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195812"
---
# <a name="about-checkpoint-workflow"></a><span data-ttu-id="9e94e-104">Sobre Checkpoint-Workflow</span><span class="sxs-lookup"><span data-stu-id="9e94e-104">About Checkpoint-Workflow</span></span>

## <a name="short-description"></a><span data-ttu-id="9e94e-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="9e94e-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="9e94e-106">Descreve a atividade de Checkpoint-Workflow, que usa um ponto de verificação em um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9e94e-106">Describes the Checkpoint-Workflow activity, which takes a checkpoint in a workflow.</span></span>

## <a name="long-description"></a><span data-ttu-id="9e94e-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="9e94e-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="9e94e-108">A atividade Checkpoint-Workflow usa um ponto de verificação, que salva o estado e os dados no fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9e94e-108">The Checkpoint-Workflow activity takes a checkpoint, which saves state and data in the workflow.</span></span> <span data-ttu-id="9e94e-109">Se o fluxo de trabalho for suspenso ou interrompido, ele poderá ser retomado do ponto de verificação mais recente, em vez de ter que ser reiniciado.</span><span class="sxs-lookup"><span data-stu-id="9e94e-109">If the workflow is suspended or interrupted, it can be resumed from the most recent checkpoint, rather than having to be restarted.</span></span>

<span data-ttu-id="9e94e-110">A atividade de Checkpoint-Workflow é válida somente em um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9e94e-110">The Checkpoint-Workflow activity is valid only in a workflow.</span></span>

### <a name="syntax"></a><span data-ttu-id="9e94e-111">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9e94e-111">SYNTAX</span></span>

```
Workflow <Verb-Noun>
{
    Checkpoint-Workflow
}
```

<span data-ttu-id="9e94e-112">A atividade de Checkpoint-Workflow não aceita nenhum parâmetro, incluindo parâmetros comuns e parâmetros comuns de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9e94e-112">The Checkpoint-Workflow activity does not accept any parameters, including common parameters and workflow common parameters.</span></span>

<span data-ttu-id="9e94e-113">Você pode posicionar o ponto de verificação Checkpoint-Activity em qualquer lugar em um fluxo de trabalho após a instrução CmdletBinding ou param.</span><span class="sxs-lookup"><span data-stu-id="9e94e-113">You can place the Checkpoint-Activity checkpoint anywhere in a workflow after the CmdletBinding or Param statement.</span></span> <span data-ttu-id="9e94e-114">No entanto, ao colocar pontos de verificação, considere o custo de desempenho de coletar os dados e gravá-los em disco no computador que está executando o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9e94e-114">However, when placing checkpoints, consider the performance cost of collecting the data and writing it to disk on the computer that is running the workflow.</span></span>

<span data-ttu-id="9e94e-115">Certifique-se de que se o tempo necessário para executar novamente uma seção do fluxo de trabalho for interrompido, ele será maior do que o tempo necessário para gravar o estado do ponto de verificação e os dados no disco.</span><span class="sxs-lookup"><span data-stu-id="9e94e-115">Be sure that the time it takes to rerun a section of the workflow if it is interrupted is greater than the time it takes to write the checkpoint state and data to disk.</span></span>

<span data-ttu-id="9e94e-116">Considere pegar pontos de verificação após etapas críticas para que o fluxo de trabalho possa ser retomado em vez de reiniciado.</span><span class="sxs-lookup"><span data-stu-id="9e94e-116">Consider taking checkpoints after critical steps so the workflow can be resumed rather than restarted.</span></span> <span data-ttu-id="9e94e-117">Por exemplo, faça um ponto de verificação após comandos que não são idempotentes.</span><span class="sxs-lookup"><span data-stu-id="9e94e-117">For example, take a checkpoint after commands that are not idempotent.</span></span>

### <a name="about-checkpoints"></a><span data-ttu-id="9e94e-118">SOBRE PONTOS DE VERIFICAÇÃO</span><span class="sxs-lookup"><span data-stu-id="9e94e-118">ABOUT CHECKPOINTS</span></span>

<span data-ttu-id="9e94e-119">Um ponto de verificação é um instantâneo do estado atual do fluxo de trabalho, incluindo os valores atuais das variáveis e qualquer saída gerada até esse ponto, salvos no disco.</span><span class="sxs-lookup"><span data-stu-id="9e94e-119">A checkpoint is a snapshot of the current state of the workflow, including the current values of variables, and any output generated up to that point, and it saves it to disk.</span></span>

<span data-ttu-id="9e94e-120">Se um fluxo de trabalho for interrompido, intencionalmente ou não intencionalmente, o fluxo de trabalho do Windows PowerShell usará automaticamente os dados no ponto de verificação mais recente para recuperar e retomar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9e94e-120">If a workflow is interrupted, intentionally or unintentionally, Windows PowerShell Workflow automatically uses the data in newest checkpoint to recover and resume the workflow.</span></span>

<span data-ttu-id="9e94e-121">Quando você executa o fluxo de trabalho como uma tarefa, por exemplo, usando o parâmetro comum do Workflow AsJob, os pontos de verificação do fluxo de trabalhos são mantidos até que você exclua o trabalho, como usando o cmdlet Remove-Job.</span><span class="sxs-lookup"><span data-stu-id="9e94e-121">When you run the workflow as a job, such as by using the AsJob workflow common parameter, the workflow checkpoints are retained until you delete the job, such as by using the Remove-Job cmdlet.</span></span>
<span data-ttu-id="9e94e-122">Caso contrário, os pontos de verificação do fluxo de trabalho serão excluídos quando o fluxo de trabalho for concluído.</span><span class="sxs-lookup"><span data-stu-id="9e94e-122">Otherwise, workflow checkpoints are deleted when the workflow completes.</span></span>

### <a name="other-checkpointing-techniques"></a><span data-ttu-id="9e94e-123">OUTRAS TÉCNICAS DE PONTO DE VERIFICAÇÃO</span><span class="sxs-lookup"><span data-stu-id="9e94e-123">OTHER CHECKPOINTING TECHNIQUES</span></span>

<span data-ttu-id="9e94e-124">Além da atividade de Checkpoint-Workflow, o fluxo de trabalho do Windows PowerShell dá suporte a outras técnicas de ponto de verificação, incluindo as seguintes:</span><span class="sxs-lookup"><span data-stu-id="9e94e-124">In addition to the Checkpoint-Workflow activity, Windows PowerShell Workflow supports other checkpointing techniques, including the following:</span></span>

- <span data-ttu-id="9e94e-125">Parâmetro comum de fluxo de trabalho PSPersist</span><span class="sxs-lookup"><span data-stu-id="9e94e-125">PSPersist workflow common parameter</span></span>
- <span data-ttu-id="9e94e-126">Parâmetros comuns da atividade PSPersist</span><span class="sxs-lookup"><span data-stu-id="9e94e-126">PSPersist activity common parameter</span></span>
- <span data-ttu-id="9e94e-127">Variável PSPersistPreference (em um fluxo de trabalho)</span><span class="sxs-lookup"><span data-stu-id="9e94e-127">PSPersistPreference variable (in a workflow)</span></span>

<span data-ttu-id="9e94e-128">Para obter mais informações sobre como adicionar um ponto de verificação a um fluxo de trabalho, consulte "como adicionar pontos de verificação a um fluxo de trabalho".</span><span class="sxs-lookup"><span data-stu-id="9e94e-128">For more information about adding a checkpoint to a workflow, see "How to Add Checkpoints to a Workflow."</span></span>

## <a name="examples"></a><span data-ttu-id="9e94e-129">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9e94e-129">EXAMPLES</span></span>

<span data-ttu-id="9e94e-130">O fluxo de trabalho a seguir inclui uma chamada para a atividade de Checkpoint-Workflow depois de concluir uma função de execução longa e um script que compartilha dados.</span><span class="sxs-lookup"><span data-stu-id="9e94e-130">The following workflow includes a call to the Checkpoint-Workflow activity after completing a long-running function and a script that share data.</span></span>

```powershell
Workflow Test-Workflow
{
    $a = Invoke-LongRunningFunction
    InlineScript { \\Server\Share\Get-DataPacks.ps1 $Using:a}
    Checkpoint-Workflow

    Invoke-LongRunningFunction
    {
        ...
    }
}
```

## <a name="see-also"></a><span data-ttu-id="9e94e-131">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="9e94e-131">SEE ALSO</span></span>

[<span data-ttu-id="9e94e-132">Escrevendo um Fluxo de Trabalho do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e94e-132">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
