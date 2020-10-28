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
# <a name="selecting-parts-of-objects-select-object"></a>Selecionar partes de objetos (Select-Object)

Você pode usar o cmdlet `Select-Object` para criar objetos do PowerShell novos e personalizados que contenhas as propriedades selecionadas dos objetos usados para criá-los. Digite o seguinte comando para criar um objeto que inclua apenas as propriedades **Name** e **FreeSpace** da classe WMI **Win32_LogicalDisk** :

```powershell
Get-CimInstance -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace
```

```Output
Name      FreeSpace
----      ---------
C:      50664845312
```

Com `Select-Object`, você pode criar propriedades calculadas. Dessa forma, é possível exibir **FreeSpace** em gigabytes em vez de bytes.

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
