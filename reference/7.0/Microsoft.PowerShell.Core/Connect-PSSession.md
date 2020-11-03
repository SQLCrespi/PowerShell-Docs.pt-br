---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/connect-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-PSSession
ms.openlocfilehash: 61f1d13628763710f01cf0c2ec413f446e4bdd39
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194963"
---
# <span data-ttu-id="64a90-103">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="64a90-103">Connect-PSSession</span></span>

## <span data-ttu-id="64a90-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="64a90-104">SYNOPSIS</span></span>
<span data-ttu-id="64a90-105">Reconecta-se a sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="64a90-105">Reconnects to disconnected sessions.</span></span>

## <span data-ttu-id="64a90-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="64a90-106">SYNTAX</span></span>

### <span data-ttu-id="64a90-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="64a90-107">Name (Default)</span></span>

```
Connect-PSSession -Name <String[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="64a90-108">Session</span><span class="sxs-lookup"><span data-stu-id="64a90-108">Session</span></span>

```
Connect-PSSession [-Session] <PSSession[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="64a90-109">ComputerNameGuid</span><span class="sxs-lookup"><span data-stu-id="64a90-109">ComputerNameGuid</span></span>

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="64a90-110">ComputerName</span><span class="sxs-lookup"><span data-stu-id="64a90-110">ComputerName</span></span>

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="64a90-111">ConnectionUriGuid</span><span class="sxs-lookup"><span data-stu-id="64a90-111">ConnectionUriGuid</span></span>

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="64a90-112">ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="64a90-112">ConnectionUri</span></span>

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="64a90-113">InstanceId</span><span class="sxs-lookup"><span data-stu-id="64a90-113">InstanceId</span></span>

```
Connect-PSSession -InstanceId <Guid[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="64a90-114">ID</span><span class="sxs-lookup"><span data-stu-id="64a90-114">Id</span></span>

```
Connect-PSSession [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="64a90-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="64a90-115">DESCRIPTION</span></span>

<span data-ttu-id="64a90-116">O cmdlet **Connect-PSSession** se reconecta a sessões do PowerShell gerenciadas pelo usuário ( **PSSessions** ) que foram desconectadas.</span><span class="sxs-lookup"><span data-stu-id="64a90-116">The **Connect-PSSession** cmdlet reconnects to user-managed PowerShell sessions ( **PSSessions** ) that were disconnected.</span></span>
<span data-ttu-id="64a90-117">Ele funciona em sessões desconectadas intencionalmente, como usando o cmdlet Disconnect-PSSession ou o parâmetro *InDisconnectedSession* do cmdlet Invoke-Command, e aqueles que foram desconectados involuntariamente, como por uma interrupção de rede temporária.</span><span class="sxs-lookup"><span data-stu-id="64a90-117">It works on sessions that are disconnected intentionally, such as by using the Disconnect-PSSession cmdlet or the *InDisconnectedSession* parameter of the Invoke-Command cmdlet, and those that were disconnected unintentionally, such as by a temporary network outage.</span></span>

<span data-ttu-id="64a90-118">**Connect-PSSession** pode se conectar a qualquer sessão desconectada que foi iniciada pelo mesmo usuário.</span><span class="sxs-lookup"><span data-stu-id="64a90-118">**Connect-PSSession** can connect to any disconnected session that was started by the same user.</span></span>
<span data-ttu-id="64a90-119">Elas incluem aquelas que foram iniciadas pelo ou desconectadas de outras sessões em outros computadores.</span><span class="sxs-lookup"><span data-stu-id="64a90-119">These include those that were started by or disconnected from other sessions on other computers.</span></span>

<span data-ttu-id="64a90-120">No entanto, **Connect-PSSession** não pode se conectar a sessões interrompidas ou fechadas, ou sessões interativas iniciadas usando o cmdlet Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="64a90-120">However, **Connect-PSSession** cannot connect to broken or closed sessions, or interactive sessions started by using the Enter-PSSession cmdlet.</span></span>
<span data-ttu-id="64a90-121">Além disso, não é possível conectar sessões a sessões iniciadas por outros usuários, a menos que você possa fornecer as credenciais do usuário que criou a sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-121">Also you cannot connect sessions to sessions started by other users, unless you can provide the credentials of the user who created the session.</span></span>

<span data-ttu-id="64a90-122">Para obter mais informações sobre o recurso de Sessões desconectadas, consulte about_Remote_Disconnected_Sessions.</span><span class="sxs-lookup"><span data-stu-id="64a90-122">For more information about the Disconnected Sessions feature, see about_Remote_Disconnected_Sessions.</span></span>

<span data-ttu-id="64a90-123">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="64a90-123">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="64a90-124">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="64a90-124">EXAMPLES</span></span>

### <span data-ttu-id="64a90-125">Exemplo 1: reconectar-se a uma sessão</span><span class="sxs-lookup"><span data-stu-id="64a90-125">Example 1: Reconnect to a session</span></span>

```
PS C:\> Connect-PSSession -ComputerName Server01 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Opened        ITTasks                  Available
```

<span data-ttu-id="64a90-126">Esse comando se reconecta à sessão ITTask no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="64a90-126">This command reconnects to the ITTask session on the Server01 computer.</span></span>

<span data-ttu-id="64a90-127">A saída mostra que o comando teve êxito.</span><span class="sxs-lookup"><span data-stu-id="64a90-127">The output shows that the command was successful.</span></span>
<span data-ttu-id="64a90-128">O **estado** da sessão é aberto e a **disponibilidade** está disponível, o que indica que você pode executar comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-128">The **State** of the session is Opened and the **Availability** is Available, which indicates that you can run commands in the session.</span></span>

### <span data-ttu-id="64a90-129">Exemplo 2: efeito de desconectar e reconectar</span><span class="sxs-lookup"><span data-stu-id="64a90-129">Example 2: Effect of disconnecting and reconnecting</span></span>

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

<span data-ttu-id="64a90-130">Este exemplo mostra o efeito de se desconectar e, em seguida, reconectar a uma sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-130">This example shows the effect of disconnecting and then reconnecting to a session.</span></span>

<span data-ttu-id="64a90-131">O primeiro comando usa o cmdlet Get-PSSession.</span><span class="sxs-lookup"><span data-stu-id="64a90-131">The first command uses the Get-PSSession cmdlet.</span></span>
<span data-ttu-id="64a90-132">Sem o parâmetro *ComputerName* , o comando obtém apenas as sessões que foram criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="64a90-132">Without the *ComputerName* parameter, the command gets only sessions that were created in the current session.</span></span>

<span data-ttu-id="64a90-133">A saída mostra que o comando obtém a sessão de Backups no computador local.</span><span class="sxs-lookup"><span data-stu-id="64a90-133">The output shows that the command gets the Backups session on the local computer.</span></span>
<span data-ttu-id="64a90-134">O **estado** da sessão é aberto e a **disponibilidade** está disponível.</span><span class="sxs-lookup"><span data-stu-id="64a90-134">The **State** of the session is Opened and the **Availability** is Available.</span></span>

<span data-ttu-id="64a90-135">O segundo comando usa o cmdlet **Get-PSSession** para obter os objetos **PSSession** que foram criados na sessão atual e o cmdlet **Disconnect-PSSession** para desconectar as sessões.</span><span class="sxs-lookup"><span data-stu-id="64a90-135">The second command uses the **Get-PSSession** cmdlet to get the **PSSession** objects that were created in the current session and the **Disconnect-PSSession** cmdlet to disconnect the sessions.</span></span>
<span data-ttu-id="64a90-136">A saída mostra que a sessão de Backups foi desconectada.</span><span class="sxs-lookup"><span data-stu-id="64a90-136">The output shows that the Backups session was disconnected.</span></span>
<span data-ttu-id="64a90-137">O **estado** da sessão está desconectado e a **disponibilidade** é nenhuma.</span><span class="sxs-lookup"><span data-stu-id="64a90-137">The **State** of the session is Disconnected and the **Availability** is None.</span></span>

<span data-ttu-id="64a90-138">O terceiro comando usa o cmdlet **Get-PSSession** para obter os objetos **PSSession** que foram criados na sessão atual e o cmdlet **Connect-PSSession** para reconectar as sessões.</span><span class="sxs-lookup"><span data-stu-id="64a90-138">The third command uses the **Get-PSSession** cmdlet to get the **PSSession** objects that were created in the current session and the **Connect-PSSession** cmdlet to reconnect the sessions.</span></span>
<span data-ttu-id="64a90-139">A saída mostra que a sessão de Backups foi reconectada.</span><span class="sxs-lookup"><span data-stu-id="64a90-139">The output shows that the Backups session was reconnected.</span></span>
<span data-ttu-id="64a90-140">O **estado** da sessão é aberto e a **disponibilidade** está disponível.</span><span class="sxs-lookup"><span data-stu-id="64a90-140">The **State** of the session is Opened and the **Availability** is Available.</span></span>

<span data-ttu-id="64a90-141">Se você usar o cmdlet **Connect-PSSession** em uma sessão que não está desconectada, o comando não afetará a sessão e não gerará nenhum erro.</span><span class="sxs-lookup"><span data-stu-id="64a90-141">If you use the **Connect-PSSession** cmdlet on a session that is not disconnected, the command does not affect the session and it does not generate any errors.</span></span>

### <span data-ttu-id="64a90-142">Exemplo 3: série de comandos em um cenário empresarial</span><span class="sxs-lookup"><span data-stu-id="64a90-142">Example 3: Series of commands in an enterprise scenario</span></span>

```
The administrator starts by creating a sessions on a remote computer and running a script in the session.The first command uses the **New-PSSession** cmdlet to create the ITTask session on the Server01 remote computer. The command uses the *ConfigurationName* parameter to specify the ITTasks session configuration. The command saves the sessions in the $s variable.
PS C:\> $s = New-PSSession -ComputerName Server01 -Name ITTask -ConfigurationName ITTasks

 The second command **Invoke-Command** cmdlet to start a background job in the session in the $s variable. It uses the *FilePath* parameter to run the script in the background job.
PS C:\> Invoke-Command -Session $s {Start-Job -FilePath \\Server30\Scripts\Backup-SQLDatabase.ps1}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Running       True            Server01             \\Server30\Scripts\Backup...

The third command uses the Disconnect-PSSession cmdlet to disconnect from the session in the $s variable. The command uses the *OutputBufferingMode* parameter with a value of Drop to prevent the script from being blocked by having to deliver output to the session. It uses the *IdleTimeoutSec* parameter to extend the session time-out to 15 hours.When the command is completed, the administrator locks her computer and goes home for the evening.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None

Later that evening, the administrator starts her home computer, logs on to the corporate network, and starts PowerShell. The fourth command uses the Get-PSSession cmdlet to get the sessions on the Server01 computer. The command finds the ITTask session.The fifth command uses the **Connect-PSSession** cmdlet to connect to the ITTask session. The command saves the session in the $s variable.
PS C:\> Get-PSSession -ComputerName Server01 -Name ITTask

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None


PS C:\> $s = Connect-PSSession -ComputerName Server01 -Name ITTask


Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Opened        ITTasks               Available

The sixth command uses the **Invoke-Command** cmdlet to run a Get-Job command in the session in the $s variable. The output shows that the job finished successfully.The seventh command uses the **Invoke-Command** cmdlet to run a Receive-Job command in the session in the $s variable in the session. The command saves the results in the $BackupSpecs variable.The eighth command uses the **Invoke-Command** cmdlet to runs another script in the session. The command uses the value of the $BackupSpecs variable in the session as input to the script.


PS C:\> Invoke-Command -Session $s {Get-Job}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Completed     True            Server01             \\Server30\Scripts\Backup...

PS C:\> Invoke-Command -Session $s {$BackupSpecs = Receive-Job -JobName Job2}

PS C:\> Invoke-Command -Session $s {\\Server30\Scripts\New-SQLDatabase.ps1 -InitData $BackupSpecs.Initialization}

The ninth command disconnects from the session in the $s variable.The administrator closes PowerShell and closes the computer. She can reconnect to the session on the next day and check the script status from her work computer.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None
```

<span data-ttu-id="64a90-143">Esta série de comandos mostra como o cmdlet **Connect-PSSession** pode ser usado em um cenário empresarial.</span><span class="sxs-lookup"><span data-stu-id="64a90-143">This series of commands shows how the **Connect-PSSession** cmdlet might be used in an enterprise scenario.</span></span>
<span data-ttu-id="64a90-144">Nesse caso, uma administradora do sistema inicia um trabalho de longa execução em uma sessão em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="64a90-144">In this case, a system administrator starts a long-running job in a session on a remote computer.</span></span>
<span data-ttu-id="64a90-145">Após iniciar o trabalho, a administradora se desconecta da sessão e vai para casa.</span><span class="sxs-lookup"><span data-stu-id="64a90-145">After starting the job, the administrator disconnects from the session and goes home.</span></span>
<span data-ttu-id="64a90-146">Mais tarde, a noite, o administrador faz logon em seu computador doméstico e verifica se o trabalho foi executado até ser concluído.</span><span class="sxs-lookup"><span data-stu-id="64a90-146">Later that evening, the administrator logs on to her home computer and verifies that the job ran until it is completed.</span></span>

## <span data-ttu-id="64a90-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="64a90-147">PARAMETERS</span></span>

### <span data-ttu-id="64a90-148">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="64a90-148">-AllowRedirection</span></span>

<span data-ttu-id="64a90-149">Indica que esse cmdlet permite o redirecionamento dessa conexão para um URI alternativo.</span><span class="sxs-lookup"><span data-stu-id="64a90-149">Indicates that this cmdlet allows redirection of this connection to an alternate URI.</span></span>

<span data-ttu-id="64a90-150">Quando você usa o parâmetro *ConnectionURI* , o destino remoto pode retornar uma instrução para redirecionar para um URI diferente.</span><span class="sxs-lookup"><span data-stu-id="64a90-150">When you use the *ConnectionURI* parameter, the remote destination can return an instruction to redirect to a different URI.</span></span>
<span data-ttu-id="64a90-151">Por padrão, o PowerShell não redireciona conexões, mas você pode usar esse parâmetro para permitir que ele redirecione a conexão.</span><span class="sxs-lookup"><span data-stu-id="64a90-151">By default, PowerShell does not redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="64a90-152">É possível também limitar o número de vezes que a conexão é redirecionada alterando o valor da opção de sessão **MaximumConnectionRedirectionCount** .</span><span class="sxs-lookup"><span data-stu-id="64a90-152">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span>
<span data-ttu-id="64a90-153">Use o parâmetro *MaximumRedirection* do cmdlet New-PSSessionOption ou defina a propriedade **MaximumConnectionRedirectionCount** da variável de preferência **$PSSessionOption** .</span><span class="sxs-lookup"><span data-stu-id="64a90-153">Use the *MaximumRedirection* parameter of the New-PSSessionOption cmdlet or set the **MaximumConnectionRedirectionCount** property of the **$PSSessionOption** preference variable.</span></span>
<span data-ttu-id="64a90-154">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="64a90-154">The default value is 5.</span></span>

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

### <span data-ttu-id="64a90-155">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="64a90-155">-ApplicationName</span></span>

<span data-ttu-id="64a90-156">Especifica o nome de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="64a90-156">Specifies the name of an application.</span></span>
<span data-ttu-id="64a90-157">Esse cmdlet se conecta somente a sessões que usam o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="64a90-157">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="64a90-158">Insira o segmento de nome de aplicativo do URI de conexão.</span><span class="sxs-lookup"><span data-stu-id="64a90-158">Enter the application name segment of the connection URI.</span></span>
<span data-ttu-id="64a90-159">Por exemplo, no seguinte URI de conexão, o nome do aplicativo é WSMan: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="64a90-159">For example, in the following connection URI, the application name is WSMan: `http://localhost:5985/WSMAN`.</span></span>
<span data-ttu-id="64a90-160">O nome de aplicativo de uma sessão é armazenado na propriedade **Runspace.ConnectionInfo.AppName** da sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-160">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="64a90-161">O valor desse parâmetro é usado para selecionar e filtrar sessões.</span><span class="sxs-lookup"><span data-stu-id="64a90-161">The value of this parameter is used to select and filter sessions.</span></span>
<span data-ttu-id="64a90-162">Ele não altera o aplicativo utilizado pela sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-162">It does not change the application that the session uses.</span></span>

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

### <span data-ttu-id="64a90-163">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="64a90-163">-Authentication</span></span>

<span data-ttu-id="64a90-164">Especifica o mecanismo usado para autenticar credenciais de usuário no comando para reconectar-se à sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="64a90-164">Specifies the mechanism that is used to authenticate user credentials in the command to reconnect to the disconnected session.</span></span> <span data-ttu-id="64a90-165">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="64a90-165">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="64a90-166">Padrão</span><span class="sxs-lookup"><span data-stu-id="64a90-166">Default</span></span>
- <span data-ttu-id="64a90-167">Básico</span><span class="sxs-lookup"><span data-stu-id="64a90-167">Basic</span></span>
- <span data-ttu-id="64a90-168">CredSSP</span><span class="sxs-lookup"><span data-stu-id="64a90-168">Credssp</span></span>
- <span data-ttu-id="64a90-169">Digest</span><span class="sxs-lookup"><span data-stu-id="64a90-169">Digest</span></span>
- <span data-ttu-id="64a90-170">Kerberos</span><span class="sxs-lookup"><span data-stu-id="64a90-170">Kerberos</span></span>
- <span data-ttu-id="64a90-171">Negotiate</span><span class="sxs-lookup"><span data-stu-id="64a90-171">Negotiate</span></span>
- <span data-ttu-id="64a90-172">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="64a90-172">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="64a90-173">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="64a90-173">The default value is Default.</span></span>

<span data-ttu-id="64a90-174">Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="64a90-174">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in the MSDN library.</span></span>

<span data-ttu-id="64a90-175">Cuidado: a autenticação do Credential Security Support Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="64a90-175">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
<span data-ttu-id="64a90-176">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="64a90-176">This mechanism increases the security risk of the remote operation.</span></span>
<span data-ttu-id="64a90-177">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="64a90-177">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

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

### <span data-ttu-id="64a90-178">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="64a90-178">-CertificateThumbprint</span></span>

<span data-ttu-id="64a90-179">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para se conectar à sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="64a90-179">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="64a90-180">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="64a90-180">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="64a90-181">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="64a90-181">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="64a90-182">Eles podem ser mapeados somente para contas de usuário local.</span><span class="sxs-lookup"><span data-stu-id="64a90-182">They can be mapped only to local user accounts.</span></span>
<span data-ttu-id="64a90-183">Eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="64a90-183">They do not work with domain accounts.</span></span>

<span data-ttu-id="64a90-184">Para obter uma impressão digital do certificado, use um comando Get-Item ou Get-ChildItem na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="64a90-184">To get a certificate thumbprint, use a Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="64a90-185">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="64a90-185">-ComputerName</span></span>

<span data-ttu-id="64a90-186">Especifica os computadores nos quais as sessões desconectadas estão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="64a90-186">Specifies the computers on which the disconnected sessions are stored.</span></span>
<span data-ttu-id="64a90-187">As sessões são armazenadas no computador que está no lado do servidor ou no fim do recebimento de uma conexão.</span><span class="sxs-lookup"><span data-stu-id="64a90-187">Sessions are stored on the computer that is at the server-side or receiving end of a connection.</span></span>
<span data-ttu-id="64a90-188">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="64a90-188">The default is the local computer.</span></span>

<span data-ttu-id="64a90-189">Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um computador.</span><span class="sxs-lookup"><span data-stu-id="64a90-189">Type the NetBIOS name, an IP address, or a fully qualified domain name of one computer.</span></span>
<span data-ttu-id="64a90-190">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="64a90-190">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="64a90-191">Para especificar o computador local, digite o nome do computador, localhost ou um ponto (.)</span><span class="sxs-lookup"><span data-stu-id="64a90-191">To specify the local computer, type the computer name, localhost, or a dot (.)</span></span>

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

### <span data-ttu-id="64a90-192">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="64a90-192">-ConfigurationName</span></span>

<span data-ttu-id="64a90-193">Conecta-se somente a sessões que usam a configuração de sessão especificada.</span><span class="sxs-lookup"><span data-stu-id="64a90-193">Connects only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="64a90-194">Insira um nome de configuração ou o URI do recurso totalmente qualificado para uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-194">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span>
<span data-ttu-id="64a90-195">Se você especificar apenas o nome da configuração, o seguinte URI de esquema será anexado: `http://schemas.microsoft.com/powershell` .</span><span class="sxs-lookup"><span data-stu-id="64a90-195">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span>
<span data-ttu-id="64a90-196">O nome de configuração de uma sessão é armazenado na propriedade **ConfigurationName** da sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-196">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="64a90-197">O valor desse parâmetro é usado para selecionar e filtrar sessões.</span><span class="sxs-lookup"><span data-stu-id="64a90-197">The value of this parameter is used to select and filter sessions.</span></span>
<span data-ttu-id="64a90-198">Ele não altera a configuração de sessão utilizada pela sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-198">It does not change the session configuration that the session uses.</span></span>

<span data-ttu-id="64a90-199">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="64a90-199">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

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

### <span data-ttu-id="64a90-200">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="64a90-200">-ConnectionUri</span></span>

<span data-ttu-id="64a90-201">Especifica os URIs dos pontos de extremidade de conexão para as sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="64a90-201">Specifies the URIs of the connection endpoints for the disconnected sessions.</span></span>

<span data-ttu-id="64a90-202">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="64a90-202">The URI must be fully qualified.</span></span>
<span data-ttu-id="64a90-203">O formato dessa cadeia de caracteres é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="64a90-203">The format of this string is as follows:</span></span>

`\<Transport\>://\<ComputerName\>:\<Port\>/\<ApplicationName\>`

<span data-ttu-id="64a90-204">O valor padrão é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="64a90-204">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="64a90-205">Se você não especificar um URI de conexão, poderá usar os parâmetros *UseSSL* e *Port* para especificar os valores de URI de conexão.</span><span class="sxs-lookup"><span data-stu-id="64a90-205">If you do not specify a connection URI, you can use the *UseSSL* and *Port* parameters to specify the connection URI values.</span></span>

<span data-ttu-id="64a90-206">Os valores válidos para o segmento **Transport** do URI são HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="64a90-206">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span>
<span data-ttu-id="64a90-207">Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada com portas de padrões: 80 para HTTP e 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="64a90-207">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span>
<span data-ttu-id="64a90-208">Para usar as portas padrão para comunicação remota do PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="64a90-208">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="64a90-209">Se o computador de destino redireciona a conexão para um URI diferente, o PowerShell impede o redirecionamento, a menos que você use o parâmetro *AllowRedirection* no comando.</span><span class="sxs-lookup"><span data-stu-id="64a90-209">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the *AllowRedirection* parameter in the command.</span></span>

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

### <span data-ttu-id="64a90-210">-Credential</span><span class="sxs-lookup"><span data-stu-id="64a90-210">-Credential</span></span>

<span data-ttu-id="64a90-211">Especifica uma conta de usuário que tem permissão para se conectar à sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="64a90-211">Specifies a user account that has permission to connect to the disconnected session.</span></span>
<span data-ttu-id="64a90-212">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="64a90-212">The default is the current user.</span></span>

<span data-ttu-id="64a90-213">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="64a90-213">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="64a90-214">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="64a90-214">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="64a90-215">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="64a90-215">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="64a90-216">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="64a90-216">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="64a90-217">-Id</span><span class="sxs-lookup"><span data-stu-id="64a90-217">-Id</span></span>

<span data-ttu-id="64a90-218">Especifica as IDs das sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="64a90-218">Specifies the IDs of the disconnected sessions.</span></span>
<span data-ttu-id="64a90-219">O parâmetro *ID* só funcionará quando a sessão desconectada tiver sido conectada anteriormente à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="64a90-219">The *Id* parameter works only when the disconnected session was previously connected to the current session.</span></span>

<span data-ttu-id="64a90-220">Este parâmetro é válido, mas não é eficaz, quando a sessão está armazenada no computador local, mas não estava conectada à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="64a90-220">This parameter is valid, but not effective, when the session is stored on the local computer, but was not connected to the current session.</span></span>

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

### <span data-ttu-id="64a90-221">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="64a90-221">-InstanceId</span></span>

<span data-ttu-id="64a90-222">Especifica as IDs de instância das sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="64a90-222">Specifies the instance IDs of the disconnected sessions.</span></span>

<span data-ttu-id="64a90-223">A ID da instância é um GUID que identifica exclusivamente uma **PSSession** em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="64a90-223">The instance ID is a GUID that uniquely identifies a **PSSession** on a local or remote computer.</span></span>

<span data-ttu-id="64a90-224">A ID da instância é armazenada na propriedade **InstanceId** da **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="64a90-224">The instance ID is stored in the **InstanceID** property of the **PSSession** .</span></span>

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

### <span data-ttu-id="64a90-225">-Name</span><span class="sxs-lookup"><span data-stu-id="64a90-225">-Name</span></span>

<span data-ttu-id="64a90-226">Especifica os nomes amigáveis das sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="64a90-226">Specifies the friendly names of the disconnected sessions.</span></span>

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

### <span data-ttu-id="64a90-227">-Port</span><span class="sxs-lookup"><span data-stu-id="64a90-227">-Port</span></span>

<span data-ttu-id="64a90-228">Especifica a porta de rede no computador remoto que é usada para se reconectar à sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-228">Specifies the network port on the remote computer that is used to reconnect to the session.</span></span>
<span data-ttu-id="64a90-229">Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão.</span><span class="sxs-lookup"><span data-stu-id="64a90-229">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span>
<span data-ttu-id="64a90-230">As portas padrão são 5985, que é a porta do WinRM para HTTP e 5986, que é a porta do WinRM para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="64a90-230">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="64a90-231">Antes de usar uma porta alternativa, você deve configurar o ouvinte de WinRM no computador remoto para escutar na porta.</span><span class="sxs-lookup"><span data-stu-id="64a90-231">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span>
<span data-ttu-id="64a90-232">Para configurar o ouvinte, digite os dois comandos a seguir no prompt do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="64a90-232">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="64a90-233">Não use o parâmetro *Port* a menos que seja necessário.</span><span class="sxs-lookup"><span data-stu-id="64a90-233">Do not use the *Port* parameter unless you must.</span></span>
<span data-ttu-id="64a90-234">A porta que está definida no comando se aplica a todos os computadores ou sessões em que o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="64a90-234">The port that is set in the command applies to all computers or sessions on which the command runs.</span></span>
<span data-ttu-id="64a90-235">Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="64a90-235">An alternate port setting might prevent the command from running on all computers.</span></span>

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

### <span data-ttu-id="64a90-236">-Sessão</span><span class="sxs-lookup"><span data-stu-id="64a90-236">-Session</span></span>

<span data-ttu-id="64a90-237">Especifica as sessões desconectadas.</span><span class="sxs-lookup"><span data-stu-id="64a90-237">Specifies the disconnected sessions.</span></span>
<span data-ttu-id="64a90-238">Insira uma variável que contém os objetos **PSSession** ou um comando que cria ou obtém os objetos **PSSession** , como um comando Get-PSSession.</span><span class="sxs-lookup"><span data-stu-id="64a90-238">Enter a variable that contains the **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a Get-PSSession command.</span></span>

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

### <span data-ttu-id="64a90-239">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="64a90-239">-SessionOption</span></span>

<span data-ttu-id="64a90-240">Especifica as opções avançadas para a sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-240">Specifies advanced options for the session.</span></span>
<span data-ttu-id="64a90-241">Insira um objeto **SessionOption** , como um que você cria usando o cmdlet New-PSSessionOption ou uma tabela de hash na qual as chaves são nomes de opção de sessão e os valores são valores de opção de sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-241">Enter a **SessionOption** object, such as one that you create by using the New-PSSessionOption cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="64a90-242">Os valores padrão das opções são determinados pelo valor da variável de preferência $PSSessionOption, se definida.</span><span class="sxs-lookup"><span data-stu-id="64a90-242">The default values for the options are determined by the value of the $PSSessionOption preference variable, if it is set.</span></span>
<span data-ttu-id="64a90-243">Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-243">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="64a90-244">Os valores de opção da sessão têm precedência sobre os valores padrão de sessões definidos na variável de preferência $PSSessionOption e na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-244">The session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span>
<span data-ttu-id="64a90-245">No entanto, eles não têm precedência sobre valores máximos, cotas ou limites definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-245">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="64a90-246">Para obter uma descrição das opções de sessão que incluem os valores padrão, consulte New-PSSessionOption.</span><span class="sxs-lookup"><span data-stu-id="64a90-246">For a description of the session options that includes the default values, see New-PSSessionOption.</span></span>
<span data-ttu-id="64a90-247">Para obter informações sobre a variável de preferência de **$PSSessionOption** , consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="64a90-247">For information about the **$PSSessionOption** preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="64a90-248">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="64a90-248">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

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

### <span data-ttu-id="64a90-249">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="64a90-249">-ThrottleLimit</span></span>

<span data-ttu-id="64a90-250">Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="64a90-250">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="64a90-251">Se você omite esse parâmetro ou digita um valor 0, o valor padrão, 32, é usado.</span><span class="sxs-lookup"><span data-stu-id="64a90-251">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="64a90-252">O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="64a90-252">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="64a90-253">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="64a90-253">-UseSSL</span></span>

<span data-ttu-id="64a90-254">Indica que esse cmdlet usa o protocolo protocolo SSL (SSL) para se conectar à sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="64a90-254">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to connect to the disconnected session.</span></span> <span data-ttu-id="64a90-255">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="64a90-255">By default, SSL is not used.</span></span>

<span data-ttu-id="64a90-256">WS-Management criptografa todo o conteúdo do PowerShell transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="64a90-256">WS-Management encrypts all PowerShell content transmitted over the network.</span></span>
<span data-ttu-id="64a90-257">O parâmetro *UseSSL* é uma proteção adicional que envia os dados por uma conexão HTTPS em vez de uma conexão http.</span><span class="sxs-lookup"><span data-stu-id="64a90-257">The *UseSSL* parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="64a90-258">Se você usar esse parâmetro, mas o SSL não estiver disponível na porta usada para o comando, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="64a90-258">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

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

### <span data-ttu-id="64a90-259">-Confirm</span><span class="sxs-lookup"><span data-stu-id="64a90-259">-Confirm</span></span>

<span data-ttu-id="64a90-260">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="64a90-260">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="64a90-261">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="64a90-261">-WhatIf</span></span>

<span data-ttu-id="64a90-262">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="64a90-262">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="64a90-263">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="64a90-263">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="64a90-264">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="64a90-264">CommonParameters</span></span>

<span data-ttu-id="64a90-265">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="64a90-265">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="64a90-266">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="64a90-266">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="64a90-267">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="64a90-267">INPUTS</span></span>

### <span data-ttu-id="64a90-268">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="64a90-268">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="64a90-269">Você pode canalizar uma sessão ( **PSSession** ) para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="64a90-269">You can pipe a session ( **PSSession** ) to this cmdlet.</span></span>

## <span data-ttu-id="64a90-270">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="64a90-270">OUTPUTS</span></span>

### <span data-ttu-id="64a90-271">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="64a90-271">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="64a90-272">Esse cmdlet retorna um objeto que representa a sessão à qual ele se reconecta.</span><span class="sxs-lookup"><span data-stu-id="64a90-272">This cmdlet returns an object that represents the session to which it reconnected.</span></span>

## <span data-ttu-id="64a90-273">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="64a90-273">NOTES</span></span>

* <span data-ttu-id="64a90-274">**Connect-PSSession** se reconecta somente a sessões desconectadas, ou seja, sessões que têm um valor de desconectado para a propriedade de **estado** .</span><span class="sxs-lookup"><span data-stu-id="64a90-274">**Connect-PSSession** reconnects only to sessions that are disconnected, that is, sessions that have a value of Disconnected for the **State** property.</span></span> <span data-ttu-id="64a90-275">Somente as sessões que estão conectadas ou terminam em computadores que executam o Windows PowerShell 3,0 ou versões posteriores podem ser desconectadas e reconectadas.</span><span class="sxs-lookup"><span data-stu-id="64a90-275">Only sessions that are connected to, or end at, computers that run Windows PowerShell 3.0 or later versions can be disconnected and reconnected.</span></span>
* <span data-ttu-id="64a90-276">Se você usar **Connect-PSSession** em uma sessão que não está desconectada, o comando não afetará a sessão e não gerará erros.</span><span class="sxs-lookup"><span data-stu-id="64a90-276">If you use **Connect-PSSession** on a session that is not disconnected, the command does not affect the session and it does not generate errors.</span></span>
* <span data-ttu-id="64a90-277">Sessões de loopback desconectadas com tokens interativos, que são criadas usando o parâmetro *EnableNetworkAccess* , podem ser reconectadas somente do computador no qual a sessão foi criada.</span><span class="sxs-lookup"><span data-stu-id="64a90-277">Disconnected loopback sessions with interactive tokens, which are created by using the *EnableNetworkAccess* parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="64a90-278">Essa restrição protege o computador contra acessos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="64a90-278">This restriction protects the computer from malicious access.</span></span>
* <span data-ttu-id="64a90-279">O valor da propriedade **State** de uma **PSSession** é relativo à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="64a90-279">The value of the **State** property of a **PSSession** is relative to the current session.</span></span>
<span data-ttu-id="64a90-280">Portanto, um valor de **desconectado** significa que a **PSSession** não está conectada à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="64a90-280">Therefore, a value of **Disconnected** means that the **PSSession** is not connected to the current session.</span></span> <span data-ttu-id="64a90-281">No entanto, isso não significa que a **PSSession** seja desconectada de todas as sessões.</span><span class="sxs-lookup"><span data-stu-id="64a90-281">However, it does not mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="64a90-282">Ela pode ser conectada a uma sessão diferente.</span><span class="sxs-lookup"><span data-stu-id="64a90-282">It might be connected to a different session.</span></span> <span data-ttu-id="64a90-283">Para determinar se é possível conectar-se ou reconectar-se à sessão, utilize a propriedade **Availability** .</span><span class="sxs-lookup"><span data-stu-id="64a90-283">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

  <span data-ttu-id="64a90-284">Um valor **Availability** de None indica que é possível conectar-se à sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-284">An **Availability** value of None indicates that you can connect to the session.</span></span>
<span data-ttu-id="64a90-285">Um valor de ocupado indica que você não pode se conectar à **PSSession** porque ela está conectada a outra sessão.</span><span class="sxs-lookup"><span data-stu-id="64a90-285">A value of Busy indicates that you cannot connect to the **PSSession** because it is connected to another session.</span></span>

  <span data-ttu-id="64a90-286">Para obter mais informações sobre os valores da propriedade **State** de sessões, consulte [Enumeração RUNSPACESTATE](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="64a90-286">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) in the MSDN library.</span></span>

  <span data-ttu-id="64a90-287">Para obter mais informações sobre os valores da propriedade de sessões de **disponibilidade** , consulte [Enumeração RUNSPACEAVAILABILITY](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="64a90-287">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) in the MSDN library.</span></span>

* <span data-ttu-id="64a90-288">Não é possível alterar o valor de tempo limite ocioso de uma **PSSession** quando você se conecta à **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="64a90-288">You cannot change the idle time-out value of a **PSSession** when you connect to the **PSSession** .</span></span> <span data-ttu-id="64a90-289">O parâmetro *SessionOption* de **Connect-PSSession** usa um objeto **SessionOption** que tem um valor **IdleTimeout** .</span><span class="sxs-lookup"><span data-stu-id="64a90-289">The *SessionOption* parameter of **Connect-PSSession** takes a **SessionOption** object that has an **IdleTimeout** value.</span></span> <span data-ttu-id="64a90-290">No entanto, o valor **IdleTimeout** do objeto **SessionOption** e o valor **IdleTimeout** da variável $PSSessionOption são ignorados ao se conectar a uma **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="64a90-290">However, the **IdleTimeout** value of the **SessionOption** object and the **IdleTimeout** value of the $PSSessionOption variable are ignored when connecting to a **PSSession** .</span></span>

  <span data-ttu-id="64a90-291">Você pode definir e alterar o tempo limite de ociosidade de uma **PSSession** ao criar a **PSSession** , usando os cmdlets **New-PSSession** ou **Invoke-Command** e quando você se desconecta da **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="64a90-291">You can set and change the idle time-out of a **PSSession** when you create the **PSSession** , by using the **New-PSSession** or **Invoke-Command** cmdlets, and when you disconnect from the **PSSession** .</span></span>

  <span data-ttu-id="64a90-292">A propriedade **IdleTimeout** de uma **PSSession** é crítica para sessões desconectadas, pois determina por quanto tempo uma sessão desconectada é mantida no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="64a90-292">The **IdleTimeout** property of a **PSSession** is critical to disconnected sessions, because it determines how long a disconnected session is maintained on the remote computer.</span></span>
<span data-ttu-id="64a90-293">Sessões desconectadas são consideradas ociosas desde o momento em que são desconectadas, ainda que comandos estejam em execução na sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="64a90-293">Disconnected sessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

## <span data-ttu-id="64a90-294">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="64a90-294">RELATED LINKS</span></span>

[<span data-ttu-id="64a90-295">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="64a90-295">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="64a90-296">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="64a90-296">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="64a90-297">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="64a90-297">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="64a90-298">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="64a90-298">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="64a90-299">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="64a90-299">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="64a90-300">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="64a90-300">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="64a90-301">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="64a90-301">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="64a90-302">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="64a90-302">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="64a90-303">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="64a90-303">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="64a90-304">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="64a90-304">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="64a90-305">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="64a90-305">Remove-PSSession</span></span>](Remove-PSSession.md)
