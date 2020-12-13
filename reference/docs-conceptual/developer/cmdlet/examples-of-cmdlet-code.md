---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplos de código do cmdlet
description: Exemplos de código do cmdlet
ms.openlocfilehash: 91dd2019300504697ad9a7a0c155a04600d09c58
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652917"
---
# <a name="examples-of-cmdlet-code"></a>Exemplos de código do cmdlet

Esta seção contém exemplos de código de cmdlet que você pode usar para começar a escrever seus próprios cmdlets.

> [!IMPORTANT]
> Se você quiser obter instruções passo a passo para escrever cmdlets, consulte [tutoriais para escrever cmdlets](./tutorials-for-writing-cmdlets.md).

## <a name="in-this-section"></a>Nesta seção

[Como escrever um cmdlet simples](./how-to-write-a-simple-cmdlet.md) Este exemplo mostra a estrutura básica do código do cmdlet.

[Como declarar parâmetros de cmdlet](./how-to-declare-cmdlet-parameters.md) Este exemplo mostra como declarar os diferentes tipos de parâmetros.

[Como declarar conjuntos de parâmetros](./how-to-declare-parameter-sets.md) Este exemplo mostra como declarar conjuntos de parâmetros que podem alterar a ação que um cmdlet executa.

[Como validar a entrada de parâmetro](./how-to-validate-parameter-input.md) Estes exemplos mostram como validar a entrada de parâmetro.

[Como declarar parâmetros dinâmicos](./how-to-declare-dynamic-parameters.md) Este exemplo mostra como declarar um parâmetro que é adicionado no tempo de execução.

[Como invocar scripts dentro de um cmdlet](./how-to-invoke-scripts-within-a-cmdlet.md) Este exemplo mostra como invocar um script que é fornecido a um cmdlet.

[Como substituir métodos de processamento de entrada](./how-to-override-input-processing-methods.md) Esses exemplos mostram a estrutura básica usada para substituir os métodos BeginProcessing, ProcessRecord e endprocessor.

[Como dar suporte a chamadas de ShouldProcess](./how-to-request-confirmations.md) Este exemplo mostra como os métodos [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) devem ser chamados de dentro de um cmdlet.

[Como dar suporte a transações](./how-to-support-transactions.md) Este exemplo mostra como indicar que o cmdlet dá suporte a transações e como implementar a ação que é executada quando o cmdlet é usado em uma transação.

[Como dar suporte a trabalhos](./how-to-support-jobs.md) Este exemplo mostra como dar suporte a trabalhos quando você escreve cmdlets.

[Como invocar um cmdlet de dentro de um cmdlet](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md) Este exemplo mostra como invocar um cmdlet de dentro de outro cmdlet, que permite adicionar a funcionalidade do cmdlet invocado ao cmdlet que você está desenvolvendo.

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
