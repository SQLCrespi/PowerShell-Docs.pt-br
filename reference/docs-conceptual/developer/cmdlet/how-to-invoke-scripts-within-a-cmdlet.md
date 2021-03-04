---
ms.date: 09/13/2016
ms.topic: reference
title: Como invocar scripts dentro de um cmdlet
description: Como invocar scripts dentro de um cmdlet
ms.openlocfilehash: 503ecb8913fe61ef3f5ec6fe969c22c2319a4f12
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685341"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a>Como invocar scripts dentro de um cmdlet

Este exemplo mostra como invocar um script que é fornecido a um cmdlet. O script é executado pelo cmdlet e seus resultados são retornados para o cmdlet como uma coleção de objetos [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) .

## <a name="to-invoke-a-script-block"></a>Para invocar um bloco de script

1. O comando verifica se um bloco de script foi fornecido ao cmdlet. Se um bloco de script foi fornecido, o comando invoca o bloco de script com seus parâmetros necessários.

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

2. Em seguida, o script faz a iteração pela coleção retornada de objetos [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) e executa as operações necessárias.

    ```csharp
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

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
