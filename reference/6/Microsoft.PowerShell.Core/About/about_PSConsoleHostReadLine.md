---
description: Explica como criar uma personalização de como o PowerShell lê a entrada no prompt do console.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_psconsolehostreadline?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSConsoleHostReadLine
ms.openlocfilehash: 59373f7a69f5a27411c9087bb666929321f654c0
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196499"
---
# <a name="about_psconsolehostreadline"></a><span data-ttu-id="93dbb-104">about_PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="93dbb-104">about_PSConsoleHostReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="93dbb-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="93dbb-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="93dbb-106">Explica como criar uma personalização de como o PowerShell lê a entrada no prompt do console.</span><span class="sxs-lookup"><span data-stu-id="93dbb-106">Explains how to create a customize how PowerShell reads input at the console prompt.</span></span>

## <a name="long-description"></a><span data-ttu-id="93dbb-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="93dbb-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="93dbb-108">A partir do Windows PowerShell 3,0, você pode escrever uma função chamada PSConsoleHostReadLine que substitui a forma padrão pela qual a entrada do console é processada.</span><span class="sxs-lookup"><span data-stu-id="93dbb-108">Starting in Windows PowerShell 3.0, you can write a function named PSConsoleHostReadLine that overrides the default way that console input is processed.</span></span>

### <a name="examples"></a><span data-ttu-id="93dbb-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="93dbb-109">EXAMPLES</span></span>

<span data-ttu-id="93dbb-110">O exemplo a seguir inicia o bloco de notas e obtém a entrada de um arquivo de texto que o usuário cria:</span><span class="sxs-lookup"><span data-stu-id="93dbb-110">The following example launches Notepad and gets input from a text File that the user creates:</span></span>

```powershell
function PSConsoleHostReadLine
{
  $inputFile = Join-Path $env:TEMP PSConsoleHostReadLine
  Set-Content $inputFile "PS > "

  # Notepad opens. Enter your command in it, save the file, and then exit.
  notepad $inputFile | Out-Null
  $userInput = Get-Content $inputFile
  $resultingCommand = $userInput.Replace("PS >", "")
  $resultingCommand
}
```

### <a name="remarks"></a><span data-ttu-id="93dbb-111">COMENTÁRIOS</span><span class="sxs-lookup"><span data-stu-id="93dbb-111">REMARKS</span></span>

<span data-ttu-id="93dbb-112">Por padrão, o PowerShell lê a entrada do console no que é conhecido como "modo cooked", no qual o subsistema do console do Windows lida com todos os menus de pressionamentos, F7 e outras entradas.</span><span class="sxs-lookup"><span data-stu-id="93dbb-112">By default, PowerShell reads input from the console in what is known as "Cooked Mode" -- in which the Windows console subsystem handles all the keypresses, F7 menus, and other input.</span></span> <span data-ttu-id="93dbb-113">Quando você pressiona ENTER ou Tab, o PowerShell Obtém o texto que você digitou até esse ponto.</span><span class="sxs-lookup"><span data-stu-id="93dbb-113">When you press Enter or Tab, PowerShell gets the text that you have typed up to that point.</span></span> <span data-ttu-id="93dbb-114">Não há como saber que você pressionou CTRL-R, CTRL-A, CTRL-E ou qualquer outra tecla antes de pressionar Enter ou Tab. No Windows PowerShell 3,0, a função PSConsoleHostReadLine resolve esse problema.</span><span class="sxs-lookup"><span data-stu-id="93dbb-114">There is no way for it to know that you pressed Ctrl-R, Ctrl-A, Ctrl-E, or any other keys before pressing Enter or Tab. In Windows PowerShell 3.0, the PSConsoleHostReadLine function solves this issue.</span></span> <span data-ttu-id="93dbb-115">Quando você define uma função chamada PSConsoleHostReadline no host do console do PowerShell, o PowerShell chama essa função em vez do mecanismo de entrada "cooked Mode".</span><span class="sxs-lookup"><span data-stu-id="93dbb-115">When you define a function named PSConsoleHostReadline in the PowerShell console host, PowerShell calls that function instead of the "Cooked Mode" input mechanism.</span></span>

### <a name="see-also"></a><span data-ttu-id="93dbb-116">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="93dbb-116">SEE ALSO</span></span>

[<span data-ttu-id="93dbb-117">about_Prompts</span><span class="sxs-lookup"><span data-stu-id="93dbb-117">about_Prompts</span></span>](about_Prompts.md)
