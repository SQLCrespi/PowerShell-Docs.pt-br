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
# <a name="how-to-support-transactions"></a><span data-ttu-id="471ef-103">Como dar suporte a transações</span><span class="sxs-lookup"><span data-stu-id="471ef-103">How to Support Transactions</span></span>

<span data-ttu-id="471ef-104">Este exemplo mostra os elementos de código básico que adicionam suporte para transações a um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="471ef-104">This example shows the basic code elements that add support for transactions to a cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="471ef-105">Para obter mais informações sobre como o Windows PowerShell lida com transações, consulte [about Transactions][about_Transactions].</span><span class="sxs-lookup"><span data-stu-id="471ef-105">For more information about how Windows PowerShell handles transactions, see [About Transactions][about_Transactions].</span></span>

## <a name="to-support-transactions"></a><span data-ttu-id="471ef-106">Para dar suporte a transações</span><span class="sxs-lookup"><span data-stu-id="471ef-106">To support transactions</span></span>

1. <span data-ttu-id="471ef-107">Ao declarar o atributo cmdlet, especifique que o cmdlet oferece suporte a transações.</span><span class="sxs-lookup"><span data-stu-id="471ef-107">When you declare the Cmdlet attribute, specify that the cmdlet supports transactions.</span></span>
   <span data-ttu-id="471ef-108">Quando o cmdlet dá suporte a transações, o Windows PowerShell adiciona o `UseTransaction` parâmetro ao cmdlet quando ele é executado.</span><span class="sxs-lookup"><span data-stu-id="471ef-108">When the cmdlet supports transactions, Windows PowerShell adds the `UseTransaction` parameter to the cmdlet when it is run.</span></span>

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. <span data-ttu-id="471ef-109">Dentro de um dos métodos de processamento de entrada, adicione um `if` bloco para determinar se uma transação está disponível.</span><span class="sxs-lookup"><span data-stu-id="471ef-109">Within one of the input processing methods, add an `if` block to determine if a transaction is available.</span></span>
   <span data-ttu-id="471ef-110">Se a `if` instrução for resolvida como `true` , as ações dentro dessa instrução poderão ser executadas dentro do contexto da transação atual.</span><span class="sxs-lookup"><span data-stu-id="471ef-110">If the `if` statement resolves to `true`, the actions within this statement can be performed within the context of the current transaction.</span></span>

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="471ef-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="471ef-111">See Also</span></span>

[<span data-ttu-id="471ef-112">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="471ef-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
