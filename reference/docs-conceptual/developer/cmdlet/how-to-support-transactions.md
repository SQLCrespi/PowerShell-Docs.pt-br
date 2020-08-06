---
title: Como dar suporte a transações | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6fda27394091195b589afef5ee53c6d3bec4efc0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786604"
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
