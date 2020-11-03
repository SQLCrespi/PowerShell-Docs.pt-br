---
description: Descreve como executar e gravar scripts no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scripts
ms.openlocfilehash: 9b82f5c24397036e4560d3c8f84e7e403769c207
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195629"
---
# <a name="about-scripts"></a><span data-ttu-id="4943d-104">Sobre scripts</span><span class="sxs-lookup"><span data-stu-id="4943d-104">About Scripts</span></span>

## <a name="short-description"></a><span data-ttu-id="4943d-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="4943d-105">Short description</span></span>
<span data-ttu-id="4943d-106">Descreve como executar e gravar scripts no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4943d-106">Describes how to run and write scripts in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="4943d-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="4943d-107">Long description</span></span>

<span data-ttu-id="4943d-108">Um script é um arquivo de texto sem formatação que contém um ou mais comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4943d-108">A script is a plain text file that contains one or more PowerShell commands.</span></span>
<span data-ttu-id="4943d-109">Os scripts do PowerShell têm uma `.ps1` extensão de arquivo.</span><span class="sxs-lookup"><span data-stu-id="4943d-109">PowerShell scripts have a `.ps1` file extension.</span></span>

<span data-ttu-id="4943d-110">Executar um script é muito parecido com a execução de um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4943d-110">Running a script is a lot like running a cmdlet.</span></span> <span data-ttu-id="4943d-111">Você digita o caminho e o nome do arquivo do script e usa parâmetros para enviar dados e definir opções.</span><span class="sxs-lookup"><span data-stu-id="4943d-111">You type the path and file name of the script and use parameters to submit data and set options.</span></span> <span data-ttu-id="4943d-112">Você pode executar scripts em seu computador ou em uma sessão remota em um computador diferente.</span><span class="sxs-lookup"><span data-stu-id="4943d-112">You can run scripts on your computer or in a remote session on a different computer.</span></span>

<span data-ttu-id="4943d-113">Escrever um script salva um comando para uso posterior e facilita o compartilhamento com outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="4943d-113">Writing a script saves a command for later use and makes it easy to share with others.</span></span> <span data-ttu-id="4943d-114">O mais importante é que você executa os comandos simplesmente digitando o caminho do script e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="4943d-114">Most importantly, it lets you run the commands simply by typing the script path and the filename.</span></span> <span data-ttu-id="4943d-115">Os scripts podem ser tão simples quanto um único comando em um arquivo ou tão extensivo quanto um programa complexo.</span><span class="sxs-lookup"><span data-stu-id="4943d-115">Scripts can be as simple as a single command in a file or as extensive as a complex program.</span></span>

<span data-ttu-id="4943d-116">Os scripts têm recursos adicionais, como o `#Requires` Comentário especial, o uso de parâmetros, suporte para seções de dados e assinatura digital para segurança.</span><span class="sxs-lookup"><span data-stu-id="4943d-116">Scripts have additional features, such as the `#Requires` special comment, the use of parameters, support for data sections, and digital signing for security.</span></span>
<span data-ttu-id="4943d-117">Você também pode escrever tópicos de ajuda para scripts e para qualquer função no script.</span><span class="sxs-lookup"><span data-stu-id="4943d-117">You can also write Help topics for scripts and for any functions in the script.</span></span>

## <a name="how-to-run-a-script"></a><span data-ttu-id="4943d-118">Como executar um script</span><span class="sxs-lookup"><span data-stu-id="4943d-118">How to run a script</span></span>

<span data-ttu-id="4943d-119">Antes de executar um script no Windows, você precisa alterar a política de execução padrão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4943d-119">Before you can run a script on Windows, you need to change the default PowerShell execution policy.</span></span> <span data-ttu-id="4943d-120">A política de execução não se aplica ao PowerShell em execução em plataformas que não são do Windows.</span><span class="sxs-lookup"><span data-stu-id="4943d-120">Execution policy does not apply to PowerShell running on non-Windows platforms.</span></span>

<span data-ttu-id="4943d-121">A política de execução padrão, `Restricted` , impede que todos os scripts sejam executados, incluindo scripts que você escreve no computador local.</span><span class="sxs-lookup"><span data-stu-id="4943d-121">The default execution policy, `Restricted`, prevents all scripts from running, including scripts that you write on the local computer.</span></span> <span data-ttu-id="4943d-122">Para obter mais informações, consulte [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="4943d-122">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="4943d-123">A política de execução é salva no registro, portanto, você precisa alterá-la apenas uma vez em cada computador.</span><span class="sxs-lookup"><span data-stu-id="4943d-123">The execution policy is saved in the registry, so you need to change it only once on each computer.</span></span>

<span data-ttu-id="4943d-124">Para alterar a política de execução, use o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="4943d-124">To change the execution policy, use the following procedure.</span></span>

<span data-ttu-id="4943d-125">No prompt de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="4943d-125">At the command prompt, type:</span></span>

```powershell
Set-ExecutionPolicy AllSigned
```

<span data-ttu-id="4943d-126">ou</span><span class="sxs-lookup"><span data-stu-id="4943d-126">or</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

<span data-ttu-id="4943d-127">A alteração entra em vigor imediatamente.</span><span class="sxs-lookup"><span data-stu-id="4943d-127">The change is effective immediately.</span></span>

<span data-ttu-id="4943d-128">Para executar um script, digite o nome completo e o caminho completo para o arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="4943d-128">To run a script, type the full name and the full path to the script file.</span></span>

<span data-ttu-id="4943d-129">Por exemplo, para executar o script de Get-ServiceLog.ps1 no diretório C:\Scripts, digite:</span><span class="sxs-lookup"><span data-stu-id="4943d-129">For example, to run the Get-ServiceLog.ps1 script in the C:\Scripts directory, type:</span></span>

```powershell
C:\Scripts\Get-ServiceLog.ps1
```

<span data-ttu-id="4943d-130">Para executar um script no diretório atual, digite o caminho para o diretório atual ou use um ponto para representar o diretório atual, seguido por uma barra invertida de caminho ( `.\` ).</span><span class="sxs-lookup"><span data-stu-id="4943d-130">To run a script in the current directory, type the path to the current directory, or use a dot to represent the current directory, followed by a path backslash (`.\`).</span></span>

<span data-ttu-id="4943d-131">Por exemplo, para executar o script de ServicesLog.ps1 no diretório local, digite:</span><span class="sxs-lookup"><span data-stu-id="4943d-131">For example, to run the ServicesLog.ps1 script in the local directory, type:</span></span>

```powershell
.\Get-ServiceLog.ps1
```

<span data-ttu-id="4943d-132">Se o script tiver parâmetros, digite os parâmetros e os valores de parâmetro após o nome de arquivo do script.</span><span class="sxs-lookup"><span data-stu-id="4943d-132">If the script has parameters, type the parameters and parameter values after the script filename.</span></span>

<span data-ttu-id="4943d-133">Por exemplo, o comando a seguir usa o parâmetro ServiceName do script Get-ServiceLog para solicitar um log da atividade do serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="4943d-133">For example, the following command uses the ServiceName parameter of the Get-ServiceLog script to request a log of WinRM service activity.</span></span>

```powershell
.\Get-ServiceLog.ps1 -ServiceName WinRM
```

<span data-ttu-id="4943d-134">Como um recurso de segurança, o PowerShell não executa scripts quando você clica duas vezes no ícone de script no explorador de arquivos ou quando você digita o nome do script sem um caminho completo, mesmo quando o script está no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="4943d-134">As a security feature, PowerShell does not run scripts when you double-click the script icon in File Explorer or when you type the script name without a full path, even when the script is in the current directory.</span></span> <span data-ttu-id="4943d-135">Para obter mais informações sobre como executar comandos e scripts no PowerShell, consulte [about_Command_Precedence](about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="4943d-135">For more information about running commands and scripts in PowerShell, see [about_Command_Precedence](about_Command_Precedence.md).</span></span>

### <a name="run-with-powershell"></a><span data-ttu-id="4943d-136">Executar com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="4943d-136">Run with PowerShell</span></span>

<span data-ttu-id="4943d-137">A partir do PowerShell 3,0, você pode executar scripts no explorador de arquivos.</span><span class="sxs-lookup"><span data-stu-id="4943d-137">Beginning in PowerShell 3.0, you can run scripts from File Explorer.</span></span>

<span data-ttu-id="4943d-138">Para usar o recurso "executar com o PowerShell":</span><span class="sxs-lookup"><span data-stu-id="4943d-138">To use the "Run with PowerShell" feature:</span></span>

<span data-ttu-id="4943d-139">Execute o explorador de arquivos, clique com o botão direito do mouse no nome de arquivo do script e selecione "executar com o PowerShell".</span><span class="sxs-lookup"><span data-stu-id="4943d-139">Run File Explorer, right-click the script filename and then select "Run with PowerShell".</span></span>

<span data-ttu-id="4943d-140">O recurso "executar com o PowerShell" foi projetado para executar scripts que não têm parâmetros obrigatórios e não retornam a saída para o prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="4943d-140">The "Run with PowerShell" feature is designed to run scripts that do not have required parameters and do not return output to the command prompt.</span></span>

<span data-ttu-id="4943d-141">Para obter mais informações, consulte [about_Run_With_PowerShell](about_Run_With_PowerShell.md).</span><span class="sxs-lookup"><span data-stu-id="4943d-141">For more information, see [about_Run_With_PowerShell](about_Run_With_PowerShell.md).</span></span>

### <a name="running-scripts-on-other-computers"></a><span data-ttu-id="4943d-142">Executando scripts em outros computadores</span><span class="sxs-lookup"><span data-stu-id="4943d-142">Running scripts on other computers</span></span>

<span data-ttu-id="4943d-143">Para executar um script em um ou mais computadores remotos, use o parâmetro **FilePath** do `Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4943d-143">To run a script on one or more remote computers, use the **FilePath** parameter of the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="4943d-144">Insira o caminho e o nome de arquivo do script como o valor do parâmetro **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="4943d-144">Enter the path and filename of the script as the value of the **FilePath** parameter.</span></span> <span data-ttu-id="4943d-145">O script deve residir no computador local ou em um diretório que o computador local possa acessar.</span><span class="sxs-lookup"><span data-stu-id="4943d-145">The script must reside on the local computer or in a directory that the local computer can access.</span></span>

<span data-ttu-id="4943d-146">O comando a seguir executa o `Get-ServiceLog.ps1` script nos computadores remotos chamados Server01 e Server02.</span><span class="sxs-lookup"><span data-stu-id="4943d-146">The following command runs the `Get-ServiceLog.ps1` script on the remote computers named Server01 and Server02.</span></span>

```powershell
Invoke-Command -ComputerName Server01,Server02 -FilePath `
  C:\Scripts\Get-ServiceLog.ps1
```

## <a name="get-help-for-scripts"></a><span data-ttu-id="4943d-147">Obter ajuda para scripts</span><span class="sxs-lookup"><span data-stu-id="4943d-147">Get help for scripts</span></span>

<span data-ttu-id="4943d-148">O cmdlet Get-Help Obtém os tópicos de ajuda para scripts, bem como para cmdlets e outros tipos de comandos.</span><span class="sxs-lookup"><span data-stu-id="4943d-148">The Get-Help cmdlet gets the help topics for scripts as well as for cmdlets and other types of commands.</span></span> <span data-ttu-id="4943d-149">Para obter o tópico da ajuda para um script, digite `Get-Help` seguido pelo caminho e nome do arquivo do script.</span><span class="sxs-lookup"><span data-stu-id="4943d-149">To get the help topic for a script, type `Get-Help` followed by the path and filename of the script.</span></span> <span data-ttu-id="4943d-150">Se o caminho do script estiver em sua `Path` variável de ambiente, você poderá omitir o caminho.</span><span class="sxs-lookup"><span data-stu-id="4943d-150">If the script path is in your `Path` environment variable, you can omit the path.</span></span>

<span data-ttu-id="4943d-151">Por exemplo, para obter ajuda para o script de ServicesLog.ps1, digite:</span><span class="sxs-lookup"><span data-stu-id="4943d-151">For example, to get help for the ServicesLog.ps1 script, type:</span></span>

```powershell
get-help C:\admin\scripts\ServicesLog.ps1
```

## <a name="how-to-write-a-script"></a><span data-ttu-id="4943d-152">Como escrever um script</span><span class="sxs-lookup"><span data-stu-id="4943d-152">How to write a script</span></span>

<span data-ttu-id="4943d-153">Um script pode conter qualquer comando válido do PowerShell, incluindo comandos únicos, comandos que usam o pipeline, funções e estruturas de controle, como instruções IF e loops for.</span><span class="sxs-lookup"><span data-stu-id="4943d-153">A script can contain any valid PowerShell commands, including single commands, commands that use the pipeline, functions, and control structures such as If statements and For loops.</span></span>

<span data-ttu-id="4943d-154">Para gravar um script, abra um novo arquivo em um editor de texto, digite os comandos e salve-os em um arquivo com um nome de arquivo válido com a `.ps1` extensão.</span><span class="sxs-lookup"><span data-stu-id="4943d-154">To write a script, open a new file in a text editor, type the commands, and save them in a file with a valid filename with the `.ps1` file extension.</span></span>

<span data-ttu-id="4943d-155">O exemplo a seguir é um script simples que obtém os serviços que estão em execução no sistema atual e os salva em um arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="4943d-155">The following example is a simple script that gets the services that are running on the current system and saves them to a log file.</span></span> <span data-ttu-id="4943d-156">O nome do arquivo de log é criado a partir da data atual.</span><span class="sxs-lookup"><span data-stu-id="4943d-156">The log filename is created from the current date.</span></span>

```powershell
$date = (get-date).dayofyear
get-service | out-file "$date.log"
```

<span data-ttu-id="4943d-157">Para criar esse script, abra um editor de texto ou um editor de script, digite esses comandos e, em seguida, salve-os em um arquivo chamado `ServiceLog.ps1` .</span><span class="sxs-lookup"><span data-stu-id="4943d-157">To create this script, open a text editor or a script editor, type these commands, and then save them in a file named `ServiceLog.ps1`.</span></span>

### <a name="parameters-in-scripts"></a><span data-ttu-id="4943d-158">Parâmetros em scripts</span><span class="sxs-lookup"><span data-stu-id="4943d-158">Parameters in scripts</span></span>

<span data-ttu-id="4943d-159">Para definir parâmetros em um script, use uma instrução param.</span><span class="sxs-lookup"><span data-stu-id="4943d-159">To define parameters in a script, use a Param statement.</span></span> <span data-ttu-id="4943d-160">A `Param` instrução deve ser a primeira instrução em um script, exceto comentários e quaisquer `#Require` instruções.</span><span class="sxs-lookup"><span data-stu-id="4943d-160">The `Param` statement must be the first statement in a script, except for comments and any `#Require` statements.</span></span>

<span data-ttu-id="4943d-161">Parâmetros de script funcionam como parâmetros de função.</span><span class="sxs-lookup"><span data-stu-id="4943d-161">Script parameters work like function parameters.</span></span> <span data-ttu-id="4943d-162">Os valores de parâmetro estão disponíveis para todos os comandos no script.</span><span class="sxs-lookup"><span data-stu-id="4943d-162">The parameter values are available to all of the commands in the script.</span></span> <span data-ttu-id="4943d-163">Todos os recursos dos parâmetros de função, incluindo o atributo de parâmetro e seus argumentos nomeados, também são válidos em scripts.</span><span class="sxs-lookup"><span data-stu-id="4943d-163">All of the features of function parameters, including the Parameter attribute and its named arguments, are also valid in scripts.</span></span>

<span data-ttu-id="4943d-164">Ao executar o script, os usuários de script digitam os parâmetros após o nome do script.</span><span class="sxs-lookup"><span data-stu-id="4943d-164">When running the script, script users type the parameters after the script name.</span></span>

<span data-ttu-id="4943d-165">O exemplo a seguir mostra um `Test-Remote.ps1` script que tem um parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="4943d-165">The following example shows a `Test-Remote.ps1` script that has a **ComputerName** parameter.</span></span> <span data-ttu-id="4943d-166">Ambas as funções de script podem acessar o valor do parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="4943d-166">Both of the script functions can access the **ComputerName** parameter value.</span></span>

```powershell
param ($ComputerName = $(throw "ComputerName parameter is required."))

function CanPing {
   $error.clear()
   $tmp = test-connection $computername -erroraction SilentlyContinue

   if (!$?)
       {write-host "Ping failed: $ComputerName."; return $false}
   else
       {write-host "Ping succeeded: $ComputerName"; return $true}
}

function CanRemote {
    $s = new-pssession $computername -erroraction SilentlyContinue

    if ($s -is [System.Management.Automation.Runspaces.PSSession])
        {write-host "Remote test succeeded: $ComputerName."}
    else
        {write-host "Remote test failed: $ComputerName."}
}

if (CanPing $computername) {CanRemote $computername}
```

<span data-ttu-id="4943d-167">Para executar esse script, digite o nome do parâmetro após o nome do script.</span><span class="sxs-lookup"><span data-stu-id="4943d-167">To run this script, type the parameter name after the script name.</span></span> <span data-ttu-id="4943d-168">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4943d-168">For example:</span></span>

```powershell
C:\PS> .\test-remote.ps1 -computername Server01

Ping succeeded: Server01
Remote test failed: Server01
```

<span data-ttu-id="4943d-169">Para obter mais informações sobre a instrução param e os parâmetros de função, consulte [about_Functions](about_Functions.md) e [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="4943d-169">For more information about the Param statement and the function parameters, see [about_Functions](about_Functions.md) and [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="writing-help-for-scripts"></a><span data-ttu-id="4943d-170">Escrevendo ajuda para scripts</span><span class="sxs-lookup"><span data-stu-id="4943d-170">Writing help for scripts</span></span>

<span data-ttu-id="4943d-171">Você pode escrever um tópico da ajuda para um script usando um dos dois métodos a seguir:</span><span class="sxs-lookup"><span data-stu-id="4943d-171">You can write a help topic for a script by using either of the two following methods:</span></span>

- <span data-ttu-id="4943d-172">Comment-Based ajuda para scripts</span><span class="sxs-lookup"><span data-stu-id="4943d-172">Comment-Based Help for Scripts</span></span>

  <span data-ttu-id="4943d-173">Crie um tópico da ajuda usando palavras-chave especiais nos comentários.</span><span class="sxs-lookup"><span data-stu-id="4943d-173">Create a Help topic by using special keywords in the comments.</span></span> <span data-ttu-id="4943d-174">Para criar uma ajuda baseada em comentários para um script, os comentários devem ser colocados no início ou no final do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="4943d-174">To create comment-based Help for a script, the comments must be placed at the beginning or end of the script file.</span></span> <span data-ttu-id="4943d-175">Para obter mais informações sobre a ajuda baseada em comentários, consulte [about_Comment_Based_Help](about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="4943d-175">For more information about comment-based Help, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span>

- <span data-ttu-id="4943d-176">XML-Based ajuda para scripts</span><span class="sxs-lookup"><span data-stu-id="4943d-176">XML-Based Help  for Scripts</span></span>

  <span data-ttu-id="4943d-177">Crie um tópico de ajuda baseado em XML, como o tipo que normalmente é criado para cmdlets.</span><span class="sxs-lookup"><span data-stu-id="4943d-177">Create an XML-based Help topic, such as the type that is typically created for cmdlets.</span></span> <span data-ttu-id="4943d-178">A ajuda baseada em XML é necessária se você estiver traduzindo tópicos da ajuda em vários idiomas.</span><span class="sxs-lookup"><span data-stu-id="4943d-178">XML-based Help is required if you are translating Help topics into multiple languages.</span></span>

<span data-ttu-id="4943d-179">Para associar o script ao tópico de ajuda baseado em XML, use o. Palavra-chave de comentário da ajuda do ExternalHelp.</span><span class="sxs-lookup"><span data-stu-id="4943d-179">To associate the script with the XML-based Help topic, use the .ExternalHelp Help comment keyword.</span></span> <span data-ttu-id="4943d-180">Para obter mais informações sobre a palavra-chave ExternalHelp, consulte [about_Comment_Based_Help](about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="4943d-180">For more information about the ExternalHelp keyword, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span> <span data-ttu-id="4943d-181">Para obter mais informações sobre a ajuda baseada em XML, consulte [como gravar a ajuda do cmdlet](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span><span class="sxs-lookup"><span data-stu-id="4943d-181">For more information about XML-based help, see [How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

### <a name="returning-an-exit-value"></a><span data-ttu-id="4943d-182">Retornando um valor de saída</span><span class="sxs-lookup"><span data-stu-id="4943d-182">Returning an exit value</span></span>

<span data-ttu-id="4943d-183">Por padrão, os scripts não retornam um status de saída quando o script termina.</span><span class="sxs-lookup"><span data-stu-id="4943d-183">By default, scripts do not return an exit status when the script ends.</span></span> <span data-ttu-id="4943d-184">Você deve usar a `exit` instrução para retornar um código de saída de um script.</span><span class="sxs-lookup"><span data-stu-id="4943d-184">You must use the `exit` statement to return an exit code from a script.</span></span> <span data-ttu-id="4943d-185">Por padrão, a `exit` instrução retorna `0` .</span><span class="sxs-lookup"><span data-stu-id="4943d-185">By default, the `exit` statement returns `0`.</span></span> <span data-ttu-id="4943d-186">Você pode fornecer um valor numérico para retornar um status de saída diferente.</span><span class="sxs-lookup"><span data-stu-id="4943d-186">You can provide a numeric value to return a different exit status.</span></span> <span data-ttu-id="4943d-187">Um código de saída diferente de zero normalmente sinaliza uma falha.</span><span class="sxs-lookup"><span data-stu-id="4943d-187">A nonzero exit code typically signals a failure.</span></span>

<span data-ttu-id="4943d-188">No Windows, qualquer número entre `[int]::MinValue` e `[int]::MaxValue` é permitido.</span><span class="sxs-lookup"><span data-stu-id="4943d-188">On Windows, any number between `[int]::MinValue` and `[int]::MaxValue` is allowed.</span></span>

<span data-ttu-id="4943d-189">No UNIX, somente números positivos entre `[byte]::MinValue` (0) e `[byte]::MaxValue` (255) são permitidos.</span><span class="sxs-lookup"><span data-stu-id="4943d-189">On Unix, only positive numbers between `[byte]::MinValue` (0) and `[byte]::MaxValue` (255) are allowed.</span></span> <span data-ttu-id="4943d-190">Um número negativo no intervalo de `-1` até `-255` é automaticamente convertido em um número positivo adicionando</span><span class="sxs-lookup"><span data-stu-id="4943d-190">A negative number in the range of `-1` through `-255` is automatically translated into a positive number by adding</span></span>
256. <span data-ttu-id="4943d-191">Por exemplo, `-2` é transformado para `254` .</span><span class="sxs-lookup"><span data-stu-id="4943d-191">For example, `-2` is transformed to `254`.</span></span>

<span data-ttu-id="4943d-192">No PowerShell, a `exit` instrução define o valor da `$LASTEXITCODE` variável.</span><span class="sxs-lookup"><span data-stu-id="4943d-192">In PowerShell, the `exit` statement sets the value of the `$LASTEXITCODE` variable.</span></span> <span data-ttu-id="4943d-193">No Shell de comando do Windows (cmd.exe), a instrução Exit define o valor da `%ERRORLEVEL%` variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="4943d-193">In the Windows Command Shell (cmd.exe), the exit statement sets the value of the `%ERRORLEVEL%` environment variable.</span></span>

<span data-ttu-id="4943d-194">Qualquer argumento que não seja numérico ou fora do intervalo específico da plataforma é convertido para o valor de `0` .</span><span class="sxs-lookup"><span data-stu-id="4943d-194">Any argument that is non-numeric or outside the platform-specific range is translated to the value of `0`.</span></span>

## <a name="script-scope-and-dot-sourcing"></a><span data-ttu-id="4943d-195">Escopo do script e ponto de origem</span><span class="sxs-lookup"><span data-stu-id="4943d-195">Script scope and dot sourcing</span></span>

<span data-ttu-id="4943d-196">Cada script é executado em seu próprio escopo.</span><span class="sxs-lookup"><span data-stu-id="4943d-196">Each script runs in its own scope.</span></span> <span data-ttu-id="4943d-197">As funções, variáveis, aliases e unidades que são criadas no script existem somente no escopo do script.</span><span class="sxs-lookup"><span data-stu-id="4943d-197">The functions, variables, aliases, and drives that are created in the script exist only in the script scope.</span></span> <span data-ttu-id="4943d-198">Você não pode acessar esses itens ou seus valores no escopo no qual o script é executado.</span><span class="sxs-lookup"><span data-stu-id="4943d-198">You cannot access these items or their values in the scope in which the script runs.</span></span>

<span data-ttu-id="4943d-199">Para executar um script em um escopo diferente, você pode especificar um escopo, como global ou local, ou pode criar um ponto de origem do script.</span><span class="sxs-lookup"><span data-stu-id="4943d-199">To run a script in a different scope, you can specify a scope, such as Global or Local, or you can dot source the script.</span></span>

<span data-ttu-id="4943d-200">O recurso de fornecimento de ponto permite executar um script no escopo atual em vez de no escopo do script.</span><span class="sxs-lookup"><span data-stu-id="4943d-200">The dot sourcing feature lets you run a script in the current scope instead of in the script scope.</span></span> <span data-ttu-id="4943d-201">Quando você executa um script que tem um ponto de origem, os comandos no script são executados como se você os tivesse digitado no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="4943d-201">When you run a script that is dot sourced, the commands in the script run as though you had typed them at the command prompt.</span></span> <span data-ttu-id="4943d-202">As funções, variáveis, aliases e unidades que o script cria são criadas no escopo no qual você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="4943d-202">The functions, variables, aliases, and drives that the script creates are created in the scope in which you are working.</span></span> <span data-ttu-id="4943d-203">Depois que o script for executado, você poderá usar os itens criados e acessar seus valores em sua sessão.</span><span class="sxs-lookup"><span data-stu-id="4943d-203">After the script runs, you can use the created items and access their values in your session.</span></span>

<span data-ttu-id="4943d-204">Para um ponto de origem de um script, digite um ponto (.) e um espaço antes do caminho do script.</span><span class="sxs-lookup"><span data-stu-id="4943d-204">To dot source a script, type a dot (.) and a space before the script path.</span></span>

<span data-ttu-id="4943d-205">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4943d-205">For example:</span></span>

```powershell
. C:\scripts\UtilityFunctions.ps1
```

<span data-ttu-id="4943d-206">ou</span><span class="sxs-lookup"><span data-stu-id="4943d-206">or</span></span>

```powershell
. .\UtilityFunctions.ps1
```

<span data-ttu-id="4943d-207">Depois `UtilityFunctions.ps1` que o script é executado, as funções e variáveis que o script cria são adicionadas ao escopo atual.</span><span class="sxs-lookup"><span data-stu-id="4943d-207">After the `UtilityFunctions.ps1` script runs, the functions and variables that the script creates are added to the current scope.</span></span>

<span data-ttu-id="4943d-208">Por exemplo, o `UtilityFunctions.ps1` script cria a `New-Profile` função e a `$ProfileName` variável.</span><span class="sxs-lookup"><span data-stu-id="4943d-208">For example, the `UtilityFunctions.ps1` script creates the `New-Profile` function and the `$ProfileName` variable.</span></span>

```powershell
#In UtilityFunctions.ps1

function New-Profile
{
  Write-Host "Running New-Profile function"
  $profileName = split-path $profile -leaf

  if (test-path $profile)
    {write-error "Profile $profileName already exists on this computer."}
  else
    {new-item -type file -path $profile -force }
}
```

<span data-ttu-id="4943d-209">Se você executar o `UtilityFunctions.ps1` script em seu próprio escopo de script, a `New-Profile` função e a `$ProfileName` variável existirão somente enquanto o script estiver em execução.</span><span class="sxs-lookup"><span data-stu-id="4943d-209">If you run the `UtilityFunctions.ps1` script in its own script scope, the `New-Profile` function and the `$ProfileName` variable exist only while the script is running.</span></span> <span data-ttu-id="4943d-210">Quando o script é encerrado, a função e a variável são removidas, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="4943d-210">When the script exits, the function and variable are removed, as shown in the following example.</span></span>

```powershell
C:\PS> .\UtilityFunctions.ps1

C:\PS> New-Profile
The term 'new-profile' is not recognized as a cmdlet, function, operable
program, or script file. Verify the term and try again.
At line:1 char:12
+ new-profile <<<<
   + CategoryInfo          : ObjectNotFound: (new-profile:String) [],
   + FullyQualifiedErrorId : CommandNotFoundException

C:\PS> $profileName
C:\PS>
```

<span data-ttu-id="4943d-211">Quando você origina o script e o executa, o script cria a `New-Profile` função e a `$ProfileName` variável em sua sessão em seu escopo.</span><span class="sxs-lookup"><span data-stu-id="4943d-211">When you dot source the script and run it, the script creates the `New-Profile` function and the `$ProfileName` variable in your session in your scope.</span></span> <span data-ttu-id="4943d-212">Depois que o script for executado, você poderá usar a `New-Profile` função em sua sessão, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="4943d-212">After the script runs, you can use the `New-Profile` function in your session, as shown in the following example.</span></span>

```powershell
C:\PS> . .\UtilityFunctions.ps1

C:\PS> New-Profile

    Directory: C:\Users\juneb\Documents\WindowsPowerShell

    Mode    LastWriteTime     Length Name
    ----    -------------     ------ ----
    -a---   1/14/2009 3:08 PM      0 Microsoft.PowerShellISE_profile.ps1

C:\PS> $profileName
Microsoft.PowerShellISE_profile.ps1
```

<span data-ttu-id="4943d-213">Para obter mais informações sobre escopo, consulte about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="4943d-213">For more information about scope, see about_Scopes.</span></span>

## <a name="scripts-in-modules"></a><span data-ttu-id="4943d-214">Scripts em módulos</span><span class="sxs-lookup"><span data-stu-id="4943d-214">Scripts in modules</span></span>

<span data-ttu-id="4943d-215">Um módulo é um conjunto de recursos do PowerShell relacionados que podem ser distribuídos como uma unidade.</span><span class="sxs-lookup"><span data-stu-id="4943d-215">A module is a set of related PowerShell resources that can be distributed as a unit.</span></span> <span data-ttu-id="4943d-216">Você pode usar módulos para organizar seus scripts, funções e outros recursos.</span><span class="sxs-lookup"><span data-stu-id="4943d-216">You can use modules to organize your scripts, functions, and other resources.</span></span> <span data-ttu-id="4943d-217">Você também pode usar módulos para distribuir seu código para outras pessoas e obter código de fontes confiáveis.</span><span class="sxs-lookup"><span data-stu-id="4943d-217">You can also use modules to distribute your code to others, and to get code from trusted sources.</span></span>

<span data-ttu-id="4943d-218">Você pode incluir scripts em seus módulos ou pode criar um módulo de script, que é um módulo que consiste inteiramente ou principalmente em um script e recursos de suporte.</span><span class="sxs-lookup"><span data-stu-id="4943d-218">You can include scripts in your modules, or you can create a script module, which is a module that consists entirely or primarily of a script and supporting resources.</span></span> <span data-ttu-id="4943d-219">Um módulo de script é apenas um script com uma extensão de arquivo. psm1.</span><span class="sxs-lookup"><span data-stu-id="4943d-219">A script module is just a script with a .psm1 file extension.</span></span>

<span data-ttu-id="4943d-220">Para obter mais informações sobre módulos, consulte [about_Modules](about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="4943d-220">For more information about modules, see [about_Modules](about_Modules.md).</span></span>

## <a name="other-script-features"></a><span data-ttu-id="4943d-221">Outros recursos de script</span><span class="sxs-lookup"><span data-stu-id="4943d-221">Other script features</span></span>

<span data-ttu-id="4943d-222">O PowerShell tem muitos recursos úteis que você pode usar em scripts.</span><span class="sxs-lookup"><span data-stu-id="4943d-222">PowerShell has many useful features that you can use in scripts.</span></span>

- <span data-ttu-id="4943d-223">`#Requires` -Você pode usar uma `#Requires` instrução para impedir que um script seja executado sem módulos ou snap-ins especificados e uma versão especificada do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4943d-223">`#Requires` - You can use a `#Requires` statement to prevent a script from running without specified modules or snap-ins and a specified version of PowerShell.</span></span> <span data-ttu-id="4943d-224">Para obter mais informações, consulte about_Requires.</span><span class="sxs-lookup"><span data-stu-id="4943d-224">For more information, see about_Requires.</span></span>

- <span data-ttu-id="4943d-225">`$PSCommandPath` -Contém o caminho completo e o nome do script que está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="4943d-225">`$PSCommandPath` - Contains the full path and name of the script that is being run.</span></span> <span data-ttu-id="4943d-226">Esse parâmetro é válido em todos os scripts.</span><span class="sxs-lookup"><span data-stu-id="4943d-226">This parameter is valid in all scripts.</span></span> <span data-ttu-id="4943d-227">Essa variável automática é introduzida no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="4943d-227">This automatic variable is introduced in PowerShell 3.0.</span></span>

- <span data-ttu-id="4943d-228">`$PSScriptRoot` -Contém o diretório do qual um script está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="4943d-228">`$PSScriptRoot` - Contains the directory from which a script is being run.</span></span> <span data-ttu-id="4943d-229">No PowerShell 2,0, essa variável é válida somente em módulos de script ( `.psm1` ).</span><span class="sxs-lookup"><span data-stu-id="4943d-229">In PowerShell 2.0, this variable is valid only in script modules (`.psm1`).</span></span>
  <span data-ttu-id="4943d-230">A partir do PowerShell 3,0, ele é válido em todos os scripts.</span><span class="sxs-lookup"><span data-stu-id="4943d-230">Beginning in PowerShell 3.0, it is valid in all scripts.</span></span>

- <span data-ttu-id="4943d-231">`$MyInvocation` -A `$MyInvocation` variável automática contém informações sobre o script atual, incluindo informações sobre como ele foi iniciado ou "invocado".</span><span class="sxs-lookup"><span data-stu-id="4943d-231">`$MyInvocation` - The `$MyInvocation` automatic variable contains information about the current script, including information about how it was started or "invoked."</span></span> <span data-ttu-id="4943d-232">Você pode usar essa variável e suas propriedades para obter informações sobre o script enquanto ele está em execução.</span><span class="sxs-lookup"><span data-stu-id="4943d-232">You can use this variable and its properties to get information about the script while it is running.</span></span> <span data-ttu-id="4943d-233">Por exemplo, o `$MyInvocation` . A variável myCommand. Path contém o caminho e o nome do arquivo do script.</span><span class="sxs-lookup"><span data-stu-id="4943d-233">For example, the `$MyInvocation`.MyCommand.Path variable contains the path and filename of the script.</span></span> <span data-ttu-id="4943d-234">`$MyInvocation`. Line contém o comando que iniciou o script, incluindo todos os parâmetros e valores.</span><span class="sxs-lookup"><span data-stu-id="4943d-234">`$MyInvocation`.Line contains the command that started the script, including all parameters and values.</span></span>

  <span data-ttu-id="4943d-235">A partir do PowerShell 3,0, o `$MyInvocation` tem duas novas propriedades que fornecem informações sobre o script que chamou ou invocou o script atual.</span><span class="sxs-lookup"><span data-stu-id="4943d-235">Beginning in PowerShell 3.0, `$MyInvocation` has two new properties that provide information about the script that called or invoked the current script.</span></span> <span data-ttu-id="4943d-236">Os valores dessas propriedades são populados somente quando o chamador ou chamador é um script.</span><span class="sxs-lookup"><span data-stu-id="4943d-236">The values of these properties are populated only when the invoker or caller is a script.</span></span>

  - <span data-ttu-id="4943d-237">**PSCommandPath** contém o caminho completo e o nome do script que chamou ou invocou o script atual.</span><span class="sxs-lookup"><span data-stu-id="4943d-237">**PSCommandPath** contains the full path and name of the script that called or invoked the current script.</span></span>

  - <span data-ttu-id="4943d-238">**PSScriptRoot** contém o diretório do script que chamou ou invocou o script atual.</span><span class="sxs-lookup"><span data-stu-id="4943d-238">**PSScriptRoot** contains the directory of the script that called or invoked the current script.</span></span>

  <span data-ttu-id="4943d-239">Ao contrário `$PSCommandPath` das `$PSScriptRoot` variáveis automáticas e que contêm informações sobre o script atual, as propriedades **PSCommandPath** e **PSScriptRoot** da `$MyInvocation` variável contêm informações sobre o script que chamou o script atual.</span><span class="sxs-lookup"><span data-stu-id="4943d-239">Unlike the `$PSCommandPath` and `$PSScriptRoot` automatic variables, which contain information about the current script, the **PSCommandPath** and **PSScriptRoot** properties of the `$MyInvocation` variable contain information about the script that called the current script.</span></span>

- <span data-ttu-id="4943d-240">Seções de dados-você pode usar a `Data` palavra-chave para separar dados da lógica em scripts.</span><span class="sxs-lookup"><span data-stu-id="4943d-240">Data sections - You can use the `Data` keyword to separate data from logic in scripts.</span></span> <span data-ttu-id="4943d-241">As seções de dados também podem facilitar a localização.</span><span class="sxs-lookup"><span data-stu-id="4943d-241">Data sections can also make localization easier.</span></span> <span data-ttu-id="4943d-242">Para obter mais informações, consulte [about_Data_Sections](about_Data_Sections.md) e [about_Script_Internationalization](about_Script_Internationalization.md).</span><span class="sxs-lookup"><span data-stu-id="4943d-242">For more information, see [about_Data_Sections](about_Data_Sections.md) and [about_Script_Internationalization](about_Script_Internationalization.md).</span></span>

- <span data-ttu-id="4943d-243">Assinatura de script – você pode adicionar uma assinatura digital a um script.</span><span class="sxs-lookup"><span data-stu-id="4943d-243">Script Signing - You can add a digital signature to a script.</span></span> <span data-ttu-id="4943d-244">Dependendo da política de execução, você pode usar assinaturas digitais para restringir a execução de scripts que podem incluir comandos não seguros.</span><span class="sxs-lookup"><span data-stu-id="4943d-244">Depending on the execution policy, you can use digital signatures to restrict the running of scripts that could include unsafe commands.</span></span> <span data-ttu-id="4943d-245">Para obter mais informações, consulte [about_Execution_Policies](about_Execution_Policies.md) e [about_Signing](about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="4943d-245">For more information, see [about_Execution_Policies](about_Execution_Policies.md) and [about_Signing](about_Signing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4943d-246">Confira também</span><span class="sxs-lookup"><span data-stu-id="4943d-246">See also</span></span>

[<span data-ttu-id="4943d-247">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="4943d-247">about_Command_Precedence</span></span>](about_Command_Precedence.md)

[<span data-ttu-id="4943d-248">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="4943d-248">about_Comment_Based_Help</span></span>](about_Comment_Based_Help.md)

[<span data-ttu-id="4943d-249">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="4943d-249">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="4943d-250">about_Functions</span><span class="sxs-lookup"><span data-stu-id="4943d-250">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="4943d-251">about_Modules</span><span class="sxs-lookup"><span data-stu-id="4943d-251">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="4943d-252">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="4943d-252">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="4943d-253">about_Requires</span><span class="sxs-lookup"><span data-stu-id="4943d-253">about_Requires</span></span>](about_Requires.md)

[<span data-ttu-id="4943d-254">about_Run_With_PowerShell</span><span class="sxs-lookup"><span data-stu-id="4943d-254">about_Run_With_PowerShell</span></span>](about_Run_With_PowerShell.md)

[<span data-ttu-id="4943d-255">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="4943d-255">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="4943d-256">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="4943d-256">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="4943d-257">about_Signing</span><span class="sxs-lookup"><span data-stu-id="4943d-257">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="4943d-258">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="4943d-258">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
