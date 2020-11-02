---
ms.date: 01/02/2020
title: Como usar o Painel de Console com o ISE do Windows PowerShell
description: Como usar o Painel de Console com o ISE do Windows PowerShell
ms.openlocfilehash: 7f6d3f5a3e4e596beb0d5c0bc395e3e7bf39906d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663659"
---
# <a name="how-to-use-the-console-pane-in-the-windows-powershell-ise"></a>Como usar o Painel de Console com o ISE do Windows PowerShell

O Painel de Console no ISE (Ambiente de Script Integrado) do Windows PowerShell funciona exatamente como a janela de console autônoma do ISE do Windows PowerShell.

Para executar um comando no Painel de Console, digite um comando e pressione <kbd>ENTER</kbd>. Para inserir vários comandos que você deseja executar em sequência, digite <kbd>SHIFT</kbd>+<kbd>ENTER</kbd> entre os comandos. Consulte [Como usar o preenchimento com Tab no Painel de Script e no Painel de Console](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md) para ver a ajuda para digitar os comandos.

Para interromper um comando, na barra de ferramentas, clique em **Parar Operação** ou pressione <kbd>CTRL</kbd>+<kbd>BREAK</kbd>. Você também poderá usar <kbd>CTRL</kbd>+<kbd>C</kbd> para interromper um comando se o contexto não for ambíguo. Por exemplo, se algum texto tiver sido marcado no Painel atual, <kbd>CTRL</kbd>+<kbd>C</kbd> será mapeado para a operação de cópia.

No Windows PowerShell v3 o Painel de Saída foi combinado com o Painel de Console. Isso traz o benefício de se comportar como console autônomo do Windows PowerShell e elimina as diferenças nos procedimentos que eram necessários quando eles eram separados. Você pode:

- Selecione e copie o texto do Painel de console para a Área de transferência para colá-lo em qualquer outra janela. Para selecionar o texto, clique e mantenha o mouse pressionado no painel de saída enquanto arrasta o mouse sobre o texto que você deseja capturar. Você também pode usar as teclas de seta enquanto mantém <kbd>Shift</kbd> pressionado para selecionar o texto. Pressione <kbd>CTRL</kbd>+<kbd>C</kbd> ou clique no ícone **Copiar** na barra de ferramentas.

- Cole o texto selecionado na posição atual do cursor. Clique no ícone **Colar** na barra de ferramentas.

- Limpe todo o texto no Painel de console. Para limpar o painel de Console, você pode clicar no ícone **Limpar Painel de Console** na barra de ferramentas ou executar o comando `Clear-Host` ou seu alias `cls`.

## <a name="see-also"></a>Consulte Também

- [Apresentando o ISE do Windows PowerShell](Introducing-the-Windows-PowerShell-ISE.md)
