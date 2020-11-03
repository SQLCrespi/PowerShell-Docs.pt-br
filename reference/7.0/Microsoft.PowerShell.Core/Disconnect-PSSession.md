---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disconnect-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-PSSession
ms.openlocfilehash: b3ee9ce8f699e66a091a017eb8c1b0c49f1b7636
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194962"
---
# <span data-ttu-id="0fb75-103">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="0fb75-103">Disconnect-PSSession</span></span>

## <span data-ttu-id="0fb75-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0fb75-104">SYNOPSIS</span></span>
<span data-ttu-id="0fb75-105">Desconecta-se de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="0fb75-105">Disconnects from a session.</span></span>

## <span data-ttu-id="0fb75-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0fb75-106">SYNTAX</span></span>

### <span data-ttu-id="0fb75-107">Sessão (padrão)</span><span class="sxs-lookup"><span data-stu-id="0fb75-107">Session (Default)</span></span>

```
Disconnect-PSSession [-Session] <PSSession[]> [-IdleTimeoutSec <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="0fb75-108">Name</span><span class="sxs-lookup"><span data-stu-id="0fb75-108">Name</span></span>

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0fb75-109">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0fb75-109">InstanceId</span></span>

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0fb75-110">ID</span><span class="sxs-lookup"><span data-stu-id="0fb75-110">Id</span></span>

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0fb75-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fb75-111">DESCRIPTION</span></span>

<span data-ttu-id="0fb75-112">O `Disconnect-PSSession` cmdlet desconecta uma sessão do PowerShell ("PSSession"), como uma iniciada usando o `New-PSSession` cmdlet, da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0fb75-112">The `Disconnect-PSSession` cmdlet disconnects a PowerShell session ("PSSession"), such as one started by using the `New-PSSession` cmdlet, from the current session.</span></span> <span data-ttu-id="0fb75-113">Como resultado, a PSSession está em um estado desconectado.</span><span class="sxs-lookup"><span data-stu-id="0fb75-113">As a result, the PSSession is in a disconnected state.</span></span> <span data-ttu-id="0fb75-114">Você pode conectar-se à PSSession desconectada por meio da sessão atual ou de outra sessão no computador local ou em um computador diferente.</span><span class="sxs-lookup"><span data-stu-id="0fb75-114">You can connect to the disconnected PSSession from the current session or from another session on the local computer or a different computer.</span></span>

<span data-ttu-id="0fb75-115">O `Disconnect-PSSession` cmdlet desconecta apenas as PSSessions abertas que estão conectadas à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0fb75-115">The `Disconnect-PSSession` cmdlet disconnects only open PSSessions that are connected to the current session.</span></span> <span data-ttu-id="0fb75-116">`Disconnect-PSSession` Não é possível desconectar PSSessions rompidos ou fechados, ou PSSessions interativas iniciadas usando o `Enter-PSSession` cmdlet, e não pode desconectar PSSessions que estão conectadas a outras sessões.</span><span class="sxs-lookup"><span data-stu-id="0fb75-116">`Disconnect-PSSession` cannot disconnect broken or closed PSSessions, or interactive PSSessions started by using the `Enter-PSSession` cmdlet, and it cannot disconnect PSSessions that are connected to other sessions.</span></span>

<span data-ttu-id="0fb75-117">Para reconectar-se a uma PSSession desconectada, use os `Connect-PSSession` `Receive-PSSession` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="0fb75-117">To reconnect to a disconnected PSSession, use the `Connect-PSSession` or `Receive-PSSession` cmdlets.</span></span>

<span data-ttu-id="0fb75-118">Quando uma PSSession é desconectada, os comandos na PSSession continuam em execução até que sejam concluídos, a menos que a PSSession expire ou os comandos na PSSession sejam bloqueados por um buffer de saída completo.</span><span class="sxs-lookup"><span data-stu-id="0fb75-118">When a PSSession is disconnected, the commands in the PSSession continue to run until they complete, unless the PSSession times out or the commands in the PSSession are blocked by a full output buffer.</span></span> <span data-ttu-id="0fb75-119">Para alterar o tempo limite de inatividade, use o parâmetro **IdleTimeoutSec** .</span><span class="sxs-lookup"><span data-stu-id="0fb75-119">To change the idle timeout, use the **IdleTimeoutSec** parameter.</span></span> <span data-ttu-id="0fb75-120">Para alterar o modo de buffer de saída, use o parâmetro **OutputBufferingMode** você também pode usar o parâmetro **InDisconnectedSession** do `Invoke-Command` cmdlet para executar um comando em uma sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="0fb75-120">To change the output buffering mode, use the **OutputBufferingMode** parameter You can also use the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet to run a command in a disconnected session.</span></span>

<span data-ttu-id="0fb75-121">Para obter mais informações sobre o recurso de Sessões desconectadas, consulte [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).</span><span class="sxs-lookup"><span data-stu-id="0fb75-121">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="0fb75-122">Este cmdlet é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0fb75-122">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="0fb75-123">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0fb75-123">EXAMPLES</span></span>

### <span data-ttu-id="0fb75-124">Exemplo 1-desconectar uma sessão por nome</span><span class="sxs-lookup"><span data-stu-id="0fb75-124">Example 1 - Disconnect a session by name</span></span>

<span data-ttu-id="0fb75-125">Este comando desconecta UpdateSession PSSession no computador Server01 da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0fb75-125">This command disconnects the UpdateSession PSSession on the Server01 computer from the current session.</span></span> <span data-ttu-id="0fb75-126">O comando usa o parâmetro **Name** para identificar a PSSession.</span><span class="sxs-lookup"><span data-stu-id="0fb75-126">The command uses the **Name** parameter to identify the PSSession.</span></span>

```
PS> Disconnect-PSSession -Name UpdateSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  UpdateSession   Server01        Disconnected  Microsoft.PowerShell          None
```

<span data-ttu-id="0fb75-127">A saída mostra que a tentativa de desconectar foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="0fb75-127">The output shows that the attempt to disconnect was successful.</span></span> <span data-ttu-id="0fb75-128">O estado da sessão é desconectado e a disponibilidade é nenhuma, o que indica que a sessão não está ocupada e pode ser reconectada.</span><span class="sxs-lookup"><span data-stu-id="0fb75-128">The session state is Disconnected and the Availability is None, which indicates that the session is not busy and can be reconnected.</span></span>

### <span data-ttu-id="0fb75-129">Exemplo 2-desconectar uma sessão de um computador específico</span><span class="sxs-lookup"><span data-stu-id="0fb75-129">Example 2 - Disconnect a session from a specific computer</span></span>

<span data-ttu-id="0fb75-130">Este comando desconecta ITTask PSSession no computador Server12 da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0fb75-130">This command disconnects the ITTask PSSession on the Server12 computer from the current session.</span></span>
<span data-ttu-id="0fb75-131">A sessão ITTask foi criada na sessão atual e se conecta-se ao computador Server12.</span><span class="sxs-lookup"><span data-stu-id="0fb75-131">The ITTask session was created in the current session and connects to the Server12 computer.</span></span> <span data-ttu-id="0fb75-132">O comando usa o `Get-PSSession` cmdlet para obter a sessão e o `Disconnect-PSSession` cmdlet para desconectá-lo.</span><span class="sxs-lookup"><span data-stu-id="0fb75-132">The command uses the `Get-PSSession` cmdlet to get the session and the `Disconnect-PSSession` cmdlet to disconnect it.</span></span>

```
PS> Get-PSSession -ComputerName Server12 -Name ITTask |
  Disconnect-PSSession -OutputBufferingMode Drop -IdleTimeoutSec 86400
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  ITTask          Server12        Disconnected  ITTasks               None
```

<span data-ttu-id="0fb75-133">O `Disconnect-PSSession` comando usa o parâmetro **OutputBufferingMode** para definir o modo de saída como **drop** .</span><span class="sxs-lookup"><span data-stu-id="0fb75-133">The `Disconnect-PSSession` command uses the **OutputBufferingMode** parameter to set the output mode to **Drop** .</span></span> <span data-ttu-id="0fb75-134">Essa configuração garante que o script em execução na sessão pode ser executado mesmo que o buffer de saída da sessão esteja cheio.</span><span class="sxs-lookup"><span data-stu-id="0fb75-134">This setting ensures that the script that is running in the session can continue to run even if the session output buffer is full.</span></span> <span data-ttu-id="0fb75-135">Como o script grava a saída de um relatório em um compartilhamento de arquivos, outras saídas podem ser perdidas sem consequências.</span><span class="sxs-lookup"><span data-stu-id="0fb75-135">Because the script writes its output to a report on a file share, other output can be lost without consequence.</span></span>

<span data-ttu-id="0fb75-136">O comando também usa o parâmetro **IdleTimeoutSec** para estender o tempo limite de inatividade da sessão para 24 horas.</span><span class="sxs-lookup"><span data-stu-id="0fb75-136">The command also uses the **IdleTimeoutSec** parameter to extend the idle timeout of the session to 24 hours.</span></span> <span data-ttu-id="0fb75-137">Essa configuração concede tempo para que esse e outros administradores reconectem-se à sessão para verificar se o script foi executado e solucionem os problemas necessários.</span><span class="sxs-lookup"><span data-stu-id="0fb75-137">This setting allows time for this administrator or other administrators to reconnect to the session to verify that the script ran and troubleshoot if needed.</span></span>

### <span data-ttu-id="0fb75-138">Exemplo 3-usando várias PSSessions em vários computadores</span><span class="sxs-lookup"><span data-stu-id="0fb75-138">Example 3 - Using multiple PSSessions on multiple computers</span></span>

<span data-ttu-id="0fb75-139">Esta série de comandos mostra como o `Disconnect-PSSession` cmdlet pode ser usado em um cenário empresarial.</span><span class="sxs-lookup"><span data-stu-id="0fb75-139">This series of commands shows how the `Disconnect-PSSession` cmdlet might be used in an enterprise scenario.</span></span> <span data-ttu-id="0fb75-140">Nesse caso, um novo técnico inicia um script em uma sessão em um computador remoto e encontra um problema.</span><span class="sxs-lookup"><span data-stu-id="0fb75-140">In this case, a new technician starts a script in a session on a remote computer and runs into a problem.</span></span> <span data-ttu-id="0fb75-141">O técnico se desconecta da sessão para que um gerente mais experiente possa se conectar a ela e resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="0fb75-141">The technician disconnects from the session so that a more experienced manager can connect to the session and resolve the problem.</span></span>

```
PS> $s = New-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
PS> Invoke-Command $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Get-PSSession -Name ITTask -ComputerName Srv1 | Disconnect-PSSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1 ITTask           Srv1            Disconnected  Microsoft.PowerShell          None

PS> Get-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None
 2 ITTask          Srv2            Opened        Microsoft.PowerShell     Available
 3 ITTask          Srv30           Opened        Microsoft.PowerShell     Available

PS> Get-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None

PS> $s = Connect-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
PS> Invoke-Command -Session $s {dir $home\Scripts\PatchStatusOutput.ps1}
PS> Invoke-Command -Session $s {mkdir $home\Scripts\PatchStatusOutput}
PS> Invoke-Command -Session $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Disconnect-PSSession -Session $s
```

<span data-ttu-id="0fb75-142">O técnico começa criando sessões em vários computadores remotos e executando um script em cada sessão.</span><span class="sxs-lookup"><span data-stu-id="0fb75-142">The technician begins by creating sessions on several remote computers and running a script in each session.</span></span> <span data-ttu-id="0fb75-143">O primeiro comando usa o `New-PSSession` cmdlet para criar a sessão ITTask em três computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="0fb75-143">The first command uses the `New-PSSession` cmdlet to create the ITTask session on three remote computers.</span></span> <span data-ttu-id="0fb75-144">O comando salva as sessões na variável $s.</span><span class="sxs-lookup"><span data-stu-id="0fb75-144">The command saves the sessions in the $s variable.</span></span> <span data-ttu-id="0fb75-145">O segundo comando usa o parâmetro **FilePath** do `Invoke-Command` cmdlet para executar um script nas sessões na variável $s.</span><span class="sxs-lookup"><span data-stu-id="0fb75-145">The second command uses the **FilePath** parameter of the `Invoke-Command` cmdlet to run a script in the sessions in the $s variable.</span></span>

<span data-ttu-id="0fb75-146">O script em execução no computador Srv1 gera erros inesperados.</span><span class="sxs-lookup"><span data-stu-id="0fb75-146">The script running on the Srv1 computer generates unexpected errors.</span></span> <span data-ttu-id="0fb75-147">O técnico entra em contato com seu gerente e pede assistência.</span><span class="sxs-lookup"><span data-stu-id="0fb75-147">The technician contacts his manager and asks for assistance.</span></span> <span data-ttu-id="0fb75-148">O gerente instrui o técnico a se desconectar da sessão para que possa investigar. O segundo comando usa o `Get-PSSession` cmdlet para obter a sessão ITTask no computador Srv1 e o `Disconnect-PSSession` cmdlet para desconectá-lo.</span><span class="sxs-lookup"><span data-stu-id="0fb75-148">The manager directs the technician to disconnect from the session so he can investigate.The second command uses the `Get-PSSession` cmdlet to get the ITTask session on the Srv1 computer and the `Disconnect-PSSession` cmdlet to disconnect it.</span></span> <span data-ttu-id="0fb75-149">Esse comando não afeta as sessões de ITTask nos outros computadores.</span><span class="sxs-lookup"><span data-stu-id="0fb75-149">This command does not affect the ITTask sessions on the other computers.</span></span>

<span data-ttu-id="0fb75-150">O terceiro comando usa o `Get-PSSession` cmdlet para obter as sessões de ITTask.</span><span class="sxs-lookup"><span data-stu-id="0fb75-150">The third command uses the `Get-PSSession` cmdlet to get the ITTask sessions.</span></span> <span data-ttu-id="0fb75-151">A saída mostra que as sessões ITTask nos computadores Srv2 e Srv30 não foram afetadas pelo comando de desconectar.</span><span class="sxs-lookup"><span data-stu-id="0fb75-151">The output shows that the ITTask sessions on the Srv2 and Srv30 computers were not affected by the command to disconnect.</span></span>

<span data-ttu-id="0fb75-152">O Gerenciador faz logon em seu computador doméstico, conecta-se à sua rede corporativa, inicia o PowerShell e usa o `Get-PSSession` cmdlet para obter a sessão ITTask no computador Srv1.</span><span class="sxs-lookup"><span data-stu-id="0fb75-152">The manager logs on to his home computer, connects to his corporate network, starts PowerShell, and uses the `Get-PSSession` cmdlet to get the ITTask session on the Srv1 computer.</span></span> <span data-ttu-id="0fb75-153">Ele usa as credenciais do técnico para acessar a sessão.</span><span class="sxs-lookup"><span data-stu-id="0fb75-153">He uses the credentials of the technician to access the session.</span></span>

<span data-ttu-id="0fb75-154">Em seguida, o Gerenciador usa o `Connect-PSSession` cmdlet para se conectar à sessão ITTask no computador Srv1.</span><span class="sxs-lookup"><span data-stu-id="0fb75-154">Next, the manager uses the `Connect-PSSession` cmdlet to connect to the ITTask session on the Srv1 computer.</span></span> <span data-ttu-id="0fb75-155">O comando salva a sessão na variável $s.</span><span class="sxs-lookup"><span data-stu-id="0fb75-155">The command saves the session in the $s variable.</span></span>

<span data-ttu-id="0fb75-156">O Gerenciador usa o `Invoke-Command` cmdlet para executar alguns comandos de diagnóstico na sessão na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="0fb75-156">The manager uses the `Invoke-Command` cmdlet to run some diagnostic commands in the session in the `$s` variable.</span></span> <span data-ttu-id="0fb75-157">Ele identifica que o script falhou porque não localizou um diretório necessário.</span><span class="sxs-lookup"><span data-stu-id="0fb75-157">He recognizes that the script failed because it did not find a required directory.</span></span>
<span data-ttu-id="0fb75-158">O Gerenciador usa a `MkDir` função para criar o diretório e, em seguida, ele reinicia o `Get-PatchStatus.ps1` script e se desconecta da sessão. O gerente relata suas descobertas ao técnico, sugere que ele se reconecte à sessão para concluir as tarefas e solicita que ele adicione um comando ao `Get-PatchStatus.ps1` script que cria o diretório necessário se ele não existir.</span><span class="sxs-lookup"><span data-stu-id="0fb75-158">The manager uses the `MkDir` function to create the directory, and then he restarts the `Get-PatchStatus.ps1` script and disconnects from the session.The manager reports his findings to the technician, suggests that he reconnect to the session to complete the tasks, and asks him to add a command to the `Get-PatchStatus.ps1` script that creates the required directory if it does not exist.</span></span>

### <span data-ttu-id="0fb75-159">Exemplo 4-alterar o valor de tempo limite para uma PSSession</span><span class="sxs-lookup"><span data-stu-id="0fb75-159">Example 4 - Change the timeout value for a PSSession</span></span>

<span data-ttu-id="0fb75-160">Este exemplo mostra como corrigir o valor da propriedade **IdleTimeout** de uma sessão para que ela possa ser desconectada.</span><span class="sxs-lookup"><span data-stu-id="0fb75-160">This example shows how to correct the value of the **IdleTimeout** property of a session so that it can be disconnected.</span></span>

<span data-ttu-id="0fb75-161">A propriedade do tempo limite de inatividade de uma sessão é crítica para sessões desconectadas, pois ela determina quanto tempo uma sessão desconectada é mantida antes de ser excluída.</span><span class="sxs-lookup"><span data-stu-id="0fb75-161">The idle timeout property of a session is critical to disconnected sessions, because it determines how long a disconnected session is maintained before it is deleted.</span></span> <span data-ttu-id="0fb75-162">Você pode definir a opção de tempo limite de inatividade ao criar uma sessão e quando desconectar-se.</span><span class="sxs-lookup"><span data-stu-id="0fb75-162">You can set the idle timeout option when you create a session and when you disconnect it.</span></span> <span data-ttu-id="0fb75-163">Os valores padrão para o tempo limite de ociosidade de uma sessão são definidos na `$PSSessionOption` variável de preferência no computador local e na configuração de sessão no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0fb75-163">The default values for the idle timeout of a session are set in the `$PSSessionOption` preference variable on the local computer and in the session configuration on the remote computer.</span></span> <span data-ttu-id="0fb75-164">Valores definidos para a sessão têm precedência sobre valores definidos na configuração da sessão, porém os valores da sessão não podem exceder as cotas definidas na configuração da sessão, como o valor **MaxIdleTimeoutMs** .</span><span class="sxs-lookup"><span data-stu-id="0fb75-164">Values set for the session take precedence over values set in the session configuration, but session values cannot exceed quotas set in the session configuration, such as the **MaxIdleTimeoutMs** value.</span></span>

```
PS> $Timeout = New-PSSessionOption -IdleTimeout 172800000
PS> $s = New-PSSession -Computer Server01 -Name ITTask -SessionOption $Timeout
PS> Disconnect-PSSession -Session $s
Disconnect-PSSession : The session ITTask cannot be disconnected because the specified
idle timeout value 172800(seconds) is either greater than the server maximum allowed
43200 (seconds) or less that the minimum allowed60(seconds).  Choose an idle time out
value that is within the allowed range and try again.

PS> Invoke-Command -ComputerName Server01 {Get-PSSessionConfiguration Microsoft.PowerShell} |
 Format-List -Property *

Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/microsoft.powershell
MaxConcurrentCommandsPerShell : 1000
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
SecurityDescriptorSddl        : O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GXGW;;;WD)
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 2147483647
Uri                           : http://schemas.microsoft.com/powershell/microsoft.powershell
SDKVersion                    : 2
Name                          : microsoft.powershell
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
ParentResourceUri             : http://schemas.microsoft.com/powershell/microsoft.powershell
Enabled                       : true
MaxShells                     : 25
MaxShellsPerUser              : 25
Permission                    : BUILTIN\Administrators AccessAllowed
PSComputerName                : localhost
RunspaceId                    : aea84310-6dbf-4c21-90ac-13980039925a
PSShowComputerName            : True


PS> $s.Runspace.ConnectionInfo
ConnectionUri                     : http://Server01/wsman
ComputerName                      : Server01
Scheme                            : http
Port                              : 80
AppName                           : /wsman
Credential                        :
ShellUri                          : http://schemas.microsoft.com/powershell/Microsoft.PowerShell
AuthenticationMechanism           : Default
CertificateThumbprint             :
MaximumConnectionRedirectionCount : 5
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
UseCompression                    : True
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
NoEncryption                      : False
UseUTF16                          : False
OutputBufferingMode               : Drop
IncludePortInSPN                  : False
Culture                           : en-US
UICulture                         : en-US
OpenTimeout                       : 180000
CancelTimeout                     : 60000
OperationTimeout                  : 180000
IdleTimeout                       : 172800000

PS> Disconnect-PSSession $s -IdleTimeoutSec 43200
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Disconnected  Microsoft.PowerShell          None

PS> $s.Runspace.ConnectionInfo.IdleTimeout
43200000
```

<span data-ttu-id="0fb75-165">O primeiro comando usa o `New-PSSessionOption` cmdlet para criar um objeto de opção de sessão.</span><span class="sxs-lookup"><span data-stu-id="0fb75-165">The first command uses the `New-PSSessionOption` cmdlet to create a session option object.</span></span> <span data-ttu-id="0fb75-166">Ele usa o **IdleTimeout** para definir um tempo limite de inatividade de 48 horas (172.800.000 milissegundos).</span><span class="sxs-lookup"><span data-stu-id="0fb75-166">It uses the **IdleTimeout** parameter to set an idle timeout of 48 hours (172800000 milliseconds).</span></span> <span data-ttu-id="0fb75-167">O comando salva o objeto de opção de sessão na variável $Timeout.</span><span class="sxs-lookup"><span data-stu-id="0fb75-167">The command saves the session option object in the $Timeout variable.</span></span>

<span data-ttu-id="0fb75-168">O segundo comando usa o `New-PSSession` cmdlet para criar a sessão ITTask no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="0fb75-168">The second command uses the `New-PSSession` cmdlet to create the ITTask session on the Server01 computer.</span></span> <span data-ttu-id="0fb75-169">O comando salva a sessão na variável $s.</span><span class="sxs-lookup"><span data-stu-id="0fb75-169">The command save the session in the $s variable.</span></span> <span data-ttu-id="0fb75-170">O valor do parâmetro **SessionOption** é o tempo limite de inatividade de 48 horas na variável $Timeout.</span><span class="sxs-lookup"><span data-stu-id="0fb75-170">The value of the **SessionOption** parameter is the 48-hour idle timeout in the $Timeout variable.</span></span>

<span data-ttu-id="0fb75-171">O terceiro comando desconecta a sessão ITTask na variável $s.</span><span class="sxs-lookup"><span data-stu-id="0fb75-171">The third command disconnects the ITTask session in the $s variable.</span></span> <span data-ttu-id="0fb75-172">O comando falha porque o valor de tempo limite de inatividade da sessão excede a cota do **MaxIdleTimeoutMs** na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="0fb75-172">The command fails because the idle timeout value of the session exceeds the **MaxIdleTimeoutMs** quota in the session configuration.</span></span> <span data-ttu-id="0fb75-173">Como o tempo limite de inatividade não é usado até que a sessão seja desconectada, essa violação pode não ser detectada enquanto a sessão estiver em uso.</span><span class="sxs-lookup"><span data-stu-id="0fb75-173">Because the idle timeout is not used until the session is disconnected, this violation can go undetected while the session is in use.</span></span>

<span data-ttu-id="0fb75-174">O quarto comando usa o `Invoke-Command` cmdlet para executar um `Get-PSSessionConfiguration` comando para a configuração de sessão do Microsoft. PowerShell no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="0fb75-174">The fourth command uses the `Invoke-Command` cmdlet to run a `Get-PSSessionConfiguration` command for the Microsoft.PowerShell session configuration on the Server01 computer.</span></span> <span data-ttu-id="0fb75-175">O comando usa o `Format-List` cmdlet para exibir todas as propriedades da configuração de sessão em uma lista. A saída mostra que a propriedade **MaxIdleTimeoutMS** , que estabelece o valor máximo permitido de **IdleTimeout** para sessões que usam a configuração de sessão, é de 43,2 milhões milissegundos (12 horas).</span><span class="sxs-lookup"><span data-stu-id="0fb75-175">The command uses the `Format-List` cmdlet to display all properties of the session configuration in a list.The output shows that the **MaxIdleTimeoutMS** property, which establishes the maximum permitted **IdleTimeout** value for sessions that use the session configuration, is 43200000 milliseconds (12 hours).</span></span>

<span data-ttu-id="0fb75-176">O quinto comando obtém valores de opção da sessão na variável $s.</span><span class="sxs-lookup"><span data-stu-id="0fb75-176">The fifth command gets the session option values of the session in the $s variable.</span></span> <span data-ttu-id="0fb75-177">Os valores de muitas opções de sessão são propriedades da propriedade **ConnectionInfo** da propriedade **runspace** da sessão. A saída mostra que o valor da propriedade **IdleTimeout** da sessão é de 172,8 milhões milissegundos (48 horas), o que viola a cota de **MaxIdleTimeoutMs** de 12 horas na configuração da sessão. Para resolver esse conflito, você pode usar o parâmetro **ConfigurationName** para selecionar uma configuração de sessão diferente ou usar o parâmetro **IdleTimeout** para reduzir o tempo limite de ociosidade da sessão.</span><span class="sxs-lookup"><span data-stu-id="0fb75-177">The values of many session options are properties of the **ConnectionInfo** property of the **Runspace** property of the session.The output shows that the value of the **IdleTimeout** property of the session is 172800000 milliseconds (48 hours), which violates the **MaxIdleTimeoutMs** quota of 12 hours in the session configuration.To resolve this conflict, you can use the **ConfigurationName** parameter to select a different session configuration or use the **IdleTimeout** parameter to reduce the idle timeout of the session.</span></span>

<span data-ttu-id="0fb75-178">O sexto comando desconecta a sessão.</span><span class="sxs-lookup"><span data-stu-id="0fb75-178">The sixth command disconnects the session.</span></span> <span data-ttu-id="0fb75-179">Ele usa o parâmetro **IdleTimeoutSec** para definir o tempo limite de ociosidade o máximo de 12 horas.</span><span class="sxs-lookup"><span data-stu-id="0fb75-179">It uses the **IdleTimeoutSec** parameter to set the idle timeout to the 12-hour maximum.</span></span>

<span data-ttu-id="0fb75-180">O sétimo comando obtém o valor da propriedade **IdleTimeout** da sessão desconectada, medido em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="0fb75-180">The seventh command gets the value of the **IdleTimeout** property of the disconnected session, which is measured in milliseconds.</span></span> <span data-ttu-id="0fb75-181">A saída confirma que o comando teve êxito.</span><span class="sxs-lookup"><span data-stu-id="0fb75-181">The output confirms that the command was successful.</span></span>

## <span data-ttu-id="0fb75-182">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0fb75-182">PARAMETERS</span></span>

### <span data-ttu-id="0fb75-183">-Id</span><span class="sxs-lookup"><span data-stu-id="0fb75-183">-Id</span></span>

<span data-ttu-id="0fb75-184">Desconecta-se de sessões com a ID de sessão especificada.</span><span class="sxs-lookup"><span data-stu-id="0fb75-184">Disconnects from sessions with the specified session ID.</span></span> <span data-ttu-id="0fb75-185">Digite uma ou mais IDs (separadas por vírgulas) ou use o operador de intervalo (..) para especificar um intervalo de IDs.</span><span class="sxs-lookup"><span data-stu-id="0fb75-185">Type one or more IDs (separated by commas), or use the range operator (..) to specify a range of IDs.</span></span>

<span data-ttu-id="0fb75-186">Para obter a ID de uma sessão, use o `Get-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0fb75-186">To get the ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="0fb75-187">O ID de instância é armazenado na propriedade **ID** da PSSession.</span><span class="sxs-lookup"><span data-stu-id="0fb75-187">The instance ID is stored in the **ID** property of the session.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0fb75-188">-IdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="0fb75-188">-IdleTimeoutSec</span></span>

<span data-ttu-id="0fb75-189">Altera o valor de tempo limite de inatividade do PSSession desconectado.</span><span class="sxs-lookup"><span data-stu-id="0fb75-189">Changes the idle timeout value of the disconnected PSSession.</span></span> <span data-ttu-id="0fb75-190">Insira um valor em segundos.</span><span class="sxs-lookup"><span data-stu-id="0fb75-190">Enter a value in seconds.</span></span> <span data-ttu-id="0fb75-191">O valor mínimo é 60 (1 minuto).</span><span class="sxs-lookup"><span data-stu-id="0fb75-191">The minimum value is 60 (1 minute).</span></span>

<span data-ttu-id="0fb75-192">O tempo limite de inatividade determina quanto tempo a PSSession desconectada é mantida no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0fb75-192">The idle timeout determines how long the disconnected PSSession is maintained on the remote computer.</span></span> <span data-ttu-id="0fb75-193">Quando o tempo limite expirar, a PSSession é excluída.</span><span class="sxs-lookup"><span data-stu-id="0fb75-193">When the timeout expires, the PSSession is deleted.</span></span>

<span data-ttu-id="0fb75-194">PSSessions desconectadas são consideradas inativas desde o momento em que são desconectadas, ainda que comandos estejam em execução na sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="0fb75-194">Disconnected PSSessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

<span data-ttu-id="0fb75-195">O valor padrão para o tempo limite de inatividade de uma sessão é definido pelo valor da propriedade **IdleTimeoutMs** da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="0fb75-195">The default value for the idle timeout of a session is set by the value of the **IdleTimeoutMs** property of the session configuration.</span></span> <span data-ttu-id="0fb75-196">O valor padrão é 7200000 milissegundos (2 horas).</span><span class="sxs-lookup"><span data-stu-id="0fb75-196">The default value is 7200000 milliseconds (2 hours).</span></span>

<span data-ttu-id="0fb75-197">O valor deste parâmetro tem precedência sobre o valor da propriedade **IdleTimeout** da variável de preferências $PSSessionOption e o valor de tempo limite de inatividade padrão na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="0fb75-197">The value of this parameter takes precedence over the value of the **IdleTimeout** property of the $PSSessionOption preference variable and the default idle timeout value in the session configuration.</span></span> <span data-ttu-id="0fb75-198">No entanto, esse valor não pode exceder o valor da propriedade **MaxIdleTimeoutMs** da configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="0fb75-198">However, this value cannot exceed the value of the **MaxIdleTimeoutMs** property of the session configuration.</span></span> <span data-ttu-id="0fb75-199">O valor padrão de **MaxIdleTimeoutMs** é de 12 horas (43.200.000 milissegundos).</span><span class="sxs-lookup"><span data-stu-id="0fb75-199">The default value of **MaxIdleTimeoutMs** is 12 hours (43200000 milliseconds).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fb75-200">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="0fb75-200">-InstanceId</span></span>

<span data-ttu-id="0fb75-201">Desconecta-se de sessões com os IDs de instância especificados.</span><span class="sxs-lookup"><span data-stu-id="0fb75-201">Disconnects from sessions with the specified instance IDs.</span></span>

<span data-ttu-id="0fb75-202">A ID de instância é um GUID que identifica exclusivamente uma sessão em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="0fb75-202">The instance ID is a GUID that uniquely identifies a session on a local or remote computer.</span></span> <span data-ttu-id="0fb75-203">O ID de instância é exclusivo, mesmo em várias sessões em vários computadores.</span><span class="sxs-lookup"><span data-stu-id="0fb75-203">The instance ID is unique, even across multiple sessions on multiple computers.</span></span>

<span data-ttu-id="0fb75-204">Para obter a ID de instância de uma sessão, use o `Get-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0fb75-204">To get the instance ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="0fb75-205">A ID da instância é armazenada na propriedade **InstanceId** da sessão.</span><span class="sxs-lookup"><span data-stu-id="0fb75-205">The instance ID is stored in the **InstanceID** property of the session.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0fb75-206">-Name</span><span class="sxs-lookup"><span data-stu-id="0fb75-206">-Name</span></span>

<span data-ttu-id="0fb75-207">Desconecta de sessões com os nomes amigáveis especificados.</span><span class="sxs-lookup"><span data-stu-id="0fb75-207">Disconnects from sessions with the specified friendly names.</span></span> <span data-ttu-id="0fb75-208">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0fb75-208">Wildcards are permitted.</span></span>

<span data-ttu-id="0fb75-209">Para obter o nome amigável de uma sessão, use o `Get-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0fb75-209">To get the friendly name of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="0fb75-210">O nome amigável de uma sessão é armazenado na propriedade **Name** da sessão.</span><span class="sxs-lookup"><span data-stu-id="0fb75-210">The friendly name is stored in the **Name** property of the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="0fb75-211">-Sessão</span><span class="sxs-lookup"><span data-stu-id="0fb75-211">-Session</span></span>

<span data-ttu-id="0fb75-212">Desconecta-se de PSSessions especificadas.</span><span class="sxs-lookup"><span data-stu-id="0fb75-212">Disconnects from the specified PSSessions.</span></span> <span data-ttu-id="0fb75-213">Insira objetos PSSession, como os que o `New-PSSession` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="0fb75-213">Enter PSSession objects, such as those that the `New-PSSession` cmdlet returns.</span></span> <span data-ttu-id="0fb75-214">Também é possível canalizar um objeto PSSession para `Disconnect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="0fb75-214">You can also pipe a PSSession object to `Disconnect-PSSession`.</span></span>

<span data-ttu-id="0fb75-215">O `Get-PSSession` cmdlet pode obter todas as PSSessions que terminam em um computador remoto, incluindo PSSessions que são desconectados e PSSessions conectados a outras sessões em outros computadores.</span><span class="sxs-lookup"><span data-stu-id="0fb75-215">The `Get-PSSession` cmdlet can get all PSSessions that terminate at a remote computer, including PSSessions that are disconnected and PSSessions that are connected to other sessions on other computers.</span></span> <span data-ttu-id="0fb75-216">`Disconnect-PSSession` desconecta somente PSSession que estão conectados à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0fb75-216">`Disconnect-PSSession` disconnects only PSSession that are connected to the current session.</span></span> <span data-ttu-id="0fb75-217">Se você canalizar outras PSSessions para `Disconnect-PSSession` , o `Disconnect-PSSession` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="0fb75-217">If you pipe other PSSessions to `Disconnect-PSSession`, the `Disconnect-PSSession` command fails.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0fb75-218">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="0fb75-218">-ThrottleLimit</span></span>

<span data-ttu-id="0fb75-219">Define o limite de limitação para o `Disconnect-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="0fb75-219">Sets the throttle limit for the `Disconnect-PSSession` command.</span></span>

<span data-ttu-id="0fb75-220">Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar este comando.</span><span class="sxs-lookup"><span data-stu-id="0fb75-220">The throttle limit is the maximum number of concurrent connections that can be established to run this command.</span></span> <span data-ttu-id="0fb75-221">Se você omite esse parâmetro ou digita um valor 0, o valor padrão, 32, é usado.</span><span class="sxs-lookup"><span data-stu-id="0fb75-221">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="0fb75-222">O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="0fb75-222">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fb75-223">-OutputBufferingMode</span><span class="sxs-lookup"><span data-stu-id="0fb75-223">-OutputBufferingMode</span></span>

<span data-ttu-id="0fb75-224">Determina como a saída do comando é gerenciada na sessão desconectada quando o buffer de saída está cheio.</span><span class="sxs-lookup"><span data-stu-id="0fb75-224">Determines how command output is managed in the disconnected session when the output buffer is full.</span></span> <span data-ttu-id="0fb75-225">O valor padrão é **Block** .</span><span class="sxs-lookup"><span data-stu-id="0fb75-225">The default value is **Block** .</span></span>

<span data-ttu-id="0fb75-226">Se o comando na sessão desconectada estiver retornando uma saída e o buffer de saída ficar cheio, o valor desse parâmetro efetivamente determina se o comando continuará a ser executado enquanto a sessão está desconectada.</span><span class="sxs-lookup"><span data-stu-id="0fb75-226">If the command in the disconnected session is returning output and the output buffer fills, the value of this parameter effectively determines whether the command continues to run while the session is disconnected.</span></span> <span data-ttu-id="0fb75-227">Um valor de **Block** suspende o comando até que a sessão seja reconectada.</span><span class="sxs-lookup"><span data-stu-id="0fb75-227">A value of **Block** suspends the command until the session is reconnected.</span></span> <span data-ttu-id="0fb75-228">Um valor de **Drop** permite que o comando ser concluído, embora os dados possam ser perdidos.</span><span class="sxs-lookup"><span data-stu-id="0fb75-228">A value of **Drop** allows the command to complete, although data might be lost.</span></span> <span data-ttu-id="0fb75-229">Ao usar o valor **Drop** , redirecione a saída do comando para um arquivo no disco.</span><span class="sxs-lookup"><span data-stu-id="0fb75-229">When using the **Drop** value, redirect the command output to a file on disk.</span></span>

<span data-ttu-id="0fb75-230">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="0fb75-230">Valid values are:</span></span>

- <span data-ttu-id="0fb75-231">**Bloquear** : quando o buffer de saída estiver cheio, a execução será suspensa até que o buffer fique claro.</span><span class="sxs-lookup"><span data-stu-id="0fb75-231">**Block** : When the output buffer is full, execution is suspended until the buffer is clear.</span></span>
- <span data-ttu-id="0fb75-232">**Remover** : quando o buffer de saída estiver cheio, a execução continuará.</span><span class="sxs-lookup"><span data-stu-id="0fb75-232">**Drop** : When the output buffer is full, execution continues.</span></span> <span data-ttu-id="0fb75-233">Conforme uma nova saída é salva, a saída mais antiga é descartada.</span><span class="sxs-lookup"><span data-stu-id="0fb75-233">As new output is saved, the oldest output is discarded.</span></span>
- <span data-ttu-id="0fb75-234">**Nenhum** : nenhum modo de buffer de saída foi especificado.</span><span class="sxs-lookup"><span data-stu-id="0fb75-234">**None** : No output buffering mode is specified.</span></span> <span data-ttu-id="0fb75-235">O valor da propriedade **OutputBufferingMode** da configuração de sessão é usada para a sessão desconectada.</span><span class="sxs-lookup"><span data-stu-id="0fb75-235">The value of the **OutputBufferingMode** property of the session configuration is used for the disconnected session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.OutputBufferingMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Block
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fb75-236">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0fb75-236">-Confirm</span></span>

<span data-ttu-id="0fb75-237">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0fb75-237">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0fb75-238">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0fb75-238">-WhatIf</span></span>

<span data-ttu-id="0fb75-239">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="0fb75-239">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0fb75-240">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="0fb75-240">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0fb75-241">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0fb75-241">CommonParameters</span></span>

<span data-ttu-id="0fb75-242">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0fb75-242">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0fb75-243">Para obter mais informações, confira [about_CommonParameters](./About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="0fb75-243">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0fb75-244">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0fb75-244">INPUTS</span></span>

### <span data-ttu-id="0fb75-245">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="0fb75-245">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="0fb75-246">Você pode canalizar uma sessão para `Disconnect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="0fb75-246">You can pipe a session to `Disconnect-PSSession`.</span></span>

## <span data-ttu-id="0fb75-247">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0fb75-247">OUTPUTS</span></span>

### <span data-ttu-id="0fb75-248">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="0fb75-248">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="0fb75-249">`Disconnect-PSSession` Retorna um objeto que representa a sessão que ele desconectou.</span><span class="sxs-lookup"><span data-stu-id="0fb75-249">`Disconnect-PSSession` returns an object that represents the session that it disconnected.</span></span>

## <span data-ttu-id="0fb75-250">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0fb75-250">NOTES</span></span>

- <span data-ttu-id="0fb75-251">O `Disconnect-PSSession` cmdlet funciona somente quando os computadores locais e remotos estão executando o PowerShell 3,0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="0fb75-251">The `Disconnect-PSSession` cmdlet works only when the local and remote computers are running PowerShell 3.0 or later.</span></span>
- <span data-ttu-id="0fb75-252">Se você usar o `Disconnect-PSSession` cmdlet em uma sessão desconectada, o comando não terá nenhum efeito na sessão e não gerará erros.</span><span class="sxs-lookup"><span data-stu-id="0fb75-252">If you use the `Disconnect-PSSession` cmdlet on a disconnected session, the command has no effect on the session and it does not generate errors.</span></span>
- <span data-ttu-id="0fb75-253">Sessões de loopback desconectadas com tokens de segurança interativos (aqueles criados com o parâmetro **EnableNetworkAccess** ) podem ser reconectados somente por meio do computador no qual a sessão foi criada.</span><span class="sxs-lookup"><span data-stu-id="0fb75-253">Disconnected loopback sessions with interactive security tokens (those created with the **EnableNetworkAccess** parameter) can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="0fb75-254">Essa restrição protege o computador contra acessos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="0fb75-254">This restriction protects the computer from malicious access.</span></span>
- <span data-ttu-id="0fb75-255">Quando você desconecta uma PSSession, o estado da sessão é **Disconnected** e a disponibilidade é **None** .</span><span class="sxs-lookup"><span data-stu-id="0fb75-255">When you disconnect a PSSession, the session state is **Disconnected** and the availability is **None** .</span></span>

  <span data-ttu-id="0fb75-256">O valor da propriedade **State** é relativo a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0fb75-256">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="0fb75-257">Portanto, um valor de **Disconnected** significa que a PSSession não está conectada à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0fb75-257">Therefore, a value of **Disconnected** means that the PSSession is not connected to the current session.</span></span> <span data-ttu-id="0fb75-258">No entanto, isso não significa que a PSSession será desconectada de todas as sessões.</span><span class="sxs-lookup"><span data-stu-id="0fb75-258">However, it does not mean that the PSSession is disconnected from all sessions.</span></span> <span data-ttu-id="0fb75-259">Ela pode ser conectada a uma sessão diferente.</span><span class="sxs-lookup"><span data-stu-id="0fb75-259">It might be connected to a different session.</span></span> <span data-ttu-id="0fb75-260">Para determinar se é possível conectar-se ou reconectar-se à sessão, utilize a propriedade **Availability** .</span><span class="sxs-lookup"><span data-stu-id="0fb75-260">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

  <span data-ttu-id="0fb75-261">Um valor **Availability** de **None** indica que é possível conectar-se à sessão.</span><span class="sxs-lookup"><span data-stu-id="0fb75-261">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="0fb75-262">Um valor de **Busy** indica que não é possível se conectar à PSSession porque está conectada a outra sessão.</span><span class="sxs-lookup"><span data-stu-id="0fb75-262">A value of **Busy** indicates that you cannot connect to the PSSession because it is connected to another session.</span></span>

  <span data-ttu-id="0fb75-263">Para obter mais informações sobre os valores da propriedade **State** de sessões, consulte [Enumeração RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate).</span><span class="sxs-lookup"><span data-stu-id="0fb75-263">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span>

  <span data-ttu-id="0fb75-264">Para obter mais informações sobre os valores da propriedade de sessões de **disponibilidade** , consulte [Enumeração RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="0fb75-264">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="0fb75-265">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0fb75-265">RELATED LINKS</span></span>

[<span data-ttu-id="0fb75-266">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="0fb75-266">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="0fb75-267">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="0fb75-267">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="0fb75-268">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="0fb75-268">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="0fb75-269">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="0fb75-269">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="0fb75-270">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="0fb75-270">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="0fb75-271">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="0fb75-271">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="0fb75-272">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="0fb75-272">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="0fb75-273">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="0fb75-273">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="0fb75-274">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="0fb75-274">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="0fb75-275">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="0fb75-275">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="0fb75-276">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="0fb75-276">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="0fb75-277">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="0fb75-277">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="0fb75-278">about_Remote</span><span class="sxs-lookup"><span data-stu-id="0fb75-278">about_Remote</span></span>](About/about_Remote.md)

[<span data-ttu-id="0fb75-279">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="0fb75-279">about_Remote_Disconnected_Sessions</span></span>](About/about_Remote_Disconnected_Sessions.md)
