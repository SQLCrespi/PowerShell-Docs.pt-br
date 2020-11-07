---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-PSSession
ms.openlocfilehash: e9b99b824a0ffe59e4572a57998010667788b59d
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345928"
---
# <span data-ttu-id="809b7-103">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="809b7-103">Receive-PSSession</span></span>

## <span data-ttu-id="809b7-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="809b7-104">SYNOPSIS</span></span>

<span data-ttu-id="809b7-105">Obtém resultados de comandos em sessões desconectadas</span><span class="sxs-lookup"><span data-stu-id="809b7-105">Gets results of commands in disconnected sessions</span></span>

## <span data-ttu-id="809b7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="809b7-106">SYNTAX</span></span>

### <span data-ttu-id="809b7-107">Sessão (padrão)</span><span class="sxs-lookup"><span data-stu-id="809b7-107">Session (Default)</span></span>

```
Receive-PSSession [-Session] <PSSession> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="809b7-108">ID</span><span class="sxs-lookup"><span data-stu-id="809b7-108">Id</span></span>

```
Receive-PSSession [-Id] <Int32> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="809b7-109">ComputerSessionName</span><span class="sxs-lookup"><span data-stu-id="809b7-109">ComputerSessionName</span></span>

```
Receive-PSSession [-ComputerName] <String> [-ApplicationName <String>] [-ConfigurationName <String>]
 -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-Port <Int32>]
 [-UseSSL] [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="809b7-110">ComputerInstanceId</span><span class="sxs-lookup"><span data-stu-id="809b7-110">ComputerInstanceId</span></span>

```
Receive-PSSession [-ComputerName] <String> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-Port <Int32>]
 [-UseSSL] [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="809b7-111">ConnectionUriSessionName</span><span class="sxs-lookup"><span data-stu-id="809b7-111">ConnectionUriSessionName</span></span>

```
Receive-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri> [-AllowRedirection]
 -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="809b7-112">ConnectionUriInstanceId</span><span class="sxs-lookup"><span data-stu-id="809b7-112">ConnectionUriInstanceId</span></span>

```
Receive-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri> [-AllowRedirection]
 -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="809b7-113">InstanceId</span><span class="sxs-lookup"><span data-stu-id="809b7-113">InstanceId</span></span>

```
Receive-PSSession -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="809b7-114">SessionName</span><span class="sxs-lookup"><span data-stu-id="809b7-114">SessionName</span></span>

```
Receive-PSSession -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="809b7-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="809b7-115">DESCRIPTION</span></span>

<span data-ttu-id="809b7-116">O `Receive-PSSession` cmdlet obtém os resultados de comandos em execução em sessões do PowerShell ( **PSSession** ) que foram desconectadas.</span><span class="sxs-lookup"><span data-stu-id="809b7-116">The `Receive-PSSession` cmdlet gets the results of commands running in PowerShell sessions ( **PSSession** ) that were disconnected.</span></span> <span data-ttu-id="809b7-117">Se a sessão estiver conectada no momento, `Receive-PSSession` o obterá os resultados dos comandos que estavam em execução quando a sessão foi desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-117">If the session is currently connected, `Receive-PSSession` gets the results of commands that were running when the session was disconnected.</span></span> <span data-ttu-id="809b7-118">Se a sessão ainda estiver desconectada, conecta-se `Receive-PSSession` à sessão, retoma todos os comandos que foram suspensos e obtém os resultados dos comandos em execução na sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-118">If the session is still disconnected, `Receive-PSSession` connects to the session, resumes any commands that were suspended, and gets the results of commands running in the session.</span></span>

<span data-ttu-id="809b7-119">Esse cmdlet foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="809b7-119">This cmdlet was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="809b7-120">Você pode usar um `Receive-PSSession` , além de ou em vez de um `Connect-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="809b7-120">You can use a `Receive-PSSession` in addition to or instead of a `Connect-PSSession` command.</span></span>
<span data-ttu-id="809b7-121">`Receive-PSSession` pode se conectar a qualquer sessão desconectada ou reconectada que foi iniciada em outras sessões ou em outros computadores.</span><span class="sxs-lookup"><span data-stu-id="809b7-121">`Receive-PSSession` can connect to any disconnected or reconnected session that was started in other sessions or on other computers.</span></span>

<span data-ttu-id="809b7-122">`Receive-PSSession` funciona em **PSSessions** que foram desconectadas intencionalmente usando o `Disconnect-PSSession` cmdlet ou o `Invoke-Command` parâmetro **InDisconnectedSession** .</span><span class="sxs-lookup"><span data-stu-id="809b7-122">`Receive-PSSession` works on **PSSessions** that were disconnected intentionally using the `Disconnect-PSSession` cmdlet or the `Invoke-Command` **InDisconnectedSession** parameter.</span></span> <span data-ttu-id="809b7-123">Ou desconectado de forma não intencional por uma interrupção de rede.</span><span class="sxs-lookup"><span data-stu-id="809b7-123">Or disconnected unintentionally by a network interruption.</span></span>

<span data-ttu-id="809b7-124">Se você usar o `Receive-PSSession` cmdlet para se conectar a uma sessão na qual nenhum comando está em execução ou suspenso, `Receive-PSSession` o se conectará à sessão, mas não retornará nenhuma saída ou erro.</span><span class="sxs-lookup"><span data-stu-id="809b7-124">If you use the `Receive-PSSession` cmdlet to connect to a session in which no commands are running or suspended, `Receive-PSSession` connects to the session, but returns no output or errors.</span></span>

<span data-ttu-id="809b7-125">Para obter mais informações sobre o recurso de Sessões desconectadas, consulte [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).</span><span class="sxs-lookup"><span data-stu-id="809b7-125">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="809b7-126">Alguns exemplos usam nivelamento para reduzir o tamanho da linha e melhorar a legibilidade.</span><span class="sxs-lookup"><span data-stu-id="809b7-126">Some examples use splatting to reduce the line length and improve readability.</span></span> <span data-ttu-id="809b7-127">Para obter mais informações, consulte [about_Splatting](./About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="809b7-127">For more information, see [about_Splatting](./About/about_Splatting.md).</span></span>

## <span data-ttu-id="809b7-128">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="809b7-128">EXAMPLES</span></span>

### <span data-ttu-id="809b7-129">Exemplo 1: conectar-se a uma PSSession</span><span class="sxs-lookup"><span data-stu-id="809b7-129">Example 1: Connect to a PSSession</span></span>

<span data-ttu-id="809b7-130">Este exemplo se conecta a uma sessão em um computador remoto e obtém os resultados de comandos que estão sendo executados em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-130">This example connects to a session on a remote computer and gets the results of commands that are running in a session.</span></span>

```powershell
Receive-PSSession -ComputerName Server01 -Name ITTask
```

<span data-ttu-id="809b7-131">O `Receive-PSSession` especifica o computador remoto com o parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="809b7-131">The `Receive-PSSession` specifies the remote computer with the **ComputerName** parameter.</span></span> <span data-ttu-id="809b7-132">O parâmetro **Name** identifica a sessão ITTask no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="809b7-132">The **Name** parameter identifies the ITTask session on the Server01 computer.</span></span> <span data-ttu-id="809b7-133">O exemplo obtém os resultados de comandos que estavam em execução na sessão ITTask.</span><span class="sxs-lookup"><span data-stu-id="809b7-133">The example gets the results of commands that were running in the ITTask session.</span></span>

<span data-ttu-id="809b7-134">Como o comando não usa o parâmetro **outtarget** , os resultados aparecem na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="809b7-134">Because the command doesn't use the **OutTarget** parameter, the results appear on the command line.</span></span>

### <span data-ttu-id="809b7-135">Exemplo 2: obter resultados de todos os comandos em sessões desconectadas</span><span class="sxs-lookup"><span data-stu-id="809b7-135">Example 2: Get results of all commands on disconnected sessions</span></span>

<span data-ttu-id="809b7-136">Este exemplo obtém os resultados de todos os comandos em execução em todas as sessões desconectadas em dois computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="809b7-136">This example gets the results of all commands running in all disconnected sessions on two remote computers.</span></span>

<span data-ttu-id="809b7-137">Se alguma sessão não tiver sido desconectada ou não estiver executando comandos, `Receive-PSSession` o não se conectará à sessão e não retornará nenhuma saída ou erro.</span><span class="sxs-lookup"><span data-stu-id="809b7-137">If any session wasn't disconnected or isn't running commands, `Receive-PSSession` doesn't connect to the session and doesn't return any output or errors.</span></span>

```powershell
Get-PSSession -ComputerName Server01, Server02 | Receive-PSSession
```

<span data-ttu-id="809b7-138">`Get-PSSession` usa o parâmetro **ComputerName** para especificar os computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="809b7-138">`Get-PSSession` uses the **ComputerName** parameter to specify the remote computers.</span></span> <span data-ttu-id="809b7-139">Os objetos são enviados ao pipeline para `Receive-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="809b7-139">The objects are sent down the pipeline to `Receive-PSSession`.</span></span>

### <span data-ttu-id="809b7-140">Exemplo 3: obter os resultados de um script em execução em uma sessão</span><span class="sxs-lookup"><span data-stu-id="809b7-140">Example 3: Get the results of a script running in a session</span></span>

<span data-ttu-id="809b7-141">Este exemplo usa o `Receive-PSSession` cmdlet para obter os resultados de um script que estava sendo executado na sessão de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="809b7-141">This example uses the `Receive-PSSession` cmdlet to get the results of a script that was running in a remote computer's session.</span></span>

```powershell
$parms = @{
  ComputerName = "Server01"
  Name = "ITTask"
  OutTarget = "Job"
  JobName = "ITTaskJob01"
  Credential = "Domain01\Admin01"
}
Receive-PSSession @parms
```

```Output
Id     Name            State         HasMoreData     Location
--     ----            -----         -----------     --------
16     ITTaskJob01     Running       True            Server01
```

<span data-ttu-id="809b7-142">O comando usa os parâmetros **ComputerName** e **Name** para identificar a sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-142">The command uses the **ComputerName** and **Name** parameters to identify the disconnected session.</span></span>
<span data-ttu-id="809b7-143">Ele usa o parâmetro de **destino** com um valor de trabalho para direcionar `Receive-PSSession` para retornar os resultados como um trabalho.</span><span class="sxs-lookup"><span data-stu-id="809b7-143">It uses the **OutTarget** parameter with a value of Job to direct `Receive-PSSession` to return the results as a job.</span></span> <span data-ttu-id="809b7-144">O parâmetro **JobName** especifica um nome para o trabalho na sessão reconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-144">The **JobName** parameter specifies a name for the job in the reconnected session.</span></span>
<span data-ttu-id="809b7-145">O parâmetro **Credential** executa o `Receive-PSSession` comando usando as permissões de um administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="809b7-145">The **Credential** parameter runs the `Receive-PSSession` command using the permissions of a domain administrator.</span></span>

<span data-ttu-id="809b7-146">A saída mostra que `Receive-PSSession` retornou os resultados como um trabalho na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="809b7-146">The output shows that `Receive-PSSession` returned the results as a job in the current session.</span></span> <span data-ttu-id="809b7-147">Para obter os resultados do trabalho, use um `Receive-Job` comando</span><span class="sxs-lookup"><span data-stu-id="809b7-147">To get the job results, use a `Receive-Job` command</span></span>

### <span data-ttu-id="809b7-148">Exemplo 4: obter resultados após uma interrupção de rede</span><span class="sxs-lookup"><span data-stu-id="809b7-148">Example 4: Get results after a network outage</span></span>

<span data-ttu-id="809b7-149">Este exemplo usa o `Receive-PSSession` cmdlet para obter os resultados de um trabalho depois que uma interrupção de rede interrompe uma conexão de sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-149">This example uses the `Receive-PSSession` cmdlet to get the results of a job after a network outage disrupts a session connection.</span></span> <span data-ttu-id="809b7-150">O PowerShell tenta automaticamente reconectar a sessão uma vez por segundo nos próximos quatro minutos e abandonar o esforço somente se todas as tentativas no intervalo de quatro minutos falharem.</span><span class="sxs-lookup"><span data-stu-id="809b7-150">PowerShell automatically attempts to reconnect the session once per second for the next four minutes and abandons the effort only if all attempts in the four-minute interval fail.</span></span>

```
PS> $s = New-PSSession -ComputerName Server01 -Name AD -ConfigurationName ADEndpoint
PS> $s

Id  Name   ComputerName    State        ConfigurationName     Availability
--  ----   ------------    -----        -----------------     ------------
8   AD      Server01       Opened       ADEndpoint               Available


PS> Invoke-Command -Session $s -FilePath \\Server12\Scripts\SharedScripts\New-ADResolve.ps1

Running "New-ADResolve.ps1"

# Network outage
# Restart local computer
# Network access is not re-established within 4 minutes


PS> Get-PSSession -ComputerName Server01

Id  Name   ComputerName    State          ConfigurationName      Availability
--  ----   ------------    -----          -----------------      ------------
1  Backup  Server01        Disconnected   Microsoft.PowerShell           None
8  AD      Server01        Disconnected   ADEndpoint                     None


PS> Receive-PSSession -ComputerName Server01 -Name AD -OutTarget Job -JobName AD

Job Id   Name      State         HasMoreData     Location
--       ----      -----         -----------     --------
16       ADJob     Running       True            Server01


PS> Get-PSSession -ComputerName Server01

Id  Name    ComputerName    State         ConfigurationName     Availability
--  ----    ------------    -----         -----------------     ------------
1  Backup   Server01        Disconnected  Microsoft.PowerShell          Busy
8  AD       Server01        Opened        ADEndpoint               Available
```

<span data-ttu-id="809b7-151">O `New-PSSession` cmdlet cria uma sessão no computador Server01 e salva a sessão na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="809b7-151">The `New-PSSession` cmdlet creates a session on the Server01 computer and saves the session in the `$s` variable.</span></span> <span data-ttu-id="809b7-152">A `$s` variável exibe que o **estado** é aberto e a **disponibilidade** está disponível.</span><span class="sxs-lookup"><span data-stu-id="809b7-152">The `$s` variable displays that the **State** is Opened and the **Availability** is Available.</span></span> <span data-ttu-id="809b7-153">Esses valores indicam que você está conectado à sessão e pode executar comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-153">These values indicate that you're connected to the session and can run commands in the session.</span></span>

<span data-ttu-id="809b7-154">O `Invoke-Command` cmdlet executa um script na sessão na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="809b7-154">The `Invoke-Command` cmdlet runs a script in the session in the `$s` variable.</span></span> <span data-ttu-id="809b7-155">O script começa a ser executado e a retornar dados, mas ocorre uma queda de rede que interrompe a sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-155">The script begins to run and return data, but a network outage occurs that interrupts the session.</span></span> <span data-ttu-id="809b7-156">O usuário precisa sair da sessão e reiniciar o computador local.</span><span class="sxs-lookup"><span data-stu-id="809b7-156">The user has to exit the session and restart the local computer.</span></span>

<span data-ttu-id="809b7-157">Quando o computador é reiniciado, o usuário inicia o PowerShell e executa um `Get-PSSession` comando para obter sessões no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="809b7-157">When the computer restarts, the user starts PowerShell and runs a `Get-PSSession` command to get sessions on the Server01 computer.</span></span> <span data-ttu-id="809b7-158">A saída mostra que a sessão do **ad** ainda existe no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="809b7-158">The output shows that the **AD** session still exists on the Server01 computer.</span></span> <span data-ttu-id="809b7-159">O **estado** indica que a sessão do **ad** está desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-159">The **State** indicates that the **AD** session is disconnected.</span></span> <span data-ttu-id="809b7-160">O valor de **disponibilidade** de nenhum, indica que a sessão não está conectada a todas as sessões de cliente.</span><span class="sxs-lookup"><span data-stu-id="809b7-160">The **Availability** value of None, indicates that the session isn't connected to any client sessions.</span></span>

<span data-ttu-id="809b7-161">O `Receive-PSSession` cmdlet se reconecta à sessão do **ad** e obtém os resultados do script que foi executado na sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-161">The `Receive-PSSession` cmdlet reconnects to the **AD** session and gets the results of the script that ran in the session.</span></span> <span data-ttu-id="809b7-162">O comando usa o parâmetro **outtarget** para solicitar os resultados em um trabalho chamado **ADJob**.</span><span class="sxs-lookup"><span data-stu-id="809b7-162">The command uses the **OutTarget** parameter to request the results in a job named **ADJob**.</span></span> <span data-ttu-id="809b7-163">O comando retorna um objeto de trabalho e a saída indica que o script ainda está em execução.</span><span class="sxs-lookup"><span data-stu-id="809b7-163">The command returns a job object and the output indicates that the script is still running.</span></span>

<span data-ttu-id="809b7-164">O `Get-PSSession` cmdlet é usado para verificar o estado do trabalho.</span><span class="sxs-lookup"><span data-stu-id="809b7-164">The `Get-PSSession` cmdlet is used to check the job state.</span></span> <span data-ttu-id="809b7-165">A saída confirma que o `Receive-PSSession` cmdlet foi reconectado à sessão do **ad** , que agora está aberta e disponível para comandos.</span><span class="sxs-lookup"><span data-stu-id="809b7-165">The output confirms that the `Receive-PSSession` cmdlet reconnected to the **AD** session, which is now open and available for commands.</span></span> <span data-ttu-id="809b7-166">E o script retomou a execução e está obtendo os resultados do script.</span><span class="sxs-lookup"><span data-stu-id="809b7-166">And, the script resumed execution and is getting the script results.</span></span>

### <span data-ttu-id="809b7-167">Exemplo 5: reconectar a sessões desconectadas</span><span class="sxs-lookup"><span data-stu-id="809b7-167">Example 5: Reconnect to disconnected sessions</span></span>

<span data-ttu-id="809b7-168">Este exemplo usa o `Receive-PSSession` cmdlet para se reconectar a sessões que foram intencionalmente desconectadas e obter os resultados de trabalhos que estavam em execução nas sessões.</span><span class="sxs-lookup"><span data-stu-id="809b7-168">This example uses the `Receive-PSSession` cmdlet to reconnect to sessions that were intentionally disconnected and get the results of jobs that were running in the sessions.</span></span>

```
PS> $parms = @{
      InDisconnectedSession = $True
      ComputerName = "Server01", "Server02", "Server30"
      FilePath = "\\Server12\Scripts\SharedScripts\Get-BugStatus.ps1"
      Name = "BugStatus"
      SessionOption = @{IdleTimeout = 86400000}
      ConfigurationName = "ITTasks"
    }
PS> Invoke-Command @parms
PS> Exit


PS> $s = Get-PSSession -ComputerName Server01, Server02, Server30 -Name BugStatus
PS> $s

Id  Name   ComputerName    State         ConfigurationName     Availability
--  ----   ------------    -----         -----------------     ------------
1  ITTask  Server01        Disconnected  ITTasks                       None
8  ITTask  Server02        Disconnected  ITTasks                       None
2  ITTask  Server30        Disconnected  ITTasks                       None


PS> $Results = Receive-PSSession -Session $s
PS> $s

Id  Name   ComputerName    State         ConfigurationName     Availability
--  ----   ------------    -----         -----------------     ------------
1  ITTask  Server01        Opened        ITTasks                  Available
8  ITTask  Server02        Opened        ITTasks                  Available
2  ITTask  Server30        Opened        ITTasks                  Available


PS> $Results

Bug Report - Domain 01
----------------------
ComputerName          BugCount          LastUpdated
--------------        ---------         ------------
Server01              121               Friday, December 30, 2011 5:03:34 PM
```

<span data-ttu-id="809b7-169">O `Invoke-Command` cmdlet executa um script em três computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="809b7-169">The `Invoke-Command` cmdlet runs a script on three remote computers.</span></span> <span data-ttu-id="809b7-170">Como o script coleta e resume dados de vários bancos de dado, ele geralmente leva o script um tempo estendido para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="809b7-170">Because the script gathers and summarizes data from multiple databases, it often takes the script an extended time to finish.</span></span> <span data-ttu-id="809b7-171">O comando usa o parâmetro **InDisconnectedSession** que inicia os scripts e, em seguida, desconecta imediatamente as sessões.</span><span class="sxs-lookup"><span data-stu-id="809b7-171">The command uses the **InDisconnectedSession** parameter that starts the scripts and then immediately disconnects the sessions.</span></span> <span data-ttu-id="809b7-172">O parâmetro **SessionOption** estende o valor de **IdleTimeout** da sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-172">The **SessionOption** parameter extends the **IdleTimeout** value of the disconnected session.</span></span> <span data-ttu-id="809b7-173">As sessões desconectadas são consideradas ociosas desde o momento em que são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="809b7-173">Disconnected sessions are considered idle from the moment they're disconnected.</span></span> <span data-ttu-id="809b7-174">É importante definir o tempo limite ocioso por tempo suficiente para que os comandos possam ser concluídos e você possa se reconectar à sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-174">It's important to set the idle time-out for long enough so that the commands can complete and you can reconnect to the session.</span></span> <span data-ttu-id="809b7-175">Você pode definir o **IdleTimeout** somente quando criar a **PSSession** e alterá-la somente quando desconectar dela.</span><span class="sxs-lookup"><span data-stu-id="809b7-175">You can set the **IdleTimeout** only when you create the **PSSession** and change it only when you disconnect from it.</span></span> <span data-ttu-id="809b7-176">Não é possível alterar o valor de **IdleTimeout** quando você se conecta a uma **PSSession** ou recebe seus resultados.</span><span class="sxs-lookup"><span data-stu-id="809b7-176">You can't change the **IdleTimeout** value when you connect to a **PSSession** or receiving its results.</span></span> <span data-ttu-id="809b7-177">Depois de executar o comando, o usuário sai do PowerShell e fecha o computador.</span><span class="sxs-lookup"><span data-stu-id="809b7-177">After running the command, the user exits PowerShell and closes the computer.</span></span>

<span data-ttu-id="809b7-178">No dia seguinte, o usuário retoma o Windows, inicia o PowerShell e usa `Get-PSSession` para obter as sessões em que os scripts estavam em execução.</span><span class="sxs-lookup"><span data-stu-id="809b7-178">The next day, the user resumes Windows, starts PowerShell, and uses `Get-PSSession` to get the sessions in which the scripts were running.</span></span> <span data-ttu-id="809b7-179">O comando identifica as sessões pelo nome do computador, nome da sessão e o nome da configuração da sessão e salva as sessões na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="809b7-179">The command identifies the sessions by the computer name, session name, and the name of the session configuration and saves the sessions in the `$s` variable.</span></span> <span data-ttu-id="809b7-180">O valor da `$s` variável é exibido e mostra que as sessões estão desconectadas, mas não estão ocupadas.</span><span class="sxs-lookup"><span data-stu-id="809b7-180">The value of the `$s` variable is displayed and shows that the sessions are disconnected, but aren't busy.</span></span>

<span data-ttu-id="809b7-181">O `Receive-PSSession` cmdlet se conecta às sessões na `$s` variável e obtém seus resultados.</span><span class="sxs-lookup"><span data-stu-id="809b7-181">The `Receive-PSSession` cmdlet connects to the sessions in the `$s` variable and gets their results.</span></span>
<span data-ttu-id="809b7-182">O comando salva os resultados na `$Results` variável.</span><span class="sxs-lookup"><span data-stu-id="809b7-182">The command saves the results in the `$Results` variable.</span></span> <span data-ttu-id="809b7-183">A `$s` variável é exibida e mostra que as sessões estão conectadas e disponíveis para comandos.</span><span class="sxs-lookup"><span data-stu-id="809b7-183">The `$s` variable is displayed and shows that the sessions are connected and available for commands.</span></span>

<span data-ttu-id="809b7-184">Os resultados do script na `$Results` variável são exibidos no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="809b7-184">The script results in the `$Results` variable are displayed in the PowerShell console.</span></span> <span data-ttu-id="809b7-185">Se qualquer um dos resultados for inesperado, o usuário poderá executar comandos nas sessões para investigar a causa raiz.</span><span class="sxs-lookup"><span data-stu-id="809b7-185">If any of the results are unexpected, the user can run commands in the sessions to investigate the root cause.</span></span>

### <span data-ttu-id="809b7-186">Exemplo 6: executando um trabalho em uma sessão desconectada</span><span class="sxs-lookup"><span data-stu-id="809b7-186">Example 6: Running a job in a disconnected session</span></span>

<span data-ttu-id="809b7-187">Este exemplo mostra o que acontece com um trabalho que está sendo executado em uma sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-187">This example shows what happens to a job that's running in a disconnected session.</span></span>

```
PS> $s = New-PSSession -ComputerName Server01 -Name Test
PS> $j = Invoke-Command -Session $s { 1..1500 | Foreach-Object {"Return $_"; sleep 30}} -AsJob
PS> $j

Id     Name           State         HasMoreData     Location
--     ----           -----         -----------     --------
16     Job1           Running       True            Server01


PS> $s | Disconnect-PSSession

Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1  Test   Server01        Disconnected  Microsoft.PowerShell          None


PS> $j

Id     Name           State         HasMoreData     Location
--     ----           -----         -----------     --------
16     Job1           Disconnected  True            Server01


PS> Receive-Job $j -Keep

Return 1
Return 2


PS> $s2 = Connect-PSSession -ComputerName Server01 -Name Test
PS> $j2 = Receive-PSSession -ComputerName Server01 -Name Test
PS> Receive-Job $j

Return 3
Return 4
```

<span data-ttu-id="809b7-188">O `New-PSSession` cmdlet cria a sessão de teste no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="809b7-188">The `New-PSSession` cmdlet creates the Test session on the Server01 computer.</span></span> <span data-ttu-id="809b7-189">O comando salva a sessão na variável `$s`.</span><span class="sxs-lookup"><span data-stu-id="809b7-189">The command saves the session in the `$s` variable.</span></span>

<span data-ttu-id="809b7-190">O `Invoke-Command` cmdlet executa um comando na sessão na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="809b7-190">The `Invoke-Command` cmdlet runs a command in the session in the `$s` variable.</span></span> <span data-ttu-id="809b7-191">O comando usa o parâmetro **AsJob** para executar o comando como um trabalho e cria o objeto de trabalho na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="809b7-191">The command uses the **AsJob** parameter to run the command as a job and creates the job object in the current session.</span></span>
<span data-ttu-id="809b7-192">O comando retorna um objeto de trabalho que é salvo na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="809b7-192">The command returns a job object that's saved in the `$j` variable.</span></span> <span data-ttu-id="809b7-193">A `$j` variável exibe o objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="809b7-193">The `$j` variable displays the job object.</span></span>

<span data-ttu-id="809b7-194">O objeto de sessão na `$s` variável é enviado ao pipeline para `Disconnect-PSSession` e a sessão é desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-194">The session object in the `$s` variable is sent down the pipeline to `Disconnect-PSSession` and the session is disconnected.</span></span>

<span data-ttu-id="809b7-195">A `$j` variável é exibida e mostra o efeito de desconectar o objeto de trabalho na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="809b7-195">The `$j` variable is displayed and shows the effect of disconnecting the job object in the `$j` variable.</span></span> <span data-ttu-id="809b7-196">O estado do trabalho agora é Desconectado.</span><span class="sxs-lookup"><span data-stu-id="809b7-196">The job state is now Disconnected.</span></span>

<span data-ttu-id="809b7-197">O `Receive-Job` é executado no trabalho na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="809b7-197">The `Receive-Job` is run on the job in the `$j` variable.</span></span> <span data-ttu-id="809b7-198">A saída mostra que o trabalho começou a retornar a saída antes de a sessão e o trabalho serem desconectados.</span><span class="sxs-lookup"><span data-stu-id="809b7-198">The output shows that the job began to return output before the session and the job were disconnected.</span></span>

<span data-ttu-id="809b7-199">O `Connect-PSSession` cmdlet é executado na mesma sessão de cliente.</span><span class="sxs-lookup"><span data-stu-id="809b7-199">The `Connect-PSSession` cmdlet is run in the same client session.</span></span> <span data-ttu-id="809b7-200">O comando reconecta-se à sessão de teste no computador Server01 e salva a sessão na `$s2` variável.</span><span class="sxs-lookup"><span data-stu-id="809b7-200">The command reconnects to the Test session on the Server01 computer and saves the session in the `$s2` variable.</span></span>

<span data-ttu-id="809b7-201">O `Receive-PSSession` cmdlet obtém os resultados do trabalho que estava sendo executado na sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-201">The `Receive-PSSession` cmdlet gets the results of the job that was running in the session.</span></span> <span data-ttu-id="809b7-202">Como o comando é executado na mesma sessão, `Receive-PSSession` o retorna os resultados como um trabalho por padrão e reutiliza o mesmo objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="809b7-202">Because the command is run in the same session, `Receive-PSSession` returns the results as a job by default and reuses the same job object.</span></span> <span data-ttu-id="809b7-203">O comando salva o trabalho na `$j2` variável.</span><span class="sxs-lookup"><span data-stu-id="809b7-203">The command saves the job in the `$j2` variable.</span></span> <span data-ttu-id="809b7-204">O `Receive-Job` cmdlet obtém os resultados do trabalho na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="809b7-204">The `Receive-Job` cmdlet gets the results of the job in the `$j` variable.</span></span>

## <span data-ttu-id="809b7-205">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="809b7-205">PARAMETERS</span></span>

### <span data-ttu-id="809b7-206">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="809b7-206">-AllowRedirection</span></span>

<span data-ttu-id="809b7-207">Indica que esse cmdlet permite o redirecionamento dessa conexão para um Uniform Resource Identifier alternativo (URI).</span><span class="sxs-lookup"><span data-stu-id="809b7-207">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="809b7-208">Quando você usa o parâmetro **ConnectionURI** , o destino remoto pode retornar uma instrução para redirecionar para um URI diferente.</span><span class="sxs-lookup"><span data-stu-id="809b7-208">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="809b7-209">Por padrão, o PowerShell não redireciona as conexões, mas você pode usar esse parâmetro para habilitá-la a redirecionar a conexão.</span><span class="sxs-lookup"><span data-stu-id="809b7-209">By default, PowerShell doesn't redirect connections, but you can use this parameter to enable it to redirect the connection.</span></span>

<span data-ttu-id="809b7-210">É possível também limitar o número de vezes que a conexão é redirecionada alterando o valor da opção de sessão **MaximumConnectionRedirectionCount**.</span><span class="sxs-lookup"><span data-stu-id="809b7-210">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="809b7-211">Use o parâmetro **MaximumRedirection** do `New-PSSessionOption` cmdlet ou defina a propriedade **MaximumConnectionRedirectionCount** da variável de `$PSSessionOption` preferência.</span><span class="sxs-lookup"><span data-stu-id="809b7-211">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="809b7-212">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="809b7-212">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-213">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="809b7-213">-ApplicationName</span></span>

<span data-ttu-id="809b7-214">Especifica um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="809b7-214">Specifies an application.</span></span> <span data-ttu-id="809b7-215">Esse cmdlet se conecta somente a sessões que usam o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="809b7-215">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="809b7-216">Insira o segmento de nome de aplicativo do URI de conexão.</span><span class="sxs-lookup"><span data-stu-id="809b7-216">Enter the application name segment of the connection URI.</span></span> <span data-ttu-id="809b7-217">Por exemplo, no seguinte URI de conexão, WSMan é o nome do aplicativo: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="809b7-217">For example, in the following connection URI, WSMan is the application name: `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="809b7-218">O nome de aplicativo de uma sessão é armazenado na propriedade **Runspace.ConnectionInfo.AppName** da sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-218">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="809b7-219">O valor do parâmetro é usado para selecionar e filtrar sessões.</span><span class="sxs-lookup"><span data-stu-id="809b7-219">The parameter's value is used to select and filter sessions.</span></span> <span data-ttu-id="809b7-220">Ele não altera o aplicativo usado pela sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-220">It doesn't change the application that the session uses.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-221">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="809b7-221">-Authentication</span></span>

<span data-ttu-id="809b7-222">Especifica o mecanismo usado para autenticar as credenciais do usuário no comando para se reconectar a uma sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-222">Specifies the mechanism that's used to authenticate the user credentials in the command to reconnect to a disconnected session.</span></span> <span data-ttu-id="809b7-223">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="809b7-223">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="809b7-224">Padrão</span><span class="sxs-lookup"><span data-stu-id="809b7-224">Default</span></span>
- <span data-ttu-id="809b7-225">Basic</span><span class="sxs-lookup"><span data-stu-id="809b7-225">Basic</span></span>
- <span data-ttu-id="809b7-226">CredSSP</span><span class="sxs-lookup"><span data-stu-id="809b7-226">Credssp</span></span>
- <span data-ttu-id="809b7-227">Digest</span><span class="sxs-lookup"><span data-stu-id="809b7-227">Digest</span></span>
- <span data-ttu-id="809b7-228">Kerberos</span><span class="sxs-lookup"><span data-stu-id="809b7-228">Kerberos</span></span>
- <span data-ttu-id="809b7-229">Negotiate</span><span class="sxs-lookup"><span data-stu-id="809b7-229">Negotiate</span></span>
- <span data-ttu-id="809b7-230">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="809b7-230">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="809b7-231">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="809b7-231">The default value is Default.</span></span>

<span data-ttu-id="809b7-232">Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="809b7-232">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="809b7-233">A autenticação do Credential Security Support Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, é projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="809b7-233">Credential Security Support Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="809b7-234">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="809b7-234">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="809b7-235">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="809b7-235">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-236">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="809b7-236">-CertificateThumbprint</span></span>

<span data-ttu-id="809b7-237">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para se conectar à sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-237">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="809b7-238">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="809b7-238">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="809b7-239">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="809b7-239">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="809b7-240">Os certificados podem ser mapeados somente para contas de usuário locais e não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="809b7-240">Certificates can be mapped only to local user accounts, and don't work with domain accounts.</span></span>

<span data-ttu-id="809b7-241">Para obter uma impressão digital do certificado, use um `Get-Item` `Get-ChildItem` comando ou na `Cert:` unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="809b7-241">To get a certificate thumbprint, use a `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-242">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="809b7-242">-ComputerName</span></span>

<span data-ttu-id="809b7-243">Especifica o computador no qual a sessão desconectada está armazenada.</span><span class="sxs-lookup"><span data-stu-id="809b7-243">Specifies the computer on which the disconnected session is stored.</span></span> <span data-ttu-id="809b7-244">As sessões são armazenadas no computador que está no lado do servidor ou no fim do recebimento de uma conexão.</span><span class="sxs-lookup"><span data-stu-id="809b7-244">Sessions are stored on the computer that's at the server-side, or receiving end of a connection.</span></span> <span data-ttu-id="809b7-245">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="809b7-245">The default is the local computer.</span></span>

<span data-ttu-id="809b7-246">Digite o nome NetBIOS, um endereço IP ou um FQDN (nome de domínio totalmente qualificado) de um computador.</span><span class="sxs-lookup"><span data-stu-id="809b7-246">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of one computer.</span></span>
<span data-ttu-id="809b7-247">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="809b7-247">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="809b7-248">Para especificar o computador local, digite o nome do computador, um ponto ( `.` ), `$env:COMPUTERNAME` ou localhost.</span><span class="sxs-lookup"><span data-stu-id="809b7-248">To specify the local computer, type the computer name, a dot (`.`), `$env:COMPUTERNAME`, or localhost.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-249">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="809b7-249">-ConfigurationName</span></span>

<span data-ttu-id="809b7-250">Especifica o nome de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-250">Specifies the name of a session configuration.</span></span> <span data-ttu-id="809b7-251">Esse cmdlet se conecta somente a sessões que usam a configuração de sessão especificada.</span><span class="sxs-lookup"><span data-stu-id="809b7-251">This cmdlet connects only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="809b7-252">Insira um nome de configuração ou o URI do recurso totalmente qualificado para uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-252">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="809b7-253">Se você especificar somente o nome da configuração, o URI de esquema a seguir será anexado:</span><span class="sxs-lookup"><span data-stu-id="809b7-253">If you specify only the configuration name, the following schema URI is prepended:</span></span>

<span data-ttu-id="809b7-254">`http://schemas.microsoft.com/powershell`.</span><span class="sxs-lookup"><span data-stu-id="809b7-254">`http://schemas.microsoft.com/powershell`.</span></span>

<span data-ttu-id="809b7-255">O nome de configuração de uma sessão é armazenado na propriedade **ConfigurationName** da sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-255">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="809b7-256">O valor do parâmetro é usado para selecionar e filtrar sessões.</span><span class="sxs-lookup"><span data-stu-id="809b7-256">The parameter's value is used to select and filter sessions.</span></span> <span data-ttu-id="809b7-257">Ele não altera a configuração de sessão usada pela sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-257">It doesn't change the session configuration that the session uses.</span></span>

<span data-ttu-id="809b7-258">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](./About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="809b7-258">For more information about session configurations, see [about_Session_Configurations](./About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-259">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="809b7-259">-ConnectionUri</span></span>

<span data-ttu-id="809b7-260">Especifica um URI que define o ponto de extremidade de conexão que é usado para reconectar-se à sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-260">Specifies a URI that defines the connection endpoint that is used to reconnect to the disconnected session.</span></span>

<span data-ttu-id="809b7-261">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="809b7-261">The URI must be fully qualified.</span></span> <span data-ttu-id="809b7-262">O formato da cadeia de caracteres é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="809b7-262">The string's format is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="809b7-263">O valor padrão é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="809b7-263">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="809b7-264">Se você não especificar um URI de conexão, poderá usar os parâmetros **UseSSL** , **ComputerName** , **Port** e **ApplicationName** para especificar os valores de URI de conexão.</span><span class="sxs-lookup"><span data-stu-id="809b7-264">If you don't specify a connection URI, you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the connection URI values.</span></span>

<span data-ttu-id="809b7-265">Os valores válidos para o segmento **Transport** do URI são HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="809b7-265">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="809b7-266">Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada com portas padrão: 80 para HTTP e 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="809b7-266">If you specify a connection URI with a Transport segment, but don't specify a port, the session is created with standard ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="809b7-267">Para usar as portas padrão para comunicação remota do PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="809b7-267">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="809b7-268">Se o computador de destino redireciona a conexão para um URI diferente, o PowerShell impede o redirecionamento, a menos que você use o parâmetro **AllowRedirection** no comando.</span><span class="sxs-lookup"><span data-stu-id="809b7-268">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ConnectionUriSessionName, ConnectionUriInstanceId
Aliases: URI, CU

Required: True
Position: 0
Default value: http://localhost:5985/WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-269">-Credential</span><span class="sxs-lookup"><span data-stu-id="809b7-269">-Credential</span></span>

<span data-ttu-id="809b7-270">Especifica uma conta de usuário que tem permissão para se conectar à sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-270">Specifies a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="809b7-271">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="809b7-271">The default is the current user.</span></span>

<span data-ttu-id="809b7-272">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="809b7-272">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="809b7-273">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="809b7-273">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="809b7-274">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="809b7-274">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="809b7-275">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="809b7-275">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-276">-Id</span><span class="sxs-lookup"><span data-stu-id="809b7-276">-Id</span></span>

<span data-ttu-id="809b7-277">Especifica a ID de uma sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-277">Specifies the ID of a disconnected session.</span></span> <span data-ttu-id="809b7-278">O parâmetro **ID** só funcionará quando a sessão desconectada tiver sido conectada anteriormente à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="809b7-278">The **Id** parameter works only when the disconnected session was previously connected to the current session.</span></span>

<span data-ttu-id="809b7-279">Esse parâmetro é válido, mas não efetivo, quando a sessão é armazenada no computador local, mas não estava conectada à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="809b7-279">This parameter is valid, but not effective, when the session is stored on the local computer, but wasn't connected to the current session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-280">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="809b7-280">-InstanceId</span></span>

<span data-ttu-id="809b7-281">Especifica a ID da instância da sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-281">Specifies the instance ID of the disconnected session.</span></span> <span data-ttu-id="809b7-282">A ID da instância é um GUID que identifica exclusivamente uma **PSSession** em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="809b7-282">The instance ID is a GUID that uniquely identifies a **PSSession** on a local or remote computer.</span></span> <span data-ttu-id="809b7-283">A ID da instância é armazenada na propriedade **InstanceId** da **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="809b7-283">The instance ID is stored in the **InstanceID** property of the **PSSession**.</span></span>

```yaml
Type: System.Guid
Parameter Sets: ComputerInstanceId, ConnectionUriInstanceId, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-284">-JobName</span><span class="sxs-lookup"><span data-stu-id="809b7-284">-JobName</span></span>

<span data-ttu-id="809b7-285">Especifica um nome amigável para o trabalho que `Receive-PSSession` retorna.</span><span class="sxs-lookup"><span data-stu-id="809b7-285">Specifies a friendly name for the job that `Receive-PSSession` returns.</span></span>

<span data-ttu-id="809b7-286">`Receive-PSSession` Retorna um trabalho quando o valor do parâmetro **outtarget** é trabalho ou o trabalho que está sendo executado na sessão desconectada foi iniciado na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="809b7-286">`Receive-PSSession` returns a job when the value of the **OutTarget** parameter is Job or the job that's running in the disconnected session was started in the current session.</span></span>

<span data-ttu-id="809b7-287">Se o trabalho que está em execução na sessão desconectada foi iniciado na sessão atual, o PowerShell reutiliza o objeto de trabalho original na sessão e ignora o valor do parâmetro **JobName** .</span><span class="sxs-lookup"><span data-stu-id="809b7-287">If the job that's running in the disconnected session was started in the current session, PowerShell reuses the original job object in the session and ignores the value of the **JobName** parameter.</span></span>

<span data-ttu-id="809b7-288">Se o trabalho que está em execução na sessão desconectada tiver sido iniciado em uma sessão diferente, o PowerShell criará um novo objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="809b7-288">If the job that's running in the disconnected session was started in a different session, PowerShell creates a new job object.</span></span> <span data-ttu-id="809b7-289">Ele usa um nome padrão, mas você pode usar este parâmetro para alterar o nome.</span><span class="sxs-lookup"><span data-stu-id="809b7-289">It uses a default name, but you can use this parameter to change the name.</span></span>

<span data-ttu-id="809b7-290">Se o valor padrão ou o valor explícito do parâmetro **outtarget** não for Job, o comando terá sucesso, mas o parâmetro **JobName** não terá nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="809b7-290">If the default value or explicit value of the **OutTarget** parameter isn't Job, the command succeeds, but the **JobName** parameter has no effect.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-291">-Name</span><span class="sxs-lookup"><span data-stu-id="809b7-291">-Name</span></span>

<span data-ttu-id="809b7-292">Especifica o nome amigável da sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-292">Specifies the friendly name of the disconnected session.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ConnectionUriSessionName, SessionName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-293">-Destino</span><span class="sxs-lookup"><span data-stu-id="809b7-293">-OutTarget</span></span>

<span data-ttu-id="809b7-294">Determina como os resultados da sessão são retornados.</span><span class="sxs-lookup"><span data-stu-id="809b7-294">Determines how the session results are returned.</span></span> <span data-ttu-id="809b7-295">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="809b7-295">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="809b7-296">**Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="809b7-296">**Job**.</span></span> <span data-ttu-id="809b7-297">Retorna os resultados de forma assíncrona em um objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="809b7-297">Returns the results asynchronously in a job object.</span></span> <span data-ttu-id="809b7-298">Você pode usar o parâmetro **JobName** para especificar um nome ou novo nome para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="809b7-298">You can use the **JobName** parameter to specify a name or new name for the job.</span></span>
- <span data-ttu-id="809b7-299">**Host**.</span><span class="sxs-lookup"><span data-stu-id="809b7-299">**Host**.</span></span> <span data-ttu-id="809b7-300">Retorna os resultados para a linha de comando (de forma síncrona).</span><span class="sxs-lookup"><span data-stu-id="809b7-300">Returns the results to the command line (synchronously).</span></span> <span data-ttu-id="809b7-301">Se o comando estiver sendo retomado ou os resultados consistirem de um grande número de objetos, a resposta poderá demorar.</span><span class="sxs-lookup"><span data-stu-id="809b7-301">If the command is being resumed or the results consist of a large number of objects, the response might be delayed.</span></span>

<span data-ttu-id="809b7-302">O valor padrão do parâmetro **outtarget** é host.</span><span class="sxs-lookup"><span data-stu-id="809b7-302">The default value of the **OutTarget** parameter is Host.</span></span> <span data-ttu-id="809b7-303">Se o comando que está sendo recebido em uma sessão desconectada foi iniciado na sessão atual, o valor padrão do parâmetro **outtarget** é o formulário no qual o comando foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="809b7-303">If the command that's being received in a disconnected session was started in the current session, the default value of the **OutTarget** parameter is the form in which the command was started.</span></span> <span data-ttu-id="809b7-304">Se o comando foi iniciado como um trabalho, por padrão, ele é retornado como um trabalho.</span><span class="sxs-lookup"><span data-stu-id="809b7-304">If the command was started as a job, by default, it's returned as a job.</span></span> <span data-ttu-id="809b7-305">Caso contrário, ele será retornado ao programa host por padrão.</span><span class="sxs-lookup"><span data-stu-id="809b7-305">Otherwise, it's returned to the host program by default.</span></span>

<span data-ttu-id="809b7-306">Normalmente, o programa do host exibe objetos retornados na linha de comando sem atraso, mas esse comportamento pode variar.</span><span class="sxs-lookup"><span data-stu-id="809b7-306">Typically, the host program displays returned objects at the command line without delay, but this behavior can vary.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.OutTarget
Parameter Sets: (All)
Aliases:
Accepted values: Default, Host, Job

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-307">-Port</span><span class="sxs-lookup"><span data-stu-id="809b7-307">-Port</span></span>

<span data-ttu-id="809b7-308">Especifica a porta de rede do computador remoto que é usada para se reconectar à sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-308">Specifies the remote computer's network port that's used to reconnect to the session.</span></span> <span data-ttu-id="809b7-309">Para se conectar a um computador remoto, ele deve estar escutando na porta usada pela conexão.</span><span class="sxs-lookup"><span data-stu-id="809b7-309">To connect to a remote computer, it must be listening on the port that the connection uses.</span></span> <span data-ttu-id="809b7-310">As portas padrão são 5985, que é a porta do WinRM para HTTP e 5986, que é a porta do WinRM para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="809b7-310">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="809b7-311">Antes de usar uma porta alternativa, você deve configurar o ouvinte do WinRM no computador remoto para escutar nessa porta.</span><span class="sxs-lookup"><span data-stu-id="809b7-311">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen on that port.</span></span> <span data-ttu-id="809b7-312">Para configurar o ouvinte, digite os dois comandos a seguir no prompt do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="809b7-312">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="809b7-313">Não use o parâmetro **Port** , a menos que seja necessário.</span><span class="sxs-lookup"><span data-stu-id="809b7-313">Don't use the **Port** parameter unless it's necessary.</span></span> <span data-ttu-id="809b7-314">A porta que é definida no comando aplica-se a todos os computadores ou sessões em que o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="809b7-314">The port that's set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="809b7-315">Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="809b7-315">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-316">-Sessão</span><span class="sxs-lookup"><span data-stu-id="809b7-316">-Session</span></span>

<span data-ttu-id="809b7-317">Especifica a sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-317">Specifies the disconnected session.</span></span> <span data-ttu-id="809b7-318">Insira uma variável que contém a **PSSession** ou um comando que cria ou obtém a **PSSession** , como um `Get-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="809b7-318">Enter a variable that contains the **PSSession** or a command that creates or gets the **PSSession** , such as a `Get-PSSession` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-319">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="809b7-319">-SessionOption</span></span>

<span data-ttu-id="809b7-320">Especifica as opções avançadas para a sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-320">Specifies advanced options for the session.</span></span> <span data-ttu-id="809b7-321">Insira um objeto **SessionOption** , como um que você cria usando o `New-PSSessionOption` cmdlet ou uma tabela de hash na qual as chaves são nomes de opção de sessão e os valores são valores de opção de sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-321">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="809b7-322">Os valores padrão para as opções são determinados pelo valor da variável de `$PSSessionOption` preferência, se ele estiver definido.</span><span class="sxs-lookup"><span data-stu-id="809b7-322">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it's set.</span></span> <span data-ttu-id="809b7-323">Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-323">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="809b7-324">Os valores de opção de sessão têm precedência sobre valores padrão para sessões definidas na `$PSSessionOption` variável de preferência e na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-324">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="809b7-325">No entanto, eles não têm precedência sobre os valores máximos, cotas ou limites definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-325">However, they don't take precedence over maximum values, quotas, or limits set in the session configuration.</span></span>

<span data-ttu-id="809b7-326">Para obter uma descrição das opções de sessão que incluem os valores padrão, consulte `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="809b7-326">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="809b7-327">Para obter informações sobre a variável de preferência de **$PSSessionOption** , consulte [about_Preference_Variables](./About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="809b7-327">For information about the **$PSSessionOption** preference variable, see [about_Preference_Variables](./About/about_Preference_Variables.md).</span></span> <span data-ttu-id="809b7-328">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](./About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="809b7-328">For more information about session configurations, see [about_Session_Configurations](./About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-329">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="809b7-329">-UseSSL</span></span>

<span data-ttu-id="809b7-330">Indica que esse cmdlet usa o protocolo protocolo SSL (SSL) para se conectar à sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-330">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to connect to the disconnected session.</span></span> <span data-ttu-id="809b7-331">Por padrão, o SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="809b7-331">By default, SSL isn't used.</span></span>

<span data-ttu-id="809b7-332">WS-Management criptografa todo o conteúdo do PowerShell transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="809b7-332">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="809b7-333">**UseSSL** é uma proteção adicional que envia os dados em uma conexão HTTPS em vez de usar uma conexão HTTP.</span><span class="sxs-lookup"><span data-stu-id="809b7-333">**UseSSL** is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="809b7-334">Se você usar esse parâmetro e o SSL não estiver disponível na porta usada para o comando, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="809b7-334">If you use this parameter and SSL isn't available on the port that's used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-335">-Confirm</span><span class="sxs-lookup"><span data-stu-id="809b7-335">-Confirm</span></span>

<span data-ttu-id="809b7-336">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="809b7-336">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-337">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="809b7-337">-WhatIf</span></span>

<span data-ttu-id="809b7-338">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="809b7-338">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="809b7-339">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="809b7-339">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="809b7-340">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="809b7-340">CommonParameters</span></span>

<span data-ttu-id="809b7-341">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="809b7-341">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="809b7-342">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="809b7-342">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="809b7-343">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="809b7-343">INPUTS</span></span>

### <span data-ttu-id="809b7-344">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="809b7-344">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="809b7-345">Você pode canalizar objetos de sessão para esse cmdlet, como objetos retornados pelo `Get-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="809b7-345">You can pipe session objects to this cmdlet, such as objects returned by the `Get-PSSession` cmdlet.</span></span>

### <span data-ttu-id="809b7-346">System.Int32</span><span class="sxs-lookup"><span data-stu-id="809b7-346">System.Int32</span></span>

<span data-ttu-id="809b7-347">É possível canalizar IDs de sessão para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="809b7-347">You can pipe session Ids to this cmdlet.</span></span>

### <span data-ttu-id="809b7-348">System.Guid</span><span class="sxs-lookup"><span data-stu-id="809b7-348">System.Guid</span></span>

<span data-ttu-id="809b7-349">Você pode canalizar as IDs de instância de sessões deste cmdlet.</span><span class="sxs-lookup"><span data-stu-id="809b7-349">You can pipe the instance Ids of sessions this cmdlet.</span></span>

### <span data-ttu-id="809b7-350">System.String</span><span class="sxs-lookup"><span data-stu-id="809b7-350">System.String</span></span>

<span data-ttu-id="809b7-351">É possível canalizar nomes de sessão para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="809b7-351">You can pipe session names to this cmdlet.</span></span>

## <span data-ttu-id="809b7-352">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="809b7-352">OUTPUTS</span></span>

### <span data-ttu-id="809b7-353">System. Management. Automation. Job ou PSObject</span><span class="sxs-lookup"><span data-stu-id="809b7-353">System.Management.Automation.Job or PSObject</span></span>

<span data-ttu-id="809b7-354">Esse cmdlet retorna os resultados dos comandos que foram executados na sessão desconectada, se houver.</span><span class="sxs-lookup"><span data-stu-id="809b7-354">This cmdlet returns the results of commands that ran in the disconnected session, if any.</span></span> <span data-ttu-id="809b7-355">Se o valor ou o valor padrão do parâmetro **outtarget** for Job, o `Receive-PSSession` retornará um objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="809b7-355">If the value or default value of the **OutTarget** parameter is Job, `Receive-PSSession` returns a job object.</span></span> <span data-ttu-id="809b7-356">Caso contrário, ele retorna objetos que representam os resultados do comando.</span><span class="sxs-lookup"><span data-stu-id="809b7-356">Otherwise, it returns objects that represent that command results.</span></span>

## <span data-ttu-id="809b7-357">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="809b7-357">NOTES</span></span>

<span data-ttu-id="809b7-358">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="809b7-358">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="809b7-359">`Receive-PSSession` Obtém resultados somente de sessões que foram desconectadas.</span><span class="sxs-lookup"><span data-stu-id="809b7-359">`Receive-PSSession` gets results only from sessions that were disconnected.</span></span> <span data-ttu-id="809b7-360">Somente as sessões que estão conectadas ou terminam em, computadores que executam o PowerShell 3,0 ou versões posteriores podem ser desconectados e reconectados.</span><span class="sxs-lookup"><span data-stu-id="809b7-360">Only sessions that are connected to, or terminate at, computers that run PowerShell 3.0 or later versions can be disconnected and reconnected.</span></span>

<span data-ttu-id="809b7-361">Se os comandos que estavam em execução na sessão desconectada não geraram resultados ou se os resultados já tiverem sido retornados para outra sessão, o `Receive-PSSession` não gerará nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="809b7-361">If the commands that were running in the disconnected session didn't generate results or if the results were already returned to another session, `Receive-PSSession` doesn't generate any output.</span></span>

<span data-ttu-id="809b7-362">O modo de buffer de saída de uma sessão determina como os comandos na sessão gerenciam a saída quando a sessão é desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-362">A session's output buffering mode determines how commands in the session manage output when the session is disconnected.</span></span> <span data-ttu-id="809b7-363">Quando o valor da opção **OutputBufferingMode** da sessão é drop e o buffer de saída está cheio, o comando começa a excluir a saída.</span><span class="sxs-lookup"><span data-stu-id="809b7-363">When the value of the **OutputBufferingMode** option of the session is Drop and the output buffer is full, the command starts to delete output.</span></span> <span data-ttu-id="809b7-364">`Receive-PSSession` Não é possível recuperar esta saída.</span><span class="sxs-lookup"><span data-stu-id="809b7-364">`Receive-PSSession` can't recover this output.</span></span> <span data-ttu-id="809b7-365">Para obter mais informações sobre a opção de modo de buffer de saída, consulte os artigos de ajuda para os cmdlets [New-PSSessionOption](New-PSSessionOption.md) e [New-PSTransportOption](New-PSTransportOption.md) .</span><span class="sxs-lookup"><span data-stu-id="809b7-365">For more information about the output buffering mode option, see the help articles for the [New-PSSessionOption](New-PSSessionOption.md) and [New-PSTransportOption](New-PSTransportOption.md) cmdlets.</span></span>

<span data-ttu-id="809b7-366">Não é possível alterar o valor de tempo limite ocioso de uma **PSSession** quando você se conecta à **PSSession** ou recebe resultados.</span><span class="sxs-lookup"><span data-stu-id="809b7-366">You can't change the idle time-out value of a **PSSession** when you connect to the **PSSession** or receive results.</span></span> <span data-ttu-id="809b7-367">O parâmetro **SessionOption** de `Receive-PSSession` usa um objeto **SessionOption** que tem um valor **IdleTimeout** .</span><span class="sxs-lookup"><span data-stu-id="809b7-367">The **SessionOption** parameter of `Receive-PSSession` takes a **SessionOption** object that has an **IdleTimeout** value.</span></span> <span data-ttu-id="809b7-368">No entanto, o valor de **IdleTimeout** do objeto **SessionOption** e o valor de **IdleTimeout** da `$PSSessionOption` variável são ignorados quando se conecta a uma **PSSession** ou recebe resultados.</span><span class="sxs-lookup"><span data-stu-id="809b7-368">However, the **IdleTimeout** value of the **SessionOption** object and the **IdleTimeout** value of the `$PSSessionOption` variable are ignored when it connects to a **PSSession** or receiving results.</span></span>

- <span data-ttu-id="809b7-369">Você pode definir e alterar o tempo limite de ociosidade de uma **PSSession** quando você cria a **PSSession** , usando os `New-PSSession` `Invoke-Command` cmdlets ou, e quando você se desconecta da **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="809b7-369">You can set and change the idle time-out of a **PSSession** when you create the **PSSession** , by using the `New-PSSession` or `Invoke-Command` cmdlets, and when you disconnect from the **PSSession**.</span></span>
- <span data-ttu-id="809b7-370">A propriedade **IdleTimeout** de uma **PSSession** é crítica para sessões desconectadas porque determina por quanto tempo uma sessão desconectada é mantida no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="809b7-370">The **IdleTimeout** property of a **PSSession** is critical to disconnected sessions because it determines how long a disconnected session is maintained on the remote computer.</span></span> <span data-ttu-id="809b7-371">Sessões desconectadas são consideradas ociosas desde o momento em que são desconectadas, ainda que comandos estejam em execução na sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-371">Disconnected sessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

<span data-ttu-id="809b7-372">Se você iniciar uma tarefa iniciar um trabalho em uma sessão remota usando o parâmetro **AsJob** do `Invoke-Command` cmdlet, o objeto de trabalho será criado na sessão atual, mesmo que o trabalho seja executado na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="809b7-372">If you start a start a job in a remote session by using the **AsJob** parameter of the `Invoke-Command` cmdlet, the job object is created in the current session, even though the job runs in the remote session.</span></span> <span data-ttu-id="809b7-373">Se você desconectar a sessão remota, o objeto de trabalho na sessão atual será desconectado do trabalho.</span><span class="sxs-lookup"><span data-stu-id="809b7-373">If you disconnect the remote session, the job object in the current session is disconnected from the job.</span></span> <span data-ttu-id="809b7-374">O objeto de trabalho contém todos os resultados que foram retornados a ele, mas não recebe novos resultados do trabalho na sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-374">The job object contains any results that were returned to it, but doesn't receive new results from the job in the disconnected session.</span></span>

<span data-ttu-id="809b7-375">Se um cliente diferente se conectar à sessão que contém o trabalho em execução, os resultados que foram entregues ao objeto de trabalho original na sessão original não estarão disponíveis na sessão conectada recentemente.</span><span class="sxs-lookup"><span data-stu-id="809b7-375">If a different client connects to the session that contains the running job, the results that were delivered to the original job object in the original session aren't available in the newly connected session.</span></span> <span data-ttu-id="809b7-376">Somente resultados que não foram fornecidos ao objeto de trabalho original ficam disponíveis na sessão reconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-376">Only results that were not delivered to the original job object are available in the reconnected session.</span></span>

<span data-ttu-id="809b7-377">Da mesma forma, se você iniciar um script em uma sessão e desconectar-se da sessão, todos os resultados que o script entrega para a sessão antes de desconectar não estarão disponíveis para outro cliente que se conecte à sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-377">Similarly, if you start a script in a session and then disconnect from the session, any results that the script delivers to the session before disconnecting aren't available to another client that connects to the session.</span></span>

<span data-ttu-id="809b7-378">Para evitar a perda de dados em sessões que você pretende desconectar, use o parâmetro **InDisconnectedSession** do `Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="809b7-378">To prevent data loss in sessions that you intend to disconnect, use the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="809b7-379">Como esse parâmetro impede que resultados sejam retornados à sessão atual, todos os resultados ficam disponíveis quando a sessão é reconectada.</span><span class="sxs-lookup"><span data-stu-id="809b7-379">Because this parameter prevents results from being returned to the current session, all results are available when the session is reconnected.</span></span>

<span data-ttu-id="809b7-380">Você também pode evitar a perda de dados usando o `Invoke-Command` cmdlet para executar um `Start-Job` comando na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="809b7-380">You can also prevent data loss by using the `Invoke-Command` cmdlet to run a `Start-Job` command in the remote session.</span></span> <span data-ttu-id="809b7-381">Nesse caso, o objeto de trabalho é criado na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="809b7-381">In this case, the job object is created in the remote session.</span></span> <span data-ttu-id="809b7-382">Você não pode usar o `Receive-PSSession` cmdlet para obter os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="809b7-382">You can't use the `Receive-PSSession` cmdlet to get the job results.</span></span> <span data-ttu-id="809b7-383">Em vez disso, use o `Connect-PSSession` cmdlet para se conectar à sessão e, em seguida, use o `Invoke-Command` cmdlet para executar um `Receive-Job` comando na sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-383">Instead, use the `Connect-PSSession` cmdlet to connect to the session and then use the `Invoke-Command` cmdlet to run a `Receive-Job` command in the session.</span></span>

<span data-ttu-id="809b7-384">Quando uma sessão que contém um trabalho em execução é desconectada e, em seguida, reconectada, o objeto de trabalho original é reutilizado somente se o trabalho é desconectado e reconectado à mesma sessão, e o comando para reconectar não especifica um novo nome de trabalho.</span><span class="sxs-lookup"><span data-stu-id="809b7-384">When a session that contains a running job is disconnected and then reconnected, the original job object is reused only if the job is disconnected and reconnected to the same session, and the command to reconnect doesn't specify a new job name.</span></span> <span data-ttu-id="809b7-385">Se a sessão for reconectada a uma sessão de cliente diferente ou se um novo nome de trabalho for especificado, o PowerShell criará um novo objeto de trabalho para a nova sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-385">If the session is reconnected to a different client session or a new job name is specified, PowerShell creates a new job object for the new session.</span></span>

<span data-ttu-id="809b7-386">Quando você desconecta uma **PSSession** , o estado da sessão é desconectado e a disponibilidade é nenhuma.</span><span class="sxs-lookup"><span data-stu-id="809b7-386">When you disconnect a **PSSession** , the session state is Disconnected and the availability is None.</span></span>

- <span data-ttu-id="809b7-387">O valor da propriedade **State** é relativo a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="809b7-387">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="809b7-388">Um valor de desconectado significa que a **PSSession** não está conectada à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="809b7-388">A value of Disconnected means that the **PSSession** isn't connected to the current session.</span></span> <span data-ttu-id="809b7-389">No entanto, isso não significa que a **PSSession** seja desconectada de todas as sessões.</span><span class="sxs-lookup"><span data-stu-id="809b7-389">However, it doesn't mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="809b7-390">Ela pode ser conectada a uma sessão diferente.</span><span class="sxs-lookup"><span data-stu-id="809b7-390">It might be connected to a different session.</span></span>
  <span data-ttu-id="809b7-391">Para determinar se é possível conectar-se ou reconectar-se à sessão, utilize a propriedade **Availability**.</span><span class="sxs-lookup"><span data-stu-id="809b7-391">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>
- <span data-ttu-id="809b7-392">Um valor **Availability** de None indica que é possível conectar-se à sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-392">An **Availability** value of None indicates that you can connect to the session.</span></span> <span data-ttu-id="809b7-393">Um valor de ocupado indica que você não pode se conectar à **PSSession** porque ela está conectada a outra sessão.</span><span class="sxs-lookup"><span data-stu-id="809b7-393">A value of Busy indicates that you can't connect to the **PSSession** because it's connected to another session.</span></span>
- <span data-ttu-id="809b7-394">Para obter mais informações sobre os valores da propriedade **State** de sessões, consulte [RUNSPACESTATE](/dotnet/api/system.management.automation.runspaces.runspacestate) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="809b7-394">For more information about the values of the **State** property of sessions, see [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate) in the MSDN library.</span></span>
- <span data-ttu-id="809b7-395">Para obter mais informações sobre os valores da propriedade de sessões de **disponibilidade** , consulte [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="809b7-395">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="809b7-396">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="809b7-396">RELATED LINKS</span></span>

[<span data-ttu-id="809b7-397">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="809b7-397">about_PSSessions</span></span>](./About/about_PSSessions.md)

[<span data-ttu-id="809b7-398">about_Remote</span><span class="sxs-lookup"><span data-stu-id="809b7-398">about_Remote</span></span>](./About/about_Remote.md)

[<span data-ttu-id="809b7-399">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="809b7-399">about_Remote_Disconnected_Sessions</span></span>](./About/about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="809b7-400">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="809b7-400">about_Session_Configurations</span></span>](./About/about_Session_Configurations.md)

[<span data-ttu-id="809b7-401">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="809b7-401">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="809b7-402">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="809b7-402">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="809b7-403">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="809b7-403">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="809b7-404">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="809b7-404">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="809b7-405">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="809b7-405">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="809b7-406">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="809b7-406">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="809b7-407">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="809b7-407">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="809b7-408">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="809b7-408">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="809b7-409">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="809b7-409">Remove-PSSession</span></span>](Remove-PSSession.md)

