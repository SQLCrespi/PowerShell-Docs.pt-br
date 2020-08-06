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
# <a name="runspace02-c-code-sample"></a>Exemplo de código Runspace02 (C#)

Aqui está o código-fonte do C# para o exemplo Runspace02. Este exemplo usa a classe [System. Management. Automation. Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) para executar o `Get-Process` cmdlet de forma síncrona. Windows Forms e a ligação de dados são usados para exibir os resultados em um controle DataGridView

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace02/Runspace02.cs" range="11-82":::

## <a name="see-also"></a>Consulte Também

[SDK do Windows PowerShell](../windows-powershell-reference.md)
