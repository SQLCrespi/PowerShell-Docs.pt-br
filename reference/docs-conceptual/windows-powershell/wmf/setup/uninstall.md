---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
title: Desinstalar o WMF 5.0
ms.openlocfilehash: f562a4a4506bfdede6b23bd186b80f40cc9e45ca
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808672"
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="b2531-103">Instruções de desinstalação</span><span class="sxs-lookup"><span data-stu-id="b2531-103">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="b2531-104">Usando o Prompt de Comando</span><span class="sxs-lookup"><span data-stu-id="b2531-104">Using Command Prompt</span></span>

1. <span data-ttu-id="b2531-105">Abra o **Prompt de Comando.**</span><span class="sxs-lookup"><span data-stu-id="b2531-105">Open **Command Prompt.**</span></span>
2. <span data-ttu-id="b2531-106">Execute o [Inicializador Autônomo do Windows Update](https://support.microsoft.com/en-us/kb/934307), conforme mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="b2531-106">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/en-us/kb/934307) as shown below:</span></span>

<span data-ttu-id="b2531-107">No Windows Server 2012 R2 e Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="b2531-107">On Windows Server 2012 R2 and Windows 8.1:</span></span>

```powershell
wusa /uninstall /kb:3134758
```

<span data-ttu-id="b2531-108">No Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="b2531-108">On Windows Server 2012:</span></span>

```powershell
wusa /uninstall /kb:3134759
```

<span data-ttu-id="b2531-109">No Windows Server 2008 R2 SP1 e Windows 7 SP1:</span><span class="sxs-lookup"><span data-stu-id="b2531-109">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>

```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="b2531-110">Usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="b2531-110">Using Control Panel</span></span>

1. <span data-ttu-id="b2531-111">Abra o **Painel de Controle.**</span><span class="sxs-lookup"><span data-stu-id="b2531-111">Open **Control Panel.**</span></span>
2. <span data-ttu-id="b2531-112">Abra **Programas** e, em seguida, **Desinstalar um programa.**</span><span class="sxs-lookup"><span data-stu-id="b2531-112">Open **Programs**, then open **Uninstall a program.**</span></span>
3. <span data-ttu-id="b2531-113">Clique em **Exibir atualizações instaladas.**</span><span class="sxs-lookup"><span data-stu-id="b2531-113">Click **View installed updates.**</span></span>
4. <span data-ttu-id="b2531-114">Selecione **Windows Management Framework 5.0** na lista de atualizações instaladas.</span><span class="sxs-lookup"><span data-stu-id="b2531-114">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="b2531-115">Isso corresponde à *KB3134758*, *KB3134759* ou *KB3134760*.</span><span class="sxs-lookup"><span data-stu-id="b2531-115">This corresponds to *KB3134758*, *KB3134759*, or *KB3134760*.</span></span> <span data-ttu-id="b2531-116">Clique em **Desinstalar.**</span><span class="sxs-lookup"><span data-stu-id="b2531-116">Click **Uninstall.**</span></span>
