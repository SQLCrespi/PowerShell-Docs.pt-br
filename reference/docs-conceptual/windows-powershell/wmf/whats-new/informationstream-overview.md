---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
title: Fluxo de informações
ms.openlocfilehash: 1a8df66f7489910b964ec398e90b76e9f30cd2e2
ms.sourcegitcommit: 87b9b989f261b52969e99159e99ee28ad8d8839a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86567834"
---
# <a name="information-stream"></a><span data-ttu-id="9f65b-103">Fluxo de informações</span><span class="sxs-lookup"><span data-stu-id="9f65b-103">Information Stream</span></span>

<span data-ttu-id="9f65b-104">O PowerShell 5.0 adiciona um novo fluxo de **Information** estruturado para transmitir dados estruturados entre um script e seu host.</span><span class="sxs-lookup"><span data-stu-id="9f65b-104">PowerShell 5.0 adds a new structured **Information** stream to transmit structured data between a script and its host.</span></span> <span data-ttu-id="9f65b-105">`Write-Host` também foi atualizado para emitir sua saída para o fluxo **Information**, onde é possível capturá-lo ou silenciá-lo.</span><span class="sxs-lookup"><span data-stu-id="9f65b-105">`Write-Host` has also been updated to emit its output to the **Information** stream where you can now capture or silence it.</span></span> <span data-ttu-id="9f65b-106">O novo cmdlet `Write-Information` usado com os parâmetros comuns **InformationVariable** e **InformationAction** permite mais flexibilidade e capacidade.</span><span class="sxs-lookup"><span data-stu-id="9f65b-106">The new `Write-Information` cmdlet used with **InformationVariable** and **InformationAction** common parameters enables more flexibility and capability.</span></span>

<span data-ttu-id="9f65b-107">A função a seguir usa os cmdlets que se aproveitam do novo fluxo **Information**.</span><span class="sxs-lookup"><span data-stu-id="9f65b-107">The following function uses cmdlets that take advantage of the new **Information** stream.</span></span>

```powershell
function OutputGusher {
  [CmdletBinding()]
  param()
  Write-Host -ForegroundColor Green 'Preparing to give you output!'
  Write-Host '============================='
  Write-Host 'I ' -ForegroundColor White -NoNewline
  Write-Host '<3 ' -ForegroundColor Red -NoNewline
  Write-Host 'Output' -ForegroundColor White
  Write-Host '============================='

  $p = Get-Process -id $pid
  $p

  Write-Information $p -Tag Process
  Write-Information 'Some spammy logging information' -Tag LogLow
  Write-Information 'Some important logging information' -Tag LogHigh

  Write-Host
  Write-Host -ForegroundColor Green 'SCRIPT COMPLETE!!'
}
```

<span data-ttu-id="9f65b-108">Os exemplos a seguir mostram os resultados da execução dessa função.</span><span class="sxs-lookup"><span data-stu-id="9f65b-108">The following examples show the results of running this function.</span></span>

```powershell
$r = OutputGusher
```

```Output
Preparing to give you output!
=============================
I <3 Output
=============================

SCRIPT COMPLETE!!
```

<span data-ttu-id="9f65b-109">A variável `$r` captura as informações do processo na variável de script `$p`.</span><span class="sxs-lookup"><span data-stu-id="9f65b-109">The `$r` variable has captured the process information in the script variable `$p`.</span></span>

```powershell
$r.Id
4008
```

<span data-ttu-id="9f65b-110">Ao contrário do cmdlet `Write-Host`, usar o parâmetro **InformationVariable** de `Write-Information` possibilita capturar a saída em uma variável.</span><span class="sxs-lookup"><span data-stu-id="9f65b-110">Unlike the `Write-Host` cmdlet, using the **InformationVariable** parameter of `Write-Information` allows you to capture the output in a variable.</span></span> <span data-ttu-id="9f65b-111">Usando a **Tag**, é possível criar canais separados para mensagens enviadas para o fluxo **Information**.</span><span class="sxs-lookup"><span data-stu-id="9f65b-111">Using the **Tag**, you can create separate channels for message sent to the **Information** stream.</span></span>

```powershell
$r = OutputGusher -InformationVariable iv
$ivOutput = $iv | Group-Object -AsHash { $_.Tags[0] } -AsString
$ivOutput
```

```Output
Preparing to give you output!
=============================
I <3 Output
=============================
SCRIPT COMPLETE!!

Name                 Value
----                 -----
LogLow               {Some spammy logging information}
LogHigh              {Some important logging information}
Process              {System.Diagnostics.Process (powershell)}
PSHOST               {Preparing to give you output!, =============================, I , <3 ...}
```

<span data-ttu-id="9f65b-112">Ao enviar uma mensagem para o fluxo **Information** com uma marca, essa mensagem não é exibida no aplicativo host, mas pode ser recuperada usando o nome da marca.</span><span class="sxs-lookup"><span data-stu-id="9f65b-112">When you send a message to the **Information** stream with a tag, that message is not displayed in the host application but can be retrieved using the tag name.</span></span> <span data-ttu-id="9f65b-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9f65b-113">For example:</span></span>

```powershell
$iv | where Tags -eq 'LogHigh'
```

```Output
Some important logging information
```
