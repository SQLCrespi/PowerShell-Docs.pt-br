---
ms.date: 06/12/2017
title: Desinstalar o WMF 5.0
description: Este artigo explica como desinstalar o WMF de versões mais antigas do Windows.
ms.openlocfilehash: d8078ea918db2c1cf9a7ddd6ea8d1413b593c0ff
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660810"
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="84047-103">Instruções de desinstalação</span><span class="sxs-lookup"><span data-stu-id="84047-103">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="84047-104">Usando o Prompt de Comando</span><span class="sxs-lookup"><span data-stu-id="84047-104">Using Command Prompt</span></span>

1. <span data-ttu-id="84047-105">Abra o **Prompt de Comando.**</span><span class="sxs-lookup"><span data-stu-id="84047-105">Open **Command Prompt.**</span></span>
2. <span data-ttu-id="84047-106">Execute o [Inicializador Autônomo do Windows Update](https://support.microsoft.com/kb/934307), conforme mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="84047-106">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/kb/934307) as shown below:</span></span>

<span data-ttu-id="84047-107">No Windows Server 2012 R2 e Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="84047-107">On Windows Server 2012 R2 and Windows 8.1:</span></span>

```powershell
wusa /uninstall /kb:3134758
```

<span data-ttu-id="84047-108">No Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="84047-108">On Windows Server 2012:</span></span>

```powershell
wusa /uninstall /kb:3134759
```

<span data-ttu-id="84047-109">No Windows Server 2008 R2 SP1 e Windows 7 SP1:</span><span class="sxs-lookup"><span data-stu-id="84047-109">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>

```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="84047-110">Usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="84047-110">Using Control Panel</span></span>

1. <span data-ttu-id="84047-111">Abra o **Painel de Controle.**</span><span class="sxs-lookup"><span data-stu-id="84047-111">Open **Control Panel.**</span></span>
2. <span data-ttu-id="84047-112">Abra **Programas** e, em seguida, **Desinstalar um programa.**</span><span class="sxs-lookup"><span data-stu-id="84047-112">Open **Programs** , then open **Uninstall a program.**</span></span>
3. <span data-ttu-id="84047-113">Clique em **Exibir atualizações instaladas.**</span><span class="sxs-lookup"><span data-stu-id="84047-113">Click **View installed updates.**</span></span>
4. <span data-ttu-id="84047-114">Selecione **Windows Management Framework 5.0** na lista de atualizações instaladas.</span><span class="sxs-lookup"><span data-stu-id="84047-114">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="84047-115">Isso corresponde à *KB3134758* , *KB3134759* ou *KB3134760*.</span><span class="sxs-lookup"><span data-stu-id="84047-115">This corresponds to *KB3134758* , *KB3134759* , or *KB3134760*.</span></span> <span data-ttu-id="84047-116">Clique em **Desinstalar.**</span><span class="sxs-lookup"><span data-stu-id="84047-116">Click **Uninstall.**</span></span>
