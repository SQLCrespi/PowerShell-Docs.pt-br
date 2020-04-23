---
ms.date: 12/23/2019
keywords: powershell, cmdlet
title: Selecionar partes de objetos com Select Object
ms.openlocfilehash: 06b92c7c4c5098c707a7d9f9d9a96e6b6a897f80
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "75737161"
---
# <a name="selecting-parts-of-objects-select-object"></a>Selecionar partes de objetos (Select-Object)

Você pode usar o cmdlet `Select-Object` para criar objetos do PowerShell novos e personalizados que contenhas as propriedades selecionadas dos objetos usados para criá-los. Digite o seguinte comando para criar um objeto que inclua apenas as propriedades **Name** e **FreeSpace** da classe WMI **Win32_LogicalDisk**:

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
