---
ms.date: 06/12/2017
title: Melhorias do Console no WMF 5.1
description: O WMF 5.1 adiciona novos recursos à experiência do console para o Windows PowerShell 5.1.
ms.openlocfilehash: 9a86a2ed4787554e7255bedf1c2ae6e798fefa45
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660753"
---
# <a name="console-improvements-in-wmf-51"></a>Melhorias do Console no WMF 5.1

## <a name="powershell-console-improvements"></a>Melhorias do console do PowerShell

As seguintes alterações foram feitas ao powershell.exe no WMF 5.1 para melhorar a experiência do console:

### <a name="vt100-support"></a>Suporte a VT100

O Windows 10 adicionou suporte para [sequências de escape VT100](/windows/console/console-virtual-terminal-sequences).
PowerShell ignorará determinadas sequências de escape de formatação do VT100 ao calcular larguras da tabela.

O PowerShell também adicionou uma nova API que pode ser usada no código de formatação para determinar se há suporte para VT100. Por exemplo:

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

Aqui está um [exemplo](https://gist.github.com/lzybkr/dcb973dccd54900b67783c48083c28f7) completo que pode ser usado para realçar correspondências de `Select-String`. Salve o exemplo em um arquivo chamado `MatchInfo.format.ps1xml`, então, para usá-lo em seu perfil ou em outro local, execute `Update-FormatData -Prepend MatchInfo.format.ps1xml`.

As sequências de escape do VT100 têm suporte apenas a partir da Atualização de Aniversário do Windows 10.
Elas não têm suporte em sistemas anteriores.

### <a name="vi-mode-support-in-psreadline"></a>Suporte ao modo vi em PSReadline

[PSReadline](https://github.com/PowerShell/PSReadLine) adiciona suporte para o modo vi. Para usar o modo vi, execute `Set-PSReadlineOption -EditMode Vi`.

### <a name="redirected-stdin-with-interactive-input"></a>STDIN redirecionada com entrada interativa

Em versões anteriores, iniciar o PowerShell com `powershell -File -` era necessário quando stdin era redirecionado e você queria inserir comandos interativamente.

Com o WMF 5.1, essa opção difícil de descobrir não é mais necessária. Você pode iniciar o PowerShell sem nenhuma opção.

Observe que PSReadline não oferece suporte à STDIN redirecionada, e a experiência de edição de linha de comando interna com STDIN redirecionada é extremamente limitada, por exemplo, as teclas de direção não funcionam. Uma versão futura do PSReadline deve resolver esse problema.
