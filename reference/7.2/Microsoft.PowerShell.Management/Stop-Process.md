---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-process?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Process
ms.openlocfilehash: 8c9e520f1f19444fd538fabee99a48ec08c69992
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595585"
---
# <span data-ttu-id="2adc0-102">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="2adc0-102">Stop-Process</span></span>

## <span data-ttu-id="2adc0-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2adc0-103">SYNOPSIS</span></span>
<span data-ttu-id="2adc0-104">Interrompe um ou mais processos em execução.</span><span class="sxs-lookup"><span data-stu-id="2adc0-104">Stops one or more running processes.</span></span>

## <span data-ttu-id="2adc0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2adc0-105">SYNTAX</span></span>

### <span data-ttu-id="2adc0-106">ID (padrão)</span><span class="sxs-lookup"><span data-stu-id="2adc0-106">Id (Default)</span></span>

```
Stop-Process [-Id] <Int32[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2adc0-107">Nome</span><span class="sxs-lookup"><span data-stu-id="2adc0-107">Name</span></span>

```
Stop-Process -Name <String[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2adc0-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="2adc0-108">InputObject</span></span>

```
Stop-Process [-InputObject] <Process[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2adc0-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2adc0-109">DESCRIPTION</span></span>

<span data-ttu-id="2adc0-110">O cmdlet **Stop-Process** interrompe um ou mais processos em execução.</span><span class="sxs-lookup"><span data-stu-id="2adc0-110">The **Stop-Process** cmdlet stops one or more running processes.</span></span>
<span data-ttu-id="2adc0-111">Você pode especificar um processo por nome do processo ou ID do processo (PID) ou passar um objeto de processo para **Stop-Process**.</span><span class="sxs-lookup"><span data-stu-id="2adc0-111">You can specify a process by process name or process ID (PID), or pass a process object to **Stop-Process**.</span></span>
<span data-ttu-id="2adc0-112">**Stop-Process** funciona apenas em processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="2adc0-112">**Stop-Process** works only on processes running on the local computer.</span></span>

<span data-ttu-id="2adc0-113">No Windows Vista e versões posteriores do sistema operacional Windows, para interromper um processo que não pertence ao usuário atual, você deve iniciar o PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="2adc0-113">On Windows Vista and later versions of the Windows operating system, to stop a process that is not owned by the current user, you must start PowerShell by using the Run as administrator option.</span></span>
<span data-ttu-id="2adc0-114">Além disso, não será solicitada a confirmação, a menos que você especifique o parâmetro *Confirm* .</span><span class="sxs-lookup"><span data-stu-id="2adc0-114">Also, you are not prompted for confirmation unless you specify the *Confirm* parameter.</span></span>

## <span data-ttu-id="2adc0-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2adc0-115">EXAMPLES</span></span>

### <span data-ttu-id="2adc0-116">Exemplo 1: parar todas as instâncias de um processo</span><span class="sxs-lookup"><span data-stu-id="2adc0-116">Example 1: Stop all instances of a process</span></span>

```
PS C:\> Stop-Process -Name "notepad"
```

<span data-ttu-id="2adc0-117">Este comando interrompe todas as instâncias do processo do Bloco de notas no computador.</span><span class="sxs-lookup"><span data-stu-id="2adc0-117">This command stops all instances of the Notepad process on the computer.</span></span>
<span data-ttu-id="2adc0-118">Cada instância do bloco de notas é executada em seu próprio processo.</span><span class="sxs-lookup"><span data-stu-id="2adc0-118">Each instance of Notepad runs in its own process.</span></span>
<span data-ttu-id="2adc0-119">Ele usa o parâmetro *Name* para especificar os processos, todos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="2adc0-119">It uses the *Name* parameter to specify the processes, all of which have the same name.</span></span>
<span data-ttu-id="2adc0-120">Se você usar o parâmetro *ID* para interromper os mesmos processos, precisaria listar as IDs de processo de cada instância do bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="2adc0-120">If you were to use the *Id* parameter to stop the same processes, you would have to list the process IDs of each instance of Notepad.</span></span>

### <span data-ttu-id="2adc0-121">Exemplo 2: parar uma instância específica de um processo</span><span class="sxs-lookup"><span data-stu-id="2adc0-121">Example 2: Stop a specific instance of a process</span></span>

```
PS C:\> Stop-Process -Id 3952 -Confirm -PassThru
Confirm
Are you sure you want to perform this action?
Performing operation "Stop-Process" on Target "notepad (3952)".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):y
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
41       2      996       3212    31            3952 notepad
```

<span data-ttu-id="2adc0-122">Este comando interrompe uma instância específica do processo do Bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="2adc0-122">This command stops a particular instance of the Notepad process.</span></span>
<span data-ttu-id="2adc0-123">Ele usa a ID do processo, 3952, para identificá-lo.</span><span class="sxs-lookup"><span data-stu-id="2adc0-123">It uses the process ID, 3952, to identify the process.</span></span>
<span data-ttu-id="2adc0-124">O parâmetro *Confirm* direciona o PowerShell para avisá-lo antes de parar o processo.</span><span class="sxs-lookup"><span data-stu-id="2adc0-124">The *Confirm* parameter directs PowerShell to prompt you before it stops the process.</span></span>
<span data-ttu-id="2adc0-125">Como o prompt inclui o nome do processo, além de sua ID, essa é a melhor prática.</span><span class="sxs-lookup"><span data-stu-id="2adc0-125">Because the prompt includes the process namein addition to its ID, this is best practice.</span></span>
<span data-ttu-id="2adc0-126">O parâmetro *PassThru* passa o objeto de processo para o formatador para exibição.</span><span class="sxs-lookup"><span data-stu-id="2adc0-126">The *PassThru* parameter passes the process object to the formatter for display.</span></span>
<span data-ttu-id="2adc0-127">Sem esse parâmetro, não haveria nenhuma exibição após um comando **Stop-Process** .</span><span class="sxs-lookup"><span data-stu-id="2adc0-127">Without this parameter, there would be no display after a **Stop-Process** command.</span></span>

### <span data-ttu-id="2adc0-128">Exemplo 3: parar um processo e detectar que ele foi interrompido</span><span class="sxs-lookup"><span data-stu-id="2adc0-128">Example 3: Stop a process and detect that it has stopped</span></span>

```
PS C:\> calc
PS C:\> $p = Get-Process -Name "calc"
PS C:\> Stop-Process -InputObject $p
PS C:\> Get-Process | Where-Object {$_.HasExited}
```

<span data-ttu-id="2adc0-129">Essa série de comandos inicia e interrompe o processo de cálculo e, em seguida, detecta os processos que foram interrompidos.</span><span class="sxs-lookup"><span data-stu-id="2adc0-129">This series of commands starts and stops the Calc process, and then detects processes that have stopped.</span></span>

<span data-ttu-id="2adc0-130">O primeiro comando inicia uma instância da calculadora.</span><span class="sxs-lookup"><span data-stu-id="2adc0-130">The first command starts an instance of the calculator.</span></span>

<span data-ttu-id="2adc0-131">O segundo comando usa **Get-Process** Obtém um objeto que representa o processo Calc e, em seguida, o armazena na variável $p.</span><span class="sxs-lookup"><span data-stu-id="2adc0-131">The second command uses **Get-Process** gets an object that represents the Calc process, and then stores it in the $p variable.</span></span>

<span data-ttu-id="2adc0-132">O terceiro comando interrompe o processo de cálculo.</span><span class="sxs-lookup"><span data-stu-id="2adc0-132">The third command stops the Calc process.</span></span>
<span data-ttu-id="2adc0-133">Ele usa o parâmetro *InputObject* para passar o objeto para **Stop-Process**.</span><span class="sxs-lookup"><span data-stu-id="2adc0-133">It uses the *InputObject* parameter to pass the object to **Stop-Process**.</span></span>

<span data-ttu-id="2adc0-134">O último comando obtém todos os processos no computador que estavam em execução, mas que agora são interrompidos.</span><span class="sxs-lookup"><span data-stu-id="2adc0-134">The last command gets all of the processes on the computer that were running but that are now stopped.</span></span>
<span data-ttu-id="2adc0-135">Ele usa o **Get-Process** para obter todos os processos no computador.</span><span class="sxs-lookup"><span data-stu-id="2adc0-135">It uses **Get-Process** to get all of the processes on the computer.</span></span>
<span data-ttu-id="2adc0-136">O operador de pipeline (|) passa os resultados para o cmdlet Where-Object, que seleciona aqueles em que o valor da propriedade **HasExited** é $true.</span><span class="sxs-lookup"><span data-stu-id="2adc0-136">The pipeline operator (|) passes the results to the Where-Object cmdlet, which selects the ones where the value of the **HasExited** property is $True.</span></span>
<span data-ttu-id="2adc0-137">**HasExited** é apenas uma propriedade de objetos de processo.</span><span class="sxs-lookup"><span data-stu-id="2adc0-137">**HasExited** is just one property of process objects.</span></span>
<span data-ttu-id="2adc0-138">Para localizar todas as propriedades, digite `Get-Process | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="2adc0-138">To find all the properties, type `Get-Process | Get-Member`.</span></span>

### <span data-ttu-id="2adc0-139">Exemplo 4: parar um processo que não pertence ao usuário atual</span><span class="sxs-lookup"><span data-stu-id="2adc0-139">Example 4: Stop a process not owned by the current user</span></span>

```
PS C:\> Get-Process -Name "lsass" | Stop-Process

Stop-Process : Cannot stop process 'lsass (596)' because of the following error: Access is denied
At line:1 char:34
+ Get-Process -Name "lsass" | Stop-Process <<<<

[ADMIN]: PS C:\> Get-Process -Name "lsass" | Stop-Process

Warning!
Are you sure you want to perform this action?
Performing operation 'Stop-Process' on Target 'lsass(596)'
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
[ADMIN]: PS C:\> Get-Process -Name "lsass" | Stop-Process -Force
[ADMIN]: PS C:\>
```

<span data-ttu-id="2adc0-140">Esses comandos mostram o efeito de usar *Force* para interromper um processo que não pertence ao usuário.</span><span class="sxs-lookup"><span data-stu-id="2adc0-140">These commands show the effect of using *Force* to stop a process that is not owned by the user.</span></span>

<span data-ttu-id="2adc0-141">O primeiro comando usa **Get-Process** para obter o processo do Lsass.</span><span class="sxs-lookup"><span data-stu-id="2adc0-141">The first command uses **Get-Process** to get the Lsass process.</span></span>
<span data-ttu-id="2adc0-142">Um operador de pipeline envia o processo para **Stop-Process** para interrompê-lo.</span><span class="sxs-lookup"><span data-stu-id="2adc0-142">A pipeline operator sends the process to **Stop-Process** to stop it.</span></span>
<span data-ttu-id="2adc0-143">Conforme mostrado na saída de exemplo, o primeiro comando falha com uma mensagem de acesso negado, pois esse processo pode ser interrompido somente por um membro do grupo de administradores no computador.</span><span class="sxs-lookup"><span data-stu-id="2adc0-143">As shown in the sample output, the first command fails with an Access denied message, because this process can be stopped only by a member of the Administrator group on the computer.</span></span>

<span data-ttu-id="2adc0-144">Quando o PowerShell é aberto usando a opção Executar como administrador e o comando é repetido, o PowerShell solicita sua confirmação.</span><span class="sxs-lookup"><span data-stu-id="2adc0-144">When PowerShell is opened by using the Run as administrator option, and the command is repeated, PowerShell prompts you for confirmation.</span></span>

<span data-ttu-id="2adc0-145">O segundo comando especifica *Force* para suprimir o prompt.</span><span class="sxs-lookup"><span data-stu-id="2adc0-145">The second command specifies *Force* to suppress the prompt.</span></span>
<span data-ttu-id="2adc0-146">Como resultado, o processo é interrompido sem confirmação.</span><span class="sxs-lookup"><span data-stu-id="2adc0-146">As a result, the process is stopped without confirmation.</span></span>

## <span data-ttu-id="2adc0-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2adc0-147">PARAMETERS</span></span>

### <span data-ttu-id="2adc0-148">-Force</span><span class="sxs-lookup"><span data-stu-id="2adc0-148">-Force</span></span>

<span data-ttu-id="2adc0-149">Interrompe os processos especificados sem pedir confirmação.</span><span class="sxs-lookup"><span data-stu-id="2adc0-149">Stops the specified processes without prompting for confirmation.</span></span>
<span data-ttu-id="2adc0-150">Por padrão, **Stop-Process** solicita confirmação antes de interromper qualquer processo que não pertence ao usuário atual.</span><span class="sxs-lookup"><span data-stu-id="2adc0-150">By default, **Stop-Process** prompts for confirmation before stopping any process that is not owned by the current user.</span></span>

<span data-ttu-id="2adc0-151">Para localizar o proprietário de um processo, use o `Get-CimInstance` cmdlet para obter um **Win32_Process** objeto que representa o processo e, em seguida, use o método **GetOwner** do objeto.</span><span class="sxs-lookup"><span data-stu-id="2adc0-151">To find the owner of a process, use the `Get-CimInstance` cmdlet to get a **Win32_Process** object that represents the process, and then use the **GetOwner** method of the object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2adc0-152">-Id</span><span class="sxs-lookup"><span data-stu-id="2adc0-152">-Id</span></span>

<span data-ttu-id="2adc0-153">Especifica as IDs de processo dos processos a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="2adc0-153">Specifies the process IDs of the processes to stop.</span></span>
<span data-ttu-id="2adc0-154">Para especificar IDs múltiplas, use vírgulas para separá-las.</span><span class="sxs-lookup"><span data-stu-id="2adc0-154">To specify multiple IDs, use commas to separate the IDs.</span></span>
<span data-ttu-id="2adc0-155">Para localizar o PID de um processo, digite `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="2adc0-155">To find the PID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2adc0-156">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2adc0-156">-InputObject</span></span>

<span data-ttu-id="2adc0-157">Especifica os objetos de processo a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="2adc0-157">Specifies the process objects to stop.</span></span>
<span data-ttu-id="2adc0-158">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="2adc0-158">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2adc0-159">-Name</span><span class="sxs-lookup"><span data-stu-id="2adc0-159">-Name</span></span>

<span data-ttu-id="2adc0-160">Especifica os nomes de processo dos processos a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="2adc0-160">Specifies the process names of the processes to stop.</span></span>
<span data-ttu-id="2adc0-161">Você pode digitar vários nomes de processo, separados por vírgulas, ou usar caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="2adc0-161">You can type multiple process names, separated by commas, or use wildcard characters.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="2adc0-162">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2adc0-162">-PassThru</span></span>

<span data-ttu-id="2adc0-163">Retorna um objeto que representa o processo.</span><span class="sxs-lookup"><span data-stu-id="2adc0-163">Returns an object that represents the process.</span></span>
<span data-ttu-id="2adc0-164">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="2adc0-164">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2adc0-165">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2adc0-165">-Confirm</span></span>

<span data-ttu-id="2adc0-166">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2adc0-166">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2adc0-167">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2adc0-167">-WhatIf</span></span>

<span data-ttu-id="2adc0-168">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="2adc0-168">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2adc0-169">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="2adc0-169">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2adc0-170">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2adc0-170">CommonParameters</span></span>
<span data-ttu-id="2adc0-171">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2adc0-171">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2adc0-172">Para obter mais informações, confira [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2adc0-172">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2adc0-173">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2adc0-173">INPUTS</span></span>

### <span data-ttu-id="2adc0-174">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="2adc0-174">System.Diagnostics.Process</span></span>

<span data-ttu-id="2adc0-175">É possível canalizar um objeto de processo para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2adc0-175">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="2adc0-176">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2adc0-176">OUTPUTS</span></span>

### <span data-ttu-id="2adc0-177">Nenhum, System. Diagnostics. Process</span><span class="sxs-lookup"><span data-stu-id="2adc0-177">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="2adc0-178">Esse cmdlet retorna um objeto **System. Diagnostics. Process** que representa o processo interrompido, se você especificar o parâmetro *PassThru* .</span><span class="sxs-lookup"><span data-stu-id="2adc0-178">This cmdlet returns a **System.Diagnostics.Process** object that represents the stopped process, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="2adc0-179">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="2adc0-179">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2adc0-180">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2adc0-180">NOTES</span></span>

* <span data-ttu-id="2adc0-181">Você também pode fazer referência a **Stop-Process** por seus aliases internos, **Kill** e **SPPS**.</span><span class="sxs-lookup"><span data-stu-id="2adc0-181">You can also refer to **Stop-Process** by its built-in aliases, **kill** and **spps**.</span></span> <span data-ttu-id="2adc0-182">Para obter mais informações, consulte about_Aliases.</span><span class="sxs-lookup"><span data-stu-id="2adc0-182">For more information, see about_Aliases.</span></span>

  <span data-ttu-id="2adc0-183">Você também pode usar as propriedades e métodos do objeto Instrumentação de Gerenciamento do Windows (WMI) **Win32_Process** no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2adc0-183">You can also use the properties and methods of the Windows Management Instrumentation (WMI) **Win32_Process** object in Windows PowerShell.</span></span>
<span data-ttu-id="2adc0-184">Para obter mais informações, consulte `Get-CimInstance` e o SDK do WMI.</span><span class="sxs-lookup"><span data-stu-id="2adc0-184">For more information, see `Get-CimInstance` and the WMI SDK.</span></span>

* <span data-ttu-id="2adc0-185">Ao parar os processos, perceba que parar um processo pode parar o processo e os serviços que dependem do processo.</span><span class="sxs-lookup"><span data-stu-id="2adc0-185">When stopping processes, realize that stopping a process can stop process and services that depend on the process.</span></span>
<span data-ttu-id="2adc0-186">Em casos extremos, interromper um processo pode parar o funcionamento do Windows.</span><span class="sxs-lookup"><span data-stu-id="2adc0-186">In an extreme case, stopping a process can stop Windows.</span></span>

## <span data-ttu-id="2adc0-187">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2adc0-187">RELATED LINKS</span></span>

[<span data-ttu-id="2adc0-188">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="2adc0-188">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="2adc0-189">Get-Process</span><span class="sxs-lookup"><span data-stu-id="2adc0-189">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="2adc0-190">Start-Process</span><span class="sxs-lookup"><span data-stu-id="2adc0-190">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="2adc0-191">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="2adc0-191">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="2adc0-192">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="2adc0-192">Wait-Process</span></span>](Wait-Process.md)

