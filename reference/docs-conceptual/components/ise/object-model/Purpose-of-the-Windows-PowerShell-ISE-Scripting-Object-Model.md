---
ms.date: 12/31/2019
keywords: powershell, cmdlet
title: Objetivo do modelo de objeto de script do ISE do Windows PowerShell
ms.openlocfilehash: 1f48df112bd19297baa311116e79d3d7603d7c81
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736225"
---
# <a name="purpose-of-the-windows-powershell-ise-scripting-object-model"></a><span data-ttu-id="2e964-103">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e964-103">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>

<span data-ttu-id="2e964-104">Objetos são associados com a forma e a função do ISE (Ambiente de Script Integrado) do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e964-104">Objects are associated with the form and function of Windows PowerShell Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="2e964-105">A referência de modelo de objeto fornece detalhes sobre as propriedades e os métodos de membros que esses objetos expõem.</span><span class="sxs-lookup"><span data-stu-id="2e964-105">The object model reference provides details about the member properties and methods that these objects expose.</span></span> <span data-ttu-id="2e964-106">Exemplos são fornecidos para mostrar como você pode usar scripts para acessar diretamente esses métodos e propriedades.</span><span class="sxs-lookup"><span data-stu-id="2e964-106">Examples are provided to show how you can use scripts to directly access these methods and properties.</span></span> <span data-ttu-id="2e964-107">O modelo de objeto de script facilita a gama de tarefas a seguir.</span><span class="sxs-lookup"><span data-stu-id="2e964-107">The scripting object model makes the following range of tasks easier.</span></span>

## <a name="customizing-the-appearance-of-windows-powershell-ise"></a><span data-ttu-id="2e964-108">Personalizando a aparência do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e964-108">Customizing the appearance of Windows PowerShell ISE</span></span>

<span data-ttu-id="2e964-109">Você pode usar o modelo de objeto para modificar as configurações e opções do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2e964-109">You can use the object model to modify the application settings and options.</span></span> <span data-ttu-id="2e964-110">Por exemplo, você pode modificá-las da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="2e964-110">For example, you can modify them as follows:</span></span>

- <span data-ttu-id="2e964-111">Mudar a cor de erros, avisos, saídas detalhadas e saídas de depuração.</span><span class="sxs-lookup"><span data-stu-id="2e964-111">Change the color of errors, warnings, verbose outputs, and debug outputs.</span></span>
- <span data-ttu-id="2e964-112">Obter ou definir cores de tela de fundo para o painel de Comando, painel de Saída e o painel de Script.</span><span class="sxs-lookup"><span data-stu-id="2e964-112">Get or set the background colors for the Command pane, the Output pane, and the Script pane.</span></span>
- <span data-ttu-id="2e964-113">Definir a cor de primeiro plano para o painel de Saída.</span><span class="sxs-lookup"><span data-stu-id="2e964-113">Set the foreground color for the Output pane.</span></span>
- <span data-ttu-id="2e964-114">Definir o nome e tamanho da fonte para o ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e964-114">Set the font name and font size for Windows PowerShell ISE.</span></span>
- <span data-ttu-id="2e964-115">Configurar alertas.</span><span class="sxs-lookup"><span data-stu-id="2e964-115">Configure warnings.</span></span> <span data-ttu-id="2e964-116">Essa configuração inclui advertências que são emitidas quando um arquivo é aberto em várias guias do PowerShell ou quando um script no arquivo é executado antes que o arquivo seja salvo.</span><span class="sxs-lookup"><span data-stu-id="2e964-116">This setting includes warnings that are issued when a file is opened in multiple PowerShell tabs or when a script in the file is run before the file has been saved.</span></span>
- <span data-ttu-id="2e964-117">Alternar entre uma exibição em que o painel Script e Painel de saída estão lado em uma exibição em que o painel Script está na parte superior do Painel de saída.</span><span class="sxs-lookup"><span data-stu-id="2e964-117">Switch between a view where the Script pane and the Output pane are side-by-side and a view where the Script pane is on top of the Output pane.</span></span>
- <span data-ttu-id="2e964-118">Encaixar o painel de Comando na parte inferior ou superior do painel de Saída.</span><span class="sxs-lookup"><span data-stu-id="2e964-118">Dock the Command pane to the bottom or the top of the Output pane.</span></span>

## <a name="enhancing-the-functionality-of-windows-powershell-ise"></a><span data-ttu-id="2e964-119">Melhorando a funcionalidade do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e964-119">Enhancing the functionality of Windows PowerShell ISE</span></span>

<span data-ttu-id="2e964-120">Você pode usar o modelo de objeto para melhorar a funcionalidade do ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e964-120">You can use the object model to enhance the functionality of Windows PowerShell ISE.</span></span> <span data-ttu-id="2e964-121">Por exemplo, você pode:</span><span class="sxs-lookup"><span data-stu-id="2e964-121">For example, you can:</span></span>

- <span data-ttu-id="2e964-122">Adicionar e modificar a instância do próprio ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e964-122">Add and modify the instance of Windows PowerShell ISE itself.</span></span> <span data-ttu-id="2e964-123">Por exemplo, para alterar os menus, você pode adicionar novos itens de menu e mapear os novos itens de menu para os scripts.</span><span class="sxs-lookup"><span data-stu-id="2e964-123">For example, to change the menus, you can add new menu items and map the new menu items to scripts.</span></span>
- <span data-ttu-id="2e964-124">Crie scripts que realizam algumas das tarefas que podem ser executadas usando os comandos de menu e botões no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e964-124">Create scripts that perform some of the tasks that you can perform by using the menu commands and buttons in Windows PowerShell ISE.</span></span> <span data-ttu-id="2e964-125">Por exemplo, você pode adicionar, remover ou selecionar uma guia PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e964-125">For example, you can add, remove, or select a PowerShell tab.</span></span>
- <span data-ttu-id="2e964-126">Complemente tarefas que podem ser realizadas usando comandos e botões de menu.</span><span class="sxs-lookup"><span data-stu-id="2e964-126">Complement tasks that can be performed by using menu commands and buttons.</span></span> <span data-ttu-id="2e964-127">Por exemplo, você pode renomear uma guia do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e964-127">For example, you can rename a PowerShell tab.</span></span>
- <span data-ttu-id="2e964-128">Manipule buffers de texto para os painéis de Comando, Saída e Script associados a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2e964-128">Manipulate text buffers for the Command pane, the Output pane, and the Script pane that are associated with a file.</span></span> <span data-ttu-id="2e964-129">Por exemplo, você pode:</span><span class="sxs-lookup"><span data-stu-id="2e964-129">For example, you can:</span></span>
  - <span data-ttu-id="2e964-130">Obtenha ou defina todo o texto.</span><span class="sxs-lookup"><span data-stu-id="2e964-130">Get or set all text.</span></span>
  - <span data-ttu-id="2e964-131">Obtenha ou defina uma seleção de texto.</span><span class="sxs-lookup"><span data-stu-id="2e964-131">Get or set a text selection.</span></span>
  - <span data-ttu-id="2e964-132">Execute um script ou uma parte selecionada de um script.</span><span class="sxs-lookup"><span data-stu-id="2e964-132">Run a script or run a selected portion of a script.</span></span>
  - <span data-ttu-id="2e964-133">Role uma linha até uma exibição.</span><span class="sxs-lookup"><span data-stu-id="2e964-133">Scroll a line into view.</span></span>
  - <span data-ttu-id="2e964-134">Insira texto em uma posição de cursor.</span><span class="sxs-lookup"><span data-stu-id="2e964-134">Insert text at a caret position.</span></span>
  - <span data-ttu-id="2e964-135">Selecione um bloco de texto.</span><span class="sxs-lookup"><span data-stu-id="2e964-135">Select a block of text.</span></span>
  - <span data-ttu-id="2e964-136">Obtenha o último número de linha.</span><span class="sxs-lookup"><span data-stu-id="2e964-136">Get the last line number.</span></span>
- <span data-ttu-id="2e964-137">Execute operações de arquivo.</span><span class="sxs-lookup"><span data-stu-id="2e964-137">Perform file operations.</span></span> <span data-ttu-id="2e964-138">Por exemplo, você pode:</span><span class="sxs-lookup"><span data-stu-id="2e964-138">For example, you can:</span></span>
  - <span data-ttu-id="2e964-139">Abrir um arquivo, salvar um arquivo ou salvar um arquivo usando um nome diferente.</span><span class="sxs-lookup"><span data-stu-id="2e964-139">Open a file, save a file, or save a file by using a different name.</span></span>
  - <span data-ttu-id="2e964-140">Determine se um arquivo foi alterado depois que foi salvo pela última vez.</span><span class="sxs-lookup"><span data-stu-id="2e964-140">Determine whether a file has been changed after it was last saved.</span></span>
  - <span data-ttu-id="2e964-141">Obtenha o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="2e964-141">Get the file name.</span></span>
  - <span data-ttu-id="2e964-142">Selecione um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2e964-142">Select a file.</span></span>

## <a name="automating-tasks"></a><span data-ttu-id="2e964-143">Automatizando tarefas</span><span class="sxs-lookup"><span data-stu-id="2e964-143">Automating tasks</span></span>

<span data-ttu-id="2e964-144">Você pode usar o modelo de objeto de script para criar atalhos de teclado para operações frequentes.</span><span class="sxs-lookup"><span data-stu-id="2e964-144">You can use the scripting object model to create keyboard shortcuts for frequent operations.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e964-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="2e964-145">See also</span></span>

- [<span data-ttu-id="2e964-146">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="2e964-146">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
