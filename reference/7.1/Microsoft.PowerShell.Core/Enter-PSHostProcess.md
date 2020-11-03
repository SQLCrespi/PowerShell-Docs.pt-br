---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pshostprocess?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSHostProcess
ms.openlocfilehash: 14f6173e318c6abd223ddff85a3694cfaac75c93
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2020
ms.locfileid: "93195076"
---
# <span data-ttu-id="23c75-103">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="23c75-103">Enter-PSHostProcess</span></span>

## <span data-ttu-id="23c75-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="23c75-104">SYNOPSIS</span></span>
<span data-ttu-id="23c75-105">Conecta-se a e entra em uma sessão interativa com um processo local.</span><span class="sxs-lookup"><span data-stu-id="23c75-105">Connects to and enters into an interactive session with a local process.</span></span>

## <span data-ttu-id="23c75-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="23c75-106">SYNTAX</span></span>

### <span data-ttu-id="23c75-107">ProcessIdParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="23c75-107">ProcessIdParameterSet (Default)</span></span>

```
Enter-PSHostProcess [-Id] <Int32> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="23c75-108">ProcessParameterSet</span><span class="sxs-lookup"><span data-stu-id="23c75-108">ProcessParameterSet</span></span>

```
Enter-PSHostProcess [-Process] <Process> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="23c75-109">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="23c75-109">ProcessNameParameterSet</span></span>

```
Enter-PSHostProcess [-Name] <String> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="23c75-110">PSHostProcessInfoParameterSet</span><span class="sxs-lookup"><span data-stu-id="23c75-110">PSHostProcessInfoParameterSet</span></span>

```
Enter-PSHostProcess [-HostProcessInfo] <PSHostProcessInfo> [[-AppDomainName] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="23c75-111">PipeNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="23c75-111">PipeNameParameterSet</span></span>

```
Enter-PSHostProcess -CustomPipeName <String> [<CommonParameters>]
```

## <span data-ttu-id="23c75-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="23c75-112">DESCRIPTION</span></span>

<span data-ttu-id="23c75-113">O `Enter-PSHostProcess` cmdlet se conecta e entra em uma sessão interativa com um processo local.</span><span class="sxs-lookup"><span data-stu-id="23c75-113">The `Enter-PSHostProcess` cmdlet connects to and enters into an interactive session with a local process.</span></span> <span data-ttu-id="23c75-114">A partir do PowerShell 6,2, esse cmdlet tem suporte em plataformas que não são do Windows.</span><span class="sxs-lookup"><span data-stu-id="23c75-114">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

<span data-ttu-id="23c75-115">Em vez de criar um novo processo para hospedar o PowerShell e executar uma sessão remota, a sessão remota e interativa é executada em um processo existente que já está executando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23c75-115">Instead of creating a new process to host PowerShell and run a remote session, the remote, interactive session is run in an existing process that is already running PowerShell.</span></span> <span data-ttu-id="23c75-116">Quando você estiver interagindo com uma sessão remota em um processo especificado, poderá enumerar os Runspaces em execução e, em seguida, selecionar um runspace para depurar executando o `Debug-Runspace` ou o `Enable-RunspaceDebug` .</span><span class="sxs-lookup"><span data-stu-id="23c75-116">When you are interacting with a remote session on a specified process, you can enumerate running runspaces, and then select a runspace to debug by running either `Debug-Runspace` or `Enable-RunspaceDebug`.</span></span>

<span data-ttu-id="23c75-117">O processo que você deseja inserir deve estar hospedando o PowerShell (System.Management.Automation.dll).</span><span class="sxs-lookup"><span data-stu-id="23c75-117">The process that you want to enter must be hosting PowerShell (System.Management.Automation.dll).</span></span>
<span data-ttu-id="23c75-118">Você deve ser membro do grupo Administradores no computador em que o processo é encontrado ou deve ser o usuário que está executando o script que iniciou o processo.</span><span class="sxs-lookup"><span data-stu-id="23c75-118">You must be either a member of the Administrators group on the computer on which the process is found, or you must be the user who is running the script that started the process.</span></span>

<span data-ttu-id="23c75-119">Depois que você selecionar um runspace para depurar, uma sessão de depuração remota será aberta para o runspace se estiver executando um comando no momento ou for interrompido no depurador.</span><span class="sxs-lookup"><span data-stu-id="23c75-119">After you have selected a runspace to debug, a remote debug session is opened for the runspace if it is either currently running a command or is stopped in the debugger.</span></span> <span data-ttu-id="23c75-120">Em seguida, você pode depurar o script do runspace da mesma forma que depuraria outros scripts de sessão remota.</span><span class="sxs-lookup"><span data-stu-id="23c75-120">You can then debug the runspace script in the same way you would debug other remote session scripts.</span></span>

<span data-ttu-id="23c75-121">Desanexar de uma sessão de depuração e, em seguida, a sessão interativa com o processo, executando Exit duas vezes ou parar a execução do script executando o comando Quit do depurador existente.</span><span class="sxs-lookup"><span data-stu-id="23c75-121">Detach from a debugging session, and then the interactive session with the process, by running exit twice, or stop script execution by running the existing debugger quit command.</span></span>

<span data-ttu-id="23c75-122">Se você especificar um processo usando o parâmetro **Name** , e houver apenas um processo encontrado com o nome especificado, o processo será inserido.</span><span class="sxs-lookup"><span data-stu-id="23c75-122">If you specify a process by using the **Name** parameter, and there is only one process found with the specified name, the process is entered.</span></span> <span data-ttu-id="23c75-123">Se mais de um processo com o nome especificado for encontrado, o PowerShell retornará um erro e listará todos os processos encontrados com o nome especificado.</span><span class="sxs-lookup"><span data-stu-id="23c75-123">If more than one process with the specified name is found, PowerShell returns an error, and lists all processes found with the specified name.</span></span>

<span data-ttu-id="23c75-124">Para dar suporte à anexação a processos em computadores remotos, o `Enter-PSHostProcess` cmdlet é habilitado em um computador remoto especificado, para que você possa anexar a um processo local dentro de uma sessão remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23c75-124">To support attaching to processes on remote computers, the `Enter-PSHostProcess` cmdlet is enabled in a specified remote computer, so that you can attach to a local process within a remote PowerShell session.</span></span>

## <span data-ttu-id="23c75-125">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="23c75-125">EXAMPLES</span></span>

### <span data-ttu-id="23c75-126">Exemplo 1: iniciar a depuração de um runspace dentro do processo do ISE do PowerShell</span><span class="sxs-lookup"><span data-stu-id="23c75-126">Example 1: Start debugging a runspace within the PowerShell ISE process</span></span>

<span data-ttu-id="23c75-127">Neste exemplo, você executa `Enter-PSHostProcess` de dentro do console do PowerShell para entrar no processo do ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23c75-127">In this example, you run `Enter-PSHostProcess` from within the PowerShell console to enter the PowerShell ISE process.</span></span> <span data-ttu-id="23c75-128">Na sessão interativa resultante, você pode encontrar um runspace que deseja depurar executando `Get-Runspace` e, em seguida, depurar o runspace.</span><span class="sxs-lookup"><span data-stu-id="23c75-128">In the resulting interactive session, you can find a runspace that you want to debug by running `Get-Runspace`, and then debug the runspace.</span></span>

```
PS C:\> Enter-PSHostProcess -Name powershell_ise
[Process:1520]: PS C:\Test\Documents>

Next, get available runspaces within the process you have entered.
PS C:\> [Process:1520]: PS C:\>  Get-Runspace
Id    Name          InstanceId                               State           Availability
--    -------       -----------                              ------          -------------
1     Runspace1     2d91211d-9cce-42f0-ab0e-71ac258b32b5     Opened          Available
2     Runspace2     a3855043-cb16-424a-a616-685360c3763b     Opened          RemoteDebug
3     MyLocalRS     2236dbd8-2105-4dec-a15a-a27d0bfaacb5     Opened          LocalDebug
4     MyRunspace    771356e9-8c44-4b70-9de5-dd17cb41e48e     Opened          Busy
5     Runspace8     3e517382-a97a-49ba-9c3c-fd21f6664288     Broken          None

The runspace objects returned by Get-Runspace also have a NoteProperty called ScriptStackTrace of
the running command stack, if available.Next, debug runspace ID 4, that is running another user's
long-running script. From the list returned from Get-Runspace, note that the runspace state is
Opened, and Availability is Busy, meaning that the runspace is still running the long-running
script.

PS C:\> [Process:1520]: PS C:\>  (Get-Runspace -Id 4).ScriptStackTrace
Command                    Arguments                           Location
-------                    ---------                           --------
MyModuleWorkflowF1         {}                                  TestNoFile3.psm1: line 6
WFTest1                    {}                                  TestNoFile2.ps1: line 14
TestNoFile2.ps1            {}                                  TestNoFile2.ps1: line 22
<ScriptBlock>              {}                                  <No file>

Start an interactive debugging session with this runspace by running the Debug-Runspace cmdlet.

PS C:\> [Process: 1520]: PS C:\>  Debug-Runspace -Id 4
Hit Line breakpoint on 'C:\TestWFVar1.ps1:83'

At C:\TestWFVar1.ps1:83 char:1
+ $scriptVar = "Script Variable"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

[Process: 1520]: [RSDBG: 4]: PS C:\> >

After you are finished debugging, allow the script to continue running without the debugger attached
by running the exit debugger command. Alternatively, you can quit the debugger with the q or Stop
commands.

PS C:\> [Process:346]: [RSDBG: 3]: PS C:\> > exit
[Process:1520]: PS C:\>

When you are finished working in the process, exit the process by running the Exit-PSHostProcess
cmdlet. This returns you to the PS C:\> prompt.

PS C:\> [Process:1520]: PS C:\>  Exit-PSHostProcess
PS C:\>
```

## <span data-ttu-id="23c75-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="23c75-129">PARAMETERS</span></span>

### <span data-ttu-id="23c75-130">-AppDomainname</span><span class="sxs-lookup"><span data-stu-id="23c75-130">-AppDomainName</span></span>

<span data-ttu-id="23c75-131">Especifica um nome de domínio de aplicativo para se conectar a se omitido, usa **defaultappdomain** .</span><span class="sxs-lookup"><span data-stu-id="23c75-131">Specifies an application domain name to connect to if omitted, uses **DefaultAppDomain** .</span></span> <span data-ttu-id="23c75-132">Use `Get-PSHostProcessInfo` para exibir os nomes de domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="23c75-132">Use `Get-PSHostProcessInfo` to display the application domain names.</span></span>

```yaml
Type: System.String
Parameter Sets: ProcessIdParameterSet, ProcessParameterSet, ProcessNameParameterSet, PSHostProcessInfoParameterSet
Aliases:

Required: False
Position: 1
Default value: DefaultAppDomain
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23c75-133">-HostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="23c75-133">-HostProcessInfo</span></span>

<span data-ttu-id="23c75-134">Especifica um objeto **PSHostProcessInfo** que pode ser conectado ao PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23c75-134">Specifies a **PSHostProcessInfo** object that can be connected to with PowerShell.</span></span> <span data-ttu-id="23c75-135">Use `Get-PSHostProcessInfo` para obter o objeto.</span><span class="sxs-lookup"><span data-stu-id="23c75-135">Use `Get-PSHostProcessInfo` to get the object.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.PSHostProcessInfo
Parameter Sets: PSHostProcessInfoParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="23c75-136">-Id</span><span class="sxs-lookup"><span data-stu-id="23c75-136">-Id</span></span>

<span data-ttu-id="23c75-137">Especifica um processo pela ID do processo.</span><span class="sxs-lookup"><span data-stu-id="23c75-137">Specifies a process by the process ID.</span></span> <span data-ttu-id="23c75-138">Para obter uma ID de processo, execute o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="23c75-138">To get a process ID, run the `Get-Process` cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ProcessIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23c75-139">-Name</span><span class="sxs-lookup"><span data-stu-id="23c75-139">-Name</span></span>

<span data-ttu-id="23c75-140">Especifica um processo pelo nome do processo.</span><span class="sxs-lookup"><span data-stu-id="23c75-140">Specifies a process by the process name.</span></span> <span data-ttu-id="23c75-141">Para obter um nome de processo, execute o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="23c75-141">To get a process name, run the `Get-Process` cmdlet.</span></span> <span data-ttu-id="23c75-142">Você também pode obter nomes de processo na caixa de diálogo Propriedades de um processo no Gerenciador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="23c75-142">You can also get process names from the Properties dialog box of a process in Task Manager.</span></span>

```yaml
Type: System.String
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23c75-143">-Processo</span><span class="sxs-lookup"><span data-stu-id="23c75-143">-Process</span></span>

<span data-ttu-id="23c75-144">Especifica um processo pelo objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="23c75-144">Specifies a process by the process object.</span></span> <span data-ttu-id="23c75-145">A maneira mais simples de usar esse parâmetro é salvar os resultados de um `Get-Process` comando que retorne o processo que você deseja inserir em uma variável e, em seguida, especificar a variável como o valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="23c75-145">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

```yaml
Type: System.Diagnostics.Process
Parameter Sets: ProcessParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="23c75-146">-CustomPipeName</span><span class="sxs-lookup"><span data-stu-id="23c75-146">-CustomPipeName</span></span>

<span data-ttu-id="23c75-147">Obtém ou define o nome do pipe nomeado personalizado ao qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="23c75-147">Gets or sets the custom named pipe name to connect to.</span></span> <span data-ttu-id="23c75-148">Normalmente, isso é usado em conjunto com o `pwsh -CustomPipeName` .</span><span class="sxs-lookup"><span data-stu-id="23c75-148">This is usually used in conjunction with `pwsh -CustomPipeName`.</span></span>

<span data-ttu-id="23c75-149">Esse parâmetro foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="23c75-149">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.String
Parameter Sets: PipeNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23c75-150">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="23c75-150">CommonParameters</span></span>

<span data-ttu-id="23c75-151">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="23c75-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="23c75-152">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="23c75-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="23c75-153">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="23c75-153">INPUTS</span></span>

### <span data-ttu-id="23c75-154">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="23c75-154">System.Diagnostics.Process</span></span>

## <span data-ttu-id="23c75-155">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="23c75-155">OUTPUTS</span></span>

## <span data-ttu-id="23c75-156">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="23c75-156">NOTES</span></span>

<span data-ttu-id="23c75-157">`Enter-PSHostProcess` Não é possível inserir o processo da sessão do PowerShell na qual você está executando o comando.</span><span class="sxs-lookup"><span data-stu-id="23c75-157">`Enter-PSHostProcess` cannot enter the process of the PowerShell session in which you are running the command.</span></span> <span data-ttu-id="23c75-158">No entanto, você pode inserir o processo de outra sessão do PowerShell ou uma sessão do ISE do PowerShell em execução ao mesmo tempo que a sessão em que você está executando `Enter-PSHostProcess` .</span><span class="sxs-lookup"><span data-stu-id="23c75-158">You can, however, enter the process of another PowerShell session, or a PowerShell ISE session that is running at the same time as the session in which you are running `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="23c75-159">`Enter-PSHostProcess` pode inserir somente os processos que estão hospedando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23c75-159">`Enter-PSHostProcess` can enter only those processes that are hosting PowerShell.</span></span> <span data-ttu-id="23c75-160">Ou seja, eles carregaram o mecanismo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23c75-160">That is, they have loaded the PowerShell engine.</span></span>

<span data-ttu-id="23c75-161">Para sair de um processo de dentro do processo, digite **Exit** e pressione <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="23c75-161">To exit a process from within the process, type **exit** , and then press <kbd>Enter</kbd>.</span></span>

<span data-ttu-id="23c75-162">Antes do PowerShell 7.1, a comunicação remota por SSH não dava suporte a sessões remotas de segundo salto.</span><span class="sxs-lookup"><span data-stu-id="23c75-162">Prior to PowerShell 7.1, remoting over SSH did not support second-hop remote sessions.</span></span> <span data-ttu-id="23c75-163">Essa funcionalidade estava limitada a sessões que usavam o WinRM.</span><span class="sxs-lookup"><span data-stu-id="23c75-163">This capability was limited to sessions using WinRM.</span></span> <span data-ttu-id="23c75-164">O PowerShell 7.1 permite que `Enter-PSSession` e `Enter-PSHostProcess` funcionem em qualquer sessão remota interativa.</span><span class="sxs-lookup"><span data-stu-id="23c75-164">PowerShell 7.1 allows `Enter-PSSession` and `Enter-PSHostProcess` to work from within any interactive remote session.</span></span>

## <span data-ttu-id="23c75-165">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="23c75-165">RELATED LINKS</span></span>

[<span data-ttu-id="23c75-166">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="23c75-166">Exit-PSHostProcess</span></span>](Exit-PSHostProcess.md)

[<span data-ttu-id="23c75-167">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="23c75-167">Get-PSHostProcessInfo</span></span>](Get-PSHostProcessInfo.md)

