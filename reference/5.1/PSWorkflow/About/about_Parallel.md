---
description: Descreve a palavra-chave Parallel, que executa as atividades em um fluxo de trabalho em paralelo.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parallel
ms.openlocfilehash: 402e93672bbea4ec9b6bfda8d608f266f6c40a21
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195807"
---
# <a name="about-parallel"></a>Sobre paralelo

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve a palavra-chave Parallel, que executa as atividades em um fluxo de trabalho em paralelo.

## <a name="long-description"></a>DESCRIÇÃO LONGA

A palavra-chave Parallel executa atividades de fluxo de trabalho em paralelo. Essa palavra-chave é válida somente no fluxo de trabalho do Windows PowerShell.

### <a name="syntax"></a>SYNTAX

```
workflow <Verb-Noun>
{
     Parallel
     {
          [<Activity>]
          [<Activity>]
        ...
     }
 }
```

## <a name="detailed-description"></a>DESCRIÇÃO DETALHADA

Os comandos de um bloco de script Parallel podem ser executados simultaneamente. A ordem de execução não é determinada.

Por exemplo, o fluxo de trabalho a seguir contém um bloco de script Parallel que executa atividades que obtêm processos e serviços do computador. Como os comandos Get-Process e Get-Service são independentes um do outro, eles podem ser executados simultaneamente e em qualquer ordem.

```powershell
workflow Test-Workflow
{
    Parallel
    {
         Get-Process
         Get-Service
    }
}
```

A execução de comandos em paralelo é muito eficiente e reduz o tempo necessário para concluir um fluxo de trabalho significativamente.

Para executar comandos selecionados em um bloco de script paralelo em ordem sequencial, use a palavra-chave Sequence. Para obter mais informações, consulte about_Sequence.

Para executar um bloco de script paralelo em itens de uma coleção, use as palavras-chave ForEach ou ForEach-Parallel.

## <a name="see-also"></a>CONSULTE TAMBÉM

["Escrevendo um fluxo de trabalho de script"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574157(v=ws.11))

[about_ForEach](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[about_ForEach-paralelo](about_ForEach-Parallel.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Sequence](about_Sequence.md)

[about_Workflows](about_workflows.md)
