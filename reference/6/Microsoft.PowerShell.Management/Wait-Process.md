---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/wait-process?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Process
ms.openlocfilehash: 97b29f13fd1106a04204f97f02d82e9760fa41ae
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193367"
---
# <span data-ttu-id="a2e68-103">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="a2e68-103">Wait-Process</span></span>

## <span data-ttu-id="a2e68-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a2e68-104">SYNOPSIS</span></span>
<span data-ttu-id="a2e68-105">Aguarda que os processos sejam interrompidos antes de aceitar mais entradas.</span><span class="sxs-lookup"><span data-stu-id="a2e68-105">Waits for the processes to be stopped before accepting more input.</span></span>

## <span data-ttu-id="a2e68-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a2e68-106">SYNTAX</span></span>

### <span data-ttu-id="a2e68-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="a2e68-107">Name (Default)</span></span>

```
Wait-Process [-Name] <String[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="a2e68-108">ID</span><span class="sxs-lookup"><span data-stu-id="a2e68-108">Id</span></span>

```
Wait-Process [-Id] <Int32[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="a2e68-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="a2e68-109">InputObject</span></span>

```
Wait-Process [[-Timeout] <Int32>] -InputObject <Process[]> [<CommonParameters>]
```

## <span data-ttu-id="a2e68-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a2e68-110">DESCRIPTION</span></span>

<span data-ttu-id="a2e68-111">O cmdlet **Wait-Process** aguarda que um ou mais processos em execução sejam interrompidos antes de aceitar a entrada.</span><span class="sxs-lookup"><span data-stu-id="a2e68-111">The **Wait-Process** cmdlet waits for one or more running processes to be stopped before accepting input.</span></span>
<span data-ttu-id="a2e68-112">No console do PowerShell, esse cmdlet suprime o prompt de comando até que os processos sejam interrompidos.</span><span class="sxs-lookup"><span data-stu-id="a2e68-112">In the PowerShell console, this cmdlet suppresses the command prompt until the processes are stopped.</span></span>
<span data-ttu-id="a2e68-113">Você pode especificar um processo por nome do processo ou ID do processo (PID) ou canalizar um objeto de processo para **Wait-Process** .</span><span class="sxs-lookup"><span data-stu-id="a2e68-113">You can specify a process by process name or process ID (PID), or pipe a process object to **Wait-Process** .</span></span>

<span data-ttu-id="a2e68-114">O **processo de espera** funciona apenas em processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="a2e68-114">**Wait-Process** works only on processes running on the local computer.</span></span>

## <span data-ttu-id="a2e68-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a2e68-115">EXAMPLES</span></span>

### <span data-ttu-id="a2e68-116">Exemplo 1: parar um processo e aguardar</span><span class="sxs-lookup"><span data-stu-id="a2e68-116">Example 1: Stop a process and wait</span></span>

```
PS C:\> $nid = (Get-Process notepad).id
PS C:\> Stop-Process -Id $nid
PS C:\> Wait-Process -Id $nid
```

<span data-ttu-id="a2e68-117">Este exemplo interrompe o processo do bloco de notas e aguarda até que o processo seja interrompido antes de continuar com o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="a2e68-117">This example stops the Notepad process and then waits for the process to be stopped before it continues with the next command.</span></span>

<span data-ttu-id="a2e68-118">O primeiro comando usa o cmdlet **Get-Process** para obter a ID do processo do bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="a2e68-118">The first command uses the **Get-Process** cmdlet to get the ID of the Notepad process.</span></span>
<span data-ttu-id="a2e68-119">Ele armazena a ID na variável $nid.</span><span class="sxs-lookup"><span data-stu-id="a2e68-119">It stores the ID in the $nid variable.</span></span>

<span data-ttu-id="a2e68-120">O segundo comando usa o cmdlet Stop-Process para interromper o processo com a ID armazenada em $nid.</span><span class="sxs-lookup"><span data-stu-id="a2e68-120">The second command uses the Stop-Process cmdlet to stop the process with the ID stored in $nid.</span></span>

<span data-ttu-id="a2e68-121">O terceiro comando usa o **processo de espera** para aguardar até que o processo do bloco de notas seja interrompido.</span><span class="sxs-lookup"><span data-stu-id="a2e68-121">The third command uses **Wait-Process** to wait until the Notepad process is stopped.</span></span>
<span data-ttu-id="a2e68-122">Ele usa o parâmetro *ID* do **processo de espera** para identificar o processo.</span><span class="sxs-lookup"><span data-stu-id="a2e68-122">It uses the *Id* parameter of **Wait-Process** to identify the process.</span></span>

### <span data-ttu-id="a2e68-123">Exemplo 2: especificando um processo</span><span class="sxs-lookup"><span data-stu-id="a2e68-123">Example 2: Specifying a process</span></span>

```
PS C:\> $p = Get-Process notepad
PS C:\> Wait-Process -Id $p.id
PS C:\> Wait-Process -Name "notepad"
PS C:\> Wait-Process -InputObject $p
```

<span data-ttu-id="a2e68-124">Esses comandos mostram três métodos diferentes de especificar um processo de **espera-processo** .</span><span class="sxs-lookup"><span data-stu-id="a2e68-124">These commands show three different methods of specifying a process to **Wait-Process** .</span></span>
<span data-ttu-id="a2e68-125">O primeiro comando obtém o processo do bloco de notas e o armazena na variável $p.</span><span class="sxs-lookup"><span data-stu-id="a2e68-125">The first command gets the Notepad process and stores it in the $p variable.</span></span>

<span data-ttu-id="a2e68-126">O segundo comando usa o parâmetro *ID* , o terceiro comando usa o parâmetro *Name* e o quarto comando usa o parâmetro *InputObject* .</span><span class="sxs-lookup"><span data-stu-id="a2e68-126">The second command uses the *Id* parameter, the third command uses the *Name* parameter, and the fourth command uses the *InputObject* parameter.</span></span>

<span data-ttu-id="a2e68-127">Esses comandos têm os mesmos resultados e podem ser usados alternadamente.</span><span class="sxs-lookup"><span data-stu-id="a2e68-127">These commands have the same results and can be used interchangeably.</span></span>

### <span data-ttu-id="a2e68-128">Exemplo 3: aguardar processos por um tempo especificado</span><span class="sxs-lookup"><span data-stu-id="a2e68-128">Example 3: Wait for processes for a specified time</span></span>

```
PS C:\> Wait-Process -Name outlook, winword -Timeout 30
```

<span data-ttu-id="a2e68-129">Esse comando espera 30 segundos até que os processos do Outlook e do Winword sejam interrompidos.</span><span class="sxs-lookup"><span data-stu-id="a2e68-129">This command waits 30 seconds for the Outlook and Winword processes to stop.</span></span>
<span data-ttu-id="a2e68-130">Se ambos os processos não forem interrompidos, o cmdlet exibirá um erro de não finalização e o prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="a2e68-130">If both processes are not stopped, the cmdlet displays a non-terminating error and the command prompt.</span></span>

## <span data-ttu-id="a2e68-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a2e68-131">PARAMETERS</span></span>

### <span data-ttu-id="a2e68-132">-Id</span><span class="sxs-lookup"><span data-stu-id="a2e68-132">-Id</span></span>

<span data-ttu-id="a2e68-133">Especifica as identificações de processos dos processos.</span><span class="sxs-lookup"><span data-stu-id="a2e68-133">Specifies the process IDs of the processes.</span></span>
<span data-ttu-id="a2e68-134">Para especificar IDs múltiplas, use vírgulas para separá-las.</span><span class="sxs-lookup"><span data-stu-id="a2e68-134">To specify multiple IDs, use commas to separate the IDs.</span></span>
<span data-ttu-id="a2e68-135">Para localizar o PID de um processo, digite `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="a2e68-135">To find the PID of a process, type `Get-Process`.</span></span>

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

### <span data-ttu-id="a2e68-136">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a2e68-136">-InputObject</span></span>

<span data-ttu-id="a2e68-137">Especifica os processos enviando objetos de processo.</span><span class="sxs-lookup"><span data-stu-id="a2e68-137">Specifies the processes by submitting process objects.</span></span>
<span data-ttu-id="a2e68-138">Insira uma variável que contenha os objetos de processo ou digite um comando ou uma expressão que obtenha os objetos de processo, como o cmdlet Get-Process.</span><span class="sxs-lookup"><span data-stu-id="a2e68-138">Enter a variable that contains the process objects, or type a command or expression that gets the process objects, such as the Get-Process cmdlet.</span></span>

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

### <span data-ttu-id="a2e68-139">-Name</span><span class="sxs-lookup"><span data-stu-id="a2e68-139">-Name</span></span>

<span data-ttu-id="a2e68-140">Especifica os nomes de processo dos processos.</span><span class="sxs-lookup"><span data-stu-id="a2e68-140">Specifies the process names of the processes.</span></span>
<span data-ttu-id="a2e68-141">Para especificar vários nomes, use vírgulas para separar os nomes.</span><span class="sxs-lookup"><span data-stu-id="a2e68-141">To specify multiple names, use commas to separate the names.</span></span>
<span data-ttu-id="a2e68-142">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="a2e68-142">Wildcard characters are not supported.</span></span>

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

### <span data-ttu-id="a2e68-143">-Tempo limite</span><span class="sxs-lookup"><span data-stu-id="a2e68-143">-Timeout</span></span>

<span data-ttu-id="a2e68-144">Especifica o tempo máximo, em segundos, que esse cmdlet aguarda a interrupção dos processos especificados.</span><span class="sxs-lookup"><span data-stu-id="a2e68-144">Specifies the maximum time, in seconds, that this cmdlet waits for the specified processes to stop.</span></span>
<span data-ttu-id="a2e68-145">Quando esse intervalo expira, o comando exibirá um erro de não finalização que lista os processos que estão em execução e termina a espera.</span><span class="sxs-lookup"><span data-stu-id="a2e68-145">When this interval expires, the command displays a non-terminating error that lists the processes that are still running, and ends the wait.</span></span>
<span data-ttu-id="a2e68-146">Por padrão, não há tempo limite.</span><span class="sxs-lookup"><span data-stu-id="a2e68-146">By default, there is no time-out.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2e68-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a2e68-147">CommonParameters</span></span>

<span data-ttu-id="a2e68-148">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a2e68-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a2e68-149">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a2e68-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a2e68-150">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a2e68-150">INPUTS</span></span>

### <span data-ttu-id="a2e68-151">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="a2e68-151">System.Diagnostics.Process</span></span>

<span data-ttu-id="a2e68-152">É possível canalizar um objeto de processo para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a2e68-152">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="a2e68-153">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a2e68-153">OUTPUTS</span></span>

### <span data-ttu-id="a2e68-154">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a2e68-154">None</span></span>

<span data-ttu-id="a2e68-155">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="a2e68-155">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a2e68-156">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a2e68-156">NOTES</span></span>

* <span data-ttu-id="a2e68-157">Esse cmdlet usa o método **WaitForExit** da classe System. Diagnostics. Process.</span><span class="sxs-lookup"><span data-stu-id="a2e68-157">This cmdlet uses the **WaitForExit** method of the System.Diagnostics.Process class.</span></span> <span data-ttu-id="a2e68-158">Para obter mais informações sobre esse método, consulte o SDK do Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a2e68-158">For more information about this method, see the Microsoft .NET Framework SDK.</span></span>

*

## <span data-ttu-id="a2e68-159">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a2e68-159">RELATED LINKS</span></span>

[<span data-ttu-id="a2e68-160">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="a2e68-160">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="a2e68-161">Get-Process</span><span class="sxs-lookup"><span data-stu-id="a2e68-161">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="a2e68-162">Start-Process</span><span class="sxs-lookup"><span data-stu-id="a2e68-162">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="a2e68-163">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="a2e68-163">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="a2e68-164">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="a2e68-164">Wait-Process</span></span>](Wait-Process.md)
