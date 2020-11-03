---
description: Descreve sessões do PowerShell (PSSessions) e explica como estabelecer uma conexão persistente com um computador remoto.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssessions?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSessions
ms.openlocfilehash: c3221254b3688bb974214c0b6b45f10fcd848bec
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196288"
---
# <a name="about-pssessions"></a><span data-ttu-id="f8179-104">Sobre PSSessions</span><span class="sxs-lookup"><span data-stu-id="f8179-104">About PSSessions</span></span>

## <a name="short-description"></a><span data-ttu-id="f8179-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="f8179-105">Short Description</span></span>
<span data-ttu-id="f8179-106">Descreve sessões do PowerShell (PSSessions) e explica como estabelecer uma conexão persistente com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f8179-106">Describes PowerShell sessions (PSSessions) and explains how to establish a persistent connection to a remote computer.</span></span>

## <a name="long-description"></a><span data-ttu-id="f8179-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="f8179-107">Long Description</span></span>

<span data-ttu-id="f8179-108">Para executar comandos do PowerShell em um computador remoto, você pode usar o parâmetro **ComputerName** de um cmdlet ou pode criar uma sessão do PowerShell (PSSession) e executar comandos na PSSession.</span><span class="sxs-lookup"><span data-stu-id="f8179-108">To run PowerShell commands on a remote computer, you can use the **ComputerName** parameter of a cmdlet, or you can create a PowerShell session (PSSession) and run commands in the PSSession.</span></span>

<span data-ttu-id="f8179-109">Quando você cria uma PSSession, o PowerShell estabelece uma conexão persistente com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f8179-109">When you create a PSSession, PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="f8179-110">Use uma PSSession para executar uma série de comandos relacionados em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f8179-110">Use a PSSession to run a series of related commands on a remote computer.</span></span> <span data-ttu-id="f8179-111">Os comandos que são executados na mesma PSSession podem compartilhar dados, como os valores de variáveis, aliases e funções.</span><span class="sxs-lookup"><span data-stu-id="f8179-111">Commands that run in the same PSSession can share data, such as the values of variables, aliases, and functions.</span></span>

<span data-ttu-id="f8179-112">Você também pode criar uma PSSession no computador local e executar comandos nela.</span><span class="sxs-lookup"><span data-stu-id="f8179-112">You can also create a PSSession on the local computer and run commands in it.</span></span>
<span data-ttu-id="f8179-113">Uma PSSession local usa a infraestrutura de comunicação remota do PowerShell para criar e manter a PSSession.</span><span class="sxs-lookup"><span data-stu-id="f8179-113">A local PSSession uses the PowerShell remoting infrastructure to create and maintain the PSSession.</span></span>

<span data-ttu-id="f8179-114">A partir do Windows PowerShell 3,0, as PSSessions são independentes das sessões nas quais elas são criadas.</span><span class="sxs-lookup"><span data-stu-id="f8179-114">Beginning in Windows PowerShell 3.0, PSSessions are independent of the sessions in which they are created.</span></span> <span data-ttu-id="f8179-115">As PSSessions ativas são mantidas no computador remoto (ou no computador na extremidade remota ou no "lado do servidor" da conexão).</span><span class="sxs-lookup"><span data-stu-id="f8179-115">Active PSSessions are maintained on the remote computer (or the computer at the remote end or "server-side" of the connection).</span></span> <span data-ttu-id="f8179-116">Como resultado, você pode se desconectar da PSSession e se reconectar a ela mais tarde, a partir do mesmo computador ou de um computador diferente.</span><span class="sxs-lookup"><span data-stu-id="f8179-116">As a result, you can disconnect from the PSSession and reconnect to it at a later time from the same computer or from a different computer.</span></span>

<span data-ttu-id="f8179-117">Este tópico explica como criar, usar, obter e excluir PSSessions.</span><span class="sxs-lookup"><span data-stu-id="f8179-117">This topic explains how to create, use, get, and delete PSSessions.</span></span> <span data-ttu-id="f8179-118">Para obter informações mais avançadas, consulte [about_PSSession_Details](about_PSSession_Details.md).</span><span class="sxs-lookup"><span data-stu-id="f8179-118">For more advanced information, see [about_PSSession_Details](about_PSSession_Details.md).</span></span>

<span data-ttu-id="f8179-119">Observação: as PSSessions usam a infraestrutura de comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8179-119">Note: PSSessions use the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="f8179-120">Para usar PSSessions, os computadores locais e remotos devem ser configurados para comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="f8179-120">To use PSSessions, the local and remote computers must be configured for remoting.</span></span>
<span data-ttu-id="f8179-121">Para obter mais informações, consulte [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8179-121">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

<span data-ttu-id="f8179-122">No Windows Vista e versões posteriores do Windows, para criar uma PSSession em um computador local, você deve iniciar o PowerShell com a opção "executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="f8179-122">In Windows Vista and later versions of Windows, to create a PSSession on a local computer, you must start PowerShell with the "Run as administrator" option.</span></span>

## <a name="what-is-a-session"></a><span data-ttu-id="f8179-123">O que é uma sessão?</span><span class="sxs-lookup"><span data-stu-id="f8179-123">What Is a Session?</span></span>

<span data-ttu-id="f8179-124">Uma sessão é um ambiente no qual o PowerShell é executado.</span><span class="sxs-lookup"><span data-stu-id="f8179-124">A session is an environment in which PowerShell runs.</span></span>

<span data-ttu-id="f8179-125">Cada vez que você inicia o PowerShell, uma sessão é criada para você e você pode executar comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="f8179-125">Each time you start PowerShell, a session is created for you, and you can run commands in the session.</span></span> <span data-ttu-id="f8179-126">Você também pode adicionar itens à sua sessão, como módulos e snap-ins, e pode criar itens, como variáveis, funções e aliases.</span><span class="sxs-lookup"><span data-stu-id="f8179-126">You can also add items to your session, such as modules and snap-ins, and you can create items, such as variables, functions, and aliases.</span></span> <span data-ttu-id="f8179-127">Esses itens existem somente na sessão e são excluídos quando a sessão termina.</span><span class="sxs-lookup"><span data-stu-id="f8179-127">These items exist only in the session and are deleted when the session ends.</span></span>

<span data-ttu-id="f8179-128">Você também pode criar sessões gerenciadas pelo usuário, conhecidas como "sessões do PowerShell" ou "PSSessions", no computador local ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f8179-128">You can also create user-managed sessions, known as " PowerShell sessions" or "PSSessions," on the local computer or on a remote computer.</span></span> <span data-ttu-id="f8179-129">Assim como a sessão padrão, você pode executar comandos em uma PSSession e adicionar e criar itens.</span><span class="sxs-lookup"><span data-stu-id="f8179-129">Like the default session, you can run commands in a PSSession and add and create items.</span></span> <span data-ttu-id="f8179-130">No entanto, diferentemente da sessão que é iniciada automaticamente, você pode controlar as PSSessions criadas por você.</span><span class="sxs-lookup"><span data-stu-id="f8179-130">However, unlike the session that starts automatically, you can control the PSSessions that you create.</span></span> <span data-ttu-id="f8179-131">Você pode obter, criar, configurar e removê-los, desconectar-se e reconectá-los e executar vários comandos na mesma PSSession.</span><span class="sxs-lookup"><span data-stu-id="f8179-131">You can get, create, configure, and remove them, disconnect and reconnect to them, and run multiple commands in the same PSSession.</span></span> <span data-ttu-id="f8179-132">A PSSession permanece disponível até você excluí-la ou expirar.</span><span class="sxs-lookup"><span data-stu-id="f8179-132">The PSSession remains available until you delete it or it times out.</span></span>

<span data-ttu-id="f8179-133">Normalmente, você cria uma PSSession para executar uma série de comandos relacionados em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f8179-133">Typically, you create a PSSession to run a series of related commands on a remote computer.</span></span> <span data-ttu-id="f8179-134">Quando você cria uma PSSession em um computador remoto, o PowerShell estabelece uma conexão persistente com o computador remoto para dar suporte à sessão.</span><span class="sxs-lookup"><span data-stu-id="f8179-134">When you create a PSSession on a remote computer, PowerShell establishes a persistent connection to the remote computer to support the session.</span></span>

<span data-ttu-id="f8179-135">Se você usar o parâmetro **ComputerName** do `Invoke-Command` `Enter-PSSession` cmdlet ou para executar um comando remoto ou para iniciar uma sessão interativa, o PowerShell criará uma sessão temporária no computador remoto e fechará a sessão assim que o comando for concluído ou assim que a sessão interativa terminar.</span><span class="sxs-lookup"><span data-stu-id="f8179-135">If you use the **ComputerName** parameter of the `Invoke-Command` or `Enter-PSSession` cmdlet to run a remote command or to start an interactive session, PowerShell creates a temporary session on the remote computer and closes the session as soon as the command is complete or as soon as the interactive session ends.</span></span> <span data-ttu-id="f8179-136">Você não pode controlar essas sessões temporárias e não pode usá-las para mais de um único comando ou uma única sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="f8179-136">You cannot control these temporary sessions, and you cannot use them for more than a single command or a single interactive session.</span></span>

<span data-ttu-id="f8179-137">No PowerShell, a "sessão atual" é a sessão na qual você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="f8179-137">In PowerShell, the "current session" is the session that you are working in.</span></span> <span data-ttu-id="f8179-138">A "sessão atual" pode se referir a qualquer sessão, incluindo uma sessão temporária ou uma PSSession.</span><span class="sxs-lookup"><span data-stu-id="f8179-138">The "current session" can refer to any session, including a temporary session or a PSSession.</span></span>

## <a name="why-use-a-pssession"></a><span data-ttu-id="f8179-139">Por que usar uma PSSession?</span><span class="sxs-lookup"><span data-stu-id="f8179-139">Why Use a PSSession?</span></span>

<span data-ttu-id="f8179-140">Use uma PSSession quando precisar de uma conexão persistente com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f8179-140">Use a PSSession when you need a persistent connection to a remote computer.</span></span>
<span data-ttu-id="f8179-141">Com uma PSSession, você pode executar uma série de comandos que compartilham dados, como o valor de variáveis, o conteúdo de uma função ou a definição de um alias.</span><span class="sxs-lookup"><span data-stu-id="f8179-141">With a PSSession, you can run a series of commands that share data, such as the value of variables, the contents of a function, or the definition of an alias.</span></span>

<span data-ttu-id="f8179-142">Você pode executar comandos remotos sem criar uma PSSession.</span><span class="sxs-lookup"><span data-stu-id="f8179-142">You can run remote commands without creating a PSSession.</span></span> <span data-ttu-id="f8179-143">Use o parâmetro **ComputerName** de cmdlets habilitados para remoto para executar um único comando ou uma série de comandos não relacionados em um ou vários computadores.</span><span class="sxs-lookup"><span data-stu-id="f8179-143">Use the **ComputerName** parameter of remote-enabled cmdlets to run a single command or a series of unrelated commands on one or many computers.</span></span>

<span data-ttu-id="f8179-144">Quando você usa o parâmetro **ComputerName** do `Invoke-Command` ou, o `Enter-PSSession` PowerShell estabelece uma conexão temporária com o computador remoto e fecha a conexão assim que o comando é concluído.</span><span class="sxs-lookup"><span data-stu-id="f8179-144">When you use the **ComputerName** parameter of `Invoke-Command` or `Enter-PSSession`, PowerShell establishes a temporary connection to the remote computer and then closes the connection as soon as the command is complete.</span></span> <span data-ttu-id="f8179-145">Todos os elementos de dados que você criar serão perdidos quando a conexão for fechada.</span><span class="sxs-lookup"><span data-stu-id="f8179-145">Any data elements that you create are lost when the connection is closed.</span></span>

<span data-ttu-id="f8179-146">Outros cmdlets que têm um parâmetro **ComputerName** , como `Get-Eventlog` e `Get-WmiObject` , usam tecnologias de comunicação remota diferentes para coletar dados.</span><span class="sxs-lookup"><span data-stu-id="f8179-146">Other cmdlets that have a **ComputerName** parameter, such as `Get-Eventlog` and `Get-WmiObject`, use different remoting technologies to gather data.</span></span> <span data-ttu-id="f8179-147">Nenhum crie uma conexão persistente como uma PSSession.</span><span class="sxs-lookup"><span data-stu-id="f8179-147">None create a persistent connection like a PSSession.</span></span>

## <a name="how-to-create-a-pssession"></a><span data-ttu-id="f8179-148">Como criar uma PSSession</span><span class="sxs-lookup"><span data-stu-id="f8179-148">How to Create a PSSession</span></span>

<span data-ttu-id="f8179-149">Para criar uma PSSession, use o `New-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f8179-149">To create a PSSession, use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="f8179-150">Para criar a PSSession em um computador remoto, use o parâmetro **ComputerName** do `New-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f8179-150">To create the PSSession on a remote computer, use the **ComputerName** parameter of the `New-PSSession` cmdlet.</span></span>

<span data-ttu-id="f8179-151">Por exemplo, o comando a seguir cria uma nova PSSession no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="f8179-151">For example, the following command creates a new PSSession on the Server01 computer.</span></span>

```powershell
New-PSSession -ComputerName Server01
```

<span data-ttu-id="f8179-152">Quando você envia o comando, `New-PSSession` o cria a PSSession e retorna um objeto que representa a PSSession.</span><span class="sxs-lookup"><span data-stu-id="f8179-152">When you submit the command, `New-PSSession` creates the PSSession and returns an object that represents the PSSession.</span></span> <span data-ttu-id="f8179-153">Você pode salvar o objeto em uma variável ao criar a PSSession ou pode usar um `Get-PSSession` comando para obter a PSSession posteriormente.</span><span class="sxs-lookup"><span data-stu-id="f8179-153">You can save the object in a variable when you create the PSSession, or you can use a `Get-PSSession` command to get the PSSession at a later time.</span></span>

<span data-ttu-id="f8179-154">Por exemplo, o comando a seguir cria uma nova PSSession no computador Server01 e salva o objeto resultante na variável $ps.</span><span class="sxs-lookup"><span data-stu-id="f8179-154">For example, the following command creates a new PSSession on the Server01 computer and saves the resulting object in the $ps variable.</span></span>

```powershell
$ps = New-PSSession -ComputerName Server01
```

## <a name="how-to-create-pssessions-on-multiple-computers"></a><span data-ttu-id="f8179-155">Como criar PSSessions em vários computadores</span><span class="sxs-lookup"><span data-stu-id="f8179-155">How to Create PSSessions on Multiple Computers</span></span>

<span data-ttu-id="f8179-156">Para criar PSSessions em vários computadores, use o parâmetro **ComputerName** do `New-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f8179-156">To create PSSessions on multiple computers, use the **ComputerName** parameter of the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="f8179-157">Digite os nomes dos computadores remotos em uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="f8179-157">Type the names of the remote computers in a comma-separated list.</span></span>

<span data-ttu-id="f8179-158">Por exemplo, para criar PSSessions nos computadores Server01, Server02 e Server03, digite:</span><span class="sxs-lookup"><span data-stu-id="f8179-158">For example, to create PSSessions on the Server01, Server02, and Server03 computers, type:</span></span>

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
```

<span data-ttu-id="f8179-159">`New-PSSession` Cria uma PSSession em cada um dos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="f8179-159">`New-PSSession` creates one PSSession on each of the remote computers.</span></span>

## <a name="how-to-get-pssessions"></a><span data-ttu-id="f8179-160">Como obter PSSessions</span><span class="sxs-lookup"><span data-stu-id="f8179-160">How to Get PSSessions</span></span>

<span data-ttu-id="f8179-161">Para obter as PSSessions que foram criadas na sessão atual, use o `Get-PSSession` cmdlet sem o parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="f8179-161">To get the PSSessions that were created in your current session, use the `Get-PSSession` cmdlet without the **ComputerName** parameter.</span></span> <span data-ttu-id="f8179-162">`Get-PSSession` Retorna o mesmo tipo de objeto que `New-PSSession` retorna.</span><span class="sxs-lookup"><span data-stu-id="f8179-162">`Get-PSSession` returns the same type of object that `New-PSSession` returns.</span></span>

<span data-ttu-id="f8179-163">O comando a seguir obtém todas as PSSessions que foram criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f8179-163">The following command gets all the PSSessions that were created in the current session.</span></span>

```powershell
Get-PSSession
```

<span data-ttu-id="f8179-164">A exibição padrão de PSSessions mostra sua ID e um nome de exibição padrão.</span><span class="sxs-lookup"><span data-stu-id="f8179-164">The default display of the PSSessions shows their ID and a default display name.</span></span> <span data-ttu-id="f8179-165">Você pode atribuir um nome de exibição alternativo ao criar a sessão.</span><span class="sxs-lookup"><span data-stu-id="f8179-165">You can assign an alternate display name when you create the session.</span></span>

```output
Id   Name       ComputerName    State    ConfigurationName
---  ----       ------------    -----    ---------------------
1    Session1   Server01        Opened   Microsoft.PowerShell
2    Session2   Server02        Opened   Microsoft.PowerShell
3    Session3   Server03        Opened   Microsoft.PowerShell
```

<span data-ttu-id="f8179-166">Você também pode salvar as PSSessions em uma variável.</span><span class="sxs-lookup"><span data-stu-id="f8179-166">You can also save the PSSessions in a variable.</span></span> <span data-ttu-id="f8179-167">O comando a seguir obtém as PSSessions e as salva na \$ variável ps123.</span><span class="sxs-lookup"><span data-stu-id="f8179-167">The following command gets the PSSessions and saves them in the \$ps123 variable.</span></span>

```powershell
$ps123 = Get-PSSession
```

<span data-ttu-id="f8179-168">Ao usar os cmdlets de PSSession, você pode se referir a uma PSSession por sua ID, por seu nome ou por sua ID de instância (um GUID).</span><span class="sxs-lookup"><span data-stu-id="f8179-168">When using the PSSession cmdlets, you can refer to a PSSession by its ID, by its name, or by its instance ID (a GUID).</span></span> <span data-ttu-id="f8179-169">O comando a seguir obtém uma PSSession por sua ID e a salva na \$ variável PS01.</span><span class="sxs-lookup"><span data-stu-id="f8179-169">The following command gets a PSSession by its ID and saves it in the \$ps01 variable.</span></span>

```powershell
$ps01 = Get-PSSession -Id 1
```

<span data-ttu-id="f8179-170">A partir do Windows PowerShell 3,0, as PSSessions são mantidas no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f8179-170">Beginning in Windows PowerShell 3.0, PSSessions are maintained on the remote computer.</span></span> <span data-ttu-id="f8179-171">Para obter as PSSessions que você criou em computadores remotos específicos, use o parâmetro **ComputerName** do `Get-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f8179-171">To get PSSessions that you created on particular remote computers, use the **ComputerName** parameter of the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="f8179-172">O comando a seguir obtém as PSSessions que você criou no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="f8179-172">The following command gets the PSSessions that you created on the Server01 remote computer.</span></span> <span data-ttu-id="f8179-173">Isso inclui PSSessions criadas na sessão atual e em outras sessões no computador local ou em outros computadores.</span><span class="sxs-lookup"><span data-stu-id="f8179-173">This includes PSSessions created in the current session and in other sessions on the local computer or other computers.</span></span>

```powershell
Get-PSSession -ComputerName Server01
```

<span data-ttu-id="f8179-174">No Windows PowerShell 2,0, `Get-PSSession` obtém somente as PSSessions que foram criadas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f8179-174">In Windows PowerShell 2.0, `Get-PSSession` gets only the PSSessions that were created in the current session.</span></span> <span data-ttu-id="f8179-175">Ele não obtém PSSessions que foram criadas em outras sessões ou em outros computadores, mesmo que as sessões estejam conectadas ao e estejam executando comandos no computador local.</span><span class="sxs-lookup"><span data-stu-id="f8179-175">It does not get PSSessions that were created in other sessions or on other computers, even if the sessions are connected to and are running commands on the local computer.</span></span>

## <a name="how-to-run-commands-in-a-pssession"></a><span data-ttu-id="f8179-176">Como executar comandos em uma PSSession</span><span class="sxs-lookup"><span data-stu-id="f8179-176">How to Run Commands in a PSSession</span></span>

<span data-ttu-id="f8179-177">Para executar um comando em uma ou mais PSSessions, use o `Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f8179-177">To run a command in one or more PSSessions, use the `Invoke-Command` cmdlet.</span></span>
<span data-ttu-id="f8179-178">Use o parâmetro Session para especificar as PSSessions e o parâmetro **scriptblock** para especificar o comando.</span><span class="sxs-lookup"><span data-stu-id="f8179-178">Use the Session parameter to specify the PSSessions and the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="f8179-179">Por exemplo, para executar um `Get-ChildItem` comando ("dir") em cada uma das três PSSessions salvas na variável $ps 123, digite:</span><span class="sxs-lookup"><span data-stu-id="f8179-179">For example, to run a `Get-ChildItem` ("dir") command in each of the three PSSessions saved in the $ps123 variable, type:</span></span>

```powershell
Invoke-Command -Session $ps123 -ScriptBlock { Get-ChildItem }
```

## <a name="how-to-delete-pssessions"></a><span data-ttu-id="f8179-180">Como excluir PSSessions</span><span class="sxs-lookup"><span data-stu-id="f8179-180">How to Delete PSSessions</span></span>

<span data-ttu-id="f8179-181">Quando você terminar com a PSSession, use o `Remove-PSSession` cmdlet para excluir a PSSession e liberar os recursos que ele estava usando.</span><span class="sxs-lookup"><span data-stu-id="f8179-181">When you are finished with the PSSession, use the `Remove-PSSession` cmdlet to delete the PSSession and to release the resources that it was using.</span></span>

```powershell
Remove-PSSession -Session $ps
```

<span data-ttu-id="f8179-182">ou</span><span class="sxs-lookup"><span data-stu-id="f8179-182">or</span></span>

```powershell
Remove-PSSession -Id 1
```

<span data-ttu-id="f8179-183">Para remover uma PSSession de um computador remoto, use o parâmetro **ComputerName** do `Remove-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f8179-183">To remove a PSSession from a remote computer, use the **ComputerName** parameter of the `Remove-PSSession` cmdlet.</span></span>

```powershell
Remove-PSSession -ComputerName Server01 -Id 1
```

<span data-ttu-id="f8179-184">Se você não excluir a PSSession, a PSSession permanecerá disponível para uso até atingir o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="f8179-184">If you do not delete the PSSession, the PSSession remains available for use until it times out.</span></span>

<span data-ttu-id="f8179-185">Você também pode usar o parâmetro **IdleTimeout** do `New-PSSessionOption` cmdlet para definir um tempo de expiração para uma PSSession ociosa.</span><span class="sxs-lookup"><span data-stu-id="f8179-185">You can also use the **IdleTimeout** parameter of the `New-PSSessionOption` cmdlet to set an expiration time for an idle PSSession.</span></span> <span data-ttu-id="f8179-186">Para obter mais informações, consulte [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="f8179-186">For more information, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

## <a name="the-pssession-cmdlets"></a><span data-ttu-id="f8179-187">Os cmdlets de PSSession</span><span class="sxs-lookup"><span data-stu-id="f8179-187">The PSSession Cmdlets</span></span>

<span data-ttu-id="f8179-188">Para obter uma lista de cmdlets PSSession, digite:</span><span class="sxs-lookup"><span data-stu-id="f8179-188">For a list of PSSession cmdlets, type:</span></span>

```powershell
Get-Help *-PSSession
```

- <span data-ttu-id="f8179-189">Connect-PSSession: conecta uma PSSession à sessão atual</span><span class="sxs-lookup"><span data-stu-id="f8179-189">Connect-PSSession: Connects a PSSession to the current session</span></span>
- <span data-ttu-id="f8179-190">Disconnect-PSSession: desconecta uma PSSession da sessão atual</span><span class="sxs-lookup"><span data-stu-id="f8179-190">Disconnect-PSSession: Disconnects a PSSession from the current session</span></span>
- <span data-ttu-id="f8179-191">Enter-PSSession: inicia uma sessão interativa</span><span class="sxs-lookup"><span data-stu-id="f8179-191">Enter-PSSession: Starts an interactive session</span></span>
- <span data-ttu-id="f8179-192">Exit-PSSession: encerra uma sessão interativa</span><span class="sxs-lookup"><span data-stu-id="f8179-192">Exit-PSSession: Ends an interactive session</span></span>
- <span data-ttu-id="f8179-193">Get-PSSession: Obtém as PSSessions na sessão atual</span><span class="sxs-lookup"><span data-stu-id="f8179-193">Get-PSSession: Gets the PSSessions in the current session</span></span>
- <span data-ttu-id="f8179-194">New-PSSession: cria uma nova PSSession em um computador local ou remoto</span><span class="sxs-lookup"><span data-stu-id="f8179-194">New-PSSession: Creates a new PSSession on a local or remote computer</span></span>
- <span data-ttu-id="f8179-195">Receive-PSSession: Obtém os resultados dos comandos que foram executados em uma sessão desconectada</span><span class="sxs-lookup"><span data-stu-id="f8179-195">Receive-PSSession: Gets the results of commands that ran in a disconnected session</span></span>
- <span data-ttu-id="f8179-196">Remove-PSSession: exclui as PSSessions na sessão atual</span><span class="sxs-lookup"><span data-stu-id="f8179-196">Remove-PSSession: Deletes the PSSessions in the current session</span></span>

## <a name="for-more-information"></a><span data-ttu-id="f8179-197">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="f8179-197">For More Information</span></span>

<span data-ttu-id="f8179-198">Para obter mais informações sobre PSSessions, consulte [about_PSSession_Details](about_PSSession_Details.md).</span><span class="sxs-lookup"><span data-stu-id="f8179-198">For more information about PSSessions, see [about_PSSession_Details](about_PSSession_Details.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f8179-199">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f8179-199">See Also</span></span>

[<span data-ttu-id="f8179-200">about_Remote</span><span class="sxs-lookup"><span data-stu-id="f8179-200">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="f8179-201">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="f8179-201">about_Remote_Disconnected_Sessions</span></span>](about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="f8179-202">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="f8179-202">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="f8179-203">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="f8179-203">Connect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Connect-PSSession)

[<span data-ttu-id="f8179-204">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="f8179-204">Disconnect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Disconnect-PSSession)

[<span data-ttu-id="f8179-205">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="f8179-205">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="f8179-206">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="f8179-206">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)

[<span data-ttu-id="f8179-207">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="f8179-207">Get-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSession)

[<span data-ttu-id="f8179-208">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="f8179-208">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="f8179-209">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="f8179-209">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="f8179-210">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="f8179-210">Remove-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Remove-PSSession)
