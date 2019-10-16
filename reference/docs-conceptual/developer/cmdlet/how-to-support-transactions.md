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
# <a name="how-to-support-transactions"></a><span data-ttu-id="34998-102">Como dar suporte a transações</span><span class="sxs-lookup"><span data-stu-id="34998-102">How to Support Transactions</span></span>

<span data-ttu-id="34998-103">Este exemplo mostra os elementos de código básico que adicionam suporte para transações a um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="34998-103">This example shows the basic code elements that add support for transactions to a cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34998-104">Para obter mais informações sobre como o Windows PowerShell lida com transações, consulte [about Transactions][about_Transactions].</span><span class="sxs-lookup"><span data-stu-id="34998-104">For more information about how Windows PowerShell handles transactions, see [About Transactions][about_Transactions].</span></span>

## <a name="to-support-transactions"></a><span data-ttu-id="34998-105">Para dar suporte a transações</span><span class="sxs-lookup"><span data-stu-id="34998-105">To support transactions</span></span>

1. <span data-ttu-id="34998-106">Ao declarar o atributo cmdlet, especifique que o cmdlet oferece suporte a transações.</span><span class="sxs-lookup"><span data-stu-id="34998-106">When you declare the Cmdlet attribute, specify that the cmdlet supports transactions.</span></span>
   <span data-ttu-id="34998-107">Quando o cmdlet dá suporte a transações, o Windows PowerShell adiciona o parâmetro `UseTransaction` ao cmdlet quando ele é executado.</span><span class="sxs-lookup"><span data-stu-id="34998-107">When the cmdlet supports transactions, Windows PowerShell adds the `UseTransaction` parameter to the cmdlet when it is run.</span></span>

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. <span data-ttu-id="34998-108">Dentro de um dos métodos de processamento de entrada, adicione um bloco `if` para determinar se uma transação está disponível.</span><span class="sxs-lookup"><span data-stu-id="34998-108">Within one of the input processing methods, add an `if` block to determine if a transaction is available.</span></span>
   <span data-ttu-id="34998-109">Se a instrução `if` for resolvida como `true`, as ações dentro dessa instrução poderão ser executadas dentro do contexto da transação atual.</span><span class="sxs-lookup"><span data-stu-id="34998-109">If the `if` statement resolves to `true`, the actions within this statement can be performed within the context of the current transaction.</span></span>

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="34998-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="34998-110">See Also</span></span>

<span data-ttu-id="34998-111">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="34998-111">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
