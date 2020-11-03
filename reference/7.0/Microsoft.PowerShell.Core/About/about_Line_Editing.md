---
description: Descreve como editar comandos no prompt de comando do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_line_editing?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Line_Editing
ms.openlocfilehash: d4b525e4c3f461b799c3bef157e04e0763a0b9c6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195885"
---
# <a name="about-line-editing"></a>Sobre edição de linha

## <a name="short-description"></a>Descrição breve

Descreve como editar comandos no prompt de comando do PowerShell.

## <a name="long-description"></a>Descrição longa

O console do PowerShell tem alguns atalhos de teclado úteis para ajudá-lo a editar comandos no prompt de comando do PowerShell.

### <a name="add-a-line"></a>Adicionar uma linha

Para adicionar uma linha, pressione <kbd>Shift</kbd> + <kbd>Enter</kbd>.

Você pode adicionar várias linhas. Cada linha adicional começa com `>>` , o prompt de continuação. Pressione <kbd>Enter</kbd> para executar o comando.

### <a name="move-left-and-right"></a>Mover para a esquerda e para a direita

Para mover o cursor um caractere para a esquerda, pressione a <kbd>seta</kbd>para a esquerda.

Para mover o cursor uma palavra para a esquerda, pressione <kbd>Ctrl</kbd> + <kbd>seta para a esquerda</kbd>.

Para mover o cursor um caractere para a direita, pressione a <kbd>seta</kbd>para a direita.

Para mover o cursor uma palavra para a direita, pressione <kbd>Ctrl</kbd> + <kbd>seta para a direita</kbd>.

### <a name="move-to-a-lines-beginning-or-end"></a>Mover para o início ou o fim de uma linha

Para mover para o início de uma linha, pressione <kbd>Home</kbd>.

Para mover para o final de uma linha, pressione <kbd>end</kbd>.

Se as linhas foram adicionadas, pressione <kbd>Home</kbd> ou <kbd>end</kbd> duas vezes para mover para o início ou fim das linhas.

### <a name="delete-characters"></a>Excluir caracteres

Para excluir o caractere por trás da posição do cursor, pressione <kbd>Backspace</kbd>.

Para excluir o caractere na posição do cursor, pressione <kbd>delete</kbd>.

### <a name="delete-characters-from-a-line"></a>Excluir caracteres de uma linha

Para excluir todos os caracteres da posição do cursor até o fim de uma linha, pressione <kbd>Ctrl</kbd> + <kbd>end</kbd>.

Para excluir todos os caracteres da posição do cursor para o início de uma linha, pressione <kbd>Ctrl</kbd> + <kbd>Home</kbd>.

Se linhas foram adicionadas, os caracteres são excluídos da linha atual e as linhas que foram adicionadas.

### <a name="insert-and-overstrike-mode"></a>Modo de inserção e sobreposição

Para alterar para o modo de substituição, pressione <kbd>Inserir</kbd>. Para retornar ao modo de inserção, pressione <kbd>Insert</kbd> novamente.

### <a name="tab-completion"></a>Preenchimento de guias

Para concluir um nome de cmdlet, um parâmetro ou um caminho, pressione a tecla <kbd>Tab</kbd> . Para percorrer uma lista de valores, pressione a tecla <kbd>Tab</kbd> novamente.

## <a name="see-also"></a>Confira também

[about_Command_Syntax](about_Command_Syntax.md)

[about_Path_Syntax](about_Path_Syntax.md)

[about_PSReadline](../../PSReadline/About/about_PSReadline.md)
