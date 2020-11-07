---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/wait-process?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Process
ms.openlocfilehash: 88eec3461a267a03bfe3a91735ece7269aa601c2
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345027"
---
# <span data-ttu-id="54e51-103">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="54e51-103">Wait-Process</span></span>

## <span data-ttu-id="54e51-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="54e51-104">SYNOPSIS</span></span>
<span data-ttu-id="54e51-105">Aguarda que os processos sejam interrompidos antes de aceitar mais entradas.</span><span class="sxs-lookup"><span data-stu-id="54e51-105">Waits for the processes to be stopped before accepting more input.</span></span>

## <span data-ttu-id="54e51-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="54e51-106">SYNTAX</span></span>

### <span data-ttu-id="54e51-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="54e51-107">Name (Default)</span></span>

```
Wait-Process [-Name] <String[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="54e51-108">ID</span><span class="sxs-lookup"><span data-stu-id="54e51-108">Id</span></span>

```
Wait-Process [-Id] <Int32[]> [[-Timeout] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="54e51-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="54e51-109">InputObject</span></span>

```
Wait-Process [[-Timeout] <Int32>] -InputObject <Process[]> [<CommonParameters>]
```

## <span data-ttu-id="54e51-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="54e51-110">DESCRIPTION</span></span>

<span data-ttu-id="54e51-111">O `Wait-Process` cmdlet aguarda que um ou mais processos em execução sejam interrompidos antes de aceitar a entrada.</span><span class="sxs-lookup"><span data-stu-id="54e51-111">The `Wait-Process` cmdlet waits for one or more running processes to be stopped before accepting input.</span></span> <span data-ttu-id="54e51-112">No console do PowerShell, esse cmdlet suprime o prompt de comando até que os processos sejam interrompidos.</span><span class="sxs-lookup"><span data-stu-id="54e51-112">In the PowerShell console, this cmdlet suppresses the command prompt until the processes are stopped.</span></span> <span data-ttu-id="54e51-113">Você pode especificar um processo por nome do processo ou ID do processo (PID) ou canalizar um objeto de processo para `Wait-Process` .</span><span class="sxs-lookup"><span data-stu-id="54e51-113">You can specify a process by process name or process ID (PID), or pipe a process object to `Wait-Process`.</span></span>

<span data-ttu-id="54e51-114">`Wait-Process` funciona somente em processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="54e51-114">`Wait-Process` works only on processes running on the local computer.</span></span>

## <span data-ttu-id="54e51-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="54e51-115">EXAMPLES</span></span>

### <span data-ttu-id="54e51-116">Exemplo 1: parar um processo e aguardar</span><span class="sxs-lookup"><span data-stu-id="54e51-116">Example 1: Stop a process and wait</span></span>

```
PS C:\> $nid = (Get-Process notepad).id
PS C:\> Stop-Process -Id $nid
PS C:\> Wait-Process -Id $nid
```

<span data-ttu-id="54e51-117">Este exemplo interrompe o processo do bloco de notas e aguarda até que o processo seja interrompido antes de continuar com o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="54e51-117">This example stops the Notepad process and then waits for the process to be stopped before it continues with the next command.</span></span>

<span data-ttu-id="54e51-118">O primeiro comando usa o `Get-Process` cmdlet para obter a ID do processo do bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="54e51-118">The first command uses the `Get-Process` cmdlet to get the ID of the Notepad process.</span></span> <span data-ttu-id="54e51-119">Ele armazena a ID na `$nid` variável.</span><span class="sxs-lookup"><span data-stu-id="54e51-119">It stores the ID in the `$nid` variable.</span></span>

<span data-ttu-id="54e51-120">O segundo comando usa o `Stop-Process` cmdlet para interromper o processo com a ID armazenada em `$nid` .</span><span class="sxs-lookup"><span data-stu-id="54e51-120">The second command uses the `Stop-Process` cmdlet to stop the process with the ID stored in `$nid`.</span></span>

<span data-ttu-id="54e51-121">O terceiro comando usa `Wait-Process` para aguardar até que o processo do bloco de notas seja interrompido.</span><span class="sxs-lookup"><span data-stu-id="54e51-121">The third command uses `Wait-Process` to wait until the Notepad process is stopped.</span></span> <span data-ttu-id="54e51-122">Ele usa o parâmetro **ID** de `Wait-Process` para identificar o processo.</span><span class="sxs-lookup"><span data-stu-id="54e51-122">It uses the **Id** parameter of `Wait-Process` to identify the process.</span></span>

### <span data-ttu-id="54e51-123">Exemplo 2: especificando um processo</span><span class="sxs-lookup"><span data-stu-id="54e51-123">Example 2: Specifying a process</span></span>

```
PS C:\> $p = Get-Process notepad
PS C:\> Wait-Process -Id $p.id
PS C:\> Wait-Process -Name "notepad"
PS C:\> Wait-Process -InputObject $p
```

<span data-ttu-id="54e51-124">Esses comandos mostram três métodos diferentes de especificar um processo para o `Wait-Process` .</span><span class="sxs-lookup"><span data-stu-id="54e51-124">These commands show three different methods of specifying a process to `Wait-Process`.</span></span> <span data-ttu-id="54e51-125">O primeiro comando obtém o processo do bloco de notas e o armazena na `$p` variável.</span><span class="sxs-lookup"><span data-stu-id="54e51-125">The first command gets the Notepad process and stores it in the `$p` variable.</span></span>

<span data-ttu-id="54e51-126">O segundo comando usa o parâmetro **ID** , o terceiro comando usa o parâmetro **Name** e o quarto comando usa o parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="54e51-126">The second command uses the **Id** parameter, the third command uses the **Name** parameter, and the fourth command uses the **InputObject** parameter.</span></span>

<span data-ttu-id="54e51-127">Esses comandos têm os mesmos resultados e podem ser usados alternadamente.</span><span class="sxs-lookup"><span data-stu-id="54e51-127">These commands have the same results and can be used interchangeably.</span></span>

### <span data-ttu-id="54e51-128">Exemplo 3: aguardar processos por um tempo especificado</span><span class="sxs-lookup"><span data-stu-id="54e51-128">Example 3: Wait for processes for a specified time</span></span>

```
PS C:\> Wait-Process -Name outlook, winword -Timeout 30
```

<span data-ttu-id="54e51-129">Esse comando espera 30 segundos até que os processos do Outlook e do Winword sejam interrompidos.</span><span class="sxs-lookup"><span data-stu-id="54e51-129">This command waits 30 seconds for the Outlook and Winword processes to stop.</span></span> <span data-ttu-id="54e51-130">Se ambos os processos não forem interrompidos, o cmdlet exibirá um erro de não finalização e o prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="54e51-130">If both processes are not stopped, the cmdlet displays a non-terminating error and the command prompt.</span></span>

## <span data-ttu-id="54e51-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="54e51-131">PARAMETERS</span></span>

### <span data-ttu-id="54e51-132">-Id</span><span class="sxs-lookup"><span data-stu-id="54e51-132">-Id</span></span>

<span data-ttu-id="54e51-133">Especifica as identificações de processos dos processos.</span><span class="sxs-lookup"><span data-stu-id="54e51-133">Specifies the process IDs of the processes.</span></span> <span data-ttu-id="54e51-134">Para especificar IDs múltiplas, use vírgulas para separá-las.</span><span class="sxs-lookup"><span data-stu-id="54e51-134">To specify multiple IDs, use commas to separate the IDs.</span></span>
<span data-ttu-id="54e51-135">Para localizar o PID de um processo, digite `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="54e51-135">To find the PID of a process, type `Get-Process`.</span></span>

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

### <span data-ttu-id="54e51-136">-InputObject</span><span class="sxs-lookup"><span data-stu-id="54e51-136">-InputObject</span></span>

<span data-ttu-id="54e51-137">Especifica os processos enviando objetos de processo.</span><span class="sxs-lookup"><span data-stu-id="54e51-137">Specifies the processes by submitting process objects.</span></span> <span data-ttu-id="54e51-138">Insira uma variável que contenha os objetos de processo ou digite um comando ou uma expressão que obtenha os objetos de processo, como o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="54e51-138">Enter a variable that contains the process objects, or type a command or expression that gets the process objects, such as the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="54e51-139">-Name</span><span class="sxs-lookup"><span data-stu-id="54e51-139">-Name</span></span>

<span data-ttu-id="54e51-140">Especifica os nomes de processo dos processos.</span><span class="sxs-lookup"><span data-stu-id="54e51-140">Specifies the process names of the processes.</span></span> <span data-ttu-id="54e51-141">Para especificar vários nomes, use vírgulas para separar os nomes.</span><span class="sxs-lookup"><span data-stu-id="54e51-141">To specify multiple names, use commas to separate the names.</span></span> <span data-ttu-id="54e51-142">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="54e51-142">Wildcard characters are not supported.</span></span>

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

### <span data-ttu-id="54e51-143">-Tempo limite</span><span class="sxs-lookup"><span data-stu-id="54e51-143">-Timeout</span></span>

<span data-ttu-id="54e51-144">Especifica o tempo máximo, em segundos, que esse cmdlet aguarda a interrupção dos processos especificados.</span><span class="sxs-lookup"><span data-stu-id="54e51-144">Specifies the maximum time, in seconds, that this cmdlet waits for the specified processes to stop.</span></span>
<span data-ttu-id="54e51-145">Quando esse intervalo expira, o comando exibirá um erro de não finalização que lista os processos que estão em execução e termina a espera.</span><span class="sxs-lookup"><span data-stu-id="54e51-145">When this interval expires, the command displays a non-terminating error that lists the processes that are still running, and ends the wait.</span></span> <span data-ttu-id="54e51-146">Por padrão, não há tempo limite.</span><span class="sxs-lookup"><span data-stu-id="54e51-146">By default, there is no time-out.</span></span>

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

### <span data-ttu-id="54e51-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="54e51-147">CommonParameters</span></span>

<span data-ttu-id="54e51-148">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="54e51-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="54e51-149">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="54e51-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="54e51-150">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="54e51-150">INPUTS</span></span>

### <span data-ttu-id="54e51-151">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="54e51-151">System.Diagnostics.Process</span></span>

<span data-ttu-id="54e51-152">É possível canalizar um objeto de processo para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="54e51-152">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="54e51-153">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="54e51-153">OUTPUTS</span></span>

### <span data-ttu-id="54e51-154">Nenhum</span><span class="sxs-lookup"><span data-stu-id="54e51-154">None</span></span>

<span data-ttu-id="54e51-155">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="54e51-155">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="54e51-156">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="54e51-156">NOTES</span></span>

<span data-ttu-id="54e51-157">O cmdlet só tem suporte em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="54e51-157">The cmdlet is only supported on Windows platforms.</span></span>

<span data-ttu-id="54e51-158">Esse cmdlet usa o método **WaitForExit** da classe **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="54e51-158">This cmdlet uses the **WaitForExit** method of the **System.Diagnostics.Process** class.</span></span>

## <span data-ttu-id="54e51-159">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="54e51-159">RELATED LINKS</span></span>

[<span data-ttu-id="54e51-160">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="54e51-160">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="54e51-161">Get-Process</span><span class="sxs-lookup"><span data-stu-id="54e51-161">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="54e51-162">Start-Process</span><span class="sxs-lookup"><span data-stu-id="54e51-162">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="54e51-163">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="54e51-163">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="54e51-164">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="54e51-164">Wait-Process</span></span>](Wait-Process.md)
