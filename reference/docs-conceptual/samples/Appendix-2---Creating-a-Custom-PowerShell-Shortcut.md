---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Apêndice 2 Criar um atalho do PowerShell personalizado
description: O procedimento a seguir descreve como criar um atalho para o Windows PowerShell que tem várias opções convenientes personalizadas.
ms.openlocfilehash: abdab517dec1357050bf431b6f2e35311ad49976
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500718"
---
# <a name="appendix-2---creating-a-custom-powershell-shortcut"></a>Apêndice 2: Criar um atalho do PowerShell personalizado

O procedimento a seguir descreve como criar um atalho para o Windows PowerShell que tem várias opções convenientes personalizadas.

1. Crie um atalho que aponta para Powershell.exe.

1. Clique com o botão direito do mouse no atalho e clique em **Propriedades** .

1. Clique na guia **Opções** .

1. Na seção **Editar Opções** , selecione a caixa de seleção **Edição Rápida** .

    Essa configuração permite selecionar o texto na janela do console do Windows PowerShell, arrastar o botão esquerdo do mouse e copiar texto para a área de transferência pressionando Enter ou clicando com o botão direito do mouse.

1. Na seção **Editar Opções** , selecione a caixa de seleção **Modo Inserir** . Essa configuração permite clicar com o botão direito do mouse na janela do console para colar o texto da área de transferência automaticamente.

1. Na seção **Histórico de Comandos** , digite ou selecione um número entre 1 e 999 na caixa **Tamanho do Buffer** . Isso define o número de comandos digitados que serão mantidas no buffer do console.

1. Na seção **Histórico de Comandos** , marque a caixa de seleção **Descartar Duplicatas Antigas** para eliminar comandos repetidos do console do buffer.

1. Clique na guia **Layout** .

1. Na seção **Buffer da Tela** , digite um número entre 1 e 9999 na caixa **Altura** . A altura representa o número de linhas de saída que são armazenados no buffer. Este é o número máximo de linhas mantido para exibição ao rolar a janela do console. Se este número for menor do que a altura mostrada na seção **Tamanho da Janela** , a altura do tamanho da janela será automaticamente reduzida com o mesmo valor.

1. Na seção **Tamanho da Janela** , digite um número entre 1 e 9999 para a largura. Isso representa o número de caracteres que são exibidas na janela do console. A largura padrão é 80 e a formatação de saída do Windows PowerShell foi projetada para essa largura.

1. Se você quiser colocar o console em um ponto específico na área de trabalho quando ele for aberto, desmarque a caixa de seleção **Permitir que o sistema posicione a janela** na seção **Posição da janela** e altere os valores nas caixas **Esquerda** e **Superior** na seção **Posição da janela** .

1. Clique em **OK** .
