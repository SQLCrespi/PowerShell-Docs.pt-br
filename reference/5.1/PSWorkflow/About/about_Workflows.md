---
description: Fornece uma breve introdução ao recurso de fluxo de trabalho do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_workflows?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Workflows
ms.openlocfilehash: fbd8ee62b1e9c6969d489c5024c33f5cca883dc6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195796"
---
# <a name="about-workflows"></a><span data-ttu-id="679c0-104">Sobre fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="679c0-104">About Workflows</span></span>

## <a name="short-description"></a><span data-ttu-id="679c0-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="679c0-105">Short description</span></span>

<span data-ttu-id="679c0-106">Fornece uma breve introdução ao recurso de fluxo de trabalho do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="679c0-106">Provides a brief introduction to the PowerShell Workflow feature.</span></span>

## <a name="long-description"></a><span data-ttu-id="679c0-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="679c0-107">Long description</span></span>

<span data-ttu-id="679c0-108">O fluxo de trabalho do PowerShell traz os benefícios do [Windows Workflow Foundation](/dotnet/framework/windows-workflow-foundation) para o PowerShell e permite que você escreva e execute fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="679c0-108">PowerShell Workflow brings the benefits of the [Windows Workflow Foundation](/dotnet/framework/windows-workflow-foundation) to PowerShell and enables you to write and run workflows.</span></span>

<span data-ttu-id="679c0-109">O fluxo de trabalho do PowerShell foi introduzido no PowerShell 3,0 e o módulo está disponível até o PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="679c0-109">PowerShell Workflow was introduced in PowerShell 3.0 and the module is available up to PowerShell 5.1.</span></span> <span data-ttu-id="679c0-110">Para obter mais informações sobre o fluxo de trabalho do PowerShell, consulte o [Guia de fluxos de trabalho](/previous-versions/powershell/scripting/components/workflows-guide) e [gravando um fluxo de trabalho do Windows PowerShell](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow).</span><span class="sxs-lookup"><span data-stu-id="679c0-110">For more information about PowerShell Workflow, see the [Workflows Guide](/previous-versions/powershell/scripting/components/workflows-guide) and [Writing a Windows PowerShell Workflow](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow).</span></span>

## <a name="about-workflows"></a><span data-ttu-id="679c0-111">Sobre fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="679c0-111">About workflows</span></span>

<span data-ttu-id="679c0-112">Os fluxos de trabalho são comandos que consistem em uma sequência ordenada de atividades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="679c0-112">Workflows are commands that consist of an ordered sequence of related activities.</span></span> <span data-ttu-id="679c0-113">Normalmente, eles são executados por um longo período de tempo, coletando dados e fazendo alterações em centenas de computadores, geralmente em ambientes heterogêneos.</span><span class="sxs-lookup"><span data-stu-id="679c0-113">Typically, they run for an extended period of time, gathering data from and making changes to hundreds of computers, often in heterogeneous environments.</span></span>

<span data-ttu-id="679c0-114">Os fluxos de trabalho podem ser escritos em XAML, a linguagem usada em Windows Workflow Foundation ou na linguagem do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="679c0-114">Workflows can be written in XAML, the language used in Windows Workflow Foundation, or in the PowerShell language.</span></span> <span data-ttu-id="679c0-115">Os fluxos de trabalho normalmente são empacotados em módulos e incluem tópicos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="679c0-115">Workflows are typically packaged in modules and include help topics.</span></span> <span data-ttu-id="679c0-116">Para obter mais informações, consulte [visão geral de XAML (WPF)](/dotnet/framework/wpf/advanced/xaml-overview-wpf).</span><span class="sxs-lookup"><span data-stu-id="679c0-116">For more information, see [XAML Overview (WPF)](/dotnet/framework/wpf/advanced/xaml-overview-wpf).</span></span>

<span data-ttu-id="679c0-117">Os fluxos de trabalho são críticos em um ambiente de ti porque podem sobreviver a reinicializações e recuperação automáticas de falhas comuns.</span><span class="sxs-lookup"><span data-stu-id="679c0-117">Workflows are critical in an IT environment because they can survive reboots and recover automatically from common failures.</span></span> <span data-ttu-id="679c0-118">Você pode desconectar e reconectar-se de sessões e computadores que executam fluxos de trabalho sem interromper o processamento de fluxo de trabalho e suspender e retomar fluxos de trabalho de forma transparente sem perda de dados.</span><span class="sxs-lookup"><span data-stu-id="679c0-118">You can disconnect and reconnect from sessions and computers running workflows without interrupting workflow processing, and suspend and resume workflows transparently without data loss.</span></span> <span data-ttu-id="679c0-119">Cada atividade em um fluxo de trabalho pode ser registrada em log e auditada para referência.</span><span class="sxs-lookup"><span data-stu-id="679c0-119">Each activity in a workflow can be logged and audited for reference.</span></span>
<span data-ttu-id="679c0-120">Os fluxos de trabalho podem ser executados como trabalhos e podem ser agendados usando o recurso trabalhos agendados do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="679c0-120">Workflows can run as jobs and can be scheduled by using the Scheduled Jobs feature of PowerShell.</span></span>

<span data-ttu-id="679c0-121">O estado e os dados em um fluxo de trabalho são salvos ou persistidos no início e no final do fluxo de trabalho e em pontos que você especificar.</span><span class="sxs-lookup"><span data-stu-id="679c0-121">The state and data in a workflow is saved or persisted at the beginning and end of the workflow and at points that you specify.</span></span> <span data-ttu-id="679c0-122">Os pontos de persistência do fluxo de trabalho funcionam como instantâneos do banco de dados ou pontos de verificação do programa para proteger o fluxo de trabalho contra os efeitos de interrupções e falhas.</span><span class="sxs-lookup"><span data-stu-id="679c0-122">Workflow persistence points work like database snapshots or program checkpoints to protect the workflow from the effects of interruptions and failures.</span></span> <span data-ttu-id="679c0-123">Se o fluxo de trabalho não puder se recuperar de uma falha, você poderá usar os dados persistentes e retomar o último ponto de persistência, em vez de executar um fluxo de trabalho extensivo desde o início.</span><span class="sxs-lookup"><span data-stu-id="679c0-123">If the workflow is unable to recover from a failure, you can use the persisted data and resume from the last persistence point, instead of rerunning an extensive workflow from the beginning.</span></span>

## <a name="workflow-requirements-and-configuration"></a><span data-ttu-id="679c0-124">Requisitos e configuração de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="679c0-124">Workflow requirements and configuration</span></span>

<span data-ttu-id="679c0-125">Uma configuração de fluxo de trabalho do PowerShell consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="679c0-125">A PowerShell Workflow configuration consists of the following elements:</span></span>

- <span data-ttu-id="679c0-126">Um computador cliente, que executa o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="679c0-126">A client computer, which runs the workflow.</span></span>
- <span data-ttu-id="679c0-127">Uma sessão de fluxo de trabalho, **PSSession** , no computador cliente ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="679c0-127">A workflow session, **PSSession** , on the client computer or on a remote computer.</span></span>
- <span data-ttu-id="679c0-128">Nós gerenciados, os computadores de destino que são afetados pelas atividades de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="679c0-128">Managed nodes, the target computers that are affected by the workflow activities.</span></span>

<span data-ttu-id="679c0-129">A sessão de fluxo de trabalho não é necessária, mas é recomendada.</span><span class="sxs-lookup"><span data-stu-id="679c0-129">The workflow session isn't required, but is recommended.</span></span> <span data-ttu-id="679c0-130">As **PSSessions** podem aproveitar os recursos de recuperação robusta e de sessões desconectadas do PowerShell para recuperar sessões de fluxo de trabalho desconectadas.</span><span class="sxs-lookup"><span data-stu-id="679c0-130">**PSSessions** can take advantage of the robust recovery and Disconnected Sessions features of PowerShell to recover disconnected workflow sessions.</span></span> <span data-ttu-id="679c0-131">Para obter mais informações, consulte [about_Remote_Disconnected_Sessions](../../Microsoft.PowerShell.Core/About/about_Remote_Disconnected_Sessions.md)</span><span class="sxs-lookup"><span data-stu-id="679c0-131">For more information, see [about_Remote_Disconnected_Sessions](../../Microsoft.PowerShell.Core/About/about_Remote_Disconnected_Sessions.md)</span></span>

<span data-ttu-id="679c0-132">Como o computador cliente e o computador no qual a sessão de fluxo de trabalho é executada podem ser nós gerenciados, você pode executar um fluxo de trabalho em um único computador que atenda a todas as funções.</span><span class="sxs-lookup"><span data-stu-id="679c0-132">Because the client computer and the computer on which the workflow session runs can be managed nodes, you can run a workflow on a single computer that fulfills all roles.</span></span>

<span data-ttu-id="679c0-133">O computador cliente e o computador no qual a sessão de fluxo de trabalho é executada deve executar o PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="679c0-133">The client computer and the computer on which the workflow session runs must be running PowerShell 3.0.</span></span> <span data-ttu-id="679c0-134">Todos os sistemas qualificados têm suporte, incluindo as opções de instalação Server Core dos sistemas operacionais Windows Server.</span><span class="sxs-lookup"><span data-stu-id="679c0-134">All eligible systems are supported, including the Server Core installation options of Windows Server operating systems.</span></span>

<span data-ttu-id="679c0-135">Para executar fluxos de trabalho que incluem cmdlets, os nós gerenciados devem ter o Windows PowerShell 2,0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="679c0-135">To run workflows that include cmdlets, the managed nodes must have Windows PowerShell 2.0 or later.</span></span> <span data-ttu-id="679c0-136">Nós gerenciados não exigem o PowerShell, a menos que o fluxo de trabalho inclua cmdlets.</span><span class="sxs-lookup"><span data-stu-id="679c0-136">Managed nodes don't require PowerShell unless the workflow includes cmdlets.</span></span> <span data-ttu-id="679c0-137">Você pode executar fluxos de trabalho que incluem comandos Instrumentação de Gerenciamento do Windows (WMI) e modelo CIM (CIM) em computadores que não têm o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="679c0-137">You can run workflows that include Windows Management Instrumentation (WMI) and Common Information Model (CIM) commands on computers that don't have PowerShell.</span></span>

## <a name="how-to-get-workflows"></a><span data-ttu-id="679c0-138">Como obter fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="679c0-138">How to get workflows</span></span>

<span data-ttu-id="679c0-139">Os fluxos de trabalho normalmente são empacotados em módulos.</span><span class="sxs-lookup"><span data-stu-id="679c0-139">Workflows are typically packaged in modules.</span></span> <span data-ttu-id="679c0-140">Para importar o módulo que inclui um fluxo de trabalho, use qualquer comando no módulo ou use o `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="679c0-140">To import the module that includes a workflow, use any command in the module or use the `Import-Module` cmdlet.</span></span>
<span data-ttu-id="679c0-141">Os módulos são importados automaticamente no primeiro uso de qualquer comando no módulo.</span><span class="sxs-lookup"><span data-stu-id="679c0-141">Modules are imported automatically on first use of any command in the module.</span></span>

<span data-ttu-id="679c0-142">Para localizar os fluxos de trabalho nos módulos instalados no seu computador, use o `Get-Command` parâmetro **CommandType** do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="679c0-142">To find the workflows in modules installed on your computer, use the `Get-Command` cmdlet's **CommandType** parameter.</span></span>

```powershell
Get-Command -CommandType Workflow
```

## <a name="how-to-run-workflows"></a><span data-ttu-id="679c0-143">Como executar fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="679c0-143">How to run workflows</span></span>

<span data-ttu-id="679c0-144">Para executar um fluxo de trabalho, use o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="679c0-144">To run a workflow, use the following procedure.</span></span>

1. <span data-ttu-id="679c0-145">Quando o nó gerenciado é o computador local, essa etapa não é necessária.</span><span class="sxs-lookup"><span data-stu-id="679c0-145">When the managed node is the local computer, this step isn't required.</span></span>
   <span data-ttu-id="679c0-146">Caso contrário, no computador cliente, inicie o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="679c0-146">Otherwise, on the client computer, start PowerShell with the **Run as administrator** option.</span></span>

   ```powershell
   Start-Process PowerShell -Verb RunAs
   ```

1. <span data-ttu-id="679c0-147">Habilite a comunicação remota do PowerShell no computador que executa a sessão de fluxo de trabalho e em nós gerenciados afetados por fluxos de trabalho que incluem cmdlets.</span><span class="sxs-lookup"><span data-stu-id="679c0-147">Enable PowerShell remoting on the computer that runs the workflow session and on managed nodes affected by workflows that include cmdlets.</span></span>

   <span data-ttu-id="679c0-148">Você só precisa fazer essa etapa uma vez em cada computador participante.</span><span class="sxs-lookup"><span data-stu-id="679c0-148">You only need to do this step once on each participating computer.</span></span>

   <span data-ttu-id="679c0-149">Esta etapa é necessária somente ao executar fluxos de trabalho que incluem cmdlets.</span><span class="sxs-lookup"><span data-stu-id="679c0-149">This step is required only when running workflows that include cmdlets.</span></span> <span data-ttu-id="679c0-150">Você não precisa habilitar a comunicação remota no computador cliente, a menos que a sessão de fluxos de trabalho seja executada no computador cliente ou em qualquer nó gerenciado que esteja executando o PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="679c0-150">You don't need to enable remoting on the client computer, unless the workflows session runs on the client computer, or on any managed nodes that are running PowerShell 3.0.</span></span>

   <span data-ttu-id="679c0-151">Para habilitar a comunicação remota, use o `Enable-PSRemoting` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="679c0-151">To enable remoting, use the `Enable-PSRemoting` cmdlet.</span></span>

   ```powershell
   Enable-PSRemoting -Force
   ```

   <span data-ttu-id="679c0-152">Você pode habilitar a comunicação remota usando a configuração ativar Política de Grupo de **execução de script** .</span><span class="sxs-lookup"><span data-stu-id="679c0-152">You can enable remoting by using the **Turn on Script Execution** Group Policy setting.</span></span> <span data-ttu-id="679c0-153">Para obter mais informações, consulte [about_Group_Policy_Settings](../../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md) e [about_Execution_Policies](../../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="679c0-153">For more information, see [about_Group_Policy_Settings](../../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md) and [about_Execution_Policies](../../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

1. <span data-ttu-id="679c0-154">Use os `New-PSWorkflowSession` `New-PSSession` cmdlets ou para criar a sessão de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="679c0-154">Use the `New-PSWorkflowSession` or `New-PSSession` cmdlets to create the workflow session.</span></span>

   <span data-ttu-id="679c0-155">O `New-PSWorkflowSession` cmdlet inicia uma sessão que usa a configuração de sessão interna **Microsoft. PowerShell. Workflow** no computador de destino.</span><span class="sxs-lookup"><span data-stu-id="679c0-155">The `New-PSWorkflowSession` cmdlet starts a session that uses the built-in **Microsoft.PowerShell.Workflow** session configuration on the destination computer.</span></span> <span data-ttu-id="679c0-156">Essa configuração de sessão inclui scripts, tipos e formatação de arquivos e opções projetadas para fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="679c0-156">This session configuration includes scripts, type and formatting files, and options that are designed for workflows.</span></span>

   <span data-ttu-id="679c0-157">Ou use o `New-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="679c0-157">Or, use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="679c0-158">Use o parâmetro **ConfigurationName** para especificar a configuração de sessão **Microsoft. PowerShell. Workflow** .</span><span class="sxs-lookup"><span data-stu-id="679c0-158">Use the **ConfigurationName** parameter to specify the **Microsoft.PowerShell.Workflow** session configuration.</span></span> <span data-ttu-id="679c0-159">Esse comando é o mesmo que usar o `New-PSWorkflowSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="679c0-159">This command is the same as using the `New-PSWorkflowSession` cmdlet.</span></span>

   <span data-ttu-id="679c0-160">Uma alternativa é usar o `New-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="679c0-160">An alternative is to use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="679c0-161">Use o parâmetro **ConfigurationName** para especificar a configuração de sessão **Microsoft. PowerShell. Workflow** .</span><span class="sxs-lookup"><span data-stu-id="679c0-161">Use the **ConfigurationName** parameter to specify the **Microsoft.PowerShell.Workflow** session configuration.</span></span>

   <span data-ttu-id="679c0-162">No computador local:</span><span class="sxs-lookup"><span data-stu-id="679c0-162">On the local computer:</span></span>

   ```powershell
   $ws = New-PSWorkflowSession
   ```

   <span data-ttu-id="679c0-163">Em um computador remoto:</span><span class="sxs-lookup"><span data-stu-id="679c0-163">On a remote computer:</span></span>

   ```powershell
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

   <span data-ttu-id="679c0-164">Se você for um administrador no computador da sessão de fluxo de trabalho, poderá usar o `New-PSWorkflowExecutionOption` cmdlet para criar configurações de opção personalizada para a configuração da sessão de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="679c0-164">If you are an Administrator on the workflow session computer, you can use the `New-PSWorkflowExecutionOption` cmdlet to create custom option settings for the workflow session configuration.</span></span> <span data-ttu-id="679c0-165">E use o `Set-PSSessionConfiguration` cmdlet para alterar a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="679c0-165">And, use the `Set-PSSessionConfiguration` cmdlet to change the session configuration.</span></span>

   ```powershell
   $sto = New-PSWorkflowExecutionOption -MaxConnectedSessions 150
   Invoke-Command -ComputerName Server01 `
   {Set-PSSessionConfiguration Microsoft.PowerShell.Workflow `
   -SessionTypeOption $Using:sto}
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

1. <span data-ttu-id="679c0-166">Execute o fluxo de trabalho na sessão de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="679c0-166">Run the workflow in the workflow session.</span></span> <span data-ttu-id="679c0-167">Para especificar os nomes dos nós gerenciados, os computadores de destino, use o parâmetro comum de fluxo de trabalho **PSComputerName** .</span><span class="sxs-lookup"><span data-stu-id="679c0-167">To specify the names of the managed nodes, target computers, use the **PSComputerName** workflow common parameter.</span></span>

   <span data-ttu-id="679c0-168">Os exemplos a seguir executam o fluxo de trabalho chamado **Test-Workflow** .</span><span class="sxs-lookup"><span data-stu-id="679c0-168">The following examples run the workflow named **Test-Workflow** .</span></span>

   <span data-ttu-id="679c0-169">Onde o nó gerenciado é o computador que hospeda a sessão de fluxo de trabalho:</span><span class="sxs-lookup"><span data-stu-id="679c0-169">Where the managed node is the computer that hosts the workflow session:</span></span>

   ```powershell
   Invoke-Command -Session $ws {Test-Workflow}
   ```

   <span data-ttu-id="679c0-170">Onde os nós gerenciados são computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="679c0-170">Where the managed nodes are remote computers.</span></span>

   ```powershell
   Invoke-Command -Session $ws{
   Test-Workflow -PSComputerName Server01, Server02 }
   ```

   <span data-ttu-id="679c0-171">O exemplo a seguir executa o **fluxo de trabalho de teste** em centenas de computadores.</span><span class="sxs-lookup"><span data-stu-id="679c0-171">The following example runs the **Test-Workflow** on hundreds of computers.</span></span> <span data-ttu-id="679c0-172">O `Get-Content` cmdlet obtém os nomes de computador de um arquivo de texto e os salva `$Servers` na variável no computador local.</span><span class="sxs-lookup"><span data-stu-id="679c0-172">The `Get-Content` cmdlet gets the computer names from a text file and saves them in the `$Servers` variable on the local computer.</span></span>

   <span data-ttu-id="679c0-173">`Invoke-Command` usa o `$Using` modificador de escopo para definir a `$Servers` variável na sessão local.</span><span class="sxs-lookup"><span data-stu-id="679c0-173">`Invoke-Command` uses the `$Using` scope modifier to define the `$Servers` variable in the local session.</span></span> <span data-ttu-id="679c0-174">Para obter mais informações sobre o `$Using` modificador de escopo, consulte [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="679c0-174">For more information about the `$Using` scope modifier, see [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span></span>

   ```powershell
   $Servers = Get-Content Servers.txt
   Invoke-Command -Session $ws {Test-Workflow -PSComputerName $Using:Servers }
   ```

## <a name="using-workflow-common-parameters"></a><span data-ttu-id="679c0-175">Usando parâmetros comuns de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="679c0-175">Using workflow common parameters</span></span>

<span data-ttu-id="679c0-176">Os parâmetros comuns do fluxo de trabalho são um conjunto de parâmetros que o PowerShell adiciona automaticamente a todos os fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="679c0-176">The workflow common parameters are a set of parameters that PowerShell adds automatically to all workflows.</span></span> <span data-ttu-id="679c0-177">O PowerShell adiciona os parâmetros comuns do cmdlet a todos os fluxos de trabalho, mesmo que o fluxo de trabalho não use o atributo **CmdletBinding** .</span><span class="sxs-lookup"><span data-stu-id="679c0-177">PowerShell adds the cmdlet common parameters to all workflows, even if the workflow doesn't use the **CmdletBinding** attribute.</span></span>

<span data-ttu-id="679c0-178">Por exemplo, o fluxo de trabalho a seguir não define nenhum parâmetro.</span><span class="sxs-lookup"><span data-stu-id="679c0-178">For example, the following workflow defines no parameters.</span></span> <span data-ttu-id="679c0-179">No entanto, quando você executa o fluxo de trabalho, ele tem **CommonParameters** e **WorkflowCommonParameters** .</span><span class="sxs-lookup"><span data-stu-id="679c0-179">However, when you run the workflow, it has both the **CommonParameters** and **WorkflowCommonParameters** .</span></span>

```powershell
workflow Test-Workflow {Get-Process}
Get-Command Test-Workflow -Syntax
```

```powershell
Test-Workflow [<WorkflowCommonParameters>] [<CommonParameters>]
```

<span data-ttu-id="679c0-180">Os parâmetros comuns do fluxo de trabalho incluem vários parâmetros que são essenciais para a execução de fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="679c0-180">The workflow common parameters include several parameters that are essential to running workflows.</span></span> <span data-ttu-id="679c0-181">Por exemplo, o parâmetro comum **PSComputerName** especifica os nós gerenciados que o fluxo de trabalho afeta.</span><span class="sxs-lookup"><span data-stu-id="679c0-181">For example, the **PSComputerName** common parameter specifies the managed nodes that the workflow affects.</span></span>

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02
}
```

<span data-ttu-id="679c0-182">O parâmetro Common do fluxo de trabalho **PSPersist** determina quando os dados do fluxo de trabalho são persistidos.</span><span class="sxs-lookup"><span data-stu-id="679c0-182">The **PSPersist** workflow common parameter determines when workflow data is persisted.</span></span> <span data-ttu-id="679c0-183">Ele permite que você adicione um ponto de persistência entre atividades a fluxos de trabalho que não definem pontos de persistência.</span><span class="sxs-lookup"><span data-stu-id="679c0-183">It enables you to add persistence point between activities to workflows that don't define persistence points.</span></span>

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPersist:$True
}
```

<span data-ttu-id="679c0-184">Outros parâmetros comuns de fluxo de trabalho permitem especificar as características da conexão remota para os nós gerenciados.</span><span class="sxs-lookup"><span data-stu-id="679c0-184">Other workflow common parameters let you specify the characteristics of the remote connection to the managed nodes.</span></span> <span data-ttu-id="679c0-185">Seus nomes e funcionalidades são semelhantes aos parâmetros de cmdlets de comunicação remota, incluindo `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="679c0-185">Their names and functionality are similar to the parameters of remoting cmdlets, including `Invoke-Command`.</span></span>

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPort 443
}
```

<span data-ttu-id="679c0-186">Tome cuidado para distinguir os parâmetros de comunicação remota que definem a conexão para a sessão de fluxo de trabalho dos parâmetros comuns de fluxo de trabalho do **PS-prefixado** que definem a conexão com os nós gerenciados.</span><span class="sxs-lookup"><span data-stu-id="679c0-186">Take care to distinguish the remoting parameters that define the connection for the workflow session from the **PS-prefixed** workflow common parameters that define the connection to the managed nodes.</span></span>

```powershell
$ws = New-PSSession -ComputerName Server01 -ConfigurationName Microsoft.PowerShell.Workflow

Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSConfigurationName Microsoft.PowerShell.Workflow
}
```

<span data-ttu-id="679c0-187">Alguns parâmetros comuns de fluxo de trabalho são exclusivos de fluxos de trabalho, como o parâmetro **PSParameterCollection** , que permite especificar valores de parâmetros comuns de fluxo de trabalho diferentes para nós remotos diferentes.</span><span class="sxs-lookup"><span data-stu-id="679c0-187">Some workflow common parameters are unique to workflows, such as the **PSParameterCollection** parameter that lets you specify different workflow common parameter values for different remote nodes.</span></span> <span data-ttu-id="679c0-188">Para obter uma lista e uma descrição dos parâmetros comuns do fluxo de trabalho, consulte [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="679c0-188">For a list and description of the workflow common parameters, see [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="679c0-189">Confira também</span><span class="sxs-lookup"><span data-stu-id="679c0-189">See also</span></span>

[<span data-ttu-id="679c0-190">Invoke-AsWorkflow</span><span class="sxs-lookup"><span data-stu-id="679c0-190">Invoke-AsWorkflow</span></span>](xref:PSWorkflowUtility.Invoke-AsWorkflow)

[<span data-ttu-id="679c0-191">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="679c0-191">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

<span data-ttu-id="679c0-192">Cmdlets [PSWorkflow](xref:PSWorkflow)</span><span class="sxs-lookup"><span data-stu-id="679c0-192">[PSWorkflow](xref:PSWorkflow) cmdlets</span></span>

[<span data-ttu-id="679c0-193">Guia de fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="679c0-193">Workflows Guide</span></span>](/previous-versions/powershell/scripting/components/workflows-guide)

[<span data-ttu-id="679c0-194">Escrevendo um Fluxo de Trabalho do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="679c0-194">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
