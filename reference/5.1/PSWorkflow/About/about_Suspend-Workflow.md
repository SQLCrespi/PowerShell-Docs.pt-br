---
description: Descreve a `Suspend-Workflow` atividade, que suspende o fluxo de trabalho no qual a atividade é exibida.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_suspend-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Fluxo de trabalho about_Suspend
ms.openlocfilehash: cbe5386ae5aa4bd863079fde240ddf2ce5384727
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195800"
---
# <a name="about-suspend-workflow"></a>Sobre Suspend-Workflow

## <a name="short-description"></a>Descrição breve

Descreve a `Suspend-Workflow` atividade, que suspende o fluxo de trabalho no qual a atividade é exibida.

## <a name="long-description"></a>Descrição longa

A `Suspend-Workflow` atividade interrompe temporariamente o processamento de fluxo de trabalho de dentro do fluxo de trabalho. Antes de suspender, o fluxo de trabalho do Windows PowerShell usa um ponto de verificação para que o estado e os dados do fluxo de trabalho sejam preservados e o fluxo de trabalho possa continuar do ponto de suspensão.

Para retomar o fluxo de trabalho, o usuário que executa o fluxo de trabalho usa o `Resume-Job` cmdlet. Não é possível retomar um fluxo de trabalho de dentro do fluxo de trabalho.

## <a name="syntax"></a>Syntax

```
workflow <Verb-Noun>
{
    Suspend-Workflow
}
```

## <a name="detailed-description"></a>Descrição detalhada

O `Suspend-Workflow` interrompe temporariamente o fluxo de trabalho e retorna um objeto de Job que representa o trabalho de fluxo de trabalho. Um objeto de trabalho é retornado mesmo que você não tenha executado o fluxo de trabalho como um Job. Por exemplo, como usando o parâmetro comum de fluxo de trabalho **AsJob** . O estado do trabalho é **suspenso** .

Você pode usar os cmdlets de trabalho do para gerenciar o trabalho suspenso de Workflow. Use o cmdlet para retomar o trabalho de workflow `Resume-Job` .

Quando você retomar o trabalho de fluxo de trabalho, o workflow será retomado no comando que segue a `Suspend-Workflow` atividade.

Por exemplo, o fluxo de trabalho a seguir inclui a `Suspend-Workflow` atividade.
Quando você executa o fluxo de trabalho, ele executa a `Get-Date` atividade, salva sua saída na `$a` variável e, em seguida, suspende o fluxo de trabalho e retorna um objeto de Job que representa o fluxo de trabalho suspenso. O tipo de trabalho é **PSWorkflowJob** .

Você pode usar os cmdlets de trabalho, como `Get-Job` , para gerenciar o trabalho de fluxo de trabalho.

```powershell
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

Test-Suspend
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Suspended  True         localhost Test-Suspend
```

## <a name="resuming-a-workflow-job"></a>Retomando um trabalho de fluxo

Use o cmdlet para retomar o trabalho de workflow `Resume-Job` . O cmdlet `Resume-Job` retorna o objeto de trabalho do fluxo de trabalho imediatamente, mesmo se ele ainda não puder ser retomado. Para aguardar o trabalho ser retomado, use o parâmetro **Wait** ou use o `Get-Job` cmdlet para obter o objeto de trabalho atual.

```powershell
Resume-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State    HasMoreData  Location  Command
--  ----  -------------  -----    -----------  --------  -------
8   Job8  PSWorkflowJob  Running  True         localhost Test-Suspend
```

```powershell
Get-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Completed  True         localhost Test-Suspend
```

## <a name="getting-the-output-of-a-workflow-job"></a>Obtendo a saída de um trabalho de fluxo

Para obter a saída de um trabalho de workflow, use o `Receive-Job` cmdlet. A saída mostra que o fluxo de trabalho foi retomado no comando que seguiu o `Suspend-Workflow` cmdlet. O valor da `$a` variável, que foi populada antes da suspensão, está disponível para o fluxo de trabalho quando ele é retomado.

```powershell
Get-Job -Name Job8 | Receive-Job
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 19
Milliseconds      : 823
Ticks             : 198230041
TotalDays         : 0.000229432917824074
TotalHours        : 0.00550639002777778
TotalMinutes      : 0.330383401666667
TotalSeconds      : 19.8230041
TotalMilliseconds : 19823.0041
PSComputerName    : localhost
```

## <a name="see-also"></a>Confira também

[about_Workflows](about_Workflows.md)

[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)

Cmdlets [PSWorkflow](xref:PSWorkflow)

[Guia de fluxos de trabalho](/previous-versions/powershell/scripting/components/workflows-guide)

[Escrevendo um Fluxo de Trabalho do Windows PowerShell](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
