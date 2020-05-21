---
title: Criando um fluxo de trabalho com atividades do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb55971a-4ea4-4c51-aeff-4e0bb05a51b2
caps.latest.revision: 6
ms.openlocfilehash: 12b0b246b78142f3811f9f566cd94e4dabd40cc9
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557458"
---
# <a name="creating-a-workflow-with-windows-powershell-activities"></a><span data-ttu-id="b92a0-102">Criar um fluxo de trabalho com atividades do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b92a0-102">Creating a Workflow with Windows PowerShell Activities</span></span>

<span data-ttu-id="b92a0-103">Você pode criar um fluxo de trabalho do Windows PowerShell selecionando atividades na caixa de ferramentas do Visual Studio e arrastando-as para a janela Designer de Fluxo de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="b92a0-103">You can create a Windows PowerShell workflow by selecting activities from the Visual Studio Toolbox and dragging them to the Workflow Designer window.</span></span> <span data-ttu-id="b92a0-104">Para obter informações sobre como adicionar atividades do Windows PowerShell à caixa de ferramentas do Visual Studio, consulte [adicionando atividades do Windows PowerShell à caixa de ferramentas do Visual Studio](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md).</span><span class="sxs-lookup"><span data-stu-id="b92a0-104">For information about adding Windows PowerShell activities to the Visual Studio Toolbox, see [Adding Windows PowerShell Activities to the Visual Studio Toolbox](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md).</span></span>

<span data-ttu-id="b92a0-105">Os procedimentos a seguir descrevem como criar um fluxo de trabalho que verifica o status de domínio de um grupo de computadores especificados pelo usuário, une-os a um domínio se eles ainda não estiverem associados e, em seguida, verifica o status novamente.</span><span class="sxs-lookup"><span data-stu-id="b92a0-105">The following procedures describe how to create a workflow that checks the domain status of a group of user-specified computers, joins them to a domain if they are not already joined, and then checks the status again.</span></span>

### <a name="setting-up-the-project"></a><span data-ttu-id="b92a0-106">Configurando o projeto</span><span class="sxs-lookup"><span data-stu-id="b92a0-106">Setting up the Project</span></span>

1. <span data-ttu-id="b92a0-107">Siga o procedimento em [adicionando atividades do Windows PowerShell à caixa de ferramentas do Visual Studio](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md) para criar um projeto de fluxo de trabalho e adicionar as atividades dos assemblies [Microsoft. PowerShell. Activities](/dotnet/api/Microsoft.PowerShell.Activities) e [Microsoft. PowerShell. Management. Activities](/dotnet/api/Microsoft.PowerShell.Management.Activities) à caixa de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="b92a0-107">Follow the procedure in [Adding Windows PowerShell Activities to the Visual Studio Toolbox](./adding-windows-powershell-activities-to-the-visual-studio-toolbox.md) to create a workflow project and add the activities from the [Microsoft.Powershell.Activities](/dotnet/api/Microsoft.PowerShell.Activities) and [Microsoft.Powershell.Management.Activities](/dotnet/api/Microsoft.PowerShell.Management.Activities) assemblies to the toolbox.</span></span>

2. <span data-ttu-id="b92a0-108">Adicione o System. Management. Automation, o Microsoft. PowerShell. Activities, o System. Management, o Microsoft. PowerShell. Management. Activities e o Microsoft. PowerShell. Commands. Management como no projeto como assemblies de referência.</span><span class="sxs-lookup"><span data-stu-id="b92a0-108">Add System.Management.Automation, Microsoft.PowerShell.Activities, System.Management, Microsoft.PowerShell.Management.Activities, and Microsoft.PowerShell.Commands.Management as to the project as reference assemblies.</span></span>

### <a name="adding-activities-to-the-workflow"></a><span data-ttu-id="b92a0-109">Adicionando atividades ao fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="b92a0-109">Adding Activities to the Workflow</span></span>

1. <span data-ttu-id="b92a0-110">Adicione uma atividade de **sequência** ao fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b92a0-110">Add a **Sequence** activity to the workflow.</span></span>

2. <span data-ttu-id="b92a0-111">Crie um argumento chamado `ComputerName` com um tipo de argumento de `String[]` .</span><span class="sxs-lookup"><span data-stu-id="b92a0-111">Create an argument named `ComputerName` with an argument type of `String[]`.</span></span> <span data-ttu-id="b92a0-112">Esse argumento representa os nomes dos computadores a serem verificados e Unidos.</span><span class="sxs-lookup"><span data-stu-id="b92a0-112">This argument represents the names of the computers to check and join.</span></span>

3. <span data-ttu-id="b92a0-113">Crie um argumento chamado `DomainCred` de tipo [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential).</span><span class="sxs-lookup"><span data-stu-id="b92a0-113">Create an argument named `DomainCred` of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential).</span></span> <span data-ttu-id="b92a0-114">Esse argumento representa as credenciais de domínio de uma conta de domínio que está autorizada a ingressar um computador no domínio.</span><span class="sxs-lookup"><span data-stu-id="b92a0-114">This argument represents the domain credentials of a domain account that is authorized to join a computer to the domain.</span></span>

4. <span data-ttu-id="b92a0-115">Crie um argumento chamado `MachineCred` de tipo [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential).</span><span class="sxs-lookup"><span data-stu-id="b92a0-115">Create an argument named `MachineCred` of type [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential).</span></span> <span data-ttu-id="b92a0-116">Esse argumento representa as credenciais de um administrador nos computadores para verificar e ingressar.</span><span class="sxs-lookup"><span data-stu-id="b92a0-116">This argument represents the credentials of an administrator on the computers to check and join.</span></span>

5. <span data-ttu-id="b92a0-117">Adicione uma atividade **ParallelForEach** dentro da atividade **Sequence** .</span><span class="sxs-lookup"><span data-stu-id="b92a0-117">Add a **ParallelForEach** activity inside the **Sequence** activity.</span></span> <span data-ttu-id="b92a0-118">Insira `comp` e `ComputerName` nas caixas de texto para que o loop itere pelos elementos da `ComputerName` matriz.</span><span class="sxs-lookup"><span data-stu-id="b92a0-118">Enter `comp` and `ComputerName` in the text boxes so that the loop iterates through the elements of the `ComputerName` array.</span></span>

6. <span data-ttu-id="b92a0-119">Adicione uma atividade **Sequence** ao corpo da atividade **ParallelForEach** .</span><span class="sxs-lookup"><span data-stu-id="b92a0-119">Add a **Sequence** activity to the body of the **ParallelForEach** activity.</span></span> <span data-ttu-id="b92a0-120">Defina a propriedade **DisplayName** da sequência como `JoinDomain` .</span><span class="sxs-lookup"><span data-stu-id="b92a0-120">Set the **DisplayName** property of the sequence to `JoinDomain`.</span></span>

7. <span data-ttu-id="b92a0-121">Adicione uma atividade **getwmiobject** à sequência **JoinDomain** .</span><span class="sxs-lookup"><span data-stu-id="b92a0-121">Add a **GetWmiObject** activity to the **JoinDomain** sequence.</span></span>

8. <span data-ttu-id="b92a0-122">Edite as propriedades da atividade **Getwmiobject** da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="b92a0-122">Edit the properties of the **GetWmiObject** activity as follows.</span></span>

   |<span data-ttu-id="b92a0-123">Propriedade</span><span class="sxs-lookup"><span data-stu-id="b92a0-123">Property</span></span>|<span data-ttu-id="b92a0-124">Valor</span><span class="sxs-lookup"><span data-stu-id="b92a0-124">Value</span></span>|
   |--------------|-----------|
   |<span data-ttu-id="b92a0-125">**Classe**</span><span class="sxs-lookup"><span data-stu-id="b92a0-125">**Class**</span></span>|<span data-ttu-id="b92a0-126">"Win32_ComputerSystem"</span><span class="sxs-lookup"><span data-stu-id="b92a0-126">"Win32_ComputerSystem"</span></span>|
   |<span data-ttu-id="b92a0-127">**PSComputerName**</span><span class="sxs-lookup"><span data-stu-id="b92a0-127">**PSComputerName**</span></span>|<span data-ttu-id="b92a0-128">às</span><span class="sxs-lookup"><span data-stu-id="b92a0-128">{comp}</span></span>|
   |<span data-ttu-id="b92a0-129">**PSCredential**</span><span class="sxs-lookup"><span data-stu-id="b92a0-129">**PSCredential**</span></span>|<span data-ttu-id="b92a0-130">MachineCred</span><span class="sxs-lookup"><span data-stu-id="b92a0-130">MachineCred</span></span>|

9. <span data-ttu-id="b92a0-131">Adicione uma atividade **addcomputer** à sequência **JoinDomain** após a atividade **getwmiobject** .</span><span class="sxs-lookup"><span data-stu-id="b92a0-131">Add an **AddComputer** activity to the **JoinDomain** sequence after the **GetWmiObject** activity.</span></span>

10. <span data-ttu-id="b92a0-132">Edite as propriedades da atividade **Addcomputer** da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="b92a0-132">Edit the properties of the **AddComputer** activity as follows.</span></span>

    |<span data-ttu-id="b92a0-133">Propriedade</span><span class="sxs-lookup"><span data-stu-id="b92a0-133">Property</span></span>|<span data-ttu-id="b92a0-134">Valor</span><span class="sxs-lookup"><span data-stu-id="b92a0-134">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="b92a0-135">**ComputerName**</span><span class="sxs-lookup"><span data-stu-id="b92a0-135">**ComputerName**</span></span>|<span data-ttu-id="b92a0-136">às</span><span class="sxs-lookup"><span data-stu-id="b92a0-136">{comp}</span></span>|
    |<span data-ttu-id="b92a0-137">**DomainCredential**</span><span class="sxs-lookup"><span data-stu-id="b92a0-137">**DomainCredential**</span></span>|<span data-ttu-id="b92a0-138">DomainCred</span><span class="sxs-lookup"><span data-stu-id="b92a0-138">DomainCred</span></span>|

11. <span data-ttu-id="b92a0-139">Adicione uma atividade **RestartComputer** à sequência **JoinDomain** após a atividade **addcomputer** .</span><span class="sxs-lookup"><span data-stu-id="b92a0-139">Add a **RestartComputer** activity to the **JoinDomain** sequence after the **AddComputer** activity.</span></span>

12. <span data-ttu-id="b92a0-140">Edite as propriedades da atividade **RestartComputer** da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="b92a0-140">Edit the properties of the **RestartComputer** activity as follows.</span></span>

    |<span data-ttu-id="b92a0-141">Propriedade</span><span class="sxs-lookup"><span data-stu-id="b92a0-141">Property</span></span>|<span data-ttu-id="b92a0-142">Valor</span><span class="sxs-lookup"><span data-stu-id="b92a0-142">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="b92a0-143">**ComputerName**</span><span class="sxs-lookup"><span data-stu-id="b92a0-143">**ComputerName**</span></span>|<span data-ttu-id="b92a0-144">às</span><span class="sxs-lookup"><span data-stu-id="b92a0-144">{comp}</span></span>|
    |<span data-ttu-id="b92a0-145">**Provedores**</span><span class="sxs-lookup"><span data-stu-id="b92a0-145">**Credential**</span></span>|<span data-ttu-id="b92a0-146">MachineCred</span><span class="sxs-lookup"><span data-stu-id="b92a0-146">MachineCred</span></span>|
    |<span data-ttu-id="b92a0-147">**Fins**</span><span class="sxs-lookup"><span data-stu-id="b92a0-147">**For**</span></span>|<span data-ttu-id="b92a0-148">Microsoft. PowerShell. Commands. WaitForServiceTypes. PowerShell</span><span class="sxs-lookup"><span data-stu-id="b92a0-148">Microsoft.PowerShell.Commands.WaitForServiceTypes.PowerShell</span></span>|
    |<span data-ttu-id="b92a0-149">**Aplicação**</span><span class="sxs-lookup"><span data-stu-id="b92a0-149">**Force**</span></span>|<span data-ttu-id="b92a0-150">True</span><span class="sxs-lookup"><span data-stu-id="b92a0-150">True</span></span>|
    |<span data-ttu-id="b92a0-151">Aguarde</span><span class="sxs-lookup"><span data-stu-id="b92a0-151">Wait</span></span>|<span data-ttu-id="b92a0-152">True</span><span class="sxs-lookup"><span data-stu-id="b92a0-152">True</span></span>|
    |<span data-ttu-id="b92a0-153">PSComputerName</span><span class="sxs-lookup"><span data-stu-id="b92a0-153">PSComputerName</span></span>|<span data-ttu-id="b92a0-154">{""}</span><span class="sxs-lookup"><span data-stu-id="b92a0-154">{""}</span></span>|

13. <span data-ttu-id="b92a0-155">Adicione uma atividade **getwmiobject** à sequência **JoinDomain** após a atividade **RestartComputer** .</span><span class="sxs-lookup"><span data-stu-id="b92a0-155">Add a **GetWmiObject** activity to the **JoinDomain** sequence after the **RestartComputer** activity.</span></span> <span data-ttu-id="b92a0-156">Edite suas propriedades para que sejam iguais à atividade **getwmiobject** anterior.</span><span class="sxs-lookup"><span data-stu-id="b92a0-156">Edit its properties to be the same as the previous **GetWmiObject** activity.</span></span>

    <span data-ttu-id="b92a0-157">Quando você tiver concluído os procedimentos, a janela de design do fluxo de trabalho deverá ser parecida com esta.</span><span class="sxs-lookup"><span data-stu-id="b92a0-157">When you have finished the procedures, the workflow design window should look like this.</span></span>

    <span data-ttu-id="b92a0-158">![JoinDomain XAML no designer de fluxo de trabalho ](media/creating-a-workflow-with-windows-powershell-activities/joindomainworkflow.png)
     ![JoinDomain XAML no designer de fluxo de trabalho](media/creating-a-workflow-with-windows-powershell-activities/joindomainworkflow.png "JoinDomainWorkflow")</span><span class="sxs-lookup"><span data-stu-id="b92a0-158">![JoinDomain XAML in Workflow designer](media/creating-a-workflow-with-windows-powershell-activities/joindomainworkflow.png)
![JoinDomain XAML in Workflow designer](media/creating-a-workflow-with-windows-powershell-activities/joindomainworkflow.png "JoinDomainWorkflow")</span></span>
