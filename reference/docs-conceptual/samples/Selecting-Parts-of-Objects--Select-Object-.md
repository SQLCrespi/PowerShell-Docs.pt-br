---
ms.date: 12/23/2019
keywords: powershell, cmdlet
title: Selecionar partes de objetos com Select Object
description: Você pode usar o cmdlet `Select-Object` para criar objetos do PowerShell novos e personalizados que contenham as propriedades selecionadas dos objetos no pipeline.
ms.openlocfilehash: 92635ac54ea1469739bcb228c5e9a0a8dbfc648b
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501024"
---
# <a name="selecting-parts-of-objects-select-object"></a><span data-ttu-id="a3898-104">Selecionar partes de objetos (Select-Object)</span><span class="sxs-lookup"><span data-stu-id="a3898-104">Selecting Parts of Objects (Select-Object)</span></span>

<span data-ttu-id="a3898-105">Você pode usar o cmdlet `Select-Object` para criar objetos do PowerShell novos e personalizados que contenhas as propriedades selecionadas dos objetos usados para criá-los.</span><span class="sxs-lookup"><span data-stu-id="a3898-105">You can use the `Select-Object` cmdlet to create new, custom PowerShell objects that contain properties selected from the objects you use to create them.</span></span> <span data-ttu-id="a3898-106">Digite o seguinte comando para criar um objeto que inclua apenas as propriedades **Name** e **FreeSpace** da classe WMI **Win32_LogicalDisk** :</span><span class="sxs-lookup"><span data-stu-id="a3898-106">Type the following command to create a new object that includes only the **Name** and **FreeSpace** properties of the **Win32_LogicalDisk** WMI class:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace
```

```Output
Name      FreeSpace
----      ---------
C:      50664845312
```

<span data-ttu-id="a3898-107">Com `Select-Object`, você pode criar propriedades calculadas.</span><span class="sxs-lookup"><span data-stu-id="a3898-107">With `Select-Object` you can create calculated properties.</span></span> <span data-ttu-id="a3898-108">Dessa forma, é possível exibir **FreeSpace** em gigabytes em vez de bytes.</span><span class="sxs-lookup"><span data-stu-id="a3898-108">So you can display **FreeSpace** in gigabytes rather than bytes.</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  Select-Object -Property Name, @{
    label='FreeSpace'
    expression={($_.FreeSpace/1GB).ToString('F2')}
  }
```

```Output
Name    FreeSpace
----    ---------
C:      47.18
```
