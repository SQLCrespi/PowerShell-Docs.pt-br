---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/debug-runspace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Runspace
ms.openlocfilehash: 96282d28249f28744cf7dff436fa2e6c601c10ca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194510"
---
# <span data-ttu-id="959ba-103">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="959ba-103">Debug-Runspace</span></span>

## <span data-ttu-id="959ba-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="959ba-104">SYNOPSIS</span></span>
<span data-ttu-id="959ba-105">Inicia uma sessão de depuração interativa com um runspace.</span><span class="sxs-lookup"><span data-stu-id="959ba-105">Starts an interactive debugging session with a runspace.</span></span>

## <span data-ttu-id="959ba-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="959ba-106">SYNTAX</span></span>

### <span data-ttu-id="959ba-107">RunspaceParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="959ba-107">RunspaceParameterSet (Default)</span></span>

```
Debug-Runspace [-Runspace] <Runspace> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="959ba-108">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="959ba-108">NameParameterSet</span></span>

```
Debug-Runspace [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="959ba-109">IdParameterSet</span><span class="sxs-lookup"><span data-stu-id="959ba-109">IdParameterSet</span></span>

```
Debug-Runspace [-Id] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="959ba-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="959ba-110">InstanceIdParameterSet</span></span>

```
Debug-Runspace [-InstanceId] <Guid> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="959ba-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="959ba-111">DESCRIPTION</span></span>

<span data-ttu-id="959ba-112">O `Debug-Runspace` cmdlet inicia uma sessão de depuração interativa com um runspace ativo local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="959ba-112">The `Debug-Runspace` cmdlet starts an interactive debugging session with a local or remote active runspace.</span></span> <span data-ttu-id="959ba-113">Você pode encontrar um runspace que deseja depurar pela primeira vez `Get-Process` para localizar os processos associados ao PowerShell, depois `Enter-PSHostProcess` com a ID do processo especificada no parâmetro **ID** para anexar ao processo e, em seguida, `Get-Runspace` para listar os Runspaces dentro do processo de host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="959ba-113">You can find a runspace that you want to debug by first running `Get-Process` to find processes associated with PowerShell, then `Enter-PSHostProcess` with the process ID specified in the **Id** parameter to attach to the process, and then `Get-Runspace` to list runspaces within the PowerShell host process.</span></span>

<span data-ttu-id="959ba-114">Depois de selecionar um runspace para depurar, se o runspace estiver executando um comando ou script no momento, ou se o script tiver sido interrompido em um ponto de interrupção, o PowerShell abrirá uma sessão de depurador remoto para o runspace.</span><span class="sxs-lookup"><span data-stu-id="959ba-114">After you have selected a runspace to debug, if the runspace is currently running a command or script, or if the script has stopped at a breakpoint, PowerShell opens a remote debugger session for the runspace.</span></span> <span data-ttu-id="959ba-115">Você pode depurar o script de runspace da mesma forma que os scripts de sessão remota são depurados.</span><span class="sxs-lookup"><span data-stu-id="959ba-115">You can debug the runspace script in the same way remote session scripts are debugged.</span></span>

<span data-ttu-id="959ba-116">Você só poderá anexar a um processo de host do PowerShell se você for um administrador no computador que está executando o processo ou se você estiver executando o script que deseja depurar.</span><span class="sxs-lookup"><span data-stu-id="959ba-116">You can only attach to a PowerShell host process if you are an administrator on the computer that is running the process, or you are running the script that you want to debug.</span></span> <span data-ttu-id="959ba-117">Além disso, você não pode inserir o processo de host que está executando a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="959ba-117">Also, you cannot enter the host process that is running the current PowerShell session.</span></span> <span data-ttu-id="959ba-118">Você só pode inserir um processo de host que esteja executando uma sessão do PowerShell diferente.</span><span class="sxs-lookup"><span data-stu-id="959ba-118">You can only enter a host process that is running a different PowerShell session.</span></span>

## <span data-ttu-id="959ba-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="959ba-119">EXAMPLES</span></span>

### <span data-ttu-id="959ba-120">Exemplo 1: Depurar um runspace remoto</span><span class="sxs-lookup"><span data-stu-id="959ba-120">Example 1: Debug a remote runspace</span></span>

```
PS C:\> Get-Process -ComputerName "WS10TestServer" -Name "*powershell*"

Handles      WS(K)   VM(M)      CPU(s)    Id  ProcessName
-------      -----   -----      ------    --  -----------
    377      69912     63     2.09      2420  powershell
    399     123396    829     4.48      1152  powershell_ise

PS C:\> Enter-PSSession -ComputerName "WS10TestServer"
[WS10TestServer]:PS C:\> Enter-PSHostProcess -Id 1152
[WS10TestServer:][Process:1152]: PS C:\Users\Test\Documents> Get-Runspace

Id Name            ComputerName    Type          State         Availability
-- ----            ------------    ----          -----         ------------
 1 Runspace1       WS10TestServer  Remote        Opened        Available
 2 RemoteHost      WS10TestServer  Remote        Opened        Busy

PS C:\> [WS10TestServer][Process:1152]: PS C:\Users\Test\Documents> Debug-Runspace -Id 2

Hit Line breakpoint on 'C:\TestWFVar1.ps1:83'
At C:\TestWFVar1.ps1:83 char:1
+ $scriptVar = "Script Variable"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[Process:1152]: [RSDBG: 2]: PS C:\> >
```

<span data-ttu-id="959ba-121">Neste exemplo, você depura um runspace que está aberto em um computador remoto, WS10TestServer.</span><span class="sxs-lookup"><span data-stu-id="959ba-121">In this example, you debug a runspace that is open on a remote computer, WS10TestServer.</span></span> <span data-ttu-id="959ba-122">Na primeira linha do comando, você executa `Get-Process` o no computador remoto e filtra os processos de host do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="959ba-122">In the first line of the command, you run `Get-Process` on the remote computer, and filter for Windows PowerShell host processes.</span></span> <span data-ttu-id="959ba-123">Neste exemplo, você deseja depurar a ID de processo 1152, o processo de host ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="959ba-123">In this example, you want to debug process ID 1152, the Windows PowerShell ISE host process.</span></span>

<span data-ttu-id="959ba-124">No segundo comando, você executa `Enter-PSSession` para abrir uma sessão remota no WS10TestServer.</span><span class="sxs-lookup"><span data-stu-id="959ba-124">In the second command, you run `Enter-PSSession` to open a remote session on WS10TestServer.</span></span> <span data-ttu-id="959ba-125">No terceiro comando, você anexa o processo de host ISE do Windows PowerShell em execução no servidor remoto executando `Enter-PSHostProcess` e especificando a ID do processo de host que você obteve no primeiro comando, 1152.</span><span class="sxs-lookup"><span data-stu-id="959ba-125">In the third command, you attach to the Windows PowerShell ISE host process running on the remote server by running `Enter-PSHostProcess`, and specifying the ID of the host process that you obtained in the first command, 1152.</span></span>

<span data-ttu-id="959ba-126">No quarto comando, você lista os Runspaces disponíveis para a ID de processo 1152 executando `Get-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="959ba-126">In the fourth command, you list available runspaces for process ID 1152 by running `Get-Runspace`.</span></span>
<span data-ttu-id="959ba-127">Você anota o número de ID do runspace ocupado; Ele está executando um script que você deseja depurar.</span><span class="sxs-lookup"><span data-stu-id="959ba-127">You note the ID number of the Busy runspace; it is running a script that you want to debug.</span></span>

<span data-ttu-id="959ba-128">No último comando, você começa a depurar um runspace aberto que está executando um script, TestWFVar1.ps1, executando `Debug-Runspace` e identificando o runspace por sua ID, 2, adicionando o parâmetro **ID** .</span><span class="sxs-lookup"><span data-stu-id="959ba-128">In the last command, you start debugging an opened runspace that is running a script, TestWFVar1.ps1, by running `Debug-Runspace`, and identifying the runspace by its ID, 2, by adding the **Id** parameter.</span></span> <span data-ttu-id="959ba-129">Como há um ponto de interrupção no script, o depurador é aberto.</span><span class="sxs-lookup"><span data-stu-id="959ba-129">Because there's a breakpoint in the script, the debugger opens.</span></span>

## <span data-ttu-id="959ba-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="959ba-130">PARAMETERS</span></span>

### <span data-ttu-id="959ba-131">-Id</span><span class="sxs-lookup"><span data-stu-id="959ba-131">-Id</span></span>

<span data-ttu-id="959ba-132">Especifica o número de ID de um runspace.</span><span class="sxs-lookup"><span data-stu-id="959ba-132">Specifies the ID number of a runspace.</span></span> <span data-ttu-id="959ba-133">Você pode executar `Get-Runspace` para mostrar IDs de runspace.</span><span class="sxs-lookup"><span data-stu-id="959ba-133">You can run `Get-Runspace` to show runspace IDs.</span></span>

```yaml
Type: System.Int32
Parameter Sets: IdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="959ba-134">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="959ba-134">-InstanceId</span></span>

<span data-ttu-id="959ba-135">Especifica um runspace por sua ID de instância, um GUID que você pode mostrar executando `Get-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="959ba-135">Specifies a runspace by its instance ID, a GUID that you can show by running `Get-Runspace`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="959ba-136">-Name</span><span class="sxs-lookup"><span data-stu-id="959ba-136">-Name</span></span>

<span data-ttu-id="959ba-137">Especifica um runspace por seu nome.</span><span class="sxs-lookup"><span data-stu-id="959ba-137">Specifies a runspace by its name.</span></span> <span data-ttu-id="959ba-138">Você pode executar `Get-Runspace` para mostrar os nomes de Runspaces.</span><span class="sxs-lookup"><span data-stu-id="959ba-138">You can run `Get-Runspace` to show the names of runspaces.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="959ba-139">-Runspace</span><span class="sxs-lookup"><span data-stu-id="959ba-139">-Runspace</span></span>

<span data-ttu-id="959ba-140">Especifica um objeto de runspace.</span><span class="sxs-lookup"><span data-stu-id="959ba-140">Specifies a runspace object.</span></span> <span data-ttu-id="959ba-141">A maneira mais simples de fornecer um valor para esse parâmetro é especificar uma variável que contenha os resultados de um comando filtrado `Get-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="959ba-141">The simplest way to provide a value for this parameter is to specify a variable that contains the results of a filtered `Get-Runspace` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.Runspace
Parameter Sets: RunspaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="959ba-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="959ba-142">-Confirm</span></span>

<span data-ttu-id="959ba-143">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="959ba-143">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="959ba-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="959ba-144">-WhatIf</span></span>

<span data-ttu-id="959ba-145">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="959ba-145">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="959ba-146">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="959ba-146">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="959ba-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="959ba-147">CommonParameters</span></span>

<span data-ttu-id="959ba-148">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="959ba-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="959ba-149">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="959ba-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="959ba-150">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="959ba-150">INPUTS</span></span>

### <span data-ttu-id="959ba-151">System. Management. Automation. Runspaces. runspace</span><span class="sxs-lookup"><span data-stu-id="959ba-151">System.Management.Automation.Runspaces.Runspace</span></span>

<span data-ttu-id="959ba-152">Você pode canalizar os resultados de um `Get-Runspace` comando para **debug-runspace.**</span><span class="sxs-lookup"><span data-stu-id="959ba-152">You can pipe the results of a `Get-Runspace` command to **Debug-Runspace.**</span></span>

## <span data-ttu-id="959ba-153">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="959ba-153">OUTPUTS</span></span>

## <span data-ttu-id="959ba-154">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="959ba-154">NOTES</span></span>

<span data-ttu-id="959ba-155">`Debug-Runspace` funciona em Runspaces que estão no estado aberto.</span><span class="sxs-lookup"><span data-stu-id="959ba-155">`Debug-Runspace` works on runspaces that are in the Opened state.</span></span> <span data-ttu-id="959ba-156">Se um estado de runspace mudar de aberto para outro Estado, esse runspace será removido automaticamente da lista em execução.</span><span class="sxs-lookup"><span data-stu-id="959ba-156">If a runspace state changes from Opened to another state, that runspace is automatically removed from the running list.</span></span> <span data-ttu-id="959ba-157">Um runspace será adicionado à lista em execução somente se ele atender aos critérios a seguir.</span><span class="sxs-lookup"><span data-stu-id="959ba-157">A runspace is added to the running list only if it meets the following criteria.</span></span>

- <span data-ttu-id="959ba-158">Se for proveniente de Invoke-Command; ou seja, ele tem uma `Invoke-Command` ID de GUID.</span><span class="sxs-lookup"><span data-stu-id="959ba-158">If it is coming from Invoke-Command; that is, it has an `Invoke-Command` GUID ID.</span></span>
- <span data-ttu-id="959ba-159">Se estiver vindo de `Debug-Runspace` ; ou seja, ele tem uma `Debug-Runspace` ID de GUID.</span><span class="sxs-lookup"><span data-stu-id="959ba-159">If it is coming from `Debug-Runspace`; that is, it has a `Debug-Runspace` GUID ID.</span></span>
- <span data-ttu-id="959ba-160">Se ele estiver vindo de um fluxo de trabalho do PowerShell, e sua ID do job de fluxo de trabalhos for a mesma ID do trabalho do depurador ativo atual.</span><span class="sxs-lookup"><span data-stu-id="959ba-160">If it is coming from a PowerShell workflow, and its workflow job ID is the same as the current active debugger workflow job ID.</span></span>

## <span data-ttu-id="959ba-161">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="959ba-161">RELATED LINKS</span></span>

[<span data-ttu-id="959ba-162">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="959ba-162">about_Debuggers</span></span>](../Microsoft.PowerShell.Core/About/about_Debuggers.md)

[<span data-ttu-id="959ba-163">Debug-Job</span><span class="sxs-lookup"><span data-stu-id="959ba-163">Debug-Job</span></span>](../Microsoft.PowerShell.Core/Debug-Job.md)

[<span data-ttu-id="959ba-164">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="959ba-164">Get-Runspace</span></span>](Get-Runspace.md)

[<span data-ttu-id="959ba-165">Get-Process</span><span class="sxs-lookup"><span data-stu-id="959ba-165">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)

[<span data-ttu-id="959ba-166">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="959ba-166">Enter-PSHostProcess</span></span>](../Microsoft.PowerShell.Core/Enter-PSHostProcess.md)

[<span data-ttu-id="959ba-167">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="959ba-167">Enter-PSSession</span></span>](../Microsoft.PowerShell.Core/Enter-PSSession.md)
