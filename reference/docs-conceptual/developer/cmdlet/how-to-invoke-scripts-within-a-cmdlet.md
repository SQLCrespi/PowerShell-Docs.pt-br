---
ms.date: 09/13/2016
ms.topic: reference
title: Como invocar scripts dentro de um cmdlet
description: Como invocar scripts dentro de um cmdlet
ms.openlocfilehash: f4a43a1e1240854e57deac5721e1e070c1a45a51
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667021"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a><span data-ttu-id="e1127-103">Como invocar scripts dentro de um cmdlet</span><span class="sxs-lookup"><span data-stu-id="e1127-103">How to Invoke Scripts Within a Cmdlet</span></span>

<span data-ttu-id="e1127-104">Este exemplo mostra como invocar um script que é fornecido a um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e1127-104">This example shows how to invoke a script that is supplied to a cmdlet.</span></span> <span data-ttu-id="e1127-105">O script é executado pelo cmdlet e seus resultados são retornados para o cmdlet como uma coleção de objetos [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) .</span><span class="sxs-lookup"><span data-stu-id="e1127-105">The script is executed by the cmdlet, and its results are returned to the cmdlet as a collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects.</span></span>

## <a name="to-invoke-a-script-block"></a><span data-ttu-id="e1127-106">Para invocar um bloco de script</span><span class="sxs-lookup"><span data-stu-id="e1127-106">To invoke a script block</span></span>

1. <span data-ttu-id="e1127-107">O comando verifica se um bloco de script foi fornecido ao cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e1127-107">The command verifies that a script block was supplied to the cmdlet.</span></span> <span data-ttu-id="e1127-108">Se um bloco de script foi fornecido, o comando invoca o bloco de script com seus parâmetros necessários.</span><span class="sxs-lookup"><span data-stu-id="e1127-108">If a script block was supplied, the command invokes the script block with its required parameters.</span></span>

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

2. <span data-ttu-id="e1127-109">Em seguida, o script faz a iteração pela coleção retornada de objetos [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) e executa as operações necessárias.</span><span class="sxs-lookup"><span data-stu-id="e1127-109">Then, the script iterates through the returned collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects and perform the necessary operations.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e1127-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e1127-110">See Also</span></span>

[<span data-ttu-id="e1127-111">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1127-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
