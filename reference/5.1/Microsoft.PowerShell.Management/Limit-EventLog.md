---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/limit-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Limit-EventLog
ms.openlocfilehash: 3ec3214103dc6151e148f7482b0be8b821871e3c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193982"
---
# <span data-ttu-id="37815-103">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="37815-103">Limit-EventLog</span></span>

## <span data-ttu-id="37815-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="37815-104">SYNOPSIS</span></span>
<span data-ttu-id="37815-105">Define as propriedades de log de eventos que limitam o tamanho do log de eventos e a idade de suas entradas.</span><span class="sxs-lookup"><span data-stu-id="37815-105">Sets the event log properties that limit the size of the event log and the age of its entries.</span></span>

## <span data-ttu-id="37815-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="37815-106">SYNTAX</span></span>

```
Limit-EventLog [-LogName] <String[]> [-ComputerName <String[]>] [-RetentionDays <Int32>]
 [-OverflowAction <OverflowAction>] [-MaximumSize <Int64>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="37815-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37815-107">DESCRIPTION</span></span>
<span data-ttu-id="37815-108">O cmdlet **Limit-EventLog** define o tamanho máximo de um log de eventos clássico, quanto tempo cada evento deve ser retido e o que acontece quando o log atinge seu tamanho máximo.</span><span class="sxs-lookup"><span data-stu-id="37815-108">The **Limit-EventLog** cmdlet sets the maximum size of a classic event log, how long each event must be retained, and what happens when the log reaches its maximum size.</span></span>
<span data-ttu-id="37815-109">Você pode usá-lo para limitar os logs de eventos em computadores locais ou remotos.</span><span class="sxs-lookup"><span data-stu-id="37815-109">You can use it to limit the event logs on local or remote computers.</span></span>

<span data-ttu-id="37815-110">Os cmdlets que contêm o substantivo EventLog (os cmdlets EventLog) funcionam somente em logs de eventos clássicos.</span><span class="sxs-lookup"><span data-stu-id="37815-110">The cmdlets that contain the EventLog noun (the EventLog cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="37815-111">Para obter eventos de logs que usam a tecnologia de log de eventos do Windows no Windows Vista e em versões posteriores do Windows, use o Get-WinEvent.</span><span class="sxs-lookup"><span data-stu-id="37815-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of Windows, use Get-WinEvent.</span></span>

## <span data-ttu-id="37815-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="37815-112">EXAMPLES</span></span>

### <span data-ttu-id="37815-113">Exemplo 1: aumentar o tamanho de um log de eventos</span><span class="sxs-lookup"><span data-stu-id="37815-113">Example 1: Increase the size of an event log</span></span>

```
PS C:\> Limit-EventLog -LogName "Windows PowerShell" -MaximumSize 20KB
```

<span data-ttu-id="37815-114">Este comando aumenta o tamanho máximo do log de eventos do Windows PowerShell no computador local para 20480 bytes (20 KB).</span><span class="sxs-lookup"><span data-stu-id="37815-114">This command increases the maximum size of the Windows PowerShell event log on the local computer to 20480 bytes (20 KB).</span></span>

### <span data-ttu-id="37815-115">Exemplo 2: manter um log de eventos durante uma duração especificada</span><span class="sxs-lookup"><span data-stu-id="37815-115">Example 2: Retain an event log for a specified duration</span></span>

```
PS C:\> Limit-EventLog -LogName Security -ComputerName "Server01", "Server02" -RetentionDays 7
```

<span data-ttu-id="37815-116">Este comando garante que os eventos no log de segurança nos computadores Server01 e Server02 sejam mantidos por pelo menos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="37815-116">This command ensures that events in the Security log on the Server01 and Server02 computers are retained for at least 7 days.</span></span>

### <span data-ttu-id="37815-117">Exemplo 3: alterar a ação de estouro de todos os logs de eventos</span><span class="sxs-lookup"><span data-stu-id="37815-117">Example 3: Change the overflow action of all event logs</span></span>

```
PS C:\> $Logs = Get-EventLog -List | ForEach {$_.log}
PS C:\> Limit-EventLog -OverflowAction OverwriteOlder -LogName $Logs
PS C:\> Get-EventLog -List

Max(K) Retain OverflowAction     Entries  Log
------ ------ --------------     -------  ---
15,168      0 OverwriteOlder       3,412  Application
512         0 OverwriteOlder           0  DFS Replication
512         0 OverwriteOlder          17  DxStudio
10,240      7 OverwriteOlder           0  HardwareEvents
512         0 OverwriteOlder           0  Internet Explorer
512         0 OverwriteOlder           0  Key Management Service
16,384      0 OverwriteOlder           4  ODiag
16,384      0 OverwriteOlder         389  OSession Security
15,168      0 OverwriteOlder      19,360  System
15,360      0 OverwriteOlder      15,828  Windows PowerShell
```

<span data-ttu-id="37815-118">Este exemplo altera a ação de estouro de todos os logs de eventos no computador local para OverwriteOlder.</span><span class="sxs-lookup"><span data-stu-id="37815-118">This example changes the overflow action of all event logs on the local computer to OverwriteOlder.</span></span>

<span data-ttu-id="37815-119">O primeiro comando obtém os nomes de log de todos os logs no computador local.</span><span class="sxs-lookup"><span data-stu-id="37815-119">The first command gets the log names of all of the logs on the local computer.</span></span>
<span data-ttu-id="37815-120">O segundo comando define a ação de estouro.</span><span class="sxs-lookup"><span data-stu-id="37815-120">The second command sets the overflow action.</span></span>
<span data-ttu-id="37815-121">O terceiro comando exibe os resultados.</span><span class="sxs-lookup"><span data-stu-id="37815-121">The third command displays the results.</span></span>

## <span data-ttu-id="37815-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="37815-122">PARAMETERS</span></span>

### <span data-ttu-id="37815-123">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="37815-123">-ComputerName</span></span>
<span data-ttu-id="37815-124">Especifica computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="37815-124">Specifies remote computers.</span></span>
<span data-ttu-id="37815-125">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="37815-125">The default is the local computer.</span></span>

<span data-ttu-id="37815-126">Digite o nome NetBIOS, um endereço IP (Internet Protocol) ou um FQDN (nome de domínio totalmente qualificado) de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="37815-126">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name (FQDN) of a remote computer.</span></span>
<span data-ttu-id="37815-127">Para especificar o computador local, digite o nome do computador, um ponto (.) ou localhost.</span><span class="sxs-lookup"><span data-stu-id="37815-127">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="37815-128">Esse parâmetro não depende da comunicação remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37815-128">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="37815-129">Você pode usar o parâmetro *ComputerName* de **Limit-EventLog** mesmo que o computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="37815-129">You can use the *ComputerName* parameter of **Limit-EventLog** even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37815-130">-LogName</span><span class="sxs-lookup"><span data-stu-id="37815-130">-LogName</span></span>
<span data-ttu-id="37815-131">Especifica os logs de evento.</span><span class="sxs-lookup"><span data-stu-id="37815-131">Specifies the event logs.</span></span>
<span data-ttu-id="37815-132">Insira o nome do log (o valor da propriedade Log; não o LogDisplayName) de um ou mais logs de eventos, separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="37815-132">Enter the log name (the value of the Log property; not the LogDisplayName) of one or more event logs, separated by commas.</span></span>
<span data-ttu-id="37815-133">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="37815-133">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="37815-134">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="37815-134">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37815-135">-MaximumSize</span><span class="sxs-lookup"><span data-stu-id="37815-135">-MaximumSize</span></span>
<span data-ttu-id="37815-136">Especifica o tamanho máximo dos logs de eventos em bytes.</span><span class="sxs-lookup"><span data-stu-id="37815-136">Specifies the maximum size of the event logs in bytes.</span></span>
<span data-ttu-id="37815-137">Insira um valor entre 64 quilobytes (KB) e 4 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="37815-137">Enter a value between 64 kilobytes (KB) and 4 gigabytes (GB).</span></span>
<span data-ttu-id="37815-138">O valor deve ser divisível por 64 KB (65536).</span><span class="sxs-lookup"><span data-stu-id="37815-138">The value must be divisible by 64 KB (65536).</span></span>

<span data-ttu-id="37815-139">Esse parâmetro especifica o valor da propriedade **MaximumKilobytes** do objeto **System. Diagnostics. EventLog** que representa um log de eventos clássico.</span><span class="sxs-lookup"><span data-stu-id="37815-139">This parameter specifies the value of the **MaximumKilobytes** property of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37815-140">-Estouro deaction</span><span class="sxs-lookup"><span data-stu-id="37815-140">-OverflowAction</span></span>
<span data-ttu-id="37815-141">Especifica o que acontece quando o log de eventos atingir seu tamanho máximo.</span><span class="sxs-lookup"><span data-stu-id="37815-141">Specifies what happens when the event log reaches its maximum size.</span></span>

<span data-ttu-id="37815-142">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="37815-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="37815-143">DoNotOverwrite: as entradas existentes são retidas e novas entradas são descartadas.</span><span class="sxs-lookup"><span data-stu-id="37815-143">DoNotOverwrite:  Existing entries are retained and new entries are discarded.</span></span>
- <span data-ttu-id="37815-144">OverwriteAsNeeded: cada nova entrada substitui a entrada mais antiga.</span><span class="sxs-lookup"><span data-stu-id="37815-144">OverwriteAsNeeded:  Each new entry overwrites the oldest entry.</span></span>
- <span data-ttu-id="37815-145">OverwriteOlder: novos eventos substituem eventos mais antigos que o valor especificado pela propriedade **MinimumRetentionDays** .</span><span class="sxs-lookup"><span data-stu-id="37815-145">OverwriteOlder:  New events overwrite events older than the value specified by the **MinimumRetentionDays** property.</span></span> <span data-ttu-id="37815-146">Se não houver eventos mais antigos do que o especificado pelo valor da propriedade **MinimumRetentionDays** , novos eventos serão descartados.</span><span class="sxs-lookup"><span data-stu-id="37815-146">If there are no events older than specified by the **MinimumRetentionDays** property value, new events are discarded.</span></span>

<span data-ttu-id="37815-147">Esse parâmetro especifica o valor da propriedade **estouraction** do objeto **System. Diagnostics. EventLog** que representa um log de eventos clássico.</span><span class="sxs-lookup"><span data-stu-id="37815-147">This parameter specifies the value of the **OverflowAction** property of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>

```yaml
Type: System.Diagnostics.OverflowAction
Parameter Sets: (All)
Aliases: OFA
Accepted values: OverwriteOlder, OverwriteAsNeeded, DoNotOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37815-148">-RetentionDays</span><span class="sxs-lookup"><span data-stu-id="37815-148">-RetentionDays</span></span>
<span data-ttu-id="37815-149">Especifica o número mínimo de dias que um evento deve permanecer no log de eventos.</span><span class="sxs-lookup"><span data-stu-id="37815-149">Specifies the minimum number of days that an event must remain in the event log.</span></span>

<span data-ttu-id="37815-150">Esse parâmetro especifica o valor da propriedade **MinimumRetentionDays** do objeto **System. Diagnostics. EventLog** que representa um log de eventos clássico.</span><span class="sxs-lookup"><span data-stu-id="37815-150">This parameter specifies the value of the **MinimumRetentionDays** property of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: MRD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37815-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="37815-151">-Confirm</span></span>
<span data-ttu-id="37815-152">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="37815-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="37815-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="37815-153">-WhatIf</span></span>
<span data-ttu-id="37815-154">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="37815-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="37815-155">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="37815-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="37815-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="37815-156">CommonParameters</span></span>
<span data-ttu-id="37815-157">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="37815-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="37815-158">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="37815-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="37815-159">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="37815-159">INPUTS</span></span>

### <span data-ttu-id="37815-160">Nenhum</span><span class="sxs-lookup"><span data-stu-id="37815-160">None</span></span>
<span data-ttu-id="37815-161">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="37815-161">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="37815-162">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="37815-162">OUTPUTS</span></span>

### <span data-ttu-id="37815-163">Nenhum</span><span class="sxs-lookup"><span data-stu-id="37815-163">None</span></span>
<span data-ttu-id="37815-164">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="37815-164">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="37815-165">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="37815-165">NOTES</span></span>

* <span data-ttu-id="37815-166">Para usar esse cmdlet no Windows Vista e em versões posteriores do Windows, abra o Windows PowerShell com a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="37815-166">To use this cmdlet on Windows Vista and later versions of Windows, open Windows PowerShell with the Run as administrator option.</span></span>

  <span data-ttu-id="37815-167">Esse cmdlet altera as propriedades do objeto **System. Diagnostics. EventLog** que representa um log de eventos clássico.</span><span class="sxs-lookup"><span data-stu-id="37815-167">This cmdlet changes the properties of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>
<span data-ttu-id="37815-168">Para ver as configurações atuais das propriedades do log de eventos, digite `Get-EventLog -List` .</span><span class="sxs-lookup"><span data-stu-id="37815-168">To see the current settings of the event log properties, type `Get-EventLog -List`.</span></span>

*

## <span data-ttu-id="37815-169">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="37815-169">RELATED LINKS</span></span>

[<span data-ttu-id="37815-170">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="37815-170">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="37815-171">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="37815-171">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="37815-172">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="37815-172">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="37815-173">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="37815-173">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="37815-174">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="37815-174">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="37815-175">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="37815-175">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="37815-176">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="37815-176">Write-EventLog</span></span>](Write-EventLog.md)
