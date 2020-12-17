---
ms.date: 01/02/2020
title: Atalhos do teclado para o ISE do Windows PowerShell
description: Este artigo é uma lista dos atalhos de teclado usados no ISE do PowerShell.
ms.openlocfilehash: d4e78c5e8e8e172ef3cdd30b0099d56ce6b6b01e
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391197"
---
# <a name="keyboard-shortcuts-for-the-windows-powershell-ise"></a>Atalhos do teclado para o ISE do Windows PowerShell

Use os atalhos de teclado a seguir para executar ações no ISE (Ambiente de Script Integrado) do Windows PowerShell&reg;. O ISE do Windows PowerShell está disponível como parte dos sistemas operacionais cliente Windows Server e Windows, mas também pode ser instalado em alguns sistemas operacionais Windows mais antigos como parte do [pacote de download do Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkID=293881).

## <a name="keyboard-shortcuts-for-editing-text"></a>Atalhos de teclado para edição de texto

Você pode usar os seguintes atalhos de teclado ao editar texto.

|              Ação              |       Atalhos do teclado       |                                                                                                                                                 Usar em                                                                                                                                                 |
| -------------------------------- | ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Ajuda**                         | <kbd>F1</kbd>                  | Painel de Script **Importante:** Você pode especificar que a ajuda com <kbd>F1</kbd> venha de docs.microsoft.com ou da Ajuda baixada (confira `Update-Help`). Para escolher, clique em **Ferramentas**, **Opções** e, na guia **Configurações Gerais**, defina ou apague **Usar conteúdo da ajuda local em vez do conteúdo online.** |
| **Copy**                         | <kbd>CTRL</kbd>+<kbd>C</kbd>   | Painel de Script, Painel de Comando e Painel de Saída                                                                                                                                                                                                                                                                 |
| **Recortar**                          | <kbd>CTRL</kbd>+<kbd>X</kbd>   | Painel de Script, Painel de Comando                                                                                                                                                                                                                                                                              |
| **Expandir ou Recolher a Estrutura de Tópicos** | <kbd>CTRL</kbd>+<kbd>M</kbd>   | Painel de Script                                                                                                                                                                                                                                                                                            |
| **Localizar no script**               | <kbd>CTRL</kbd>+<kbd>F</kbd>   | Painel de Script                                                                                                                                                                                                                                                                                            |
| **Localizar próximo no script**          | <kbd>F3</kbd>                  | Painel de Script                                                                                                                                                                                                                                                                                            |
| **Localizar anterior no script**      | <kbd>SHIFT</kbd>+<kbd>F3</kbd> | Painel de Script                                                                                                                                                                                                                                                                                            |
| **Localizar Chave Correspondente**          | <kbd>CTRL</kbd>+<kbd>]</kbd>   | Painel de Script                                                                                                                                                                                                                                                                                            |
| **Colar**                        | <kbd>CTRL</kbd>+<kbd>V</kbd>   | Painel de Script, Painel de Comando                                                                                                                                                                                                                                                                              |
| **Refazer**                         | <kbd>CTRL</kbd>+<kbd>Y</kbd>   | Painel de Script, Painel de Comando                                                                                                                                                                                                                                                                              |
| **Substituir no script**            | <kbd>CTRL</kbd>+<kbd>H</kbd>   | Painel de Script                                                                                                                                                                                                                                                                                            |
| **Salvar**                         | <kbd>CTRL</kbd>+<kbd>S</kbd>   | Painel de Script                                                                                                                                                                                                                                                                                            |
| **Selecionar tudo**                   | <kbd>CTRL</kbd>+<kbd>A</kbd>   | Painel de Script, Painel de Comando e Painel de Saída                                                                                                                                                                                                                                                                 |
| **Mostrar Snippets**                | <kbd>CTRL</kbd>+<kbd>J</kbd>   | Painel de Script, Painel de Comando                                                                                                                                                                                                                                                                              |
| **Desfazer**                         | <kbd>CTRL</kbd>+<kbd>Z</kbd>   | Painel de Script, Painel de Comando                                                                                                                                                                                                                                                                              |

## <a name="keyboard-shortcuts-for-running-scripts"></a>Atalhos de teclado para execução de scripts

Você pode usar os seguintes atalhos de teclado ao executar scripts no Painel de Script.

|            Ação            |                                                                                                             Atalho do Teclado                                                                                                             |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Novo**                      | <kbd>CTRL</kbd>+<kbd>N</kbd>                                                                                                                                                                                                              |
| **Abrir**                     | <kbd>CTRL</kbd>+<kbd>O</kbd>                                                                                                                                                                                                              |
| **Executar**                      | <kbd>F5</kbd>                                                                                                                                                                                                                             |
| **Executar seleção**            | <kbd>F8</kbd>                                                                                                                                                                                                                             |
| **Parar execução**           | <kbd>CTRL</kbd>+<kbd>BREAK</kbd>. <kbd>CTRL</kbd>+<kbd>C</kbd> pode ser usado quando o contexto é ambíguo (quando não há textos selecionados).                                                                                              |
| **Tab** (para o próximo script)     | <kbd>CTRL</kbd>+<kbd>TAB</kbd> **Observação:** usar Tab para o próximo script funciona apenas quando você tem uma única guia do Windows PowerShell aberta, ou quando tem mais de uma guia do Windows PowerShell aberta, mas com o destaque no Painel de Script.               |
| **Tab** (para o script anterior) | <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>TAB</kbd> **Observação:** usar Tab para o script anterior funciona apenas quando você tem uma única guia do Windows PowerShell aberta, ou quando tem mais de uma guia do Windows PowerShell aberta, mas com o destaque no Painel de Script. |

## <a name="keyboard-shortcuts-for-customizing-the-view"></a>Atalhos de teclado para personalizar a exibição

Você pode usar os seguintes atalhos de teclado para personalizar a exibição no ISE do Windows PowerShell. Eles são acessíveis de todos os painéis no aplicativo.

|                        Ação                         |               Atalho do Teclado               |
| ----------------------------------------------------- | --------------------------------------------- |
| **Ir para Painel de Comando (v2) ou do Console (v3 e posterior)** | <kbd>CTRL</kbd>+<kbd>D</kbd>                  |
| **Ir para o Painel de Saída (apenas v2)**                       | <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>O</kbd> |
| **Ir para o Painel de script**                                 | <kbd>CTRL</kbd>+<kbd>I</kbd>                  |
| **Mostrar Painel de script**                                  | <kbd>CTRL</kbd>+<kbd>R</kbd>                  |
| **Ocultar Painel de script**                                  | <kbd>CTRL</kbd>+<kbd>R</kbd>                  |
| **Mover o Painel de script para cima**                               | <kbd>CTRL</kbd>+<kbd>1</kbd>                  |
| **Mover o Painel de script para a direita**                            | <kbd>CTRL</kbd>+<kbd>2</kbd>                  |
| **Maximizar o Painel de script**                              | <kbd>CTRL</kbd>+<kbd>3</kbd>                  |
| **Ampliar**                                           | <kbd>CTRL</kbd>+<kbd>+</kbd>                  |
| **Reduzir**                                          | <kbd>CTRL</kbd>+<kbd>-</kbd>                  |

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
> Você também pode usar os atalhos de teclado projetados para o console do Windows PowerShell ao depurar scripts no ISE do Windows PowerShell. Para usar esses atalhos, você deve digitar o atalho no Painel de Comando e pressionar <kbd>ENTER</kbd>.

|                        Ação                        | Atalho do Teclado |                Usar em                 |
| ---------------------------------------------------- | ----------------- | ------------------------------------- |
| **Continuar**                                         | `C`               | Painel de Console ao depurar um script |
| **Intervir**                                        | `S`               | Painel de Console ao depurar um script |
| **Contornar**                                        | `V`               | Painel de Console ao depurar um script |
| **Sair**                                         | `O`               | Painel de Console ao depurar um script |
| **Repetir Último Comando** (para Intervir ou Contornar) | <kbd>ENTER</kbd>  | Painel de Console ao depurar um script |
| **Exibir pilha de chamadas**                               | `K`               | Painel de Console ao depurar um script |
| **Parar depuração**                                   | `Q`               | Painel de Console ao depurar um script |
| **Listar o script**                                  | `L`               | Painel de Console ao depurar um script |
| **Exibir comandos de depuração do console**               | `H` ou `?`        | Painel de Console ao depurar um script |

## <a name="keyboard-shortcuts-for-windows-powershell-tabs"></a>Atalhos do teclado para as guias do Windows PowerShell

Você pode usar os seguintes atalhos do teclado ao utilizar as guias do Windows PowerShell.

|             Ação              |                                                        Atalho do Teclado                                                        |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| **Fechar a guia do PowerShell**        | <kbd>CTRL</kbd>+<kbd>W</kbd>                                                                                                    |
| **Nova guia do PowerShell**          | <kbd>CTRL</kbd>+<kbd>T</kbd>                                                                                                    |
| **Guia anterior do PowerShell**     | <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>TAB</kbd>. Este atalho funciona somente quando nenhum arquivo estiver aberto em qualquer uma das guias do Windows PowerShell. |
| **Próxima guia do Windows PowerShell** | <kbd>CTRL</kbd>+<kbd>TAB</kbd>. Este atalho funciona somente quando nenhum arquivo estiver aberto em qualquer uma das guias do Windows PowerShell.                  |

## <a name="keyboard-shortcuts-for-starting-and-exiting"></a>Atalhos de teclado para iniciar e sair

Você pode usar os seguintes atalhos de teclado para iniciar o console do Windows PowerShell (PowerShell.exe) ou para sair do ISE do Windows PowerShell.

|                        Ação                        |               Atalho do Teclado               |
| ---------------------------------------------------- | --------------------------------------------- |
| **Sair**                                             | <kbd>ALT</kbd>+<kbd>F4</kbd>                  |
| **Iniciar o PowerShell.exe**(console do Windows PowerShell) | <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> |

## <a name="see-also"></a>Consulte Também

- [PowerShell Magazine: a lista completa de atalhos de teclado para ISE do Windows PowerShell](https://www.powershellmagazine.com/2013/01/29/the-complete-list-of-powershell-ise-3-0-keyboard-shortcuts/)
