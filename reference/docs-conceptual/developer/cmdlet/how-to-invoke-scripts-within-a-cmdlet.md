---
title: Como invocar scripts em um cmdlet | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 248ad7e2e35fe53682836d094a391023007fa0b7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784122"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a><span data-ttu-id="94601-102">Como invocar scripts dentro de um cmdlet</span><span class="sxs-lookup"><span data-stu-id="94601-102">How to Invoke Scripts Within a Cmdlet</span></span>

<span data-ttu-id="94601-103">Este exemplo mostra como invocar um script que é fornecido a um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="94601-103">This example shows how to invoke a script that is supplied to a cmdlet.</span></span> <span data-ttu-id="94601-104">O script é executado pelo cmdlet e seus resultados são retornados para o cmdlet como uma coleção de objetos [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) .</span><span class="sxs-lookup"><span data-stu-id="94601-104">The script is executed by the cmdlet, and its results are returned to the cmdlet as a collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects.</span></span>

## <a name="to-invoke-a-script-block"></a><span data-ttu-id="94601-105">Para invocar um bloco de script</span><span class="sxs-lookup"><span data-stu-id="94601-105">To invoke a script block</span></span>

1. <span data-ttu-id="94601-106">O comando verifica se um bloco de script foi fornecido ao cmdlet.</span><span class="sxs-lookup"><span data-stu-id="94601-106">The command verifies that a script block was supplied to the cmdlet.</span></span> <span data-ttu-id="94601-107">Se um bloco de script foi fornecido, o comando invoca o bloco de script com seus parâmetros necessários.</span><span class="sxs-lookup"><span data-stu-id="94601-107">If a script block was supplied, the command invokes the script block with its required parameters.</span></span>

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

2. <span data-ttu-id="94601-108">Em seguida, o script faz a iteração pela coleção retornada de objetos [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) e executa as operações necessárias.</span><span class="sxs-lookup"><span data-stu-id="94601-108">Then, the script iterates through the returned collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects and perform the necessary operations.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="94601-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="94601-109">See Also</span></span>

[<span data-ttu-id="94601-110">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="94601-110">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
