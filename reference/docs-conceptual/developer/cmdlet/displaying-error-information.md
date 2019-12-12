---
title: Exibindo informações de erro | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76fcc0c1-9795-45d3-a564-40f822b657b5
caps.latest.revision: 8
ms.openlocfilehash: 4bc8666ee9053eb368402c8644558f4fe2dcc9ee
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369965"
---
# <a name="displaying-error-information"></a><span data-ttu-id="b1fbe-102">Exibir informações de erro</span><span class="sxs-lookup"><span data-stu-id="b1fbe-102">Displaying Error Information</span></span>

<span data-ttu-id="b1fbe-103">Este tópico discute as maneiras pelas quais os usuários podem exibir informações de erro.</span><span class="sxs-lookup"><span data-stu-id="b1fbe-103">This topic discusses the ways in which users can display error information.</span></span>

<span data-ttu-id="b1fbe-104">Quando o cmdlet encontrar um erro, a apresentação das informações de erro, por padrão, será semelhante à saída de erro a seguir.</span><span class="sxs-lookup"><span data-stu-id="b1fbe-104">When your cmdlet encounters an error, the presentation of the error information will, by default, resemble the following error output.</span></span>

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

<span data-ttu-id="b1fbe-105">No entanto, os usuários podem exibir erros por categoria definindo a variável `$ErrorView` como `"CategoryView"`.</span><span class="sxs-lookup"><span data-stu-id="b1fbe-105">However, users can view errors by category by setting the `$ErrorView` variable to `"CategoryView"`.</span></span> <span data-ttu-id="b1fbe-106">A exibição de categoria exibe informações específicas do registro de erro em vez de uma descrição de texto livre do erro.</span><span class="sxs-lookup"><span data-stu-id="b1fbe-106">Category view displays specific information from the error record rather than a free-text description of the error.</span></span> <span data-ttu-id="b1fbe-107">Esse modo de exibição pode ser útil se você tiver uma longa lista de erros a serem verificados.</span><span class="sxs-lookup"><span data-stu-id="b1fbe-107">This view can be useful if you have a long list of errors to scan.</span></span> <span data-ttu-id="b1fbe-108">No modo de exibição de categoria, a mensagem de erro anterior é exibida da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="b1fbe-108">In category view, the previous error message is displayed as follows.</span></span>

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

<span data-ttu-id="b1fbe-109">Para obter mais informações sobre categorias de erro, consulte [registros de erro do Windows PowerShell](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="b1fbe-109">For more information about error categories, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b1fbe-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b1fbe-110">See Also</span></span>

[<span data-ttu-id="b1fbe-111">Registros de erro do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1fbe-111">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

<span data-ttu-id="b1fbe-112">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="b1fbe-112">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
