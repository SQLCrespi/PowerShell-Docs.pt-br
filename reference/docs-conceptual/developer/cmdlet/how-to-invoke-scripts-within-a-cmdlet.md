---
title: Como invocar scripts em um cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc0bc6ce-48a5-4d9c-927e-636bca743e9f
caps.latest.revision: 9
ms.openlocfilehash: 7dcb8bc20ab56225764854f9dc6fdfd858ed7451
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364405"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a><span data-ttu-id="907cd-102">Como invocar scripts dentro de um cmdlet</span><span class="sxs-lookup"><span data-stu-id="907cd-102">How to Invoke Scripts Within a Cmdlet</span></span>

<span data-ttu-id="907cd-103">Este exemplo mostra como invocar um script que é fornecido a um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="907cd-103">This example shows how to invoke a script that is supplied to a cmdlet.</span></span> <span data-ttu-id="907cd-104">O script é executado pelo cmdlet e seus resultados são retornados para o cmdlet como uma coleção de objetos [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) .</span><span class="sxs-lookup"><span data-stu-id="907cd-104">The script is executed by the cmdlet, and its results are returned to the cmdlet as a collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects.</span></span>

## <a name="to-invoke-a-script-block"></a><span data-ttu-id="907cd-105">Para invocar um bloco de script</span><span class="sxs-lookup"><span data-stu-id="907cd-105">To invoke a script block</span></span>

1. <span data-ttu-id="907cd-106">O comando verifica se um bloco de script foi fornecido ao cmdlet.</span><span class="sxs-lookup"><span data-stu-id="907cd-106">The command verifies that a script block was supplied to the cmdlet.</span></span> <span data-ttu-id="907cd-107">Se um bloco de script foi fornecido, o comando invoca o bloco de script com seus parâmetros necessários.</span><span class="sxs-lookup"><span data-stu-id="907cd-107">If a script block was supplied, the command invokes the script block with its required parameters.</span></span>

    ```csharp
    if (script != null)
    {
      WriteDebug("Executing script block.");

      // Invoke the script block with the required arguments.
      Collection<PSObject> PSObjects =
                     script.Invoke(
                                   line,
                                   simpleMatch,
                                   caseSensitive
                                  );
    ```

2. <span data-ttu-id="907cd-108">Em seguida, o script faz a iteração pela coleção retornada de objetos [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) e executa as operações necessárias.</span><span class="sxs-lookup"><span data-stu-id="907cd-108">Then, the script iterates through the returned collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects and perform the necessary operations.</span></span>

    ```c
    foreach (PSObject psObject in psObjects)
    {
      if (LanguagePrimitives.IsTrue(psObject))
      {
        result = new MatchInfo();
        result.Line = line;
        result.IgnoreCase = !caseSensitive;

        break;
      }
    }

    ```

## <a name="see-also"></a><span data-ttu-id="907cd-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="907cd-109">See Also</span></span>

<span data-ttu-id="907cd-110">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="907cd-110">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
