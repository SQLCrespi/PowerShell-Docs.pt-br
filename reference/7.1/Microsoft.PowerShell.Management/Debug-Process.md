---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 905f3522a071fdd3f59d020b734c689a59e68a63
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194754"
---
# <span data-ttu-id="5a72a-103">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="5a72a-103">Debug-Process</span></span>

## <span data-ttu-id="5a72a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5a72a-104">SYNOPSIS</span></span>
<span data-ttu-id="5a72a-105">Depura um ou mais processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="5a72a-105">Debugs one or more processes running on the local computer.</span></span>

## <span data-ttu-id="5a72a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5a72a-106">SYNTAX</span></span>

### <span data-ttu-id="5a72a-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="5a72a-107">Name (Default)</span></span>

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5a72a-108">ID</span><span class="sxs-lookup"><span data-stu-id="5a72a-108">Id</span></span>

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5a72a-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="5a72a-109">InputObject</span></span>

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5a72a-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5a72a-110">DESCRIPTION</span></span>

<span data-ttu-id="5a72a-111">O cmdlet **Debug-Process** anexa um depurador a um ou mais processos em execução em um computador local.</span><span class="sxs-lookup"><span data-stu-id="5a72a-111">The **Debug-Process** cmdlet attaches a debugger to one or more running processes on a local computer.</span></span>
<span data-ttu-id="5a72a-112">Você pode especificar os processos por seu nome de processo ou ID de processo (PID) ou pode canalizar objetos de processo para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5a72a-112">You can specify the processes by their process name or process ID (PID), or you can pipe process objects to this cmdlet.</span></span>

<span data-ttu-id="5a72a-113">Esse cmdlet anexa o depurador que está atualmente registrado para o processo.</span><span class="sxs-lookup"><span data-stu-id="5a72a-113">This cmdlet attaches the debugger that is currently registered for the process.</span></span>
<span data-ttu-id="5a72a-114">Antes de usar esse cmdlet, verifique se um depurador foi baixado e configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="5a72a-114">Before using this cmdlet, verify that a debugger is downloaded and correctly configured.</span></span>

## <span data-ttu-id="5a72a-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5a72a-115">EXAMPLES</span></span>

### <span data-ttu-id="5a72a-116">Exemplo 1: anexar um depurador a um processo no computador</span><span class="sxs-lookup"><span data-stu-id="5a72a-116">Example 1: Attach a debugger to a process on the computer</span></span>

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

<span data-ttu-id="5a72a-117">Esse comando anexa um depurador ao processo do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="5a72a-117">This command attaches a debugger to the PowerShell process on the computer.</span></span>

### <span data-ttu-id="5a72a-118">Exemplo 2: anexar um depurador a todos os processos que começam com a cadeia de caracteres especificada</span><span class="sxs-lookup"><span data-stu-id="5a72a-118">Example 2: Attach a debugger to all processes that begin with the specified string</span></span>

```
PS C:\> Debug-Process -Name "SQL*"
```

<span data-ttu-id="5a72a-119">Esse comando anexa um depurador a todos os processos que têm nomes que começam com SQL.</span><span class="sxs-lookup"><span data-stu-id="5a72a-119">This command attaches a debugger to all processes that have names that begin with SQL.</span></span>

### <span data-ttu-id="5a72a-120">Exemplo 3: anexar um depurador a vários processos</span><span class="sxs-lookup"><span data-stu-id="5a72a-120">Example 3: Attach a debugger to multiple processes</span></span>

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

<span data-ttu-id="5a72a-121">Esse comando anexa um depurador aos processos Winlogon, Explorer e Outlook.</span><span class="sxs-lookup"><span data-stu-id="5a72a-121">This command attaches a debugger to the Winlogon, Explorer, and Outlook processes.</span></span>

### <span data-ttu-id="5a72a-122">Exemplo 4: anexar um depurador a várias IDs de processo</span><span class="sxs-lookup"><span data-stu-id="5a72a-122">Example 4: Attach a debugger to multiple process IDs</span></span>

```
PS C:\> Debug-Process -Id 1132, 2028
```

<span data-ttu-id="5a72a-123">Esse comando anexa um depurador aos processos que têm as IDs de processo 1132 e 2028.</span><span class="sxs-lookup"><span data-stu-id="5a72a-123">This command attaches a debugger to the processes that have process IDs 1132 and 2028.</span></span>

### <span data-ttu-id="5a72a-124">Exemplo 5: usar Get-Process para obter um processo e, em seguida, anexar um depurador a ele</span><span class="sxs-lookup"><span data-stu-id="5a72a-124">Example 5: Use Get-Process to get a process then attach a debugger to it</span></span>

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

<span data-ttu-id="5a72a-125">Esse comando anexa um depurador aos processos do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="5a72a-125">This command attaches a debugger to the PowerShell processes on the computer.</span></span>
<span data-ttu-id="5a72a-126">Ele usa o cmdlet **Get-Process** para obter os processos do PowerShell no computador e usa um operador de pipeline (|) para enviar os processos para o cmdlet **Debug-Process** .</span><span class="sxs-lookup"><span data-stu-id="5a72a-126">It uses the **Get-Process** cmdlet to get the PowerShell processes on the computer, and it uses a pipeline operator (|) to send the processes to the **Debug-Process** cmdlet.</span></span>

<span data-ttu-id="5a72a-127">Para especificar um processo específico do PowerShell, use o parâmetro ID de **Get-Process** .</span><span class="sxs-lookup"><span data-stu-id="5a72a-127">To specify a particular PowerShell process, use the ID parameter of **Get-Process** .</span></span>

### <span data-ttu-id="5a72a-128">Exemplo 6: anexar um depurador a um processo atual no computador local</span><span class="sxs-lookup"><span data-stu-id="5a72a-128">Example 6: Attach a debugger to a current process on the local computer</span></span>

```
PS C:\> $PID | Debug-Process
```

<span data-ttu-id="5a72a-129">Esse comando anexa um depurador aos processos atuais do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="5a72a-129">This command attaches a debugger to the current PowerShell processes on the computer.</span></span>

<span data-ttu-id="5a72a-130">O comando usa a $PID variável automática, que contém a ID de processo do processo atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a72a-130">The command uses the $PID automatic variable, which contains the process ID of the current PowerShell process.</span></span>
<span data-ttu-id="5a72a-131">Em seguida, ele usa um operador de pipeline (|) para enviar a ID do processo para o cmdlet **Debug-Process** .</span><span class="sxs-lookup"><span data-stu-id="5a72a-131">Then, it uses a pipeline operator (|) to send the process ID to the **Debug-Process** cmdlet.</span></span>

<span data-ttu-id="5a72a-132">Para obter mais informações sobre a $PID variável automática, consulte about_Automatic_Variables.</span><span class="sxs-lookup"><span data-stu-id="5a72a-132">For more information about the $PID automatic variable, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="5a72a-133">Exemplo 7: anexar um depurador a um processo que usa o parâmetro InputObject</span><span class="sxs-lookup"><span data-stu-id="5a72a-133">Example 7: Attach a debugger to a process that uses the InputObject parameter</span></span>

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

<span data-ttu-id="5a72a-134">Esse comando anexa um depurador aos processos do PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="5a72a-134">This command attaches a debugger to the PowerShell processes on the local computer.</span></span>

<span data-ttu-id="5a72a-135">O primeiro comando usa o cmdlet **Get-Process** para obter os processos do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="5a72a-135">The first command uses the **Get-Process** cmdlet to get the PowerShell processes on the computer.</span></span>
<span data-ttu-id="5a72a-136">Ele salva o objeto de processo resultante na variável chamada $P.</span><span class="sxs-lookup"><span data-stu-id="5a72a-136">It saves the resulting process object in the variable named $P.</span></span>

<span data-ttu-id="5a72a-137">O segundo comando usa o parâmetro *InputObject* do cmdlet **Debug-Process** para enviar o objeto de processo na variável $P.</span><span class="sxs-lookup"><span data-stu-id="5a72a-137">The second command uses the *InputObject* parameter of the **Debug-Process** cmdlet to submit the process object in the $P variable.</span></span>

## <span data-ttu-id="5a72a-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5a72a-138">PARAMETERS</span></span>

### <span data-ttu-id="5a72a-139">-Id</span><span class="sxs-lookup"><span data-stu-id="5a72a-139">-Id</span></span>

<span data-ttu-id="5a72a-140">Especifica os identificadores de processo dos processos a depurar.</span><span class="sxs-lookup"><span data-stu-id="5a72a-140">Specifies the process IDs of the processes to be debugged.</span></span>
<span data-ttu-id="5a72a-141">O nome do parâmetro de *ID* é opcional.</span><span class="sxs-lookup"><span data-stu-id="5a72a-141">The *Id* parameter name is optional.</span></span>

<span data-ttu-id="5a72a-142">Para localizar a ID de processo de um processo, digite `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="5a72a-142">To find the process ID of a process, type `Get-Process`.</span></span>

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

### <span data-ttu-id="5a72a-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5a72a-143">-InputObject</span></span>

<span data-ttu-id="5a72a-144">Especifica os objetos de processo que representam os processos a serem depurados.</span><span class="sxs-lookup"><span data-stu-id="5a72a-144">Specifies the process objects that represent processes to be debugged.</span></span>
<span data-ttu-id="5a72a-145">Insira uma variável que contém os objetos de processo ou um comando que obtém os objetos de processo, como o cmdlet Get-Process.</span><span class="sxs-lookup"><span data-stu-id="5a72a-145">Enter a variable that contains the process objects or a command that gets the process objects, such as the Get-Process cmdlet.</span></span>
<span data-ttu-id="5a72a-146">Você também pode canalizar objetos de processo para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5a72a-146">You can also pipe process objects to this cmdlet.</span></span>

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

### <span data-ttu-id="5a72a-147">-Name</span><span class="sxs-lookup"><span data-stu-id="5a72a-147">-Name</span></span>

<span data-ttu-id="5a72a-148">Especifica os nomes dos processos a serem depurados.</span><span class="sxs-lookup"><span data-stu-id="5a72a-148">Specifies the names of the processes to be debugged.</span></span>
<span data-ttu-id="5a72a-149">Se houver mais de um processo com o mesmo nome, esse cmdlet anexará um depurador a todos os processos com esse nome.</span><span class="sxs-lookup"><span data-stu-id="5a72a-149">If there is more than one process with the same name, this cmdlet attaches a debugger to all processes with that name.</span></span>
<span data-ttu-id="5a72a-150">O parâmetro *Name* é opcional.</span><span class="sxs-lookup"><span data-stu-id="5a72a-150">The *Name* parameter is optional.</span></span>

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

### <span data-ttu-id="5a72a-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5a72a-151">-Confirm</span></span>

<span data-ttu-id="5a72a-152">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5a72a-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5a72a-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5a72a-153">-WhatIf</span></span>

<span data-ttu-id="5a72a-154">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="5a72a-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5a72a-155">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="5a72a-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5a72a-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5a72a-156">CommonParameters</span></span>

<span data-ttu-id="5a72a-157">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5a72a-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5a72a-158">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5a72a-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5a72a-159">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5a72a-159">INPUTS</span></span>

### <span data-ttu-id="5a72a-160">System. Int32, System. Diagnostics. Process, System. String</span><span class="sxs-lookup"><span data-stu-id="5a72a-160">System.Int32, System.Diagnostics.Process, System.String</span></span>

<span data-ttu-id="5a72a-161">É possível canalizar uma ID de processo (Int32), um objeto de processo (System. Diagnostics. Process) ou um nome de processo (cadeia de caracteres) para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5a72a-161">You can pipe a process ID (Int32), a process object (System.Diagnostics.Process), or a process name (String) to this cmdlet.</span></span>

## <span data-ttu-id="5a72a-162">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5a72a-162">OUTPUTS</span></span>

### <span data-ttu-id="5a72a-163">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5a72a-163">None</span></span>

<span data-ttu-id="5a72a-164">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="5a72a-164">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5a72a-165">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5a72a-165">NOTES</span></span>

* <span data-ttu-id="5a72a-166">Esse cmdlet usa o método AttachDebugger da classe Win32_Process da WMI (Instrumentação de Gerenciamento do Windows).</span><span class="sxs-lookup"><span data-stu-id="5a72a-166">This cmdlet uses the AttachDebugger method of the Windows Management Instrumentation (WMI) Win32_Process class.</span></span> <span data-ttu-id="5a72a-167">Para obter mais informações sobre esse método, consulte o [método AttachDebugger](https://go.microsoft.com/fwlink/?LinkId=143640) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="5a72a-167">For more information about this method, see [AttachDebugger method](https://go.microsoft.com/fwlink/?LinkId=143640) in the MSDN library.</span></span>

## <span data-ttu-id="5a72a-168">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5a72a-168">RELATED LINKS</span></span>

[<span data-ttu-id="5a72a-169">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="5a72a-169">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="5a72a-170">Get-Process</span><span class="sxs-lookup"><span data-stu-id="5a72a-170">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="5a72a-171">Start-Process</span><span class="sxs-lookup"><span data-stu-id="5a72a-171">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="5a72a-172">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="5a72a-172">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="5a72a-173">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="5a72a-173">Wait-Process</span></span>](Wait-Process.md)

