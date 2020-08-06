---
title: Exibindo informações de erro | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e542110e9c35a74c5d4c112b0a831f7f8ad9242e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774568"
---
# <a name="displaying-error-information"></a><span data-ttu-id="af119-102">Exibir informações de erro</span><span class="sxs-lookup"><span data-stu-id="af119-102">Displaying Error Information</span></span>

<span data-ttu-id="af119-103">Este tópico discute as maneiras pelas quais os usuários podem exibir informações de erro.</span><span class="sxs-lookup"><span data-stu-id="af119-103">This topic discusses the ways in which users can display error information.</span></span>

<span data-ttu-id="af119-104">Quando o cmdlet encontrar um erro, a apresentação das informações de erro, por padrão, será semelhante à saída de erro a seguir.</span><span class="sxs-lookup"><span data-stu-id="af119-104">When your cmdlet encounters an error, the presentation of the error information will, by default, resemble the following error output.</span></span>

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

<span data-ttu-id="af119-105">No entanto, os usuários podem exibir erros por categoria definindo a `$ErrorView` variável como `"CategoryView"` .</span><span class="sxs-lookup"><span data-stu-id="af119-105">However, users can view errors by category by setting the `$ErrorView` variable to `"CategoryView"`.</span></span> <span data-ttu-id="af119-106">A exibição de categoria exibe informações específicas do registro de erro em vez de uma descrição de texto livre do erro.</span><span class="sxs-lookup"><span data-stu-id="af119-106">Category view displays specific information from the error record rather than a free-text description of the error.</span></span> <span data-ttu-id="af119-107">Esse modo de exibição pode ser útil se você tiver uma longa lista de erros a serem verificados.</span><span class="sxs-lookup"><span data-stu-id="af119-107">This view can be useful if you have a long list of errors to scan.</span></span> <span data-ttu-id="af119-108">No modo de exibição de categoria, a mensagem de erro anterior é exibida da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="af119-108">In category view, the previous error message is displayed as follows.</span></span>

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

<span data-ttu-id="af119-109">Para obter mais informações sobre categorias de erro, consulte [registros de erro do Windows PowerShell](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="af119-109">For more information about error categories, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="af119-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="af119-110">See Also</span></span>

[<span data-ttu-id="af119-111">Registros de erros do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="af119-111">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="af119-112">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="af119-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
