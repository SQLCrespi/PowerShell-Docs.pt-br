---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 660d2b4845df8091ff8b69b28c4e7695af557122
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596999"
---
# <span data-ttu-id="d570e-102">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="d570e-102">Debug-Process</span></span>

## <span data-ttu-id="d570e-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d570e-103">SYNOPSIS</span></span>
<span data-ttu-id="d570e-104">Depura um ou mais processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="d570e-104">Debugs one or more processes running on the local computer.</span></span>

## <span data-ttu-id="d570e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d570e-105">SYNTAX</span></span>

### <span data-ttu-id="d570e-106">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="d570e-106">Name (Default)</span></span>

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d570e-107">ID</span><span class="sxs-lookup"><span data-stu-id="d570e-107">Id</span></span>

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d570e-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="d570e-108">InputObject</span></span>

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d570e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d570e-109">DESCRIPTION</span></span>

<span data-ttu-id="d570e-110">O `Debug-Process` cmdlet anexa um depurador a um ou mais processos em execução em um computador local.</span><span class="sxs-lookup"><span data-stu-id="d570e-110">The `Debug-Process` cmdlet attaches a debugger to one or more running processes on a local computer.</span></span>
<span data-ttu-id="d570e-111">Você pode especificar os processos por seu nome de processo ou ID de processo (PID) ou pode canalizar objetos de processo para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d570e-111">You can specify the processes by their process name or process ID (PID), or you can pipe process objects to this cmdlet.</span></span>

<span data-ttu-id="d570e-112">Esse cmdlet anexa o depurador que está atualmente registrado para o processo.</span><span class="sxs-lookup"><span data-stu-id="d570e-112">This cmdlet attaches the debugger that is currently registered for the process.</span></span> <span data-ttu-id="d570e-113">Antes de usar esse cmdlet, verifique se um depurador foi baixado e configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="d570e-113">Before using this cmdlet, verify that a debugger is downloaded and correctly configured.</span></span>

## <span data-ttu-id="d570e-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d570e-114">EXAMPLES</span></span>

### <span data-ttu-id="d570e-115">Exemplo 1: anexar um depurador a um processo no computador</span><span class="sxs-lookup"><span data-stu-id="d570e-115">Example 1: Attach a debugger to a process on the computer</span></span>

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

<span data-ttu-id="d570e-116">Esse comando anexa um depurador ao processo do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="d570e-116">This command attaches a debugger to the PowerShell process on the computer.</span></span>

### <span data-ttu-id="d570e-117">Exemplo 2: anexar um depurador a todos os processos que começam com a cadeia de caracteres especificada</span><span class="sxs-lookup"><span data-stu-id="d570e-117">Example 2: Attach a debugger to all processes that begin with the specified string</span></span>

```
PS C:\> Debug-Process -Name "SQL*"
```

<span data-ttu-id="d570e-118">Esse comando anexa um depurador a todos os processos que têm nomes que começam com SQL.</span><span class="sxs-lookup"><span data-stu-id="d570e-118">This command attaches a debugger to all processes that have names that begin with SQL.</span></span>

### <span data-ttu-id="d570e-119">Exemplo 3: anexar um depurador a vários processos</span><span class="sxs-lookup"><span data-stu-id="d570e-119">Example 3: Attach a debugger to multiple processes</span></span>

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

<span data-ttu-id="d570e-120">Esse comando anexa um depurador aos processos Winlogon, Explorer e Outlook.</span><span class="sxs-lookup"><span data-stu-id="d570e-120">This command attaches a debugger to the Winlogon, Explorer, and Outlook processes.</span></span>

### <span data-ttu-id="d570e-121">Exemplo 4: anexar um depurador a várias IDs de processo</span><span class="sxs-lookup"><span data-stu-id="d570e-121">Example 4: Attach a debugger to multiple process IDs</span></span>

```
PS C:\> Debug-Process -Id 1132, 2028
```

<span data-ttu-id="d570e-122">Esse comando anexa um depurador aos processos que têm as IDs de processo 1132 e 2028.</span><span class="sxs-lookup"><span data-stu-id="d570e-122">This command attaches a debugger to the processes that have process IDs 1132 and 2028.</span></span>

### <span data-ttu-id="d570e-123">Exemplo 5: usar Get-Process para obter um processo e, em seguida, anexar um depurador a ele</span><span class="sxs-lookup"><span data-stu-id="d570e-123">Example 5: Use Get-Process to get a process then attach a debugger to it</span></span>

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

<span data-ttu-id="d570e-124">Esse comando anexa um depurador aos processos do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="d570e-124">This command attaches a debugger to the PowerShell processes on the computer.</span></span> <span data-ttu-id="d570e-125">Ele usa o `Get-Process` cmdlet para obter os processos do PowerShell no computador e usa um operador de pipeline ( `|` ) para enviar os processos para o `Debug-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d570e-125">It uses the `Get-Process` cmdlet to get the PowerShell processes on the computer, and it uses a pipeline operator (`|`) to send the processes to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="d570e-126">Para especificar um processo específico do PowerShell, use o parâmetro ID de `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="d570e-126">To specify a particular PowerShell process, use the ID parameter of `Get-Process`.</span></span>

### <span data-ttu-id="d570e-127">Exemplo 6: anexar um depurador a um processo atual no computador local</span><span class="sxs-lookup"><span data-stu-id="d570e-127">Example 6: Attach a debugger to a current process on the local computer</span></span>

```
PS C:\> $PID | Debug-Process
```

<span data-ttu-id="d570e-128">Esse comando anexa um depurador aos processos atuais do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="d570e-128">This command attaches a debugger to the current PowerShell processes on the computer.</span></span>

<span data-ttu-id="d570e-129">O comando usa a `$PID` variável automática, que contém a ID de processo do processo atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d570e-129">The command uses the `$PID` automatic variable, which contains the process ID of the current PowerShell process.</span></span> <span data-ttu-id="d570e-130">Em seguida, ele usa um operador de pipeline ( `|` ) para enviar a ID do processo para o `Debug-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d570e-130">Then, it uses a pipeline operator (`|`) to send the process ID to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="d570e-131">Para obter mais informações sobre a `$PID` variável automática, consulte about_Automatic_Variables.</span><span class="sxs-lookup"><span data-stu-id="d570e-131">For more information about the `$PID` automatic variable, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="d570e-132">Exemplo 7: anexar um depurador a um processo que usa o parâmetro InputObject</span><span class="sxs-lookup"><span data-stu-id="d570e-132">Example 7: Attach a debugger to a process that uses the InputObject parameter</span></span>

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

<span data-ttu-id="d570e-133">Esse comando anexa um depurador aos processos do PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="d570e-133">This command attaches a debugger to the PowerShell processes on the local computer.</span></span>

<span data-ttu-id="d570e-134">O primeiro comando usa o `Get-Process` cmdlet para obter os processos do PowerShell no computador.</span><span class="sxs-lookup"><span data-stu-id="d570e-134">The first command uses the `Get-Process` cmdlet to get the PowerShell processes on the computer.</span></span> <span data-ttu-id="d570e-135">Ele salva o objeto de processo resultante na variável chamada `$P` .</span><span class="sxs-lookup"><span data-stu-id="d570e-135">It saves the resulting process object in the variable named `$P`.</span></span>

<span data-ttu-id="d570e-136">O segundo comando usa o parâmetro **InputObject** do `Debug-Process` cmdlet para enviar o objeto de processo na `$P` variável.</span><span class="sxs-lookup"><span data-stu-id="d570e-136">The second command uses the **InputObject** parameter of the `Debug-Process` cmdlet to submit the process object in the `$P` variable.</span></span>

## <span data-ttu-id="d570e-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d570e-137">PARAMETERS</span></span>

### <span data-ttu-id="d570e-138">-Id</span><span class="sxs-lookup"><span data-stu-id="d570e-138">-Id</span></span>

<span data-ttu-id="d570e-139">Especifica os identificadores de processo dos processos a depurar.</span><span class="sxs-lookup"><span data-stu-id="d570e-139">Specifies the process IDs of the processes to be debugged.</span></span> <span data-ttu-id="d570e-140">O nome do parâmetro de **ID** é opcional.</span><span class="sxs-lookup"><span data-stu-id="d570e-140">The **Id** parameter name is optional.</span></span>

<span data-ttu-id="d570e-141">Para localizar a ID de processo de um processo, digite `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="d570e-141">To find the process ID of a process, type `Get-Process`.</span></span>

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

### <span data-ttu-id="d570e-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d570e-142">-InputObject</span></span>

<span data-ttu-id="d570e-143">Especifica os objetos de processo que representam os processos a serem depurados.</span><span class="sxs-lookup"><span data-stu-id="d570e-143">Specifies the process objects that represent processes to be debugged.</span></span> <span data-ttu-id="d570e-144">Insira uma variável que contém os objetos de processo ou um comando que obtém os objetos de processo, como o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d570e-144">Enter a variable that contains the process objects or a command that gets the process objects, such as the `Get-Process` cmdlet.</span></span> <span data-ttu-id="d570e-145">Você também pode canalizar objetos de processo para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d570e-145">You can also pipe process objects to this cmdlet.</span></span>

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

### <span data-ttu-id="d570e-146">-Name</span><span class="sxs-lookup"><span data-stu-id="d570e-146">-Name</span></span>

<span data-ttu-id="d570e-147">Especifica os nomes dos processos a serem depurados.</span><span class="sxs-lookup"><span data-stu-id="d570e-147">Specifies the names of the processes to be debugged.</span></span> <span data-ttu-id="d570e-148">Se houver mais de um processo com o mesmo nome, esse cmdlet anexará um depurador a todos os processos com esse nome.</span><span class="sxs-lookup"><span data-stu-id="d570e-148">If there is more than one process with the same name, this cmdlet attaches a debugger to all processes with that name.</span></span> <span data-ttu-id="d570e-149">O parâmetro **Name** é opcional.</span><span class="sxs-lookup"><span data-stu-id="d570e-149">The **Name** parameter is optional.</span></span>

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

### <span data-ttu-id="d570e-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d570e-150">-Confirm</span></span>

<span data-ttu-id="d570e-151">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d570e-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d570e-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d570e-152">-WhatIf</span></span>

<span data-ttu-id="d570e-153">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="d570e-153">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="d570e-154">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="d570e-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d570e-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d570e-155">CommonParameters</span></span>

<span data-ttu-id="d570e-156">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d570e-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d570e-157">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d570e-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d570e-158">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d570e-158">INPUTS</span></span>

### <span data-ttu-id="d570e-159">System. Int32, System. Diagnostics. Process, System. String</span><span class="sxs-lookup"><span data-stu-id="d570e-159">System.Int32, System.Diagnostics.Process, System.String</span></span>

<span data-ttu-id="d570e-160">É possível canalizar uma ID de processo (Int32), um objeto de processo (System. Diagnostics. Process) ou um nome de processo (cadeia de caracteres) para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d570e-160">You can pipe a process ID (Int32), a process object (System.Diagnostics.Process), or a process name (String) to this cmdlet.</span></span>

## <span data-ttu-id="d570e-161">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d570e-161">OUTPUTS</span></span>

### <span data-ttu-id="d570e-162">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d570e-162">None</span></span>

<span data-ttu-id="d570e-163">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="d570e-163">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d570e-164">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d570e-164">NOTES</span></span>

<span data-ttu-id="d570e-165">Esse cmdlet usa o método AttachDebugger da classe Win32_Process da WMI (Instrumentação de Gerenciamento do Windows).</span><span class="sxs-lookup"><span data-stu-id="d570e-165">This cmdlet uses the AttachDebugger method of the Windows Management Instrumentation (WMI) Win32_Process class.</span></span> <span data-ttu-id="d570e-166">Para obter mais informações sobre esse método, consulte o [método AttachDebugger](https://go.microsoft.com/fwlink/?LinkId=143640) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="d570e-166">For more information about this method, see [AttachDebugger method](https://go.microsoft.com/fwlink/?LinkId=143640) in the MSDN library.</span></span>

## <span data-ttu-id="d570e-167">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d570e-167">RELATED LINKS</span></span>

[<span data-ttu-id="d570e-168">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="d570e-168">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="d570e-169">Get-Process</span><span class="sxs-lookup"><span data-stu-id="d570e-169">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="d570e-170">Start-Process</span><span class="sxs-lookup"><span data-stu-id="d570e-170">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="d570e-171">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="d570e-171">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="d570e-172">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="d570e-172">Wait-Process</span></span>](Wait-Process.md)
