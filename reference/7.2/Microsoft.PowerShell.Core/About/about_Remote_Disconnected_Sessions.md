---
description: Explica como desconectar e reconectar-se a uma sessão do PowerShell (PSSession).
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_disconnected_sessions?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Disconnected_Sessions
ms.openlocfilehash: 0756e110b1058915f6280e2ea59ee915bedb2c75
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599017"
---
# <a name="about-remote-disconnected-sessions"></a><span data-ttu-id="f27f4-103">Sobre sessões desconectadas remotas</span><span class="sxs-lookup"><span data-stu-id="f27f4-103">About Remote Disconnected Sessions</span></span>

## <a name="short-description"></a><span data-ttu-id="f27f4-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="f27f4-104">Short description</span></span>

<span data-ttu-id="f27f4-105">Explica como desconectar e reconectar-se a uma sessão do PowerShell (PSSession).</span><span class="sxs-lookup"><span data-stu-id="f27f4-105">Explains how to disconnect and reconnect to a PowerShell Session (PSSession).</span></span>

## <a name="long-description"></a><span data-ttu-id="f27f4-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="f27f4-106">Long description</span></span>

<span data-ttu-id="f27f4-107">A partir do PowerShell 3,0, você pode se desconectar de uma PSSession e reconectar-se à PSSession no mesmo computador ou em um computador diferente.</span><span class="sxs-lookup"><span data-stu-id="f27f4-107">Beginning in PowerShell 3.0, you can disconnect from a PSSession and reconnect to the PSSession on the same computer or a different computer.</span></span> <span data-ttu-id="f27f4-108">O estado da sessão é mantido e os comandos na PSSession continuam a ser executados enquanto a sessão está desconectada.</span><span class="sxs-lookup"><span data-stu-id="f27f4-108">The session state is maintained and commands in the PSSession continue to run while the session is disconnected.</span></span>

<span data-ttu-id="f27f4-109">O recurso de sessões desconectadas só estará disponível quando o computador remoto estiver executando o PowerShell 3,0 ou uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="f27f4-109">The Disconnected Sessions feature is only available when the remote computer is running PowerShell 3.0 or a later version.</span></span>

<span data-ttu-id="f27f4-110">O recurso de sessões desconectadas permite fechar a sessão na qual uma PSSession foi criada e até mesmo fechar o PowerShell e desligar o computador, sem interromper os comandos em execução na PSSession.</span><span class="sxs-lookup"><span data-stu-id="f27f4-110">The Disconnected Sessions feature allows you to close the session in which a PSSession was created, and even close PowerShell, and shut down the computer, without disrupting commands running in the PSSession.</span></span> <span data-ttu-id="f27f4-111">As sessões desconectadas são úteis para executar comandos que levam um longo tempo para serem concluídas e fornece a flexibilidade de tempo e dispositivo que os profissionais de ti exigem.</span><span class="sxs-lookup"><span data-stu-id="f27f4-111">Disconnected sessions are useful for running commands that take an extended time to complete, and provides the time and device flexibility that IT professionals require.</span></span>

<span data-ttu-id="f27f4-112">Não é possível desconectar-se de uma sessão interativa que é iniciada usando o `Enter-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f27f4-112">You can't disconnect from an interactive session that is started by using the `Enter-PSSession` cmdlet.</span></span>

<span data-ttu-id="f27f4-113">Você pode usar sessões desconectadas para gerenciar PSSessions que foram desconectadas involuntariamente como resultado de uma interrupção de computador ou rede.</span><span class="sxs-lookup"><span data-stu-id="f27f4-113">You can use disconnected sessions to manage PSSessions that were disconnected unintentionally as the result of a computer or network outage.</span></span>

<span data-ttu-id="f27f4-114">No uso do mundo real, o recurso de sessões desconectadas permite que você comece a resolver um problema, volte a sua atenção para um problema de prioridade mais alta e, em seguida, retome o trabalho na solução, mesmo em um computador diferente em um local diferente.</span><span class="sxs-lookup"><span data-stu-id="f27f4-114">In real-world use, the Disconnected Sessions feature allows you to begin solving a problem, turn your attention to a higher priority issue, and then resume work on the solution, even on a different computer in a different location.</span></span>

## <a name="disconnected-session-cmdlets"></a><span data-ttu-id="f27f4-115">Cmdlets de sessão desconectada</span><span class="sxs-lookup"><span data-stu-id="f27f4-115">Disconnected session cmdlets</span></span>

<span data-ttu-id="f27f4-116">Os cmdlets a seguir dão suporte ao recurso de sessões desconectadas:</span><span class="sxs-lookup"><span data-stu-id="f27f4-116">The following cmdlets support the Disconnected Sessions feature:</span></span>

- <span data-ttu-id="f27f4-117">`Connect-PSSession`: Conecta-se a uma PSSession desconectada.</span><span class="sxs-lookup"><span data-stu-id="f27f4-117">`Connect-PSSession`: Connects to a disconnected PSSession.</span></span>
- <span data-ttu-id="f27f4-118">`Disconnect-PSSession`: Desconecta uma PSSession.</span><span class="sxs-lookup"><span data-stu-id="f27f4-118">`Disconnect-PSSession`: Disconnects a PSSession.</span></span>
- <span data-ttu-id="f27f4-119">`Get-PSSession`: Obtém PSSessions no computador local ou em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="f27f4-119">`Get-PSSession`: Gets PSSessions on the local computer or on remote computers.</span></span>
- <span data-ttu-id="f27f4-120">`Receive-PSSession`: Obtém os resultados dos comandos que foram executados em sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="f27f4-120">`Receive-PSSession`: Gets the results of commands that ran in disconnected sessions.</span></span>
- <span data-ttu-id="f27f4-121">`Invoke-Command`: O parâmetro **InDisconnectedSession** cria uma PSSession e desconecta-se imediatamente.</span><span class="sxs-lookup"><span data-stu-id="f27f4-121">`Invoke-Command`: **InDisconnectedSession** parameter creates a PSSession and disconnects immediately.</span></span>

## <a name="how-the-disconnected-sessions-feature-works"></a><span data-ttu-id="f27f4-122">Como funciona o recurso de sessões desconectadas</span><span class="sxs-lookup"><span data-stu-id="f27f4-122">How the Disconnected Sessions feature works</span></span>

<span data-ttu-id="f27f4-123">A partir do PowerShell 3,0, as PSSessions são independentes das sessões nas quais elas são criadas.</span><span class="sxs-lookup"><span data-stu-id="f27f4-123">Beginning in PowerShell 3.0, PSSessions are independent of the sessions in which they're created.</span></span> <span data-ttu-id="f27f4-124">As PSSessions ativas são mantidas no computador remoto ou no **lado do servidor** da conexão, mesmo que a sessão na qual a PSSession foi criada seja fechada e o computador de origem seja desligado ou desconectado da rede.</span><span class="sxs-lookup"><span data-stu-id="f27f4-124">Active PSSessions are maintained on the remote computer or **server-side** of the connection, even if the session in which the PSSession was created is closed and the originating computer is shut down or disconnected from the network.</span></span>

<span data-ttu-id="f27f4-125">No PowerShell 2,0, a PSSession é excluída do computador remoto quando é desconectada da sessão de origem ou a sessão na qual ela foi criada termina.</span><span class="sxs-lookup"><span data-stu-id="f27f4-125">In PowerShell 2.0, the PSSession is deleted from the remote computer when it's disconnected from the originating session or the session in which it was created ends.</span></span>

<span data-ttu-id="f27f4-126">Quando você desconecta uma PSSession, a PSSession permanece ativa e é mantida no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f27f4-126">When you disconnect a PSSession, the PSSession remains active and is maintained on the remote computer.</span></span> <span data-ttu-id="f27f4-127">O estado da sessão muda de **sendo executado** para **desconectado**.</span><span class="sxs-lookup"><span data-stu-id="f27f4-127">The session state changes from **Running** to **Disconnected**.</span></span> <span data-ttu-id="f27f4-128">Você pode se reconectar a uma PSSession desconectada da sessão atual ou de uma sessão diferente no mesmo computador ou em um computador diferente.</span><span class="sxs-lookup"><span data-stu-id="f27f4-128">You can reconnect to a disconnected PSSession from the current session or from a different session on the same computer, or from a different computer.</span></span> <span data-ttu-id="f27f4-129">O computador remoto que mantém a sessão deve estar em execução e estar conectado à rede.</span><span class="sxs-lookup"><span data-stu-id="f27f4-129">The remote computer that maintains the session must be running and be connected to the network.</span></span>

<span data-ttu-id="f27f4-130">Os comandos em uma PSSession desconectada continuam a ser executados sem interrupções no computador remoto até que o comando seja concluído ou o buffer de saída seja preenchido.</span><span class="sxs-lookup"><span data-stu-id="f27f4-130">Commands in a disconnected PSSession continue to run uninterrupted on the remote computer until the command completes or the output buffer fills.</span></span> <span data-ttu-id="f27f4-131">Para impedir que um buffer de saída completo suspenda um comando, use o parâmetro **OutputBufferingMode** dos `Disconnect-PSSession` `New-PSSessionOption` `New-PSTransportOption` cmdlets, ou.</span><span class="sxs-lookup"><span data-stu-id="f27f4-131">To prevent a full output buffer from suspending a command, use the **OutputBufferingMode** parameter of the `Disconnect-PSSession`, `New-PSSessionOption`, or `New-PSTransportOption` cmdlets.</span></span>

<span data-ttu-id="f27f4-132">As sessões desconectadas são mantidas no estado desconectado no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f27f4-132">Disconnected sessions are maintained in the disconnected state on the remote computer.</span></span> <span data-ttu-id="f27f4-133">Eles estão disponíveis para você se reconectar, até que você exclua a PSSession, como usando o `Remove-PSSession` cmdlet ou até que o tempo limite de ociosidade da PSSession expire.</span><span class="sxs-lookup"><span data-stu-id="f27f4-133">They're available for you to reconnect, until you delete the PSSession, such as by using the `Remove-PSSession` cmdlet, or until the idle timeout of the PSSession expires.</span></span> <span data-ttu-id="f27f4-134">Você pode ajustar o tempo limite de ociosidade de uma PSSession usando os parâmetros **IdleTimeoutSec** ou **IdleTimeout** dos `Disconnect-PSSession` `New-PSSessionOption` `New-PSTransportOption` cmdlets, ou.</span><span class="sxs-lookup"><span data-stu-id="f27f4-134">You can adjust the idle timeout of a PSSession by using the **IdleTimeoutSec** or **IdleTimeout** parameters of the `Disconnect-PSSession`, `New-PSSessionOption`, or `New-PSTransportOption` cmdlets.</span></span>

<span data-ttu-id="f27f4-135">Outro usuário pode se conectar a PSSessions que você criou, mas somente se eles puderem fornecer as credenciais que foram usadas para criar a sessão ou usar as `RunAs` credenciais da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="f27f4-135">Another user can connect to PSSessions that you created, but only if they can provide the credentials that were used to create the session, or use the `RunAs` credentials of the session configuration.</span></span>

## <a name="how-to-get-pssessions"></a><span data-ttu-id="f27f4-136">Como obter PSSessions</span><span class="sxs-lookup"><span data-stu-id="f27f4-136">How to get PSSessions</span></span>

<span data-ttu-id="f27f4-137">A partir do PowerShell 3,0, o `Get-PSSession` cmdlet obtém PSSessions no computador local e nos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="f27f4-137">Beginning in PowerShell 3.0, the `Get-PSSession` cmdlet gets PSSessions on the local computer and remote computers.</span></span> <span data-ttu-id="f27f4-138">Ele também pode obter PSSessions que foram criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f27f4-138">It can also get PSSessions that were created in the current session.</span></span>

<span data-ttu-id="f27f4-139">Para obter as PSSessions no computador local ou nos computadores remotos, use os parâmetros **ComputerName** ou **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="f27f4-139">To get PSSessions on the local computer or remote computers, use the **ComputerName** or **ConnectionUri** parameters.</span></span> <span data-ttu-id="f27f4-140">Sem parâmetros, `Get-PSSession` Obtém PSSession que foram criadas na sessão local, independentemente de onde elas forem encerradas.</span><span class="sxs-lookup"><span data-stu-id="f27f4-140">Without parameters, `Get-PSSession` gets PSSession that were created in the local session, regardless of where they terminate.</span></span>

<span data-ttu-id="f27f4-141">Ao obter as PSSessions, lembre-se de procurar por elas no computador no qual elas são mantidas, ou seja, o computador remoto ou **do lado do servidor** .</span><span class="sxs-lookup"><span data-stu-id="f27f4-141">When getting PSSessions, remember to look for them on the computer on which they're maintained, that is, the remote or **server-side** computer.</span></span>

<span data-ttu-id="f27f4-142">Por exemplo, se você criar uma PSSession para o computador Server01, obtenha a sessão do computador Server01.</span><span class="sxs-lookup"><span data-stu-id="f27f4-142">For example, if you create a PSSession to the Server01 computer, get the session from the Server01 computer.</span></span> <span data-ttu-id="f27f4-143">Se você criar uma PSSession de outro computador para o computador local, obtenha a sessão do computador local.</span><span class="sxs-lookup"><span data-stu-id="f27f4-143">If you create a PSSession from another computer to the local computer, get the session from the local computer.</span></span>

<span data-ttu-id="f27f4-144">A seqüência de comandos a seguir mostra como o `Get-PSSession` funciona.</span><span class="sxs-lookup"><span data-stu-id="f27f4-144">The following command sequence shows how `Get-PSSession` works.</span></span>

<span data-ttu-id="f27f4-145">O primeiro comando cria uma sessão para o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="f27f4-145">The first command creates a session to the Server01 computer.</span></span> <span data-ttu-id="f27f4-146">A sessão reside no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="f27f4-146">The session resides on the Server01 computer.</span></span>

```powershell
New-PSSession -ComputerName Server01
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

<span data-ttu-id="f27f4-147">Para obter a sessão, use o parâmetro **ComputerName** de `Get-PSSession` com um valor de Server01.</span><span class="sxs-lookup"><span data-stu-id="f27f4-147">To get the session, use the **ComputerName** parameter of `Get-PSSession` with a value of Server01.</span></span>

```powershell
Get-PSSession -ComputerName Server01
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

<span data-ttu-id="f27f4-148">Se o valor do parâmetro **ComputerName** de `Get-PSSession` for localhost, o `Get-PSSession` obterá PSSessions que terminam em e são mantidos no computador local.</span><span class="sxs-lookup"><span data-stu-id="f27f4-148">If the value of the **ComputerName** parameter of `Get-PSSession` is localhost, `Get-PSSession` gets PSSessions that terminate at and are maintained on the local computer.</span></span> <span data-ttu-id="f27f4-149">Ele não obtém PSSessions no computador Server01, mesmo que eles tenham sido iniciados no computador local.</span><span class="sxs-lookup"><span data-stu-id="f27f4-149">It doesn't get PSSessions on the Server01 computer, even if they were started on the local computer.</span></span>

```powershell
Get-PSSession -ComputerName localhost
```

<span data-ttu-id="f27f4-150">Para obter as sessões que foram criadas na sessão atual, use o `Get-PSSession` cmdlet sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="f27f4-150">To get sessions that were created in the current session, use the `Get-PSSession` cmdlet without parameters.</span></span> <span data-ttu-id="f27f4-151">Neste exemplo, `Get-PSSession` Obtém a PSSession que foi criada na sessão atual e conecta-se ao computador Server01.</span><span class="sxs-lookup"><span data-stu-id="f27f4-151">In this example, `Get-PSSession` gets the PSSession that was created in the current session and connects to the Server01 computer.</span></span>

```powershell
Get-PSSession
```

```Output
Id Name      ComputerName  State    ConfigurationName     Availability
-- ----      ------------  -----    -----------------     ------------
 2 Session2  Server01      Opened   Microsoft.PowerShell     Available
```

## <a name="how-to-disconnect-sessions"></a><span data-ttu-id="f27f4-152">Como desconectar sessões</span><span class="sxs-lookup"><span data-stu-id="f27f4-152">How to disconnect sessions</span></span>

<span data-ttu-id="f27f4-153">Para desconectar uma PSSession, use o `Disconnect-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f27f4-153">To disconnect a PSSession, use the `Disconnect-PSSession` cmdlet.</span></span> <span data-ttu-id="f27f4-154">Para identificar a PSSession, use o parâmetro **Session** ou o pipeline a PSSession dos `New-PSSession` `Get-PSSession` cmdlets ou para `Disconnect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="f27f4-154">To identify the PSSession, use the **Session** parameter, or pipeline a PSSession from the `New-PSSession` or `Get-PSSession` cmdlets to `Disconnect-PSSession`.</span></span>

<span data-ttu-id="f27f4-155">O comando a seguir desconecta a PSSession para o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="f27f4-155">The following command disconnects the PSSession to the Server01 computer.</span></span>
<span data-ttu-id="f27f4-156">Observe que o valor da propriedade **State** está **desconectado** e a **disponibilidade** é **None**.</span><span class="sxs-lookup"><span data-stu-id="f27f4-156">Notice that the value of the **State** property is **Disconnected** and the **Availability** is **None**.</span></span>

```powershell
Get-PSSession -ComputerName Server01 | Disconnect-PSSession
```

```Output
Id Name      ComputerName  State         ConfigurationName     Availability
-- ----      ------------  -----         -----------------     ------------
 2 Session2  Server01      Disconnected  Microsoft.PowerShell          None
```

<span data-ttu-id="f27f4-157">Para criar uma sessão desconectada, use o parâmetro **InDisconnectedSession** do `Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f27f4-157">To create a disconnected session, use the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="f27f4-158">Ele cria uma sessão, inicia o comando e se desconecta imediatamente, antes que o comando possa retornar qualquer saída.</span><span class="sxs-lookup"><span data-stu-id="f27f4-158">It creates a session, starts the command, and disconnects immediately, before the command can return any output.</span></span>

<span data-ttu-id="f27f4-159">O comando a seguir executa um `Get-WinEvent` comando em uma sessão desconectada no computador remoto Server02.</span><span class="sxs-lookup"><span data-stu-id="f27f4-159">The following command runs a `Get-WinEvent` command in a disconnected session on the Server02 remote computer.</span></span>

```powershell
Invoke-Command -ComputerName Server02 -InDisconnectedSession -ScriptBlock {
   Get-WinEvent -LogName "*PowerShell*" }
```

```Output
Id Name      ComputerName  State         ConfigurationName     Availability
-- ----      ------------  -----         -----------------     ------------
 4 Session3  Server02      Disconnected  Microsoft.PowerShell          None
```

## <a name="how-to-connect-to-disconnected-sessions"></a><span data-ttu-id="f27f4-160">Como se conectar a sessões desconectadas</span><span class="sxs-lookup"><span data-stu-id="f27f4-160">How to connect to disconnected sessions</span></span>

<span data-ttu-id="f27f4-161">Você pode se conectar a qualquer PSSession desconectada disponível da sessão na qual você criou a PSSession ou de outras sessões no computador local ou em outros computadores.</span><span class="sxs-lookup"><span data-stu-id="f27f4-161">You can connect to any available disconnected PSSession from the session in which you created the PSSession or from other sessions on the local computer or other computers.</span></span>

<span data-ttu-id="f27f4-162">Você pode criar uma PSSession, executar comandos na PSSession, desconectar-se da PSSession, fechar o PowerShell e desligar o computador.</span><span class="sxs-lookup"><span data-stu-id="f27f4-162">You can create a PSSession, run commands in the PSSession, disconnect from the PSSession, close PowerShell, and shut down the computer.</span></span> <span data-ttu-id="f27f4-163">Horas depois, você pode abrir um computador diferente, obter a PSSession, conectar-se a ele e obter os resultados dos comandos que foram executados na PSSession enquanto ele estava desconectado.</span><span class="sxs-lookup"><span data-stu-id="f27f4-163">Hours later, you can open a different computer, get the PSSession, connect to it, and get the results of commands that ran in the PSSession while it was disconnected.</span></span> <span data-ttu-id="f27f4-164">Em seguida, você pode executar mais comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="f27f4-164">Then you can run more commands in the session.</span></span>

<span data-ttu-id="f27f4-165">Para conectar uma PSSession desconectada, use o `Connect-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f27f4-165">To connect a disconnected PSSession, use the `Connect-PSSession` cmdlet.</span></span> <span data-ttu-id="f27f4-166">Use os parâmetros **ComputerName** ou **conexãouri** para identificar a PSSession ou o pipeline a PSSession de `Get-PSSession` para `Connect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="f27f4-166">Use the **ComputerName** or **ConnectionUri** parameters to identify the PSSession, or pipeline a PSSession from `Get-PSSession` to `Connect-PSSession`.</span></span>

<span data-ttu-id="f27f4-167">O comando a seguir obtém as sessões no computador Server02.</span><span class="sxs-lookup"><span data-stu-id="f27f4-167">The following command gets the sessions on the Server02 computer.</span></span> <span data-ttu-id="f27f4-168">A saída inclui duas sessões desconectadas, ambas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f27f4-168">The output includes two disconnected sessions, both of which are available.</span></span>

```powershell
Get-PSSession -ComputerName Server02
```

```Output
Id Name      ComputerName   State         ConfigurationName     Availability
-- ----      ------------   -----         -----------------     ------------
 2 Session2  juneb-srv8320  Disconnected  Microsoft.PowerShell          None
 4 Session3  juneb-srv8320  Disconnected  Microsoft.PowerShell          None
```

<span data-ttu-id="f27f4-169">O comando a seguir se conecta ao Session2.</span><span class="sxs-lookup"><span data-stu-id="f27f4-169">The following command connects to Session2.</span></span> <span data-ttu-id="f27f4-170">A PSSession agora está aberta e disponível.</span><span class="sxs-lookup"><span data-stu-id="f27f4-170">The PSSession is now open and available.</span></span>

```powershell
Connect-PSSession -ComputerName Server02 -Name Session2
```

```Output
Id Name      ComputerName    State    ConfigurationName     Availability
-- ----      ------------    -----    -----------------     ------------
 2 Session2  juneb-srv8320   Opened   Microsoft.PowerShell     Available
```

## <a name="how-to-get-the-results"></a><span data-ttu-id="f27f4-171">Como obter os resultados</span><span class="sxs-lookup"><span data-stu-id="f27f4-171">How to get the results</span></span>

<span data-ttu-id="f27f4-172">Para obter os resultados dos comandos que foram executados em uma PSSession desconectada, use o `Receive-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f27f4-172">To get the results of commands that ran in a disconnected PSSession, use the `Receive-PSSession` cmdlet.</span></span>

<span data-ttu-id="f27f4-173">Você pode usar `Receive-PSSession` em vez de usar o `Connect-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f27f4-173">You can use `Receive-PSSession` rather than using the `Connect-PSSession` cmdlet.</span></span> <span data-ttu-id="f27f4-174">Se a sessão já estiver reconectada, `Receive-PSSession` o obterá os resultados dos comandos que foram executados quando a sessão foi desconectada.</span><span class="sxs-lookup"><span data-stu-id="f27f4-174">If the session is already reconnected, `Receive-PSSession` gets the results of commands that ran when the session was disconnected.</span></span> <span data-ttu-id="f27f4-175">Se a PSSession ainda estiver desconectada, `Receive-PSSession` conecta-se a ela e obtém os resultados dos comandos que foram executados enquanto ele estava desconectado.</span><span class="sxs-lookup"><span data-stu-id="f27f4-175">If the PSSession is still disconnected, `Receive-PSSession` connects to it and then gets the results of commands that ran while it was disconnected.</span></span>

<span data-ttu-id="f27f4-176">`Receive-PSSession` pode retornar os resultados em um trabalho (de modo assíncrono) ou para o programa de host (de forma síncrona).</span><span class="sxs-lookup"><span data-stu-id="f27f4-176">`Receive-PSSession` can return the results in a job (asynchronously) or to the host program (synchronously).</span></span> <span data-ttu-id="f27f4-177">Use o parâmetro **outtarget** para selecionar o **trabalho** ou o **host**.</span><span class="sxs-lookup"><span data-stu-id="f27f4-177">Use the **OutTarget** parameter to select **Job** or **Host**.</span></span> <span data-ttu-id="f27f4-178">O valor padrão é **host**.</span><span class="sxs-lookup"><span data-stu-id="f27f4-178">The default value is **Host**.</span></span> <span data-ttu-id="f27f4-179">No entanto, se o comando que está sendo recebido tiver sido iniciado na sessão atual como um **trabalho**, ele será retornado como um **trabalho** por padrão.</span><span class="sxs-lookup"><span data-stu-id="f27f4-179">However, if the command that's being received was started in the current session as a **Job**, it's returned as a **Job** by default.</span></span>

<span data-ttu-id="f27f4-180">O comando a seguir usa o `Receive-PSSession` cmdlet para se conectar à PSSession no computador Server02 e obter os resultados do `Get-WinEvent` comando que foi executado na sessão Session3.</span><span class="sxs-lookup"><span data-stu-id="f27f4-180">The following command uses the `Receive-PSSession` cmdlet to connect to the PSSession on the Server02 computer and get the results of the `Get-WinEvent` command that ran in the Session3 session.</span></span> <span data-ttu-id="f27f4-181">O comando usa o parâmetro **outtarget** para obter os resultados em um **trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f27f4-181">The command uses the **OutTarget** parameter to get the results in a **Job**.</span></span>

```powershell
Receive-PSSession -ComputerName Server02 -Name Session3 -OutTarget Job
```

```Output
Id   Name   PSJobTypeName   State         HasMoreData     Location
--   ----   -------------   -----         -----------     --------
 3   Job3   RemoteJob       Running       True            Server02
```

<span data-ttu-id="f27f4-182">Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f27f4-182">To get the job's results, use the `Receive-Job` cmdlet.</span></span>

```powershell
Get-Job | Receive-Job -Keep
```

```Output
ProviderName: PowerShell

TimeCreated             Id LevelDisplayName Message     PSComputerName
-----------             -- ---------------- -------     --------------
5/14/2012 7:26:04 PM   400 Information      Engine stat Server02
5/14/2012 7:26:03 PM   600 Information      Provider "W Server02
5/14/2012 7:26:03 PM   600 Information      Provider "C Server02
5/14/2012 7:26:03 PM   600 Information      Provider "V Server02
```

## <a name="state-and-availability-properties"></a><span data-ttu-id="f27f4-183">Propriedades de estado e disponibilidade</span><span class="sxs-lookup"><span data-stu-id="f27f4-183">State and Availability properties</span></span>

<span data-ttu-id="f27f4-184">As propriedades de **estado** e **disponibilidade** de uma PSSession desconectada informam se a sessão está disponível para que você se reconecte a ela.</span><span class="sxs-lookup"><span data-stu-id="f27f4-184">The **State** and **Availability** properties of a disconnected PSSession tell you whether the session is available for you to reconnect to it.</span></span>

<span data-ttu-id="f27f4-185">Quando uma PSSession é conectada à sessão atual, seu estado é **aberto** e sua disponibilidade está **disponível**.</span><span class="sxs-lookup"><span data-stu-id="f27f4-185">When a PSSession is connected to the current session, its state is **Opened** and its availability is **Available**.</span></span> <span data-ttu-id="f27f4-186">Quando você se desconecta da PSSession, o estado de PSSession é **desconectado** e sua disponibilidade é **nenhuma**.</span><span class="sxs-lookup"><span data-stu-id="f27f4-186">When you disconnect from the PSSession, the PSSession state is **Disconnected** and its availability is **None**.</span></span>

<span data-ttu-id="f27f4-187">O valor da propriedade **State** é relativo a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f27f4-187">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="f27f4-188">Um valor de **desconectado** significa que a PSSession não está conectada à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f27f4-188">A value of **Disconnected** means that the PSSession isn't connected to the current session.</span></span> <span data-ttu-id="f27f4-189">Mas, não significa que PSSession está desconectado de todas as sessões.</span><span class="sxs-lookup"><span data-stu-id="f27f4-189">But, it doesn't mean that the PSSession is disconnected from all sessions.</span></span> <span data-ttu-id="f27f4-190">Ela pode ser conectada a uma sessão diferente.</span><span class="sxs-lookup"><span data-stu-id="f27f4-190">It might be connected to a different session.</span></span>

<span data-ttu-id="f27f4-191">Para determinar se você pode se conectar ou reconectar-se à PSSession, use a propriedade de **disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="f27f4-191">To determine whether you can connect or reconnect to the PSSession, use the **Availability** property.</span></span> <span data-ttu-id="f27f4-192">Um valor de **None** indica que você pode se conectar à sessão.</span><span class="sxs-lookup"><span data-stu-id="f27f4-192">A value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="f27f4-193">Um valor de **ocupado** indica que você não pode se conectar à PSSession porque ela está conectada a outra sessão.</span><span class="sxs-lookup"><span data-stu-id="f27f4-193">A value of **Busy** indicates that you can't connect to the PSSession because it's connected to another session.</span></span>

<span data-ttu-id="f27f4-194">O exemplo a seguir é executado em duas sessões do PowerShell no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="f27f4-194">The following example is run in two PowerShell sessions on the same computer.</span></span>
<span data-ttu-id="f27f4-195">Observe que os valores de alteração das propriedades **State** e **Availability** em cada sessão como PSSession são desconectados e reconectados.</span><span class="sxs-lookup"><span data-stu-id="f27f4-195">Note the changing values of the **State** and **Availability** properties in each session as the PSSession is disconnected and reconnected.</span></span>

```powershell
# Session 1
New-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1  Test   Server30        Opened        Microsoft.PowerShell     Available
```

```powershell
# Session 2
Get-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          Busy
```

```powershell
# Session 1
Get-PSSession -ComputerName Server30 -Name Test | Disconnect-PSSession
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          None
```

```powershell
# Session 2
Get-PSSession -ComputerName Server30
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          None
```

```powershell
# Session 2
Connect-PSSession -ComputerName Server30 -Name Test
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
3 Test    Server30        Opened        Microsoft.PowerShell     Available
```

```powershell
# Session 1
Get-PSSession -ComputerName Server30
```

```Output
Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1 Test    Server30        Disconnected  Microsoft.PowerShell          Busy
```

```Output
# Idle Timeout
```

<span data-ttu-id="f27f4-196">As sessões desconectadas são mantidas no computador remoto até que você as exclua, como usando o `Remove-PSSession` cmdlet, ou elas atingem o tempo limite. A propriedade **IdleTimeout** de uma PSSession determina por quanto tempo uma sessão desconectada é mantida antes de ser excluída.</span><span class="sxs-lookup"><span data-stu-id="f27f4-196">Disconnected sessions are maintained on the remote computer until you delete them, such as by using the `Remove-PSSession` cmdlet, or they time out. The **IdleTimeout** property of a PSSession determines how long a disconnected session is maintained before it's deleted.</span></span>

<span data-ttu-id="f27f4-197">As PSSessions ficam ociosas quando o **thread de pulsação** não recebe nenhuma resposta.</span><span class="sxs-lookup"><span data-stu-id="f27f4-197">PSSessions are idle when the **heartbeat thread** receives no response.</span></span>
<span data-ttu-id="f27f4-198">Desconectar uma sessão a torna ociosa e inicia o relógio de **IdleTimeout** , mesmo que os comandos ainda estejam em execução na sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="f27f4-198">Disconnecting a session makes it idle and starts the **IdleTimeout** clock, even if commands are still running in the disconnected session.</span></span> <span data-ttu-id="f27f4-199">O PowerShell considera as sessões desconectadas como ativas, mas ociosas.</span><span class="sxs-lookup"><span data-stu-id="f27f4-199">PowerShell considers disconnected sessions to be active, but idle.</span></span>

<span data-ttu-id="f27f4-200">Ao criar e desconectar sessões, verifique se o tempo limite de ociosidade na PSSession é longo o suficiente para manter a sessão para suas necessidades, mas não tanto tempo que consome recursos desnecessários no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f27f4-200">When creating and disconnecting sessions, verify that the idle timeout in the PSSession is long enough to maintain the session for your needs, but not so long that it consumes unnecessary resources on the remote computer.</span></span>

<span data-ttu-id="f27f4-201">A propriedade **IdleTimeoutMs** da configuração de sessão determina o tempo limite de ociosidade padrão de sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="f27f4-201">The **IdleTimeoutMs** property of the session configuration determines the default idle timeout of sessions that use the session configuration.</span></span> <span data-ttu-id="f27f4-202">Você pode substituir o valor padrão, mas o valor que você usa não pode exceder a propriedade **MaxIdleTimeoutMs** da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="f27f4-202">You can override the default value, but the value that you use can't exceed the **MaxIdleTimeoutMs** property of the session configuration.</span></span>

<span data-ttu-id="f27f4-203">Para localizar o valor dos valores **IdleTimeoutMs** e **MaxIdleTimeoutMs** de uma configuração de sessão, use o seguinte formato de comando.</span><span class="sxs-lookup"><span data-stu-id="f27f4-203">To find the value of the **IdleTimeoutMs** and **MaxIdleTimeoutMs** values of a session configuration, use the following command format.</span></span>

```powershell
Get-PSSessionConfiguration |
  Format-Table Name, IdleTimeoutMs, MaxIdleTimeoutMs
```

<span data-ttu-id="f27f4-204">Você pode substituir o valor padrão na configuração da sessão e definir o tempo limite de ociosidade de uma PSSession ao criar uma PSSession e quando você se desconecta.</span><span class="sxs-lookup"><span data-stu-id="f27f4-204">You can override the default value in the session configuration and set the idle timeout of a PSSession when you create a PSSession and when you disconnect.</span></span>

<span data-ttu-id="f27f4-205">Se você for um membro do grupo Administradores no computador remoto, poderá criar e alterar as propriedades **IdleTimeoutMs** e **MaxIdleTimeoutMs** de configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="f27f4-205">If you're a member of the Administrators group on the remote computer, you can create and change the **IdleTimeoutMs** and **MaxIdleTimeoutMs** properties of session configurations.</span></span>

## <a name="idle-timeout-values"></a><span data-ttu-id="f27f4-206">Valores de tempo limite de ociosidade</span><span class="sxs-lookup"><span data-stu-id="f27f4-206">Idle timeout values</span></span>

<span data-ttu-id="f27f4-207">O valor de tempo limite de ociosidade de configurações de sessão e opções de sessão é em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="f27f4-207">The idle timeout value of session configurations and session options is in milliseconds.</span></span> <span data-ttu-id="f27f4-208">O valor de tempo limite de ociosidade de sessões e opções de configuração de sessão é em segundos.</span><span class="sxs-lookup"><span data-stu-id="f27f4-208">The idle timeout value of sessions and session configuration options is in seconds.</span></span>

<span data-ttu-id="f27f4-209">Você pode definir o tempo limite de ociosidade de uma PSSession ao criar a PSSession ( `New-PSSession` , `Invoke-Command` ) e quando você se desconecta dela ( `Disconnect-PSSession` ).</span><span class="sxs-lookup"><span data-stu-id="f27f4-209">You can set the idle timeout of a PSSession when you create the PSSession (`New-PSSession`, `Invoke-Command`) and when you disconnect from it (`Disconnect-PSSession`).</span></span> <span data-ttu-id="f27f4-210">No entanto, não é possível alterar o valor de **IdleTimeout** quando você se conecta a PSSession ( `Connect-PSSession` ) ou Get Results ( `Receive-PSSession` ).</span><span class="sxs-lookup"><span data-stu-id="f27f4-210">However, you can't change the **IdleTimeout** value when you connect to the PSSession (`Connect-PSSession`) or get results (`Receive-PSSession`).</span></span>

<span data-ttu-id="f27f4-211">Os `Connect-PSSession` `Receive-PSSession` cmdlets e têm um parâmetro **SessionOption** que usa um objeto **SessionOption** , como um retornado pelo `New-PSSessionOption` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f27f4-211">The `Connect-PSSession` and `Receive-PSSession` cmdlets have a **SessionOption** parameter that takes a **SessionOption** object, such as one returned by the `New-PSSessionOption` cmdlet.</span></span> <span data-ttu-id="f27f4-212">O valor de **IdleTimeout** no objeto **SessionOption** e o valor **IdleTimeout** na `$PSSessionOption` variável de preferência não alteram o valor de **IdleTimeout** de PSSession em um `Connect-PSSession` `Receive-PSSession` comando ou.</span><span class="sxs-lookup"><span data-stu-id="f27f4-212">The **IdleTimeout** value in **SessionOption** object and the **IdleTimeout** value in the `$PSSessionOption` preference variable don't change the value of the **IdleTimeout** of the PSSession in a `Connect-PSSession` or `Receive-PSSession` command.</span></span>

<span data-ttu-id="f27f4-213">Para criar uma PSSession com um valor de tempo limite ocioso específico, crie uma `$PSSessionOption` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="f27f4-213">To create a PSSession with a particular idle timeout value, create a `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="f27f4-214">Defina o valor da propriedade **IdleTimeout** para o valor desejado (em milissegundos).</span><span class="sxs-lookup"><span data-stu-id="f27f4-214">Set the value of the **IdleTimeout** property to the desired value (in milliseconds).</span></span>

<span data-ttu-id="f27f4-215">Quando você cria PSSessions, os valores na `$PSSessionOption` variável têm precedência sobre os valores na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="f27f4-215">When you create PSSessions, the values in `$PSSessionOption` variable take precedence over the values in the session configuration.</span></span>

<span data-ttu-id="f27f4-216">Por exemplo, o comando a seguir define um tempo limite de ociosidade de 48 horas:</span><span class="sxs-lookup"><span data-stu-id="f27f4-216">For example, the following command sets an idle timeout of 48 hours:</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -IdleTimeoutMSec 172800000
```

<span data-ttu-id="f27f4-217">Para criar uma PSSession com um valor de tempo limite ocioso específico, use o parâmetro **IdleTimeoutMSec** do `New-PSSessionOption` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f27f4-217">To create a PSSession with a particular idle timeout value, use the **IdleTimeoutMSec** parameter of the `New-PSSessionOption` cmdlet.</span></span> <span data-ttu-id="f27f4-218">Em seguida, use a opção de sessão no valor do parâmetro **SessionOption** dos `New-PSSession` `Invoke-Command` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="f27f4-218">Then, use the session option in the value of the **SessionOption** parameter of the `New-PSSession` or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="f27f4-219">Os valores definidos ao criar a sessão têm precedência sobre os valores definidos na `$PSSessionOption` variável de preferência e a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="f27f4-219">The values set when creating the session take precedence over the values set in the `$PSSessionOption` preference variable and the session configuration.</span></span>

<span data-ttu-id="f27f4-220">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f27f4-220">For example:</span></span>

```powershell
$o = New-PSSessionOption -IdleTimeoutMSec 172800000
New-PSSession -SessionOption $o
```

<span data-ttu-id="f27f4-221">Para alterar o tempo limite de ociosidade de uma PSSession ao desconectar, use o parâmetro **IdleTimeoutSec** do `Disconnect-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f27f4-221">To change the idle timeout of a PSSession when disconnecting, use the **IdleTimeoutSec** parameter of the `Disconnect-PSSession` cmdlet.</span></span>

<span data-ttu-id="f27f4-222">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f27f4-222">For example:</span></span>

```powershell
Disconnect-PSSession -IdleTimeoutSec 172800
```

<span data-ttu-id="f27f4-223">Para criar uma configuração de sessão com um tempo limite de ociosidade específico e o tempo limite de ociosidade máximo, use os parâmetros **IdleTimeoutSec** e **MaxIdleTimeoutSec** do `New-PSTransportOption` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f27f4-223">To create a session configuration with a particular idle timeout and maximum idle timeout, use the **IdleTimeoutSec** and **MaxIdleTimeoutSec** parameters of the `New-PSTransportOption` cmdlet.</span></span> <span data-ttu-id="f27f4-224">Em seguida, use a opção Transport no valor do parâmetro **TransportOption** de `Register-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="f27f4-224">Then, use the transport option in the value of the **TransportOption** parameter of `Register-PSSessionConfiguration`.</span></span>

<span data-ttu-id="f27f4-225">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f27f4-225">For example:</span></span>

```powershell
$o = New-PSTransportOption -IdleTimeoutSec 172800 -MaxIdleTimeoutSec 259200
Register-PSSessionConfiguration -Name Test -TransportOption $o
```

<span data-ttu-id="f27f4-226">Para alterar o tempo limite de ociosidade padrão e o tempo limite máximo de ociosidade de uma configuração de sessão, use os parâmetros **IdleTimeoutSec** e **MaxIdleTimeoutSec** do `New-PSTransportOption` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f27f4-226">To change the default idle timeout and maximum idle timeout of a session configuration, use the **IdleTimeoutSec** and **MaxIdleTimeoutSec** parameters of the `New-PSTransportOption` cmdlet.</span></span> <span data-ttu-id="f27f4-227">Em seguida, use a opção Transport no valor do parâmetro **TransportOption** de `Set-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="f27f4-227">Then, use the transport option in the value of the **TransportOption** parameter of `Set-PSSessionConfiguration`.</span></span>

<span data-ttu-id="f27f4-228">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f27f4-228">For example:</span></span>

```powershell
$o = New-PSTransportOption -IdleTimeoutSec 172800 -MaxIdleTimeoutSec 259200
Set-PSSessionConfiguration -Name Test -TransportOption $o
```

## <a name="output-buffering-mode"></a><span data-ttu-id="f27f4-229">Modo de buffer de saída</span><span class="sxs-lookup"><span data-stu-id="f27f4-229">Output buffering mode</span></span>

<span data-ttu-id="f27f4-230">O modo de buffer de saída de uma PSSession determina como a saída do comando é gerenciada quando o buffer de saída da PSSession está cheio.</span><span class="sxs-lookup"><span data-stu-id="f27f4-230">The output buffering mode of a PSSession determines how command output is managed when the output buffer of the PSSession is full.</span></span>

<span data-ttu-id="f27f4-231">Em uma sessão desconectada, o modo de buffer de saída determina efetivamente se o comando continua a ser executado enquanto a sessão está desconectada.</span><span class="sxs-lookup"><span data-stu-id="f27f4-231">In a disconnected session, the output buffering mode effectively determines whether the command continues to run while the session is disconnected.</span></span>

<span data-ttu-id="f27f4-232">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f27f4-232">The valid values as follows:</span></span>

- <span data-ttu-id="f27f4-233">**Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="f27f4-233">**Block**.</span></span> <span data-ttu-id="f27f4-234">Quando o buffer de saída está cheio, a execução é suspensa até que o buffer esteja limpo.</span><span class="sxs-lookup"><span data-stu-id="f27f4-234">When the output buffer is full, execution is suspended until the buffer is clear.</span></span> <span data-ttu-id="f27f4-235">O valor padrão.</span><span class="sxs-lookup"><span data-stu-id="f27f4-235">The default value.</span></span>
- <span data-ttu-id="f27f4-236">**Drop**.</span><span class="sxs-lookup"><span data-stu-id="f27f4-236">**Drop**.</span></span> <span data-ttu-id="f27f4-237">Quando o buffer de saída está cheio, a execução continua.</span><span class="sxs-lookup"><span data-stu-id="f27f4-237">When the output buffer is full, execution continues.</span></span> <span data-ttu-id="f27f4-238">À medida que a nova saída é gerada, a saída mais antiga é descartada.</span><span class="sxs-lookup"><span data-stu-id="f27f4-238">As new output is generated, the oldest output is discarded.</span></span>

<span data-ttu-id="f27f4-239">O **bloqueio** preserva os dados, mas pode interromper o comando.</span><span class="sxs-lookup"><span data-stu-id="f27f4-239">**Block** preserves data, but might interrupt the command.</span></span> <span data-ttu-id="f27f4-240">Um valor de **Drop** permite que o comando ser concluído, embora os dados possam ser perdidos.</span><span class="sxs-lookup"><span data-stu-id="f27f4-240">A value of **Drop** allows the command to complete, although data might be lost.</span></span> <span data-ttu-id="f27f4-241">Ao usar o valor **Drop**, redirecione a saída do comando para um arquivo no disco.</span><span class="sxs-lookup"><span data-stu-id="f27f4-241">When using the **Drop** value, redirect the command output to a file on disk.</span></span> <span data-ttu-id="f27f4-242">Esse valor é recomendado para sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="f27f4-242">This value is recommended for disconnected sessions.</span></span>

<span data-ttu-id="f27f4-243">A propriedade **OutputBufferingMode** da configuração de sessão determina o modo de buffer de saída padrão de sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="f27f4-243">The **OutputBufferingMode** property of the session configuration determines the default output buffering mode of sessions that use the session configuration.</span></span>

<span data-ttu-id="f27f4-244">Para localizar o valor de uma configuração de sessão do **OutputBufferingMode**, você pode usar qualquer um dos seguintes formatos de comando:</span><span class="sxs-lookup"><span data-stu-id="f27f4-244">To find a session configuration's value of the **OutputBufferingMode**, you can use either of the following command formats:</span></span>

```powershell
(Get-PSSessionConfiguration <ConfigurationName>).OutputBufferingMode
```

```powershell
Get-PSSessionConfiguration | Format-Table Name, OutputBufferingMode
```

<span data-ttu-id="f27f4-245">Você pode substituir o valor padrão na configuração da sessão e definir o modo de buffer de saída de uma PSSession quando você cria uma PSSession, quando você se desconecta e quando você se reconecta.</span><span class="sxs-lookup"><span data-stu-id="f27f4-245">You can override the default value in the session configuration and set the output buffering mode of a PSSession when you create a PSSession, when you disconnect, and when you reconnect.</span></span>

<span data-ttu-id="f27f4-246">Se você for um membro do grupo Administradores no computador remoto, poderá criar e alterar o modo de buffer de saída de configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="f27f4-246">If you're a member of the Administrators group on the remote computer, you can create and change the output buffering mode of session configurations.</span></span>

<span data-ttu-id="f27f4-247">Para criar uma PSSession com um modo de buffer de saída de **drop**, crie uma `$PSSessionOption` variável de preferência na qual o valor da propriedade **OutputBufferingMode** seja **drop**.</span><span class="sxs-lookup"><span data-stu-id="f27f4-247">To create a PSSession with an output buffering mode of **Drop**, create a `$PSSessionOption` preference variable in which the value of the **OutputBufferingMode** property is **Drop**.</span></span>

<span data-ttu-id="f27f4-248">Quando você cria PSSessions, os valores na `$PSSessionOption` variável têm precedência sobre os valores na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="f27f4-248">When you create PSSessions, the values in `$PSSessionOption` variable take precedence over the values in the session configuration.</span></span>

<span data-ttu-id="f27f4-249">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f27f4-249">For example:</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -OutputBufferingMode Drop
```

<span data-ttu-id="f27f4-250">Para criar uma PSSession com um modo de buffer de saída de **drop**, use o parâmetro **OutputBufferingMode** do `New-PSSessionOption` cmdlet para criar uma opção de sessão com um valor de **drop**.</span><span class="sxs-lookup"><span data-stu-id="f27f4-250">To create a PSSession with an output buffering mode of **Drop**, use the **OutputBufferingMode** parameter of the `New-PSSessionOption` cmdlet to create a session option with a value of **Drop**.</span></span> <span data-ttu-id="f27f4-251">Em seguida, use a opção de sessão no valor do parâmetro **SessionOption** dos `New-PSSession` `Invoke-Command` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="f27f4-251">Then, use the session option in the value of the **SessionOption** parameter of the `New-PSSession` or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="f27f4-252">Os valores definidos ao criar a sessão têm precedência sobre os valores definidos na `$PSSessionOption` variável de preferência e a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="f27f4-252">The values set when creating the session take precedence over the values set in the `$PSSessionOption` preference variable and the session configuration.</span></span>

<span data-ttu-id="f27f4-253">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f27f4-253">For example:</span></span>

```powershell
$o = New-PSSessionOption -OutputBufferingMode Drop
New-PSSession -SessionOption $o
```

<span data-ttu-id="f27f4-254">Para alterar o modo de buffer de saída de uma PSSession ao desconectar, use o parâmetro **OutputBufferingMode** do `Disconnect-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f27f4-254">To change the output buffering mode of a PSSession when disconnecting, use the **OutputBufferingMode** parameter of the `Disconnect-PSSession` cmdlet.</span></span>

<span data-ttu-id="f27f4-255">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f27f4-255">For example:</span></span>

```powershell
Disconnect-PSSession -OutputBufferingMode Drop
```

<span data-ttu-id="f27f4-256">Para alterar o modo de buffer de saída de uma PSSession ao reconectar, use o parâmetro **OutputBufferingMode** do `New-PSSessionOption` cmdlet para criar uma opção de sessão com um valor de **drop**.</span><span class="sxs-lookup"><span data-stu-id="f27f4-256">To change the output buffering mode of a PSSession when reconnecting, use the **OutputBufferingMode** parameter of the `New-PSSessionOption` cmdlet to create a session option with a value of **Drop**.</span></span> <span data-ttu-id="f27f4-257">Em seguida, use a opção de sessão no valor do parâmetro **SessionOption** de `Connect-PSSession` ou `Receive-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="f27f4-257">Then, use the session option in the value of the **SessionOption** parameter of `Connect-PSSession` or `Receive-PSSession`.</span></span>

<span data-ttu-id="f27f4-258">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f27f4-258">For example:</span></span>

```powershell
$o = New-PSSessionOption -OutputBufferingMode Drop
Connect-PSSession -ComputerName Server01 -Name Test -SessionOption $o
```

<span data-ttu-id="f27f4-259">Para criar uma configuração de sessão com um modo de **descarte** de buffer de saída padrão, use o parâmetro **OutputBufferingMode** do `New-PSTransportOption` cmdlet para criar um objeto de opção de transporte com um valor de **drop**.</span><span class="sxs-lookup"><span data-stu-id="f27f4-259">To create a session configuration with a default output buffering mode of **Drop**, use the **OutputBufferingMode** parameter of the `New-PSTransportOption` cmdlet to create a transport option object with a value of **Drop**.</span></span> <span data-ttu-id="f27f4-260">Em seguida, use a opção Transport no valor do parâmetro **TransportOption** de `Register-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="f27f4-260">Then, use the transport option in the value of the **TransportOption** parameter of `Register-PSSessionConfiguration`.</span></span>

<span data-ttu-id="f27f4-261">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f27f4-261">For example:</span></span>

```powershell
$o = New-PSTransportOption -OutputBufferingMode Drop
Register-PSSessionConfiguration -Name Test -TransportOption $o
```

<span data-ttu-id="f27f4-262">Para alterar o modo de buffer de saída padrão de uma configuração de sessão, use o parâmetro **OutputBufferingMode** do `New-PSTransportOption` cmdlet para criar uma opção de transporte com um valor de **drop**.</span><span class="sxs-lookup"><span data-stu-id="f27f4-262">To change the default output buffering mode of a session configuration, use the **OutputBufferingMode** parameter of the `New-PSTransportOption` cmdlet to create a transport option with a value of **Drop**.</span></span> <span data-ttu-id="f27f4-263">Em seguida, use a opção Transport no valor do parâmetro **SessionOption** de `Set-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="f27f4-263">Then, use the Transport option in the value of the **SessionOption** parameter of `Set-PSSessionConfiguration`.</span></span>

<span data-ttu-id="f27f4-264">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f27f4-264">For example:</span></span>

```powershell
$o = New-PSTransportOption -OutputBufferingMode Drop
Set-PSSessionConfiguration -Name Test -TransportOption $o
```

## <a name="disconnecting-loopback-sessions"></a><span data-ttu-id="f27f4-265">Desconectando sessões de loopback</span><span class="sxs-lookup"><span data-stu-id="f27f4-265">Disconnecting loopback sessions</span></span>

<span data-ttu-id="f27f4-266">Sessões de loopback, ou sessões locais, são PSSessions que se originam e terminam no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="f27f4-266">Loopback sessions, or local sessions, are PSSessions that originate and terminate on the same computer.</span></span> <span data-ttu-id="f27f4-267">Assim como outras PSSessions, as sessões de loopback ativas são mantidas no computador na extremidade remota da conexão (o computador local), para que você possa se desconectar e reconectar-se a sessões de loopback.</span><span class="sxs-lookup"><span data-stu-id="f27f4-267">Like other PSSessions, active loopback sessions are maintained on the computer on the remote end of the connection (the local computer), so you can disconnect from and reconnect to loopback sessions.</span></span>

<span data-ttu-id="f27f4-268">Por padrão, as sessões de loopback são criadas com um token de segurança de rede que não permite que os comandos sejam executados na sessão para acessar outros computadores.</span><span class="sxs-lookup"><span data-stu-id="f27f4-268">By default, loopback sessions are created with a network security token that doesn't permit commands run in the session to access other computers.</span></span> <span data-ttu-id="f27f4-269">Você pode se reconectar a sessões de loopback que têm um token de segurança de rede de qualquer sessão no computador local ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f27f4-269">You can reconnect to loopback sessions that have a network security token from any session on the local computer or a remote computer.</span></span>

<span data-ttu-id="f27f4-270">No entanto, se você  usar o parâmetro EnableNetworkAccess `New-PSSession` do `Enter-PSSession` cmdlet,, ou `Invoke-Command` , a sessão de loopback será criada com um token de segurança interativo.</span><span class="sxs-lookup"><span data-stu-id="f27f4-270">However, if you use the **EnableNetworkAccess** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlet, the loopback session is created with an interactive security token.</span></span> <span data-ttu-id="f27f4-271">O token interativo permite que os comandos executados na sessão de loopback obtenham dados de outros computadores.</span><span class="sxs-lookup"><span data-stu-id="f27f4-271">The interactive token enables commands that run in the loopback session to get data from other computers.</span></span>

<span data-ttu-id="f27f4-272">Você pode desconectar sessões de loopback com tokens interativos e, em seguida, reconectá-las da mesma sessão ou de uma sessão diferente no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="f27f4-272">You can disconnect loopback sessions with interactive tokens and then reconnect to them from the same session or a different session on the same computer.</span></span>
<span data-ttu-id="f27f4-273">No entanto, para impedir o acesso mal-intencionado, você pode se reconectar a sessões de loopback com tokens interativos somente do computador no qual elas foram criadas.</span><span class="sxs-lookup"><span data-stu-id="f27f4-273">However, to prevent malicious access, you can reconnect to loopback sessions with interactive tokens only from the computer on which they were created.</span></span>

## <a name="waiting-for-jobs-in-disconnected-sessions"></a><span data-ttu-id="f27f4-274">Aguardando trabalhos em sessões desconectadas</span><span class="sxs-lookup"><span data-stu-id="f27f4-274">Waiting for jobs in disconnected sessions</span></span>

<span data-ttu-id="f27f4-275">O `Wait-Job` cmdlet aguarda até que um trabalho seja concluído e, em seguida, retorna ao prompt de comando ou ao próximo comando.</span><span class="sxs-lookup"><span data-stu-id="f27f4-275">The `Wait-Job` cmdlet waits until a job completes and then returns to the command prompt or the next command.</span></span> <span data-ttu-id="f27f4-276">Por padrão, `Wait-Job` retorna se a sessão na qual um trabalho está sendo executado está desconectada.</span><span class="sxs-lookup"><span data-stu-id="f27f4-276">By default, `Wait-Job` returns if the session in which a job is running is disconnected.</span></span> <span data-ttu-id="f27f4-277">Para instruir o `Wait-Job` cmdlet a aguardar até que a sessão seja reconectada, no estado **aberto** , use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="f27f4-277">To direct the `Wait-Job` cmdlet to wait until the session is reconnected, in the **Opened** state, use the **Force** parameter.</span></span> <span data-ttu-id="f27f4-278">Para obter mais informações, consulte [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job).</span><span class="sxs-lookup"><span data-stu-id="f27f4-278">For more information, see [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job).</span></span>

## <a name="robust-sessions-and-unintentional-disconnection"></a><span data-ttu-id="f27f4-279">Sessões robustas e desconexão não intencional</span><span class="sxs-lookup"><span data-stu-id="f27f4-279">Robust sessions and unintentional disconnection</span></span>

<span data-ttu-id="f27f4-280">Uma PSSession pode ser desconectada de forma não intencional devido a uma falha no computador ou à interrupção da rede.</span><span class="sxs-lookup"><span data-stu-id="f27f4-280">A PSSession might be unintentionally disconnected because of a computer failure or network outage.</span></span> <span data-ttu-id="f27f4-281">O PowerShell tenta recuperar a PSSession, mas seu sucesso depende da gravidade e da duração da causa.</span><span class="sxs-lookup"><span data-stu-id="f27f4-281">PowerShell attempts to recover the PSSession, but its success depends upon the severity and duration of the cause.</span></span>

<span data-ttu-id="f27f4-282">O estado de uma PSSession desconectada involuntariamente pode ser **rompido** ou **fechado**, mas também pode ser **desconectado**.</span><span class="sxs-lookup"><span data-stu-id="f27f4-282">The state of an unintentionally disconnected PSSession might be **Broken** or **Closed**, but it might also be **Disconnected**.</span></span> <span data-ttu-id="f27f4-283">Se o valor do **estado** for **desconectado**, você poderá usar as mesmas técnicas para gerenciar a PSSession como faria se a sessão fosse desconectada intencionalmente.</span><span class="sxs-lookup"><span data-stu-id="f27f4-283">If the value of **State** is **Disconnected**, you can use the same techniques to manage the PSSession as you would if the session were disconnected intentionally.</span></span> <span data-ttu-id="f27f4-284">Por exemplo, você pode usar o `Connect-PSSession` cmdlet para se reconectar à sessão e ao `Receive-PSSession` cmdlet para obter resultados de comandos que foram executados enquanto a sessão foi desconectada.</span><span class="sxs-lookup"><span data-stu-id="f27f4-284">For example, you can use the `Connect-PSSession` cmdlet to reconnect to the session and the `Receive-PSSession` cmdlet to get results of commands that ran while the session was disconnected.</span></span>

<span data-ttu-id="f27f4-285">Se você fechar (sair) a sessão na qual uma PSSession foi criada enquanto os comandos estão em execução na PSSession, o PowerShell manterá a PSSession no estado **desconectado** no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f27f4-285">If you close (exit) the session in which a PSSession was created while commands are running in the PSSession, PowerShell maintains the PSSession in the **Disconnected** state on the remote computer.</span></span> <span data-ttu-id="f27f4-286">Se você fechar (sair) a sessão na qual uma PSSession foi criada, mas nenhum comando estiver sendo executado na PSSession, o PowerShell não tentará manter a PSSession.</span><span class="sxs-lookup"><span data-stu-id="f27f4-286">If you close (exit) the session in which a PSSession was created, but no commands are running in the PSSession, PowerShell doesn't attempt to maintain the PSSession.</span></span>

## <a name="see-also"></a><span data-ttu-id="f27f4-287">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f27f4-287">See also</span></span>

[<span data-ttu-id="f27f4-288">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="f27f4-288">about_Jobs</span></span>](about_Jobs.md)

[<span data-ttu-id="f27f4-289">about_Remote</span><span class="sxs-lookup"><span data-stu-id="f27f4-289">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="f27f4-290">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="f27f4-290">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="f27f4-291">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="f27f4-291">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="f27f4-292">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="f27f4-292">about_Session_Configurations</span></span>](about_Session_Configurations.md)

[<span data-ttu-id="f27f4-293">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="f27f4-293">Connect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Connect-PSSession)

[<span data-ttu-id="f27f4-294">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="f27f4-294">Disconnect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Disconnect-PSSession)

[<span data-ttu-id="f27f4-295">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="f27f4-295">Get-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSession)

[<span data-ttu-id="f27f4-296">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="f27f4-296">Receive-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Receive-PSSession)

[<span data-ttu-id="f27f4-297">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="f27f4-297">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

