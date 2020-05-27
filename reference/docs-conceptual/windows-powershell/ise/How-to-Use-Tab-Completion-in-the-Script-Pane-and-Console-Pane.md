---
ms.date: 01/02/2020
keywords: powershell, cmdlet
title: Como usar o preenchimento com Tab no Painel de Script e no Painel de Console
ms.openlocfilehash: 07cf9ff75db8d33ed018542153bfcd7503035e40
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808822"
---
# <a name="how-to-use-tab-completion-in-the-script-pane-and-console-pane"></a><span data-ttu-id="7346e-103">Como usar o preenchimento com Tab no Painel de Script e no Painel de Console</span><span class="sxs-lookup"><span data-stu-id="7346e-103">How to Use Tab Completion in the Script Pane and Console Pane</span></span>

<span data-ttu-id="7346e-104">O preenchimento com Tab fornece ajuda automática quando você está digitando no Painel de Script ou no Painel de Comando.</span><span class="sxs-lookup"><span data-stu-id="7346e-104">Tab completion provides automatic help when you are typing in the Script Pane or in the Command Pane.</span></span> <span data-ttu-id="7346e-105">Use as seguintes etapas para aproveitar esse recurso:</span><span class="sxs-lookup"><span data-stu-id="7346e-105">Use the following steps to take advantage of this feature:</span></span>

## <a name="to-automatically-complete-a-command-entry"></a><span data-ttu-id="7346e-106">Para preencher automaticamente uma entrada de comando</span><span class="sxs-lookup"><span data-stu-id="7346e-106">To automatically complete a command entry</span></span>

<span data-ttu-id="7346e-107">No Painel de Comando ou Painel de Script, digite alguns caracteres de um comando e, em seguida, pressione <kbd>TAB</kbd> para escolher o texto de preenchimento desejado.</span><span class="sxs-lookup"><span data-stu-id="7346e-107">In the Command Pane or Script Pane, type a few characters of a command and then press <kbd>TAB</kbd> to select the desired completion text.</span></span> <span data-ttu-id="7346e-108">Se vários itens começam com o texto que você digitou inicialmente, continue a pressionar <kbd>TAB</kbd> até que o item desejado seja exibido.</span><span class="sxs-lookup"><span data-stu-id="7346e-108">If multiple items begin with the text that you initially typed, then continue pressing <kbd>TAB</kbd> until the item you want appears.</span></span> <span data-ttu-id="7346e-109">O preenchimento com Tab pode ajudar na digitação do nome de um cmdlet, nome de parâmetro, nome de variável, nome de propriedade do objeto ou um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="7346e-109">Tab completion can help with typing a cmdlet name, parameter name, variable name, object property name, or a file path.</span></span>

> [!NOTE]
> <span data-ttu-id="7346e-110">No Painel de Script, pressionar <kbd>TAB</kbd> preencherá automaticamente um comando somente quando você estiver editando arquivos `.ps1`, `.psd1` ou `.psm1`.</span><span class="sxs-lookup"><span data-stu-id="7346e-110">In the Script Pane, pressing <kbd>TAB</kbd> will automatically complete a command only when you are editing `.ps1`, `.psd1`, or `.psm1` files.</span></span> <span data-ttu-id="7346e-111">O preenchimento com Tab funciona a qualquer momento quando você está digitando no Painel de Comando.</span><span class="sxs-lookup"><span data-stu-id="7346e-111">Tab completion works any time when you are typing in the Command Pane.</span></span>

## <a name="to-automatically-complete-a-cmdlet-parameter-entry"></a><span data-ttu-id="7346e-112">Para preencher automaticamente uma entrada de parâmetro de cmdlet</span><span class="sxs-lookup"><span data-stu-id="7346e-112">To automatically complete a cmdlet parameter entry</span></span>

<span data-ttu-id="7346e-113">No Painel de Comando ou de Script, digite um cmdlet seguido por um traço e pressione <kbd>TAB</kbd>.</span><span class="sxs-lookup"><span data-stu-id="7346e-113">In the Command Pane or Script pane, type a cmdlet followed by a dash and then press <kbd>TAB</kbd>.</span></span>

<span data-ttu-id="7346e-114">Por exemplo, digite `Get-Process -` e pressione <kbd>TAB</kbd> várias vezes para exibir cada um dos parâmetros do cmdlet sucessivamente.</span><span class="sxs-lookup"><span data-stu-id="7346e-114">For example, type `Get-Process -` and then press <kbd>TAB</kbd> multiple times to display each of the parameters for the cmdlet in turn.</span></span>

## <a name="see-also"></a><span data-ttu-id="7346e-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7346e-115">See Also</span></span>

- [<span data-ttu-id="7346e-116">Apresentando o ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7346e-116">Introducing the Windows PowerShell ISE</span></span>](Introducing-the-Windows-PowerShell-ISE.md)
- [<span data-ttu-id="7346e-117">Como criar uma guia do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7346e-117">How to Create a PowerShell Tab</span></span>](How-to-Create-a-PowerShell-Tab-in-Windows-PowerShell-ISE.md)
