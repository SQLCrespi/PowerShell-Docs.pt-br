---
description: Contém perguntas e respostas sobre a execução de comandos remotos no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_faq?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_FAQ
ms.openlocfilehash: 47ef8069d0f1f179f19600057409b93fd10e1831
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196282"
---
# <a name="about-remote-faq"></a><span data-ttu-id="740f4-104">Perguntas frequentes sobre comunicação remota</span><span class="sxs-lookup"><span data-stu-id="740f4-104">About Remote FAQ</span></span>

## <a name="short-description"></a><span data-ttu-id="740f4-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="740f4-105">Short description</span></span>
<span data-ttu-id="740f4-106">Contém perguntas e respostas sobre a execução de comandos remotos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="740f4-106">Contains questions and answers about running remote commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="740f4-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="740f4-107">Long description</span></span>

<span data-ttu-id="740f4-108">Quando você trabalha remotamente, digita comandos no PowerShell em um computador (conhecido como "computador local"), mas os comandos são executados em outro computador (conhecido como "computador remoto").</span><span class="sxs-lookup"><span data-stu-id="740f4-108">When you work remotely, you type commands in PowerShell on one computer (known as the "local computer"), but the commands run on another computer (known as the "remote computer").</span></span> <span data-ttu-id="740f4-109">A experiência de trabalhar remotamente deve ser muito parecida com o trabalho diretamente no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-109">The experience of working remotely should be as much like working directly at the remote computer as possible.</span></span>

<span data-ttu-id="740f4-110">Observação: para usar a comunicação remota do PowerShell, o computador remoto deve ser configurado para comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="740f4-110">Note: To use PowerShell remoting, the remote computer must be configured for remoting.</span></span> <span data-ttu-id="740f4-111">Para obter mais informações, consulte [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="740f4-111">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

### <a name="must-both-computers-have-powershell-installed"></a><span data-ttu-id="740f4-112">Os dois computadores devem ter o PowerShell instalado?</span><span class="sxs-lookup"><span data-stu-id="740f4-112">Must both computers have PowerShell installed?</span></span>

<span data-ttu-id="740f4-113">Sim.</span><span class="sxs-lookup"><span data-stu-id="740f4-113">Yes.</span></span> <span data-ttu-id="740f4-114">Para trabalhar remotamente, os computadores locais e remotos devem ter o PowerShell, o Microsoft .NET Framework e o protocolo WS-Management (Web Services for Management).</span><span class="sxs-lookup"><span data-stu-id="740f4-114">To work remotely, the local and remote computers must have PowerShell, the Microsoft .NET Framework, and the Web Services for Management (WS-Management) protocol.</span></span> <span data-ttu-id="740f4-115">Todos os arquivos e outros recursos necessários para executar um comando específico devem estar no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-115">Any files and other resources that are needed to execute a particular command must be on the remote computer.</span></span>

<span data-ttu-id="740f4-116">Computadores que executam o Windows PowerShell 3,0 e computadores que executam o Windows PowerShell 2,0 podem se conectar entre si remotamente e executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="740f4-116">Computers running Windows PowerShell 3.0 and computers running Windows PowerShell 2.0 can connect to each other remotely and run remote commands.</span></span>
<span data-ttu-id="740f4-117">No entanto, alguns recursos, como a capacidade de se desconectar de uma sessão e se reconectar a ela, funcionam somente quando ambos os computadores executam o Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="740f4-117">However, some features, such as the ability to disconnect from a session and reconnect to it, work only when both computers are running Windows PowerShell 3.0.</span></span>

<span data-ttu-id="740f4-118">Você deve ter permissão para se conectar ao computador remoto, permissão para executar o PowerShell e permissão para acessar armazenamentos de dados (como arquivos e pastas) e o registro no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-118">You must have permission to connect to the remote computer, permission to run PowerShell, and permission to access data stores (such as files and folders), and the registry on the remote computer.</span></span>

<span data-ttu-id="740f4-119">Para obter mais informações, consulte [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="740f4-119">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

### <a name="how-does-remoting-work"></a><span data-ttu-id="740f4-120">Como funciona a comunicação remota?</span><span class="sxs-lookup"><span data-stu-id="740f4-120">How does remoting work?</span></span>

<span data-ttu-id="740f4-121">Quando você envia um comando remoto, o comando é transmitido pela rede para o mecanismo do PowerShell no computador remoto e é executado no cliente do PowerShell no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-121">When you submit a remote command, the command is transmitted across the network to the PowerShell engine on the remote computer, and it runs in the PowerShell client on the remote computer.</span></span> <span data-ttu-id="740f4-122">Os resultados do comando são enviados de volta ao computador local e aparecem na sessão do PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="740f4-122">The command results are sent back to the local computer and appear in the PowerShell session on the local computer.</span></span>

<span data-ttu-id="740f4-123">Para transmitir os comandos e receber a saída, o PowerShell usa o protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="740f4-123">To transmit the commands and receive the output, PowerShell uses the WS-Management protocol.</span></span> <span data-ttu-id="740f4-124">Para obter informações sobre o protocolo WS-Management, consulte [protocolo WS-Management](/windows/win32/winrm/ws-management-protocol) na documentação do Windows.</span><span class="sxs-lookup"><span data-stu-id="740f4-124">For information about the WS-Management protocol, see [WS-Management Protocol](/windows/win32/winrm/ws-management-protocol) in the Windows documentation.</span></span>

<span data-ttu-id="740f4-125">A partir do Windows PowerShell 3,0, as sessões remotas são armazenadas no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-125">Beginning in Windows PowerShell 3.0, remote sessions are stored on the remote computer.</span></span> <span data-ttu-id="740f4-126">Isso permite que você se desconecte da sessão e reconecte-se de uma sessão diferente ou de um computador diferente sem interromper os comandos ou perder o estado.</span><span class="sxs-lookup"><span data-stu-id="740f4-126">This enables you to disconnect from the session and reconnect from a different session or a different computer without interrupting the commands or losing state.</span></span>

### <a name="is-powershell-remoting-secure"></a><span data-ttu-id="740f4-127">A comunicação remota do PowerShell é segura?</span><span class="sxs-lookup"><span data-stu-id="740f4-127">Is PowerShell remoting secure?</span></span>

<span data-ttu-id="740f4-128">Quando você se conecta a um computador remoto, o sistema usa as credenciais de nome de usuário e senha no computador local ou as credenciais que você fornece no comando para fazer logon no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-128">When you connect to a remote computer, the system uses the username and password credentials on the local computer or the credentials that you supply in the command to log you in to the remote computer.</span></span> <span data-ttu-id="740f4-129">As credenciais e o restante da transmissão são criptografados.</span><span class="sxs-lookup"><span data-stu-id="740f4-129">The credentials and the rest of the transmission are encrypted.</span></span>

<span data-ttu-id="740f4-130">Para adicionar proteção adicional, você pode configurar o computador remoto para usar protocolo SSL (SSL) em vez de HTTP para escutar solicitações de Gerenciamento Remoto do Windows (WinRM).</span><span class="sxs-lookup"><span data-stu-id="740f4-130">To add additional protection, you can configure the remote computer to use Secure Sockets Layer (SSL) instead of HTTP to listen for Windows Remote Management (WinRM) requests.</span></span> <span data-ttu-id="740f4-131">Em seguida, os usuários podem usar o parâmetro **UseSSL** dos `Invoke-Command` `New-PSSession` `Enter-PSSession` cmdlets, e ao estabelecer uma conexão.</span><span class="sxs-lookup"><span data-stu-id="740f4-131">Then, users can use the **UseSSL** parameter of the `Invoke-Command`, `New-PSSession`, and `Enter-PSSession` cmdlets when establishing a connection.</span></span> <span data-ttu-id="740f4-132">Essa opção usa o canal HTTPS mais seguro em vez de HTTP.</span><span class="sxs-lookup"><span data-stu-id="740f4-132">This option uses the more secure HTTPS channel instead of HTTP.</span></span>

### <a name="do-all-remote-commands-require-powershell-remoting"></a><span data-ttu-id="740f4-133">Todos os comandos remotos exigem comunicação remota do PowerShell?</span><span class="sxs-lookup"><span data-stu-id="740f4-133">Do all remote commands require PowerShell remoting?</span></span>

<span data-ttu-id="740f4-134">Não.</span><span class="sxs-lookup"><span data-stu-id="740f4-134">No.</span></span> <span data-ttu-id="740f4-135">Vários cmdlets têm um parâmetro **ComputerName** que permite que você obtenha objetos do computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-135">Several cmdlets have a **ComputerName** parameter that lets you get objects from the remote computer.</span></span>

<span data-ttu-id="740f4-136">Esses cmdlets não usam a comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="740f4-136">These cmdlets do not use PowerShell remoting.</span></span> <span data-ttu-id="740f4-137">Portanto, você pode usá-los em qualquer computador que esteja executando o PowerShell, mesmo se o computador não estiver configurado para comunicação remota do PowerShell ou se o computador não atender aos requisitos de comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="740f4-137">So, you can use them on any computer that is running PowerShell, even if the computer is not configured for PowerShell remoting or if the computer does not meet the requirements for PowerShell remoting.</span></span>

<span data-ttu-id="740f4-138">Esses cmdlets incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="740f4-138">These cmdlets include the following:</span></span>

- `Get-Process`
- `Get-Service`
- `Get-WinEvent`
- `Get-EventLog`
- `Test-Connection`

<span data-ttu-id="740f4-139">Para localizar todos os cmdlets com um parâmetro **ComputerName** , digite:</span><span class="sxs-lookup"><span data-stu-id="740f4-139">To find all the cmdlets with a **ComputerName** parameter, type:</span></span>

```powershell
Get-Help * -Parameter ComputerName
# or
Get-Command -ParameterName ComputerName
```

<span data-ttu-id="740f4-140">Para determinar se o parâmetro **ComputerName** de um determinado cmdlet requer comunicação remota do PowerShell, consulte a descrição do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="740f4-140">To determine whether the **ComputerName** parameter of a particular cmdlet requires PowerShell remoting, see the parameter description.</span></span> <span data-ttu-id="740f4-141">Para exibir a descrição do parâmetro, digite:</span><span class="sxs-lookup"><span data-stu-id="740f4-141">To display the parameter description, type:</span></span>

```powershell
Get-Help <cmdlet-name> -Parameter ComputerName
```

<span data-ttu-id="740f4-142">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="740f4-142">For example:</span></span>

```powershell
Get-Help Get-Process -Parameter ComputerName
```

<span data-ttu-id="740f4-143">Para todos os outros comandos, use o `Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="740f4-143">For all other commands, use the `Invoke-Command` cmdlet.</span></span>

### <a name="how-do-i-run-a-command-on-a-remote-computer"></a><span data-ttu-id="740f4-144">Como fazer executar um comando em um computador remoto?</span><span class="sxs-lookup"><span data-stu-id="740f4-144">How do I run a command on a remote computer?</span></span>

<span data-ttu-id="740f4-145">Para executar um comando em um computador remoto, use o `Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="740f4-145">To run a command on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="740f4-146">Coloque o comando entre chaves ( `{}` ) para torná-lo um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="740f4-146">Enclose your command in braces (`{}`) to make it a script block.</span></span> <span data-ttu-id="740f4-147">Use o parâmetro **scriptblock** do `Invoke-Command` para especificar o comando.</span><span class="sxs-lookup"><span data-stu-id="740f4-147">Use the **ScriptBlock** parameter of `Invoke-Command` to specify the command.</span></span>

<span data-ttu-id="740f4-148">Você pode usar o parâmetro **ComputerName** de `Invoke-Command` para especificar um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-148">You can use the **ComputerName** parameter of `Invoke-Command` to specify a remote computer.</span></span> <span data-ttu-id="740f4-149">Ou, você pode criar uma conexão persistente com um computador remoto (uma sessão) e, em seguida, usar o parâmetro de **sessão** do `Invoke-Command` para executar o comando na sessão.</span><span class="sxs-lookup"><span data-stu-id="740f4-149">Or, you can create a persistent connection to a remote computer (a session) and then use the **Session** parameter of `Invoke-Command` to run the command in the session.</span></span>

<span data-ttu-id="740f4-150">Por exemplo, os comandos a seguir executam um `Get-Process` comando remotamente.</span><span class="sxs-lookup"><span data-stu-id="740f4-150">For example, the following commands run a `Get-Process` command remotely.</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -ScriptBlock {Get-Process}

#  - OR -

Invoke-Command -Session $s -ScriptBlock {Get-Process}
```

<span data-ttu-id="740f4-151">Para interromper um comando remoto, digite <kbd>Ctrl</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="740f4-151">To interrupt a remote command, type <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="740f4-152">A solicitação de interrupção é passada para o computador remoto, onde ele encerra o comando remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-152">The interruption request is passed to the remote computer, where it terminates the remote command.</span></span>

<span data-ttu-id="740f4-153">Para obter mais informações sobre comandos remotos, consulte about_Remote e os tópicos de ajuda para os cmdlets que oferecem suporte a comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="740f4-153">For more information about remote commands, see about_Remote and the Help topics for the cmdlets that support remoting.</span></span>

### <a name="can-i-just-telnet-into-a-remote-computer"></a><span data-ttu-id="740f4-154">Posso apenas fazer o Telnet em um computador remoto?</span><span class="sxs-lookup"><span data-stu-id="740f4-154">Can I just telnet into a remote computer?</span></span>

<span data-ttu-id="740f4-155">Você pode usar o `Enter-PSSession` cmdlet para iniciar uma sessão interativa com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-155">You can use the `Enter-PSSession` cmdlet to start an interactive session with a remote computer.</span></span>

<span data-ttu-id="740f4-156">No prompt do PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="740f4-156">At the PowerShell prompt, type:</span></span>

```powershell
Enter-PSSession <ComputerName>
```

<span data-ttu-id="740f4-157">O prompt de comando é alterado para mostrar que você está conectado ao computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-157">The command prompt changes to show that you are connected to the remote computer.</span></span>

```
<ComputerName>\C:>
```

<span data-ttu-id="740f4-158">Agora, os comandos digitados são executados no computador remoto, como se você os tivesse digitado diretamente no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-158">Now, the commands that you type run on the remote computer just as though you typed them directly on the remote computer.</span></span>

<span data-ttu-id="740f4-159">Para encerrar a sessão interativa, digite:</span><span class="sxs-lookup"><span data-stu-id="740f4-159">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="740f4-160">Uma sessão interativa é uma sessão persistente que usa o protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="740f4-160">An interactive session is a persistent session that uses the WS-Management protocol.</span></span> <span data-ttu-id="740f4-161">Não é o mesmo que usar o Telnet, mas fornece uma experiência semelhante.</span><span class="sxs-lookup"><span data-stu-id="740f4-161">It is not the same as using Telnet, but it provides a similar experience.</span></span>

<span data-ttu-id="740f4-162">Para obter mais informações, consulte `Enter-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="740f4-162">For more information, see `Enter-PSSession`.</span></span>

### <a name="can-i-create-a-persistent-connection"></a><span data-ttu-id="740f4-163">Posso criar uma conexão persistente?</span><span class="sxs-lookup"><span data-stu-id="740f4-163">Can I create a persistent connection?</span></span>

<span data-ttu-id="740f4-164">Sim.</span><span class="sxs-lookup"><span data-stu-id="740f4-164">Yes.</span></span> <span data-ttu-id="740f4-165">Você pode executar comandos remotos especificando o nome do computador remoto, seu nome NetBIOS ou seu endereço IP.</span><span class="sxs-lookup"><span data-stu-id="740f4-165">You can run remote commands by specifying the name of the remote computer, its NetBIOS name, or its IP address.</span></span> <span data-ttu-id="740f4-166">Ou, você pode executar comandos remotos especificando uma sessão do PowerShell (PSSession) que está conectada ao computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-166">Or, you can run remote commands by specifying a PowerShell session (PSSession) that is connected to the remote computer.</span></span>

<span data-ttu-id="740f4-167">Quando você usa o parâmetro **ComputerName** do `Invoke-Command` ou, o `Enter-PSSession` PowerShell estabelece uma conexão temporária.</span><span class="sxs-lookup"><span data-stu-id="740f4-167">When you use the **ComputerName** parameter of `Invoke-Command` or `Enter-PSSession`, PowerShell establishes a temporary connection.</span></span> <span data-ttu-id="740f4-168">O PowerShell usa a conexão para executar apenas o comando atual e fecha a conexão.</span><span class="sxs-lookup"><span data-stu-id="740f4-168">PowerShell uses the connection to run only the current command, and then it closes the connection.</span></span> <span data-ttu-id="740f4-169">Esse é um método muito eficiente para executar um único comando ou vários comandos não relacionados, mesmo em vários computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="740f4-169">This is a very efficient method for running a single command or several unrelated commands, even on many remote computers.</span></span>

<span data-ttu-id="740f4-170">Quando você usa o `New-PSSession` cmdlet para criar uma PSSession, o PowerShell estabelece uma conexão persistente para a PSSession.</span><span class="sxs-lookup"><span data-stu-id="740f4-170">When you use the `New-PSSession` cmdlet to create a PSSession, PowerShell establishes a persistent connection for the PSSession.</span></span> <span data-ttu-id="740f4-171">Em seguida, você pode executar vários comandos na PSSession, incluindo comandos que compartilham dados.</span><span class="sxs-lookup"><span data-stu-id="740f4-171">Then, you can run multiple commands in the PSSession, including commands that share data.</span></span>

<span data-ttu-id="740f4-172">Normalmente, você cria uma PSSession para executar uma série de comandos relacionados que compartilham dados.</span><span class="sxs-lookup"><span data-stu-id="740f4-172">Typically, you create a PSSession to run a series of related commands that share data.</span></span> <span data-ttu-id="740f4-173">Caso contrário, a conexão temporária criada pelo parâmetro **ComputerName** é suficiente para a maioria dos comandos.</span><span class="sxs-lookup"><span data-stu-id="740f4-173">Otherwise, the temporary connection created by the **ComputerName** parameter is sufficient for most commands.</span></span>

<span data-ttu-id="740f4-174">Para obter mais informações sobre sessões, consulte about_PSSessions.</span><span class="sxs-lookup"><span data-stu-id="740f4-174">For more information about sessions, see about_PSSessions.</span></span>

### <a name="can-i-run-commands-on-more-than-one-computer-at-a-time"></a><span data-ttu-id="740f4-175">Posso executar comandos em mais de um computador por vez?</span><span class="sxs-lookup"><span data-stu-id="740f4-175">Can I run commands on more than one computer at a time?</span></span>

<span data-ttu-id="740f4-176">Sim.</span><span class="sxs-lookup"><span data-stu-id="740f4-176">Yes.</span></span> <span data-ttu-id="740f4-177">O parâmetro **ComputerName** do `Invoke-Command` cmdlet aceita vários nomes de computador e o parâmetro **Session** aceita várias PSSessions.</span><span class="sxs-lookup"><span data-stu-id="740f4-177">The **ComputerName** parameter of the `Invoke-Command` cmdlet accepts multiple computer names, and the **Session** parameter accepts multiple PSSessions.</span></span>

<span data-ttu-id="740f4-178">Quando você executa um `Invoke-Command` comando, o PowerShell executa os comandos em todos os computadores especificados ou em todas as PSSessions especificadas.</span><span class="sxs-lookup"><span data-stu-id="740f4-178">When you run an `Invoke-Command` command, PowerShell runs the commands on all of the specified computers or in all of the specified PSSessions.</span></span>

<span data-ttu-id="740f4-179">O PowerShell pode gerenciar centenas de conexões remotas simultâneas.</span><span class="sxs-lookup"><span data-stu-id="740f4-179">PowerShell can manage hundreds of concurrent remote connections.</span></span> <span data-ttu-id="740f4-180">No entanto, o número de comandos remotos que você pode enviar pode ser limitado pelos recursos do seu computador e sua capacidade de estabelecer e manter várias conexões de rede.</span><span class="sxs-lookup"><span data-stu-id="740f4-180">However, the number of remote commands that you can send might be limited by the resources of your computer and its capacity to establish and maintain multiple network connections.</span></span>

<span data-ttu-id="740f4-181">Para obter mais informações, consulte o exemplo no `Invoke-Command` tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="740f4-181">For more information, see the example in the `Invoke-Command` Help topic.</span></span>

### <a name="where-are-my-profiles"></a><span data-ttu-id="740f4-182">Onde estão meus perfis?</span><span class="sxs-lookup"><span data-stu-id="740f4-182">Where are my profiles?</span></span>

<span data-ttu-id="740f4-183">Os perfis do PowerShell não são executados automaticamente em sessões remotas, portanto, os comandos que o perfil adiciona não estão presentes na sessão.</span><span class="sxs-lookup"><span data-stu-id="740f4-183">PowerShell profiles are not run automatically in remote sessions, so the commands that the profile adds are not present in the session.</span></span> <span data-ttu-id="740f4-184">Além disso, a `$profile` variável automática não é populada em sessões remotas.</span><span class="sxs-lookup"><span data-stu-id="740f4-184">In addition, the `$profile` automatic variable is not populated in remote sessions.</span></span>

<span data-ttu-id="740f4-185">Para executar um perfil em uma sessão, use o `Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="740f4-185">To run a profile in a session, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="740f4-186">Por exemplo, o comando a seguir executa o perfil CurrentUserCurrentHost do computador local na sessão no `$s` .</span><span class="sxs-lookup"><span data-stu-id="740f4-186">For example, the following command runs the CurrentUserCurrentHost profile from the local computer in the session in `$s`.</span></span>

```
Invoke-Command -Session $s -FilePath $profile
```

<span data-ttu-id="740f4-187">O comando a seguir executa o perfil CurrentUserCurrentHost do computador remoto na sessão no `$s` .</span><span class="sxs-lookup"><span data-stu-id="740f4-187">The following command runs the CurrentUserCurrentHost profile from the remote computer in the session in `$s`.</span></span> <span data-ttu-id="740f4-188">Como a `$profile` variável não é populada, o comando usa o caminho explícito para o perfil.</span><span class="sxs-lookup"><span data-stu-id="740f4-188">Because the `$profile` variable is not populated, the command uses the explicit path to the profile.</span></span>

```powershell
Invoke-Command -Session $s {
  . "$home\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"
}
```

<span data-ttu-id="740f4-189">Depois de executar esse comando, os comandos que o perfil adiciona à sessão estão disponíveis no `$s` .</span><span class="sxs-lookup"><span data-stu-id="740f4-189">After running this command, the commands that the profile adds to the session are available in `$s`.</span></span>

<span data-ttu-id="740f4-190">Você também pode usar um script de inicialização em uma configuração de sessão para executar um perfil em cada sessão remota que usa a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="740f4-190">You can also use a startup script in a session configuration to run a profile in every remote session that uses the session configuration.</span></span>

<span data-ttu-id="740f4-191">Para obter mais informações sobre perfis do PowerShell, consulte about_Profiles.</span><span class="sxs-lookup"><span data-stu-id="740f4-191">For more information about PowerShell profiles, see about_Profiles.</span></span>
<span data-ttu-id="740f4-192">Para obter mais informações sobre configurações de sessão, consulte `Register-PSSessionConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="740f4-192">For more information about session configurations, see `Register-PSSessionConfiguration`.</span></span>

### <a name="how-does-throttling-work-on-remote-commands"></a><span data-ttu-id="740f4-193">Como a limitação funciona em comandos remotos?</span><span class="sxs-lookup"><span data-stu-id="740f4-193">How does throttling work on remote commands?</span></span>

<span data-ttu-id="740f4-194">Para ajudá-lo a gerenciar os recursos em seu computador local, o PowerShell inclui um recurso de limitação por comando que permite limitar o número de conexões remotas simultâneas estabelecidas para cada comando.</span><span class="sxs-lookup"><span data-stu-id="740f4-194">To help you manage the resources on your local computer, PowerShell includes a per-command throttling feature that lets you limit the number of concurrent remote connections that are established for each command.</span></span>

<span data-ttu-id="740f4-195">O padrão é 32 conexões simultâneas, mas você pode usar o parâmetro **ThrottleLimit** dos cmdlets para definir um limite de limitação personalizado para comandos específicos.</span><span class="sxs-lookup"><span data-stu-id="740f4-195">The default is 32 concurrent connections, but you can use the **ThrottleLimit** parameter of the cmdlets to set a custom throttle limit for particular commands.</span></span>

<span data-ttu-id="740f4-196">Ao usar o recurso de limitação, lembre-se de que ele é aplicado a cada comando, e não a toda a sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="740f4-196">When you use the throttling feature, remember that it is applied to each command, not to the entire session or to the computer.</span></span> <span data-ttu-id="740f4-197">Se você estiver executando comandos simultaneamente em várias sessões ou PSSessions, o número de conexões simultâneas será a soma das conexões simultâneas em todas as sessões.</span><span class="sxs-lookup"><span data-stu-id="740f4-197">If you are running commands concurrently in several sessions or PSSessions, the number of concurrent connections is the sum of the concurrent connections in all the sessions.</span></span>

<span data-ttu-id="740f4-198">Para localizar cmdlets com um parâmetro **ThrottleLimit** , digite:</span><span class="sxs-lookup"><span data-stu-id="740f4-198">To find cmdlets with a **ThrottleLimit** parameter, type:</span></span>

```
Get-Help * -Parameter ThrottleLimit
-or-
Get-Command -ParameterName ThrottleLimit
```

### <a name="is-the-output-of-remote-commands-different-from-local-output"></a><span data-ttu-id="740f4-199">A saída de comandos remotos é diferente da saída local?</span><span class="sxs-lookup"><span data-stu-id="740f4-199">Is the output of remote commands different from local output?</span></span>

<span data-ttu-id="740f4-200">Quando você usa o PowerShell localmente, você envia e recebe objetos de .NET Framework "ao vivo"; objetos "dinâmicos" são objetos associados a programas reais ou componentes do sistema.</span><span class="sxs-lookup"><span data-stu-id="740f4-200">When you use PowerShell locally, you send and receive "live" .NET Framework objects; "live" objects are objects that are associated with actual programs or system components.</span></span> <span data-ttu-id="740f4-201">Quando você invoca os métodos ou altera as propriedades de objetos dinâmicos, as alterações afetam o programa ou componente real.</span><span class="sxs-lookup"><span data-stu-id="740f4-201">When you invoke the methods or change the properties of live objects, the changes affect the actual program or component.</span></span> <span data-ttu-id="740f4-202">E, quando as propriedades de um programa ou componente são alteradas, as propriedades do objeto que as representa também são alteradas.</span><span class="sxs-lookup"><span data-stu-id="740f4-202">And, when the properties of a program or component change, the properties of the object that represent them also change.</span></span>

<span data-ttu-id="740f4-203">No entanto, como a maioria dos objetos dinâmicos não pode ser transmitida pela rede, o PowerShell "serializa" a maioria dos objetos enviados em comandos remotos, ou seja, converte cada objeto em uma série de elementos de dados XML (linguagem de restrição em XML [CLiXML]) para transmissão.</span><span class="sxs-lookup"><span data-stu-id="740f4-203">However, because most live objects cannot be transmitted over the network, PowerShell "serializes" most of the objects sent in remote commands, that is, it converts each object into a series of XML (Constraint Language in XML [CLiXML]) data elements for transmission.</span></span>

<span data-ttu-id="740f4-204">Quando o PowerShell recebe um objeto serializado, ele converte o XML em um tipo de objeto desserializado.</span><span class="sxs-lookup"><span data-stu-id="740f4-204">When PowerShell receives a serialized object, it converts the XML into a deserialized object type.</span></span> <span data-ttu-id="740f4-205">O objeto desserializado é um registro preciso das propriedades do programa ou componente em um momento anterior, mas não é mais "dinâmico", ou seja, não está mais diretamente associado ao componente.</span><span class="sxs-lookup"><span data-stu-id="740f4-205">The deserialized object is an accurate record of the properties of the program or component at a previous time, but it is no longer "live", that is, it is no longer directly associated with the component.</span></span> <span data-ttu-id="740f4-206">E os métodos são removidos porque não são mais eficazes.</span><span class="sxs-lookup"><span data-stu-id="740f4-206">And, the methods are removed because they are no longer effective.</span></span>

<span data-ttu-id="740f4-207">Normalmente, você pode usar objetos desserializados da mesma forma que usaria objetos dinâmicos, mas deve estar ciente de suas limitações.</span><span class="sxs-lookup"><span data-stu-id="740f4-207">Typically, you can use deserialized objects just as you would use live objects, but you must be aware of their limitations.</span></span> <span data-ttu-id="740f4-208">Além disso, os objetos retornados pelo `Invoke-Command` cmdlet têm propriedades adicionais que ajudam a determinar a origem do comando.</span><span class="sxs-lookup"><span data-stu-id="740f4-208">Also, the objects that are returned by the `Invoke-Command` cmdlet have additional properties that help you to determine the origin of the command.</span></span>

<span data-ttu-id="740f4-209">Alguns tipos de objeto, como objetos DirectoryInfo e GUIDs, são convertidos de volta em objetos dinâmicos quando eles são recebidos.</span><span class="sxs-lookup"><span data-stu-id="740f4-209">Some object types, such as DirectoryInfo objects and GUIDs, are converted back into live objects when they are received.</span></span> <span data-ttu-id="740f4-210">Esses objetos não precisam de tratamento ou formatação especial.</span><span class="sxs-lookup"><span data-stu-id="740f4-210">These objects do not need any special handling or formatting.</span></span>

<span data-ttu-id="740f4-211">Para obter informações sobre como interpretar e formatar a saída remota, consulte [about_Remote_Output](about_Remote_Output.md).</span><span class="sxs-lookup"><span data-stu-id="740f4-211">For information about interpreting and formatting remote output, see [about_Remote_Output](about_Remote_Output.md).</span></span>

### <a name="can-i-run-background-jobs-remotely"></a><span data-ttu-id="740f4-212">Posso executar trabalhos em segundo plano remotamente?</span><span class="sxs-lookup"><span data-stu-id="740f4-212">Can I run background jobs remotely?</span></span>

<span data-ttu-id="740f4-213">Sim.</span><span class="sxs-lookup"><span data-stu-id="740f4-213">Yes.</span></span> <span data-ttu-id="740f4-214">Um trabalho em segundo plano do PowerShell é um comando do PowerShell que é executado de forma assíncrona sem interagir com a sessão.</span><span class="sxs-lookup"><span data-stu-id="740f4-214">A PowerShell background job is a PowerShell command that runs asynchronously without interacting with the session.</span></span> <span data-ttu-id="740f4-215">Quando você inicia um trabalho em segundo plano, o prompt de comando retorna imediatamente, e você pode continuar a trabalhar na sessão enquanto o trabalho é executado, mesmo que ele seja executado por um longo período de tempo.</span><span class="sxs-lookup"><span data-stu-id="740f4-215">When you start a background job, the command prompt returns immediately, and you can continue to work in the session while the job runs even if it runs for an extended period of time.</span></span>

<span data-ttu-id="740f4-216">Você pode iniciar um trabalho em segundo plano mesmo que outros comandos estejam em execução porque os trabalhos em segundo plano sempre são executados de forma assíncrona em uma sessão temporária.</span><span class="sxs-lookup"><span data-stu-id="740f4-216">You can start a background job even while other commands are running because background jobs always run asynchronously in a temporary session.</span></span>

<span data-ttu-id="740f4-217">Você pode executar trabalhos em segundo plano em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-217">You can run background jobs on a local or remote computer.</span></span> <span data-ttu-id="740f4-218">Por padrão, um trabalho em segundo plano é executado no computador local.</span><span class="sxs-lookup"><span data-stu-id="740f4-218">By default, a background job runs on the local computer.</span></span> <span data-ttu-id="740f4-219">No entanto, você pode usar o parâmetro **AsJob** do `Invoke-Command` cmdlet para executar qualquer comando remoto como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="740f4-219">However, you can use the **AsJob** parameter of the `Invoke-Command` cmdlet to run any remote command as a background job.</span></span> <span data-ttu-id="740f4-220">E, você pode usar `Invoke-Command` o para executar um `Start-Job` comando remotamente.</span><span class="sxs-lookup"><span data-stu-id="740f4-220">And, you can use `Invoke-Command` to run a `Start-Job` command remotely.</span></span>

<span data-ttu-id="740f4-221">Para obter mais informações sobre trabalhos em segundo plano no PowerShell, consulte [about_Jobs (about_Jobs. MD)] e [about_Remote_Jobs (about_Remote_Jobs. MD)].</span><span class="sxs-lookup"><span data-stu-id="740f4-221">For more information about background jobs in PowerShell , see [about_Jobs(about_Jobs.md)] and [about_Remote_Jobs(about_Remote_Jobs.md)].</span></span>

### <a name="can-i-run-windows-programs-on-a-remote-computer"></a><span data-ttu-id="740f4-222">Posso executar programas do Windows em um computador remoto?</span><span class="sxs-lookup"><span data-stu-id="740f4-222">Can I run windows programs on a remote computer?</span></span>

<span data-ttu-id="740f4-223">Você pode usar os comandos remotos do PowerShell para executar programas baseados no Windows em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="740f4-223">You can use PowerShell remote commands to run Windows-based programs on remote computers.</span></span> <span data-ttu-id="740f4-224">Por exemplo, você pode executar `Shutdown.exe` ou `Ipconfig.exe` em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-224">For example, you can run `Shutdown.exe` or `Ipconfig.exe` on a remote computer.</span></span>

<span data-ttu-id="740f4-225">No entanto, você não pode usar comandos do PowerShell para abrir a interface do usuário para qualquer programa em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-225">However, you cannot use PowerShell commands to open the user interface for any program on a remote computer.</span></span>

<span data-ttu-id="740f4-226">Quando você inicia um programa do Windows em um computador remoto, o comando não é concluído e o prompt de comando do PowerShell não retorna, até que o programa seja concluído ou até que você pressione <kbd>Ctrl</kbd> + <kbd>C</kbd> para interromper o comando.</span><span class="sxs-lookup"><span data-stu-id="740f4-226">When you start a Windows program on a remote computer, the command is not completed, and the PowerShell command prompt does not return, until the program is finished or until you press <kbd>CTRL</kbd>+<kbd>C</kbd> to interrupt the command.</span></span> <span data-ttu-id="740f4-227">Por exemplo, se você executar o `Ipconfig.exe` programa em um computador remoto, o prompt de comando não retornará até que o `Ipconfig.exe` seja concluído.</span><span class="sxs-lookup"><span data-stu-id="740f4-227">For example, if you run the `Ipconfig.exe` program on a remote computer, the command prompt does not return until `Ipconfig.exe` is completed.</span></span>

<span data-ttu-id="740f4-228">Se você usar comandos remotos para iniciar um programa que tenha uma interface do usuário, o processo do programa será iniciado, mas a interface do usuário não será exibida.</span><span class="sxs-lookup"><span data-stu-id="740f4-228">If you use remote commands to start a program that has a user interface, the program process starts, but the user interface does not appear.</span></span> <span data-ttu-id="740f4-229">O comando do PowerShell não é concluído e o prompt de comando não retorna até que o processo do programa seja interrompido ou até que você pressione <kbd>Ctrl</kbd> + <kbd>C</kbd>, o que interrompe o comando e interrompe o processo.</span><span class="sxs-lookup"><span data-stu-id="740f4-229">The PowerShell command is not completed, and the command prompt does not return until you stop the program process or until you press <kbd>CTRL</kbd>+<kbd>C</kbd>, which interrupts the command and stops the process.</span></span>

<span data-ttu-id="740f4-230">Por exemplo, se você usar um comando do PowerShell para executar `Notepad` em um computador remoto, o processo do bloco de notas será iniciado no computador remoto, mas a interface do usuário do bloco de notas não será exibida.</span><span class="sxs-lookup"><span data-stu-id="740f4-230">For example, if you use a PowerShell command to run `Notepad` on a remote computer, the Notepad process starts on the remote computer, but the Notepad user interface does not appear.</span></span> <span data-ttu-id="740f4-231">Para interromper o comando e restaurar o prompt de comando, pressione <kbd>Ctrl</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="740f4-231">To interrupt the command and restore the command prompt, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

### <a name="can-i-limit-the-commands-that-users-can-run-remotely-on-my-computer"></a><span data-ttu-id="740f4-232">Posso limitar os comandos que os usuários podem executar remotamente no meu computador?</span><span class="sxs-lookup"><span data-stu-id="740f4-232">Can I limit the commands that users can run remotely on my computer?</span></span>

<span data-ttu-id="740f4-233">Sim.</span><span class="sxs-lookup"><span data-stu-id="740f4-233">Yes.</span></span> <span data-ttu-id="740f4-234">Cada sessão remota deve usar uma das configurações de sessão no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-234">Every remote session must use one of the session configurations on the remote computer.</span></span> <span data-ttu-id="740f4-235">Você pode gerenciar as configurações de sessão no seu computador (e as permissões para essas configurações de sessão) para determinar quem pode executar comandos remotamente em seu computador e quais comandos eles podem executar.</span><span class="sxs-lookup"><span data-stu-id="740f4-235">You can manage the session configurations on your computer (and the permissions to those session configurations) to determine who can run commands remotely on your computer and which commands they can run.</span></span>

<span data-ttu-id="740f4-236">Uma configuração de sessão configura o ambiente para a sessão.</span><span class="sxs-lookup"><span data-stu-id="740f4-236">A session configuration configures the environment for the session.</span></span> <span data-ttu-id="740f4-237">Você pode definir a configuração usando um assembly que implementa uma nova classe de configuração ou usando um script que é executado na sessão.</span><span class="sxs-lookup"><span data-stu-id="740f4-237">You can define the configuration by using an assembly that implements a new configuration class or by using a script that runs in the session.</span></span> <span data-ttu-id="740f4-238">A configuração pode determinar os comandos que estão disponíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="740f4-238">The configuration can determine the commands that are available in the session.</span></span>
<span data-ttu-id="740f4-239">Além disso, a configuração pode incluir configurações que protegem o computador, como configurações que limitam a quantidade de dados que a sessão pode receber remotamente em um único objeto ou comando.</span><span class="sxs-lookup"><span data-stu-id="740f4-239">And, the configuration can include settings that protect the computer, such as settings that limit the amount of data that the session can receive remotely in a single object or command.</span></span> <span data-ttu-id="740f4-240">Você também pode especificar um descritor de segurança que determina as permissões necessárias para usar a configuração.</span><span class="sxs-lookup"><span data-stu-id="740f4-240">You can also specify a security descriptor that determines the permissions that are required to use the configuration.</span></span>

<span data-ttu-id="740f4-241">O `Enable-PSRemoting` cmdlet cria as configurações de sessão padrão em seu computador: Microsoft. PowerShell, Microsoft. PowerShell. Workflow e Microsoft. powershell32 (somente sistemas operacionais de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="740f4-241">The `Enable-PSRemoting` cmdlet creates the default session configurations on your computer: Microsoft.PowerShell, Microsoft.PowerShell.Workflow, and Microsoft.PowerShell32 (64-bit operating systems only).</span></span> <span data-ttu-id="740f4-242">`Enable-PSRemoting` define o descritor de segurança para a configuração para permitir que somente membros do grupo Administradores no seu computador os utilizem.</span><span class="sxs-lookup"><span data-stu-id="740f4-242">`Enable-PSRemoting` sets the security descriptor for the configuration to allow only members of the Administrators group on your computer to use them.</span></span>

<span data-ttu-id="740f4-243">Você pode usar os cmdlets de configuração de sessão para editar as configurações de sessão padrão, para criar novas configurações de sessão e para alterar os descritores de segurança de todas as configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="740f4-243">You can use the session configuration cmdlets to edit the default session configurations, to create new session configurations, and to change the security descriptors of all the session configurations.</span></span>

<span data-ttu-id="740f4-244">A partir do Windows PowerShell 3,0, o `New-PSSessionConfigurationFile` cmdlet permite que você crie configurações de sessão personalizadas usando um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="740f4-244">Beginning in Windows PowerShell 3.0, the `New-PSSessionConfigurationFile` cmdlet lets you create custom session configurations by using a text file.</span></span> <span data-ttu-id="740f4-245">O arquivo inclui opções para definir o modo de linguagem e para especificar os cmdlets e módulos que estão disponíveis em sessões que usam a configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="740f4-245">The file includes options for setting the language mode and for specifying the cmdlets and modules that are available in sessions that use the session configuration.</span></span>

<span data-ttu-id="740f4-246">Quando os usuários usam `Invoke-Command` os `New-PSSession` cmdlets,, ou `Enter-PSSession` , eles podem usar o parâmetro **ConfigurationName** para indicar a configuração de sessão usada para a sessão.</span><span class="sxs-lookup"><span data-stu-id="740f4-246">When users use the `Invoke-Command`, `New-PSSession`, or `Enter-PSSession` cmdlets, they can use the **ConfigurationName** parameter to indicate the session configuration that is used for the session.</span></span> <span data-ttu-id="740f4-247">Além disso, eles podem alterar a configuração padrão usada por suas sessões alterando o valor da `$PSSessionConfigurationName` variável de preferência na sessão.</span><span class="sxs-lookup"><span data-stu-id="740f4-247">And, they can change the default configuration that their sessions use by changing the value of the `$PSSessionConfigurationName` preference variable in the session.</span></span>

<span data-ttu-id="740f4-248">Para obter mais informações sobre configurações de sessão, consulte a ajuda para os cmdlets de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="740f4-248">For more information about session configurations, see the Help for the session configuration cmdlets.</span></span> <span data-ttu-id="740f4-249">Para localizar os cmdlets de configuração de sessão, digite:</span><span class="sxs-lookup"><span data-stu-id="740f4-249">To find the session configuration cmdlets, type:</span></span>

```powershell
Get-Command *PSSessionConfiguration
```

### <a name="what-are-fan-in-and-fan-out-configurations"></a><span data-ttu-id="740f4-250">O que são configurações de Fan-in e Fan out?</span><span class="sxs-lookup"><span data-stu-id="740f4-250">What are fan in and fan out configurations?</span></span>

<span data-ttu-id="740f4-251">O cenário de comunicação remota do PowerShell mais comum que envolve vários computadores é a configuração de um para muitos, na qual um computador local (o computador do administrador) executa comandos do PowerShell em vários computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="740f4-251">The most common PowerShell remoting scenario involving multiple computers is the one-to-many configuration, in which one local computer (the administrator's computer) runs PowerShell commands on numerous remote computers.</span></span> <span data-ttu-id="740f4-252">Isso é conhecido como o cenário de "Fan-out".</span><span class="sxs-lookup"><span data-stu-id="740f4-252">This is known as the "fan-out" scenario.</span></span>

<span data-ttu-id="740f4-253">No entanto, em algumas empresas, a configuração é muitos para um, em que muitos computadores cliente se conectam a um único computador remoto que está executando o PowerShell, como um servidor de arquivos ou um quiosque.</span><span class="sxs-lookup"><span data-stu-id="740f4-253">However, in some enterprises, the configuration is many-to-one, where many client computers connect to a single remote computer that is running PowerShell, such as a file server or a kiosk.</span></span> <span data-ttu-id="740f4-254">Isso é conhecido como a configuração "Fan-in".</span><span class="sxs-lookup"><span data-stu-id="740f4-254">This is known as the "fan-in" configuration.</span></span>

<span data-ttu-id="740f4-255">A comunicação remota do PowerShell dá suporte a configurações de Fan-out e de Fan-in.</span><span class="sxs-lookup"><span data-stu-id="740f4-255">PowerShell remoting supports both fan-out and fan-in configurations.</span></span>

<span data-ttu-id="740f4-256">Para a configuração de Fan-out, o PowerShell usa o protocolo WS-Management (Web Services for Management) e o serviço WinRM que dá suporte à implementação da Microsoft do WS-Management.</span><span class="sxs-lookup"><span data-stu-id="740f4-256">For the fan-out configuration, PowerShell uses the Web Services for Management (WS-Management) protocol and the WinRM service that supports the Microsoft implementation of WS-Management.</span></span> <span data-ttu-id="740f4-257">Quando um computador local se conecta a um computador remoto, WS-Management estabelece uma conexão e usa um plug-in para o PowerShell para iniciar o processo de host do PowerShell (Wsmprovhost.exe) no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-257">When a local computer connects to a remote computer, WS-Management establishes a connection and uses a plug-in for PowerShell to start the PowerShell host process (Wsmprovhost.exe) on the remote computer.</span></span> <span data-ttu-id="740f4-258">O usuário pode especificar uma porta alternativa, uma configuração de sessão alternativa e outros recursos para personalizar a conexão remota.</span><span class="sxs-lookup"><span data-stu-id="740f4-258">The user can specify an alternate port, an alternate session configuration, and other features to customize the remote connection.</span></span>

<span data-ttu-id="740f4-259">Para dar suporte à configuração "Fan-in", o PowerShell usa o IIS (serviços de informações da Internet) para hospedar o WS-Management, carregar o plug-in do PowerShell e iniciar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="740f4-259">To support the "fan-in" configuration, PowerShell uses internet Information Services (IIS) to host WS-Management, to load the PowerShell plug-in, and to start PowerShell.</span></span> <span data-ttu-id="740f4-260">Nesse cenário, em vez de iniciar cada sessão do PowerShell em um processo separado, todas as sessões do PowerShell são executadas no mesmo processo de host.</span><span class="sxs-lookup"><span data-stu-id="740f4-260">In this scenario, instead of starting each PowerShell session in a separate process, all PowerShell sessions run in the same host process.</span></span>

<span data-ttu-id="740f4-261">O gerenciamento remoto de hospedagem e de Fan-in do IIS não tem suporte no Windows XP ou no Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="740f4-261">IIS hosting and fan-in remote management is not supported in Windows XP or in Windows Server 2003.</span></span>

<span data-ttu-id="740f4-262">Em uma configuração de Fan-in, o usuário pode especificar um URI de conexão e um ponto de extremidade HTTP, incluindo o transporte, o nome do computador, a porta e o nome do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="740f4-262">In a fan-in configuration, the user can specify a connection URI and an HTTP endpoint, including the transport, computer name, port, and application name.</span></span>
<span data-ttu-id="740f4-263">O IIS encaminha todas as solicitações com um nome de aplicativo especificado para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="740f4-263">IIS forwards all the requests with a specified application name to the application.</span></span> <span data-ttu-id="740f4-264">O padrão é WS-Management, que pode hospedar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="740f4-264">The default is WS-Management, which can host PowerShell.</span></span>

<span data-ttu-id="740f4-265">Você também pode especificar um mecanismo de autenticação e proibir ou permitir o redirecionamento de pontos de extremidade HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="740f4-265">You can also specify an authentication mechanism and prohibit or allow redirection from HTTP and HTTPS endpoints.</span></span>

### <a name="can-i-test-remoting-on-a-single-computer-not-in-a-domain"></a><span data-ttu-id="740f4-266">Posso testar a comunicação remota em um único computador que não está em um domínio?</span><span class="sxs-lookup"><span data-stu-id="740f4-266">Can I test remoting on a single computer not in a domain?</span></span>

<span data-ttu-id="740f4-267">Sim.</span><span class="sxs-lookup"><span data-stu-id="740f4-267">Yes.</span></span> <span data-ttu-id="740f4-268">A comunicação remota do PowerShell está disponível mesmo quando o computador local não está em um domínio.</span><span class="sxs-lookup"><span data-stu-id="740f4-268">PowerShell remoting is available even when the local computer is not in a domain.</span></span> <span data-ttu-id="740f4-269">Você pode usar os recursos de comunicação remota para se conectar a sessões e criar sessões no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="740f4-269">You can use the remoting features to connect to sessions and to create sessions on the same computer.</span></span> <span data-ttu-id="740f4-270">Os recursos funcionam da mesma forma que quando você se conecta a um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-270">The features work the same as they do when you connect to a remote computer.</span></span>

<span data-ttu-id="740f4-271">Para executar comandos remotos em um computador em um grupo de trabalho, altere as seguintes configurações do Windows no computador.</span><span class="sxs-lookup"><span data-stu-id="740f4-271">To run remote commands on a computer in a workgroup, change the following Windows settings on the computer.</span></span>

<span data-ttu-id="740f4-272">Cuidado: essas configurações afetam todos os usuários no sistema e podem tornar o sistema mais vulnerável a um ataque mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="740f4-272">Caution: These settings affect all users on the system and they can make the system more vulnerable to a malicious attack.</span></span> <span data-ttu-id="740f4-273">Tome cuidado ao fazer essas alterações.</span><span class="sxs-lookup"><span data-stu-id="740f4-273">Use caution when making these changes.</span></span>

- <span data-ttu-id="740f4-274">Windows Vista, Windows 7, Windows 8:</span><span class="sxs-lookup"><span data-stu-id="740f4-274">Windows Vista, Windows 7, Windows 8:</span></span>

  <span data-ttu-id="740f4-275">Crie a seguinte entrada de registro e, em seguida, defina seu valor como 1: LocalAccountTokenFilterPolicy em ` HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`</span><span class="sxs-lookup"><span data-stu-id="740f4-275">Create the following registry entry, and then set its value to 1: LocalAccountTokenFilterPolicy in ` HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`</span></span>

  <span data-ttu-id="740f4-276">Você pode usar o seguinte comando do PowerShell para adicionar essa entrada:</span><span class="sxs-lookup"><span data-stu-id="740f4-276">You can use the following PowerShell command to add this entry:</span></span>

    ```powershell
    $parameters = @{
      Path='HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System'
      Name='LocalAccountTokenFilterPolicy'
      propertyType='DWord'
      Value=1
    }
    New-ItemProperty @parameters
    ```

- <span data-ttu-id="740f4-277">Windows Server 2003, Windows Server 2008, Windows Server 2012, Windows Server 2012 R2:</span><span class="sxs-lookup"><span data-stu-id="740f4-277">Windows Server 2003, Windows Server 2008, Windows Server 2012, Windows Server 2012 R2:</span></span>

  <span data-ttu-id="740f4-278">Nenhuma alteração é necessária porque a configuração padrão da política "acesso à rede: modelo de compartilhamento e segurança para contas locais" é "clássica".</span><span class="sxs-lookup"><span data-stu-id="740f4-278">No changes are needed because the default setting of the "Network Access: Sharing and security model for local accounts" policy is "Classic".</span></span> <span data-ttu-id="740f4-279">Verifique a configuração caso ela tenha sido alterada.</span><span class="sxs-lookup"><span data-stu-id="740f4-279">Verify the setting in case it has changed.</span></span>

### <a name="can-i-run-remote-commands-on-a-computer-in-another-domain"></a><span data-ttu-id="740f4-280">Posso executar comandos remotos em um computador em outro domínio?</span><span class="sxs-lookup"><span data-stu-id="740f4-280">Can I run remote commands on a computer in another domain?</span></span>

<span data-ttu-id="740f4-281">Sim.</span><span class="sxs-lookup"><span data-stu-id="740f4-281">Yes.</span></span> <span data-ttu-id="740f4-282">Normalmente, os comandos são executados sem erros, embora talvez seja necessário usar o parâmetro **Credential** dos `Invoke-Command` `New-PSSession` cmdlets, ou `Enter-PSSession` para fornecer as credenciais de um membro do grupo Administradores no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="740f4-282">Typically, the commands run without error, although you might need to use the **Credential** parameter of the `Invoke-Command`, `New-PSSession`, or `Enter-PSSession` cmdlets to provide the credentials of a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="740f4-283">Isso às vezes é necessário mesmo quando o usuário atual é membro do grupo Administradores nos computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="740f4-283">This is sometimes required even when the current user is a member of the Administrators group on the local and remote computers.</span></span>

<span data-ttu-id="740f4-284">No entanto, se o computador remoto não estiver em um domínio no qual o computador local confia, talvez o computador remoto não consiga autenticar as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="740f4-284">However, if the remote computer is not in a domain that the local computer trusts, the remote computer might not be able to authenticate the user's credentials.</span></span>

<span data-ttu-id="740f4-285">Para habilitar a autenticação, use o comando a seguir para adicionar o computador remoto à lista de hosts confiáveis para o computador local no WinRM.</span><span class="sxs-lookup"><span data-stu-id="740f4-285">To enable authentication, use the following command to add the remote computer to the list of trusted hosts for the local computer in WinRM.</span></span> <span data-ttu-id="740f4-286">Digite o comando no prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="740f4-286">Type the command at the PowerShell prompt.</span></span>

```powershell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value <Remote-computer-name>
```

<span data-ttu-id="740f4-287">Por exemplo, para adicionar o computador Server01 à lista de hosts confiáveis no computador local, digite o seguinte comando no prompt do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="740f4-287">For example, to add the Server01 computer to the list of trusted hosts on the local computer, type the following command at the PowerShell prompt:</span></span>

```powershell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value Server01
```

### <a name="does-powershell-support-remoting-over-ssh"></a><span data-ttu-id="740f4-288">O PowerShell dá suporte a comunicação remota por SSH?</span><span class="sxs-lookup"><span data-stu-id="740f4-288">Does PowerShell support remoting over SSH?</span></span>

<span data-ttu-id="740f4-289">Sim.</span><span class="sxs-lookup"><span data-stu-id="740f4-289">Yes.</span></span> <span data-ttu-id="740f4-290">Para obter mais informações, consulte [comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="740f4-290">For more information, see [PowerShell remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

## <a name="see-also"></a><span data-ttu-id="740f4-291">Confira também</span><span class="sxs-lookup"><span data-stu-id="740f4-291">See also</span></span>

[<span data-ttu-id="740f4-292">about_Remote</span><span class="sxs-lookup"><span data-stu-id="740f4-292">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="740f4-293">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="740f4-293">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="740f4-294">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="740f4-294">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="740f4-295">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="740f4-295">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)

[<span data-ttu-id="740f4-296">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="740f4-296">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="740f4-297">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="740f4-297">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="740f4-298">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="740f4-298">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
