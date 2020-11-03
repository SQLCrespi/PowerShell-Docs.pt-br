---
description: Descreve a `InlineScript` atividade, que executa comandos do PowerShell em um fluxo de trabalho.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_inlinescript?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_InlineScript
ms.openlocfilehash: 2eaeb02c6441865551b586e27a39c4000826752b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195810"
---
# <a name="about-inlinescript"></a><span data-ttu-id="16355-104">Sobre o InlineScript</span><span class="sxs-lookup"><span data-stu-id="16355-104">About InlineScript</span></span>

## <a name="short-description"></a><span data-ttu-id="16355-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="16355-105">Short description</span></span>

<span data-ttu-id="16355-106">Descreve a `InlineScript` atividade, que executa comandos do PowerShell em um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="16355-106">Describes the `InlineScript` activity, that runs PowerShell commands in a workflow.</span></span>

## <a name="long-description"></a><span data-ttu-id="16355-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="16355-107">Long description</span></span>

<span data-ttu-id="16355-108">A `InlineScript` atividade executa comandos em um fluxo de trabalho de sessão do PowerShell compartilhado.</span><span class="sxs-lookup"><span data-stu-id="16355-108">The `InlineScript` activity runs commands in a shared PowerShell session's workflow.</span></span> <span data-ttu-id="16355-109">`InlineScript` Só é válido em fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="16355-109">`InlineScript` is only valid in workflows.</span></span>

## <a name="syntax"></a><span data-ttu-id="16355-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="16355-110">Syntax</span></span>

```
InlineScript {<script block>} <ActivityCommonParameters>
```

## <a name="detailed-description"></a><span data-ttu-id="16355-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="16355-111">Detailed description</span></span>

<span data-ttu-id="16355-112">A `InlineScript` atividade executa comandos em uma sessão do PowerShell compartilhada.</span><span class="sxs-lookup"><span data-stu-id="16355-112">The `InlineScript` activity runs commands in a shared PowerShell session.</span></span> <span data-ttu-id="16355-113">Você pode incluí-lo em um fluxo de trabalho para executar comandos que compartilham dados e comandos que, de outra forma, não são válidos em um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="16355-113">You can include it in a workflow to run commands that share data and commands that aren't otherwise valid in a workflow.</span></span>

<span data-ttu-id="16355-114">O `InlineScript` bloco de script pode incluir todos os comandos e expressões do PowerShell válidos.</span><span class="sxs-lookup"><span data-stu-id="16355-114">The `InlineScript` script block can include all valid PowerShell commands and expressions.</span></span> <span data-ttu-id="16355-115">Como os comandos e as expressões em um `InlineScript` bloco de script são executados na mesma sessão, eles compartilham todos os Estados e dados, incluindo os módulos importados e os valores das variáveis.</span><span class="sxs-lookup"><span data-stu-id="16355-115">Because the commands and expressions in an `InlineScript` script block run in the same session, they share all state and data, including imported modules and the values of variables.</span></span>

<span data-ttu-id="16355-116">Você pode colocar uma `InlineScript` atividade em qualquer lugar em um fluxo de trabalho ou em um fluxo de trabalho aninhado, incluindo dentro de um loop ou instrução de controle ou um bloco de script paralelo ou de sequência.</span><span class="sxs-lookup"><span data-stu-id="16355-116">You can place an `InlineScript` activity anywhere in a workflow or nested workflow, including inside a loop or control statement or a Parallel or Sequence script block.</span></span>

<span data-ttu-id="16355-117">A `InlineScript` atividade tem os parâmetros comuns da atividade, incluindo **PSPersist** .</span><span class="sxs-lookup"><span data-stu-id="16355-117">The `InlineScript` activity has the activity common parameters, including **PSPersist** .</span></span> <span data-ttu-id="16355-118">No entanto, os comandos e expressões em um `InlineScript` bloco de script não têm os recursos de fluxo de trabalho, como ponto de verificação, persistência e parâmetros comuns de fluxo de trabalho ou atividade.</span><span class="sxs-lookup"><span data-stu-id="16355-118">However, the commands and expressions in an `InlineScript` script block don't have the workflow features such as checkpointing, or persistence, and workflow or activity common parameters.</span></span> <span data-ttu-id="16355-119">Para obter mais informações, consulte [about_ActivityCommonParameters](about_ActivityCommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="16355-119">For more information, see [about_ActivityCommonParameters](about_ActivityCommonParameters.md).</span></span>

## <a name="inlinescript-variables"></a><span data-ttu-id="16355-120">Variáveis InlineScript</span><span class="sxs-lookup"><span data-stu-id="16355-120">InlineScript Variables</span></span>

<span data-ttu-id="16355-121">Por padrão, as variáveis definidas em um fluxo de trabalho não são visíveis para os comandos no `InlineScript` bloco de script.</span><span class="sxs-lookup"><span data-stu-id="16355-121">By default, the variables that are defined in a workflow aren't visible to the commands in the `InlineScript` script block.</span></span> <span data-ttu-id="16355-122">Para tornar as variáveis de fluxo de trabalho visíveis para o `InlineScript` , use o `$Using` modificador de escopo.</span><span class="sxs-lookup"><span data-stu-id="16355-122">To make workflow variables visible to the `InlineScript`, use the `$Using` scope modifier.</span></span> <span data-ttu-id="16355-123">O `$Using` modificador de escopo é necessário apenas uma vez para cada variável no `InlineScript` .</span><span class="sxs-lookup"><span data-stu-id="16355-123">The `$Using` scope modifier is required only once for each variable in the `InlineScript`.</span></span>

<span data-ttu-id="16355-124">Para obter mais informações sobre o `$Using` modificador de escopo, consulte [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="16355-124">For more information about the `$Using` scope modifier, see [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span></span>

<span data-ttu-id="16355-125">O exemplo a seguir mostra que o `$Using` modificador de escopo torna o valor da `$a` variável de fluxo de trabalho de nível superior disponível para os comandos no bloco de `InlineScript` script.</span><span class="sxs-lookup"><span data-stu-id="16355-125">The following example shows that the `$Using` scope modifier makes the value of the `$a` top-level workflow variable available to the commands in the `InlineScript` script block.</span></span>

```powershell
workflow Test-Workflow {
  $a = 3

  ## Without $Using, the $a workflow variable isn't visible
  ## in inline script.
  InlineScript {"Inline A0 = $a"}

  ## $Using imports the variable and its current value.
  InlineScript {"Inline A1 = $Using:a"}
}

Test-Workflow
```

```output
Inline A0 =
Inline A1 = 3
```

## <a name="returning-variables-in-inlinescript"></a><span data-ttu-id="16355-126">Retornando variáveis em InlineScript</span><span class="sxs-lookup"><span data-stu-id="16355-126">Returning variables in InlineScript</span></span>

<span data-ttu-id="16355-127">`InlineScript` os comandos podem alterar o valor da variável que foi importada do escopo do fluxo de trabalho, mas as alterações não são visíveis no escopo do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="16355-127">`InlineScript` commands can change the value of the variable that was imported from workflow scope, but the changes aren't visible in workflow scope.</span></span> <span data-ttu-id="16355-128">Para torná-las visíveis, retorne o valor alterado para o escopo do fluxo de trabalho, conforme exibido no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="16355-128">To make them visible, return the changed value to the workflow scope, as shown in the following example.</span></span>

```powershell
workflow Test-Workflow {
  $a = 3

  ##  Changes to the InlineScript variable value don't
  ##  change the workflow variable.
  InlineScript {
    $a = $Using:a+1;
    "Inline A = $a"
  }
  "Workflow A = $a"

  ##  To change the variable in workflow scope, return the
  ##  new value.
  $a = InlineScript {$b = $Using:a+1; $b}
  "Workflow New A = $a"
}

Test-Workflow
```

```output
Inline A = 4
Workflow A = 3
Workflow New A = 4
```

> [!NOTE]
> <span data-ttu-id="16355-129">Uma instrução com o `$Using` modificador de escopo deve aparecer antes de qualquer uso da variável no `InlineScript` bloco de script.</span><span class="sxs-lookup"><span data-stu-id="16355-129">A statement with the `$Using` scope modifier should appear before any use of the variable in the `InlineScript` script block.</span></span>

## <a name="running-in-process"></a><span data-ttu-id="16355-130">Executando em processo</span><span class="sxs-lookup"><span data-stu-id="16355-130">Running in-process</span></span>

<span data-ttu-id="16355-131">Para melhorar a confiabilidade, os comandos no `InlineScript` bloco de script são executados em seu próprio processo, separados do processo no qual o fluxo de trabalho é executado e, em seguida, retornam a saída para o processo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="16355-131">To improve reliability, the commands in the `InlineScript` script block run in their own process, separate from the process in which the workflow runs, and then return their output to the workflow process.</span></span>

<span data-ttu-id="16355-132">Para direcionar o PowerShell para executar a `InlineScript` atividade no processo de fluxo de trabalho, remova o `InlineScript` valor da propriedade **OutOfProcessActivity** da configuração de sessão, como usando o `New-PSWorkflowExecutionOption` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="16355-132">To direct PowerShell to run the `InlineScript` activity in the workflow process, remove the `InlineScript` value from the **OutOfProcessActivity** property of the session configuration, such as by using the `New-PSWorkflowExecutionOption` cmdlet.</span></span>

### <a name="example"></a><span data-ttu-id="16355-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="16355-133">Example</span></span>

<span data-ttu-id="16355-134">O `InlineScript` no fluxo de trabalho a seguir inclui comandos que são válidos no PowerShell, mas não são válidos em fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="16355-134">The `InlineScript` in the following workflow includes commands that are valid in PowerShell but aren't valid in workflows.</span></span> <span data-ttu-id="16355-135">Por exemplo, o `New-Object` cmdlet com o parâmetro **ComObject** .</span><span class="sxs-lookup"><span data-stu-id="16355-135">For example, the `New-Object` cmdlet with the **ComObject** parameter.</span></span>

```powershell
workflow Test-Workflow
{
  $ie = InlineScript {
    $ie = New-Object -ComObject InternetExplorer.Application -Property @{navigate2="www.microsoft.com"}

    $ie.Visible = $true
  }

  $ie
}

Test-Workflow
```

## <a name="see-also"></a><span data-ttu-id="16355-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="16355-136">See also</span></span>

[<span data-ttu-id="16355-137">about_ActivityCommonParameters</span><span class="sxs-lookup"><span data-stu-id="16355-137">about_ActivityCommonParameters</span></span>](about_ActivityCommonParameters.md)

[<span data-ttu-id="16355-138">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="16355-138">about_Remote_Variables</span></span>](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)

[<span data-ttu-id="16355-139">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="16355-139">about_WorkflowCommonParameters</span></span>](about_WorkflowCommonParameters.md)

<span data-ttu-id="16355-140">Cmdlets [PSWorkflow](xref:PSWorkflow)</span><span class="sxs-lookup"><span data-stu-id="16355-140">[PSWorkflow](xref:PSWorkflow) cmdlets</span></span>

[<span data-ttu-id="16355-141">Guia de fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="16355-141">Workflows Guide</span></span>](/previous-versions/powershell/scripting/components/workflows-guide)

[<span data-ttu-id="16355-142">Escrevendo um Fluxo de Trabalho do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="16355-142">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
