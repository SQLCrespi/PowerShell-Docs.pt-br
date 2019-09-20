---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
title: Melhorias do Console no WMF 5.1
ms.openlocfilehash: d0dd8e3c31dc0ddebab1bb899468b77a9292954d
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71147626"
---
# <a name="console-improvements-in-wmf-51"></a><span data-ttu-id="85e62-103">Melhorias do Console no WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="85e62-103">Console Improvements in WMF 5.1</span></span>

## <a name="powershell-console-improvements"></a><span data-ttu-id="85e62-104">Melhorias do console do PowerShell</span><span class="sxs-lookup"><span data-stu-id="85e62-104">PowerShell console improvements</span></span>

<span data-ttu-id="85e62-105">As seguintes alterações foram feitas ao powershell.exe no WMF 5.1 para melhorar a experiência do console:</span><span class="sxs-lookup"><span data-stu-id="85e62-105">The following changes have been made to powershell.exe in WMF 5.1 to improve the console experience:</span></span>

### <a name="vt100-support"></a><span data-ttu-id="85e62-106">Suporte a VT100</span><span class="sxs-lookup"><span data-stu-id="85e62-106">VT100 support</span></span>

<span data-ttu-id="85e62-107">O Windows 10 adicionou suporte para [sequências de escape VT100](/windows/console/console-virtual-terminal-sequences).</span><span class="sxs-lookup"><span data-stu-id="85e62-107">Windows 10 added support for [VT100 escape sequences](/windows/console/console-virtual-terminal-sequences).</span></span>
<span data-ttu-id="85e62-108">PowerShell ignorará determinadas sequências de escape de formatação do VT100 ao calcular larguras da tabela.</span><span class="sxs-lookup"><span data-stu-id="85e62-108">PowerShell will ignore certain VT100 formatting escape sequences when calculating table widths.</span></span>

<span data-ttu-id="85e62-109">O PowerShell também adicionou uma nova API que pode ser usada no código de formatação para determinar se há suporte para VT100.</span><span class="sxs-lookup"><span data-stu-id="85e62-109">PowerShell also added a new API that can be used in formatting code to determine if VT100 is supported.</span></span> <span data-ttu-id="85e62-110">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="85e62-110">For example:</span></span>

```powershell
if ($host.UI.SupportsVirtualTerminal)
{
    $esc = [char]0x1b
    "A yellow ${esc}[93mhello${esc}[0m"
}
else
{
    "A default hello"
}
```

<span data-ttu-id="85e62-111">Aqui está um [exemplo](https://gist.github.com/lzybkr/dcb973dccd54900b67783c48083c28f7) completo que pode ser usado para realçar correspondências de `Select-String`.</span><span class="sxs-lookup"><span data-stu-id="85e62-111">Here is a complete [example](https://gist.github.com/lzybkr/dcb973dccd54900b67783c48083c28f7) that can be used to highlight matches from `Select-String`.</span></span> <span data-ttu-id="85e62-112">Salve o exemplo em um arquivo chamado `MatchInfo.format.ps1xml`, então, para usá-lo em seu perfil ou em outro local, execute `Update-FormatData -Prepend MatchInfo.format.ps1xml`.</span><span class="sxs-lookup"><span data-stu-id="85e62-112">Save the example in a file named `MatchInfo.format.ps1xml`, then to use it, in your profile or elsewhere, run `Update-FormatData -Prepend MatchInfo.format.ps1xml`.</span></span>

<span data-ttu-id="85e62-113">As sequências de escape do VT100 têm suporte apenas a partir da Atualização de Aniversário do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="85e62-113">Note that VT100 escape sequences are only supported starting with the Windows 10 Anniversary update.</span></span>
<span data-ttu-id="85e62-114">Elas não têm suporte em sistemas anteriores.</span><span class="sxs-lookup"><span data-stu-id="85e62-114">They are not supported on earlier systems.</span></span>

### <a name="vi-mode-support-in-psreadline"></a><span data-ttu-id="85e62-115">Suporte ao modo vi em PSReadline</span><span class="sxs-lookup"><span data-stu-id="85e62-115">Vi mode support in PSReadline</span></span>

<span data-ttu-id="85e62-116">[PSReadline](https://github.com/PowerShell/PSReadLine) adiciona suporte para o modo vi.</span><span class="sxs-lookup"><span data-stu-id="85e62-116">[PSReadline](https://github.com/PowerShell/PSReadLine) adds support for vi mode.</span></span> <span data-ttu-id="85e62-117">Para usar o modo vi, execute `Set-PSReadlineOption -EditMode Vi`.</span><span class="sxs-lookup"><span data-stu-id="85e62-117">To use vi mode, run `Set-PSReadlineOption -EditMode Vi`.</span></span>

### <a name="redirected-stdin-with-interactive-input"></a><span data-ttu-id="85e62-118">STDIN redirecionada com entrada interativa</span><span class="sxs-lookup"><span data-stu-id="85e62-118">Redirected stdin with interactive input</span></span>

<span data-ttu-id="85e62-119">Em versões anteriores, iniciar o PowerShell com `powershell -File -` era necessário quando stdin era redirecionado e você queria inserir comandos interativamente.</span><span class="sxs-lookup"><span data-stu-id="85e62-119">In earlier versions, starting PowerShell with `powershell -File -` was required when stdin was redirected and you wanted to enter commands interactively.</span></span>

<span data-ttu-id="85e62-120">Com o WMF 5.1, essa opção difícil de descobrir não é mais necessária.</span><span class="sxs-lookup"><span data-stu-id="85e62-120">With WMF 5.1, this hard to discover option is no longer necessary.</span></span> <span data-ttu-id="85e62-121">Você pode iniciar o PowerShell sem nenhuma opção.</span><span class="sxs-lookup"><span data-stu-id="85e62-121">You can start PowerShell without any options.</span></span>

<span data-ttu-id="85e62-122">Observe que PSReadline não oferece suporte à STDIN redirecionada, e a experiência de edição de linha de comando interna com STDIN redirecionada é extremamente limitada, por exemplo, as teclas de direção não funcionam.</span><span class="sxs-lookup"><span data-stu-id="85e62-122">Note that PSReadline does not support redirected stdin, and the built-in command-line editing experience with redirected stdin is extremely limited, for example, arrow keys don't work.</span></span> <span data-ttu-id="85e62-123">Uma versão futura do PSReadline deve resolver esse problema.</span><span class="sxs-lookup"><span data-stu-id="85e62-123">A future release of PSReadline should address this issue.</span></span>