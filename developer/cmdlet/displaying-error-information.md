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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068276"
---
# <a name="displaying-error-information"></a><span data-ttu-id="1a1b7-102">Exibir informações de erro</span><span class="sxs-lookup"><span data-stu-id="1a1b7-102">Displaying Error Information</span></span>

<span data-ttu-id="1a1b7-103">Este tópico discute as maneiras em que os usuários podem exibir informações de erro.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-103">This topic discusses the ways in which users can display error information.</span></span>

<span data-ttu-id="1a1b7-104">Quando seu cmdlet encontra um erro, a apresentação das informações de erro serão, por padrão, se parecer com a seguinte saída de erro.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-104">When your cmdlet encounters an error, the presentation of the error information will, by default, resemble the following error output.</span></span>

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

<span data-ttu-id="1a1b7-105">No entanto, os usuários podem exibir erros por categoria, definindo o `$ErrorView` variável para `"CategoryView"`.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-105">However, users can view errors by category by setting the `$ErrorView` variable to `"CategoryView"`.</span></span> <span data-ttu-id="1a1b7-106">Modo de exibição de categoria exibe informações específicas do registro de erro em vez de uma descrição de texto livre do erro.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-106">Category view displays specific information from the error record rather than a free-text description of the error.</span></span> <span data-ttu-id="1a1b7-107">Este modo de exibição pode ser útil se você tiver uma longa lista de erros de verificação.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-107">This view can be useful if you have a long list of errors to scan.</span></span> <span data-ttu-id="1a1b7-108">No modo de exibição de categoria, a mensagem de erro anterior é exibida da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="1a1b7-108">In category view, the previous error message is displayed as follows.</span></span>

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

<span data-ttu-id="1a1b7-109">Para obter mais informações sobre categorias de erro, consulte [registros de erros do Windows PowerShell](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="1a1b7-109">For more information about error categories, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1a1b7-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1a1b7-110">See Also</span></span>

[<span data-ttu-id="1a1b7-111">Registros de erro do PowerShell do Windows</span><span class="sxs-lookup"><span data-stu-id="1a1b7-111">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

<span data-ttu-id="1a1b7-112">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="1a1b7-112">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
