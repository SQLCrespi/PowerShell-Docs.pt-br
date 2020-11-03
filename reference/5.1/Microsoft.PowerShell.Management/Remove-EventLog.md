---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-EventLog
ms.openlocfilehash: 4cf29146727c9a54715459a2d56e47a27c5bacc0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193955"
---
# <span data-ttu-id="b489a-103">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="b489a-103">Remove-EventLog</span></span>

## <span data-ttu-id="b489a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b489a-104">SYNOPSIS</span></span>
<span data-ttu-id="b489a-105">Exclui um log de eventos ou cancela o registro de uma fonte de evento.</span><span class="sxs-lookup"><span data-stu-id="b489a-105">Deletes an event log or unregisters an event source.</span></span>

## <span data-ttu-id="b489a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b489a-106">SYNTAX</span></span>

### <span data-ttu-id="b489a-107">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="b489a-107">Default (Default)</span></span>

```
Remove-EventLog [[-ComputerName] <String[]>] [-LogName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b489a-108">Fonte</span><span class="sxs-lookup"><span data-stu-id="b489a-108">Source</span></span>

```
Remove-EventLog [[-ComputerName] <String[]>] [-Source <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b489a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b489a-109">DESCRIPTION</span></span>
<span data-ttu-id="b489a-110">O cmdlet **Remove-EventLog** exclui um arquivo de log de eventos de um computador local ou remoto e cancela o registro de todas as suas origens de eventos para o log.</span><span class="sxs-lookup"><span data-stu-id="b489a-110">The **Remove-EventLog** cmdlet deletes an event log file from a local or remote computer and unregisters all its event sources for the log.</span></span>
<span data-ttu-id="b489a-111">Você também pode usar este cmdlet para cancelar o registro de fontes de evento sem excluir nenhum dos logs de eventos.</span><span class="sxs-lookup"><span data-stu-id="b489a-111">You can also use this cmdlet to unregister event sources without deleting any event logs.</span></span>

<span data-ttu-id="b489a-112">Os cmdlets que contêm o substantivo **EventLog** , os cmdlets **EventLog** , só funcionam em logs de eventos clássicos.</span><span class="sxs-lookup"><span data-stu-id="b489a-112">The cmdlets that contain the **EventLog** noun, the **EventLog** cmdlets, work only on classic event logs.</span></span>
<span data-ttu-id="b489a-113">Para obter eventos de logs que usam a tecnologia de log de eventos do Windows no Windows Vista e versões posteriores do sistema operacional Windows, use Get-WinEvent.</span><span class="sxs-lookup"><span data-stu-id="b489a-113">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use Get-WinEvent.</span></span>

<span data-ttu-id="b489a-114">Cuidado: esse cmdlet pode excluir logs de eventos do sistema operacional, o que pode causar falhas de aplicativo e um comportamento de sistema inesperado.</span><span class="sxs-lookup"><span data-stu-id="b489a-114">CAUTION: This cmdlet can delete operating system event logs, which might cause application failures and unexpected system behavior.</span></span>

## <span data-ttu-id="b489a-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b489a-115">EXAMPLES</span></span>

### <span data-ttu-id="b489a-116">Exemplo 1: remover um log de eventos do computador local</span><span class="sxs-lookup"><span data-stu-id="b489a-116">Example 1: Remove an event log from the local computer</span></span>

```
PS C:\> Remove-EventLog -LogName "MyLog"
```

<span data-ttu-id="b489a-117">Esse comando exclui o log de eventos MyLog do computador local e cancela o registro das suas fontes de evento.</span><span class="sxs-lookup"><span data-stu-id="b489a-117">This command deletes the MyLog event log from the local computer and unregisters its event sources.</span></span>

### <span data-ttu-id="b489a-118">Exemplo 2: remover um log de eventos de vários computadores</span><span class="sxs-lookup"><span data-stu-id="b489a-118">Example 2: Remove an event log from several computers</span></span>

```
PS C:\> Remove-EventLog -LogName "MyLog", "TestLog" -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="b489a-119">Esse comando exclui os logs de eventos MyLog e TestLog do computador local e os computadores remotos Server01 e Server02.</span><span class="sxs-lookup"><span data-stu-id="b489a-119">This command deletes the MyLog and TestLog event logs from the local computer and the Server01 and Server02 remote computers.</span></span>
<span data-ttu-id="b489a-120">O comando também cancela o registro de fontes de evento para esses logs.</span><span class="sxs-lookup"><span data-stu-id="b489a-120">The command also unregisters the event sources for these logs.</span></span>

### <span data-ttu-id="b489a-121">Exemplo 3: excluir uma origem do evento</span><span class="sxs-lookup"><span data-stu-id="b489a-121">Example 3: Delete an event source</span></span>

```
PS C:\> Remove-EventLog -Source "MyApp"
```

<span data-ttu-id="b489a-122">Esse comando exclui a origem do evento MyApp dos logs no computador local.</span><span class="sxs-lookup"><span data-stu-id="b489a-122">This command deletes the MyApp event source from the logs on the local computer.</span></span>
<span data-ttu-id="b489a-123">Quando o comando é concluído, o programa MyApp não pode gravar em nenhum log de eventos.</span><span class="sxs-lookup"><span data-stu-id="b489a-123">When the command finishes, the MyApp program cannot write to any event logs.</span></span>

### <span data-ttu-id="b489a-124">Exemplo 4: remover um log de eventos e confirmar a ação</span><span class="sxs-lookup"><span data-stu-id="b489a-124">Example 4: Remove an event log and confirm the action</span></span>

```
The first command lists the event logs on the local computer.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
15,168      7 OverwriteAsNeeded          12 ZapLog

The second command deletes the ZapLog event log.
PS C:\> Remove-EventLog -LogName "ZapLog"

The third command lists the event logs again. The ZapLog event log no longer appears in the list.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
```

<span data-ttu-id="b489a-125">Estes comandos mostram como listar os logs de eventos em um computador e verificar se um comando **Remove-EventLog** foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="b489a-125">These commands show how to list the event logs on a computer and verify that a **Remove-EventLog** command was successful.</span></span>

### <span data-ttu-id="b489a-126">Exemplo 5: remover uma origem do evento e confirmar a ação</span><span class="sxs-lookup"><span data-stu-id="b489a-126">Example 5: Remove an event source and confirm the action</span></span>

```
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'" | foreach {$_.sources}
MyApp
TestApp
PS C:\> Remove-Eventlog -Source "MyApp"
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'"} | foreach {$_.sources}
TestApp
```

<span data-ttu-id="b489a-127">Esses comandos usam o cmdlet Get-WmiObject para listar as fontes de evento no computador local.</span><span class="sxs-lookup"><span data-stu-id="b489a-127">These commands use the Get-WmiObject cmdlet to list the event sources on the local computer.</span></span>
<span data-ttu-id="b489a-128">É possível usar esses comandos para verificar o êxito de um comando ou para excluir uma fonte de evento.</span><span class="sxs-lookup"><span data-stu-id="b489a-128">You can these commands to verify the success of a command or to delete an event source.</span></span>

<span data-ttu-id="b489a-129">O primeiro comando obtém as fontes de eventos do log de eventos TestLog no computador local.</span><span class="sxs-lookup"><span data-stu-id="b489a-129">The first command gets the event sources of the TestLog event log on the local computer.</span></span>
<span data-ttu-id="b489a-130">MyApp é uma das fontes.</span><span class="sxs-lookup"><span data-stu-id="b489a-130">MyApp is one of the sources.</span></span>

<span data-ttu-id="b489a-131">O segundo comando usa o parâmetro *Source* de **Remove-EventLog** para excluir a origem do evento MyApp.</span><span class="sxs-lookup"><span data-stu-id="b489a-131">The second command uses the *Source* parameter of **Remove-EventLog** to delete the MyApp event source.</span></span>

<span data-ttu-id="b489a-132">O terceiro comando é idêntico ao primeiro.</span><span class="sxs-lookup"><span data-stu-id="b489a-132">The third command is identical to the first.</span></span>
<span data-ttu-id="b489a-133">Ele mostra que a fonte de evento MyApp foi excluída.</span><span class="sxs-lookup"><span data-stu-id="b489a-133">It shows that the MyApp event source was deleted.</span></span>

## <span data-ttu-id="b489a-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b489a-134">PARAMETERS</span></span>

### <span data-ttu-id="b489a-135">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="b489a-135">-ComputerName</span></span>
<span data-ttu-id="b489a-136">Especifica um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="b489a-136">Specifies a remote computer.</span></span>
<span data-ttu-id="b489a-137">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="b489a-137">The default is the local computer.</span></span>

<span data-ttu-id="b489a-138">Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="b489a-138">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="b489a-139">Para especificar o computador local, digite o nome do computador, um ponto (.) ou localhost.</span><span class="sxs-lookup"><span data-stu-id="b489a-139">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="b489a-140">Esse parâmetro não depende da comunicação remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b489a-140">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="b489a-141">Você pode usar o parâmetro *ComputerName* de **Remove-EventLog** mesmo que o computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="b489a-141">You can use the *ComputerName* parameter of **Remove-EventLog** even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b489a-142">-LogName</span><span class="sxs-lookup"><span data-stu-id="b489a-142">-LogName</span></span>
<span data-ttu-id="b489a-143">Especifica os logs de evento.</span><span class="sxs-lookup"><span data-stu-id="b489a-143">Specifies the event logs.</span></span>
<span data-ttu-id="b489a-144">Insira o nome do log de um ou mais logs de eventos, separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="b489a-144">Enter the log name of one or more event logs, separated by commas.</span></span>
<span data-ttu-id="b489a-145">O nome do log é o valor da propriedade **log** , não o *LogDisplayName* , caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b489a-145">The log name is the value of the **Log** property, not the *LogDisplayName* , Wildcard characters are not permitted.</span></span>
<span data-ttu-id="b489a-146">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="b489a-146">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b489a-147">-Source</span><span class="sxs-lookup"><span data-stu-id="b489a-147">-Source</span></span>
<span data-ttu-id="b489a-148">Especifica as origens de eventos que esse cmdlet cancela o registro.</span><span class="sxs-lookup"><span data-stu-id="b489a-148">Specifies the event sources that this cmdlet unregisters.</span></span>
<span data-ttu-id="b489a-149">Insira os nomes de origem, não o nome do executável, separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="b489a-149">Enter the source names, not the executable name, separated by commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: SRC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b489a-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b489a-150">-Confirm</span></span>
<span data-ttu-id="b489a-151">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b489a-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b489a-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b489a-152">-WhatIf</span></span>
<span data-ttu-id="b489a-153">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="b489a-153">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b489a-154">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="b489a-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b489a-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b489a-155">CommonParameters</span></span>
<span data-ttu-id="b489a-156">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b489a-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b489a-157">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b489a-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b489a-158">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b489a-158">INPUTS</span></span>

### <span data-ttu-id="b489a-159">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b489a-159">None</span></span>
<span data-ttu-id="b489a-160">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b489a-160">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="b489a-161">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b489a-161">OUTPUTS</span></span>

### <span data-ttu-id="b489a-162">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b489a-162">None</span></span>
<span data-ttu-id="b489a-163">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="b489a-163">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="b489a-164">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b489a-164">NOTES</span></span>

* <span data-ttu-id="b489a-165">Para usar **Remove-EventLog** no Windows Vista e em versões posteriores do sistema operacional Windows, inicie o Windows PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="b489a-165">To use **Remove-EventLog** on Windows Vista and later versions of the Windows operating system, start Windows PowerShell by using the Run as administrator option.</span></span>

  <span data-ttu-id="b489a-166">Se você remover um log de eventos e, em seguida, recriar o log, você não poderá registrar as mesmas fontes de evento.</span><span class="sxs-lookup"><span data-stu-id="b489a-166">If you remove an event log and then re-create the log, you will not be able to register the same event sources.</span></span>
<span data-ttu-id="b489a-167">Aplicativos que usavam as fontes de eventos para gravar entradas para o log original não serão capazes de gravar no novo log.</span><span class="sxs-lookup"><span data-stu-id="b489a-167">Applications that used the events sources to write entries to the original log will not be able to write to the new log.</span></span>

* <span data-ttu-id="b489a-168">Quando você cancela o registro de uma fonte de evento para um log específico, a origem do evento pode ser impedida de gravar entradas nos outros logs de eventos.</span><span class="sxs-lookup"><span data-stu-id="b489a-168">When you unregister an event source for a particular log, the event source might be prevented from writing entries in other event logs.</span></span>

## <span data-ttu-id="b489a-169">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b489a-169">RELATED LINKS</span></span>

[<span data-ttu-id="b489a-170">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="b489a-170">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="b489a-171">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="b489a-171">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="b489a-172">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="b489a-172">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="b489a-173">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="b489a-173">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="b489a-174">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="b489a-174">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="b489a-175">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="b489a-175">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="b489a-176">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="b489a-176">Write-EventLog</span></span>](Write-EventLog.md)
