---
description: Descreve como executar comandos remotos no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote
ms.openlocfilehash: d88521eeb2a5a4cd1f7d9e6303b4814b5a1c0bb6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195834"
---
# <a name="about-remote"></a><span data-ttu-id="26ddc-104">Sobre o remoto</span><span class="sxs-lookup"><span data-stu-id="26ddc-104">About Remote</span></span>

## <a name="short-description"></a><span data-ttu-id="26ddc-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="26ddc-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="26ddc-106">Descreve como executar comandos remotos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26ddc-106">Describes how to run remote commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="26ddc-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="26ddc-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="26ddc-108">Você pode executar comandos remotos em um único computador ou em vários computadores usando uma conexão temporária ou persistente.</span><span class="sxs-lookup"><span data-stu-id="26ddc-108">You can run remote commands on a single computer or on multiple computers by using a temporary or persistent connection.</span></span> <span data-ttu-id="26ddc-109">Você também pode iniciar uma sessão interativa com um único computador remoto.</span><span class="sxs-lookup"><span data-stu-id="26ddc-109">You can also start an interactive session with a single remote computer.</span></span>

<span data-ttu-id="26ddc-110">Este tópico fornece uma série de exemplos para mostrar como executar diferentes tipos de comando remoto.</span><span class="sxs-lookup"><span data-stu-id="26ddc-110">This topic provides a series of examples to show you how to run different types of remote command.</span></span> <span data-ttu-id="26ddc-111">Depois de tentar esses comandos básicos, leia os tópicos da ajuda que descrevem cada cmdlet que é usado nesses comandos.</span><span class="sxs-lookup"><span data-stu-id="26ddc-111">After you try these basic commands, read the Help topics that describe each cmdlet that is used in these commands.</span></span> <span data-ttu-id="26ddc-112">Os tópicos fornecem os detalhes e explicam como você pode modificar os comandos para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="26ddc-112">The topics provide the details and explain how you can modify the commands to meet your needs.</span></span>

<span data-ttu-id="26ddc-113">Observação: para usar a comunicação remota do PowerShell, os computadores locais e remotos devem ser configurados para comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="26ddc-113">Note: To use PowerShell remoting, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="26ddc-114">Para obter mais informações, consulte [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26ddc-114">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

## <a name="how-to-start-an-interactive-session-enter-pssession"></a><span data-ttu-id="26ddc-115">COMO INICIAR UMA SESSÃO INTERATIVA (ENTER-PSSESSION)</span><span class="sxs-lookup"><span data-stu-id="26ddc-115">HOW TO START AN INTERACTIVE SESSION (ENTER-PSSESSION)</span></span>

<span data-ttu-id="26ddc-116">A maneira mais fácil de executar comandos remotos é iniciar uma sessão interativa com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="26ddc-116">The easiest way to run remote commands is to start an interactive session with a remote computer.</span></span>

<span data-ttu-id="26ddc-117">Quando a sessão é iniciada, os comandos digitados são executados no computador remoto, assim como se você os digitou diretamente no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="26ddc-117">When the session starts, the commands that you type run on the remote computer, just as though you typed them directly on the remote computer.</span></span> <span data-ttu-id="26ddc-118">Você pode se conectar a apenas um computador em cada sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="26ddc-118">You can connect to only one computer in each interactive session.</span></span>

<span data-ttu-id="26ddc-119">Para iniciar uma sessão interativa, use o cmdlet Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="26ddc-119">To start an interactive session, use the Enter-PSSession cmdlet.</span></span> <span data-ttu-id="26ddc-120">O comando a seguir inicia uma sessão interativa com o computador Server01:</span><span class="sxs-lookup"><span data-stu-id="26ddc-120">The following command starts an interactive session with the Server01 computer:</span></span>

```powershell
Enter-PSSession Server01
```

<span data-ttu-id="26ddc-121">O prompt de comando é alterado para indicar que você está conectado ao computador Server01.</span><span class="sxs-lookup"><span data-stu-id="26ddc-121">The command prompt changes to indicate that you are connected to the Server01 computer.</span></span>

```
Server01\PS>
```

<span data-ttu-id="26ddc-122">Agora, você pode digitar comandos no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="26ddc-122">Now, you can type commands on the Server01 computer.</span></span>

<span data-ttu-id="26ddc-123">Para encerrar a sessão interativa, digite:</span><span class="sxs-lookup"><span data-stu-id="26ddc-123">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="26ddc-124">Para obter mais informações, consulte Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="26ddc-124">For more information, see Enter-PSSession.</span></span>

## <a name="how-to-use-cmdlets-that-have-a-computername-parameter-to-get-remote-data"></a><span data-ttu-id="26ddc-125">COMO USAR CMDLETS QUE TÊM UM PARÂMETRO COMPUTERNAME PARA OBTER DADOS REMOTOS</span><span class="sxs-lookup"><span data-stu-id="26ddc-125">HOW TO USE CMDLETS THAT HAVE A COMPUTERNAME PARAMETER TO GET REMOTE DATA</span></span>

<span data-ttu-id="26ddc-126">Vários cmdlets têm um parâmetro ComputerName que permite que você obtenha objetos de computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="26ddc-126">Several cmdlets have a ComputerName parameter that lets you get objects from remote computers.</span></span>

<span data-ttu-id="26ddc-127">Como esses cmdlets não usam a comunicação remota do PowerShell baseada no WS-Management, você pode usar o parâmetro ComputerName desses cmdlets em qualquer computador que esteja executando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26ddc-127">Because these cmdlets do not use WS-Management-based PowerShell remoting, you can use the ComputerName parameter of these cmdlets on any computer that is running PowerShell.</span></span> <span data-ttu-id="26ddc-128">Os computadores não precisam ser configurados para comunicação remota do PowerShell e os computadores não precisam atender aos requisitos do sistema para comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="26ddc-128">The computers do not have to be configured for PowerShell remoting, and the computers do not have to meet the system requirements for remoting.</span></span>

<span data-ttu-id="26ddc-129">Os cmdlets a seguir têm um parâmetro ComputerName:</span><span class="sxs-lookup"><span data-stu-id="26ddc-129">The following cmdlets have a ComputerName parameter:</span></span>

```
Clear-EventLog    Limit-EventLog
Get-Counter       New-EventLog
Get-EventLog      Remove-EventLog
Get-HotFix        Restart-Computer
Get-Process       Show-EventLog
Get-Service       Stop-Computer
Get-WinEvent      Test-Connection
Get-WmiObject     Write-EventLog
```

<span data-ttu-id="26ddc-130">Por exemplo, o comando a seguir obtém os serviços no computador remoto Server01:</span><span class="sxs-lookup"><span data-stu-id="26ddc-130">For example, the following command gets the services on the Server01 remote computer:</span></span>

```powershell
Get-Service -ComputerName Server01
```

<span data-ttu-id="26ddc-131">Normalmente, os cmdlets que oferecem suporte a comunicação remota sem configuração especial têm um parâmetro **ComputerName** e não têm um parâmetro **Session** .</span><span class="sxs-lookup"><span data-stu-id="26ddc-131">Typically, cmdlets that support remoting without special configuration have a **ComputerName** parameter and do not have a **Session** parameter.</span></span> <span data-ttu-id="26ddc-132">Para localizar esses cmdlets em sua sessão, digite:</span><span class="sxs-lookup"><span data-stu-id="26ddc-132">To find these cmdlets in your session, type:</span></span>

```powershell
Get-Command | Where-Object {
  $_.Parameters.Keys -contains 'ComputerName' -and
  $_.Parameters.Keys -notcontains 'Session'
}
```

## <a name="how-to-run-a-remote-command"></a><span data-ttu-id="26ddc-133">COMO EXECUTAR UM COMANDO REMOTO</span><span class="sxs-lookup"><span data-stu-id="26ddc-133">HOW TO RUN A REMOTE COMMAND</span></span>

<span data-ttu-id="26ddc-134">Para executar outros comandos em computadores remotos, use o cmdlet Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="26ddc-134">To run other commands on remote computers, use the Invoke-Command cmdlet.</span></span>

<span data-ttu-id="26ddc-135">Para executar um único comando ou alguns comandos não relacionados, use o parâmetro ComputerName de Invoke-Command para especificar os computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="26ddc-135">To run a single command or a few unrelated commands, use the ComputerName parameter of Invoke-Command to specify the remote computers.</span></span> <span data-ttu-id="26ddc-136">Use o parâmetro ScriptBlock para especificar o comando.</span><span class="sxs-lookup"><span data-stu-id="26ddc-136">Use the ScriptBlock parameter to specify the command.</span></span>

<span data-ttu-id="26ddc-137">Por exemplo, o comando a seguir executa um comando Get-Culture no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="26ddc-137">For example, the following command runs a Get-Culture command on the Server01 computer.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Culture}
```

<span data-ttu-id="26ddc-138">O parâmetro ComputerName foi projetado para a situação em que você executa um único comando ou vários comandos não relacionados em um ou vários computadores.</span><span class="sxs-lookup"><span data-stu-id="26ddc-138">The ComputerName parameter is designed for situation in which you run a single command or several unrelated commands on one or many computers.</span></span> <span data-ttu-id="26ddc-139">Para estabelecer uma conexão persistente com um computador remoto, use o parâmetro Session.</span><span class="sxs-lookup"><span data-stu-id="26ddc-139">To establish a persistent connection to a remote computer, use the Session parameter.</span></span>

## <a name="how-to-create-a-persistent-connection-pssession"></a><span data-ttu-id="26ddc-140">COMO CRIAR UMA CONEXÃO PERSISTENTE (PSSESSION)</span><span class="sxs-lookup"><span data-stu-id="26ddc-140">HOW TO CREATE A PERSISTENT CONNECTION (PSSESSION)</span></span>

<span data-ttu-id="26ddc-141">Quando você usa o parâmetro ComputerName do cmdlet Invoke-Command, o Windows PowerShell estabelece uma conexão apenas para o comando.</span><span class="sxs-lookup"><span data-stu-id="26ddc-141">When you use the ComputerName parameter of the Invoke-Command cmdlet, Windows PowerShell establishes a connection just for the command.</span></span> <span data-ttu-id="26ddc-142">Em seguida, fecha a conexão quando o comando for concluído.</span><span class="sxs-lookup"><span data-stu-id="26ddc-142">Then, it closes the connection when the command is complete.</span></span> <span data-ttu-id="26ddc-143">Todas as variáveis ou funções definidas no comando são perdidas.</span><span class="sxs-lookup"><span data-stu-id="26ddc-143">Any variables or functions that are defined in the command are lost.</span></span>

<span data-ttu-id="26ddc-144">Para criar uma conexão persistente com um computador remoto, use o cmdlet New-PSSession.</span><span class="sxs-lookup"><span data-stu-id="26ddc-144">To create a persistent connection to a remote computer, use the New-PSSession cmdlet.</span></span> <span data-ttu-id="26ddc-145">Por exemplo, o comando a seguir cria PSSessions nos computadores Server01 e Server02 e, em seguida, salva as PSSessions na variável $s.</span><span class="sxs-lookup"><span data-stu-id="26ddc-145">For example, the following command creates PSSessions on the Server01 and Server02 computers and then saves the PSSessions in the $s variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
```

## <a name="how-to-run-commands-in-a-pssession"></a><span data-ttu-id="26ddc-146">COMO EXECUTAR COMANDOS EM UMA PSSESSION</span><span class="sxs-lookup"><span data-stu-id="26ddc-146">HOW TO RUN COMMANDS IN A PSSESSION</span></span>

<span data-ttu-id="26ddc-147">Com uma PSSession, você pode executar uma série de comandos remotos que compartilham dados, como funções, aliases e os valores de variáveis.</span><span class="sxs-lookup"><span data-stu-id="26ddc-147">With a PSSession, you can run a series of remote commands that share data, like functions, aliases, and the values of variables.</span></span> <span data-ttu-id="26ddc-148">Para executar comandos em uma PSSession, use o parâmetro Session do cmdlet Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="26ddc-148">To run commands in a PSSession, use the Session parameter of the Invoke-Command cmdlet.</span></span>

<span data-ttu-id="26ddc-149">Por exemplo, o comando a seguir usa o cmdlet Invoke-Command para executar um comando Get-Process em PSSessions nos computadores Server01 e Server02.</span><span class="sxs-lookup"><span data-stu-id="26ddc-149">For example, the following command uses the Invoke-Command cmdlet to run a Get-Process command in the PSSessions on the Server01 and Server02 computers.</span></span>
<span data-ttu-id="26ddc-150">O comando salva os processos em uma variável $p em cada PSSession.</span><span class="sxs-lookup"><span data-stu-id="26ddc-150">The command saves the processes in a $p variable in each PSSession.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process}
```

<span data-ttu-id="26ddc-151">Como a PSSession usa uma conexão persistente, você pode executar outro comando na mesma PSSession que usa a variável $p.</span><span class="sxs-lookup"><span data-stu-id="26ddc-151">Because the PSSession uses a persistent connection, you can run another command in the same PSSession that uses the $p variable.</span></span> <span data-ttu-id="26ddc-152">O comando a seguir conta o número de processos salvos em $p.</span><span class="sxs-lookup"><span data-stu-id="26ddc-152">The following command counts the number of processes saved in $p.</span></span>

```powershell
Invoke-Command -Session $s -ScriptBlock {$p.count}
```

## <a name="how-to-run-a-remote-command-on-multiple-computers"></a><span data-ttu-id="26ddc-153">COMO EXECUTAR UM COMANDO REMOTO EM VÁRIOS COMPUTADORES</span><span class="sxs-lookup"><span data-stu-id="26ddc-153">HOW TO RUN A REMOTE COMMAND ON MULTIPLE COMPUTERS</span></span>

<span data-ttu-id="26ddc-154">Para executar um comando remoto em vários computadores, digite todos os nomes de computador no valor do parâmetro ComputerName de Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="26ddc-154">To run a remote command on multiple computers, type all of the computer names in the value of the ComputerName parameter of Invoke-Command.</span></span> <span data-ttu-id="26ddc-155">Separe os nomes com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="26ddc-155">Separate the names with commas.</span></span>

<span data-ttu-id="26ddc-156">Por exemplo, o comando a seguir executa um comando Get-Culture em três computadores:</span><span class="sxs-lookup"><span data-stu-id="26ddc-156">For example, the following command runs a Get-Culture command on three computers:</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture}
```

<span data-ttu-id="26ddc-157">Você também pode executar um comando em várias PSSessions.</span><span class="sxs-lookup"><span data-stu-id="26ddc-157">You can also run a command in multiple PSSessions.</span></span> <span data-ttu-id="26ddc-158">Os comandos a seguir criam PSSessions nos computadores Server01, Server02 e Server03 e, em seguida, executam um comando Get-Culture em cada uma das PSSessions.</span><span class="sxs-lookup"><span data-stu-id="26ddc-158">The following commands create PSSessions on the Server01, Server02, and Server03 computers and then run a Get-Culture command in each of the PSSessions.</span></span>

```powershell
$s = New-PSSession -ComputerName S1, S2, S3
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

<span data-ttu-id="26ddc-159">Para incluir a lista de computadores do computador local, digite o nome do computador local, digite um ponto (.) ou digite "localhost".</span><span class="sxs-lookup"><span data-stu-id="26ddc-159">To include the local computer list of computers, type the name of the local computer, type a dot (.), or type  "localhost".</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3, localhost -ScriptBlock {Get-Culture}
```

## <a name="how-to-run-a-script-on-remote-computers"></a><span data-ttu-id="26ddc-160">COMO EXECUTAR UM SCRIPT EM COMPUTADORES REMOTOS</span><span class="sxs-lookup"><span data-stu-id="26ddc-160">HOW TO RUN A SCRIPT ON REMOTE COMPUTERS</span></span>

<span data-ttu-id="26ddc-161">Para executar um script local em computadores remotos, use o parâmetro FilePath de Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="26ddc-161">To run a local script on remote computers, use the FilePath parameter of Invoke-Command.</span></span>

<span data-ttu-id="26ddc-162">Por exemplo, o comando a seguir executa o script Sample.ps1 nos computadores S1 e S2:</span><span class="sxs-lookup"><span data-stu-id="26ddc-162">For example, the following command runs the Sample.ps1 script on the S1 and S2 computers:</span></span>

```powershell
Invoke-Command -ComputerName S1, S2 -FilePath C:\Test\Sample.ps1
```

<span data-ttu-id="26ddc-163">Os resultados do script são retornados para o computador local.</span><span class="sxs-lookup"><span data-stu-id="26ddc-163">The results of the script are returned to the local computer.</span></span> <span data-ttu-id="26ddc-164">Você não precisa copiar nenhum arquivo.</span><span class="sxs-lookup"><span data-stu-id="26ddc-164">You do not need to copy any files.</span></span>

## <a name="how-to-stop-a-remote-command"></a><span data-ttu-id="26ddc-165">COMO INTERROMPER UM COMANDO REMOTO</span><span class="sxs-lookup"><span data-stu-id="26ddc-165">HOW TO STOP A REMOTE COMMAND</span></span>

<span data-ttu-id="26ddc-166">Para interromper um comando, pressione CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="26ddc-166">To interrupt a command, press CTRL+C.</span></span> <span data-ttu-id="26ddc-167">A solicitação de interrupção é passada para o computador remoto onde ele termina o comando remoto.</span><span class="sxs-lookup"><span data-stu-id="26ddc-167">The interrupt request is passed to the remote computer where it terminates the remote command.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="26ddc-168">PARA OBTER MAIS INFORMAÇÕES</span><span class="sxs-lookup"><span data-stu-id="26ddc-168">FOR MORE INFORMATION</span></span>

- <span data-ttu-id="26ddc-169">Para obter informações sobre os requisitos de sistema para comunicação remota, consulte [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26ddc-169">For information about the system requirements for remoting, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

- <span data-ttu-id="26ddc-170">Para obter ajuda na formatação da saída remota, consulte [about_Remote_Output](about_Remote_Output.md).</span><span class="sxs-lookup"><span data-stu-id="26ddc-170">For help in formatting remote output, see [about_Remote_Output](about_Remote_Output.md).</span></span>

- <span data-ttu-id="26ddc-171">Para obter informações sobre como funciona a comunicação remota, como gerenciar dados remotos, configurações especiais, problemas de segurança e outras perguntas frequentes, consulte [about_Remote_FAQ](about_Remote_FAQ.md).</span><span class="sxs-lookup"><span data-stu-id="26ddc-171">For information about how remoting works, how to manage remote data, special configurations, security issues, and other frequently asked questions, see [about_Remote_FAQ](about_Remote_FAQ.md).</span></span>

- <span data-ttu-id="26ddc-172">Para obter ajuda na resolução de erros de comunicação remota, consulte about_Remote_Troubleshooting.</span><span class="sxs-lookup"><span data-stu-id="26ddc-172">For help in resolving remoting errors, see about_Remote_Troubleshooting.</span></span>

- <span data-ttu-id="26ddc-173">Para obter informações sobre PSSessions e conexões persistentes, consulte [about_PSSessions](about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="26ddc-173">For information about PSSessions and persistent connections, see [about_PSSessions](about_PSSessions.md).</span></span>

- <span data-ttu-id="26ddc-174">Para obter informações sobre trabalhos em segundo plano do PowerShell, consulte [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="26ddc-174">For information about PowerShell background jobs, see [about_Jobs](about_Jobs.md).</span></span>

## <a name="keywords"></a><span data-ttu-id="26ddc-175">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="26ddc-175">KEYWORDS</span></span>

<span data-ttu-id="26ddc-176">about_Remoting</span><span class="sxs-lookup"><span data-stu-id="26ddc-176">about_Remoting</span></span>

## <a name="see-also"></a><span data-ttu-id="26ddc-177">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="26ddc-177">SEE ALSO</span></span>

[<span data-ttu-id="26ddc-178">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="26ddc-178">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="26ddc-179">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="26ddc-179">about_Remote_Disconnected_Sessions</span></span>](about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="26ddc-180">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="26ddc-180">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="26ddc-181">about_Remote_FAQ</span><span class="sxs-lookup"><span data-stu-id="26ddc-181">about_Remote_FAQ</span></span>](about_Remote_FAQ.md)

[<span data-ttu-id="26ddc-182">about_Remote_TroubleShooting</span><span class="sxs-lookup"><span data-stu-id="26ddc-182">about_Remote_TroubleShooting</span></span>](about_Remote_TroubleShooting.md)

[<span data-ttu-id="26ddc-183">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="26ddc-183">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="26ddc-184">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="26ddc-184">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="26ddc-185">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="26ddc-185">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="26ddc-186">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="26ddc-186">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

