---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pshostprocess?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSHostProcess
ms.openlocfilehash: 56b8cef1911d1365f9568483921bfb49fbc32451
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193334"
---
# <span data-ttu-id="11ca0-103">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="11ca0-103">Enter-PSHostProcess</span></span>

## <span data-ttu-id="11ca0-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="11ca0-104">SYNOPSIS</span></span>
<span data-ttu-id="11ca0-105">Conecta-se a e entra em uma sessão interativa com um processo local.</span><span class="sxs-lookup"><span data-stu-id="11ca0-105">Connects to and enters into an interactive session with a local process.</span></span>

## <span data-ttu-id="11ca0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="11ca0-106">SYNTAX</span></span>

### <span data-ttu-id="11ca0-107">ProcessIdParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="11ca0-107">ProcessIdParameterSet (Default)</span></span>

```
Enter-PSHostProcess [-Id] <Int32> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="11ca0-108">ProcessParameterSet</span><span class="sxs-lookup"><span data-stu-id="11ca0-108">ProcessParameterSet</span></span>

```
Enter-PSHostProcess [-Process] <Process> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="11ca0-109">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="11ca0-109">ProcessNameParameterSet</span></span>

```
Enter-PSHostProcess [-Name] <String> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="11ca0-110">PSHostProcessInfoParameterSet</span><span class="sxs-lookup"><span data-stu-id="11ca0-110">PSHostProcessInfoParameterSet</span></span>

```
Enter-PSHostProcess [-HostProcessInfo] <PSHostProcessInfo> [[-AppDomainName] <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="11ca0-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="11ca0-111">DESCRIPTION</span></span>

<span data-ttu-id="11ca0-112">O `Enter-PSHostProcess` cmdlet se conecta e entra em uma sessão interativa com um processo local.</span><span class="sxs-lookup"><span data-stu-id="11ca0-112">The `Enter-PSHostProcess` cmdlet connects to and enters into an interactive session with a local process.</span></span>

<span data-ttu-id="11ca0-113">Em vez de criar um novo processo para hospedar o PowerShell e executar uma sessão remota, a sessão remota e interativa é executada em um processo existente que já está executando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11ca0-113">Instead of creating a new process to host PowerShell and run a remote session, the remote, interactive session is run in an existing process that is already running PowerShell.</span></span> <span data-ttu-id="11ca0-114">Quando você estiver interagindo com uma sessão remota em um processo especificado, poderá enumerar os Runspaces em execução e, em seguida, selecionar um runspace para depurar executando o `Debug-Runspace` ou o `Enable-RunspaceDebug` .</span><span class="sxs-lookup"><span data-stu-id="11ca0-114">When you are interacting with a remote session on a specified process, you can enumerate running runspaces, and then select a runspace to debug by running either `Debug-Runspace` or `Enable-RunspaceDebug`.</span></span>

<span data-ttu-id="11ca0-115">O processo que você deseja inserir deve estar hospedando o PowerShell (System.Management.Automation.dll).</span><span class="sxs-lookup"><span data-stu-id="11ca0-115">The process that you want to enter must be hosting PowerShell (System.Management.Automation.dll).</span></span>
<span data-ttu-id="11ca0-116">Você deve ser membro do grupo Administradores no computador em que o processo é encontrado ou deve ser o usuário que está executando o script que iniciou o processo.</span><span class="sxs-lookup"><span data-stu-id="11ca0-116">You must be either a member of the Administrators group on the computer on which the process is found, or you must be the user who is running the script that started the process.</span></span>

<span data-ttu-id="11ca0-117">Depois que você selecionar um runspace para depurar, uma sessão de depuração remota será aberta para o runspace se estiver executando um comando no momento ou for interrompido no depurador.</span><span class="sxs-lookup"><span data-stu-id="11ca0-117">After you have selected a runspace to debug, a remote debug session is opened for the runspace if it is either currently running a command or is stopped in the debugger.</span></span> <span data-ttu-id="11ca0-118">Em seguida, você pode depurar o script do runspace da mesma forma que depuraria outros scripts de sessão remota.</span><span class="sxs-lookup"><span data-stu-id="11ca0-118">You can then debug the runspace script in the same way you would debug other remote session scripts.</span></span>

<span data-ttu-id="11ca0-119">Desanexar de uma sessão de depuração e, em seguida, a sessão interativa com o processo, executando Exit duas vezes ou parar a execução do script executando o comando Quit do depurador existente.</span><span class="sxs-lookup"><span data-stu-id="11ca0-119">Detach from a debugging session, and then the interactive session with the process, by running exit twice, or stop script execution by running the existing debugger quit command.</span></span>

<span data-ttu-id="11ca0-120">Se você especificar um processo usando o parâmetro **Name** , e houver apenas um processo encontrado com o nome especificado, o processo será inserido.</span><span class="sxs-lookup"><span data-stu-id="11ca0-120">If you specify a process by using the **Name** parameter, and there is only one process found with the specified name, the process is entered.</span></span> <span data-ttu-id="11ca0-121">Se mais de um processo com o nome especificado for encontrado, o PowerShell retornará um erro e listará todos os processos encontrados com o nome especificado.</span><span class="sxs-lookup"><span data-stu-id="11ca0-121">If more than one process with the specified name is found, PowerShell returns an error, and lists all processes found with the specified name.</span></span>

<span data-ttu-id="11ca0-122">Para dar suporte à anexação a processos em computadores remotos, o `Enter-PSHostProcess` cmdlet é habilitado em um computador remoto especificado, para que você possa anexar a um processo local dentro de uma sessão remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11ca0-122">To support attaching to processes on remote computers, the `Enter-PSHostProcess` cmdlet is enabled in a specified remote computer, so that you can attach to a local process within a remote PowerShell session.</span></span>

## <span data-ttu-id="11ca0-123">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="11ca0-123">EXAMPLES</span></span>

### <span data-ttu-id="11ca0-124">Exemplo 1: iniciar a depuração de um runspace dentro do processo do ISE do PowerShell</span><span class="sxs-lookup"><span data-stu-id="11ca0-124">Example 1: Start debugging a runspace within the PowerShell ISE process</span></span>

<span data-ttu-id="11ca0-125">Neste exemplo, você executa `Enter-PSHostProcess` de dentro do console do PowerShell para entrar no processo do ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11ca0-125">In this example, you run `Enter-PSHostProcess` from within the PowerShell console to enter the PowerShell ISE process.</span></span> <span data-ttu-id="11ca0-126">Na sessão interativa resultante, você pode encontrar um runspace que deseja depurar executando `Get-Runspace` e, em seguida, depurar o runspace.</span><span class="sxs-lookup"><span data-stu-id="11ca0-126">In the resulting interactive session, you can find a runspace that you want to debug by running `Get-Runspace`, and then debug the runspace.</span></span>

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

## <span data-ttu-id="11ca0-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="11ca0-127">PARAMETERS</span></span>

### <span data-ttu-id="11ca0-128">-AppDomainname</span><span class="sxs-lookup"><span data-stu-id="11ca0-128">-AppDomainName</span></span>

<span data-ttu-id="11ca0-129">Especifica um nome de domínio de aplicativo para se conectar a se omitido, usa **defaultappdomain** .</span><span class="sxs-lookup"><span data-stu-id="11ca0-129">Specifies an application domain name to connect to if omitted, uses **DefaultAppDomain** .</span></span> <span data-ttu-id="11ca0-130">Use `Get-PSHostProcessInfo` para exibir os nomes de domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="11ca0-130">Use `Get-PSHostProcessInfo` to display the application domain names.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: DefaultAppDomain
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="11ca0-131">-HostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="11ca0-131">-HostProcessInfo</span></span>

<span data-ttu-id="11ca0-132">Especifica um objeto **PSHostProcessInfo** que pode ser conectado ao PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11ca0-132">Specifies a **PSHostProcessInfo** object that can be connected to with PowerShell.</span></span> <span data-ttu-id="11ca0-133">Use `Get-PSHostProcessInfo` para obter o objeto.</span><span class="sxs-lookup"><span data-stu-id="11ca0-133">Use `Get-PSHostProcessInfo` to get the object.</span></span>

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

### <span data-ttu-id="11ca0-134">-Id</span><span class="sxs-lookup"><span data-stu-id="11ca0-134">-Id</span></span>

<span data-ttu-id="11ca0-135">Especifica um processo pela ID do processo.</span><span class="sxs-lookup"><span data-stu-id="11ca0-135">Specifies a process by the process ID.</span></span> <span data-ttu-id="11ca0-136">Para obter uma ID de processo, execute o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="11ca0-136">To get a process ID, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="11ca0-137">-Name</span><span class="sxs-lookup"><span data-stu-id="11ca0-137">-Name</span></span>

<span data-ttu-id="11ca0-138">Especifica um processo pelo nome do processo.</span><span class="sxs-lookup"><span data-stu-id="11ca0-138">Specifies a process by the process name.</span></span> <span data-ttu-id="11ca0-139">Para obter um nome de processo, execute o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="11ca0-139">To get a process name, run the `Get-Process` cmdlet.</span></span> <span data-ttu-id="11ca0-140">Você também pode obter nomes de processo na caixa de diálogo Propriedades de um processo no Gerenciador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="11ca0-140">You can also get process names from the Properties dialog box of a process in Task Manager.</span></span>

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

### <span data-ttu-id="11ca0-141">-Processo</span><span class="sxs-lookup"><span data-stu-id="11ca0-141">-Process</span></span>

<span data-ttu-id="11ca0-142">Especifica um processo pelo objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="11ca0-142">Specifies a process by the process object.</span></span> <span data-ttu-id="11ca0-143">A maneira mais simples de usar esse parâmetro é salvar os resultados de um `Get-Process` comando que retorne o processo que você deseja inserir em uma variável e, em seguida, especificar a variável como o valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="11ca0-143">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

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

### <span data-ttu-id="11ca0-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="11ca0-144">CommonParameters</span></span>

<span data-ttu-id="11ca0-145">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="11ca0-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="11ca0-146">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="11ca0-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="11ca0-147">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="11ca0-147">INPUTS</span></span>

### <span data-ttu-id="11ca0-148">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="11ca0-148">System.Diagnostics.Process</span></span>

## <span data-ttu-id="11ca0-149">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="11ca0-149">OUTPUTS</span></span>

## <span data-ttu-id="11ca0-150">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="11ca0-150">NOTES</span></span>

<span data-ttu-id="11ca0-151">`Enter-PSHostProcess` Não é possível inserir o processo da sessão do PowerShell na qual você está executando o comando.</span><span class="sxs-lookup"><span data-stu-id="11ca0-151">`Enter-PSHostProcess` cannot enter the process of the PowerShell session in which you are running the command.</span></span> <span data-ttu-id="11ca0-152">No entanto, você pode inserir o processo de outra sessão do PowerShell ou uma sessão do ISE do PowerShell em execução ao mesmo tempo que a sessão em que você está executando `Enter-PSHostProcess` .</span><span class="sxs-lookup"><span data-stu-id="11ca0-152">You can, however, enter the process of another PowerShell session, or a PowerShell ISE session that is running at the same time as the session in which you are running `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="11ca0-153">`Enter-PSHostProcess` pode inserir somente os processos que estão hospedando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11ca0-153">`Enter-PSHostProcess` can enter only those processes that are hosting PowerShell.</span></span> <span data-ttu-id="11ca0-154">Ou seja, eles carregaram o mecanismo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11ca0-154">That is, they have loaded the PowerShell engine.</span></span>

<span data-ttu-id="11ca0-155">Para sair de um processo de dentro do processo, digite **Exit** e pressione <kbd>Enter</kbd>.</span><span class="sxs-lookup"><span data-stu-id="11ca0-155">To exit a process from within the process, type **exit** , and then press <kbd>Enter</kbd>.</span></span>

## <span data-ttu-id="11ca0-156">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="11ca0-156">RELATED LINKS</span></span>

[<span data-ttu-id="11ca0-157">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="11ca0-157">Exit-PSHostProcess</span></span>](Exit-PSHostProcess.md)

[<span data-ttu-id="11ca0-158">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="11ca0-158">Get-PSHostProcessInfo</span></span>](Get-PSHostProcessInfo.md)
