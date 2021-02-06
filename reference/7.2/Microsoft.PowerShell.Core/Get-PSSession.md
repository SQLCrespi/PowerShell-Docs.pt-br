---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSession
ms.openlocfilehash: e06eaaa3b6042a2105462adfc2ba8f0a4867f045
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595967"
---
# <span data-ttu-id="389ad-102">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="389ad-102">Get-PSSession</span></span>

## <span data-ttu-id="389ad-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="389ad-103">SYNOPSIS</span></span>
<span data-ttu-id="389ad-104">Obtém as sessões do PowerShell em computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="389ad-104">Gets the PowerShell sessions on local and remote computers.</span></span>

## <span data-ttu-id="389ad-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="389ad-105">SYNTAX</span></span>

### <span data-ttu-id="389ad-106">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="389ad-106">Name (Default)</span></span>

```
Get-PSSession [-Name <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="389ad-107">ComputerName</span><span class="sxs-lookup"><span data-stu-id="389ad-107">ComputerName</span></span>

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="389ad-108">ComputerInstanceId</span><span class="sxs-lookup"><span data-stu-id="389ad-108">ComputerInstanceId</span></span>

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="389ad-109">ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="389ad-109">ConnectionUri</span></span>

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="389ad-110">ConnectionUriInstanceId</span><span class="sxs-lookup"><span data-stu-id="389ad-110">ConnectionUriInstanceId</span></span>

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] -InstanceId <Guid[]>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="389ad-111">VMNameInstanceId</span><span class="sxs-lookup"><span data-stu-id="389ad-111">VMNameInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="389ad-112">ContainerId</span><span class="sxs-lookup"><span data-stu-id="389ad-112">ContainerId</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="389ad-113">ContainerIdInstanceId</span><span class="sxs-lookup"><span data-stu-id="389ad-113">ContainerIdInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="389ad-114">VMId</span><span class="sxs-lookup"><span data-stu-id="389ad-114">VMId</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### <span data-ttu-id="389ad-115">VMIdInstanceId</span><span class="sxs-lookup"><span data-stu-id="389ad-115">VMIdInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### <span data-ttu-id="389ad-116">VMName</span><span class="sxs-lookup"><span data-stu-id="389ad-116">VMName</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMName <String[]>
 [<CommonParameters>]
```

### <span data-ttu-id="389ad-117">InstanceId</span><span class="sxs-lookup"><span data-stu-id="389ad-117">InstanceId</span></span>

```
Get-PSSession [-InstanceId <Guid[]>] [<CommonParameters>]
```

### <span data-ttu-id="389ad-118">ID</span><span class="sxs-lookup"><span data-stu-id="389ad-118">Id</span></span>

```
Get-PSSession [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="389ad-119">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="389ad-119">DESCRIPTION</span></span>

<span data-ttu-id="389ad-120">O `Get-PSSession` cmdlet obtém as sessões do PowerShell gerenciadas pelo usuário (**PSSessions**) em computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="389ad-120">The `Get-PSSession` cmdlet gets the user-managed PowerShell sessions (**PSSessions**) on local and remote computers.</span></span>

<span data-ttu-id="389ad-121">A partir do Windows PowerShell 3,0, as sessões são armazenadas nos computadores na extremidade remota de cada conexão.</span><span class="sxs-lookup"><span data-stu-id="389ad-121">Starting in Windows PowerShell 3.0, sessions are stored on the computers at the remote end of each connection.</span></span> <span data-ttu-id="389ad-122">Você pode usar os parâmetros **ComputerName** ou **conexãouri** do `Get-PSSession` para obter as sessões que se conectam ao computador local ou a computadores remotos, mesmo que eles não tenham sido criados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="389ad-122">You can use the **ComputerName** or **ConnectionUri** parameters of `Get-PSSession` to get the sessions that connect to the local computer or remote computers, even if they were not created in the current session.</span></span>

<span data-ttu-id="389ad-123">Sem parâmetros, `Get-PSSession` obtém todas as sessões que foram criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="389ad-123">Without parameters, `Get-PSSession` gets all sessions that were created in the current session.</span></span>

<span data-ttu-id="389ad-124">Use os parâmetros de filtragem, incluindo **Name**, **ID**, **InstanceId**, **State**, **ApplicationName** e **ConfigurationName** para selecionar entre as sessões que `Get-PSSession` retorna.</span><span class="sxs-lookup"><span data-stu-id="389ad-124">Use the filtering parameters, including **Name**, **ID**, **InstanceID**, **State**, **ApplicationName**, and **ConfigurationName** to select from among the sessions that `Get-PSSession` returns.</span></span>

<span data-ttu-id="389ad-125">Use os parâmetros restantes para configurar a conexão temporária na qual o `Get-PSSession` comando é executado quando você usa os parâmetros **ComputerName** ou **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="389ad-125">Use the remaining parameters to configure the temporary connection in which the `Get-PSSession` command runs when you use the **ComputerName** or **ConnectionUri** parameters.</span></span>

<span data-ttu-id="389ad-126">Observação: no Windows PowerShell 2,0, sem parâmetros, `Get-PSSession` obtém todas as sessões que foram criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="389ad-126">NOTE: In Windows PowerShell 2.0, without parameters, `Get-PSSession` gets all sessions that were created in the current session.</span></span> <span data-ttu-id="389ad-127">O parâmetro **ComputerName** Obtém as sessões que foram criadas na sessão atual e se conecta ao computador especificado.</span><span class="sxs-lookup"><span data-stu-id="389ad-127">The **ComputerName** parameter gets sessions that were created in the current session and connect to the specified computer.</span></span>

<span data-ttu-id="389ad-128">Para obter mais informações sobre sessões do PowerShell, consulte [about_PSSessions](about/about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="389ad-128">For more information about PowerShell sessions, see [about_PSSessions](about/about_PSSessions.md).</span></span>

## <span data-ttu-id="389ad-129">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="389ad-129">EXAMPLES</span></span>

### <span data-ttu-id="389ad-130">Exemplo 1: obter sessões criadas na sessão atual</span><span class="sxs-lookup"><span data-stu-id="389ad-130">Example 1: Get sessions created in the current session</span></span>

```powershell
Get-PSSession
```

<span data-ttu-id="389ad-131">Esse comando obtém todas as **PSSessions** que foram criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="389ad-131">This command gets all of the **PSSessions** that were created in the current session.</span></span> <span data-ttu-id="389ad-132">Ele não obtém **PSSessions** que foram criadas em outras sessões ou em outros computadores, mesmo que se conectem a este computador.</span><span class="sxs-lookup"><span data-stu-id="389ad-132">It does not get **PSSessions** that were created in other sessions or on other computers, even if they connect to this computer.</span></span>

### <span data-ttu-id="389ad-133">Exemplo 2: obter sessões conectadas ao computador local</span><span class="sxs-lookup"><span data-stu-id="389ad-133">Example 2: Get sessions connected to the local computer</span></span>

```powershell
Get-PSSession -ComputerName "localhost"
```

<span data-ttu-id="389ad-134">Esse comando obtém as **PSSessions** que estão conectadas ao computador local.</span><span class="sxs-lookup"><span data-stu-id="389ad-134">This command gets the **PSSessions** that are connected to the local computer.</span></span> <span data-ttu-id="389ad-135">Para indicar o computador local, digite o nome do computador, localhost ou um ponto (.)</span><span class="sxs-lookup"><span data-stu-id="389ad-135">To indicate the local computer, type the computer name, localhost, or a dot (.)</span></span>

<span data-ttu-id="389ad-136">O comando retorna todas as sessões no computador local, mesmo que elas tenham sido criadas em sessões ou em computadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="389ad-136">The command returns all of the sessions on the local computer, even if they were created in different sessions or on different computers.</span></span>

### <span data-ttu-id="389ad-137">Exemplo 3: obter sessões conectadas a um computador</span><span class="sxs-lookup"><span data-stu-id="389ad-137">Example 3: Get sessions connected to a computer</span></span>

```powershell
Get-PSSession -ComputerName "Server02"
```

```Output
 Id Name            ComputerName    State         ConfigurationName     Availability
 -- ----            ------------    -----         -----------------     ------------
  2 Session3        Server02       Disconnected  ITTasks                       Busy
  1 ScheduledJobs   Server02       Opened        Microsoft.PowerShell     Available
  3 Test            Server02       Disconnected  Microsoft.PowerShell          Busy
```

<span data-ttu-id="389ad-138">Esse comando obtém as **PSSessions** que estão conectadas ao computador Server02.</span><span class="sxs-lookup"><span data-stu-id="389ad-138">This command gets the **PSSessions** that are connected to the Server02 computer.</span></span>

<span data-ttu-id="389ad-139">O comando retorna todas as sessões em Server02, mesmo que elas tenham sido criadas em sessões ou em computadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="389ad-139">The command returns all of the sessions on Server02, even if they were created in different sessions or on different computers.</span></span>

<span data-ttu-id="389ad-140">A saída mostra que duas das sessões têm o estado de Desconectado e a disponibilidade de Ocupado.</span><span class="sxs-lookup"><span data-stu-id="389ad-140">The output shows that two of the sessions have a Disconnected state and a Busy availability.</span></span> <span data-ttu-id="389ad-141">Elas foram criadas em sessões diferentes e estão em uso atualmente.</span><span class="sxs-lookup"><span data-stu-id="389ad-141">They were created in different sessions and are currently in use.</span></span> <span data-ttu-id="389ad-142">A sessão ScheduledJobs, que está aberta e disponível, foi criada na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="389ad-142">The ScheduledJobs session, which is Opened and Available, was created in the current session.</span></span>

### <span data-ttu-id="389ad-143">Exemplo 4: salvar os resultados deste comando</span><span class="sxs-lookup"><span data-stu-id="389ad-143">Example 4: Save results of this command</span></span>

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
$s1, $s2, $s3 = Get-PSSession
```

<span data-ttu-id="389ad-144">Este exemplo mostra como salvar os resultados de um `Get-PSSession` comando em várias variáveis.</span><span class="sxs-lookup"><span data-stu-id="389ad-144">This example shows how to save the results of a `Get-PSSession` command in multiple variables.</span></span>

<span data-ttu-id="389ad-145">O primeiro comando usa o `New-PSSession` cmdlet para criar **PSSessions** em três computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="389ad-145">The first command uses the `New-PSSession` cmdlet to create **PSSessions** on three remote computers.</span></span>

<span data-ttu-id="389ad-146">O segundo comando usa um `Get-PSSession` cmdlet para obter as três **PSSessions**.</span><span class="sxs-lookup"><span data-stu-id="389ad-146">The second command uses a `Get-PSSession` cmdlet to get the three **PSSessions**.</span></span> <span data-ttu-id="389ad-147">Em seguida, ele salva cada uma das **PSSessions** em uma variável separada.</span><span class="sxs-lookup"><span data-stu-id="389ad-147">It then saves each of the **PSSessions** in a separate variable.</span></span>

<span data-ttu-id="389ad-148">Quando o PowerShell atribui uma matriz de objetos a uma matriz de variáveis, ele atribui o primeiro objeto à primeira variável, o segundo objeto à segunda variável e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="389ad-148">When PowerShell assigns an array of objects to an array of variables, it assigns the first object to the first variable, the second object to the second variable, and so on.</span></span> <span data-ttu-id="389ad-149">Se houver mais objetos que variáveis, ele atribui todos os objetos restantes à última variável da matriz.</span><span class="sxs-lookup"><span data-stu-id="389ad-149">If there are more objects than variables, it assigns all remaining objects to the last variable in the array.</span></span> <span data-ttu-id="389ad-150">Se houver mais variáveis que objetos, as variáveis extra não são usadas.</span><span class="sxs-lookup"><span data-stu-id="389ad-150">If there are more variables than objects, the extra variables are not used.</span></span>

### <span data-ttu-id="389ad-151">Exemplo 5: excluir uma sessão usando uma ID de instância</span><span class="sxs-lookup"><span data-stu-id="389ad-151">Example 5: Delete a session by using an instance ID</span></span>

```powershell
Get-PSSession | Format-Table -Property ComputerName, InstanceID
$s = Get-PSSession -InstanceID a786be29-a6bb-40da-80fb-782c67f7db0f
Remove-PSSession -Session $s
```

<span data-ttu-id="389ad-152">Este exemplo mostra como obter uma **PSSession** usando sua ID de instância e, em seguida, excluir a **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="389ad-152">This example shows how to get a **PSSession** by using its instance ID, and then to delete the **PSSession**.</span></span>

<span data-ttu-id="389ad-153">O primeiro comando obtém todas as **PSSessions** que foram criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="389ad-153">The first command gets all of the **PSSessions** that were created in the current session.</span></span> <span data-ttu-id="389ad-154">Ele envia as **PSSessions** para o cmdlet Format-Table, que exibe as propriedades **ComputerName** e **InstanceId** de cada **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="389ad-154">It sends the **PSSessions** to the Format-Table cmdlet, which displays the **ComputerName** and **InstanceID** properties of each **PSSession**.</span></span>

<span data-ttu-id="389ad-155">O segundo comando usa o `Get-PSSession` cmdlet para obter uma **PSSession** específica e salvá-la na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="389ad-155">The second command uses the `Get-PSSession` cmdlet to get a particular **PSSession** and to save it in the `$s` variable.</span></span> <span data-ttu-id="389ad-156">O comando usa o parâmetro **InstanceId** para identificar a **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="389ad-156">The command uses the **InstanceID** parameter to identify the **PSSession**.</span></span>

<span data-ttu-id="389ad-157">O terceiro comando usa o cmdlet Remove-PSSession para excluir a **PSSession** na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="389ad-157">The third command uses the Remove-PSSession cmdlet to delete the **PSSession** in the `$s` variable.</span></span>

### <span data-ttu-id="389ad-158">Exemplo 6: obter uma sessão que tem um nome específico</span><span class="sxs-lookup"><span data-stu-id="389ad-158">Example 6: Get a session that has a particular name</span></span>

<span data-ttu-id="389ad-159">Os comandos neste exemplo encontram uma sessão que tem um formato de nome específico e usa uma configuração de sessão específica e, em seguida, se conecta à sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-159">The commands in this example find a session that has a particular name format and uses a particular session configuration and then connect to the session.</span></span> <span data-ttu-id="389ad-160">Você pode usar um comando como este para encontrar uma sessão na qual um colega iniciou uma tarefa e se conectar para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="389ad-160">You can use a command like this one to find a session in which a colleague started a task and connect to finish the task.</span></span>

```powershell
Get-PSSession -ComputerName Server02, Server12 -Name BackupJob* -ConfigurationName ITTasks -SessionOption @{OperationTimeout=240000}
```

```Output
 Id Name            ComputerName    State         ConfigurationName     Availability
 -- ----            ------------    -----         -----------------     ------------
  3 BackupJob04     Server02        Disconnected        ITTasks                  None
```

```powershell
$s = Get-PSSession -ComputerName Server02 -Name BackupJob04 -ConfigurationName ITTasks | Connect-PSSession
$s
```

```Output
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 5 BackupJob04     Server02        Opened        ITTasks                  Available
```

<span data-ttu-id="389ad-161">O primeiro comando obtém sessões nos computadores remotos Server02 e Server12 que têm nomes que começam com BackupJob e usam a configuração de sessão ITTasks. O comando usa o parâmetro **Name** para especificar o padrão de nome e o parâmetro **ConfigurationName** para especificar a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-161">The first command gets sessions on the Server02 and Server12 remote computers that have names that begin with BackupJob and use the ITTasks session configuration.The command uses the **Name** parameter to specify the name pattern and the **ConfigurationName** parameter to specify the session configuration.</span></span> <span data-ttu-id="389ad-162">O valor do parâmetro **SessionOption** é uma tabela de hash que define o valor de **OperationTimeout** como 240.000 milissegundos (4 minutos).</span><span class="sxs-lookup"><span data-stu-id="389ad-162">The value of the **SessionOption** parameter is a hash table that sets the value of the **OperationTimeout** to 240000 milliseconds (4 minutes).</span></span> <span data-ttu-id="389ad-163">Essa configuração fornece ao comando mais tempo para ser concluído. Os parâmetros **ConfigurationName** e **SessionOption** são usados para configurar as sessões temporárias nas quais o `Get-PSSession` cmdlet é executado em cada computador. A saída mostra que o comando retorna a sessão BackupJob04.</span><span class="sxs-lookup"><span data-stu-id="389ad-163">This setting gives the command more time to complete.The **ConfigurationName** and **SessionOption** parameters are used to configure the temporary sessions in which the `Get-PSSession` cmdlet runs on each computer.The output shows that the command returns the BackupJob04 session.</span></span> <span data-ttu-id="389ad-164">A sessão está desconectada e a **disponibilidade** é nenhuma, o que indica que ela não está em uso.</span><span class="sxs-lookup"><span data-stu-id="389ad-164">The session is disconnected and the **Availability** is None, which indicates that it is not in use.</span></span>

<span data-ttu-id="389ad-165">O segundo comando usa o `Get-PSSession` cmdlet para obter a sessão BackupJob04 e o cmdlet Connect-PSSession para se conectar à sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-165">The second command uses the `Get-PSSession` cmdlet to get to the BackupJob04 session and the Connect-PSSession cmdlet to connect to the session.</span></span> <span data-ttu-id="389ad-166">O comando salva a sessão na variável $s.</span><span class="sxs-lookup"><span data-stu-id="389ad-166">The command saves the session in the $s variable.</span></span>

<span data-ttu-id="389ad-167">O terceiro comando obtém a sessão na variável $s.</span><span class="sxs-lookup"><span data-stu-id="389ad-167">The third command gets the session in the $s variable.</span></span> <span data-ttu-id="389ad-168">A saída mostra que o `Connect-PSSession` comando foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="389ad-168">The output shows that the `Connect-PSSession` command was successful.</span></span> <span data-ttu-id="389ad-169">A sessão está no estado **Opened** e está disponível para uso.</span><span class="sxs-lookup"><span data-stu-id="389ad-169">The session is in the **Opened** state and is available for use.</span></span>

### <span data-ttu-id="389ad-170">Exemplo 7: obter uma sessão usando sua ID</span><span class="sxs-lookup"><span data-stu-id="389ad-170">Example 7: Get a session by using its ID</span></span>

```powershell
Get-PSSession -Id 2
```

<span data-ttu-id="389ad-171">Este comando obtém a **PSSession** com ID 2.</span><span class="sxs-lookup"><span data-stu-id="389ad-171">This command gets the **PSSession** with ID 2.</span></span> <span data-ttu-id="389ad-172">Como o valor da propriedade **ID** é exclusivo somente na sessão atual, o parâmetro **ID** é válido somente para comandos locais.</span><span class="sxs-lookup"><span data-stu-id="389ad-172">Because the value of the **ID** property is unique only in the current session, the **Id** parameter is valid only for local commands.</span></span>

## <span data-ttu-id="389ad-173">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="389ad-173">PARAMETERS</span></span>

### <span data-ttu-id="389ad-174">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="389ad-174">-AllowRedirection</span></span>

<span data-ttu-id="389ad-175">Indica que esse cmdlet permite o redirecionamento dessa conexão para um Uniform Resource Identifier alternativo (URI).</span><span class="sxs-lookup"><span data-stu-id="389ad-175">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="389ad-176">Por padrão, o PowerShell não redireciona conexões.</span><span class="sxs-lookup"><span data-stu-id="389ad-176">By default, PowerShell does not redirect connections.</span></span>

<span data-ttu-id="389ad-177">Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="389ad-177">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ConnectionUri** parameter.</span></span>

<span data-ttu-id="389ad-178">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="389ad-178">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-179">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="389ad-179">-ApplicationName</span></span>

<span data-ttu-id="389ad-180">Especifica o nome de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="389ad-180">Specifies the name of an application.</span></span> <span data-ttu-id="389ad-181">Esse cmdlet se conecta somente a sessões que usam o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="389ad-181">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="389ad-182">Insira o segmento de nome de aplicativo do URI de conexão.</span><span class="sxs-lookup"><span data-stu-id="389ad-182">Enter the application name segment of the connection URI.</span></span> <span data-ttu-id="389ad-183">Por exemplo, no seguinte URI de conexão, o nome do aplicativo é WSMan: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="389ad-183">For example, in the following connection URI, the application name is WSMan: `http://localhost:5985/WSMAN`.</span></span> <span data-ttu-id="389ad-184">O nome de aplicativo de uma sessão é armazenado na propriedade **Runspace.ConnectionInfo.AppName** da sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-184">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="389ad-185">O valor desse parâmetro é usado para selecionar e filtrar sessões.</span><span class="sxs-lookup"><span data-stu-id="389ad-185">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="389ad-186">Ele não altera o aplicativo utilizado pela sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-186">It does not change the application that the session uses.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-187">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="389ad-187">-Authentication</span></span>

<span data-ttu-id="389ad-188">Especifica o mecanismo usado para autenticar credenciais para a sessão na qual o `Get-PSSession` comando é executado.</span><span class="sxs-lookup"><span data-stu-id="389ad-188">Specifies the mechanism that is used to authenticate credentials for the session in which the `Get-PSSession` command runs.</span></span>

<span data-ttu-id="389ad-189">Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **ComputerName** ou **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="389ad-189">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="389ad-190">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="389ad-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="389ad-191">Padrão</span><span class="sxs-lookup"><span data-stu-id="389ad-191">Default</span></span>
- <span data-ttu-id="389ad-192">Básico</span><span class="sxs-lookup"><span data-stu-id="389ad-192">Basic</span></span>
- <span data-ttu-id="389ad-193">CredSSP</span><span class="sxs-lookup"><span data-stu-id="389ad-193">Credssp</span></span>
- <span data-ttu-id="389ad-194">Digest</span><span class="sxs-lookup"><span data-stu-id="389ad-194">Digest</span></span>
- <span data-ttu-id="389ad-195">Kerberos</span><span class="sxs-lookup"><span data-stu-id="389ad-195">Kerberos</span></span>
- <span data-ttu-id="389ad-196">Negotiate</span><span class="sxs-lookup"><span data-stu-id="389ad-196">Negotiate</span></span>
- <span data-ttu-id="389ad-197">NegotiateWithImplicitCredential.</span><span class="sxs-lookup"><span data-stu-id="389ad-197">NegotiateWithImplicitCredential.</span></span>

<span data-ttu-id="389ad-198">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="389ad-198">The default value is Default.</span></span>

<span data-ttu-id="389ad-199">Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="389ad-199">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

<span data-ttu-id="389ad-200">Cuidado: a autenticação do Credential Security Support Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="389ad-200">CAUTION: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="389ad-201">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="389ad-201">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="389ad-202">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="389ad-202">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="389ad-203">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="389ad-203">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-204">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="389ad-204">-CertificateThumbprint</span></span>

<span data-ttu-id="389ad-205">Especifica o certificado de chave pública digital (X509) de uma conta de usuário que tem permissão para criar a sessão na qual o `Get-PSSession` comando é executado.</span><span class="sxs-lookup"><span data-stu-id="389ad-205">Specifies the digital public key certificate (X509) of a user account that has permission to create the session in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="389ad-206">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="389ad-206">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="389ad-207">Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **ComputerName** ou **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="389ad-207">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="389ad-208">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="389ad-208">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="389ad-209">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="389ad-209">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="389ad-210">Para obter uma impressão digital do certificado, use um comando Get-Item ou Get-ChildItem na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="389ad-210">To get a certificate thumbprint, use a Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

<span data-ttu-id="389ad-211">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="389ad-211">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-212">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="389ad-212">-ComputerName</span></span>

<span data-ttu-id="389ad-213">Especifica uma matriz de nomes de computadores.</span><span class="sxs-lookup"><span data-stu-id="389ad-213">Specifies an array of names of computers.</span></span> <span data-ttu-id="389ad-214">Obtém as sessões que conectam a computadores especificados.</span><span class="sxs-lookup"><span data-stu-id="389ad-214">Gets the sessions that connect to the specified computers.</span></span>
<span data-ttu-id="389ad-215">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="389ad-215">Wildcard characters are not permitted.</span></span> <span data-ttu-id="389ad-216">Nenhum valor padrão.</span><span class="sxs-lookup"><span data-stu-id="389ad-216">There is no default value.</span></span>

<span data-ttu-id="389ad-217">A partir do Windows PowerShell 3,0, os objetos **PSSession** são armazenados nos computadores na extremidade remota de cada conexão.</span><span class="sxs-lookup"><span data-stu-id="389ad-217">Beginning in Windows PowerShell 3.0, **PSSession** objects are stored on the computers at the remote end of each connection.</span></span> <span data-ttu-id="389ad-218">Para obter as sessões nos computadores especificados, o PowerShell cria uma conexão temporária com cada computador e executa um `Get-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="389ad-218">To get the sessions on the specified computers, PowerShell creates a temporary connection to each computer and runs a `Get-PSSession` command.</span></span>

<span data-ttu-id="389ad-219">Digite o nome de NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um ou mais computadores.</span><span class="sxs-lookup"><span data-stu-id="389ad-219">Type the NetBIOS name, an IP address, or a fully-qualified domain name of one or more computers.</span></span> <span data-ttu-id="389ad-220">Para especificar o computador local, digite o nome do computador, localhost ou um ponto (.).</span><span class="sxs-lookup"><span data-stu-id="389ad-220">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span>

<span data-ttu-id="389ad-221">Observação: esse parâmetro Obtém sessões somente de computadores que executam o Windows PowerShell 3,0 ou versões posteriores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="389ad-221">Note: This parameter gets sessions only from computers that run Windows PowerShell 3.0 or later versions of PowerShell.</span></span> <span data-ttu-id="389ad-222">Versões anteriores não armazenam sessões.</span><span class="sxs-lookup"><span data-stu-id="389ad-222">Earlier versions do not store sessions.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerInstanceId, ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-223">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="389ad-223">-ConfigurationName</span></span>

<span data-ttu-id="389ad-224">Especifica o nome de uma configuração.</span><span class="sxs-lookup"><span data-stu-id="389ad-224">Specifies the name of a configuration.</span></span> <span data-ttu-id="389ad-225">Esse cmdlet obtém somente as sessões que usam a configuração de sessão especificada.</span><span class="sxs-lookup"><span data-stu-id="389ad-225">This cmdlet gets only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="389ad-226">Insira um nome de configuração ou o URI do recurso totalmente qualificado para uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-226">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="389ad-227">Se você especificar apenas o nome da configuração, o seguinte URI de esquema será anexado: `http://schemas.microsoft.com/powershell` .</span><span class="sxs-lookup"><span data-stu-id="389ad-227">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span> <span data-ttu-id="389ad-228">O nome de configuração de uma sessão é armazenado na propriedade **ConfigurationName** da sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-228">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="389ad-229">O valor desse parâmetro é usado para selecionar e filtrar sessões.</span><span class="sxs-lookup"><span data-stu-id="389ad-229">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="389ad-230">Ele não altera a configuração de sessão utilizada pela sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-230">It does not change the session configuration that the session uses.</span></span>

<span data-ttu-id="389ad-231">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="389ad-231">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri, ContainerId, ContainerIdInstanceId, VMId, VMIdInstanceId, VMName, VMNameInstanceId
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-232">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="389ad-232">-ConnectionUri</span></span>

<span data-ttu-id="389ad-233">Especifica um URI que define o ponto de extremidade de conexão para a sessão temporária na qual o `Get-PSSession` comando é executado.</span><span class="sxs-lookup"><span data-stu-id="389ad-233">Specifies a URI that defines the connection endpoint for the temporary session in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="389ad-234">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="389ad-234">The URI must be fully qualified.</span></span>

<span data-ttu-id="389ad-235">Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="389ad-235">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ConnectionUri** parameter.</span></span>

<span data-ttu-id="389ad-236">O formato dessa cadeia de caracteres é:</span><span class="sxs-lookup"><span data-stu-id="389ad-236">The format of this string is:</span></span>

`<Transport>://<ComputerName>:<Port\>/<ApplicationName>`

<span data-ttu-id="389ad-237">O valor padrão é: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="389ad-237">The default value is: `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="389ad-238">Se você não especificar um **conexãouri**, poderá usar os parâmetros **UseSSL**, **ComputerName**, **Port** e **ApplicationName** para especificar os valores de **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="389ad-238">If you do not specify a **ConnectionUri**, you can use the **UseSSL**, **ComputerName**, **Port**, and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span> <span data-ttu-id="389ad-239">Os valores válidos para o segmento Transport do URI são HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="389ad-239">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="389ad-240">Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada com portas de padrões: 80 para HTTP e 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="389ad-240">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="389ad-241">Para usar as portas padrão para comunicação remota do PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="389ad-241">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="389ad-242">Se o computador de destino redireciona a conexão para um URI diferente, o PowerShell impede o redirecionamento, a menos que você use o parâmetro **AllowRedirection** no comando.</span><span class="sxs-lookup"><span data-stu-id="389ad-242">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

<span data-ttu-id="389ad-243">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="389ad-243">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="389ad-244">Esse parâmetro Obtém sessões somente de computadores que executam o Windows PowerShell 3,0 ou versões posteriores do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="389ad-244">This parameter gets sessions only from computers that run Windows PowerShell 3.0 or later versions of Windows PowerShell.</span></span> <span data-ttu-id="389ad-245">Versões anteriores não armazenam sessões.</span><span class="sxs-lookup"><span data-stu-id="389ad-245">Earlier versions do not store sessions.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUriInstanceId, ConnectionUri
Aliases: URI, CU

Required: True
Position: 0
Default value: Http://localhost:5985/WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-246">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="389ad-246">-ContainerId</span></span>

<span data-ttu-id="389ad-247">Especifica uma matriz de IDs de contêineres.</span><span class="sxs-lookup"><span data-stu-id="389ad-247">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="389ad-248">Esse cmdlet inicia uma sessão interativa com cada um dos contêineres especificados.</span><span class="sxs-lookup"><span data-stu-id="389ad-248">This cmdlet starts an interactive session with each of the specified containers.</span></span> <span data-ttu-id="389ad-249">Use o `docker ps` comando para obter uma lista de IDs de contêiner.</span><span class="sxs-lookup"><span data-stu-id="389ad-249">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="389ad-250">Para obter mais informações, consulte a ajuda para o comando [Docker PS](https://docs.docker.com/engine/reference/commandline/ps/) .</span><span class="sxs-lookup"><span data-stu-id="389ad-250">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId, ContainerIdInstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-251">-Credential</span><span class="sxs-lookup"><span data-stu-id="389ad-251">-Credential</span></span>

<span data-ttu-id="389ad-252">Especifica uma credencial de usuário.</span><span class="sxs-lookup"><span data-stu-id="389ad-252">Specifies a user credential.</span></span> <span data-ttu-id="389ad-253">Esse cmdlet executa o comando com as permissões do usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="389ad-253">This cmdlet runs the command with the permissions of the specified user.</span></span> <span data-ttu-id="389ad-254">Especifique uma conta de usuário que tenha permissão para se conectar ao computador remoto e executar um `Get-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="389ad-254">Specify a user account that has permission to connect to the remote computer and run a `Get-PSSession` command.</span></span> <span data-ttu-id="389ad-255">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="389ad-255">The default is the current user.</span></span>

<span data-ttu-id="389ad-256">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**, ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="389ad-256">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="389ad-257">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="389ad-257">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="389ad-258">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="389ad-258">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="389ad-259">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="389ad-259">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

<span data-ttu-id="389ad-260">Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **ComputerName** ou **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="389ad-260">This parameter configures to the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="389ad-261">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="389ad-261">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-262">-Id</span><span class="sxs-lookup"><span data-stu-id="389ad-262">-Id</span></span>

<span data-ttu-id="389ad-263">Especifica uma matriz de IDs de sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-263">Specifies an array of session IDs.</span></span> <span data-ttu-id="389ad-264">Esse cmdlet obtém apenas as sessões com as IDs especificadas.</span><span class="sxs-lookup"><span data-stu-id="389ad-264">This cmdlet gets only the sessions with the specified IDs.</span></span> <span data-ttu-id="389ad-265">Digite uma ou mais IDs, separadas por vírgulas, ou use o operador de intervalo (..) para especificar um intervalo de IDs.</span><span class="sxs-lookup"><span data-stu-id="389ad-265">Type one or more IDs, separated by commas, or use the range operator (..) to specify a range of IDs.</span></span> <span data-ttu-id="389ad-266">Você não pode usar o parâmetro ID junto com o parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="389ad-266">You cannot use the ID parameter together with the **ComputerName** parameter.</span></span>

<span data-ttu-id="389ad-267">Uma ID é um inteiro que identifica exclusivamente as sessões gerenciadas pelo usuário na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="389ad-267">An ID is an integer that uniquely identifies the user-managed sessions in the current session.</span></span> <span data-ttu-id="389ad-268">É mais fácil lembrar e digitar do que a **InstanceId**, mas só é exclusiva na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="389ad-268">It is easier to remember and type than the **InstanceId**, but it is unique only within the current session.</span></span> <span data-ttu-id="389ad-269">A ID de uma sessão é armazenada na propriedade ID da sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-269">The ID of a session is stored in the ID property of the session.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-270">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="389ad-270">-InstanceId</span></span>

<span data-ttu-id="389ad-271">Especifica uma matriz de IDs de instância de sessões.</span><span class="sxs-lookup"><span data-stu-id="389ad-271">Specifies an array of instance IDs of sessions.</span></span> <span data-ttu-id="389ad-272">Esse cmdlet obtém apenas as sessões com as IDs de instância especificadas.</span><span class="sxs-lookup"><span data-stu-id="389ad-272">This cmdlet gets only the sessions with the specified instance IDs.</span></span>

<span data-ttu-id="389ad-273">A ID de instância é um GUID que identifica exclusivamente uma sessão em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="389ad-273">The instance ID is a GUID that uniquely identifies a session on a local or remote computer.</span></span> <span data-ttu-id="389ad-274">A **InstanceId** é exclusiva, mesmo quando você tem várias sessões em execução no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="389ad-274">The **InstanceID** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="389ad-275">A ID de instância de uma sessão é armazenada na propriedade **InstanceID** da sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-275">The instance ID of a session is stored in the **InstanceID** property of the session.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: ComputerInstanceId, ConnectionUriInstanceId, ContainerIdInstanceId, VMIdInstanceId, VMNameInstanceId, InstanceId
Aliases:

Required: True (ComputerInstanceId, ConnectionUriInstanceId, ContainerIdInstanceId, VMIdInstanceId, VMNameInstanceId), False (InstanceId)
Position: Named
Default value: All sessions
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-276">-Name</span><span class="sxs-lookup"><span data-stu-id="389ad-276">-Name</span></span>

<span data-ttu-id="389ad-277">Especifica uma matriz de nomes de sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-277">Specifies an array of session names.</span></span> <span data-ttu-id="389ad-278">Esse cmdlet obtém apenas as sessões que têm os nomes amigáveis especificados.</span><span class="sxs-lookup"><span data-stu-id="389ad-278">This cmdlet gets only the sessions that have the specified friendly names.</span></span> <span data-ttu-id="389ad-279">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="389ad-279">Wildcard characters are permitted.</span></span>

<span data-ttu-id="389ad-280">O nome amigável de uma sessão é armazenado na propriedade **Name** da sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-280">The friendly name of a session is stored in the **Name** property of the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri, ContainerId, VMId, VMName
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="389ad-281">-Port</span><span class="sxs-lookup"><span data-stu-id="389ad-281">-Port</span></span>

<span data-ttu-id="389ad-282">Especifica a porta de rede especificada que é usada para a conexão temporária na qual o `Get-PSSession` comando é executado.</span><span class="sxs-lookup"><span data-stu-id="389ad-282">Specifies the specified network port that is used for the temporary connection in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="389ad-283">Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão.</span><span class="sxs-lookup"><span data-stu-id="389ad-283">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="389ad-284">As portas padrão são 5985, que é a porta do WinRM para HTTP e 5986, que é a porta do WinRM para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="389ad-284">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="389ad-285">Antes de usar uma porta alternativa, você deve configurar o ouvinte de WinRM no computador remoto para escutar na porta.</span><span class="sxs-lookup"><span data-stu-id="389ad-285">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="389ad-286">Para configurar o ouvinte, digite os dois comandos a seguir no prompt do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="389ad-286">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="389ad-287">Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **ComputerName** ou **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="389ad-287">This parameter configures to the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="389ad-288">Não use o parâmetro **Port** a menos que seja necessário.</span><span class="sxs-lookup"><span data-stu-id="389ad-288">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="389ad-289">A **porta** definida no comando aplica-se a todos os computadores ou sessões em que o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="389ad-289">The **Port** set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="389ad-290">Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="389ad-290">An alternate port setting might prevent the command from running on all computers.</span></span>

<span data-ttu-id="389ad-291">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="389ad-291">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: 5985, 5986
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-292">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="389ad-292">-SessionOption</span></span>

<span data-ttu-id="389ad-293">Especifica as opções avançadas para a sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-293">Specifies advanced options for the session.</span></span> <span data-ttu-id="389ad-294">Insira um objeto **SessionOption** , como um que você cria usando o cmdlet New-PSSessionOption ou uma tabela de hash na qual as chaves são nomes de opção de sessão e os valores são valores de opção de sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-294">Enter a **SessionOption** object, such as one that you create by using the New-PSSessionOption cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="389ad-295">Os valores padrão das opções são determinados pelo valor da variável de preferência $PSSessionOption, se definida.</span><span class="sxs-lookup"><span data-stu-id="389ad-295">The default values for the options are determined by the value of the $PSSessionOption preference variable, if it is set.</span></span> <span data-ttu-id="389ad-296">Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-296">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="389ad-297">Os valores de opção da sessão têm precedência sobre os valores padrão de sessões definidos na variável de preferência $PSSessionOption e na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-297">The session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span> <span data-ttu-id="389ad-298">No entanto, eles não têm precedência sobre valores máximos, cotas ou limites definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-298">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="389ad-299">Para obter uma descrição das opções de sessão, incluindo os valores padrão, consulte `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="389ad-299">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="389ad-300">Para obter informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="389ad-300">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="389ad-301">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="389ad-301">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-302">-Estado</span><span class="sxs-lookup"><span data-stu-id="389ad-302">-State</span></span>

<span data-ttu-id="389ad-303">Especifica um estado de sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-303">Specifies a session state.</span></span> <span data-ttu-id="389ad-304">Este cmdlet obtém apenas sessões no estado especificado.</span><span class="sxs-lookup"><span data-stu-id="389ad-304">This cmdlet gets only sessions in the specified state.</span></span> <span data-ttu-id="389ad-305">Os valores aceitáveis para esse parâmetro são: todos, abertos, desconectados, fechados e desfeitos.</span><span class="sxs-lookup"><span data-stu-id="389ad-305">The acceptable values for this parameter are: All, Opened, Disconnected, Closed, and Broken.</span></span> <span data-ttu-id="389ad-306">O valor padrão é All.</span><span class="sxs-lookup"><span data-stu-id="389ad-306">The default value is All.</span></span>

<span data-ttu-id="389ad-307">O valor de estado de sessão é relativo à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="389ad-307">The session state value is relative to the current sessions.</span></span> <span data-ttu-id="389ad-308">Sessões que não tiverem sido criadas nas sessões atuais e não estiverem conectadas à sessão atual terão um estado de Disconnected, mesmo quando estiverem conectadas a uma sessão diferente.</span><span class="sxs-lookup"><span data-stu-id="389ad-308">Sessions that were not created in the current sessions and are not connected to the current session have a state of Disconnected even when they are connected to a different session.</span></span>

<span data-ttu-id="389ad-309">O estado de uma sessão é armazenado na propriedade **State** da sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-309">The state of a session is stored in the **State** property of the session.</span></span>

<span data-ttu-id="389ad-310">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="389ad-310">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.SessionFilterState
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri, ContainerId, ContainerIdInstanceId, VMId, VMIdInstanceId, VMName, VMNameInstanceId
Aliases:
Accepted values: All, Opened, Disconnected, Closed, Broken

Required: False
Position: Named
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-311">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="389ad-311">-ThrottleLimit</span></span>

<span data-ttu-id="389ad-312">Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o `Get-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="389ad-312">Specifies the maximum number of concurrent connections that can be established to run the `Get-PSSession` command.</span></span> <span data-ttu-id="389ad-313">Se você omitir esse parâmetro ou digitar o valor 0 (zero), o valor padrão, 32, será usado.</span><span class="sxs-lookup"><span data-stu-id="389ad-313">If you omit this parameter or enter a value of 0 (zero), the default value, 32, is used.</span></span> <span data-ttu-id="389ad-314">O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="389ad-314">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

<span data-ttu-id="389ad-315">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="389ad-315">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-316">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="389ad-316">-UseSSL</span></span>

<span data-ttu-id="389ad-317">Indica que esse cmdlet usa o protocolo protocolo SSL (SSL) para estabelecer a conexão na qual o `Get-PSSession` comando é executado.</span><span class="sxs-lookup"><span data-stu-id="389ad-317">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish the connection in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="389ad-318">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="389ad-318">By default, SSL is not used.</span></span> <span data-ttu-id="389ad-319">Se você usar esse parâmetro e o SSL não estiver disponível na porta usada para o comando, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="389ad-319">If you use this parameter, but SSL is not available on the port used for the command, the command fails.</span></span>

<span data-ttu-id="389ad-320">Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="389ad-320">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** parameter.</span></span>

<span data-ttu-id="389ad-321">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="389ad-321">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-322">-VMId</span><span class="sxs-lookup"><span data-stu-id="389ad-322">-VMId</span></span>

<span data-ttu-id="389ad-323">Especifica uma matriz de ID de máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="389ad-323">Specifies an array of ID of virtual machines.</span></span> <span data-ttu-id="389ad-324">Esse cmdlet inicia uma sessão interativa com cada uma das máquinas virtuais especificadas.</span><span class="sxs-lookup"><span data-stu-id="389ad-324">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="389ad-325">Para ver as máquinas virtuais que estão disponíveis para você, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="389ad-325">To see the virtual machines that are available to you, use the following command:</span></span>

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId, VMIdInstanceId
Aliases: VMGuid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-326">-VMName</span><span class="sxs-lookup"><span data-stu-id="389ad-326">-VMName</span></span>

<span data-ttu-id="389ad-327">Especifica uma matriz de nomes de máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="389ad-327">Specifies an array of names of virtual machines.</span></span> <span data-ttu-id="389ad-328">Esse cmdlet inicia uma sessão interativa com cada uma das máquinas virtuais especificadas.</span><span class="sxs-lookup"><span data-stu-id="389ad-328">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="389ad-329">Para ver as máquinas virtuais que estão disponíveis para você, use o `Get-VM` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="389ad-329">To see the virtual machines that are available to you, use the `Get-VM` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName, VMNameInstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="389ad-330">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="389ad-330">CommonParameters</span></span>

<span data-ttu-id="389ad-331">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="389ad-331">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="389ad-332">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="389ad-332">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="389ad-333">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="389ad-333">INPUTS</span></span>

### <span data-ttu-id="389ad-334">Nenhum</span><span class="sxs-lookup"><span data-stu-id="389ad-334">None</span></span>

<span data-ttu-id="389ad-335">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="389ad-335">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="389ad-336">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="389ad-336">OUTPUTS</span></span>

### <span data-ttu-id="389ad-337">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="389ad-337">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="389ad-338">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="389ad-338">NOTES</span></span>

- <span data-ttu-id="389ad-339">Esse cmdlet obtém objetos **PSSession** de sessões gerenciadas pelo usuário "como aquelas criadas usando os cmdlets New-PSSession, `Enter-PSSession` e Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="389ad-339">This cmdlet gets user-managed sessions **PSSession** objects" such as those that are created by using the New-PSSession, `Enter-PSSession`, and Invoke-Command cmdlets.</span></span> <span data-ttu-id="389ad-340">Ele não obtém a sessão gerenciada pelo sistema que é criada quando você inicia o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="389ad-340">It does not get the system-managed session that is created when you start PowerShell.</span></span>
- <span data-ttu-id="389ad-341">A partir do Windows PowerShell 3,0, os objetos **PSSession** são armazenados no computador que está no lado do servidor ou no fim do recebimento de uma conexão.</span><span class="sxs-lookup"><span data-stu-id="389ad-341">Starting in Windows PowerShell 3.0, **PSSession** objects are stored on the computer that is at the server-side or receiving end of a connection.</span></span> <span data-ttu-id="389ad-342">Para obter as sessões armazenadas no computador local ou em um computador remoto, o PowerShell estabelece uma sessão temporária para o computador especificado e executa comandos de consulta na sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-342">To get the sessions that are stored on the local computer or a remote computer, PowerShell establishes a temporary session to the specified computer and runs query commands in the session.</span></span>
- <span data-ttu-id="389ad-343">Para obter sessões que se conectam a um computador remoto, use os parâmetros **ComputerName** ou **ConnectionUri** para especificar o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="389ad-343">To get sessions that connect to a remote computer, use the **ComputerName** or **ConnectionUri** parameters to specify the remote computer.</span></span> <span data-ttu-id="389ad-344">Para filtrar as sessões que `Get-PSSession` Obtém, use os parâmetros **Name**, **ID**, **InstanceId** e **State** .</span><span class="sxs-lookup"><span data-stu-id="389ad-344">To filter the sessions that `Get-PSSession` gets, use the **Name**, **ID**, **InstanceID**, and **State** parameters.</span></span> <span data-ttu-id="389ad-345">Use os parâmetros restantes para configurar a sessão temporária que o `Get-PSSession` usa.</span><span class="sxs-lookup"><span data-stu-id="389ad-345">Use the remaining parameters to configure the temporary session that `Get-PSSession` uses.</span></span>
- <span data-ttu-id="389ad-346">Quando você usa os parâmetros **ComputerName** ou **conexãouri** , o `Get-PSSession` obtém apenas sessões de computadores que executam o Windows PowerShell 3,0 e versões posteriores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="389ad-346">When you use the **ComputerName** or **ConnectionUri** parameters, `Get-PSSession` gets only sessions from computers running Windows PowerShell 3.0 and later versions of PowerShell.</span></span>
- <span data-ttu-id="389ad-347">O valor da propriedade **State** de uma **PSSession** é relativo à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="389ad-347">The value of the **State** property of a **PSSession** is relative to the current session.</span></span>
  <span data-ttu-id="389ad-348">Portanto, um valor de **desconectado** significa que a **PSSession** não está conectada à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="389ad-348">Therefore, a value of **Disconnected** means that the **PSSession** is not connected to the current session.</span></span> <span data-ttu-id="389ad-349">No entanto, isso não significa que a **PSSession** seja desconectada de todas as sessões.</span><span class="sxs-lookup"><span data-stu-id="389ad-349">However, it does not mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="389ad-350">Ela pode ser conectada a uma sessão diferente.</span><span class="sxs-lookup"><span data-stu-id="389ad-350">It might be connected to a different session.</span></span> <span data-ttu-id="389ad-351">Para determinar se você pode se conectar ou reconectar-se à **PSSession** da sessão atual, use a propriedade de **disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="389ad-351">To determine whether you can connect or reconnect to the **PSSession** from the current session, use the **Availability** property.</span></span>

<span data-ttu-id="389ad-352">Um valor **Availability** de **None** indica que é possível conectar-se à sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-352">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="389ad-353">Um valor de **ocupado** indica que você não pode se conectar à **PSSession** porque ela está conectada a outra sessão.</span><span class="sxs-lookup"><span data-stu-id="389ad-353">A value of **Busy** indicates that you cannot connect to the **PSSession** because it is connected to another session.</span></span>

<span data-ttu-id="389ad-354">Para obter mais informações sobre os valores da propriedade **State** de sessões, consulte [Enumeração RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate).</span><span class="sxs-lookup"><span data-stu-id="389ad-354">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span>

<span data-ttu-id="389ad-355">Para obter mais informações sobre os valores da propriedade de sessões de **disponibilidade** , consulte [Enumeração RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="389ad-355">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="389ad-356">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="389ad-356">RELATED LINKS</span></span>

[<span data-ttu-id="389ad-357">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="389ad-357">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="389ad-358">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="389ad-358">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="389ad-359">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="389ad-359">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="389ad-360">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="389ad-360">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="389ad-361">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="389ad-361">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="389ad-362">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="389ad-362">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="389ad-363">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="389ad-363">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="389ad-364">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="389ad-364">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="389ad-365">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="389ad-365">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="389ad-366">about_Remote</span><span class="sxs-lookup"><span data-stu-id="389ad-366">about_Remote</span></span>](About/about_Remote.md)

