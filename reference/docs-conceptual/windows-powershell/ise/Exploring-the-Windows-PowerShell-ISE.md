---
ms.date: 01/02/2020
title: Explorando o ISE do Windows PowerShell
description: Este artigo é uma visão geral dos recursos do ISE do Windows PowerShell
ms.topic: landing-page
ms.custom: ISE-F1-page
ms.openlocfilehash: 4ef3f471f11c2f1de818491a193fcf34201cb04a
ms.sourcegitcommit: 109ff625773389be56e98e994b7e56146f2b9d93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "93296362"
---
# <a name="exploring-the-windows-powershell-ise"></a>Explorando o ISE do Windows PowerShell

Você pode usar o ISE (Ambiente de Script Integrado) do Windows PowerShell para criar, executar e depurar scripts e comandos. O ISE do Windows PowerShell é composto por uma barra de menus, guias do Windows PowerShell, a barra de ferramentas, guias de script, um Painel de Script, um Painel Console, uma barra de status, um controle deslizante de tamanho de texto e a Ajuda contextual.

## <a name="menu-bar"></a>Barra de menu

A barra de menus contém os menus **Arquivo** , **Editar** , **Exibir** , **Ferramentas** , **Depurar** , **Complementos** e **Ajuda**. Os botões nos menus permitem executar tarefas relacionadas à escrita e execução de scripts e execução de comandos no ISE do Windows PowerShell. Além disso, é possível colocar uma [ferramenta complementar](object-model/The-ISEAddOnTool-Object.md) na barra de menus executando os scripts que usam a [hierarquia de modelo de objeto do ISE](object-model/The-ISE-Object-Model-Hierarchy.md).

## <a name="windows-powershell-tabs"></a>Guias do Windows PowerShell

Uma guia do Windows PowerShell é o ambiente em que um script do Windows PowerShell é executado. Você pode abrir novas guias do Windows PowerShell no ISE do Windows PowerShell para criar ambientes separados em seu computador local ou em computadores remotos. Você pode ter um máximo de oito guias do PowerShell abertas simultaneamente.

Para mais informações, confira [Como criar uma guia do PowerShell no ISE do Windows PowerShell](How-to-Create-a-PowerShell-Tab-in-Windows-PowerShell-ISE.md).

## <a name="toolbar"></a>Barra de ferramentas

Os seguintes botões estão localizados na barra de ferramentas.

|             Botão             |                                                                                     Função                                                                                     |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Novo**                        | Abre um novo script.                                                                                                                                                              |
| **Abrir**                       | Abre um arquivo ou um script existente.                                                                                                                                                |
| **Salvar**                       | Salva um script ou um arquivo.                                                                                                                                                          |
| **Recortar**                        | Recorta o texto selecionado e o copia para a área de transferência.                                                                                                                           |
| **Copy**                       | Copia o texto selecionado para a área de transferência.                                                                                                                                       |
| **Colar**                      | Cola o conteúdo da área de transferência na posição do cursor.                                                                                                                     |
| **Limpar Painel de Saída**          | Limpa todo o conteúdo no Painel de Saída.                                                                                                                                           |
| **Desfazer**                       | Reverte a ação que acabou de ser executada.                                                                                                                                     |
| **Refazer**                       | Realiza a ação que acabou de ser desfeita.                                                                                                                                        |
| **Executar Script**                 | Executa um script.                                                                                                                                                                   |
| **Executar seleção**              | Executa uma parte selecionada de um script.                                                                                                                                             |
| **Parar execução**             | Interrompe um script que está em execução.                                                                                                                                                  |
| **Nova Guia do PowerShell Remota**  | Cria uma nova Guia do PowerShell que estabelece uma sessão em um computador remoto. Uma caixa de diálogo é exibida e solicita que você insira os detalhes necessários para estabelecer a conexão remota. |
| **Inicia o PowerShell.exe**       | Abre o Console do Windows PowerShell.                                                                                                                                                      |
| **Mostrar o Painel de Script Acima**       | Move o Painel de Script para cima na exibição.                                                                                                                                 |
| **Mostrar o Painel de Script à Direita**     | Move o Painel de Script para a direita na exibição.                                                                                                                               |
| **Mostrar o Painel de Script Maximizado** | Maximiza o Painel de Script.                                                                                                                                                       |

## <a name="script-tab"></a>Guia de Script

Exibe o nome do script que você está editando. Você pode clicar em uma guia de script para selecionar o script que deseja editar.

Ao apontar para a guia do script, o caminho totalmente qualificado para o arquivo de script é exibido em uma dica de ferramenta.

## <a name="script-pane"></a>Painel de Script

Permite criar e executar scripts. Você pode abrir, editar e executar scripts existentes no Painel de Script. Para mais informações, confira [Como gravar e executar scripts no ISE do Windows PowerShell](How-to-Write-and-Run-Scripts-in-the-Windows-PowerShell-ISE.md).

## <a name="console-pane"></a>Painel de Console

Exibe os resultados dos comandos e scripts executados por você. Você pode executar comandos no Painel de Console. Você também pode copiar e limpar o conteúdo do Painel de Console.

Para obter mais informações, confira os seguintes artigos:

- [Como usar o Painel de Console com o ISE do Windows PowerShell](How-to-Use-the-Console-Pane-in-the-Windows-PowerShell-ISE.md)
- [Como depurar scripts no ISE do Windows PowerShell](How-to-Debug-Scripts-in-Windows-PowerShell-ISE.md)
- [Como usar o preenchimento com Tab no Painel de Script e no Painel de Console](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md)

## <a name="status-bar"></a>Barra de Status

Permite que você veja se os comandos e scripts que você executou foram concluídos. A barra de status localiza-se na parte mais inferior da tela. Partes selecionadas de mensagens de erro são exibidas na barra de status.

## <a name="text-size-slider"></a>Controle deslizante de tamanho de texto

Aumenta ou diminui o tamanho do texto na tela.

## <a name="help"></a>Ajuda

A Ajuda para o ISE do Windows PowerShell está disponível na Web na Biblioteca do TechNet. Você pode abrir a Ajuda clicando em **Ajuda do ISE do Windows PowerShell** no menu **Ajuda** ou pressionando a tecla <kbd>F1</kbd> em qualquer lugar, exceto quando o cursor estiver em um nome de cmdlet no Painel de Script ou no Painel de Console. No menu **Ajuda** , você também pode executar o cmdlet `Update-Help` e exibir a janela Comando, que auxilia na construção de comandos mostrando todos os parâmetros para um cmdlet e permitindo preencher os parâmetros em um formulário de fácil utilização.

## <a name="see-also"></a>Consulte Também

- [Apresentando o ISE do Windows PowerShell](Introducing-the-Windows-PowerShell-ISE.md)
- [Como usar perfis no ISE do Windows PowerShell](How-to-Use-Profiles-in-Windows-PowerShell-ISE.md)
- [Acessibilidade no ISE do Windows PowerShell](Accessibility-in-Windows-PowerShell-ISE.md)
- [Atalhos do teclado para o ISE do Windows PowerShell](Keyboard-Shortcuts-for-the-Windows-PowerShell-ISE.md)
