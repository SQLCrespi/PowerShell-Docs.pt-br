---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSession
ms.openlocfilehash: 08ca0ec9a45542e86ea197fc24df65430f2d0649
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93195030"
---
# <span data-ttu-id="5893b-103">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="5893b-103">Get-PSSession</span></span>

## <span data-ttu-id="5893b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5893b-104">SYNOPSIS</span></span>
<span data-ttu-id="5893b-105">Obtém as sessões do PowerShell em computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="5893b-105">Gets the PowerShell sessions on local and remote computers.</span></span>

## <span data-ttu-id="5893b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5893b-106">SYNTAX</span></span>

### <span data-ttu-id="5893b-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="5893b-107">Name (Default)</span></span>

```
Get-PSSession [-Name <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="5893b-108">ComputerName</span><span class="sxs-lookup"><span data-stu-id="5893b-108">ComputerName</span></span>

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="5893b-109">ComputerInstanceId</span><span class="sxs-lookup"><span data-stu-id="5893b-109">ComputerInstanceId</span></span>

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="5893b-110">ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="5893b-110">ConnectionUri</span></span>

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="5893b-111">ConnectionUriInstanceId</span><span class="sxs-lookup"><span data-stu-id="5893b-111">ConnectionUriInstanceId</span></span>

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] -InstanceId <Guid[]>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="5893b-112">VMNameInstanceId</span><span class="sxs-lookup"><span data-stu-id="5893b-112">VMNameInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="5893b-113">ContainerId</span><span class="sxs-lookup"><span data-stu-id="5893b-113">ContainerId</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="5893b-114">ContainerIdInstanceId</span><span class="sxs-lookup"><span data-stu-id="5893b-114">ContainerIdInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="5893b-115">VMId</span><span class="sxs-lookup"><span data-stu-id="5893b-115">VMId</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### <span data-ttu-id="5893b-116">VMIdInstanceId</span><span class="sxs-lookup"><span data-stu-id="5893b-116">VMIdInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### <span data-ttu-id="5893b-117">VMName</span><span class="sxs-lookup"><span data-stu-id="5893b-117">VMName</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMName <String[]>
 [<CommonParameters>]
```

### <span data-ttu-id="5893b-118">InstanceId</span><span class="sxs-lookup"><span data-stu-id="5893b-118">InstanceId</span></span>

```
Get-PSSession [-InstanceId <Guid[]>] [<CommonParameters>]
```

### <span data-ttu-id="5893b-119">ID</span><span class="sxs-lookup"><span data-stu-id="5893b-119">Id</span></span>

```
Get-PSSession [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="5893b-120">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5893b-120">DESCRIPTION</span></span>

<span data-ttu-id="5893b-121">O `Get-PSSession` cmdlet obtém as sessões do PowerShell gerenciadas pelo usuário ( **PSSessions** ) em computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="5893b-121">The `Get-PSSession` cmdlet gets the user-managed PowerShell sessions ( **PSSessions** ) on local and remote computers.</span></span>

<span data-ttu-id="5893b-122">A partir do Windows PowerShell 3,0, as sessões são armazenadas nos computadores na extremidade remota de cada conexão.</span><span class="sxs-lookup"><span data-stu-id="5893b-122">Starting in Windows PowerShell 3.0, sessions are stored on the computers at the remote end of each connection.</span></span> <span data-ttu-id="5893b-123">Você pode usar os parâmetros **ComputerName** ou **conexãouri** do `Get-PSSession` para obter as sessões que se conectam ao computador local ou a computadores remotos, mesmo que eles não tenham sido criados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5893b-123">You can use the **ComputerName** or **ConnectionUri** parameters of `Get-PSSession` to get the sessions that connect to the local computer or remote computers, even if they were not created in the current session.</span></span>

<span data-ttu-id="5893b-124">Sem parâmetros, `Get-PSSession` obtém todas as sessões que foram criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5893b-124">Without parameters, `Get-PSSession` gets all sessions that were created in the current session.</span></span>

<span data-ttu-id="5893b-125">Use os parâmetros de filtragem, incluindo **Name** , **ID** , **InstanceId** , **State** , **ApplicationName** e **ConfigurationName** para selecionar entre as sessões que `Get-PSSession` retorna.</span><span class="sxs-lookup"><span data-stu-id="5893b-125">Use the filtering parameters, including **Name** , **ID** , **InstanceID** , **State** , **ApplicationName** , and **ConfigurationName** to select from among the sessions that `Get-PSSession` returns.</span></span>

<span data-ttu-id="5893b-126">Use os parâmetros restantes para configurar a conexão temporária na qual o `Get-PSSession` comando é executado quando você usa os parâmetros **ComputerName** ou **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="5893b-126">Use the remaining parameters to configure the temporary connection in which the `Get-PSSession` command runs when you use the **ComputerName** or **ConnectionUri** parameters.</span></span>

<span data-ttu-id="5893b-127">Observação: no Windows PowerShell 2,0, sem parâmetros, `Get-PSSession` obtém todas as sessões que foram criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5893b-127">NOTE: In Windows PowerShell 2.0, without parameters, `Get-PSSession` gets all sessions that were created in the current session.</span></span> <span data-ttu-id="5893b-128">O parâmetro **ComputerName** Obtém as sessões que foram criadas na sessão atual e se conecta ao computador especificado.</span><span class="sxs-lookup"><span data-stu-id="5893b-128">The **ComputerName** parameter gets sessions that were created in the current session and connect to the specified computer.</span></span>

<span data-ttu-id="5893b-129">Para obter mais informações sobre sessões do PowerShell, consulte [about_PSSessions](about/about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="5893b-129">For more information about PowerShell sessions, see [about_PSSessions](about/about_PSSessions.md).</span></span>

## <span data-ttu-id="5893b-130">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5893b-130">EXAMPLES</span></span>

### <span data-ttu-id="5893b-131">Exemplo 1: obter sessões criadas na sessão atual</span><span class="sxs-lookup"><span data-stu-id="5893b-131">Example 1: Get sessions created in the current session</span></span>

```powershell
Get-PSSession
```

<span data-ttu-id="5893b-132">Esse comando obtém todas as **PSSessions** que foram criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5893b-132">This command gets all of the **PSSessions** that were created in the current session.</span></span> <span data-ttu-id="5893b-133">Ele não obtém **PSSessions** que foram criadas em outras sessões ou em outros computadores, mesmo que se conectem a este computador.</span><span class="sxs-lookup"><span data-stu-id="5893b-133">It does not get **PSSessions** that were created in other sessions or on other computers, even if they connect to this computer.</span></span>

### <span data-ttu-id="5893b-134">Exemplo 2: obter sessões conectadas ao computador local</span><span class="sxs-lookup"><span data-stu-id="5893b-134">Example 2: Get sessions connected to the local computer</span></span>

```powershell
Get-PSSession -ComputerName "localhost"
```

<span data-ttu-id="5893b-135">Esse comando obtém as **PSSessions** que estão conectadas ao computador local.</span><span class="sxs-lookup"><span data-stu-id="5893b-135">This command gets the **PSSessions** that are connected to the local computer.</span></span> <span data-ttu-id="5893b-136">Para indicar o computador local, digite o nome do computador, localhost ou um ponto (.)</span><span class="sxs-lookup"><span data-stu-id="5893b-136">To indicate the local computer, type the computer name, localhost, or a dot (.)</span></span>

<span data-ttu-id="5893b-137">O comando retorna todas as sessões no computador local, mesmo que elas tenham sido criadas em sessões ou em computadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="5893b-137">The command returns all of the sessions on the local computer, even if they were created in different sessions or on different computers.</span></span>

### <span data-ttu-id="5893b-138">Exemplo 3: obter sessões conectadas a um computador</span><span class="sxs-lookup"><span data-stu-id="5893b-138">Example 3: Get sessions connected to a computer</span></span>

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

<span data-ttu-id="5893b-139">Esse comando obtém as **PSSessions** que estão conectadas ao computador Server02.</span><span class="sxs-lookup"><span data-stu-id="5893b-139">This command gets the **PSSessions** that are connected to the Server02 computer.</span></span>

<span data-ttu-id="5893b-140">O comando retorna todas as sessões em Server02, mesmo que elas tenham sido criadas em sessões ou em computadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="5893b-140">The command returns all of the sessions on Server02, even if they were created in different sessions or on different computers.</span></span>

<span data-ttu-id="5893b-141">A saída mostra que duas das sessões têm o estado de Desconectado e a disponibilidade de Ocupado.</span><span class="sxs-lookup"><span data-stu-id="5893b-141">The output shows that two of the sessions have a Disconnected state and a Busy availability.</span></span> <span data-ttu-id="5893b-142">Elas foram criadas em sessões diferentes e estão em uso atualmente.</span><span class="sxs-lookup"><span data-stu-id="5893b-142">They were created in different sessions and are currently in use.</span></span> <span data-ttu-id="5893b-143">A sessão ScheduledJobs, que está aberta e disponível, foi criada na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5893b-143">The ScheduledJobs session, which is Opened and Available, was created in the current session.</span></span>

### <span data-ttu-id="5893b-144">Exemplo 4: salvar os resultados deste comando</span><span class="sxs-lookup"><span data-stu-id="5893b-144">Example 4: Save results of this command</span></span>

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
$s1, $s2, $s3 = Get-PSSession
```

<span data-ttu-id="5893b-145">Este exemplo mostra como salvar os resultados de um `Get-PSSession` comando em várias variáveis.</span><span class="sxs-lookup"><span data-stu-id="5893b-145">This example shows how to save the results of a `Get-PSSession` command in multiple variables.</span></span>

<span data-ttu-id="5893b-146">O primeiro comando usa o `New-PSSession` cmdlet para criar **PSSessions** em três computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="5893b-146">The first command uses the `New-PSSession` cmdlet to create **PSSessions** on three remote computers.</span></span>

<span data-ttu-id="5893b-147">O segundo comando usa um `Get-PSSession` cmdlet para obter as três **PSSessions** .</span><span class="sxs-lookup"><span data-stu-id="5893b-147">The second command uses a `Get-PSSession` cmdlet to get the three **PSSessions** .</span></span> <span data-ttu-id="5893b-148">Em seguida, ele salva cada uma das **PSSessions** em uma variável separada.</span><span class="sxs-lookup"><span data-stu-id="5893b-148">It then saves each of the **PSSessions** in a separate variable.</span></span>

<span data-ttu-id="5893b-149">Quando o PowerShell atribui uma matriz de objetos a uma matriz de variáveis, ele atribui o primeiro objeto à primeira variável, o segundo objeto à segunda variável e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="5893b-149">When PowerShell assigns an array of objects to an array of variables, it assigns the first object to the first variable, the second object to the second variable, and so on.</span></span> <span data-ttu-id="5893b-150">Se houver mais objetos que variáveis, ele atribui todos os objetos restantes à última variável da matriz.</span><span class="sxs-lookup"><span data-stu-id="5893b-150">If there are more objects than variables, it assigns all remaining objects to the last variable in the array.</span></span> <span data-ttu-id="5893b-151">Se houver mais variáveis que objetos, as variáveis extra não são usadas.</span><span class="sxs-lookup"><span data-stu-id="5893b-151">If there are more variables than objects, the extra variables are not used.</span></span>

### <span data-ttu-id="5893b-152">Exemplo 5: excluir uma sessão usando uma ID de instância</span><span class="sxs-lookup"><span data-stu-id="5893b-152">Example 5: Delete a session by using an instance ID</span></span>

```powershell
Get-PSSession | Format-Table -Property ComputerName, InstanceID
$s = Get-PSSession -InstanceID a786be29-a6bb-40da-80fb-782c67f7db0f
Remove-PSSession -Session $s
```

<span data-ttu-id="5893b-153">Este exemplo mostra como obter uma **PSSession** usando sua ID de instância e, em seguida, excluir a **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="5893b-153">This example shows how to get a **PSSession** by using its instance ID, and then to delete the **PSSession** .</span></span>

<span data-ttu-id="5893b-154">O primeiro comando obtém todas as **PSSessions** que foram criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5893b-154">The first command gets all of the **PSSessions** that were created in the current session.</span></span> <span data-ttu-id="5893b-155">Ele envia as **PSSessions** para o cmdlet Format-Table, que exibe as propriedades **ComputerName** e **InstanceId** de cada **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="5893b-155">It sends the **PSSessions** to the Format-Table cmdlet, which displays the **ComputerName** and **InstanceID** properties of each **PSSession** .</span></span>

<span data-ttu-id="5893b-156">O segundo comando usa o `Get-PSSession` cmdlet para obter uma **PSSession** específica e salvá-la na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="5893b-156">The second command uses the `Get-PSSession` cmdlet to get a particular **PSSession** and to save it in the `$s` variable.</span></span> <span data-ttu-id="5893b-157">O comando usa o parâmetro **InstanceId** para identificar a **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="5893b-157">The command uses the **InstanceID** parameter to identify the **PSSession** .</span></span>

<span data-ttu-id="5893b-158">O terceiro comando usa o cmdlet Remove-PSSession para excluir a **PSSession** na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="5893b-158">The third command uses the Remove-PSSession cmdlet to delete the **PSSession** in the `$s` variable.</span></span>

### <span data-ttu-id="5893b-159">Exemplo 6: obter uma sessão que tem um nome específico</span><span class="sxs-lookup"><span data-stu-id="5893b-159">Example 6: Get a session that has a particular name</span></span>

<span data-ttu-id="5893b-160">Os comandos neste exemplo encontram uma sessão que tem um formato de nome específico e usa uma configuração de sessão específica e, em seguida, se conecta à sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-160">The commands in this example find a session that has a particular name format and uses a particular session configuration and then connect to the session.</span></span> <span data-ttu-id="5893b-161">Você pode usar um comando como este para encontrar uma sessão na qual um colega iniciou uma tarefa e se conectar para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="5893b-161">You can use a command like this one to find a session in which a colleague started a task and connect to finish the task.</span></span>

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

<span data-ttu-id="5893b-162">O primeiro comando obtém sessões nos computadores remotos Server02 e Server12 que têm nomes que começam com BackupJob e usam a configuração de sessão ITTasks. O comando usa o parâmetro **Name** para especificar o padrão de nome e o parâmetro **ConfigurationName** para especificar a configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-162">The first command gets sessions on the Server02 and Server12 remote computers that have names that begin with BackupJob and use the ITTasks session configuration.The command uses the **Name** parameter to specify the name pattern and the **ConfigurationName** parameter to specify the session configuration.</span></span> <span data-ttu-id="5893b-163">O valor do parâmetro **SessionOption** é uma tabela de hash que define o valor de **OperationTimeout** como 240.000 milissegundos (4 minutos).</span><span class="sxs-lookup"><span data-stu-id="5893b-163">The value of the **SessionOption** parameter is a hash table that sets the value of the **OperationTimeout** to 240000 milliseconds (4 minutes).</span></span> <span data-ttu-id="5893b-164">Essa configuração fornece ao comando mais tempo para ser concluído. Os parâmetros **ConfigurationName** e **SessionOption** são usados para configurar as sessões temporárias nas quais o `Get-PSSession` cmdlet é executado em cada computador. A saída mostra que o comando retorna a sessão BackupJob04.</span><span class="sxs-lookup"><span data-stu-id="5893b-164">This setting gives the command more time to complete.The **ConfigurationName** and **SessionOption** parameters are used to configure the temporary sessions in which the `Get-PSSession` cmdlet runs on each computer.The output shows that the command returns the BackupJob04 session.</span></span> <span data-ttu-id="5893b-165">A sessão está desconectada e a **disponibilidade** é nenhuma, o que indica que ela não está em uso.</span><span class="sxs-lookup"><span data-stu-id="5893b-165">The session is disconnected and the **Availability** is None, which indicates that it is not in use.</span></span>

<span data-ttu-id="5893b-166">O segundo comando usa o `Get-PSSession` cmdlet para obter a sessão BackupJob04 e o cmdlet Connect-PSSession para se conectar à sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-166">The second command uses the `Get-PSSession` cmdlet to get to the BackupJob04 session and the Connect-PSSession cmdlet to connect to the session.</span></span> <span data-ttu-id="5893b-167">O comando salva a sessão na variável $s.</span><span class="sxs-lookup"><span data-stu-id="5893b-167">The command saves the session in the $s variable.</span></span>

<span data-ttu-id="5893b-168">O terceiro comando obtém a sessão na variável $s.</span><span class="sxs-lookup"><span data-stu-id="5893b-168">The third command gets the session in the $s variable.</span></span> <span data-ttu-id="5893b-169">A saída mostra que o `Connect-PSSession` comando foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="5893b-169">The output shows that the `Connect-PSSession` command was successful.</span></span> <span data-ttu-id="5893b-170">A sessão está no estado **Opened** e está disponível para uso.</span><span class="sxs-lookup"><span data-stu-id="5893b-170">The session is in the **Opened** state and is available for use.</span></span>

### <span data-ttu-id="5893b-171">Exemplo 7: obter uma sessão usando sua ID</span><span class="sxs-lookup"><span data-stu-id="5893b-171">Example 7: Get a session by using its ID</span></span>

```powershell
Get-PSSession -Id 2
```

<span data-ttu-id="5893b-172">Este comando obtém a **PSSession** com ID 2.</span><span class="sxs-lookup"><span data-stu-id="5893b-172">This command gets the **PSSession** with ID 2.</span></span> <span data-ttu-id="5893b-173">Como o valor da propriedade **ID** é exclusivo somente na sessão atual, o parâmetro **ID** é válido somente para comandos locais.</span><span class="sxs-lookup"><span data-stu-id="5893b-173">Because the value of the **ID** property is unique only in the current session, the **Id** parameter is valid only for local commands.</span></span>

## <span data-ttu-id="5893b-174">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5893b-174">PARAMETERS</span></span>

### <span data-ttu-id="5893b-175">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="5893b-175">-AllowRedirection</span></span>

<span data-ttu-id="5893b-176">Indica que esse cmdlet permite o redirecionamento dessa conexão para um Uniform Resource Identifier alternativo (URI).</span><span class="sxs-lookup"><span data-stu-id="5893b-176">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="5893b-177">Por padrão, o PowerShell não redireciona conexões.</span><span class="sxs-lookup"><span data-stu-id="5893b-177">By default, PowerShell does not redirect connections.</span></span>

<span data-ttu-id="5893b-178">Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="5893b-178">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ConnectionUri** parameter.</span></span>

<span data-ttu-id="5893b-179">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5893b-179">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5893b-180">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="5893b-180">-ApplicationName</span></span>

<span data-ttu-id="5893b-181">Especifica o nome de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5893b-181">Specifies the name of an application.</span></span> <span data-ttu-id="5893b-182">Esse cmdlet se conecta somente a sessões que usam o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="5893b-182">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="5893b-183">Insira o segmento de nome de aplicativo do URI de conexão.</span><span class="sxs-lookup"><span data-stu-id="5893b-183">Enter the application name segment of the connection URI.</span></span> <span data-ttu-id="5893b-184">Por exemplo, no seguinte URI de conexão, o nome do aplicativo é WSMan: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="5893b-184">For example, in the following connection URI, the application name is WSMan: `http://localhost:5985/WSMAN`.</span></span> <span data-ttu-id="5893b-185">O nome de aplicativo de uma sessão é armazenado na propriedade **Runspace.ConnectionInfo.AppName** da sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-185">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="5893b-186">O valor desse parâmetro é usado para selecionar e filtrar sessões.</span><span class="sxs-lookup"><span data-stu-id="5893b-186">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="5893b-187">Ele não altera o aplicativo utilizado pela sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-187">It does not change the application that the session uses.</span></span>

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

### <span data-ttu-id="5893b-188">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="5893b-188">-Authentication</span></span>

<span data-ttu-id="5893b-189">Especifica o mecanismo usado para autenticar credenciais para a sessão na qual o `Get-PSSession` comando é executado.</span><span class="sxs-lookup"><span data-stu-id="5893b-189">Specifies the mechanism that is used to authenticate credentials for the session in which the `Get-PSSession` command runs.</span></span>

<span data-ttu-id="5893b-190">Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **ComputerName** ou **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="5893b-190">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="5893b-191">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="5893b-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5893b-192">Padrão</span><span class="sxs-lookup"><span data-stu-id="5893b-192">Default</span></span>
- <span data-ttu-id="5893b-193">Básico</span><span class="sxs-lookup"><span data-stu-id="5893b-193">Basic</span></span>
- <span data-ttu-id="5893b-194">CredSSP</span><span class="sxs-lookup"><span data-stu-id="5893b-194">Credssp</span></span>
- <span data-ttu-id="5893b-195">Digest</span><span class="sxs-lookup"><span data-stu-id="5893b-195">Digest</span></span>
- <span data-ttu-id="5893b-196">Kerberos</span><span class="sxs-lookup"><span data-stu-id="5893b-196">Kerberos</span></span>
- <span data-ttu-id="5893b-197">Negotiate</span><span class="sxs-lookup"><span data-stu-id="5893b-197">Negotiate</span></span>
- <span data-ttu-id="5893b-198">NegotiateWithImplicitCredential.</span><span class="sxs-lookup"><span data-stu-id="5893b-198">NegotiateWithImplicitCredential.</span></span>

<span data-ttu-id="5893b-199">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="5893b-199">The default value is Default.</span></span>

<span data-ttu-id="5893b-200">Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="5893b-200">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in the MSDN library.</span></span>

<span data-ttu-id="5893b-201">Cuidado: a autenticação do Credential Security Support Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="5893b-201">CAUTION: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="5893b-202">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="5893b-202">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="5893b-203">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="5893b-203">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="5893b-204">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5893b-204">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5893b-205">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="5893b-205">-CertificateThumbprint</span></span>

<span data-ttu-id="5893b-206">Especifica o certificado de chave pública digital (X509) de uma conta de usuário que tem permissão para criar a sessão na qual o `Get-PSSession` comando é executado.</span><span class="sxs-lookup"><span data-stu-id="5893b-206">Specifies the digital public key certificate (X509) of a user account that has permission to create the session in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="5893b-207">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="5893b-207">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="5893b-208">Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **ComputerName** ou **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="5893b-208">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="5893b-209">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="5893b-209">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="5893b-210">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="5893b-210">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="5893b-211">Para obter uma impressão digital do certificado, use um comando Get-Item ou Get-ChildItem na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="5893b-211">To get a certificate thumbprint, use a Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

<span data-ttu-id="5893b-212">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5893b-212">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5893b-213">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="5893b-213">-ComputerName</span></span>

<span data-ttu-id="5893b-214">Especifica uma matriz de nomes de computadores.</span><span class="sxs-lookup"><span data-stu-id="5893b-214">Specifies an array of names of computers.</span></span> <span data-ttu-id="5893b-215">Obtém as sessões que conectam a computadores especificados.</span><span class="sxs-lookup"><span data-stu-id="5893b-215">Gets the sessions that connect to the specified computers.</span></span>
<span data-ttu-id="5893b-216">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5893b-216">Wildcard characters are not permitted.</span></span> <span data-ttu-id="5893b-217">Nenhum valor padrão.</span><span class="sxs-lookup"><span data-stu-id="5893b-217">There is no default value.</span></span>

<span data-ttu-id="5893b-218">A partir do Windows PowerShell 3,0, os objetos **PSSession** são armazenados nos computadores na extremidade remota de cada conexão.</span><span class="sxs-lookup"><span data-stu-id="5893b-218">Beginning in Windows PowerShell 3.0, **PSSession** objects are stored on the computers at the remote end of each connection.</span></span> <span data-ttu-id="5893b-219">Para obter as sessões nos computadores especificados, o PowerShell cria uma conexão temporária com cada computador e executa um `Get-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="5893b-219">To get the sessions on the specified computers, PowerShell creates a temporary connection to each computer and runs a `Get-PSSession` command.</span></span>

<span data-ttu-id="5893b-220">Digite o nome de NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um ou mais computadores.</span><span class="sxs-lookup"><span data-stu-id="5893b-220">Type the NetBIOS name, an IP address, or a fully-qualified domain name of one or more computers.</span></span> <span data-ttu-id="5893b-221">Para especificar o computador local, digite o nome do computador, localhost ou um ponto (.).</span><span class="sxs-lookup"><span data-stu-id="5893b-221">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span>

<span data-ttu-id="5893b-222">Observação: esse parâmetro Obtém sessões somente de computadores que executam o Windows PowerShell 3,0 ou versões posteriores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5893b-222">Note: This parameter gets sessions only from computers that run Windows PowerShell 3.0 or later versions of PowerShell.</span></span> <span data-ttu-id="5893b-223">Versões anteriores não armazenam sessões.</span><span class="sxs-lookup"><span data-stu-id="5893b-223">Earlier versions do not store sessions.</span></span>

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

### <span data-ttu-id="5893b-224">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="5893b-224">-ConfigurationName</span></span>

<span data-ttu-id="5893b-225">Especifica o nome de uma configuração.</span><span class="sxs-lookup"><span data-stu-id="5893b-225">Specifies the name of a configuration.</span></span> <span data-ttu-id="5893b-226">Esse cmdlet obtém somente as sessões que usam a configuração de sessão especificada.</span><span class="sxs-lookup"><span data-stu-id="5893b-226">This cmdlet gets only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="5893b-227">Insira um nome de configuração ou o URI do recurso totalmente qualificado para uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-227">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="5893b-228">Se você especificar apenas o nome da configuração, o seguinte URI de esquema será anexado: `http://schemas.microsoft.com/powershell` .</span><span class="sxs-lookup"><span data-stu-id="5893b-228">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span> <span data-ttu-id="5893b-229">O nome de configuração de uma sessão é armazenado na propriedade **ConfigurationName** da sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-229">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="5893b-230">O valor desse parâmetro é usado para selecionar e filtrar sessões.</span><span class="sxs-lookup"><span data-stu-id="5893b-230">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="5893b-231">Ele não altera a configuração de sessão utilizada pela sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-231">It does not change the session configuration that the session uses.</span></span>

<span data-ttu-id="5893b-232">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="5893b-232">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

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

### <span data-ttu-id="5893b-233">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="5893b-233">-ConnectionUri</span></span>

<span data-ttu-id="5893b-234">Especifica um URI que define o ponto de extremidade de conexão para a sessão temporária na qual o `Get-PSSession` comando é executado.</span><span class="sxs-lookup"><span data-stu-id="5893b-234">Specifies a URI that defines the connection endpoint for the temporary session in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="5893b-235">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="5893b-235">The URI must be fully qualified.</span></span>

<span data-ttu-id="5893b-236">Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="5893b-236">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ConnectionUri** parameter.</span></span>

<span data-ttu-id="5893b-237">O formato dessa cadeia de caracteres é:</span><span class="sxs-lookup"><span data-stu-id="5893b-237">The format of this string is:</span></span>

`<Transport>://<ComputerName>:<Port\>/<ApplicationName>`

<span data-ttu-id="5893b-238">O valor padrão é: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="5893b-238">The default value is: `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="5893b-239">Se você não especificar um **conexãouri** , poderá usar os parâmetros **UseSSL** , **ComputerName** , **Port** e **ApplicationName** para especificar os valores de **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="5893b-239">If you do not specify a **ConnectionUri** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span> <span data-ttu-id="5893b-240">Os valores válidos para o segmento Transport do URI são HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5893b-240">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="5893b-241">Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada com portas de padrões: 80 para HTTP e 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5893b-241">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="5893b-242">Para usar as portas padrão para comunicação remota do PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5893b-242">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="5893b-243">Se o computador de destino redireciona a conexão para um URI diferente, o PowerShell impede o redirecionamento, a menos que você use o parâmetro **AllowRedirection** no comando.</span><span class="sxs-lookup"><span data-stu-id="5893b-243">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

<span data-ttu-id="5893b-244">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5893b-244">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="5893b-245">Esse parâmetro Obtém sessões somente de computadores que executam o Windows PowerShell 3,0 ou versões posteriores do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5893b-245">This parameter gets sessions only from computers that run Windows PowerShell 3.0 or later versions of Windows PowerShell.</span></span> <span data-ttu-id="5893b-246">Versões anteriores não armazenam sessões.</span><span class="sxs-lookup"><span data-stu-id="5893b-246">Earlier versions do not store sessions.</span></span>

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

### <span data-ttu-id="5893b-247">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="5893b-247">-ContainerId</span></span>

<span data-ttu-id="5893b-248">Especifica uma matriz de IDs de contêineres.</span><span class="sxs-lookup"><span data-stu-id="5893b-248">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="5893b-249">Esse cmdlet inicia uma sessão interativa com cada um dos contêineres especificados.</span><span class="sxs-lookup"><span data-stu-id="5893b-249">This cmdlet starts an interactive session with each of the specified containers.</span></span> <span data-ttu-id="5893b-250">Use o `docker ps` comando para obter uma lista de IDs de contêiner.</span><span class="sxs-lookup"><span data-stu-id="5893b-250">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="5893b-251">Para obter mais informações, consulte a ajuda para o comando [Docker PS](https://docs.docker.com/engine/reference/commandline/ps/) .</span><span class="sxs-lookup"><span data-stu-id="5893b-251">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

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

### <span data-ttu-id="5893b-252">-Credential</span><span class="sxs-lookup"><span data-stu-id="5893b-252">-Credential</span></span>

<span data-ttu-id="5893b-253">Especifica uma credencial de usuário.</span><span class="sxs-lookup"><span data-stu-id="5893b-253">Specifies a user credential.</span></span> <span data-ttu-id="5893b-254">Esse cmdlet executa o comando com as permissões do usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="5893b-254">This cmdlet runs the command with the permissions of the specified user.</span></span> <span data-ttu-id="5893b-255">Especifique uma conta de usuário que tenha permissão para se conectar ao computador remoto e executar um `Get-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="5893b-255">Specify a user account that has permission to connect to the remote computer and run a `Get-PSSession` command.</span></span> <span data-ttu-id="5893b-256">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="5893b-256">The default is the current user.</span></span>

<span data-ttu-id="5893b-257">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5893b-257">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="5893b-258">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="5893b-258">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="5893b-259">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="5893b-259">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="5893b-260">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="5893b-260">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

<span data-ttu-id="5893b-261">Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **ComputerName** ou **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="5893b-261">This parameter configures to the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="5893b-262">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5893b-262">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5893b-263">-Id</span><span class="sxs-lookup"><span data-stu-id="5893b-263">-Id</span></span>

<span data-ttu-id="5893b-264">Especifica uma matriz de IDs de sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-264">Specifies an array of session IDs.</span></span> <span data-ttu-id="5893b-265">Esse cmdlet obtém apenas as sessões com as IDs especificadas.</span><span class="sxs-lookup"><span data-stu-id="5893b-265">This cmdlet gets only the sessions with the specified IDs.</span></span> <span data-ttu-id="5893b-266">Digite uma ou mais IDs, separadas por vírgulas, ou use o operador de intervalo (..) para especificar um intervalo de IDs.</span><span class="sxs-lookup"><span data-stu-id="5893b-266">Type one or more IDs, separated by commas, or use the range operator (..) to specify a range of IDs.</span></span> <span data-ttu-id="5893b-267">Você não pode usar o parâmetro ID junto com o parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="5893b-267">You cannot use the ID parameter together with the **ComputerName** parameter.</span></span>

<span data-ttu-id="5893b-268">Uma ID é um inteiro que identifica exclusivamente as sessões gerenciadas pelo usuário na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5893b-268">An ID is an integer that uniquely identifies the user-managed sessions in the current session.</span></span> <span data-ttu-id="5893b-269">É mais fácil lembrar e digitar do que a **InstanceId** , mas só é exclusiva na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5893b-269">It is easier to remember and type than the **InstanceId** , but it is unique only within the current session.</span></span> <span data-ttu-id="5893b-270">A ID de uma sessão é armazenada na propriedade ID da sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-270">The ID of a session is stored in the ID property of the session.</span></span>

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

### <span data-ttu-id="5893b-271">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="5893b-271">-InstanceId</span></span>

<span data-ttu-id="5893b-272">Especifica uma matriz de IDs de instância de sessões.</span><span class="sxs-lookup"><span data-stu-id="5893b-272">Specifies an array of instance IDs of sessions.</span></span> <span data-ttu-id="5893b-273">Esse cmdlet obtém apenas as sessões com as IDs de instância especificadas.</span><span class="sxs-lookup"><span data-stu-id="5893b-273">This cmdlet gets only the sessions with the specified instance IDs.</span></span>

<span data-ttu-id="5893b-274">A ID de instância é um GUID que identifica exclusivamente uma sessão em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="5893b-274">The instance ID is a GUID that uniquely identifies a session on a local or remote computer.</span></span> <span data-ttu-id="5893b-275">A **InstanceId** é exclusiva, mesmo quando você tem várias sessões em execução no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5893b-275">The **InstanceID** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="5893b-276">A ID de instância de uma sessão é armazenada na propriedade **InstanceID** da sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-276">The instance ID of a session is stored in the **InstanceID** property of the session.</span></span>

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

### <span data-ttu-id="5893b-277">-Name</span><span class="sxs-lookup"><span data-stu-id="5893b-277">-Name</span></span>

<span data-ttu-id="5893b-278">Especifica uma matriz de nomes de sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-278">Specifies an array of session names.</span></span> <span data-ttu-id="5893b-279">Esse cmdlet obtém apenas as sessões que têm os nomes amigáveis especificados.</span><span class="sxs-lookup"><span data-stu-id="5893b-279">This cmdlet gets only the sessions that have the specified friendly names.</span></span> <span data-ttu-id="5893b-280">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5893b-280">Wildcard characters are permitted.</span></span>

<span data-ttu-id="5893b-281">O nome amigável de uma sessão é armazenado na propriedade **Name** da sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-281">The friendly name of a session is stored in the **Name** property of the session.</span></span>

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

### <span data-ttu-id="5893b-282">-Port</span><span class="sxs-lookup"><span data-stu-id="5893b-282">-Port</span></span>

<span data-ttu-id="5893b-283">Especifica a porta de rede especificada que é usada para a conexão temporária na qual o `Get-PSSession` comando é executado.</span><span class="sxs-lookup"><span data-stu-id="5893b-283">Specifies the specified network port that is used for the temporary connection in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="5893b-284">Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão.</span><span class="sxs-lookup"><span data-stu-id="5893b-284">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="5893b-285">As portas padrão são 5985, que é a porta do WinRM para HTTP e 5986, que é a porta do WinRM para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5893b-285">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="5893b-286">Antes de usar uma porta alternativa, você deve configurar o ouvinte de WinRM no computador remoto para escutar na porta.</span><span class="sxs-lookup"><span data-stu-id="5893b-286">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="5893b-287">Para configurar o ouvinte, digite os dois comandos a seguir no prompt do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5893b-287">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="5893b-288">Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **ComputerName** ou **conexãouri** .</span><span class="sxs-lookup"><span data-stu-id="5893b-288">This parameter configures to the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="5893b-289">Não use o parâmetro **Port** a menos que seja necessário.</span><span class="sxs-lookup"><span data-stu-id="5893b-289">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="5893b-290">A **porta** definida no comando aplica-se a todos os computadores ou sessões em que o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="5893b-290">The **Port** set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="5893b-291">Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="5893b-291">An alternate port setting might prevent the command from running on all computers.</span></span>

<span data-ttu-id="5893b-292">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5893b-292">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5893b-293">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="5893b-293">-SessionOption</span></span>

<span data-ttu-id="5893b-294">Especifica as opções avançadas para a sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-294">Specifies advanced options for the session.</span></span> <span data-ttu-id="5893b-295">Insira um objeto **SessionOption** , como um que você cria usando o cmdlet New-PSSessionOption ou uma tabela de hash na qual as chaves são nomes de opção de sessão e os valores são valores de opção de sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-295">Enter a **SessionOption** object, such as one that you create by using the New-PSSessionOption cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="5893b-296">Os valores padrão das opções são determinados pelo valor da variável de preferência $PSSessionOption, se definida.</span><span class="sxs-lookup"><span data-stu-id="5893b-296">The default values for the options are determined by the value of the $PSSessionOption preference variable, if it is set.</span></span> <span data-ttu-id="5893b-297">Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-297">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="5893b-298">Os valores de opção da sessão têm precedência sobre os valores padrão de sessões definidos na variável de preferência $PSSessionOption e na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-298">The session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span> <span data-ttu-id="5893b-299">No entanto, eles não têm precedência sobre valores máximos, cotas ou limites definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-299">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="5893b-300">Para obter uma descrição das opções de sessão, incluindo os valores padrão, consulte `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="5893b-300">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="5893b-301">Para obter informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="5893b-301">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="5893b-302">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="5893b-302">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

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

### <span data-ttu-id="5893b-303">-Estado</span><span class="sxs-lookup"><span data-stu-id="5893b-303">-State</span></span>

<span data-ttu-id="5893b-304">Especifica um estado de sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-304">Specifies a session state.</span></span> <span data-ttu-id="5893b-305">Este cmdlet obtém apenas sessões no estado especificado.</span><span class="sxs-lookup"><span data-stu-id="5893b-305">This cmdlet gets only sessions in the specified state.</span></span> <span data-ttu-id="5893b-306">Os valores aceitáveis para esse parâmetro são: todos, abertos, desconectados, fechados e desfeitos.</span><span class="sxs-lookup"><span data-stu-id="5893b-306">The acceptable values for this parameter are: All, Opened, Disconnected, Closed, and Broken.</span></span> <span data-ttu-id="5893b-307">O valor padrão é All.</span><span class="sxs-lookup"><span data-stu-id="5893b-307">The default value is All.</span></span>

<span data-ttu-id="5893b-308">O valor de estado de sessão é relativo à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5893b-308">The session state value is relative to the current sessions.</span></span> <span data-ttu-id="5893b-309">Sessões que não tiverem sido criadas nas sessões atuais e não estiverem conectadas à sessão atual terão um estado de Disconnected, mesmo quando estiverem conectadas a uma sessão diferente.</span><span class="sxs-lookup"><span data-stu-id="5893b-309">Sessions that were not created in the current sessions and are not connected to the current session have a state of Disconnected even when they are connected to a different session.</span></span>

<span data-ttu-id="5893b-310">O estado de uma sessão é armazenado na propriedade **State** da sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-310">The state of a session is stored in the **State** property of the session.</span></span>

<span data-ttu-id="5893b-311">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5893b-311">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5893b-312">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="5893b-312">-ThrottleLimit</span></span>

<span data-ttu-id="5893b-313">Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o `Get-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="5893b-313">Specifies the maximum number of concurrent connections that can be established to run the `Get-PSSession` command.</span></span> <span data-ttu-id="5893b-314">Se você omitir esse parâmetro ou digitar o valor 0 (zero), o valor padrão, 32, será usado.</span><span class="sxs-lookup"><span data-stu-id="5893b-314">If you omit this parameter or enter a value of 0 (zero), the default value, 32, is used.</span></span> <span data-ttu-id="5893b-315">O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="5893b-315">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

<span data-ttu-id="5893b-316">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5893b-316">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5893b-317">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="5893b-317">-UseSSL</span></span>

<span data-ttu-id="5893b-318">Indica que esse cmdlet usa o protocolo protocolo SSL (SSL) para estabelecer a conexão na qual o `Get-PSSession` comando é executado.</span><span class="sxs-lookup"><span data-stu-id="5893b-318">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish the connection in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="5893b-319">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="5893b-319">By default, SSL is not used.</span></span> <span data-ttu-id="5893b-320">Se você usar esse parâmetro e o SSL não estiver disponível na porta usada para o comando, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="5893b-320">If you use this parameter, but SSL is not available on the port used for the command, the command fails.</span></span>

<span data-ttu-id="5893b-321">Esse parâmetro configura a conexão temporária que é criada para executar um `Get-PSSession` comando com o parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="5893b-321">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** parameter.</span></span>

<span data-ttu-id="5893b-322">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5893b-322">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5893b-323">-VMId</span><span class="sxs-lookup"><span data-stu-id="5893b-323">-VMId</span></span>

<span data-ttu-id="5893b-324">Especifica uma matriz de ID de máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="5893b-324">Specifies an array of ID of virtual machines.</span></span> <span data-ttu-id="5893b-325">Esse cmdlet inicia uma sessão interativa com cada uma das máquinas virtuais especificadas.</span><span class="sxs-lookup"><span data-stu-id="5893b-325">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="5893b-326">Para ver as máquinas virtuais que estão disponíveis para você, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="5893b-326">To see the virtual machines that are available to you, use the following command:</span></span>

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

### <span data-ttu-id="5893b-327">-VMName</span><span class="sxs-lookup"><span data-stu-id="5893b-327">-VMName</span></span>

<span data-ttu-id="5893b-328">Especifica uma matriz de nomes de máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="5893b-328">Specifies an array of names of virtual machines.</span></span> <span data-ttu-id="5893b-329">Esse cmdlet inicia uma sessão interativa com cada uma das máquinas virtuais especificadas.</span><span class="sxs-lookup"><span data-stu-id="5893b-329">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="5893b-330">Para ver as máquinas virtuais que estão disponíveis para você, use o `Get-VM` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5893b-330">To see the virtual machines that are available to you, use the `Get-VM` cmdlet.</span></span>

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

### <span data-ttu-id="5893b-331">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5893b-331">CommonParameters</span></span>

<span data-ttu-id="5893b-332">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5893b-332">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5893b-333">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5893b-333">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5893b-334">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5893b-334">INPUTS</span></span>

### <span data-ttu-id="5893b-335">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5893b-335">None</span></span>

<span data-ttu-id="5893b-336">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5893b-336">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="5893b-337">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5893b-337">OUTPUTS</span></span>

### <span data-ttu-id="5893b-338">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="5893b-338">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="5893b-339">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5893b-339">NOTES</span></span>

- <span data-ttu-id="5893b-340">Esse cmdlet obtém objetos **PSSession** de sessões gerenciadas pelo usuário "como aquelas criadas usando os cmdlets New-PSSession, `Enter-PSSession` e Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="5893b-340">This cmdlet gets user-managed sessions **PSSession** objects" such as those that are created by using the New-PSSession, `Enter-PSSession`, and Invoke-Command cmdlets.</span></span> <span data-ttu-id="5893b-341">Ele não obtém a sessão gerenciada pelo sistema que é criada quando você inicia o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5893b-341">It does not get the system-managed session that is created when you start PowerShell.</span></span>
- <span data-ttu-id="5893b-342">A partir do Windows PowerShell 3,0, os objetos **PSSession** são armazenados no computador que está no lado do servidor ou no fim do recebimento de uma conexão.</span><span class="sxs-lookup"><span data-stu-id="5893b-342">Starting in Windows PowerShell 3.0, **PSSession** objects are stored on the computer that is at the server-side or receiving end of a connection.</span></span> <span data-ttu-id="5893b-343">Para obter as sessões armazenadas no computador local ou em um computador remoto, o PowerShell estabelece uma sessão temporária para o computador especificado e executa comandos de consulta na sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-343">To get the sessions that are stored on the local computer or a remote computer, PowerShell establishes a temporary session to the specified computer and runs query commands in the session.</span></span>
- <span data-ttu-id="5893b-344">Para obter sessões que se conectam a um computador remoto, use os parâmetros **ComputerName** ou **ConnectionUri** para especificar o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="5893b-344">To get sessions that connect to a remote computer, use the **ComputerName** or **ConnectionUri** parameters to specify the remote computer.</span></span> <span data-ttu-id="5893b-345">Para filtrar as sessões que `Get-PSSession` Obtém, use os parâmetros **Name** , **ID** , **InstanceId** e **State** .</span><span class="sxs-lookup"><span data-stu-id="5893b-345">To filter the sessions that `Get-PSSession` gets, use the **Name** , **ID** , **InstanceID** , and **State** parameters.</span></span> <span data-ttu-id="5893b-346">Use os parâmetros restantes para configurar a sessão temporária que o `Get-PSSession` usa.</span><span class="sxs-lookup"><span data-stu-id="5893b-346">Use the remaining parameters to configure the temporary session that `Get-PSSession` uses.</span></span>
- <span data-ttu-id="5893b-347">Quando você usa os parâmetros **ComputerName** ou **conexãouri** , o `Get-PSSession` obtém apenas sessões de computadores que executam o Windows PowerShell 3,0 e versões posteriores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5893b-347">When you use the **ComputerName** or **ConnectionUri** parameters, `Get-PSSession` gets only sessions from computers running Windows PowerShell 3.0 and later versions of PowerShell.</span></span>
- <span data-ttu-id="5893b-348">O valor da propriedade **State** de uma **PSSession** é relativo à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5893b-348">The value of the **State** property of a **PSSession** is relative to the current session.</span></span>
  <span data-ttu-id="5893b-349">Portanto, um valor de **desconectado** significa que a **PSSession** não está conectada à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5893b-349">Therefore, a value of **Disconnected** means that the **PSSession** is not connected to the current session.</span></span> <span data-ttu-id="5893b-350">No entanto, isso não significa que a **PSSession** seja desconectada de todas as sessões.</span><span class="sxs-lookup"><span data-stu-id="5893b-350">However, it does not mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="5893b-351">Ela pode ser conectada a uma sessão diferente.</span><span class="sxs-lookup"><span data-stu-id="5893b-351">It might be connected to a different session.</span></span> <span data-ttu-id="5893b-352">Para determinar se você pode se conectar ou reconectar-se à **PSSession** da sessão atual, use a propriedade de **disponibilidade** .</span><span class="sxs-lookup"><span data-stu-id="5893b-352">To determine whether you can connect or reconnect to the **PSSession** from the current session, use the **Availability** property.</span></span>

<span data-ttu-id="5893b-353">Um valor **Availability** de **None** indica que é possível conectar-se à sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-353">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="5893b-354">Um valor de **ocupado** indica que você não pode se conectar à **PSSession** porque ela está conectada a outra sessão.</span><span class="sxs-lookup"><span data-stu-id="5893b-354">A value of **Busy** indicates that you cannot connect to the **PSSession** because it is connected to another session.</span></span>

<span data-ttu-id="5893b-355">Para obter mais informações sobre os valores da propriedade **State** de sessões, consulte [Enumeração RunspaceState](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate).</span><span class="sxs-lookup"><span data-stu-id="5893b-355">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate).</span></span>

<span data-ttu-id="5893b-356">Para obter mais informações sobre os valores da propriedade de sessões de **disponibilidade** , consulte [Enumeração RunspaceAvailability](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="5893b-356">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="5893b-357">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5893b-357">RELATED LINKS</span></span>

[<span data-ttu-id="5893b-358">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="5893b-358">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="5893b-359">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="5893b-359">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="5893b-360">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="5893b-360">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="5893b-361">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="5893b-361">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="5893b-362">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="5893b-362">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="5893b-363">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="5893b-363">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="5893b-364">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="5893b-364">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="5893b-365">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="5893b-365">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="5893b-366">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="5893b-366">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="5893b-367">about_Remote</span><span class="sxs-lookup"><span data-stu-id="5893b-367">about_Remote</span></span>](About/about_Remote.md)

