---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/write-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-EventLog
ms.openlocfilehash: 051f02b00144805569d5130686a51a0f42b64b00
ms.sourcegitcommit: f5986121386c81acddcf324eb0526d7d092bcc8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "98584624"
---
# <span data-ttu-id="2a234-103">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="2a234-103">Write-EventLog</span></span>

## <span data-ttu-id="2a234-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2a234-104">SYNOPSIS</span></span>
<span data-ttu-id="2a234-105">Grava um evento em um log de eventos.</span><span class="sxs-lookup"><span data-stu-id="2a234-105">Writes an event to an event log.</span></span>

## <span data-ttu-id="2a234-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2a234-106">SYNTAX</span></span>

```
Write-EventLog [-LogName] <String> [-Source] <String> [[-EntryType] <EventLogEntryType>] [-Category <Int16>]
 [-EventId] <Int32> [-Message] <String> [-RawData <Byte[]>] [-ComputerName <String>] [<CommonParameters>]
```

## <span data-ttu-id="2a234-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2a234-107">DESCRIPTION</span></span>

<span data-ttu-id="2a234-108">O `Write-EventLog` cmdlet grava um evento em um log de eventos.</span><span class="sxs-lookup"><span data-stu-id="2a234-108">The `Write-EventLog` cmdlet writes an event to an event log.</span></span>

<span data-ttu-id="2a234-109">Para gravar um evento em um log de eventos, o log de eventos deve existir no computador, e a origem deve ser registrada para o log de eventos.</span><span class="sxs-lookup"><span data-stu-id="2a234-109">To write an event to an event log, the event log must exist on the computer and the source must be registered for the event log.</span></span>

<span data-ttu-id="2a234-110">Os cmdlets que contêm o substantivo **EventLog** (os cmdlets **EventLog** ) só funcionam em logs de eventos clássicos.</span><span class="sxs-lookup"><span data-stu-id="2a234-110">The cmdlets that contain the **EventLog** noun (the **EventLog** cmdlets) work only on classic event logs.</span></span> <span data-ttu-id="2a234-111">Para obter eventos de logs que usam a tecnologia de log de eventos do Windows no Windows Vista e versões posteriores do sistema operacional Windows, use o `Get-WinEvent` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2a234-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use the `Get-WinEvent` cmdlet.</span></span>

## <span data-ttu-id="2a234-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2a234-112">EXAMPLES</span></span>

### <span data-ttu-id="2a234-113">Exemplo 1: gravar um evento no log de eventos do aplicativo</span><span class="sxs-lookup"><span data-stu-id="2a234-113">Example 1: Write an event to the Application event log</span></span>

```
PS C:\> Write-EventLog -LogName "Application" -Source "MyApp" -EventID 3001 -EntryType Information -Message "MyApp added a user-requested feature to the display." -Category 1 -RawData 10,20
```

<span data-ttu-id="2a234-114">Este comando grava um evento no log de eventos de aplicativo da origem MyApp.</span><span class="sxs-lookup"><span data-stu-id="2a234-114">This command writes an event from the MyApp source to the Application event log.</span></span>

### <span data-ttu-id="2a234-115">Exemplo 2: gravar um evento no log de eventos do aplicativo de um computador remoto</span><span class="sxs-lookup"><span data-stu-id="2a234-115">Example 2: Write an event to the Application event log of a remote computer</span></span>

```
PS C:\> Write-EventLog -ComputerName "Server01" -LogName Application -Source "MyApp" -EventID 3001 -Message "MyApp added a user-requested feature to the display."
```

<span data-ttu-id="2a234-116">Este comando grava um evento da origem MyApp no log de eventos do aplicativo no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="2a234-116">This command writes an event from the MyApp source to the Application event log on the Server01 remote computer.</span></span>

## <span data-ttu-id="2a234-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2a234-117">PARAMETERS</span></span>

### <span data-ttu-id="2a234-118">-Categoria</span><span class="sxs-lookup"><span data-stu-id="2a234-118">-Category</span></span>

<span data-ttu-id="2a234-119">Especifica uma categoria de tarefa para o evento.</span><span class="sxs-lookup"><span data-stu-id="2a234-119">Specifies a task category for the event.</span></span> <span data-ttu-id="2a234-120">Insira um número inteiro que está associado às cadeias de caracteres no arquivo de mensagem de categoria para o log de eventos.</span><span class="sxs-lookup"><span data-stu-id="2a234-120">Enter an integer that is associated with the strings in the category message file for the event log.</span></span>

```yaml
Type: System.Int16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2a234-121">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="2a234-121">-ComputerName</span></span>

<span data-ttu-id="2a234-122">Especifica um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="2a234-122">Specifies a remote computer.</span></span> <span data-ttu-id="2a234-123">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="2a234-123">The default is the local computer.</span></span>

<span data-ttu-id="2a234-124">Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="2a234-124">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>

<span data-ttu-id="2a234-125">Esse parâmetro não depende da comunicação remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a234-125">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="2a234-126">Você pode usar o parâmetro **ComputerName** do `Get-EventLog` cmdlet, mesmo se o computador não estiver configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="2a234-126">You can use the **ComputerName** parameter of the `Get-EventLog` cmdlet even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2a234-127">-EntryType</span><span class="sxs-lookup"><span data-stu-id="2a234-127">-EntryType</span></span>

<span data-ttu-id="2a234-128">Especifica o tipo de entrada do evento.</span><span class="sxs-lookup"><span data-stu-id="2a234-128">Specifies the entry type of the event.</span></span> <span data-ttu-id="2a234-129">Os valores aceitáveis para esse parâmetro são: erro, aviso, informações, SuccessAudit e FailureAudit.</span><span class="sxs-lookup"><span data-stu-id="2a234-129">The acceptable values for this parameter are: Error, Warning, Information, SuccessAudit, and FailureAudit.</span></span> <span data-ttu-id="2a234-130">O valor padrão é Information.</span><span class="sxs-lookup"><span data-stu-id="2a234-130">The default value is Information.</span></span>

<span data-ttu-id="2a234-131">Para obter uma descrição dos valores, consulte [Enumeração EventLogEntryType](/dotnet/api/system.diagnostics.eventlogentrytype).</span><span class="sxs-lookup"><span data-stu-id="2a234-131">For a description of the values, see [EventLogEntryType Enumeration](/dotnet/api/system.diagnostics.eventlogentrytype).</span></span>

```yaml
Type: System.Diagnostics.EventLogEntryType
Parameter Sets: (All)
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2a234-132">-EventId</span><span class="sxs-lookup"><span data-stu-id="2a234-132">-EventId</span></span>

<span data-ttu-id="2a234-133">Especifica o identificador do evento.</span><span class="sxs-lookup"><span data-stu-id="2a234-133">Specifies the event identifier.</span></span> <span data-ttu-id="2a234-134">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="2a234-134">This parameter is required.</span></span> <span data-ttu-id="2a234-135">O valor máximo para o parâmetro **EventID** é 65535.</span><span class="sxs-lookup"><span data-stu-id="2a234-135">The maximum value for the **EventId** parameter is 65535.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: ID, EID

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2a234-136">-LogName</span><span class="sxs-lookup"><span data-stu-id="2a234-136">-LogName</span></span>

<span data-ttu-id="2a234-137">Especifica o nome do log no qual o evento será gravado.</span><span class="sxs-lookup"><span data-stu-id="2a234-137">Specifies the name of the log to which the event is written.</span></span> <span data-ttu-id="2a234-138">Insira o nome do log.</span><span class="sxs-lookup"><span data-stu-id="2a234-138">Enter the log name.</span></span> <span data-ttu-id="2a234-139">O nome do log é o valor da propriedade **log** , não o **LogDisplayName**.</span><span class="sxs-lookup"><span data-stu-id="2a234-139">The log name is the value of the **Log** property, not the **LogDisplayName**.</span></span> <span data-ttu-id="2a234-140">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="2a234-140">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="2a234-141">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="2a234-141">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2a234-142">-Mensagem</span><span class="sxs-lookup"><span data-stu-id="2a234-142">-Message</span></span>

<span data-ttu-id="2a234-143">Especifica a mensagem do evento.</span><span class="sxs-lookup"><span data-stu-id="2a234-143">Specifies the event message.</span></span> <span data-ttu-id="2a234-144">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="2a234-144">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MSG

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2a234-145">-RawData</span><span class="sxs-lookup"><span data-stu-id="2a234-145">-RawData</span></span>

<span data-ttu-id="2a234-146">Especifica os dados binários associados ao evento, em bytes.</span><span class="sxs-lookup"><span data-stu-id="2a234-146">Specifies the binary data that is associated with the event, in bytes.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: (All)
Aliases: RD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2a234-147">-Source</span><span class="sxs-lookup"><span data-stu-id="2a234-147">-Source</span></span>

<span data-ttu-id="2a234-148">Especifica a origem do evento, que normalmente é o nome do aplicativo que está gravando o evento no log.</span><span class="sxs-lookup"><span data-stu-id="2a234-148">Specifies the event source, which is typically the name of the application that is writing the event to the log.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2a234-149">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2a234-149">CommonParameters</span></span>

<span data-ttu-id="2a234-150">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2a234-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2a234-151">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2a234-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2a234-152">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2a234-152">INPUTS</span></span>

### <span data-ttu-id="2a234-153">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2a234-153">None</span></span>

<span data-ttu-id="2a234-154">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2a234-154">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2a234-155">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2a234-155">OUTPUTS</span></span>

### <span data-ttu-id="2a234-156">System. Diagnostics. EventLogEntry</span><span class="sxs-lookup"><span data-stu-id="2a234-156">System.Diagnostics.EventLogEntry</span></span>

<span data-ttu-id="2a234-157">Esse cmdlet retorna objetos que representam os eventos nos logs.</span><span class="sxs-lookup"><span data-stu-id="2a234-157">This cmdlet returns objects that represents the events in the logs.</span></span>

## <span data-ttu-id="2a234-158">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2a234-158">NOTES</span></span>

<span data-ttu-id="2a234-159">Para alguns logs de eventos do Windows, a gravação de eventos requer direitos de administrador.</span><span class="sxs-lookup"><span data-stu-id="2a234-159">For some Windows event logs, writing events requires administrator rights.</span></span> <span data-ttu-id="2a234-160">Você deve iniciar o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="2a234-160">You must start PowerShell using the **Run as Administrator** option.</span></span>

## <span data-ttu-id="2a234-161">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2a234-161">RELATED LINKS</span></span>

[<span data-ttu-id="2a234-162">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="2a234-162">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="2a234-163">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="2a234-163">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="2a234-164">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="2a234-164">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="2a234-165">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="2a234-165">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="2a234-166">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="2a234-166">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="2a234-167">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="2a234-167">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="2a234-168">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="2a234-168">Write-EventLog</span></span>](Write-EventLog.md)
