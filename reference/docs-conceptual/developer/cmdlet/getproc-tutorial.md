---
ms.date: 09/13/2016
ms.topic: reference
title: Tutorial de GetProc
description: Tutorial de GetProc
ms.openlocfilehash: 9379e791dd5361fcf5b79061bf0a601ebeb84f42
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652781"
---
# <a name="getproc-tutorial"></a>Tutorial de GetProc

Esta seção fornece um tutorial para criar um cmdlet Get-Proc que é muito semelhante ao cmdlet [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) fornecido pelo Windows PowerShell. Este tutorial fornece fragmentos de código que ilustram como os cmdlets são implementados e uma explicação do código.

## <a name="topics-in-this-tutorial"></a>Tópicos deste tutorial

Os tópicos deste tutorial foram criados para serem lidos sequencialmente, com cada tópico sobre o que foi discutido no tópico anterior.

[Criando um cmdlet sem parâmetros](./creating-a-cmdlet-without-parameters.md) Esta seção descreve como criar um cmdlet que recupera informações do computador local sem o uso de parâmetros e, em seguida, grava as informações no pipeline.

[Adicionando parâmetros que processam Command-Line entrada](./adding-parameters-that-process-command-line-input.md) Esta seção descreve como adicionar um parâmetro ao cmdlet Get-Proc para que o cmdlet possa processar a entrada com base em objetos explícitos passados para o cmdlet. A implementação descrita aqui recupera processos com base em seu nome e, em seguida, grava as informações no pipeline.

[Adicionando parâmetros que processam a entrada do pipeline](./adding-parameters-that-process-pipeline-input.md) Esta seção descreve como adicionar um parâmetro ao cmdlet Get-Proc para que o cmdlet possa processar objetos passados para ele por meio do pipeline. O cmdlet de implementação descrito aqui recupera processos com base em objetos passados para o cmdlet e, em seguida, grava as informações no pipeline.

[Adicionando relatórios de erros não finalizados ao seu cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) Esta seção descreve como adicionar relatórios de erros não finalizados a um cmdlet. A implementação descrita aqui detecta erros de não encerramento que ocorrem durante o processamento de entrada e grava um registro de erro no fluxo de erros.

## <a name="see-also"></a>Consulte Também

[Criar um cmdlet sem parâmetros](./creating-a-cmdlet-without-parameters.md)

[Adicionando parâmetros que processam Command-Line entrada](./adding-parameters-that-process-command-line-input.md)

[Adicionar parâmetros que processam a entrada de pipeline](./adding-parameters-that-process-pipeline-input.md)

[Adicionando relatórios de erros não finalizados ao seu cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
