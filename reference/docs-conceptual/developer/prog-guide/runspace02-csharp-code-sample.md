---
title: Exemplo de código do Runspace02 (C#) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1e58f035f20baa7443d9031499062a45beae01b9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87778448"
---
# <a name="runspace02-c-code-sample"></a><span data-ttu-id="1ed53-102">Exemplo de código Runspace02 (C#)</span><span class="sxs-lookup"><span data-stu-id="1ed53-102">Runspace02 (C#) Code Sample</span></span>

<span data-ttu-id="1ed53-103">Aqui está o código-fonte do C# para o exemplo Runspace02.</span><span class="sxs-lookup"><span data-stu-id="1ed53-103">Here is the C# source code for the Runspace02 sample.</span></span> <span data-ttu-id="1ed53-104">Este exemplo usa a classe [System. Management. Automation. Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) para executar o `Get-Process` cmdlet de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="1ed53-104">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute the `Get-Process` cmdlet synchronously.</span></span> <span data-ttu-id="1ed53-105">Windows Forms e a ligação de dados são usados para exibir os resultados em um controle DataGridView</span><span class="sxs-lookup"><span data-stu-id="1ed53-105">Windows Forms and data binding are then used to display the results in a DataGridView control</span></span>

## <a name="code-sample"></a><span data-ttu-id="1ed53-106">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="1ed53-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs" range="11-82":::

## <a name="see-also"></a><span data-ttu-id="1ed53-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1ed53-107">See Also</span></span>

[<span data-ttu-id="1ed53-108">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ed53-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
