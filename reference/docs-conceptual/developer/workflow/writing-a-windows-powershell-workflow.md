---
title: Escrevendo um fluxo de trabalho do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2551ceed-836f-4275-9fc0-ea68446d6a35
caps.latest.revision: 7
ms.openlocfilehash: 4f0be193fb5b5c753d040a48e5f49235ece11708
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366005"
---
# <a name="writing-a-windows-powershell-workflow"></a><span data-ttu-id="0caf9-102">Escrevendo um Fluxo de Trabalho do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0caf9-102">Writing a Windows PowerShell Workflow</span></span>

<span data-ttu-id="0caf9-103">Você pode criar um fluxo de trabalho XAML adicionando atividades expostas por assemblies do Windows PowerShell ao designer de fluxo de trabalho no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0caf9-103">You can create a XAML workflow by adding activities exposed by Windows PowerShell assemblies to the Workflow designer in Visual Studio.</span></span> <span data-ttu-id="0caf9-104">Os assemblies do Windows PowerShell a seguir expõem atividades habilitadas para fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0caf9-104">The following Windows PowerShell assemblies expose workflow-enabled activities.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0caf9-105">Um fluxo de trabalho XAML deve ser empacotado como um módulo se você quiser fornecer ajuda para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0caf9-105">A XAML workflow must be packaged as a module if you want to provide help for the workflow.</span></span> <span data-ttu-id="0caf9-106">Para obter informações sobre módulos, consulte [escrevendo um módulo do Windows PowerShell](../module/writing-a-windows-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="0caf9-106">For information about modules, see [Writing a Windows PowerShell Module](../module/writing-a-windows-powershell-module.md).</span></span>

- [<span data-ttu-id="0caf9-107">Microsoft. PowerShell. Activities</span><span class="sxs-lookup"><span data-stu-id="0caf9-107">Microsoft.Powershell.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Activities)

- [<span data-ttu-id="0caf9-108">Microsoft. PowerShell. Core. Activities</span><span class="sxs-lookup"><span data-stu-id="0caf9-108">Microsoft.Powershell.Core.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Core.Activities)

- [<span data-ttu-id="0caf9-109">Microsoft. PowerShell. Diagnostics. Activities</span><span class="sxs-lookup"><span data-stu-id="0caf9-109">Microsoft.Powershell.Diagnostics.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Diagnostics.Activities)

- [<span data-ttu-id="0caf9-110">Microsoft. PowerShell. Management. Activities</span><span class="sxs-lookup"><span data-stu-id="0caf9-110">Microsoft.Powershell.Management.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Management.Activities)

- [<span data-ttu-id="0caf9-111">Microsoft. PowerShell. Security. Activities</span><span class="sxs-lookup"><span data-stu-id="0caf9-111">Microsoft.Powershell.Security.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Security.Activities)

- [<span data-ttu-id="0caf9-112">Microsoft. PowerShell. Utility. Activities</span><span class="sxs-lookup"><span data-stu-id="0caf9-112">Microsoft.Powershell.Utility.Activities</span></span>](/dotnet/api/Microsoft.PowerShell.Utility.Activities)

  <span data-ttu-id="0caf9-113">Os tópicos a seguir descrevem como criar um fluxo de trabalho usando atividades do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0caf9-113">The following topics describe how to create a Workflow by using Windows PowerShell activities.</span></span>

- [<span data-ttu-id="0caf9-114">Adicionando atividades do Windows PowerShell à caixa de ferramentas do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0caf9-114">Adding Windows PowerShell Activities to the Visual Studio Toolbox</span></span>](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md)

- [<span data-ttu-id="0caf9-115">Criando um fluxo de trabalho com atividades do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0caf9-115">Creating a Workflow with Windows PowerShell Activities</span></span>](./creating-a-workflow-with-windows-powershell-activities.md)

- [<span data-ttu-id="0caf9-116">Criando um fluxo de trabalho usando um script do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0caf9-116">Creating a Workflow by Using a Windows PowerShell Script</span></span>](./creating-a-workflow-by-using-a-windows-powershell-script.md)

- [<span data-ttu-id="0caf9-117">Importando e invocando um fluxo de trabalho do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0caf9-117">Importing and Invoking a Windows PowerShell Workflow</span></span>](./importing-and-invoking-a-windows-powershell-workflow.md)

- [<span data-ttu-id="0caf9-118">Criando uma atividade de fluxo de trabalho a partir de um cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0caf9-118">Creating a Workflow Activity from a Windows PowerShell Cmdlet</span></span>](./creating-a-workflow-activity-from-a-windows-powershell-cmdlet.md)