---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
title: Fluxo de informações
ms.openlocfilehash: c54603cf0dd4f0b69f8147620130f9f29bc3e5ec
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855741"
---
# <a name="information-stream"></a>Fluxo de informações

O PowerShell 5.0 adiciona um novo fluxo de **Information** estruturado para transmitir dados estruturados entre um script e seu host. `Write-Host` também foi atualizado para emitir sua saída para o fluxo **Information**, onde é possível capturá-lo ou silenciá-lo. O novo cmdlet `Write-Information` usado com os parâmetros comuns **InformationVariable** e **InformationAction** permite mais flexibilidade e capacidade.

A função a seguir usa os cmdlets que se aproveitam do novo fluxo **Information**.

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

Os exemplos a seguir mostram os resultados da execução dessa função.

```powershell
$r = c:\temp\OutputGusher
```

```Output
Preparing to give you output!
=============================
I <3 Output
=============================

SCRIPT COMPLETE!!
```

A variável `$r` captura as informações do processo na variável de script `$p`.

```powershell
$r.Id
4008
```

Ao contrário do cmdlet `Write-Host`, usar o parâmetro **InformationVariable** de `Write-Information` possibilita capturar a saída em uma variável. Usando a **Tag**, é possível criar canais separados para mensagens enviadas para o fluxo **Information**.

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

Ao enviar uma mensagem para o fluxo **Information** com uma marca, essa mensagem não é exibida no aplicativo host, mas pode ser recuperada usando o nome da marca. Por exemplo:

```powershell
$iv | where Tags -eq 'LogHigh'
```

```Output
Some important logging information
```