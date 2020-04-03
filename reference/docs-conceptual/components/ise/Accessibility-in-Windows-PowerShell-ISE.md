---
ms.date: 12/19/2019
keywords: powershell, cmdlet
title: Acessibilidade no ISE do Windows PowerShell
ms.openlocfilehash: 89eff839d69fdbd5a1fa48b61dab627ef83f751b
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500956"
---
# <a name="accessibility-in-windows-powershell-ise"></a>Acessibilidade no ISE do Windows PowerShell

Este tópico descreve os recursos de acessibilidade do ISE (Ambiente de Script Integrado) do Windows PowerShell que podem ser úteis.

- [Como alterar o tamanho e o local dos Painéis de console e de script](#how-to-change-the-size-and-location-of-the-console-and-script-panes)
- [Atalhos de teclado para edição de texto](#keyboard-shortcuts-for-editing-text)
- [Atalhos de teclado para execução de scripts](#keyboard-shortcuts-for-running-scripts)
- [Atalhos de teclado para personalizar a exibição](#keyboard-shortcuts-for-customizing-the-view)
- [Atalhos de teclado para depuração de scripts](#keyboard-shortcuts-for-debugging-scripts)
- [Atalhos do teclado para as guias do Windows PowerShell](#keyboard-shortcuts-for-windows-powershell-tabs)
- [Atalhos de teclado para iniciar e sair](#keyboard-shortcuts-for-starting-and-exiting)
- [Gerenciamento do ponto de interrupção com cmdlets](#breakpoint-management)

A Microsoft tem o compromisso de facilitar o uso de seus produtos e serviços para todos. Os tópicos a seguir fornecem informações sobre os recursos, produtos e serviços que tornam o ISE do Windows PowerShell mais acessível para pessoas portadoras de deficiência.

Além dos recursos de acessibilidade e utilitários no Microsoft Windows, os seguintes recursos tornam o ISE do Windows PowerShell mais acessível a pessoas com deficiências:

- Atalhos do teclado

- Tabela de cores de sintaxe e a capacidade de modificar várias outras configurações de cor usando o objeto de script [$psISE.Options](object-model/The-ISEOptions-Object.md).

- Alteração do tamanho do texto

## <a name="how-to-change-the-size-and-location-of-the-console-and-script-panes"></a>Como alterar o tamanho e o local dos Painéis de Console e de Script

Você pode usar as etapas a seguir para alterar o tamanho e o local do Painel de Console e do Painel de Script. Quando você abrir o ISE do Windows PowerShell novamente, as alterações de tamanho e localização feitas serão mantidas.

### <a name="to-resize-the-script-pane-and-console-pane"></a>Para redimensionar o Painel de Script e o Painel de Console

1. Coloque o ponteiro na linha de divisão entre o Painel de Script e o Painel de Console.

2. Quando o ponteiro do mouse mudar para uma seta dupla, arraste a borda para alterar o tamanho do painel.

### <a name="to-move-the-script-pane-and-console-pane"></a>Para mover o Painel de Script e o Painel de Console

Realize um dos seguintes procedimentos:

- Para mover o Painel de Script acima do Painel de Console, pressione <kbd>CTRL</kbd>+<kbd>1</kbd> ou, na barra de ferramentas, clique no ícone **Mostrar Painel de Script Acima** ou então, no menu **Exibir**, clique em **Mostrar Painel de Script Acima**.

- Para mover o Painel de Script para a direita do Painel de Console, pressione <kbd>CTRL</kbd>+<kbd>2</kbd> ou, na barra de ferramentas, clique no ícone **Mostrar Painel de Script à Direita** ou então, no menu **Exibir**, clique em **Mostrar Painel de Script à Direita**.

- Para maximizar o Painel de Script, pressione <kbd>CTRL</kbd>+<kbd>3</kbd> ou, na barra de ferramentas, clique no ícone **Mostrar Painel de Script Maximizado** ou então, no menu **Exibir**, clique em **Mostrar Painel de Script Maximizado**.

- Para maximizar o Painel de Console e ocultar o Painel de Script, na extrema borda direita da linha de guias, clique no ícone **Ocultar Painel de Script**, no menu **Exibir**, clique para desmarcar a opção de menu **Mostrar Painel de Script**.

- Para exibir o Painel de Script quando o Painel de Console está maximizado, na extrema borda direita da linha de guias, clique no ícone **Ocultar Painel de Script** ou então, no menu **Exibir**, clique para marcar a opção de menu **Mostrar Painel de Script**.

## <a name="keyboard-shortcuts-for-editing-text"></a>Atalhos de teclado para edição de texto

Você pode usar os seguintes atalhos de teclado ao editar texto.

|           Ação            |       Atalhos do teclado       |          Usar em           |
| --------------------------- | ------------------------------ | ------------------------- |
| **Copy**                    | <kbd>CTRL</kbd>+<kbd>C</kbd>   | Painel de script, o painel de console |
| **Recortar**                     | <kbd>CTRL</kbd>+<kbd>X</kbd>   | Painel de script, o painel de console |
| **Localizar no script**          | <kbd>CTRL</kbd>+<kbd>F</kbd>   | Painel de Script               |
| **Localizar próximo no script**     | <kbd>F3</kbd>                  | Painel de Script               |
| **Localizar anterior no script** | <kbd>SHIFT</kbd>+<kbd>F3</kbd> | Painel de Script               |
| **Colar**                   | <kbd>CTRL</kbd>+<kbd>V</kbd>   | Painel de script, o painel de console |
| **Refazer**                    | <kbd>CTRL</kbd>+<kbd>Y</kbd>   | Painel de script, o painel de console |
| **Substituir no script**       | <kbd>CTRL</kbd>+<kbd>H</kbd>   | Painel de Script               |
| **Salvar**                    | <kbd>CTRL</kbd>+<kbd>S</kbd>   | Painel de Script               |
| **Selecionar tudo**              | <kbd>CTRL</kbd>+<kbd>A</kbd>   | Painel de script, o painel de console |
| **Desfazer**                    | <kbd>CTRL</kbd>+<kbd>Z</kbd>   | Painel de script, o painel de console |

## <a name="keyboard-shortcuts-for-running-scripts"></a>Atalhos de teclado para execução de scripts

Você pode usar os seguintes atalhos de teclado ao executar scripts no Painel de Script.

|            Ação            |                                                                                                     Atalho do Teclado                                                                                                      |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Novo**                      | <kbd>CTRL</kbd>+<kbd>N</kbd>                                                                                                                                                                                               |
| **Abrir**                     | <kbd>CTRL</kbd>+<kbd>O</kbd>                                                                                                                                                                                               |
| **Executar**                      | <kbd>F5</kbd>                                                                                                                                                                                                              |
| **Executar seleção**            | <kbd>F8</kbd>                                                                                                                                                                                                              |
| **Parar execução**           | <kbd>CTRL</kbd>+<kbd>BREAK</kbd>. <kbd>CTRL</kbd>+<kbd>C</kbd> pode ser usado quando o contexto é ambíguo (quando não há textos selecionados).                                                                               |
| **Tab** (para o próximo script)     | <kbd>CTRL</kbd>+<kbd>TAB</kbd> **Observação:** usar Tab para ir para o próximo script só funciona quando você tem uma única guia do PowerShell aberta ou quando tem mais de uma guia do PowerShell aberta, mas o destaque está no painel Script.                |
| **Tab** (para o script anterior) | <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>TAB</kbd> **Observação:** usar Tab para ir para o script anterior só funciona quando você tem uma única guia do PowerShell aberta ou se tem mais de uma guia do PowerShell aberta, mas o destaque está no painel Script. |

## <a name="keyboard-shortcuts-for-customizing-the-view"></a>Atalhos de teclado para personalizar a exibição

Você pode usar os seguintes atalhos de teclado para personalizar a exibição no ISE do Windows PowerShell. Eles são acessíveis de todos os painéis no aplicativo.

|           Ação           |         Atalho do Teclado        |
| -------------------------- | -------------------------------- |
| **Ir para o Painel de console**     | <kbd>CTRL</kbd>+<kbd>D</kbd>     |
| **Ir para o Painel de script**      | <kbd>CTRL</kbd>+<kbd>I</kbd>     |
| **Mostrar Painel de script**       | <kbd>CTRL</kbd>+<kbd>R</kbd>     |
| **Ocultar Painel de script**       | <kbd>CTRL</kbd>+<kbd>R</kbd>     |
| **Mover o Painel de script para cima**    | <kbd>CTRL</kbd>+<kbd>1</kbd>     |
| **Mover o Painel de script para a direita** | <kbd>CTRL</kbd>+<kbd>2</kbd>     |
| **Maximizar o Painel de script**   | <kbd>CTRL</kbd>+<kbd>3</kbd>     |
| **Ampliar**                | <kbd>CTRL</kbd>+<kbd>SINAL DE MAIS</kbd>  |
| **Reduzir**               | <kbd>CTRL</kbd>+<kbd>SINAL DE MENOS</kbd> |

## <a name="keyboard-shortcuts-for-debugging-scripts"></a>Atalhos de teclado para depuração de scripts

Você pode usar os seguintes atalhos do teclado ao depurar scripts.

|           Ação           |               Atalho do Teclado                |                Usar em                |
| -------------------------- | ---------------------------------------------- | ------------------------------------ |
| **Executar/continuar**           | <kbd>F5</kbd>                                  | Painel de Script ao depurar um script |
| **Intervir**              | <kbd>F11</kbd>                                 | Painel de Script ao depurar um script |
| **Contornar**              | <kbd>F10</kbd>                                 | Painel de Script ao depurar um script |
| **Sair**               | <kbd>SHIFT</kbd>+<kbd>F11</kbd>                | Painel de Script ao depurar um script |
| **Exibir pilha de chamadas**     | <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>  | Painel de Script ao depurar um script |
| **Listar pontos de interrupção**       | <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>L</kbd>  | Painel de Script ao depurar um script |
| **Alternar ponto de interrupção**      | <kbd>F9</kbd>                                  | Painel de Script ao depurar um script |
| **Remover todos os pontos de interrupção** | <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>F9</kbd> | Painel de Script ao depurar um script |
| **Parar depurador**          | <kbd>SHIFT</kbd>+<kbd>F5</kbd>                 | Painel de Script ao depurar um script |

> [!NOTE]
> Você também pode usar os atalhos de teclado projetados para o console do Windows PowerShell ao depurar scripts no ISE do Windows PowerShell. Para usar esses atalhos, você deve digitar o atalho no Painel de Console e pressionar <kbd>ENTER</kbd>.

|                 Ação                  |      Atalho do Teclado       |                Usar em                 |
| --------------------------------------- | ---------------------------- | ------------------------------------- |
| **Continuar**                            | <kbd>C</kbd>                 | Painel de Console ao depurar um script |
| **Intervir**                           | <kbd>S</kbd>                 | Painel de Console ao depurar um script |
| **Contornar**                           | <kbd>V</kbd>                 | Painel de Console ao depurar um script |
| **Sair**                            | <kbd>O</kbd>                 | Painel de Console ao depurar um script |
| **Repetir Último Comando** (Intervir/Contornar) | <kbd>ENTER</kbd>             | Painel de Console ao depurar um script |
| **Exibir pilha de chamadas**                  | <kbd>K</kbd>                 | Painel de Console ao depurar um script |
| **Parar depuração**                      | <kbd>Q</kbd>                 | Painel de Console ao depurar um script |
| **Listar o script**                     | <kbd>L</kbd>                 | Painel de Console ao depurar um script |
| **Exibir comandos de depuração do console**  | <kbd>H</kbd> ou <kbd>?</kbd> | Painel de Console ao depurar um script |

## <a name="keyboard-shortcuts-for-windows-powershell-tabs"></a>Atalhos do teclado para as guias do Windows PowerShell

Você pode usar os seguintes atalhos do teclado ao utilizar as guias do Windows PowerShell.

|             Ação              |                                 Atalho do Teclado                                  |
| ------------------------------- | ---------------------------------------------------------------------------------- |
| **Fechar a guia do PowerShell**        | <kbd>CTRL</kbd>+<kbd>W</kbd>                                                       |
| **Nova guia do PowerShell**          | <kbd>CTRL</kbd>+<kbd>T</kbd>                                                       |
| **Guia anterior do PowerShell**     | <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>TAB</kbd> (Somente quando nenhum arquivo estiver aberto em nenhuma das guias do PowerShell) |
| **Próxima guia do Windows PowerShell** | <kbd>CTRL</kbd>+<kbd>TAB</kbd> (Somente quando nenhum arquivo estiver aberto em nenhuma das guias do PowerShell) |

## <a name="keyboard-shortcuts-for-starting-and-exiting"></a>Atalhos de teclado para iniciar e sair

Você pode usar os seguintes atalhos de teclado para iniciar o console do Windows PowerShell (**PowerShell.exe**) ou para sair do ISE do Windows PowerShell.

|                        Ação                         |               Atalho do Teclado               |
| ----------------------------------------------------- | --------------------------------------------- |
| **Sair**                                              | <kbd>ALT</kbd>+<kbd>F4</kbd>                  |
| **Iniciar o PowerShell.exe** (console do Windows PowerShell) | <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> |

## <a name="breakpoint-management"></a>Gerenciamento do ponto de interrupção

Para os deficientes visuais, informações de ponto de interrupção estão disponíveis por meio dos cmdlets para gerenciar pontos de interrupção, como [Get-PSBreakpoint](/powershell/module/Microsoft.PowerShell.Utility/Get-PSBreakpoint) e [Set-PSBreakpoint](/powershell/module/Microsoft.PowerShell.Utility/Set-PSBreakpoint). Para saber mais, veja "Como gerenciar pontos de interrupção" em [Como depurar scripts no ISE do Windows PowerShell](How-to-Debug-Scripts-in-Windows-PowerShell-ISE.md).

## <a name="see-also"></a>Consulte Também

[Apresentando o ISE do Windows PowerShell](Introducing-the-Windows-PowerShell-ISE.md)
