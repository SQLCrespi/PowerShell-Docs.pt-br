---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJob
ms.openlocfilehash: 6144d9f19b86727bc09d07e94f4bcf158e3b7071
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387899"
---
# <span data-ttu-id="f6f2f-103">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f6f2f-103">Set-ScheduledJob</span></span>

## <span data-ttu-id="f6f2f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f6f2f-104">SYNOPSIS</span></span>
<span data-ttu-id="f6f2f-105">Altera trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-105">Changes scheduled jobs.</span></span>

## <span data-ttu-id="f6f2f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f6f2f-106">SYNTAX</span></span>

### <span data-ttu-id="f6f2f-107">ScriptBlock (padrão)</span><span class="sxs-lookup"><span data-stu-id="f6f2f-107">ScriptBlock (Default)</span></span>

```
Set-ScheduledJob [-Name <String>] [-ScriptBlock <ScriptBlock>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### <span data-ttu-id="f6f2f-108">FilePath</span><span class="sxs-lookup"><span data-stu-id="f6f2f-108">FilePath</span></span>

```
Set-ScheduledJob [-Name <String>] [-FilePath <String>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### <span data-ttu-id="f6f2f-109">Execução</span><span class="sxs-lookup"><span data-stu-id="f6f2f-109">Execution</span></span>

```
Set-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-ClearExecutionHistory] [-PassThru]
 [<CommonParameters>]
```

## <span data-ttu-id="f6f2f-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f6f2f-110">DESCRIPTION</span></span>
<span data-ttu-id="f6f2f-111">O cmdlet **Set-ScheduledJob** altera as propriedades dos trabalhos agendados, como os comandos que os trabalhos executam ou as credenciais necessárias para executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-111">The **Set-ScheduledJob** cmdlet changes the properties of scheduled jobs, such as the commands that the jobs run or the credentials required to run the job.</span></span>
<span data-ttu-id="f6f2f-112">Você também pode usar isso para limpar o histórico de execução do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-112">You can also use it to clear the execution history of the scheduled job.</span></span>

<span data-ttu-id="f6f2f-113">Para usar esse cmdlet, comece usando o cmdlet Get-ScheduledJob para obter o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-113">To use this cmdlet, begin by using the Get-ScheduledJob cmdlet to get the scheduled job.</span></span>
<span data-ttu-id="f6f2f-114">Em seguida, redirecione o trabalho agendado para **set-ScheduledJob** ou salve o trabalho em uma variável e use o parâmetro *InputObject* para identificar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-114">Then, pipe the scheduled job to **Set-ScheduledJob** or save the job in a variable and use the *InputObject* parameter to identify the job.</span></span>
<span data-ttu-id="f6f2f-115">Use os parâmetros restantes do **Set-ScheduledJob** para alterar as propriedades do trabalho ou limpar o histórico de execução.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-115">Use the remaining parameters of **Set-ScheduledJob** to change the job properties or clear the execution history.</span></span>

<span data-ttu-id="f6f2f-116">Embora você possa usar **set-ScheduledJob** para alterar os gatilhos e as opções de um trabalho agendado, os cmdlets Add-JobTrigger, Set-JobTrigger e Set-ScheduledJobOption fornecem maneiras muito mais fáceis de realizar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-116">Although you can use **Set-ScheduledJob** to change the triggers and options of a scheduled job, the Add-JobTrigger, Set-JobTrigger, and Set-ScheduledJobOption cmdlets provide much easier ways to accomplish those tasks.</span></span>
<span data-ttu-id="f6f2f-117">Para criar um novo trabalho agendado, use o cmdlet Register-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-117">To create a new scheduled job, use the Register-ScheduledJob cmdlet.</span></span>

<span data-ttu-id="f6f2f-118">O parâmetro *Trigger* de **set-ScheduledJob** adiciona um ou mais gatilhos de trabalho que iniciam o trabalho.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-118">The *Trigger* parameter of **Set-ScheduledJob** adds one or more job triggers that start the job.</span></span>
<span data-ttu-id="f6f2f-119">O parâmetro *Trigger* é opcional, de modo que você pode adicionar gatilhos ao criar o trabalho agendado, adicionar gatilhos de trabalho mais tarde, adicionar o parâmetro *RunNow* para iniciar o trabalho imediatamente, usar o cmdlet Start-Job para iniciar o trabalho imediatamente a qualquer momento ou salvar o trabalho agendado não disparado como um modelo para outros trabalhos.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-119">The *Trigger* parameter is optional, so you can add triggers when you create the scheduled job, add job triggers later, add the *RunNow* parameter to start the job immediately, use the Start-Job cmdlet to start the job immediately at any time, or save the untriggered scheduled job as a template for other jobs.</span></span>

<span data-ttu-id="f6f2f-120">**Set-ScheduledJob** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-120">**Set-ScheduledJob** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="f6f2f-121">Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-121">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="f6f2f-122">Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-122">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="f6f2f-123">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-123">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="f6f2f-124">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f6f2f-124">EXAMPLES</span></span>

### <span data-ttu-id="f6f2f-125">Exemplo 1: alterar o script que um trabalho executa</span><span class="sxs-lookup"><span data-stu-id="f6f2f-125">Example 1: Change the script that a job runs</span></span>

```
PS C:\> Get-ScheduledJob -Name "Inventory"
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-Inventory.ps1             True

The second command uses the Get-ScheduledJob cmdlet to get the Inventory scheduled job. A pipeline operator (|) sends the scheduled job to the **Set-ScheduledJob** cmdlet. The **Set-ScheduledJob** cmdlet uses the *Script* parameter to specify a new script, Get-FullInventory.ps1. The command uses the *Passthru* parameter to return the scheduled job after the change.
PS C:\> Get-ScheduledJob -Name "Inventory" | Set-ScheduledJob -FilePath "C:\Scripts\Get-FullInventory.ps1" -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-FullInventory.ps1         True
```

<span data-ttu-id="f6f2f-126">Este exemplo mostra como alterar o script que é executado em um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-126">This example shows how to change the script that is run in a scheduled job.</span></span>

<span data-ttu-id="f6f2f-127">O primeiro comando usa o cmdlet Get-ScheduledJob para obter o trabalho agendado de inventário.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-127">The first command uses the Get-ScheduledJob cmdlet to get the Inventory scheduled job.</span></span>
<span data-ttu-id="f6f2f-128">A saída mostra que o trabalho executa o script Get-Inventory.ps1.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-128">The output shows that the job runs the Get-Inventory.ps1 script.</span></span>

<span data-ttu-id="f6f2f-129">Este comando não é obrigatório. Ele está incluído apenas para mostrar o efeito da alteração do script.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-129">This command is not required; it is included only to show the effect of the script change.</span></span>

### <span data-ttu-id="f6f2f-130">Exemplo 2: excluir o histórico de execução de um trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="f6f2f-130">Example 2: Delete the execution history of a scheduled job</span></span>

```
PS C:\> Get-ScheduledJob BackupArchive | Set-ScheduledJob -ClearExecutionHistory
```

<span data-ttu-id="f6f2f-131">Esse comando exclui o histórico de execução atual e salva os resultados do trabalho para o trabalho agendado BackupArchive.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-131">This command deletes the current execution history and saved job results for the BackupArchive scheduled job.</span></span>

<span data-ttu-id="f6f2f-132">O comando usa o cmdlet Get-ScheduledJob para obter o trabalho agendado do BackupArchive.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-132">The command uses the Get-ScheduledJob cmdlet to get the BackupArchive scheduled job.</span></span>
<span data-ttu-id="f6f2f-133">Um operador de pipeline (|) envia o trabalho para o cmdlet **Set-ScheduledJob** para alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-133">A pipeline operator (|) sends the job to the **Set-ScheduledJob** cmdlet to change it.</span></span>
<span data-ttu-id="f6f2f-134">O cmdlet **set-ScheduledJob** usa o parâmetro *ClearExecutionHistory* para excluir o histórico de execução e os resultados salvos.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-134">The **Set-ScheduledJob** cmdlet uses the *ClearExecutionHistory* parameter to delete the execution history and saved results.</span></span>

<span data-ttu-id="f6f2f-135">Para obter mais informações sobre o histórico de execução e os resultados do trabalho dos trabalhos agendados salvos, consulte about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-135">For more information about the execution history and saved job results of scheduled jobs, see about_Scheduled_Jobs.</span></span>

### <span data-ttu-id="f6f2f-136">Exemplo 3: alterar os trabalhos agendados em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="f6f2f-136">Example 3: Change scheduled jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -Computer "Server01, Server02" -ScriptBlock {Get-ScheduledJob | Set-ScheduledJob -InitializationScript \\SrvA\Scripts\SetForRun.ps1}
```

<span data-ttu-id="f6f2f-137">Esse comando altera o script de inicialização em todos os trabalhos agendados nos computadores Server01 e Server02.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-137">This command changes the initialization script in all scheduled jobs on the Server01 and Server02 computers.</span></span>

<span data-ttu-id="f6f2f-138">O comando usa o cmdlet Invoke-Command para executar um comando nos computadores Server01 e Server02.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-138">The command uses the Invoke-Command cmdlet to run a command on the Server01 and Server02 computers.</span></span>

<span data-ttu-id="f6f2f-139">O comando remoto começa com um comando Get-ScheduledJob que obtém todos os trabalhos agendados no computador.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-139">The remote command begins with a Get-ScheduledJob command that gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="f6f2f-140">Os trabalhos agendados são canalizados para o cmdlet **set-ScheduledJob** , que altera o script de inicialização para SetForRun.ps1.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-140">The scheduled jobs are piped to the **Set-ScheduledJob** cmdlet, which changes the initialization script to SetForRun.ps1.</span></span>

## <span data-ttu-id="f6f2f-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f6f2f-141">PARAMETERS</span></span>

### <span data-ttu-id="f6f2f-142">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="f6f2f-142">-ArgumentList</span></span>
<span data-ttu-id="f6f2f-143">Especifica valores para os parâmetros do script especificados pelo parâmetro *FilePath* ou para o comando especificado pelo parâmetro *ScriptBlock*.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-143">Specifies values for the parameters of the script that is specified by the *FilePath* parameter or for the command that is specified by the *ScriptBlock* parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-144">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="f6f2f-144">-Authentication</span></span>
<span data-ttu-id="f6f2f-145">Especifica o mecanismo usado para autenticar as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-145">Specifies the mechanism that is used to authenticate the user's credentials.</span></span>
<span data-ttu-id="f6f2f-146">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="f6f2f-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f6f2f-147">Padrão</span><span class="sxs-lookup"><span data-stu-id="f6f2f-147">Default</span></span>
- <span data-ttu-id="f6f2f-148">Basic</span><span class="sxs-lookup"><span data-stu-id="f6f2f-148">Basic</span></span>
- <span data-ttu-id="f6f2f-149">CredSSP</span><span class="sxs-lookup"><span data-stu-id="f6f2f-149">Credssp</span></span>
- <span data-ttu-id="f6f2f-150">Digest</span><span class="sxs-lookup"><span data-stu-id="f6f2f-150">Digest</span></span>
- <span data-ttu-id="f6f2f-151">Kerberos</span><span class="sxs-lookup"><span data-stu-id="f6f2f-151">Kerberos</span></span>
- <span data-ttu-id="f6f2f-152">Negotiate</span><span class="sxs-lookup"><span data-stu-id="f6f2f-152">Negotiate</span></span>
- <span data-ttu-id="f6f2f-153">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="f6f2f-153">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="f6f2f-154">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-154">The default value is Default.</span></span> <span data-ttu-id="f6f2f-155">Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism) no SDK do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-155">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism) in the PowerShell SDK.</span></span>

<span data-ttu-id="f6f2f-156">Cuidado: a autenticação do Credential Security Support Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-156">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
<span data-ttu-id="f6f2f-157">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-157">This mechanism increases the security risk of the remote operation.</span></span>
<span data-ttu-id="f6f2f-158">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-158">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ScriptBlock, FilePath
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-159">-ClearExecutionHistory</span><span class="sxs-lookup"><span data-stu-id="f6f2f-159">-ClearExecutionHistory</span></span>
<span data-ttu-id="f6f2f-160">Exclui o histórico de execução atual e os resultados salvos do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-160">Deletes the current execution history and the saved results of the scheduled job.</span></span>

<span data-ttu-id="f6f2f-161">O histórico de execução de trabalho e os resultados do trabalho são salvos com o trabalho agendado no diretório $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs no computador onde o trabalho é criado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-161">The job execution history and job results are saved with the scheduled job in the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs directory on the computer on which the job is created.</span></span>
<span data-ttu-id="f6f2f-162">Para ver o histórico de execução, use o cmdlet Get-Job.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-162">To see the execution history, use the Get-Job cmdlet.</span></span>
<span data-ttu-id="f6f2f-163">Para obter os resultados do trabalho, use o cmdlet Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-163">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="f6f2f-164">Esse parâmetro não afeta os eventos que o Agendador de tarefas grava nos logs de eventos do Windows e não impede que o Windows PowerShell salve os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-164">This parameter does not affect the events that Task Scheduler writes to the Windows event logs and it does not stop Windows PowerShell from saving job results.</span></span>
<span data-ttu-id="f6f2f-165">Para gerenciar o número de resultados de trabalho que são salvos, use o parâmetro *MaxResultCount*.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-165">To manage the number of job results that are saved, use the *MaxResultCount* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Execution
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-166">-Credential</span><span class="sxs-lookup"><span data-stu-id="f6f2f-166">-Credential</span></span>
<span data-ttu-id="f6f2f-167">Especifica uma conta de usuário que tenha permissão para executar o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-167">Specifies a user account that has permission to run the scheduled job.</span></span>
<span data-ttu-id="f6f2f-168">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-168">The default is the current user.</span></span>

<span data-ttu-id="f6f2f-169">Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um do cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-169">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one from the Get-Credential cmdlet.</span></span>
<span data-ttu-id="f6f2f-170">Se você inserir apenas um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-170">If you enter only a user name, you will be prompted for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-171">-FilePath</span><span class="sxs-lookup"><span data-stu-id="f6f2f-171">-FilePath</span></span>
<span data-ttu-id="f6f2f-172">Especifica um script que o trabalho agendado executa.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-172">Specifies a script that the scheduled job runs.</span></span>
<span data-ttu-id="f6f2f-173">Insira o caminho para um arquivo .ps1 no computador local.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-173">Enter the path to a .ps1 file on the local computer.</span></span>
<span data-ttu-id="f6f2f-174">Para especificar valores padrão para os parâmetros de script, use o parâmetro *ArgumentList*.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-174">To specify default values for the script parameters, use the *ArgumentList* parameter.</span></span>
<span data-ttu-id="f6f2f-175">Cada trabalho agendado deve ter um valor *ScriptBlock* ou *FilePath*.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-175">Every scheduled job must have either a *ScriptBlock* or *FilePath* value.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-176">-InitializationScript</span><span class="sxs-lookup"><span data-stu-id="f6f2f-176">-InitializationScript</span></span>
<span data-ttu-id="f6f2f-177">Especifica o caminho totalmente qualificado para um script do Windows PowerShell (.ps1).</span><span class="sxs-lookup"><span data-stu-id="f6f2f-177">Specifies the fully qualified path to a Windows PowerShell script (.ps1).</span></span>
<span data-ttu-id="f6f2f-178">O script de inicialização é executado na sessão criada para o trabalho em segundo plano antes dos comandos especificados pelo parâmetro *ScriptBlock* ou pelo script especificado pelo parâmetro *FilePath*.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-178">The initialization script runs in the session that is created for the background job before the commands that are specified by the *ScriptBlock* parameter or the script that is specified by the *FilePath* parameter.</span></span>
<span data-ttu-id="f6f2f-179">Você pode usar o script de inicialização para configurar a sessão, adicionando arquivos, funções ou aliases, criando diretórios ou verificando pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-179">You can use the initialization script to configure the session, such as adding files, functions, or aliases, creating directories, or checking for prerequisites.</span></span>

<span data-ttu-id="f6f2f-180">Para especificar um script que execute os comandos de trabalho principal, use o parâmetro *FilePath*.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-180">To specify a script that runs the primary job commands, use the *FilePath* parameter.</span></span>

<span data-ttu-id="f6f2f-181">Se o script de inicialização gerar um erro, incluindo um erro de não finalização, a instância atual do trabalho agendado não será executada e seu status falhará.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-181">If the initialization script generates an error, including a non-terminating error, the current instance of the scheduled job does not run and its status is Failed.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-182">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f6f2f-182">-InputObject</span></span>
<span data-ttu-id="f6f2f-183">Especifica o trabalho agendado a ser alterado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-183">Specifies the scheduled job to be changed.</span></span>
<span data-ttu-id="f6f2f-184">Insira uma variável que contenha objetos **ScheduledJobDefinition** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobDefinition** , como um comando Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-184">Enter a variable that contains **ScheduledJobDefinition** objects or type a command or expression that gets **ScheduledJobDefinition** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="f6f2f-185">Você também pode canalizar um objeto **ScheduledJobDefinition** para **set-ScheduledJob**.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-185">You can also pipe a **ScheduledJobDefinition** object to **Set-ScheduledJob**.</span></span>

<span data-ttu-id="f6f2f-186">Se você especificar vários trabalhos agendados, o **Set-ScheduledJob** faz as mesmas alterações em todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-186">If you specify multiple scheduled jobs, **Set-ScheduledJob** makes the same changes to all jobs.</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-187">-MaxResultCount</span><span class="sxs-lookup"><span data-stu-id="f6f2f-187">-MaxResultCount</span></span>
<span data-ttu-id="f6f2f-188">Especifica quantas entradas de resultado do trabalho são mantidas para o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-188">Specifies how many job result entries are maintained for the scheduled job.</span></span>
<span data-ttu-id="f6f2f-189">O valor padrão é 32.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-189">The default value is 32.</span></span>

<span data-ttu-id="f6f2f-190">O Windows PowerShell salva o histórico de execução e os resultados de cada instância disparada do trabalho agendado no disco.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-190">Windows PowerShell saves the execution history and results of each triggered instance of the scheduled job on disk.</span></span>
<span data-ttu-id="f6f2f-191">O valor desse parâmetro determina o número de resultados de instância de trabalho que são salvas para essa tarefa agendada.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-191">The value of this parameter determines the number of job instance results that are saved for this scheduled job.</span></span>
<span data-ttu-id="f6f2f-192">Quando o número de resultados de instância de trabalho excede esse valor, o Windows PowerShell exclui os resultados da instância de trabalho mais antiga para abrir espaço para os resultados da instância de trabalho mais recente.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-192">When the number of job instance results exceeds this value, Windows PowerShell deletes the results of the oldest job instance to make room for the results of the newest job instance.</span></span>

<span data-ttu-id="f6f2f-193">O histórico de execução do trabalho e os resultados do trabalho são salvos nos diretórios do $home \AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs \\ \<JobName\> \Output \\ \<Timestamp\> no computador em que o trabalho foi criado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-193">The job execution history and job results are saved in the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\\\<JobName\>\Output\\\<Timestamp\> directories on the computer on which the job is created.</span></span>
<span data-ttu-id="f6f2f-194">Para ver o histórico de execução, use o cmdlet Get-Job.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-194">To see the execution history, use the Get-Job cmdlet.</span></span>
<span data-ttu-id="f6f2f-195">Para obter os resultados do trabalho, use o cmdlet Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-195">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="f6f2f-196">O parâmetro *MaxResultCount* define o valor da propriedade ExecutionHistoryLength do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-196">The *MaxResultCount* parameter sets the value of the ExecutionHistoryLength property of the scheduled job.</span></span>

<span data-ttu-id="f6f2f-197">Para excluir os resultados de trabalho e o histórico de execução atuais, use o parâmetro *ClearExecutionHistory*.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-197">To delete the current execution history and job results, use the *ClearExecutionHistory* parameter.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-198">-Name</span><span class="sxs-lookup"><span data-stu-id="f6f2f-198">-Name</span></span>
<span data-ttu-id="f6f2f-199">Especifica um novo nome para o trabalho agendado e instâncias do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-199">Specifies a new name for the scheduled job and instances of the scheduled job.</span></span>
<span data-ttu-id="f6f2f-200">O nome deve ser exclusivo no computador local.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-200">The name must be unique on the local computer.</span></span>

<span data-ttu-id="f6f2f-201">Para identificar o trabalho agendado a ser alterado, use o parâmetro *InputObject* ou redirecione um trabalho agendado de Get-ScheduledJob para **set-ScheduledJob**.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-201">To identify the scheduled job to be changed, use the *InputObject* parameter or pipe a scheduled job from Get-ScheduledJob to **Set-ScheduledJob**.</span></span>

<span data-ttu-id="f6f2f-202">Esse parâmetro não altera os nomes das instâncias de trabalho em disco.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-202">This parameter does not change the names of job instances on disk.</span></span>
<span data-ttu-id="f6f2f-203">Ele afeta somente instâncias de trabalho que foram iniciadas após a conclusão do comando.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-203">It affects only job instances that are started after this command completes.</span></span>

```yaml
Type: System.String
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-204">-PassThru</span><span class="sxs-lookup"><span data-stu-id="f6f2f-204">-PassThru</span></span>
<span data-ttu-id="f6f2f-205">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-205">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="f6f2f-206">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-206">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-207">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="f6f2f-207">-RunAs32</span></span>
<span data-ttu-id="f6f2f-208">Executa o trabalho agendado em um processo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-208">Runs the scheduled job in a 32-bit process.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-209">-RunEvery</span><span class="sxs-lookup"><span data-stu-id="f6f2f-209">-RunEvery</span></span>

<span data-ttu-id="f6f2f-210">Usado para especificar a frequência de execução do trabalho.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-210">Used to specify how often to run the job.</span></span> <span data-ttu-id="f6f2f-211">Por exemplo, use esta opção para executar um trabalho a cada 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-211">For example, use this option to run a job every 15 minutes.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-212">-RunNow</span><span class="sxs-lookup"><span data-stu-id="f6f2f-212">-RunNow</span></span>
<span data-ttu-id="f6f2f-213">Inicia um trabalho imediatamente, assim que o cmdlet **set-ScheduledJob** é executado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-213">Starts a job immediately, as soon as the **Set-ScheduledJob** cmdlet is run.</span></span>
<span data-ttu-id="f6f2f-214">Esse parâmetro elimina a necessidade de disparar o Agendador de tarefas para executar um script do Windows PowerShell imediatamente após o registro e não exige que os usuários criem um disparador que especifica a data e a hora de início.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-214">This parameter eliminates the need to trigger Task Scheduler to run a Windows PowerShell script immediately after registration, and does not require users to create a trigger that specifies a starting date and time.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-215">-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f6f2f-215">-ScheduledJobOption</span></span>
<span data-ttu-id="f6f2f-216">Define opções para o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-216">Sets options for the scheduled job.</span></span>
<span data-ttu-id="f6f2f-217">Insira um objeto **ScheduledJobOptions** , como um que você cria usando o cmdlet New-ScheduledJobOption ou um valor de tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-217">Enter a **ScheduledJobOptions** object, such as one that you create by using the New-ScheduledJobOption cmdlet, or a hash table value.</span></span>

<span data-ttu-id="f6f2f-218">Você pode definir opções para um trabalho agendado ao registrar o trabalho agendado ou usar os cmdlets Set-ScheduledJobOption ou **set-ScheduledJob** para definir ou alterar opções.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-218">You can set options for a scheduled job when you register the scheduled job or use the Set-ScheduledJobOption or **Set-ScheduledJob** cmdlets to set or change options.</span></span>

<span data-ttu-id="f6f2f-219">Muitas das opções e seus valores padrão determinam se e quando um trabalho agendado será executado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-219">Many of the options and their default values determine whether and when a scheduled job runs.</span></span>
<span data-ttu-id="f6f2f-220">Certifique-se de examinar essas opções antes de agendar um trabalho.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-220">Be sure to review these options before scheduling a job.</span></span>
<span data-ttu-id="f6f2f-221">Para obter uma descrição das opções de trabalho agendado, incluindo os valores padrão, consulte New-ScheduledJobOption.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-221">For a description of the scheduled job options, including the default values, see New-ScheduledJobOption.</span></span>

<span data-ttu-id="f6f2f-222">Para enviar uma tabela de hash, use as seguintes chaves.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-222">To submit a hash table, use the following keys.</span></span>
<span data-ttu-id="f6f2f-223">Na tabela de hash a seguir, as chaves são exibidas com seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-223">In the following hash table, the keys are shown with their default values.</span></span>

`@{# Power SettingsStartIfOnBattery=$False;StopIfGoingOnBattery=$True; WakeToRun=$False; # Idle SettingsStartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False;# Security settingsShowInTaskScheduler=$TrueRunElevated=$False;# MiscRunWithoutNetwork=$False;DoNotAllowDemandStart=$False;MultipleInstancePolicy=IgnoreNew# Can be IgnoreNew, Parallel, Queue, StopExisting}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-224">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="f6f2f-224">-ScriptBlock</span></span>
<span data-ttu-id="f6f2f-225">Especifica os comandos que o trabalho agendado executa.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-225">Specifies the commands that the scheduled job runs.</span></span>
<span data-ttu-id="f6f2f-226">Coloque os comandos entre chaves ({}) para criar um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-226">Enclose the commands in braces ( { } ) to create a script block.</span></span>
<span data-ttu-id="f6f2f-227">Para especificar valores padrão para os parâmetros de comando, use o parâmetro *ArgumentList*.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-227">To specify default values for command parameters, use the *ArgumentList* parameter.</span></span>

<span data-ttu-id="f6f2f-228">Cada comando Register-ScheduledJob deve usar o parâmetro *ScriptBlock* ou *FilePath*.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-228">Every Register-ScheduledJob command must use either the *ScriptBlock* or *FilePath* parameters.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-229">-Gatilho</span><span class="sxs-lookup"><span data-stu-id="f6f2f-229">-Trigger</span></span>
<span data-ttu-id="f6f2f-230">Especifica os gatilhos para o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-230">Specifies the triggers for the scheduled job.</span></span>
<span data-ttu-id="f6f2f-231">Insira um ou mais objetos **ScheduledJobTrigger** , como os objetos retornados pelo cmdlet New-JobTrigger ou uma tabela de hash de chaves e valores de gatilho de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-231">Enter one or more **ScheduledJobTrigger** objects, such as the objects that the New-JobTrigger cmdlet returns, or a hash table of job trigger keys and values.</span></span>

<span data-ttu-id="f6f2f-232">Um gatilho de trabalho inicia um trabalho agendado automaticamente em um único tempo ou recorrente agendado ou quando ocorre um evento.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-232">A job trigger starts a scheduled job automatically on a one-time or recurring scheduled or when an event occurs.</span></span>

<span data-ttu-id="f6f2f-233">Disparadores de trabalho são opcionais.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-233">Job triggers are optional.</span></span>
<span data-ttu-id="f6f2f-234">Você pode adicionar um gatilho ao criar o trabalho agendado, usar os cmdlets Add-JobTrigger ou **set-ScheduledJob** para adicionar gatilhos posteriormente ou usar o cmdlet Start-Job para iniciar o trabalho agendado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-234">You can add a trigger when you create the scheduled job, use the Add-JobTrigger or **Set-ScheduledJob** cmdlets to add triggers later, or use the Start-Job cmdlet to start the scheduled job immediately.</span></span>
<span data-ttu-id="f6f2f-235">Você também pode criar e manter um trabalho agendado sem nenhum disparador de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-235">You can also create and maintain a scheduled job that has no job triggers.</span></span>

<span data-ttu-id="f6f2f-236">Para enviar uma tabela de hash, use as seguintes chaves.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-236">To submit a hash table, use the following keys.</span></span>

<span data-ttu-id="f6f2f-237">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (ou qualquer cadeia de hora válida); `DaysOfWeek="Monday", "Wednesday"` (ou qualquer combinação de nomes de dias); `Interval=2` (ou qualquer intervalo de frequência válido); `RandomDelay="30minutes"` (ou qualquer cadeia de caracteres TimeSpan válida); `User="Domain1\User01"` (ou qualquer usuário válido; usado somente com o valor de frequência AtLogon)</span><span class="sxs-lookup"><span data-stu-id="f6f2f-237">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (or any valid time string); `DaysOfWeek="Monday", "Wednesday"` (or any combination of day names); `Interval=2` (or any valid frequency interval); `RandomDelay="30minutes"` (or any valid timespan string); `User="Domain1\User01"` (or any valid user; used only with the AtLogon frequency value)</span></span>

<span data-ttu-id="f6f2f-238">}</span><span class="sxs-lookup"><span data-stu-id="f6f2f-238">}</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f6f2f-239">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f6f2f-239">CommonParameters</span></span>
<span data-ttu-id="f6f2f-240">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-240">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f6f2f-241">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f6f2f-241">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f6f2f-242">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f6f2f-242">INPUTS</span></span>

### <span data-ttu-id="f6f2f-243">Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="f6f2f-243">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="f6f2f-244">Você pode direcionar trabalhos agendados para **Set-ScheduledJob**.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-244">You can pipe scheduled jobs to **Set-ScheduledJob**.</span></span>

## <span data-ttu-id="f6f2f-245">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f6f2f-245">OUTPUTS</span></span>

### <span data-ttu-id="f6f2f-246">Nenhum ou Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="f6f2f-246">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="f6f2f-247">Se você usar o parâmetro *Passthru* , **Set-ScheduledJob** retorna o trabalho agendado que foi alterado.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-247">If you use the *Passthru* parameter, **Set-ScheduledJob** returns the scheduled job that was changed.</span></span>
<span data-ttu-id="f6f2f-248">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="f6f2f-248">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f6f2f-249">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f6f2f-249">NOTES</span></span>

## <span data-ttu-id="f6f2f-250">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f6f2f-250">RELATED LINKS</span></span>

[<span data-ttu-id="f6f2f-251">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f6f2f-251">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="f6f2f-252">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f6f2f-252">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="f6f2f-253">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f6f2f-253">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="f6f2f-254">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f6f2f-254">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="f6f2f-255">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f6f2f-255">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="f6f2f-256">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f6f2f-256">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="f6f2f-257">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f6f2f-257">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="f6f2f-258">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f6f2f-258">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="f6f2f-259">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f6f2f-259">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="f6f2f-260">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f6f2f-260">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="f6f2f-261">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f6f2f-261">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="f6f2f-262">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f6f2f-262">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="f6f2f-263">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f6f2f-263">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="f6f2f-264">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f6f2f-264">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="f6f2f-265">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f6f2f-265">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="f6f2f-266">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f6f2f-266">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
