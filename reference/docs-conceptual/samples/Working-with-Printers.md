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
# <a name="working-with-printers-in-windows"></a><span data-ttu-id="dea94-104">Como trabalhar com impressoras no Windows</span><span class="sxs-lookup"><span data-stu-id="dea94-104">Working with Printers in Windows</span></span>

<span data-ttu-id="dea94-105">Você pode usar o PowerShell para gerenciar impressoras usando o WMI e o objeto COM **WScript.Network** do WSH.</span><span class="sxs-lookup"><span data-stu-id="dea94-105">You can use PowerShell to manage printers by using WMI and the **WScript.Network** COM object from WSH.</span></span> <span data-ttu-id="dea94-106">Usaremos uma combinação das duas ferramentas para demonstrar as tarefas específicas.</span><span class="sxs-lookup"><span data-stu-id="dea94-106">We will use a mix of both tools to demonstrate specific tasks.</span></span>

## <a name="listing-printer-connections"></a><span data-ttu-id="dea94-107">Listar conexões de impressora</span><span class="sxs-lookup"><span data-stu-id="dea94-107">Listing Printer Connections</span></span>

<span data-ttu-id="dea94-108">A maneira mais simples de listar as impressoras instaladas em um computador é usar o a classe do WMI **Win32_Printer** :</span><span class="sxs-lookup"><span data-stu-id="dea94-108">The simplest way to list the printers installed on a computer is to use the WMI **Win32_Printer** class:</span></span>

```powershell
Get-CimInstance -Class Win32_Printer
```

<span data-ttu-id="dea94-109">Você também pode listar as impressoras usando o objeto COM **WScript.Network** que normalmente é usado nos scripts do WSH:</span><span class="sxs-lookup"><span data-stu-id="dea94-109">You can also list the printers by using the **WScript.Network** COM object that is typically used in WSH scripts:</span></span>

```powershell
(New-Object -ComObject WScript.Network).EnumPrinterConnections()
```

<span data-ttu-id="dea94-110">Como esse comando retorna uma coleção simples de cadeia de caracteres de nomes de portas e nomes de dispositivo de impressora sem qualquer distinção rótulos, por isso não é fácil interpretar.</span><span class="sxs-lookup"><span data-stu-id="dea94-110">Because this command returns a simple string collection of port names and printer device names without any distinguishing labels, it is not easy to interpret.</span></span>

## <a name="adding-a-network-printer"></a><span data-ttu-id="dea94-111">Adicionar uma impressora de rede</span><span class="sxs-lookup"><span data-stu-id="dea94-111">Adding a Network Printer</span></span>

<span data-ttu-id="dea94-112">Para adicionar uma nova impressora de rede, use **WScript.Network** :</span><span class="sxs-lookup"><span data-stu-id="dea94-112">To add a new network printer, use **WScript.Network** :</span></span>

```powershell
(New-Object -ComObject WScript.Network).AddWindowsPrinterConnection("\\Printserver01\Xerox5")
```

## <a name="setting-a-default-printer"></a><span data-ttu-id="dea94-113">Configurar uma impressora padrão</span><span class="sxs-lookup"><span data-stu-id="dea94-113">Setting a Default Printer</span></span>

<span data-ttu-id="dea94-114">Para usar o WMI para definir a impressora padrão, localize a impressora na coleção **Win32_Printer** e, em seguida, invoque o método **SetDefaultPrinter** :</span><span class="sxs-lookup"><span data-stu-id="dea94-114">To use WMI to set the default printer, find the printer in the **Win32_Printer** collection and then invoke the **SetDefaultPrinter** method:</span></span>

```powershell
$printer = Get-CimInstance -Class Win32_Printer -Filter "Name='HP LaserJet 5Si'"
Invoke-CimMethod -InputObject $printer -MethodName SetDefaultPrinter
```

<span data-ttu-id="dea94-115">**WScript.Network** é um pouco mais simples de usar, pois ele tem um método **SetDefaultPrinter** que usa apenas o nome da impressora como um argumento:</span><span class="sxs-lookup"><span data-stu-id="dea94-115">**WScript.Network** is a little simpler to use, because it has a **SetDefaultPrinter** method that takes only the printer name as an argument:</span></span>

```powershell
(New-Object -ComObject WScript.Network).SetDefaultPrinter('HP LaserJet 5Si')
```

## <a name="removing-a-printer-connection"></a><span data-ttu-id="dea94-116">Remover a conexão da impressora</span><span class="sxs-lookup"><span data-stu-id="dea94-116">Removing a Printer Connection</span></span>

<span data-ttu-id="dea94-117">Para remover uma conexão de impressora, use o método **WScript.Network RemovePrinterConnection** :</span><span class="sxs-lookup"><span data-stu-id="dea94-117">To remove a printer connection, use the **WScript.Network RemovePrinterConnection** method:</span></span>

```powershell
(New-Object -ComObject WScript.Network).RemovePrinterConnection("\\Printserver01\Xerox5")
```
