---
title: Como dar suporte a transações | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4732e38c-b1a0-4de7-b6de-75dbde850488
caps.latest.revision: 8
ms.openlocfilehash: c5eea216efd8048aee5768c78c0b48617670f091
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365535"
---
# <a name="how-to-support-transactions"></a>Como dar suporte a transações

Este exemplo mostra os elementos de código básico que adicionam suporte para transações a um cmdlet.

> [!IMPORTANT]
> Para obter mais informações sobre como o Windows PowerShell lida com transações, consulte [about Transactions][about_Transactions].

## <a name="to-support-transactions"></a>Para dar suporte a transações

1. Ao declarar o atributo cmdlet, especifique que o cmdlet oferece suporte a transações.
   Quando o cmdlet dá suporte a transações, o Windows PowerShell adiciona o parâmetro `UseTransaction` ao cmdlet quando ele é executado.

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. Dentro de um dos métodos de processamento de entrada, adicione um bloco `if` para determinar se uma transação está disponível.
   Se a instrução `if` for resolvida como `true`, as ações dentro dessa instrução poderão ser executadas dentro do contexto da transação atual.

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

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
