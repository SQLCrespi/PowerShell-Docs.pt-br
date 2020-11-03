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
# <a name="about-checkpoint-workflow"></a>Sobre Checkpoint-Workflow

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve a atividade de Checkpoint-Workflow, que usa um ponto de verificação em um fluxo de trabalho.

## <a name="long-description"></a>DESCRIÇÃO LONGA

A atividade Checkpoint-Workflow usa um ponto de verificação, que salva o estado e os dados no fluxo de trabalho. Se o fluxo de trabalho for suspenso ou interrompido, ele poderá ser retomado do ponto de verificação mais recente, em vez de ter que ser reiniciado.

A atividade de Checkpoint-Workflow é válida somente em um fluxo de trabalho.

### <a name="syntax"></a>SYNTAX

```
Workflow <Verb-Noun>
{
    Checkpoint-Workflow
}
```

A atividade de Checkpoint-Workflow não aceita nenhum parâmetro, incluindo parâmetros comuns e parâmetros comuns de fluxo de trabalho.

Você pode posicionar o ponto de verificação Checkpoint-Activity em qualquer lugar em um fluxo de trabalho após a instrução CmdletBinding ou param. No entanto, ao colocar pontos de verificação, considere o custo de desempenho de coletar os dados e gravá-los em disco no computador que está executando o fluxo de trabalho.

Certifique-se de que se o tempo necessário para executar novamente uma seção do fluxo de trabalho for interrompido, ele será maior do que o tempo necessário para gravar o estado do ponto de verificação e os dados no disco.

Considere pegar pontos de verificação após etapas críticas para que o fluxo de trabalho possa ser retomado em vez de reiniciado. Por exemplo, faça um ponto de verificação após comandos que não são idempotentes.

### <a name="about-checkpoints"></a>SOBRE PONTOS DE VERIFICAÇÃO

Um ponto de verificação é um instantâneo do estado atual do fluxo de trabalho, incluindo os valores atuais das variáveis e qualquer saída gerada até esse ponto, salvos no disco.

Se um fluxo de trabalho for interrompido, intencionalmente ou não intencionalmente, o fluxo de trabalho do Windows PowerShell usará automaticamente os dados no ponto de verificação mais recente para recuperar e retomar o fluxo de trabalho.

Quando você executa o fluxo de trabalho como uma tarefa, por exemplo, usando o parâmetro comum do Workflow AsJob, os pontos de verificação do fluxo de trabalhos são mantidos até que você exclua o trabalho, como usando o cmdlet Remove-Job.
Caso contrário, os pontos de verificação do fluxo de trabalho serão excluídos quando o fluxo de trabalho for concluído.

### <a name="other-checkpointing-techniques"></a>OUTRAS TÉCNICAS DE PONTO DE VERIFICAÇÃO

Além da atividade de Checkpoint-Workflow, o fluxo de trabalho do Windows PowerShell dá suporte a outras técnicas de ponto de verificação, incluindo as seguintes:

- Parâmetro comum de fluxo de trabalho PSPersist
- Parâmetros comuns da atividade PSPersist
- Variável PSPersistPreference (em um fluxo de trabalho)

Para obter mais informações sobre como adicionar um ponto de verificação a um fluxo de trabalho, consulte "como adicionar pontos de verificação a um fluxo de trabalho".

## <a name="examples"></a>EXEMPLOS

O fluxo de trabalho a seguir inclui uma chamada para a atividade de Checkpoint-Workflow depois de concluir uma função de execução longa e um script que compartilha dados.

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

## <a name="see-also"></a>CONSULTE TAMBÉM

[Escrevendo um Fluxo de Trabalho do Windows PowerShell](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
