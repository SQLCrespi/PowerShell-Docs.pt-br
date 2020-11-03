---
external help file: Microsoft.PowerShell.Workflow.ServiceCore.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSWorkflowUtility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflowutility/invoke-asworkflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-AsWorkflow
ms.openlocfilehash: b96bce9fe4d574fe2b7e9c7c0f1e05ee0508adce
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193655"
---
# <span data-ttu-id="56e8f-103">Invoke-AsWorkflow</span><span class="sxs-lookup"><span data-stu-id="56e8f-103">Invoke-AsWorkflow</span></span>

## <span data-ttu-id="56e8f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="56e8f-104">SYNOPSIS</span></span>
<span data-ttu-id="56e8f-105">Executa um comando ou uma expressão como um Fluxo de Trabalho do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56e8f-105">Runs a command or expression as a Windows PowerShell Workflow.</span></span>

## <span data-ttu-id="56e8f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="56e8f-106">SYNTAX</span></span>

### <span data-ttu-id="56e8f-107">Comando (padrão)</span><span class="sxs-lookup"><span data-stu-id="56e8f-107">Command (Default)</span></span>

```
Invoke-AsWorkflow [-CommandName <String>] [-Parameter <Hashtable>] [-InputObject <Object>] [<CommonParameters>]
```

### <span data-ttu-id="56e8f-108">Expression</span><span class="sxs-lookup"><span data-stu-id="56e8f-108">Expression</span></span>

```
Invoke-AsWorkflow [-Expression <String>] [-InputObject <Object>] [<CommonParameters>]
```

## <span data-ttu-id="56e8f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="56e8f-109">DESCRIPTION</span></span>

<span data-ttu-id="56e8f-110">O `Invoke-AsWorkflow` fluxo de trabalho executa qualquer comando ou expressão como um script embutido em um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="56e8f-110">The `Invoke-AsWorkflow` workflow runs any command or expression as an inline script in a workflow.</span></span>
<span data-ttu-id="56e8f-111">Esses fluxos de trabalho usam a semântica do fluxo de trabalho padrão, têm todos os parâmetros comuns de fluxo de trabalho e todos os benefícios dos fluxos de trabalho, incluindo a capacidade de parar, reiniciar e recuperar.</span><span class="sxs-lookup"><span data-stu-id="56e8f-111">These workflows use the standard workflow semantics, have all workflow common parameters, and have all benefits of workflows, including the ability to stop, resume, and recover.</span></span>

<span data-ttu-id="56e8f-112">Fluxos de trabalho são criados para comandos de longa execução que coletam dados críticos, mas podem ser usados para executar qualquer comando.</span><span class="sxs-lookup"><span data-stu-id="56e8f-112">Workflows are designed for long-running commands that collect critical data, but can be used to run any command.</span></span>
<span data-ttu-id="56e8f-113">Para obter mais informações, consulte [about_Workflows](../PSWorkflow/About/about_Workflows.md).</span><span class="sxs-lookup"><span data-stu-id="56e8f-113">For more information, see [about_Workflows](../PSWorkflow/About/about_Workflows.md).</span></span>

<span data-ttu-id="56e8f-114">Também é possível adicionar parâmetros comuns de fluxo de trabalho para esse comando.</span><span class="sxs-lookup"><span data-stu-id="56e8f-114">You can also add workflow common parameters to this command.</span></span>
<span data-ttu-id="56e8f-115">Para obter mais informações sobre parâmetros comuns de fluxo de trabalho, consulte [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)</span><span class="sxs-lookup"><span data-stu-id="56e8f-115">For more information about workflow common parameters, see [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)</span></span>

<span data-ttu-id="56e8f-116">Este fluxo de trabalho é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="56e8f-116">This workflow is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="56e8f-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="56e8f-117">EXAMPLES</span></span>

### <span data-ttu-id="56e8f-118">Exemplo 1: executar um cmdlet como um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="56e8f-118">Example 1: Run a cmdlet as a workflow</span></span>

```powershell
Invoke-AsWorkflow -PSComputerName (Get-Content Servers.txt) -CommandName Get-ExecutionPolicy
```

```output
PSComputerName                     PSSourceJobInstanceId                   Value
--------------                     ---------------------                   -----
Server01                           77b1cdf8-8226-4662-9067-cd2fa5c3b711    AllSigned
Server02                           a33542d7-3cdd-4339-ab99-0e7cd8e59462    Unrestricted
Server03                           279bac28-066a-4646-9497-8fcdcfe9757e    AllSigned
localhost                          0d858009-2cc4-47a4-a2e0-da17dc2883d0    RemoteSigned
```

<span data-ttu-id="56e8f-119">Esse comando executa o `Get-ExecutionPolicy` cmdlet como um fluxo de trabalho em centenas de computadores.</span><span class="sxs-lookup"><span data-stu-id="56e8f-119">This command runs the `Get-ExecutionPolicy` cmdlet as a workflow on hundreds of computers.</span></span>

<span data-ttu-id="56e8f-120">O comando utiliza o parâmetro **CommandName** para especificar o cmdlet que é executado no fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="56e8f-120">The command uses the **CommandName** parameter to specify the cmdlet that runs in the workflow.</span></span>
<span data-ttu-id="56e8f-121">Ele usa o parâmetro comum de fluxo de trabalho **PSComputerName** para especificar os computadores em que o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="56e8f-121">It uses the **PSComputerName** workflow common parameter to specify the computers on which the command runs.</span></span>
<span data-ttu-id="56e8f-122">O valor do parâmetro **PSComputerName** é um `Get-Content` comando que obtém uma lista de nomes de computador do arquivo de Servers.txt.</span><span class="sxs-lookup"><span data-stu-id="56e8f-122">The value of the **PSComputerName** parameter is a `Get-Content` command that gets a list of computer names from the Servers.txt file.</span></span>
<span data-ttu-id="56e8f-123">O valor do parâmetro é colocado entre parênteses para direcionar o Windows PowerShell a executar o `Get-Command` comando antes de usar o valor.</span><span class="sxs-lookup"><span data-stu-id="56e8f-123">The parameter value is enclosed in parentheses to direct Windows PowerShell to run the `Get-Command` command before using the value.</span></span>

<span data-ttu-id="56e8f-124">Assim como acontece com todos os comandos remotos, se o comando é executado no computador local, (se o valor do parâmetro PSComputerName inclui o computador local), você deve iniciar o Windows PowerShell com a opção "Executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="56e8f-124">As with all remote commands, if the command runs on the local computer, (if the value of the PSComputerName parameter includes the local computer), you must start Windows PowerShell with the "Run as administrator" option.</span></span>

### <span data-ttu-id="56e8f-125">Exemplo 2: executar um cmdlet com parâmetros</span><span class="sxs-lookup"><span data-stu-id="56e8f-125">Example 2: Run a cmdlet with parameters</span></span>

```powershell
$s = Import-Csv .\Servers.csv -Header ServerName, ServerID
Invoke-AsWorkflow -CommandName Get-ExecutionPolicy -Parameter @{Scope="Process"} -PSComputerName {$s.ServerName} -PSConnectionRetryCount 5
```

<span data-ttu-id="56e8f-126">O primeiro comando usa o `Import-Csv` cmdlet para criar um objeto do conteúdo no arquivo de Servers.csv.</span><span class="sxs-lookup"><span data-stu-id="56e8f-126">The first command uses the `Import-Csv` cmdlet to create an object from the content in the Servers.csv file.</span></span> <span data-ttu-id="56e8f-127">O comando usa o `Header` parâmetro para criar uma `ServerName` propriedade para a coluna que contém os nomes dos computadores de destino, também conhecidos como "nós remotos".</span><span class="sxs-lookup"><span data-stu-id="56e8f-127">The command uses the `Header` parameter to create a `ServerName` property for the column that contains the names of the target computers, also known as "remote nodes."</span></span> <span data-ttu-id="56e8f-128">O comando salva o resultado na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="56e8f-128">The command saves the result in the `$s` variable.</span></span>

<span data-ttu-id="56e8f-129">O segundo comando usa o `Invoke-AsWorkflow` fluxo de trabalho para executar um `Get-ExecutionPolicy` comando nos computadores do arquivo de Servers.csv.</span><span class="sxs-lookup"><span data-stu-id="56e8f-129">The second command uses the `Invoke-AsWorkflow` workflow to run a `Get-ExecutionPolicy` command on the computers in the Servers.csv file.</span></span> <span data-ttu-id="56e8f-130">O comando usa o parâmetro **CommandName** de `Invoke-AsWorkflow`  para especificar o comando a ser executado no fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="56e8f-130">The command uses the **CommandName** parameter of `Invoke-AsWorkflow`  to specify the command to run in the workflow.</span></span> <span data-ttu-id="56e8f-131">Ele usa o `Parameter` parâmetro de `Invoke-AsWorkflow` para especificar o `Scope` parâmetro do `Get-ExecutionPolicy` cmdlet com um valor de **process** . O comando também usa o `PSConnectionRetryCount` parâmetro comum do fluxo de trabalho para limitar o comando a cinco tentativas em cada computador e o `PSComputerName` parâmetro comum do fluxo de trabalho para especificar os nomes dos nós remotos (computadores de destino).</span><span class="sxs-lookup"><span data-stu-id="56e8f-131">It uses the `Parameter` parameter of `Invoke-AsWorkflow` to specify the `Scope` parameter of the `Get-ExecutionPolicy` cmdlet with a value of **Process** .The command also uses the `PSConnectionRetryCount` workflow common parameter to limit the command to five attempts on each computer and the `PSComputerName` workflow common parameter to specify the names of the remote nodes (target computers).</span></span> <span data-ttu-id="56e8f-132">O valor do `PSComputerName` parâmetro é uma expressão que obtém a `ServerName` propriedade de cada objeto na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="56e8f-132">The value of the `PSComputerName` parameter is an expression that gets the `ServerName` property of every object in the `$s` variable.</span></span>

<span data-ttu-id="56e8f-133">Esses comandos executam um `Get-ExecutionPolicy` comando como um fluxo de trabalho em centenas de computadores.</span><span class="sxs-lookup"><span data-stu-id="56e8f-133">These commands run a `Get-ExecutionPolicy` command as a workflow on hundreds of computers.</span></span>
<span data-ttu-id="56e8f-134">O comando usa o `Scope` parâmetro do `Get-ExecutionPolicy` cmdlet com um valor de **processo** para obter a política de execução na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="56e8f-134">The command uses the `Scope` parameter of the `Get-ExecutionPolicy` cmdlet with a value of **Process** to get the execution policy in the current session.</span></span>

### <span data-ttu-id="56e8f-135">Exemplo 3: executar uma expressão como um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="56e8f-135">Example 3: Run an expression as a workflow</span></span>

```powershell
Invoke-AsWorkflow -Expression "ipconfig /all" -PSComputerName (Get-Content DomainControllers.txt) -AsJob -JobName IPConfig
```

```output
Id     Name          PSJobTypeName   State         HasMoreData   Location                Command
--     ----          -------------   -----         -----------   --------                -------
2      IpConfig      PSWorkflowJob   Completed     True          Server01, Server01...   Invoke-AsWorkflow
```

<span data-ttu-id="56e8f-136">Esse comando usa o `Invoke-AsWorkflow` fluxo de trabalho para executar um comando ipconfig como um job de workflow nos computadores listados no arquivo de DomainControllers.txt.</span><span class="sxs-lookup"><span data-stu-id="56e8f-136">This command uses the `Invoke-AsWorkflow` workflow to run an Ipconfig command as a workflow job on the computers listed in the DomainControllers.txt file.</span></span>

<span data-ttu-id="56e8f-137">O comando usa o `Expression` parâmetro para especificar a expressão a ser executada.</span><span class="sxs-lookup"><span data-stu-id="56e8f-137">The command uses the `Expression` parameter to specify the expression to run.</span></span>
<span data-ttu-id="56e8f-138">Ele usa o `PSComputerName` parâmetro Common do fluxo de trabalho para especificar os nomes dos nós remotos (computadores de destino).</span><span class="sxs-lookup"><span data-stu-id="56e8f-138">It uses the `PSComputerName` workflow common parameter to specify the names of the remote nodes (target computers).</span></span>

<span data-ttu-id="56e8f-139">O comando também usa os `AsJob` parâmetros comuns do e do `JobName` fluxo de trabalho para executar o workflow como uma tarefa em segundo plano em cada computador com o nome do trabalho "ipconfig".</span><span class="sxs-lookup"><span data-stu-id="56e8f-139">The command also uses the `AsJob` and `JobName` workflow common parameters to run the workflow as a background job on each computer with the "Ipconfig" job name.</span></span>

<span data-ttu-id="56e8f-140">O comando retorna um `ContainerParentJob` objeto ( `System.Management.Automation.ContainerParentJob` ) que contém os trabalhos de fluxo de trabalho em cada computador.</span><span class="sxs-lookup"><span data-stu-id="56e8f-140">The command returns a `ContainerParentJob` object (`System.Management.Automation.ContainerParentJob`) that contains the workflow jobs on each computer.</span></span>

## <span data-ttu-id="56e8f-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="56e8f-141">PARAMETERS</span></span>

### <span data-ttu-id="56e8f-142">-CommandName</span><span class="sxs-lookup"><span data-stu-id="56e8f-142">-CommandName</span></span>

<span data-ttu-id="56e8f-143">Executa o cmdlet especificado ou função avançada como um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="56e8f-143">Runs the specified cmdlet or advanced function as a workflow.</span></span>
<span data-ttu-id="56e8f-144">Insira o nome do cmdlet ou da função, como `Update-Help` , `Set-ExecutionPolicy` ou `Set-NetFirewallRule` .</span><span class="sxs-lookup"><span data-stu-id="56e8f-144">Enter the cmdlet or function name, such as `Update-Help`, `Set-ExecutionPolicy`, or `Set-NetFirewallRule`.</span></span>

```yaml
Type: System.String
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="56e8f-145">-Expressão</span><span class="sxs-lookup"><span data-stu-id="56e8f-145">-Expression</span></span>

<span data-ttu-id="56e8f-146">Especifica a expressão que esse cmdlet executa como um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="56e8f-146">Specifies the  expression that this cmdlet runs as a workflow.</span></span>
<span data-ttu-id="56e8f-147">Insira a expressão como uma cadeia de caracteres, como `"ipconfig /all"` .</span><span class="sxs-lookup"><span data-stu-id="56e8f-147">Enter the expression as a string, such as `"ipconfig /all"`.</span></span>
<span data-ttu-id="56e8f-148">Se a expressão incluir espaços ou caracteres especiais, coloque-a entre aspas.</span><span class="sxs-lookup"><span data-stu-id="56e8f-148">If the expression includes spaces or special characters, enclose the expression in quotation marks.</span></span>

```yaml
Type: System.String
Parameter Sets: Expression
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="56e8f-149">Parâmetros do </span><span class="sxs-lookup"><span data-stu-id="56e8f-149">-Parameter</span></span>

<span data-ttu-id="56e8f-150">Especifica os parâmetros e os valores de parâmetro do comando especificado no `CommandName` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="56e8f-150">Specifies the parameters and parameter values of the command that is specified in the `CommandName` parameter.</span></span>
<span data-ttu-id="56e8f-151">Insira uma tabela de hash na qual cada chave seja um nome de parâmetro e seu valor seja o valor do parâmetro, como `@{ExecutionPolicy="AllSigned"}` .</span><span class="sxs-lookup"><span data-stu-id="56e8f-151">Enter a hash table in which each key is a parameter name and its value is the parameter value, such as `@{ExecutionPolicy="AllSigned"}`.</span></span>

<span data-ttu-id="56e8f-152">Para obter informações sobre tabelas de hash, consulte [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="56e8f-152">For information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="56e8f-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="56e8f-153">-InputObject</span></span>

<span data-ttu-id="56e8f-154">Usado para permitir a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="56e8f-154">Used to allows pipeline input.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="56e8f-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="56e8f-155">CommonParameters</span></span>

<span data-ttu-id="56e8f-156">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="56e8f-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="56e8f-157">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="56e8f-157">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

### <span data-ttu-id="56e8f-158">WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="56e8f-158">WorkflowCommonParameters</span></span>

<span data-ttu-id="56e8f-159">Esse cmdlet também dá suporte a parâmetros comuns específicos de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="56e8f-159">This cmdlet also supports workflow specific common parameters.</span></span>
<span data-ttu-id="56e8f-160">Para obter informações, consulte [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="56e8f-160">For information, see [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md).</span></span>

## <span data-ttu-id="56e8f-161">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="56e8f-161">INPUTS</span></span>

### <span data-ttu-id="56e8f-162">System.Object</span><span class="sxs-lookup"><span data-stu-id="56e8f-162">System.Object</span></span>

<span data-ttu-id="56e8f-163">É possível canalizar qualquer objeto para o `InputObject` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="56e8f-163">You can pipe any object to the `InputObject` parameter.</span></span>

## <span data-ttu-id="56e8f-164">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="56e8f-164">OUTPUTS</span></span>

### <span data-ttu-id="56e8f-165">Nenhum</span><span class="sxs-lookup"><span data-stu-id="56e8f-165">None</span></span>

<span data-ttu-id="56e8f-166">Esse comando não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="56e8f-166">This command does not generate any output.</span></span>
<span data-ttu-id="56e8f-167">No entanto, ele executa o fluxo de trabalho que pode gerar uma saída.</span><span class="sxs-lookup"><span data-stu-id="56e8f-167">However, it runs the workflow, which might generate output.</span></span>

## <span data-ttu-id="56e8f-168">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="56e8f-168">NOTES</span></span>

## <span data-ttu-id="56e8f-169">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="56e8f-169">RELATED LINKS</span></span>

[<span data-ttu-id="56e8f-170">New-PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="56e8f-170">New-PSWorkflowExecutionOption</span></span>](../PSWorkflow/New-PSWorkflowExecutionOption.md)

[<span data-ttu-id="56e8f-171">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="56e8f-171">New-PSWorkflowSession</span></span>](../PSWorkflow/New-PSWorkflowSession.md)

[<span data-ttu-id="56e8f-172">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="56e8f-172">about_Workflows</span></span>](../PSWorkflow/About/about_Workflows.md)

[<span data-ttu-id="56e8f-173">about_Workflow_Common_Parameters</span><span class="sxs-lookup"><span data-stu-id="56e8f-173">about_Workflow_Common_Parameters</span></span>](../PSWorkflow/About/about_WorkflowCommonParameters.md)
