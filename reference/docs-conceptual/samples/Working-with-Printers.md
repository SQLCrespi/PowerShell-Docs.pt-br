---
ms.date: 12/23/2019
keywords: powershell, cmdlet
title: Trabalhando com impressoras
description: Este artigo mostra como gerenciar impressoras no Windows usando objetos WMI e interfaces COM.
ms.openlocfilehash: 2606753783043eeae8e9d461e56f0901149cb8e3
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501075"
---
# <a name="working-with-printers-in-windows"></a>Como trabalhar com impressoras no Windows

Você pode usar o PowerShell para gerenciar impressoras usando o WMI e o objeto COM **WScript.Network** do WSH. Usaremos uma combinação das duas ferramentas para demonstrar as tarefas específicas.

## <a name="listing-printer-connections"></a>Listar conexões de impressora

A maneira mais simples de listar as impressoras instaladas em um computador é usar o a classe do WMI **Win32_Printer** :

```powershell
Get-CimInstance -Class Win32_Printer
```

Você também pode listar as impressoras usando o objeto COM **WScript.Network** que normalmente é usado nos scripts do WSH:

```powershell
(New-Object -ComObject WScript.Network).EnumPrinterConnections()
```

Como esse comando retorna uma coleção simples de cadeia de caracteres de nomes de portas e nomes de dispositivo de impressora sem qualquer distinção rótulos, por isso não é fácil interpretar.

## <a name="adding-a-network-printer"></a>Adicionar uma impressora de rede

Para adicionar uma nova impressora de rede, use **WScript.Network** :

```powershell
(New-Object -ComObject WScript.Network).AddWindowsPrinterConnection("\\Printserver01\Xerox5")
```

## <a name="setting-a-default-printer"></a>Configurar uma impressora padrão

Para usar o WMI para definir a impressora padrão, localize a impressora na coleção **Win32_Printer** e, em seguida, invoque o método **SetDefaultPrinter** :

```powershell
$printer = Get-CimInstance -Class Win32_Printer -Filter "Name='HP LaserJet 5Si'"
Invoke-CimMethod -InputObject $printer -MethodName SetDefaultPrinter
```

**WScript.Network** é um pouco mais simples de usar, pois ele tem um método **SetDefaultPrinter** que usa apenas o nome da impressora como um argumento:

```powershell
(New-Object -ComObject WScript.Network).SetDefaultPrinter('HP LaserJet 5Si')
```

## <a name="removing-a-printer-connection"></a>Remover a conexão da impressora

Para remover uma conexão de impressora, use o método **WScript.Network RemovePrinterConnection** :

```powershell
(New-Object -ComObject WScript.Network).RemovePrinterConnection("\\Printserver01\Xerox5")
```
