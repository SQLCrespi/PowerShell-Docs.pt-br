---
description: Explica como criar uma personalização de como o PowerShell lê a entrada no prompt do console.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_psconsolehostreadline?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSConsoleHostReadLine
ms.openlocfilehash: 49c3ce4099109fc721a13b61f390f564b8893a25
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196246"
---
# <a name="about_psconsolehostreadline"></a>about_PSConsoleHostReadLine

## <a name="short-description"></a>DESCRIÇÃO BREVE
Explica como criar uma personalização de como o PowerShell lê a entrada no prompt do console.

## <a name="long-description"></a>DESCRIÇÃO LONGA

A partir do Windows PowerShell 3,0, você pode escrever uma função chamada PSConsoleHostReadLine que substitui a forma padrão pela qual a entrada do console é processada.

### <a name="examples"></a>EXEMPLOS

O exemplo a seguir inicia o bloco de notas e obtém a entrada de um arquivo de texto que o usuário cria:

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

### <a name="remarks"></a>COMENTÁRIOS

Por padrão, o PowerShell lê a entrada do console no que é conhecido como "modo cooked", no qual o subsistema do console do Windows lida com todos os menus de pressionamentos, F7 e outras entradas. Quando você pressiona ENTER ou Tab, o PowerShell Obtém o texto que você digitou até esse ponto. Não há como saber que você pressionou CTRL-R, CTRL-A, CTRL-E ou qualquer outra tecla antes de pressionar Enter ou Tab. No Windows PowerShell 3,0, a função PSConsoleHostReadLine resolve esse problema. Quando você define uma função chamada PSConsoleHostReadline no host do console do PowerShell, o PowerShell chama essa função em vez do mecanismo de entrada "cooked Mode".

### <a name="see-also"></a>CONSULTE TAMBÉM

[about_Prompts](about_Prompts.md)
