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
# <a name="appendix-2---creating-a-custom-powershell-shortcut"></a><span data-ttu-id="e5421-104">Apêndice 2: Criar um atalho do PowerShell personalizado</span><span class="sxs-lookup"><span data-stu-id="e5421-104">Appendix 2 - Creating a Custom PowerShell Shortcut</span></span>

<span data-ttu-id="e5421-105">O procedimento a seguir descreve como criar um atalho para o Windows PowerShell que tem várias opções convenientes personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e5421-105">The following procedure describes how to create a shortcut to Windows PowerShell that has several convenient options customized.</span></span>

1. <span data-ttu-id="e5421-106">Crie um atalho que aponta para Powershell.exe.</span><span class="sxs-lookup"><span data-stu-id="e5421-106">Create a shortcut that points to Powershell.exe.</span></span>

1. <span data-ttu-id="e5421-107">Clique com o botão direito do mouse no atalho e clique em **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="e5421-107">Right-click the shortcut, and then click **Properties** .</span></span>

1. <span data-ttu-id="e5421-108">Clique na guia **Opções** .</span><span class="sxs-lookup"><span data-stu-id="e5421-108">Click the **Options** tab.</span></span>

1. <span data-ttu-id="e5421-109">Na seção **Editar Opções** , selecione a caixa de seleção **Edição Rápida** .</span><span class="sxs-lookup"><span data-stu-id="e5421-109">In the **Edit Options** section, select the **QuickEdit** check box.</span></span>

    <span data-ttu-id="e5421-110">Essa configuração permite selecionar o texto na janela do console do Windows PowerShell, arrastar o botão esquerdo do mouse e copiar texto para a área de transferência pressionando Enter ou clicando com o botão direito do mouse.</span><span class="sxs-lookup"><span data-stu-id="e5421-110">This setting lets you select text in the Windows PowerShell console window by dragging the left  mouse button, and it lets you copy text to the clipboard by pressing ENTER or by right-clicking  the mouse.</span></span>

1. <span data-ttu-id="e5421-111">Na seção **Editar Opções** , selecione a caixa de seleção **Modo Inserir** .</span><span class="sxs-lookup"><span data-stu-id="e5421-111">In the **Edit Options** section, select the **Insert Mode** check box.</span></span> <span data-ttu-id="e5421-112">Essa configuração permite clicar com o botão direito do mouse na janela do console para colar o texto da área de transferência automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e5421-112">This setting lets you right-click in the console window to automatically paste text from the clipboard.</span></span>

1. <span data-ttu-id="e5421-113">Na seção **Histórico de Comandos** , digite ou selecione um número entre 1 e 999 na caixa **Tamanho do Buffer** .</span><span class="sxs-lookup"><span data-stu-id="e5421-113">In the **Command History** section, type or select a number between 1 and 999 in the **Buffer Size** box.</span></span> <span data-ttu-id="e5421-114">Isso define o número de comandos digitados que serão mantidas no buffer do console.</span><span class="sxs-lookup"><span data-stu-id="e5421-114">This sets the number of typed commands that will be kept in the console buffer.</span></span>

1. <span data-ttu-id="e5421-115">Na seção **Histórico de Comandos** , marque a caixa de seleção **Descartar Duplicatas Antigas** para eliminar comandos repetidos do console do buffer.</span><span class="sxs-lookup"><span data-stu-id="e5421-115">In the **Command History** section, select the **Discard Old Duplicates** check box to eliminate repeated commands from the console buffer.</span></span>

1. <span data-ttu-id="e5421-116">Clique na guia **Layout** .</span><span class="sxs-lookup"><span data-stu-id="e5421-116">Click the **Layout** tab.</span></span>

1. <span data-ttu-id="e5421-117">Na seção **Buffer da Tela** , digite um número entre 1 e 9999 na caixa **Altura** .</span><span class="sxs-lookup"><span data-stu-id="e5421-117">In the **Screen Buffer** section, type a number between 1 and 9999 in the **Height** box.</span></span> <span data-ttu-id="e5421-118">A altura representa o número de linhas de saída que são armazenados no buffer.</span><span class="sxs-lookup"><span data-stu-id="e5421-118">The height represents the number of lines of output that are buffered.</span></span> <span data-ttu-id="e5421-119">Este é o número máximo de linhas mantido para exibição ao rolar a janela do console.</span><span class="sxs-lookup"><span data-stu-id="e5421-119">This is the maximum number of lines retained for viewing when you scroll through the console window.</span></span> <span data-ttu-id="e5421-120">Se este número for menor do que a altura mostrada na seção **Tamanho da Janela** , a altura do tamanho da janela será automaticamente reduzida com o mesmo valor.</span><span class="sxs-lookup"><span data-stu-id="e5421-120">If this number is lower than the height shown in the **Window size** section, the window size height will automatically be reduced to the same value.</span></span>

1. <span data-ttu-id="e5421-121">Na seção **Tamanho da Janela** , digite um número entre 1 e 9999 para a largura.</span><span class="sxs-lookup"><span data-stu-id="e5421-121">In the **Window Size** section, type a number between 1 and 9999 for the width.</span></span> <span data-ttu-id="e5421-122">Isso representa o número de caracteres que são exibidas na janela do console.</span><span class="sxs-lookup"><span data-stu-id="e5421-122">This represents the number of characters that are displayed across the console window.</span></span> <span data-ttu-id="e5421-123">A largura padrão é 80 e a formatação de saída do Windows PowerShell foi projetada para essa largura.</span><span class="sxs-lookup"><span data-stu-id="e5421-123">The default width is 80, and Windows PowerShell's output formatting is designed for this width.</span></span>

1. <span data-ttu-id="e5421-124">Se você quiser colocar o console em um ponto específico na área de trabalho quando ele for aberto, desmarque a caixa de seleção **Permitir que o sistema posicione a janela** na seção **Posição da janela** e altere os valores nas caixas **Esquerda** e **Superior** na seção **Posição da janela** .</span><span class="sxs-lookup"><span data-stu-id="e5421-124">If you want to place the console at a particular point on the desktop when it is opened, clear  the **Let system position window** check box in the **Window position** section, and then change  the values in the **Left** and **Top** boxes in the **Window position** section.</span></span>

1. <span data-ttu-id="e5421-125">Clique em **OK** .</span><span class="sxs-lookup"><span data-stu-id="e5421-125">Click **OK** .</span></span>
