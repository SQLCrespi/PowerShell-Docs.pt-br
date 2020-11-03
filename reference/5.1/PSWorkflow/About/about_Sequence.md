---
description: Descreve a `Sequence` palavra-chave que executa as atividades selecionadas sequencialmente.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_sequence?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Sequence
ms.openlocfilehash: a9dd4fb24274fe4e1478ca69c734b43a2f196792
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195805"
---
# <a name="about-sequence"></a>Sobre a sequência

## <a name="short-description"></a>Descrição breve

Descreve a `Sequence` palavra-chave que executa as atividades selecionadas sequencialmente.

## <a name="long-description"></a>Descrição longa

A `Sequence` palavra-chave executa as atividades de fluxo de trabalho selecionadas em sequência. As atividades de fluxo de trabalho são executadas na ordem em que aparecem e não são executadas simultaneamente. A `Sequence` palavra-chave só é válida em um fluxo de trabalho do PowerShell.

A `Sequence` palavra-chave é usada em um `Parallel` bloco de script para executar os comandos selecionados em sequência.

Como as atividades de fluxo de trabalho são executadas em sequência por padrão, a `Sequence` palavra-chave só é eficaz em um `Parallel` bloco de script. Se a `Sequence` palavra-chave não estiver incluída em um `Parallel` bloco de script, ela será válida, mas ineficaz.

O `Sequence` bloco de script permite executar mais comandos em paralelo, permitindo que você execute os comandos dependentes sequencialmente.

## <a name="syntax"></a>Syntax

### <a name="workflow-using-sequence"></a>Fluxo de trabalho usando sequência

```
workflow <Verb-Noun>
{
    Sequence
    {
        [<Activity>]
        [<Activity>]
        # ...
    }
}
```

### <a name="workflow-using-parallel-and-sequence"></a>Fluxo de trabalho usando Parallel e Sequence

```
workflow <Verb-Noun>
{
    Parallel
    {
        [<Activity>]
        Sequence
        {
            [<Activity>]
            [<Activity>]
            # ...
        }
    }
}
```

## <a name="detailed-description"></a>Descrição detalhada

Os comandos em um bloco de script `Parallel` podem ser executados simultaneamente. A ordem de execução não é determinada. Esse recurso melhora o desempenho de um fluxo de trabalho de script.

Você pode usar um `Sequence` bloco de script para executar as atividades selecionadas sequencialmente, embora as atividades apareçam em um `Parallel` bloco de script.

As atividades em um `Sequence` bloco de script são executadas consecutivamente na ordem em que estão listadas. Uma atividade em um `Sequence` bloco de script só inicia após a conclusão da atividade anterior.

No entanto, quando o `Sequence` bloco de script aparece em um `Parallel` bloco de script, a ordem na qual o `Sequence` bloco de script é executado não é determinada. Ele pode ser executado antes, depois ou simultaneamente com outras atividades no bloco de `Parallel` script.

Por exemplo, o fluxo de trabalho a seguir inclui um `Parallel` bloco de script que executa atividades que obtêm processos e serviços no computador. O `Parallel` bloco de script contém um `Sequence` bloco de script que obtém informações de um arquivo e usa as informações como entrada para um script.

Os `Get-Process` `Get-Service` comandos, e relacionados ao hotfix são independentes um do outro. Os comandos podem ser executados simultaneamente ou em qualquer ordem. No entanto, o comando que obtém as informações do hotfix deve ser executado antes do comando que o utiliza.

```powershell
workflow Test-Workflow
{
    Parallel
    {
    Get-Process
    Get-Service

    Sequence
    {
        $Hotfix = Get-Content 'D:\HotFixes\Required.txt'
        Foreach ($h in $Hotfix) {'D:\Scripts\Verify-Hotfix' -Hotfix $h}
        }
    }
}
```

## <a name="see-also"></a>Confira também

[about_ForEach](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[about_ForEach-paralelo](about_ForEach-Parallel.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Parallel](about_Parallel.md)

[about_Workflows](about_Workflows.md)

[Criar um fluxo de trabalho pelo uso de um script do Windows PowerShell](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)
