---
ms.date: 09/13/2016
ms.topic: reference
title: Como dar suporte a transações
description: Como dar suporte a transações
ms.openlocfilehash: 5691c246830dab9f4808801c04353ebfb2c3e981
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666953"
---
# <a name="how-to-support-transactions"></a>Como dar suporte a transações

Este exemplo mostra os elementos de código básico que adicionam suporte para transações a um cmdlet.

> [!IMPORTANT]
> Para obter mais informações sobre como o Windows PowerShell lida com transações, consulte [about Transactions][about_Transactions].

## <a name="to-support-transactions"></a>Para dar suporte a transações

1. Ao declarar o atributo cmdlet, especifique que o cmdlet oferece suporte a transações.
   Quando o cmdlet dá suporte a transações, o Windows PowerShell adiciona o `UseTransaction` parâmetro ao cmdlet quando ele é executado.

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. Dentro de um dos métodos de processamento de entrada, adicione um `if` bloco para determinar se uma transação está disponível.
   Se a `if` instrução for resolvida como `true` , as ações dentro dessa instrução poderão ser executadas dentro do contexto da transação atual.

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
