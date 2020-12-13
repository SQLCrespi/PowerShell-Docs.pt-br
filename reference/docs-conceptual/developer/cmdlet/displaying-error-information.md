---
ms.date: 09/13/2016
ms.topic: reference
title: Exibir informações de erro
description: Exibir informações de erro
ms.openlocfilehash: 37a3adb91d0e616a5c7f27bcab866f8da139f969
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653052"
---
# <a name="displaying-error-information"></a><span data-ttu-id="dceef-103">Exibir informações de erro</span><span class="sxs-lookup"><span data-stu-id="dceef-103">Displaying Error Information</span></span>

<span data-ttu-id="dceef-104">Este tópico discute as maneiras pelas quais os usuários podem exibir informações de erro.</span><span class="sxs-lookup"><span data-stu-id="dceef-104">This topic discusses the ways in which users can display error information.</span></span>

<span data-ttu-id="dceef-105">Quando o cmdlet encontrar um erro, a apresentação das informações de erro, por padrão, será semelhante à saída de erro a seguir.</span><span class="sxs-lookup"><span data-stu-id="dceef-105">When your cmdlet encounters an error, the presentation of the error information will, by default, resemble the following error output.</span></span>

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

<span data-ttu-id="dceef-106">No entanto, os usuários podem exibir erros por categoria definindo a `$ErrorView` variável como `"CategoryView"` .</span><span class="sxs-lookup"><span data-stu-id="dceef-106">However, users can view errors by category by setting the `$ErrorView` variable to `"CategoryView"`.</span></span> <span data-ttu-id="dceef-107">A exibição de categoria exibe informações específicas do registro de erro em vez de uma descrição de texto livre do erro.</span><span class="sxs-lookup"><span data-stu-id="dceef-107">Category view displays specific information from the error record rather than a free-text description of the error.</span></span> <span data-ttu-id="dceef-108">Esse modo de exibição pode ser útil se você tiver uma longa lista de erros a serem verificados.</span><span class="sxs-lookup"><span data-stu-id="dceef-108">This view can be useful if you have a long list of errors to scan.</span></span> <span data-ttu-id="dceef-109">No modo de exibição de categoria, a mensagem de erro anterior é exibida da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="dceef-109">In category view, the previous error message is displayed as follows.</span></span>

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

<span data-ttu-id="dceef-110">Para obter mais informações sobre categorias de erro, consulte [registros de erro do Windows PowerShell](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="dceef-110">For more information about error categories, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dceef-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dceef-111">See Also</span></span>

[<span data-ttu-id="dceef-112">Registros de erros do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dceef-112">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

<span data-ttu-id="dceef-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="dceef-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
