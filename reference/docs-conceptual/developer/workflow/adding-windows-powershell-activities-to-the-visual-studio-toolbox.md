---
title: Adicionando atividades do Windows PowerShell à caixa de ferramentas do Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c8ef289-0659-42d1-9976-044b144201eb
caps.latest.revision: 6
ms.openlocfilehash: ecd23d3eb722137bdda0498fc71e0e966c57a589
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561182"
---
# <a name="adding-windows-powershell-activities-to-the-visual-studio-toolbox"></a><span data-ttu-id="e6ec3-102">Adicionar atividades do Windows PowerShell à caixa de ferramentas do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e6ec3-102">Adding Windows PowerShell Activities to the Visual Studio Toolbox</span></span>

<span data-ttu-id="e6ec3-103">Antes de criar um fluxo de trabalho do PowerShell usando Designer de Fluxo de Trabalho, você deve primeiro adicionar as atividades do PowerShell à caixa de ferramentas em um projeto de aplicativo do console de fluxo de trabalho do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e6ec3-103">Before you author a PowerShell Workflow using Workflow Designer, you must first add the PowerShell Activities to the Toolbox in a Visual Studio Workflow console application project.</span></span> <span data-ttu-id="e6ec3-104">O procedimento a seguir mostra como adicionar as atividades do assembly Microsoft. PowerShell. Core. Activities à caixa de ferramentas do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e6ec3-104">The following procedure shows how to add the activities from the Microsoft.PowerShell.Core.Activities assembly to the Visual Studio toolbox.</span></span>

### <a name="adding-windows-powershell-activities-to-the-toolbox"></a><span data-ttu-id="e6ec3-105">Adicionando atividades do Windows PowerShell à caixa de ferramentas</span><span class="sxs-lookup"><span data-stu-id="e6ec3-105">Adding Windows PowerShell Activities to the Toolbox</span></span>

1. <span data-ttu-id="e6ec3-106">Crie um novo projeto de aplicativo de console de fluxo de trabalho no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e6ec3-106">Create a new Workflow console application project in Visual Studio.</span></span>

2. <span data-ttu-id="e6ec3-107">No menu **Exibir** , clique em **Caixa de Ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="e6ec3-107">On the **View** menu, click **Toolbox**.</span></span>

3. <span data-ttu-id="e6ec3-108">Adicione uma nova guia na caixa de ferramentas clicando com o botão direito do mouse na caixa de ferramentas e clicando em **Adicionar guia**e dê à nova guia um nome como "atividades do PowerShell".</span><span class="sxs-lookup"><span data-stu-id="e6ec3-108">Add a new tab in the Toolbox by right-clicking inside the Toolbox and clicking **Add Tab**, and give the new tab a name such as "PowerShell Activities".</span></span>

   <span data-ttu-id="e6ec3-109">A adição de uma guia permite que você agrupe as atividades do PowerShell separadas de outras ferramentas na caixa de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="e6ec3-109">Adding a tab allows you to group the PowerShell Activities separate from other tools in the Toolbox.</span></span>

4. <span data-ttu-id="e6ec3-110">Na nova guia caixa de ferramentas, clique em **escolher itens...**. A caixa de diálogo **escolher itens da caixa de ferramentas** é exibida.</span><span class="sxs-lookup"><span data-stu-id="e6ec3-110">On the new Toolbox tab, click **Choose Items...**. The **Choose Toolbox Items** dialog appears.</span></span>

5. <span data-ttu-id="e6ec3-111">Na caixa de diálogo **escolher itens da caixa de ferramentas** , clique na guia **sistema. atividades** .</span><span class="sxs-lookup"><span data-stu-id="e6ec3-111">In the **Choose Toolbox Items** dialog, click the **System.Activities** tab.</span></span>

6. <span data-ttu-id="e6ec3-112">Clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="e6ec3-112">Click **Browse**.</span></span>

7. <span data-ttu-id="e6ec3-113">Navegue até a pasta%WINDIR%\Microsoft.NET\assembly\ GAC_MSIL \Microsoft.PowerShell.Core.Activities\v4.0_3.0.0.0__31bf3856ad364e e clique duas vezes em Microsoft. PowerShell. Core. Activities. dll.</span><span class="sxs-lookup"><span data-stu-id="e6ec3-113">Navigate to the %WINDIR%\Microsoft.NET\assembly\GAC_MSIL\Microsoft.PowerShell.Core.Activities\v4.0_3.0.0.0__31bf3856ad364e folder and double-click Microsoft.PowerShell.Core.Activities.dll.</span></span>

8. <span data-ttu-id="e6ec3-114">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6ec3-114">Click **OK**.</span></span> <span data-ttu-id="e6ec3-115">As atividades definidas pelo assembly Microsoft. PowerShell. Core. Activities agora estão disponíveis na caixa de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="e6ec3-115">The activities defined by the Microsoft.PowerShell.Core.Activities assembly are now available in the toolbox.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6ec3-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e6ec3-116">See Also</span></span>

[<span data-ttu-id="e6ec3-117">Escrevendo um Fluxo de Trabalho do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6ec3-117">Writing a Windows PowerShell Workflow</span></span>](./writing-a-windows-powershell-workflow.md)

[<span data-ttu-id="e6ec3-118">Criar um fluxo de trabalho com atividades do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6ec3-118">Creating a Workflow with Windows PowerShell Activities</span></span>](./creating-a-workflow-with-windows-powershell-activities.md)
