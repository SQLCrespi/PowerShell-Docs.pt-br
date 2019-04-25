---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: 385bb7223b19c8ace8088ba469e543721a527b99
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057497"
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="8de6f-102">Instruções de desinstalação</span><span class="sxs-lookup"><span data-stu-id="8de6f-102">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="8de6f-103">Usando o Prompt de Comando</span><span class="sxs-lookup"><span data-stu-id="8de6f-103">Using Command Prompt</span></span>
1.  <span data-ttu-id="8de6f-104">Abra o **Prompt de Comando.**</span><span class="sxs-lookup"><span data-stu-id="8de6f-104">Open **Command Prompt.**</span></span>
2.  <span data-ttu-id="8de6f-105">Execute o [Inicializador Autônomo do Windows Update](https://support.microsoft.com/en-us/kb/934307), conforme mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="8de6f-105">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/en-us/kb/934307) as shown below:</span></span>

<span data-ttu-id="8de6f-106">No Windows Server 2012 R2 e Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="8de6f-106">On Windows Server 2012 R2 and Windows 8.1:</span></span>
```powershell
wusa /uninstall /kb:3134758
```
<span data-ttu-id="8de6f-107">No Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="8de6f-107">On Windows Server 2012:</span></span>
```powershell
wusa /uninstall /kb:3134759
```
<span data-ttu-id="8de6f-108">No Windows Server 2008 R2 SP1 e Windows 7 SP1:</span><span class="sxs-lookup"><span data-stu-id="8de6f-108">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>
```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="8de6f-109">Usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="8de6f-109">Using Control Panel</span></span>
1.  <span data-ttu-id="8de6f-110">Abra o **Painel de Controle.**</span><span class="sxs-lookup"><span data-stu-id="8de6f-110">Open **Control Panel.**</span></span>
2.  <span data-ttu-id="8de6f-111">Abra **Programas** e, em seguida, **Desinstalar um programa.**</span><span class="sxs-lookup"><span data-stu-id="8de6f-111">Open **Programs**, then open **Uninstall a program.**</span></span>
3.  <span data-ttu-id="8de6f-112">Clique em **Exibir atualizações instaladas.**</span><span class="sxs-lookup"><span data-stu-id="8de6f-112">Click **View installed updates.**</span></span>
4.  <span data-ttu-id="8de6f-113">Selecione **Windows Management Framework 5.0** na lista de atualizações instaladas.</span><span class="sxs-lookup"><span data-stu-id="8de6f-113">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="8de6f-114">Isso corresponde à *KB3134758*, *KB3134759* ou *KB3134760*.</span><span class="sxs-lookup"><span data-stu-id="8de6f-114">This corresponds to *KB3134758*, *KB3134759*, or *KB3134760*.</span></span> <span data-ttu-id="8de6f-115">Clique em **Desinstalar.**</span><span class="sxs-lookup"><span data-stu-id="8de6f-115">Click **Uninstall.**</span></span>
