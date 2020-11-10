---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 05075a00074eb69a0fe492da95c28c2ad912c291
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389038"
---
# <span data-ttu-id="f14e0-103">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="f14e0-103">Debug-Process</span></span>

## <span data-ttu-id="f14e0-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f14e0-104">SYNOPSIS</span></span>
<span data-ttu-id="f14e0-105">Depura um ou mais processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="f14e0-105">Debugs one or more processes running on the local computer.</span></span>

## <span data-ttu-id="f14e0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f14e0-106">SYNTAX</span></span>

### <span data-ttu-id="f14e0-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="f14e0-107">Name (Default)</span></span>

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f14e0-108">ID</span><span class="sxs-lookup"><span data-stu-id="f14e0-108">Id</span></span>

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f14e0-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="f14e0-109">InputObject</span></span>

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f14e0-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f14e0-110">DESCRIPTION</span></span>

<span data-ttu-id="f14e0-111">O `Debug-Process` cmdlet anexa um depurador a um ou mais processos em execução em um computador local.</span><span class="sxs-lookup"><span data-stu-id="f14e0-111">The `Debug-Process` cmdlet attaches a debugger to one or more running processes on a local computer.</span></span>
<span data-ttu-id="f14e0-112">Você pode especificar os processos por seu nome de processo ou ID de processo (PID) ou pode canalizar objetos de processo para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f14e0-112">You can specify the processes by their process name or process ID (PID), or you can pipe process objects to this cmdlet.</span></span>

<span data-ttu-id="f14e0-113">Esse cmdlet anexa o depurador que está atualmente registrado para o processo.</span><span class="sxs-lookup"><span data-stu-id="f14e0-113">This cmdlet attaches the debugger that is currently registered for the process.</span></span> <span data-ttu-id="f14e0-114">Antes de usar esse cmdlet, verifique se um depurador foi baixado e configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="f14e0-114">Before using this cmdlet, verify that a debugger is downloaded and correctly configured.</span></span>

## <span data-ttu-id="f14e0-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f14e0-115">EXAMPLES</span></span>

### <span data-ttu-id="f14e0-116">Exemplo 1: anexar um depurador a um processo no computador</span><span class="sxs-lookup"><span data-stu-id="f14e0-116">Example 1: Attach a debugger to a process on the computer</span></span>

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

<span data-ttu-id="f14e0-117">Esse comando anexa um depurador ao processo do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="f14e0-117">This command attaches a debugger to the PowerShell process on the computer.</span></span>

### <span data-ttu-id="f14e0-118">Exemplo 2: anexar um depurador a todos os processos que começam com a cadeia de caracteres especificada</span><span class="sxs-lookup"><span data-stu-id="f14e0-118">Example 2: Attach a debugger to all processes that begin with the specified string</span></span>

```
PS C:\> Debug-Process -Name "SQL*"
```

<span data-ttu-id="f14e0-119">Esse comando anexa um depurador a todos os processos que têm nomes que começam com SQL.</span><span class="sxs-lookup"><span data-stu-id="f14e0-119">This command attaches a debugger to all processes that have names that begin with SQL.</span></span>

### <span data-ttu-id="f14e0-120">Exemplo 3: anexar um depurador a vários processos</span><span class="sxs-lookup"><span data-stu-id="f14e0-120">Example 3: Attach a debugger to multiple processes</span></span>

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

<span data-ttu-id="f14e0-121">Esse comando anexa um depurador aos processos Winlogon, Explorer e Outlook.</span><span class="sxs-lookup"><span data-stu-id="f14e0-121">This command attaches a debugger to the Winlogon, Explorer, and Outlook processes.</span></span>

### <span data-ttu-id="f14e0-122">Exemplo 4: anexar um depurador a várias IDs de processo</span><span class="sxs-lookup"><span data-stu-id="f14e0-122">Example 4: Attach a debugger to multiple process IDs</span></span>

```
PS C:\> Debug-Process -Id 1132, 2028
```

<span data-ttu-id="f14e0-123">Esse comando anexa um depurador aos processos que têm as IDs de processo 1132 e 2028.</span><span class="sxs-lookup"><span data-stu-id="f14e0-123">This command attaches a debugger to the processes that have process IDs 1132 and 2028.</span></span>

### <span data-ttu-id="f14e0-124">Exemplo 5: usar Get-Process para obter um processo e, em seguida, anexar um depurador a ele</span><span class="sxs-lookup"><span data-stu-id="f14e0-124">Example 5: Use Get-Process to get a process then attach a debugger to it</span></span>

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

<span data-ttu-id="f14e0-125">Esse comando anexa um depurador aos processos do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="f14e0-125">This command attaches a debugger to the PowerShell processes on the computer.</span></span> <span data-ttu-id="f14e0-126">Ele usa o `Get-Process` cmdlet para obter os processos do PowerShell no computador e usa um operador de pipeline ( `|` ) para enviar os processos para o `Debug-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f14e0-126">It uses the `Get-Process` cmdlet to get the PowerShell processes on the computer, and it uses a pipeline operator (`|`) to send the processes to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="f14e0-127">Para especificar um processo específico do PowerShell, use o parâmetro ID de `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="f14e0-127">To specify a particular PowerShell process, use the ID parameter of `Get-Process`.</span></span>

### <span data-ttu-id="f14e0-128">Exemplo 6: anexar um depurador a um processo atual no computador local</span><span class="sxs-lookup"><span data-stu-id="f14e0-128">Example 6: Attach a debugger to a current process on the local computer</span></span>

```
PS C:\> $PID | Debug-Process
```

<span data-ttu-id="f14e0-129">Esse comando anexa um depurador aos processos atuais do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="f14e0-129">This command attaches a debugger to the current PowerShell processes on the computer.</span></span>

<span data-ttu-id="f14e0-130">O comando usa a `$PID` variável automática, que contém a ID de processo do processo atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f14e0-130">The command uses the `$PID` automatic variable, which contains the process ID of the current PowerShell process.</span></span> <span data-ttu-id="f14e0-131">Em seguida, ele usa um operador de pipeline ( `|` ) para enviar a ID do processo para o `Debug-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f14e0-131">Then, it uses a pipeline operator (`|`) to send the process ID to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="f14e0-132">Para obter mais informações sobre a `$PID` variável automática, consulte about_Automatic_Variables.</span><span class="sxs-lookup"><span data-stu-id="f14e0-132">For more information about the `$PID` automatic variable, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="f14e0-133">Exemplo 7: anexar um depurador a um processo que usa o parâmetro InputObject</span><span class="sxs-lookup"><span data-stu-id="f14e0-133">Example 7: Attach a debugger to a process that uses the InputObject parameter</span></span>

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

<span data-ttu-id="f14e0-134">Esse comando anexa um depurador aos processos do PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="f14e0-134">This command attaches a debugger to the PowerShell processes on the local computer.</span></span>

<span data-ttu-id="f14e0-135">O primeiro comando usa o `Get-Process` cmdlet para obter os processos do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="f14e0-135">The first command uses the `Get-Process` cmdlet to get the PowerShell processes on the computer.</span></span> <span data-ttu-id="f14e0-136">Ele salva o objeto de processo resultante na variável chamada `$P` .</span><span class="sxs-lookup"><span data-stu-id="f14e0-136">It saves the resulting process object in the variable named `$P`.</span></span>

<span data-ttu-id="f14e0-137">O segundo comando usa o parâmetro **InputObject** do `Debug-Process` cmdlet para enviar o objeto de processo na `$P` variável.</span><span class="sxs-lookup"><span data-stu-id="f14e0-137">The second command uses the **InputObject** parameter of the `Debug-Process` cmdlet to submit the process object in the `$P` variable.</span></span>

## <span data-ttu-id="f14e0-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f14e0-138">PARAMETERS</span></span>

### <span data-ttu-id="f14e0-139">-Id</span><span class="sxs-lookup"><span data-stu-id="f14e0-139">-Id</span></span>

<span data-ttu-id="f14e0-140">Especifica os identificadores de processo dos processos a depurar.</span><span class="sxs-lookup"><span data-stu-id="f14e0-140">Specifies the process IDs of the processes to be debugged.</span></span> <span data-ttu-id="f14e0-141">O nome do parâmetro de **ID** é opcional.</span><span class="sxs-lookup"><span data-stu-id="f14e0-141">The **Id** parameter name is optional.</span></span>

<span data-ttu-id="f14e0-142">Para localizar a ID de processo de um processo, digite `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="f14e0-142">To find the process ID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases: PID, ProcessId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f14e0-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f14e0-143">-InputObject</span></span>

<span data-ttu-id="f14e0-144">Especifica os objetos de processo que representam os processos a serem depurados.</span><span class="sxs-lookup"><span data-stu-id="f14e0-144">Specifies the process objects that represent processes to be debugged.</span></span> <span data-ttu-id="f14e0-145">Insira uma variável que contém os objetos de processo ou um comando que obtém os objetos de processo, como o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f14e0-145">Enter a variable that contains the process objects or a command that gets the process objects, such as the `Get-Process` cmdlet.</span></span> <span data-ttu-id="f14e0-146">Você também pode canalizar objetos de processo para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f14e0-146">You can also pipe process objects to this cmdlet.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f14e0-147">-Name</span><span class="sxs-lookup"><span data-stu-id="f14e0-147">-Name</span></span>

<span data-ttu-id="f14e0-148">Especifica os nomes dos processos a serem depurados.</span><span class="sxs-lookup"><span data-stu-id="f14e0-148">Specifies the names of the processes to be debugged.</span></span> <span data-ttu-id="f14e0-149">Se houver mais de um processo com o mesmo nome, esse cmdlet anexará um depurador a todos os processos com esse nome.</span><span class="sxs-lookup"><span data-stu-id="f14e0-149">If there is more than one process with the same name, this cmdlet attaches a debugger to all processes with that name.</span></span> <span data-ttu-id="f14e0-150">O parâmetro **Name** é opcional.</span><span class="sxs-lookup"><span data-stu-id="f14e0-150">The **Name** parameter is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f14e0-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f14e0-151">-Confirm</span></span>

<span data-ttu-id="f14e0-152">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f14e0-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f14e0-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f14e0-153">-WhatIf</span></span>

<span data-ttu-id="f14e0-154">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="f14e0-154">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="f14e0-155">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="f14e0-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f14e0-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f14e0-156">CommonParameters</span></span>

<span data-ttu-id="f14e0-157">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f14e0-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f14e0-158">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f14e0-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f14e0-159">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f14e0-159">INPUTS</span></span>

### <span data-ttu-id="f14e0-160">System. Int32, System. Diagnostics. Process, System. String</span><span class="sxs-lookup"><span data-stu-id="f14e0-160">System.Int32, System.Diagnostics.Process, System.String</span></span>

<span data-ttu-id="f14e0-161">É possível canalizar uma ID de processo (Int32), um objeto de processo (System. Diagnostics. Process) ou um nome de processo (cadeia de caracteres) para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f14e0-161">You can pipe a process ID (Int32), a process object (System.Diagnostics.Process), or a process name (String) to this cmdlet.</span></span>

## <span data-ttu-id="f14e0-162">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f14e0-162">OUTPUTS</span></span>

### <span data-ttu-id="f14e0-163">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f14e0-163">None</span></span>

<span data-ttu-id="f14e0-164">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="f14e0-164">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f14e0-165">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f14e0-165">NOTES</span></span>

<span data-ttu-id="f14e0-166">Esse cmdlet usa o método AttachDebugger da classe Win32_Process da WMI (Instrumentação de Gerenciamento do Windows).</span><span class="sxs-lookup"><span data-stu-id="f14e0-166">This cmdlet uses the AttachDebugger method of the Windows Management Instrumentation (WMI) Win32_Process class.</span></span> <span data-ttu-id="f14e0-167">Para obter mais informações sobre esse método, consulte o [método AttachDebugger](https://go.microsoft.com/fwlink/?LinkId=143640) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="f14e0-167">For more information about this method, see [AttachDebugger method](https://go.microsoft.com/fwlink/?LinkId=143640) in the MSDN library.</span></span>

## <span data-ttu-id="f14e0-168">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f14e0-168">RELATED LINKS</span></span>

[<span data-ttu-id="f14e0-169">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="f14e0-169">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="f14e0-170">Get-Process</span><span class="sxs-lookup"><span data-stu-id="f14e0-170">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="f14e0-171">Start-Process</span><span class="sxs-lookup"><span data-stu-id="f14e0-171">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="f14e0-172">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="f14e0-172">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="f14e0-173">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="f14e0-173">Wait-Process</span></span>](Wait-Process.md)
