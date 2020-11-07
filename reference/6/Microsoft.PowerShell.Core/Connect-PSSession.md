---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/connect-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-PSSession
ms.openlocfilehash: 36a03257d8241dbe7e9c851a95eaaa3e3dbbda27
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345537"
---
# <span data-ttu-id="d5e13-103">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="d5e13-103">Connect-PSSession</span></span>

## <span data-ttu-id="d5e13-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d5e13-104">SYNOPSIS</span></span>
<span data-ttu-id="d5e13-105">Reconecta-se a sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="d5e13-105">Reconnects to disconnected sessions.</span></span>

## <span data-ttu-id="d5e13-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d5e13-106">SYNTAX</span></span>

### <span data-ttu-id="d5e13-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="d5e13-107">Name (Default)</span></span>

```
Connect-PSSession -Name <String[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
  [<CommonParameters>]
```

### <span data-ttu-id="d5e13-108">Session</span><span class="sxs-lookup"><span data-stu-id="d5e13-108">Session</span></span>

```
Connect-PSSession [-Session] <PSSession[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
  [<CommonParameters>]
```

### <span data-ttu-id="d5e13-109">ComputerNameGuid</span><span class="sxs-lookup"><span data-stu-id="d5e13-109">ComputerNameGuid</span></span>

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
  -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
  [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
  [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d5e13-110">ComputerName</span><span class="sxs-lookup"><span data-stu-id="d5e13-110">ComputerName</span></span>

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
  [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
  [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
  [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d5e13-111">ConnectionUriGuid</span><span class="sxs-lookup"><span data-stu-id="d5e13-111">ConnectionUriGuid</span></span>

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
  -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
  [-CertificateThumbprint <String>] [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>]
  [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d5e13-112">ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="d5e13-112">ConnectionUri</span></span>

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
  [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
  [-CertificateThumbprint <String>] [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>]
  [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d5e13-113">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d5e13-113">InstanceId</span></span>

```
Connect-PSSession -InstanceId <Guid[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
  [<CommonParameters>]
```

### <span data-ttu-id="d5e13-114">ID</span><span class="sxs-lookup"><span data-stu-id="d5e13-114">Id</span></span>

```
Connect-PSSession [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d5e13-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d5e13-115">DESCRIPTION</span></span>

<span data-ttu-id="d5e13-116">O `Connect-PSSession` cmdlet se reconecta a sessões do PowerShell gerenciadas pelo usuário ( **PSSessions** ) que foram desconectadas.</span><span class="sxs-lookup"><span data-stu-id="d5e13-116">The `Connect-PSSession` cmdlet reconnects to user-managed PowerShell sessions ( **PSSessions** ) that were disconnected.</span></span> <span data-ttu-id="d5e13-117">Ele funciona em sessões desconectadas intencionalmente, como usando o `Disconnect-PSSession` cmdlet ou o parâmetro **InDisconnectedSession** do `Invoke-Command` cmdlet, e aqueles que foram desconectados de forma não intencional, como por uma interrupção de rede temporária.</span><span class="sxs-lookup"><span data-stu-id="d5e13-117">It works on sessions that are disconnected intentionally, such as by using the `Disconnect-PSSession` cmdlet or the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet, and those that were disconnected unintentionally, such as by a temporary network outage.</span></span>

<span data-ttu-id="d5e13-118">`Connect-PSSession` pode se conectar a qualquer sessão desconectada que foi iniciada pelo mesmo usuário.</span><span class="sxs-lookup"><span data-stu-id="d5e13-118">`Connect-PSSession` can connect to any disconnected session that was started by the same user.</span></span> <span data-ttu-id="d5e13-119">Elas incluem aquelas que foram iniciadas pelo ou desconectadas de outras sessões em outros computadores.</span><span class="sxs-lookup"><span data-stu-id="d5e13-119">These include those that were started by or disconnected from other sessions on other computers.</span></span>

<span data-ttu-id="d5e13-120">No entanto, o `Connect-PSSession` não pode se conectar a sessões interrompidas ou fechadas, ou sessões interativas iniciadas usando o `Enter-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5e13-120">However, `Connect-PSSession` cannot connect to broken or closed sessions, or interactive sessions started by using the `Enter-PSSession` cmdlet.</span></span> <span data-ttu-id="d5e13-121">Além disso, não é possível conectar sessões a sessões iniciadas por outros usuários, a menos que você possa fornecer as credenciais do usuário que criou a sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-121">Also you cannot connect sessions to sessions started by other users, unless you can provide the credentials of the user who created the session.</span></span>

<span data-ttu-id="d5e13-122">Para obter mais informações sobre o recurso de Sessões desconectadas, consulte [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span><span class="sxs-lookup"><span data-stu-id="d5e13-122">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="d5e13-123">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d5e13-123">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="d5e13-124">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d5e13-124">EXAMPLES</span></span>

### <span data-ttu-id="d5e13-125">Exemplo 1: reconectar-se a uma sessão</span><span class="sxs-lookup"><span data-stu-id="d5e13-125">Example 1: Reconnect to a session</span></span>

```
PS C:\> Connect-PSSession -ComputerName Server01 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Opened        ITTasks                  Available
```

<span data-ttu-id="d5e13-126">Esse comando se reconecta à sessão ITTask no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="d5e13-126">This command reconnects to the ITTask session on the Server01 computer.</span></span>

<span data-ttu-id="d5e13-127">A saída mostra que o comando teve êxito.</span><span class="sxs-lookup"><span data-stu-id="d5e13-127">The output shows that the command was successful.</span></span> <span data-ttu-id="d5e13-128">O **estado** da sessão é aberto e a **disponibilidade** está disponível, o que indica que você pode executar comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-128">The **State** of the session is Opened and the **Availability** is Available, which indicates that you can run commands in the session.</span></span>

### <span data-ttu-id="d5e13-129">Exemplo 2: efeito de desconectar e reconectar</span><span class="sxs-lookup"><span data-stu-id="d5e13-129">Example 2: Effect of disconnecting and reconnecting</span></span>

```
PS C:\> Get-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available


PS C:\> Get-PSSession | Disconnect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Disconnected  Microsoft.PowerShell          None


PS C:\> Get-PSSession | Connect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available
```

<span data-ttu-id="d5e13-130">Este exemplo mostra o efeito de se desconectar e, em seguida, reconectar a uma sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-130">This example shows the effect of disconnecting and then reconnecting to a session.</span></span>

<span data-ttu-id="d5e13-131">O primeiro comando usa o `Get-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5e13-131">The first command uses the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="d5e13-132">Sem o parâmetro **ComputerName** , o comando obtém apenas as sessões que foram criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d5e13-132">Without the **ComputerName** parameter, the command gets only sessions that were created in the current session.</span></span>

<span data-ttu-id="d5e13-133">A saída mostra que o comando obtém a sessão de Backups no computador local.</span><span class="sxs-lookup"><span data-stu-id="d5e13-133">The output shows that the command gets the Backups session on the local computer.</span></span> <span data-ttu-id="d5e13-134">O **estado** da sessão é aberto e a **disponibilidade** está disponível.</span><span class="sxs-lookup"><span data-stu-id="d5e13-134">The **State** of the session is Opened and the **Availability** is Available.</span></span>

<span data-ttu-id="d5e13-135">O segundo comando usa o `Get-PSSession` cmdlet para obter os objetos **PSSession** que foram criados na sessão atual e o `Disconnect-PSSession` cmdlet para desconectar as sessões.</span><span class="sxs-lookup"><span data-stu-id="d5e13-135">The second command uses the `Get-PSSession` cmdlet to get the **PSSession** objects that were created in the current session and the `Disconnect-PSSession` cmdlet to disconnect the sessions.</span></span> <span data-ttu-id="d5e13-136">A saída mostra que a sessão de Backups foi desconectada.</span><span class="sxs-lookup"><span data-stu-id="d5e13-136">The output shows that the Backups session was disconnected.</span></span> <span data-ttu-id="d5e13-137">O **estado** da sessão está desconectado e a **disponibilidade** é nenhuma.</span><span class="sxs-lookup"><span data-stu-id="d5e13-137">The **State** of the session is Disconnected and the **Availability** is None.</span></span>

<span data-ttu-id="d5e13-138">O terceiro comando usa o `Get-PSSession` cmdlet para obter os objetos **PSSession** que foram criados na sessão atual e o `Connect-PSSession` cmdlet para reconectar as sessões.</span><span class="sxs-lookup"><span data-stu-id="d5e13-138">The third command uses the `Get-PSSession` cmdlet to get the **PSSession** objects that were created in the current session and the `Connect-PSSession` cmdlet to reconnect the sessions.</span></span> <span data-ttu-id="d5e13-139">A saída mostra que a sessão de Backups foi reconectada.</span><span class="sxs-lookup"><span data-stu-id="d5e13-139">The output shows that the Backups session was reconnected.</span></span> <span data-ttu-id="d5e13-140">O **estado** da sessão é aberto e a **disponibilidade** está disponível.</span><span class="sxs-lookup"><span data-stu-id="d5e13-140">The **State** of the session is Opened and the **Availability** is Available.</span></span>

<span data-ttu-id="d5e13-141">Se você usar o `Connect-PSSession` cmdlet em uma sessão que não está desconectada, o comando não afetará a sessão e não gerará nenhum erro.</span><span class="sxs-lookup"><span data-stu-id="d5e13-141">If you use the `Connect-PSSession` cmdlet on a session that is not disconnected, the command does not affect the session and it does not generate any errors.</span></span>

### <span data-ttu-id="d5e13-142">Exemplo 3: série de comandos em um cenário empresarial</span><span class="sxs-lookup"><span data-stu-id="d5e13-142">Example 3: Series of commands in an enterprise scenario</span></span>

<span data-ttu-id="d5e13-143">Esta série de comandos mostra como o `Connect-PSSession` cmdlet pode ser usado em um cenário empresarial.</span><span class="sxs-lookup"><span data-stu-id="d5e13-143">This series of commands shows how the `Connect-PSSession` cmdlet might be used in an enterprise scenario.</span></span> <span data-ttu-id="d5e13-144">Nesse caso, uma administradora do sistema inicia um trabalho de longa execução em uma sessão em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d5e13-144">In this case, a system administrator starts a long-running job in a session on a remote computer.</span></span> <span data-ttu-id="d5e13-145">Após iniciar o trabalho, a administradora se desconecta da sessão e vai para casa.</span><span class="sxs-lookup"><span data-stu-id="d5e13-145">After starting the job, the administrator disconnects from the session and goes home.</span></span>
<span data-ttu-id="d5e13-146">Mais tarde, a noite, o administrador faz logon em seu computador doméstico e verifica se o trabalho foi executado até ser concluído.</span><span class="sxs-lookup"><span data-stu-id="d5e13-146">Later that evening, the administrator logs on to her home computer and verifies that the job ran until it is completed.</span></span>

<span data-ttu-id="d5e13-147">O administrador começa criando sessões em um computador remoto e executando um script na sessão. O primeiro comando usa o `New-PSSession` cmdlet para criar a sessão ITTask no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="d5e13-147">The administrator starts by creating a sessions on a remote computer and running a script in the session.The first command uses the `New-PSSession` cmdlet to create the ITTask session on the Server01 remote computer.</span></span> <span data-ttu-id="d5e13-148">O comando usa o parâmetro **ConfigurationName** para especificar a configuração da sessão ITTasks.</span><span class="sxs-lookup"><span data-stu-id="d5e13-148">The command uses the **ConfigurationName** parameter to specify the ITTasks session configuration.</span></span> <span data-ttu-id="d5e13-149">O comando salva as sessões na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="d5e13-149">The command saves the sessions in the `$s` variable.</span></span>

<span data-ttu-id="d5e13-150">O segundo cmdlet de comando `Invoke-Command` para iniciar um trabalho em segundo plano na sessão na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="d5e13-150">The second command `Invoke-Command` cmdlet to start a background job in the session in the `$s` variable.</span></span> <span data-ttu-id="d5e13-151">Ele usa o parâmetro **FilePath** para executar o script no trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="d5e13-151">It uses the **FilePath** parameter to run the script in the background job.</span></span>

<span data-ttu-id="d5e13-152">O terceiro comando usa o `Disconnect-PSSession` cmdlet para se desconectar da sessão na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="d5e13-152">The third command uses the `Disconnect-PSSession` cmdlet to disconnect from the session in the `$s` variable.</span></span> <span data-ttu-id="d5e13-153">O comando usa o parâmetro **OutputBufferingMode** com um valor de Drop para impedir que o script seja bloqueado por precisar fornecer saída à sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-153">The command uses the **OutputBufferingMode** parameter with a value of Drop to prevent the script from being blocked by having to deliver output to the session.</span></span> <span data-ttu-id="d5e13-154">Ele usa o parâmetro **IdleTimeoutSec** para estender o tempo limite da sessão para 15 horas.</span><span class="sxs-lookup"><span data-stu-id="d5e13-154">It uses the **IdleTimeoutSec** parameter to extend the session time-out to 15 hours.</span></span> <span data-ttu-id="d5e13-155">Quando o comando é concluído, o administrador bloqueia seu computador e entra em casa pela noite.</span><span class="sxs-lookup"><span data-stu-id="d5e13-155">When the command is completed, the administrator locks her computer and goes home for the evening.</span></span>

<span data-ttu-id="d5e13-156">Mais tarde, a noite, o administrador inicia seu computador doméstico, faz logon na rede corporativa e inicia o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5e13-156">Later that evening, the administrator starts her home computer, logs on to the corporate network, and starts PowerShell.</span></span> <span data-ttu-id="d5e13-157">O quarto comando usa o `Get-PSSession` cmdlet para obter as sessões no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="d5e13-157">The fourth command uses the `Get-PSSession` cmdlet to get the sessions on the Server01 computer.</span></span> <span data-ttu-id="d5e13-158">O comando localiza a sessão ITTask. O quinto comando usa o `Connect-PSSession` cmdlet para se conectar à sessão ITTask.</span><span class="sxs-lookup"><span data-stu-id="d5e13-158">The command finds the ITTask session.The fifth command uses the `Connect-PSSession` cmdlet to connect to the ITTask session.</span></span> <span data-ttu-id="d5e13-159">O comando salva a sessão na variável `$s`.</span><span class="sxs-lookup"><span data-stu-id="d5e13-159">The command saves the session in the `$s` variable.</span></span>

<span data-ttu-id="d5e13-160">O sexto comando usa o `Invoke-Command` cmdlet para executar um `Get-Job` comando na sessão na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="d5e13-160">The sixth command uses the `Invoke-Command` cmdlet to run a `Get-Job` command in the session in the `$s` variable.</span></span> <span data-ttu-id="d5e13-161">A saída mostra que o trabalho foi concluído com êxito. O sétimo comando usa o `Invoke-Command` cmdlet para executar um `Receive-Job` comando na sessão na `$s` variável na sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-161">The output shows that the job finished successfully.The seventh command uses the `Invoke-Command` cmdlet to run a `Receive-Job` command in the session in the `$s` variable in the session.</span></span> <span data-ttu-id="d5e13-162">O comando salva os resultados na `$BackupSpecs` variável. O oitavo comando usa o `Invoke-Command` cmdlet para executar outro script na sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-162">The command saves the results in the `$BackupSpecs` variable.The eighth command uses the `Invoke-Command` cmdlet to runs another script in the session.</span></span> <span data-ttu-id="d5e13-163">O comando usa o valor da `$BackupSpecs` variável na sessão como entrada para o script.</span><span class="sxs-lookup"><span data-stu-id="d5e13-163">The command uses the value of the `$BackupSpecs` variable in the session as input to the script.</span></span>

```
PS C:\> $s = New-PSSession -ComputerName Server01 -Name ITTask -ConfigurationName ITTasks
PS C:\> Invoke-Command -Session $s {Start-Job -FilePath \\Server30\Scripts\Backup-SQLDatabase.ps1}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Running       True            Server01             \\Server30\Scripts\Backup...

PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None

PS C:\> Get-PSSession -ComputerName Server01 -Name ITTask

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None


PS C:\> $s = Connect-PSSession -ComputerName Server01 -Name ITTask


Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Opened        ITTasks               Available

PS C:\> Invoke-Command -Session $s {Get-Job}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Completed     True            Server01             \\Server30\Scripts\Backup...

PS C:\> Invoke-Command -Session $s {$BackupSpecs = Receive-Job -JobName Job2}

PS C:\> Invoke-Command -Session $s {\\Server30\Scripts\New-SQLDatabase.ps1 -InitData $BackupSpecs.Initialization}

PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None
```

<span data-ttu-id="d5e13-164">O nono comando desconecta da sessão na `$s` variável. O administrador fecha o PowerShell e fecha o computador.</span><span class="sxs-lookup"><span data-stu-id="d5e13-164">The ninth command disconnects from the session in the `$s` variable.The administrator closes PowerShell and closes the computer.</span></span> <span data-ttu-id="d5e13-165">Ela pode se reconectar à sessão no dia seguinte e verificar o status do script do seu computador de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d5e13-165">She can reconnect to the session on the next day and check the script status from her work computer.</span></span>

## <span data-ttu-id="d5e13-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d5e13-166">PARAMETERS</span></span>

### <span data-ttu-id="d5e13-167">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="d5e13-167">-AllowRedirection</span></span>

<span data-ttu-id="d5e13-168">Indica que esse cmdlet permite o redirecionamento dessa conexão para um URI alternativo.</span><span class="sxs-lookup"><span data-stu-id="d5e13-168">Indicates that this cmdlet allows redirection of this connection to an alternate URI.</span></span>

<span data-ttu-id="d5e13-169">Quando você usa o parâmetro **ConnectionURI** , o destino remoto pode retornar uma instrução para redirecionar para um URI diferente.</span><span class="sxs-lookup"><span data-stu-id="d5e13-169">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="d5e13-170">Por padrão, o PowerShell não redireciona conexões, mas você pode usar esse parâmetro para permitir que ele redirecione a conexão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-170">By default, PowerShell does not redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="d5e13-171">É possível também limitar o número de vezes que a conexão é redirecionada alterando o valor da opção de sessão **MaximumConnectionRedirectionCount**.</span><span class="sxs-lookup"><span data-stu-id="d5e13-171">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="d5e13-172">Use o parâmetro **MaximumRedirection** do `New-PSSessionOption` cmdlet ou defina a propriedade **MaximumConnectionRedirectionCount** da variável de preferência **$PSSessionOption** .</span><span class="sxs-lookup"><span data-stu-id="d5e13-172">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the **$PSSessionOption** preference variable.</span></span> <span data-ttu-id="d5e13-173">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="d5e13-173">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-174">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="d5e13-174">-ApplicationName</span></span>

<span data-ttu-id="d5e13-175">Especifica o nome de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d5e13-175">Specifies the name of an application.</span></span> <span data-ttu-id="d5e13-176">Esse cmdlet se conecta somente a sessões que usam o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="d5e13-176">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="d5e13-177">Insira o segmento de nome de aplicativo do URI de conexão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-177">Enter the application name segment of the connection URI.</span></span> <span data-ttu-id="d5e13-178">Por exemplo, no seguinte URI de conexão, o nome do aplicativo é WSMan: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="d5e13-178">For example, in the following connection URI, the application name is WSMan: `http://localhost:5985/WSMAN`.</span></span> <span data-ttu-id="d5e13-179">O nome de aplicativo de uma sessão é armazenado na propriedade **Runspace.ConnectionInfo.AppName** da sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-179">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="d5e13-180">O valor desse parâmetro é usado para selecionar e filtrar sessões.</span><span class="sxs-lookup"><span data-stu-id="d5e13-180">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="d5e13-181">Ele não altera o aplicativo utilizado pela sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-181">It does not change the application that the session uses.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-182">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="d5e13-182">-Authentication</span></span>

<span data-ttu-id="d5e13-183">Especifica o mecanismo usado para autenticar credenciais de usuário no comando para reconectar-se à sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="d5e13-183">Specifies the mechanism that is used to authenticate user credentials in the command to reconnect to the disconnected session.</span></span> <span data-ttu-id="d5e13-184">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="d5e13-184">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d5e13-185">Padrão</span><span class="sxs-lookup"><span data-stu-id="d5e13-185">Default</span></span>
- <span data-ttu-id="d5e13-186">Basic</span><span class="sxs-lookup"><span data-stu-id="d5e13-186">Basic</span></span>
- <span data-ttu-id="d5e13-187">CredSSP</span><span class="sxs-lookup"><span data-stu-id="d5e13-187">Credssp</span></span>
- <span data-ttu-id="d5e13-188">Digest</span><span class="sxs-lookup"><span data-stu-id="d5e13-188">Digest</span></span>
- <span data-ttu-id="d5e13-189">Kerberos</span><span class="sxs-lookup"><span data-stu-id="d5e13-189">Kerberos</span></span>
- <span data-ttu-id="d5e13-190">Negotiate</span><span class="sxs-lookup"><span data-stu-id="d5e13-190">Negotiate</span></span>
- <span data-ttu-id="d5e13-191">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="d5e13-191">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="d5e13-192">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="d5e13-192">The default value is Default.</span></span>

<span data-ttu-id="d5e13-193">Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="d5e13-193">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in the MSDN library.</span></span>

> [!CAUTION]
> <span data-ttu-id="d5e13-194">A autenticação CredSSP (Credencial Security Support Provider), na qual as credenciais do usuário são passadas a um computador remoto para autenticação, foi projetada para comandos que exijam autenticação em mais de um recurso, como acessar um compartilhamento de rede remota.</span><span class="sxs-lookup"><span data-stu-id="d5e13-194">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="d5e13-195">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="d5e13-195">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="d5e13-196">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="d5e13-196">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-197">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="d5e13-197">-CertificateThumbprint</span></span>

<span data-ttu-id="d5e13-198">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para se conectar à sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="d5e13-198">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="d5e13-199">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="d5e13-199">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="d5e13-200">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="d5e13-200">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="d5e13-201">Eles podem ser mapeados somente para contas de usuário local.</span><span class="sxs-lookup"><span data-stu-id="d5e13-201">They can be mapped only to local user accounts.</span></span> <span data-ttu-id="d5e13-202">Eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="d5e13-202">They do not work with domain accounts.</span></span>

<span data-ttu-id="d5e13-203">Para obter uma impressão digital do certificado, use um `Get-Item` `Get-ChildItem` comando ou na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="d5e13-203">To get a certificate thumbprint, use a `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-204">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d5e13-204">-ComputerName</span></span>

<span data-ttu-id="d5e13-205">Especifica os computadores nos quais as sessões desconectadas estão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="d5e13-205">Specifies the computers on which the disconnected sessions are stored.</span></span> <span data-ttu-id="d5e13-206">As sessões são armazenadas no computador que está no lado do servidor ou no fim do recebimento de uma conexão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-206">Sessions are stored on the computer that is at the server-side or receiving end of a connection.</span></span> <span data-ttu-id="d5e13-207">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="d5e13-207">The default is the local computer.</span></span>

<span data-ttu-id="d5e13-208">Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um computador.</span><span class="sxs-lookup"><span data-stu-id="d5e13-208">Type the NetBIOS name, an IP address, or a fully qualified domain name of one computer.</span></span> <span data-ttu-id="d5e13-209">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d5e13-209">Wildcard characters are not permitted.</span></span> <span data-ttu-id="d5e13-210">Para especificar o computador local, digite o nome do computador, localhost ou um ponto (.)</span><span class="sxs-lookup"><span data-stu-id="d5e13-210">To specify the local computer, type the computer name, localhost, or a dot (.)</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameGuid, ComputerName
Aliases: Cn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-211">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="d5e13-211">-ConfigurationName</span></span>

<span data-ttu-id="d5e13-212">Conecta-se somente a sessões que usam a configuração de sessão especificada.</span><span class="sxs-lookup"><span data-stu-id="d5e13-212">Connects only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="d5e13-213">Insira um nome de configuração ou o URI do recurso totalmente qualificado para uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-213">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="d5e13-214">Se você especificar apenas o nome da configuração, o seguinte URI de esquema será anexado: `http://schemas.microsoft.com/powershell` .</span><span class="sxs-lookup"><span data-stu-id="d5e13-214">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span> <span data-ttu-id="d5e13-215">O nome de configuração de uma sessão é armazenado na propriedade **ConfigurationName** da sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-215">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="d5e13-216">O valor desse parâmetro é usado para selecionar e filtrar sessões.</span><span class="sxs-lookup"><span data-stu-id="d5e13-216">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="d5e13-217">Ele não altera a configuração de sessão utilizada pela sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-217">It does not change the session configuration that the session uses.</span></span>

<span data-ttu-id="d5e13-218">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="d5e13-218">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-219">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="d5e13-219">-ConnectionUri</span></span>

<span data-ttu-id="d5e13-220">Especifica os URIs dos pontos de extremidade de conexão para as sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="d5e13-220">Specifies the URIs of the connection endpoints for the disconnected sessions.</span></span>

<span data-ttu-id="d5e13-221">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="d5e13-221">The URI must be fully qualified.</span></span> <span data-ttu-id="d5e13-222">O formato dessa cadeia de caracteres é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d5e13-222">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="d5e13-223">O valor padrão é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d5e13-223">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="d5e13-224">Se você não especificar um URI de conexão, poderá usar os parâmetros **UseSSL** e **Port** para especificar os valores de URI de conexão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-224">If you do not specify a connection URI, you can use the **UseSSL** and **Port** parameters to specify the connection URI values.</span></span>

<span data-ttu-id="d5e13-225">Os valores válidos para o segmento **Transport** do URI são HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d5e13-225">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="d5e13-226">Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada com portas de padrões: 80 para HTTP e 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d5e13-226">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="d5e13-227">Para usar as portas padrão para comunicação remota do PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d5e13-227">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="d5e13-228">Se o computador de destino redireciona a conexão para um URI diferente, o PowerShell impede o redirecionamento, a menos que você use o parâmetro **AllowRedirection** no comando.</span><span class="sxs-lookup"><span data-stu-id="d5e13-228">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUri, ConnectionUriGuid
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-229">-Credential</span><span class="sxs-lookup"><span data-stu-id="d5e13-229">-Credential</span></span>

<span data-ttu-id="d5e13-230">Especifica uma conta de usuário que tem permissão para se conectar à sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="d5e13-230">Specifies a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="d5e13-231">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="d5e13-231">The default is the current user.</span></span>

<span data-ttu-id="d5e13-232">Digite um nome de usuário, como `User01` ou `Domain01\User01` , ou insira um `PSCredential` objeto gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5e13-232">Type a user name, such as `User01` or `Domain01\User01`, or enter a `PSCredential` object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="d5e13-233">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="d5e13-233">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="d5e13-234">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="d5e13-234">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="d5e13-235">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="d5e13-235">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-236">-Id</span><span class="sxs-lookup"><span data-stu-id="d5e13-236">-Id</span></span>

<span data-ttu-id="d5e13-237">Especifica as IDs das sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="d5e13-237">Specifies the IDs of the disconnected sessions.</span></span> <span data-ttu-id="d5e13-238">O parâmetro **ID** só funcionará quando a sessão desconectada tiver sido conectada anteriormente à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d5e13-238">The **Id** parameter works only when the disconnected session was previously connected to the current session.</span></span>

<span data-ttu-id="d5e13-239">Este parâmetro é válido, mas não é eficaz, quando a sessão está armazenada no computador local, mas não estava conectada à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d5e13-239">This parameter is valid, but not effective, when the session is stored on the local computer, but was not connected to the current session.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-240">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="d5e13-240">-InstanceId</span></span>

<span data-ttu-id="d5e13-241">Especifica as IDs de instância das sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="d5e13-241">Specifies the instance IDs of the disconnected sessions.</span></span>

<span data-ttu-id="d5e13-242">A ID da instância é um GUID que identifica exclusivamente uma **PSSession** em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="d5e13-242">The instance ID is a GUID that uniquely identifies a **PSSession** on a local or remote computer.</span></span>

<span data-ttu-id="d5e13-243">A ID da instância é armazenada na propriedade **InstanceId** da **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="d5e13-243">The instance ID is stored in the **InstanceID** property of the **PSSession**.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: ComputerNameGuid, ConnectionUriGuid, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-244">-Name</span><span class="sxs-lookup"><span data-stu-id="d5e13-244">-Name</span></span>

<span data-ttu-id="d5e13-245">Especifica os nomes amigáveis das sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="d5e13-245">Specifies the friendly names of the disconnected sessions.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri
Aliases:

Required: True (Name), False (ComputerName, ConnectionUri)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-246">-Port</span><span class="sxs-lookup"><span data-stu-id="d5e13-246">-Port</span></span>

<span data-ttu-id="d5e13-247">Especifica a porta de rede no computador remoto que é usada para se reconectar à sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-247">Specifies the network port on the remote computer that is used to reconnect to the session.</span></span> <span data-ttu-id="d5e13-248">Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-248">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="d5e13-249">As portas padrão são 5985, que é a porta do WinRM para HTTP e 5986, que é a porta do WinRM para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d5e13-249">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="d5e13-250">Antes de usar uma porta alternativa, você deve configurar o ouvinte de WinRM no computador remoto para escutar na porta.</span><span class="sxs-lookup"><span data-stu-id="d5e13-250">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="d5e13-251">Para configurar o ouvinte, digite os dois comandos a seguir no prompt do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d5e13-251">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="d5e13-252">Não use o parâmetro **Port** a menos que seja necessário.</span><span class="sxs-lookup"><span data-stu-id="d5e13-252">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="d5e13-253">A porta que está definida no comando se aplica a todos os computadores ou sessões em que o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="d5e13-253">The port that is set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="d5e13-254">Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="d5e13-254">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-255">-Sessão</span><span class="sxs-lookup"><span data-stu-id="d5e13-255">-Session</span></span>

<span data-ttu-id="d5e13-256">Especifica as sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="d5e13-256">Specifies the disconnected sessions.</span></span> <span data-ttu-id="d5e13-257">Insira uma variável que contém os objetos **PSSession** ou um comando que cria ou obtém os objetos **PSSession** , como um `Get-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="d5e13-257">Enter a variable that contains the **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `Get-PSSession` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-258">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="d5e13-258">-SessionOption</span></span>

<span data-ttu-id="d5e13-259">Especifica as opções avançadas para a sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-259">Specifies advanced options for the session.</span></span> <span data-ttu-id="d5e13-260">Insira um objeto **SessionOption** , como um que você cria usando o `New-PSSessionOption` cmdlet ou uma tabela de hash na qual as chaves são nomes de opção de sessão e os valores são valores de opção de sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-260">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="d5e13-261">Os valores padrão para as opções são determinados pelo valor da variável de `$PSSessionOption` preferência, se estiver definido.</span><span class="sxs-lookup"><span data-stu-id="d5e13-261">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="d5e13-262">Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-262">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="d5e13-263">Os valores de opção de sessão têm precedência sobre valores padrão para sessões definidas na `$PSSessionOption` variável de preferência e na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-263">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="d5e13-264">No entanto, eles não têm precedência sobre valores máximos, cotas ou limites definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-264">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="d5e13-265">Para obter uma descrição das opções de sessão que incluem os valores padrão, consulte `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="d5e13-265">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="d5e13-266">Para obter informações sobre a variável de preferência de **$PSSessionOption** , consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d5e13-266">For information about the **$PSSessionOption** preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="d5e13-267">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="d5e13-267">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-268">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="d5e13-268">-ThrottleLimit</span></span>

<span data-ttu-id="d5e13-269">Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="d5e13-269">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="d5e13-270">Se você omite esse parâmetro ou digita um valor 0, o valor padrão, 32, é usado.</span><span class="sxs-lookup"><span data-stu-id="d5e13-270">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="d5e13-271">O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="d5e13-271">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-272">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="d5e13-272">-UseSSL</span></span>

<span data-ttu-id="d5e13-273">Indica que esse cmdlet usa o protocolo protocolo SSL (SSL) para se conectar à sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="d5e13-273">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to connect to the disconnected session.</span></span> <span data-ttu-id="d5e13-274">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="d5e13-274">By default, SSL is not used.</span></span>

<span data-ttu-id="d5e13-275">WS-Management criptografa todo o conteúdo do PowerShell transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="d5e13-275">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="d5e13-276">O parâmetro **UseSSL** é uma proteção adicional que envia os dados por uma conexão HTTPS em vez de uma conexão http.</span><span class="sxs-lookup"><span data-stu-id="d5e13-276">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="d5e13-277">Se você usar esse parâmetro, mas o SSL não estiver disponível na porta usada para o comando, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="d5e13-277">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5e13-278">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d5e13-278">-Confirm</span></span>

<span data-ttu-id="d5e13-279">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5e13-279">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d5e13-280">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d5e13-280">-WhatIf</span></span>

<span data-ttu-id="d5e13-281">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="d5e13-281">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d5e13-282">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="d5e13-282">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d5e13-283">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d5e13-283">CommonParameters</span></span>

<span data-ttu-id="d5e13-284">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d5e13-284">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d5e13-285">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d5e13-285">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d5e13-286">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d5e13-286">INPUTS</span></span>

### <span data-ttu-id="d5e13-287">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="d5e13-287">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="d5e13-288">Você pode canalizar uma sessão ( **PSSession** ) para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5e13-288">You can pipe a session ( **PSSession** ) to this cmdlet.</span></span>

## <span data-ttu-id="d5e13-289">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d5e13-289">OUTPUTS</span></span>

### <span data-ttu-id="d5e13-290">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="d5e13-290">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="d5e13-291">Esse cmdlet retorna um objeto que representa a sessão à qual ele se reconecta.</span><span class="sxs-lookup"><span data-stu-id="d5e13-291">This cmdlet returns an object that represents the session to which it reconnected.</span></span>

## <span data-ttu-id="d5e13-292">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d5e13-292">NOTES</span></span>

- <span data-ttu-id="d5e13-293">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="d5e13-293">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="d5e13-294">`Connect-PSSession` reconecta-se somente a sessões desconectadas, ou seja, sessões que têm um valor de desconectado para a propriedade de **estado** .</span><span class="sxs-lookup"><span data-stu-id="d5e13-294">`Connect-PSSession` reconnects only to sessions that are disconnected, that is, sessions that have a value of Disconnected for the **State** property.</span></span> <span data-ttu-id="d5e13-295">Somente as sessões que estão conectadas ou terminam em computadores que executam o Windows PowerShell 3,0 ou versões posteriores podem ser desconectadas e reconectadas.</span><span class="sxs-lookup"><span data-stu-id="d5e13-295">Only sessions that are connected to, or end at, computers that run Windows PowerShell 3.0 or later versions can be disconnected and reconnected.</span></span>

- <span data-ttu-id="d5e13-296">Se você usar `Connect-PSSession` o em uma sessão que não está desconectada, o comando não afetará a sessão e não gerará erros.</span><span class="sxs-lookup"><span data-stu-id="d5e13-296">If you use `Connect-PSSession` on a session that is not disconnected, the command does not affect the session and it does not generate errors.</span></span>

- <span data-ttu-id="d5e13-297">Sessões de loopback desconectadas com tokens interativos, que são criadas usando o parâmetro **EnableNetworkAccess** , podem ser reconectadas somente do computador no qual a sessão foi criada.</span><span class="sxs-lookup"><span data-stu-id="d5e13-297">Disconnected loopback sessions with interactive tokens, which are created by using the **EnableNetworkAccess** parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="d5e13-298">Essa restrição protege o computador contra acessos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="d5e13-298">This restriction protects the computer from malicious access.</span></span>

- <span data-ttu-id="d5e13-299">O valor da propriedade **State** de uma **PSSession** é relativo à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d5e13-299">The value of the **State** property of a **PSSession** is relative to the current session.</span></span>
  <span data-ttu-id="d5e13-300">Portanto, um valor de **desconectado** significa que a **PSSession** não está conectada à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d5e13-300">Therefore, a value of **Disconnected** means that the **PSSession** is not connected to the current session.</span></span> <span data-ttu-id="d5e13-301">No entanto, isso não significa que a **PSSession** seja desconectada de todas as sessões.</span><span class="sxs-lookup"><span data-stu-id="d5e13-301">However, it does not mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="d5e13-302">Ela pode ser conectada a uma sessão diferente.</span><span class="sxs-lookup"><span data-stu-id="d5e13-302">It might be connected to a different session.</span></span> <span data-ttu-id="d5e13-303">Para determinar se é possível conectar-se ou reconectar-se à sessão, utilize a propriedade **Availability**.</span><span class="sxs-lookup"><span data-stu-id="d5e13-303">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

  <span data-ttu-id="d5e13-304">Um valor **Availability** de None indica que é possível conectar-se à sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-304">An **Availability** value of None indicates that you can connect to the session.</span></span> <span data-ttu-id="d5e13-305">Um valor de ocupado indica que você não pode se conectar à **PSSession** porque ela está conectada a outra sessão.</span><span class="sxs-lookup"><span data-stu-id="d5e13-305">A value of Busy indicates that you cannot connect to the **PSSession** because it is connected to another session.</span></span>

  <span data-ttu-id="d5e13-306">Para obter mais informações sobre os valores da propriedade **State** de sessões, consulte [Enumeração RUNSPACESTATE](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="d5e13-306">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) in the MSDN library.</span></span>

  <span data-ttu-id="d5e13-307">Para obter mais informações sobre os valores da propriedade de sessões de **disponibilidade** , consulte [Enumeração RUNSPACEAVAILABILITY](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="d5e13-307">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) in the MSDN library.</span></span>

- <span data-ttu-id="d5e13-308">Não é possível alterar o valor de tempo limite ocioso de uma **PSSession** quando você se conecta à **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="d5e13-308">You cannot change the idle time-out value of a **PSSession** when you connect to the **PSSession**.</span></span> <span data-ttu-id="d5e13-309">O parâmetro **SessionOption** de `Connect-PSSession` usa um objeto **SessionOption** que tem um valor **IdleTimeout** .</span><span class="sxs-lookup"><span data-stu-id="d5e13-309">The **SessionOption** parameter of `Connect-PSSession` takes a **SessionOption** object that has an **IdleTimeout** value.</span></span> <span data-ttu-id="d5e13-310">No entanto, o valor **IdleTimeout** do objeto **SessionOption** e o valor **IdleTimeout** da `$PSSessionOption` variável são ignorados ao se conectar a uma **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="d5e13-310">However, the **IdleTimeout** value of the **SessionOption** object and the **IdleTimeout** value of the `$PSSessionOption` variable are ignored when connecting to a **PSSession**.</span></span>

  <span data-ttu-id="d5e13-311">Você pode definir e alterar o tempo limite de ociosidade de uma **PSSession** quando você cria a **PSSession** , usando os `New-PSSession` `Invoke-Command` cmdlets ou, e quando você se desconecta da **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="d5e13-311">You can set and change the idle time-out of a **PSSession** when you create the **PSSession** , by using the `New-PSSession` or `Invoke-Command` cmdlets, and when you disconnect from the **PSSession**.</span></span>

  <span data-ttu-id="d5e13-312">A propriedade **IdleTimeout** de uma **PSSession** é crítica para sessões desconectadas, pois determina por quanto tempo uma sessão desconectada é mantida no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d5e13-312">The **IdleTimeout** property of a **PSSession** is critical to disconnected sessions, because it determines how long a disconnected session is maintained on the remote computer.</span></span> <span data-ttu-id="d5e13-313">Sessões desconectadas são consideradas ociosas desde o momento em que são desconectadas, ainda que comandos estejam em execução na sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="d5e13-313">Disconnected sessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

## <span data-ttu-id="d5e13-314">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d5e13-314">RELATED LINKS</span></span>

[<span data-ttu-id="d5e13-315">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="d5e13-315">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="d5e13-316">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="d5e13-316">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="d5e13-317">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="d5e13-317">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="d5e13-318">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="d5e13-318">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="d5e13-319">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d5e13-319">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="d5e13-320">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="d5e13-320">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="d5e13-321">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="d5e13-321">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="d5e13-322">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="d5e13-322">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="d5e13-323">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="d5e13-323">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="d5e13-324">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="d5e13-324">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="d5e13-325">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="d5e13-325">Remove-PSSession</span></span>](Remove-PSSession.md)
