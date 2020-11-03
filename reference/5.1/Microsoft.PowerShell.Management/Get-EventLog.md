---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 3/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventLog
ms.openlocfilehash: ab1a97dc3c78bbfdcc239fd573ef3b1f839e2b21
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194183"
---
# <span data-ttu-id="11763-103">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="11763-103">Get-EventLog</span></span>

## <span data-ttu-id="11763-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="11763-104">SYNOPSIS</span></span>
<span data-ttu-id="11763-105">Obtém os eventos em um log de eventos ou uma lista dos logs de eventos no computador local ou nos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="11763-105">Gets the events in an event log, or a list of the event logs, on the local computer or remote computers.</span></span>

## <span data-ttu-id="11763-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="11763-106">SYNTAX</span></span>

### <span data-ttu-id="11763-107">LogName (padrão)</span><span class="sxs-lookup"><span data-stu-id="11763-107">LogName (Default)</span></span>

```
Get-EventLog [-LogName] <String> [-ComputerName <String[]>] [-Newest <Int32>] [-After <DateTime>]
 [-Before <DateTime>] [-UserName <String[]>] [[-InstanceId] <Int64[]>] [-Index <Int32[]>]
 [-EntryType <String[]>] [-Source <String[]>] [-Message <String>] [-AsBaseObject]
 [<CommonParameters>]
```

### <span data-ttu-id="11763-108">Lista</span><span class="sxs-lookup"><span data-stu-id="11763-108">List</span></span>

```
Get-EventLog [-ComputerName <String[]>] [-List] [-AsString] [<CommonParameters>]
```

## <span data-ttu-id="11763-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="11763-109">DESCRIPTION</span></span>

<span data-ttu-id="11763-110">O `Get-EventLog` cmdlet obtém eventos e logs de eventos de computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="11763-110">The `Get-EventLog` cmdlet gets events and event logs from local and remote computers.</span></span> <span data-ttu-id="11763-111">Por padrão, o `Get-EventLog` Obtém logs do computador local.</span><span class="sxs-lookup"><span data-stu-id="11763-111">By default, `Get-EventLog` gets logs from the local computer.</span></span> <span data-ttu-id="11763-112">Para obter logs de computadores remotos, use o parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="11763-112">To get logs from remote computers, use the **ComputerName** parameter.</span></span>

<span data-ttu-id="11763-113">Você pode usar os `Get-EventLog` parâmetros e os valores de propriedade para pesquisar eventos.</span><span class="sxs-lookup"><span data-stu-id="11763-113">You can use the `Get-EventLog` parameters and property values to search for events.</span></span> <span data-ttu-id="11763-114">O cmdlet obtém os eventos que correspondem aos valores de propriedade especificados.</span><span class="sxs-lookup"><span data-stu-id="11763-114">The cmdlet gets events that match the specified property values.</span></span>

<span data-ttu-id="11763-115">Os cmdlets do PowerShell que contêm o `EventLog` substantivo só funcionam em logs de eventos clássicos do Windows, como aplicativo, sistema ou segurança.</span><span class="sxs-lookup"><span data-stu-id="11763-115">PowerShell cmdlets that contain the `EventLog` noun work only on Windows classic event logs such as Application, System, or Security.</span></span> <span data-ttu-id="11763-116">Para obter logs que usam a tecnologia de log de eventos do Windows no Windows Vista e versões posteriores do Windows, use `Get-WinEvent` .</span><span class="sxs-lookup"><span data-stu-id="11763-116">To get logs that use the Windows Event Log technology in Windows Vista and later Windows versions, use `Get-WinEvent`.</span></span>

> [!NOTE]
> <span data-ttu-id="11763-117">`Get-EventLog` usa uma API do Win32 que é preterida.</span><span class="sxs-lookup"><span data-stu-id="11763-117">`Get-EventLog` uses a Win32 API that is deprecated.</span></span> <span data-ttu-id="11763-118">Os resultados podem não ser precisos.</span><span class="sxs-lookup"><span data-stu-id="11763-118">The results may not be accurate.</span></span> <span data-ttu-id="11763-119">`Get-WinEvent`Em vez disso, use o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="11763-119">Use the `Get-WinEvent` cmdlet instead.</span></span>

## <span data-ttu-id="11763-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="11763-120">EXAMPLES</span></span>

### <span data-ttu-id="11763-121">Exemplo 1: obter logs de eventos no computador local</span><span class="sxs-lookup"><span data-stu-id="11763-121">Example 1: Get event logs on the local computer</span></span>

<span data-ttu-id="11763-122">Este exemplo exibe a lista de logs de eventos que estão disponíveis no computador local.</span><span class="sxs-lookup"><span data-stu-id="11763-122">This example displays the list of event logs that are available on the local computer.</span></span> <span data-ttu-id="11763-123">Os nomes na coluna log são usados com o parâmetro **LogName** para especificar qual log é pesquisado em busca de eventos.</span><span class="sxs-lookup"><span data-stu-id="11763-123">The names in the Log column are used with the **LogName** parameter to specify which log is searched for events.</span></span>

```powershell
Get-EventLog -List
```

```Output
Max(K)   Retain   OverflowAction      Entries  Log
------   ------   --------------      -------  ---
15,168        0   OverwriteAsNeeded   20,792   Application
15,168        0   OverwriteAsNeeded   12,559   System
15,360        0   OverwriteAsNeeded   11,173   Windows PowerShell
```

<span data-ttu-id="11763-124">O `Get-EventLog` cmdlet usa o parâmetro **list** para exibir os logs disponíveis.</span><span class="sxs-lookup"><span data-stu-id="11763-124">The `Get-EventLog` cmdlet uses the **List** parameter to display the available logs.</span></span>

### <span data-ttu-id="11763-125">Exemplo 2: obter entradas recentes de um log de eventos no computador local</span><span class="sxs-lookup"><span data-stu-id="11763-125">Example 2: Get recent entries from an event log on the local computer</span></span>

<span data-ttu-id="11763-126">Este exemplo obtém entradas recentes do log de eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="11763-126">This example gets recent entries from the System event log.</span></span>

```powershell
Get-EventLog -LogName System -Newest 5
```

```Output
Index   Time          EntryType    Source              InstanceID   Message
-----   ----          ---------    ------              ----------   -------
13820   Jan 17 19:16  Error        DCOM                     10016   The description for Event...
13819   Jan 17 19:08  Error        DCOM                     10016   The description for Event...
13818   Jan 17 19:06  Information  Service Control...  1073748864   The start type of the Back...
13817   Jan 17 19:05  Error        DCOM                     10016   The description for Event...
13815   Jan 17 19:03  Information  Microsoft-Windows...        35   The time service is now sync...
```

<span data-ttu-id="11763-127">O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log de eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="11763-127">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System event log.</span></span> <span data-ttu-id="11763-128">O parâmetro **mais recente** retorna os cinco eventos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="11763-128">The **Newest** parameter returns the five most recent events.</span></span>

### <span data-ttu-id="11763-129">Exemplo 3: localizar todas as fontes para um número específico de entradas em um log de eventos</span><span class="sxs-lookup"><span data-stu-id="11763-129">Example 3: Find all sources for a specific number of entries in an event log</span></span>

<span data-ttu-id="11763-130">Este exemplo mostra como localizar todas as fontes incluídas nas 1000 entradas mais recentes no log de eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="11763-130">This example shows how to find all of the sources that are included in the 1000 most recent entries in the System event log.</span></span>

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$Events | Group-Object -Property Source -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count   Name
-----   ----
  110   DCOM
   65   Service Control Manager
   51   Microsoft-Windows-Kern...
   14   EventLog
   14   BTHUSB
   13   Win32k
```

<span data-ttu-id="11763-131">O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log do sistema.</span><span class="sxs-lookup"><span data-stu-id="11763-131">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="11763-132">O parâmetro **mais recente** seleciona os 1000 eventos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="11763-132">The **Newest** parameter selects the 1000 most recent events.</span></span> <span data-ttu-id="11763-133">Os objetos de evento são armazenados na `$Events` variável.</span><span class="sxs-lookup"><span data-stu-id="11763-133">The event objects are stored in the `$Events` variable.</span></span> <span data-ttu-id="11763-134">Os `$Events` objetos são enviados para o pipeline para o `Group-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="11763-134">The `$Events` objects are sent down the pipeline to the `Group-Object` cmdlet.</span></span>
<span data-ttu-id="11763-135">`Group-Object` usa o parâmetro **Property** para agrupar os objetos por origem e conta o número de objetos para cada fonte.</span><span class="sxs-lookup"><span data-stu-id="11763-135">`Group-Object` uses the **Property** parameter to group the objects by source and counts the number of objects for each source.</span></span> <span data-ttu-id="11763-136">O parâmetro **NoElement** remove os membros do grupo da saída.</span><span class="sxs-lookup"><span data-stu-id="11763-136">The **NoElement** parameter removes the group members from the output.</span></span>
<span data-ttu-id="11763-137">O `Sort-Object` cmdlet usa o parâmetro **Property** para classificar pela contagem de cada nome de origem.</span><span class="sxs-lookup"><span data-stu-id="11763-137">The `Sort-Object` cmdlet uses the **Property** parameter to sort by the count of each source name.</span></span>
<span data-ttu-id="11763-138">O parâmetro **decrescente** classifica a lista em ordem por contagem, da mais alta para a mais baixa.</span><span class="sxs-lookup"><span data-stu-id="11763-138">The **Descending** parameter sorts the list in order by count from highest to lowest.</span></span>

### <span data-ttu-id="11763-139">Exemplo 4: obter eventos de erro de um log de eventos específico</span><span class="sxs-lookup"><span data-stu-id="11763-139">Example 4: Get error events from a specific event log</span></span>

<span data-ttu-id="11763-140">Este exemplo obtém eventos de erro do log de eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="11763-140">This example gets error events from the System event log.</span></span>

```powershell
Get-EventLog -LogName System -EntryType Error
```

```Output
Index Time          EntryType   Source  InstanceID Message
----- ----          ---------   ------  ---------- -------
13296 Jan 16 13:53  Error       DCOM    10016 The description for Event ID '10016' in Source...
13291 Jan 16 13:51  Error       DCOM    10016 The description for Event ID '10016' in Source...
13245 Jan 16 11:45  Error       DCOM    10016 The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error       DCOM    10016 The description for Event ID '10016' in Source...
```

<span data-ttu-id="11763-141">O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log do sistema.</span><span class="sxs-lookup"><span data-stu-id="11763-141">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="11763-142">O parâmetro **EntryType** filtra os eventos para mostrar apenas os eventos de erro.</span><span class="sxs-lookup"><span data-stu-id="11763-142">The **EntryType** parameter filters the events to show only Error events.</span></span>

### <span data-ttu-id="11763-143">Exemplo 5: obter eventos de um log de eventos com uma InstanceId e um valor de origem</span><span class="sxs-lookup"><span data-stu-id="11763-143">Example 5: Get events from an event log with an InstanceId and Source value</span></span>

<span data-ttu-id="11763-144">Este exemplo obtém eventos do log do sistema para um InstanceId e uma origem específicos.</span><span class="sxs-lookup"><span data-stu-id="11763-144">This example gets events from the System log for a specific InstanceId and Source.</span></span>

```powershell
Get-EventLog -LogName System -InstanceId 10016 -Source DCOM
```

```Output
Index Time          EntryType  Source  InstanceID  Message
----- ----          ---------  ------  ----------  -------
13245 Jan 16 11:45  Error      DCOM         10016  The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error      DCOM         10016  The description for Event ID '10016' in Source...
13219 Jan 16 10:00  Error      DCOM         10016  The description for Event ID '10016' in Source...
```

<span data-ttu-id="11763-145">O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log do sistema.</span><span class="sxs-lookup"><span data-stu-id="11763-145">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="11763-146">O parâmetro **InstanceId** seleciona os eventos com a ID de instância especificada.</span><span class="sxs-lookup"><span data-stu-id="11763-146">The **InstanceID** parameter selects the events with the specified Instance ID.</span></span> <span data-ttu-id="11763-147">O parâmetro **Source** especifica a propriedade de evento.</span><span class="sxs-lookup"><span data-stu-id="11763-147">The **Source** parameter specifies the event property.</span></span>

### <span data-ttu-id="11763-148">Exemplo 6: obter eventos de vários computadores</span><span class="sxs-lookup"><span data-stu-id="11763-148">Example 6: Get events from multiple computers</span></span>

<span data-ttu-id="11763-149">Esse comando obtém os eventos do log de eventos do sistema em três computadores: Server01, Server02 e Server03.</span><span class="sxs-lookup"><span data-stu-id="11763-149">This command gets the events from the System event log on three computers: Server01, Server02, and Server03.</span></span>

```powershell
Get-EventLog -LogName System -ComputerName Server01, Server02, Server03
```

<span data-ttu-id="11763-150">O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log do sistema.</span><span class="sxs-lookup"><span data-stu-id="11763-150">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="11763-151">O parâmetro **ComputerName** usa uma cadeia de caracteres separada por vírgulas para listar os computadores dos quais você deseja obter os logs de eventos.</span><span class="sxs-lookup"><span data-stu-id="11763-151">The **ComputerName** parameter uses a comma-separated string to list the computers from which you want to get the event logs.</span></span>

### <span data-ttu-id="11763-152">Exemplo 7: obter todos os eventos que incluem uma palavra específica na mensagem</span><span class="sxs-lookup"><span data-stu-id="11763-152">Example 7: Get all events that include a specific word in the message</span></span>

<span data-ttu-id="11763-153">Esse comando obtém todos os eventos no log de eventos do sistema que contêm uma palavra específica na mensagem do evento.</span><span class="sxs-lookup"><span data-stu-id="11763-153">This command gets all the events in the System event log that contain a specific word in the event's message.</span></span> <span data-ttu-id="11763-154">É possível que o valor do parâmetro de **mensagem** especificado seja incluído no conteúdo da mensagem, mas não seja exibido no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11763-154">It's possible that your specified **Message** parameter's value is included in the message's content but isn't displayed on the PowerShell console.</span></span>

```powershell
Get-EventLog -LogName System -Message *description*
```

```Output
Index Time          EntryType   Source       InstanceID   Message
----- ----          ---------   ------       ----------   -------
13821 Jan 17 19:17  Error       DCOM              10016   The description for Event ID '10016'...
13820 Jan 17 19:16  Error       DCOM              10016   The description for Event ID '10016'...
13819 Jan 17 19:08  Error       DCOM              10016   The description for Event ID '10016'...
```

<span data-ttu-id="11763-155">O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log de eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="11763-155">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System event log.</span></span> <span data-ttu-id="11763-156">O parâmetro **Message** especifica uma palavra a ser pesquisada no campo Message de cada evento.</span><span class="sxs-lookup"><span data-stu-id="11763-156">The **Message** parameter specifies a word to search for in the message field of each event.</span></span>

### <span data-ttu-id="11763-157">Exemplo 8: exibir os valores de propriedade de um evento</span><span class="sxs-lookup"><span data-stu-id="11763-157">Example 8: Display the property values of an event</span></span>

<span data-ttu-id="11763-158">Este exemplo mostra como exibir todas as propriedades e valores de um evento.</span><span class="sxs-lookup"><span data-stu-id="11763-158">This example shows how to display all of an event's properties and values.</span></span>

```powershell
$A = Get-EventLog -LogName System -Newest 1
$A | Select-Object -Property *
```

```Output
EventID            : 10016
MachineName        : localhost
Data               : {}
Index              : 13821
Category           : (0)
CategoryNumber     : 0
EntryType          : Error
Message            : The description for Event ID '10016' in Source 'DCOM'...
Source             : DCOM
ReplacementStrings : {Local,...}
InstanceId         : 10016
TimeGenerated      : 1/17/2019 19:17:23
TimeWritten        : 1/17/2019 19:17:23
UserName           : username
Site               :
Container          :
```

<span data-ttu-id="11763-159">O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log de eventos do sistema.</span><span class="sxs-lookup"><span data-stu-id="11763-159">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System event log.</span></span> <span data-ttu-id="11763-160">O parâmetro **mais** recente seleciona o objeto de evento mais recente.</span><span class="sxs-lookup"><span data-stu-id="11763-160">The **Newest** parameter selects the most recent event object.</span></span> <span data-ttu-id="11763-161">O objeto é armazenado na `$A` variável.</span><span class="sxs-lookup"><span data-stu-id="11763-161">The object is stored in the `$A` variable.</span></span> <span data-ttu-id="11763-162">O objeto na `$A` variável é enviado ao pipeline para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="11763-162">The object in the `$A` variable is sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="11763-163">`Select-Object` usa o parâmetro **Property** com um asterisco ( `*` ) para selecionar todas as propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="11763-163">`Select-Object` uses the **Property** parameter with an asterisk (`*`) to select all of the object's properties.</span></span>

### <span data-ttu-id="11763-164">Exemplo 9: obter eventos de um log de eventos usando uma origem e uma ID de evento</span><span class="sxs-lookup"><span data-stu-id="11763-164">Example 9: Get events from an event log using a source and event ID</span></span>

<span data-ttu-id="11763-165">Este exemplo obtém eventos para uma origem especificada e uma ID de evento.</span><span class="sxs-lookup"><span data-stu-id="11763-165">This example gets events for a specified Source and Event ID.</span></span>

```powershell
Get-EventLog -LogName Application -Source Outlook | Where-Object {$_.EventID -eq 63} |
              Select-Object -Property Source, EventID, InstanceId, Message
```

```Output
Source   EventID   InstanceId   Message
------   -------   ----------   -------
Outlook       63   1073741887   The Exchange web service request succeeded.
Outlook       63   1073741887   Outlook detected a change notification.
Outlook       63   1073741887   The Exchange web service request succeeded.
```

<span data-ttu-id="11763-166">O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log de eventos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="11763-166">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the Application event log.</span></span> <span data-ttu-id="11763-167">O parâmetro **Source** especifica o nome do aplicativo, Outlook.</span><span class="sxs-lookup"><span data-stu-id="11763-167">The **Source** parameter specifies the application name, Outlook.</span></span> <span data-ttu-id="11763-168">Os objetos são enviados para o pipeline para o `Where-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="11763-168">The objects are sent down the pipeline to the `Where-Object` cmdlet.</span></span> <span data-ttu-id="11763-169">Para cada objeto no pipeline, o `Where-Object` cmdlet usa a variável `$_.EventID` para comparar a propriedade de ID do evento com o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="11763-169">For each object in the pipeline, the `Where-Object` cmdlet uses the variable `$_.EventID` to compare the Event ID property to the specified value.</span></span> <span data-ttu-id="11763-170">Os objetos são enviados para o pipeline para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="11763-170">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="11763-171">`Select-Object` usa o parâmetro **Property** para selecionar as propriedades a serem exibidas no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11763-171">`Select-Object` uses the **Property** parameter to select the properties to display in the PowerShell console.</span></span>

### <span data-ttu-id="11763-172">Exemplo 10: obter eventos e agrupar por uma propriedade</span><span class="sxs-lookup"><span data-stu-id="11763-172">Example 10: Get events and group by a property</span></span>

```powershell
Get-EventLog -LogName System -UserName NT* | Group-Object -Property UserName -NoElement |
              Select-Object -Property Count, Name
```

```Output
Count  Name
-----  ----
6031   NT AUTHORITY\SYSTEM
  42   NT AUTHORITY\LOCAL SERVICE
   4   NT AUTHORITY\NETWORK SERVICE
```

<span data-ttu-id="11763-173">O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log do sistema.</span><span class="sxs-lookup"><span data-stu-id="11763-173">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="11763-174">O parâmetro **username** inclui o curinga asterisco ( `*` ) para especificar uma parte do nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="11763-174">The **UserName** parameter includes the asterisk (`*`) wildcard to specify a portion of the user name.</span></span> <span data-ttu-id="11763-175">Os objetos de evento são enviados para o pipeline para o `Group-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="11763-175">The event objects are sent down the pipeline to the `Group-Object` cmdlet.</span></span> <span data-ttu-id="11763-176">`Group-Object` usa o parâmetro **Property** para especificar que a propriedade **username** é usada para agrupar os objetos e contar o número de objetos para cada nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="11763-176">`Group-Object` uses the **Property** parameter to specify that the **UserName** property is used to group the objects and count the number of objects for each user name.</span></span> <span data-ttu-id="11763-177">O parâmetro **NoElement** remove os membros do grupo da saída.</span><span class="sxs-lookup"><span data-stu-id="11763-177">The **NoElement** parameter removes the group members from the output.</span></span> <span data-ttu-id="11763-178">Os objetos são enviados para o pipeline para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="11763-178">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="11763-179">`Select-Object` usa o parâmetro **Property** para selecionar as propriedades a serem exibidas no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11763-179">`Select-Object` uses the **Property** parameter to select the properties to display in the PowerShell console.</span></span>

### <span data-ttu-id="11763-180">Exemplo 11: obter eventos que ocorreram durante um intervalo de data e hora específico</span><span class="sxs-lookup"><span data-stu-id="11763-180">Example 11: Get events that occurred during a specific date and time range</span></span>

<span data-ttu-id="11763-181">Este exemplo obtém eventos de erro do log de eventos do sistema para um intervalo de data e hora especificado.</span><span class="sxs-lookup"><span data-stu-id="11763-181">This example gets Error events from the System event log for a specified date and time range.</span></span> <span data-ttu-id="11763-182">Os parâmetros **before** e **After** definem o intervalo de data e hora, mas são excluídos da saída.</span><span class="sxs-lookup"><span data-stu-id="11763-182">The **Before** and **After** parameters set the date and time range but are excluded from the output.</span></span>

```powershell
$Begin = Get-Date -Date '1/17/2019 08:00:00'
$End = Get-Date -Date '1/17/2019 17:00:00'
Get-EventLog -LogName System -EntryType Error -After $Begin -Before $End
```

```Output
Index Time          EntryType   Source   InstanceID  Message
----- ----          ---------   ------   ----------  -------
13821 Jan 17 13:40  Error       DCOM          10016  The description for Event ID...
13820 Jan 17 13:11  Error       DCOM          10016  The description for Event ID...
...
12372 Jan 17 10:08  Error       DCOM          10016  The description for Event ID...
12371 Jan 17 09:04  Error       DCOM          10016  The description for Event ID...
```

<span data-ttu-id="11763-183">O `Get-Date` cmdlet usa o parâmetro **Date** para especificar uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="11763-183">The `Get-Date` cmdlet uses the **Date** parameter to specify a date and time.</span></span> <span data-ttu-id="11763-184">Os objetos **DateTime** são armazenados nas `$Begin` variáveis e `$End` .</span><span class="sxs-lookup"><span data-stu-id="11763-184">The **DateTime** objects are stored in the `$Begin` and `$End` variables.</span></span> <span data-ttu-id="11763-185">O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log do sistema.</span><span class="sxs-lookup"><span data-stu-id="11763-185">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="11763-186">O parâmetro **EntryType** especifica o tipo de evento Error.</span><span class="sxs-lookup"><span data-stu-id="11763-186">The **EntryType** parameter specifies the Error event type.</span></span> <span data-ttu-id="11763-187">O intervalo de data e hora é definido pelo parâmetro **After** e `$Begin` a variável e o parâmetro **before** e a `$End` variável.</span><span class="sxs-lookup"><span data-stu-id="11763-187">The date and time range is set by the **After** parameter and `$Begin` variable and the **Before** parameter and `$End` variable.</span></span>

## <span data-ttu-id="11763-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="11763-188">PARAMETERS</span></span>

### <span data-ttu-id="11763-189">-Depois de</span><span class="sxs-lookup"><span data-stu-id="11763-189">-After</span></span>

<span data-ttu-id="11763-190">Obtém os eventos que ocorreram após uma data e hora especificadas.</span><span class="sxs-lookup"><span data-stu-id="11763-190">Gets events that occurred after a specified date and time.</span></span> <span data-ttu-id="11763-191">A data e a hora do parâmetro **After** são excluídas da saída.</span><span class="sxs-lookup"><span data-stu-id="11763-191">The **After** parameter date and time are excluded from the output.</span></span> <span data-ttu-id="11763-192">Insira um objeto **DateTime** , como o valor retornado pelo `Get-Date` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="11763-192">Enter a **DateTime** object, such as the value returned by the `Get-Date` cmdlet.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="11763-193">-Asbaseobject</span><span class="sxs-lookup"><span data-stu-id="11763-193">-AsBaseObject</span></span>

<span data-ttu-id="11763-194">Indica que esse cmdlet retorna um objeto **System. Diagnostics. EventLogEntry** padrão para cada evento.</span><span class="sxs-lookup"><span data-stu-id="11763-194">Indicates that this cmdlet returns a standard **System.Diagnostics.EventLogEntry** object for each event.</span></span> <span data-ttu-id="11763-195">Sem esse parâmetro, `Get-EventLog` retorna um objeto **PSObject** estendido com as propriedades **EventLogName** , **Source** e **InstanceId** adicionais.</span><span class="sxs-lookup"><span data-stu-id="11763-195">Without this parameter, `Get-EventLog` returns an extended **PSObject** object with additional **EventLogName** , **Source** , and **InstanceId** properties.</span></span>

<span data-ttu-id="11763-196">Para ver o efeito desse parâmetro, redirecione os eventos para o `Get-Member` cmdlet e examine o valor **TypeName** no resultado.</span><span class="sxs-lookup"><span data-stu-id="11763-196">To see the effect of this parameter, pipe the events to the `Get-Member` cmdlet and examine the **TypeName** value in the result.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="11763-197">-AsString</span><span class="sxs-lookup"><span data-stu-id="11763-197">-AsString</span></span>

<span data-ttu-id="11763-198">Indica que esse cmdlet retorna a saída como cadeias de caracteres, em vez de objetos.</span><span class="sxs-lookup"><span data-stu-id="11763-198">Indicates that this cmdlet returns the output as strings, instead of objects.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="11763-199">-Antes de</span><span class="sxs-lookup"><span data-stu-id="11763-199">-Before</span></span>

<span data-ttu-id="11763-200">Obtém os eventos que ocorreram antes de uma data e hora especificadas.</span><span class="sxs-lookup"><span data-stu-id="11763-200">Gets events that occurred before a specified date and time.</span></span> <span data-ttu-id="11763-201">A data e a hora do parâmetro **before** são excluídas da saída.</span><span class="sxs-lookup"><span data-stu-id="11763-201">The **Before** parameter date and time are excluded from the output.</span></span> <span data-ttu-id="11763-202">Insira um objeto **DateTime** , como o valor retornado pelo `Get-Date` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="11763-202">Enter a **DateTime** object, such as the value returned by the `Get-Date` cmdlet.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="11763-203">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="11763-203">-ComputerName</span></span>

<span data-ttu-id="11763-204">Esse parâmetro especifica o nome NetBIOS de um computador remoto, endereço IP (Internet Protocol) ou um FQDN (nome de domínio totalmente qualificado).</span><span class="sxs-lookup"><span data-stu-id="11763-204">This parameter specifies a remote computer's NetBIOS name, Internet Protocol (IP) address, or a fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="11763-205">Se o parâmetro **ComputerName** não for especificado, `Get-EventLog` o padrão será o computador local.</span><span class="sxs-lookup"><span data-stu-id="11763-205">If the **ComputerName** parameter isn't specified, `Get-EventLog` defaults to the local computer.</span></span> <span data-ttu-id="11763-206">O parâmetro também aceita um ponto ( `.` ) para especificar o computador local.</span><span class="sxs-lookup"><span data-stu-id="11763-206">The parameter also accepts a dot (`.`) to specify the local computer.</span></span>

<span data-ttu-id="11763-207">O parâmetro **ComputerName** não depende da comunicação remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11763-207">The **ComputerName** parameter doesn't rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="11763-208">Você pode usar `Get-EventLog` com o parâmetro **ComputerName** mesmo se o computador não estiver configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="11763-208">You can use `Get-EventLog` with the **ComputerName** parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="11763-209">-EntryType</span><span class="sxs-lookup"><span data-stu-id="11763-209">-EntryType</span></span>

<span data-ttu-id="11763-210">Especifica, como uma matriz de cadeia de caracteres, o tipo de entrada dos eventos que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="11763-210">Specifies, as a string array, the entry type of the events that this cmdlet gets.</span></span>

<span data-ttu-id="11763-211">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="11763-211">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="11763-212">Erro</span><span class="sxs-lookup"><span data-stu-id="11763-212">Error</span></span>
- <span data-ttu-id="11763-213">Informações</span><span class="sxs-lookup"><span data-stu-id="11763-213">Information</span></span>
- <span data-ttu-id="11763-214">FailureAudit</span><span class="sxs-lookup"><span data-stu-id="11763-214">FailureAudit</span></span>
- <span data-ttu-id="11763-215">SuccessAudit</span><span class="sxs-lookup"><span data-stu-id="11763-215">SuccessAudit</span></span>
- <span data-ttu-id="11763-216">Aviso</span><span class="sxs-lookup"><span data-stu-id="11763-216">Warning</span></span>

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="11763-217">-Índice</span><span class="sxs-lookup"><span data-stu-id="11763-217">-Index</span></span>

<span data-ttu-id="11763-218">Especifica os valores de índice a serem obtidos do log de eventos.</span><span class="sxs-lookup"><span data-stu-id="11763-218">Specifies the index values to get from the event log.</span></span> <span data-ttu-id="11763-219">O parâmetro aceita uma cadeia de caracteres separada por vírgulas de valores.</span><span class="sxs-lookup"><span data-stu-id="11763-219">The parameter accepts a comma-separated string of values.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="11763-220">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="11763-220">-InstanceId</span></span>

<span data-ttu-id="11763-221">Especifica as IDs de instância a serem obtidas do log de eventos.</span><span class="sxs-lookup"><span data-stu-id="11763-221">Specifies the Instance IDs to get from the event log.</span></span> <span data-ttu-id="11763-222">O parâmetro aceita uma cadeia de caracteres separada por vírgulas de valores.</span><span class="sxs-lookup"><span data-stu-id="11763-222">The parameter accepts a comma-separated string of values.</span></span>

```yaml
Type: System.Int64[]
Parameter Sets: LogName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="11763-223">-Lista</span><span class="sxs-lookup"><span data-stu-id="11763-223">-List</span></span>

<span data-ttu-id="11763-224">Exibe a lista de logs de eventos no computador.</span><span class="sxs-lookup"><span data-stu-id="11763-224">Displays the list of event logs on the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="11763-225">-LogName</span><span class="sxs-lookup"><span data-stu-id="11763-225">-LogName</span></span>

<span data-ttu-id="11763-226">Especifica o nome de um log de eventos.</span><span class="sxs-lookup"><span data-stu-id="11763-226">Specifies the name of one event log.</span></span> <span data-ttu-id="11763-227">Para localizar os nomes de log, use `Get-EventLog -List` .</span><span class="sxs-lookup"><span data-stu-id="11763-227">To find the log names use `Get-EventLog -List`.</span></span> <span data-ttu-id="11763-228">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="11763-228">Wildcard characters are permitted.</span></span> <span data-ttu-id="11763-229">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="11763-229">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="11763-230">-Mensagem</span><span class="sxs-lookup"><span data-stu-id="11763-230">-Message</span></span>

<span data-ttu-id="11763-231">Especifica uma cadeia de caracteres na mensagem do evento.</span><span class="sxs-lookup"><span data-stu-id="11763-231">Specifies a string in the event message.</span></span> <span data-ttu-id="11763-232">Você pode usar esse parâmetro para procurar mensagens que contenham determinadas palavras ou frases.</span><span class="sxs-lookup"><span data-stu-id="11763-232">You can use this parameter to search for messages that contain certain words or phrases.</span></span> <span data-ttu-id="11763-233">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="11763-233">Wildcards are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: MSG

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="11763-234">-Mais recente</span><span class="sxs-lookup"><span data-stu-id="11763-234">-Newest</span></span>

<span data-ttu-id="11763-235">Começa com os eventos mais recentes e Obtém o número especificado de eventos.</span><span class="sxs-lookup"><span data-stu-id="11763-235">Begins with the newest events and gets the specified number of events.</span></span> <span data-ttu-id="11763-236">O número de eventos é necessário, por exemplo `-Newest 100` .</span><span class="sxs-lookup"><span data-stu-id="11763-236">The number of events is required, for example `-Newest 100`.</span></span> <span data-ttu-id="11763-237">Especifica o número máximo de eventos que são retornados.</span><span class="sxs-lookup"><span data-stu-id="11763-237">Specifies the maximum number of events that are returned.</span></span>

```yaml
Type: System.Int32
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="11763-238">-Source</span><span class="sxs-lookup"><span data-stu-id="11763-238">-Source</span></span>

<span data-ttu-id="11763-239">Especifica, como uma matriz de cadeia de caracteres, fontes que foram gravadas no log que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="11763-239">Specifies, as a string array, sources that were written to the log that this cmdlet gets.</span></span> <span data-ttu-id="11763-240">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="11763-240">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ABO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="11763-241">-UserName</span><span class="sxs-lookup"><span data-stu-id="11763-241">-UserName</span></span>

<span data-ttu-id="11763-242">Especifica, como uma matriz de cadeia de caracteres, nomes de usuário associados a eventos.</span><span class="sxs-lookup"><span data-stu-id="11763-242">Specifies, as a string array, user names that are associated with events.</span></span> <span data-ttu-id="11763-243">Insira nomes ou padrões de nome, como `User01` , `User*` ou `Domain01\User*` .</span><span class="sxs-lookup"><span data-stu-id="11763-243">Enter names or name patterns, such as `User01`, `User*`, or `Domain01\User*`.</span></span> <span data-ttu-id="11763-244">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="11763-244">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="11763-245">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="11763-245">CommonParameters</span></span>

<span data-ttu-id="11763-246">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="11763-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="11763-247">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="11763-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="11763-248">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="11763-248">INPUTS</span></span>

### <span data-ttu-id="11763-249">Nenhum</span><span class="sxs-lookup"><span data-stu-id="11763-249">None</span></span>

<span data-ttu-id="11763-250">Não é possível canalizar a entrada para `Get-EventLog` .</span><span class="sxs-lookup"><span data-stu-id="11763-250">You cannot pipe input to `Get-EventLog`.</span></span>

## <span data-ttu-id="11763-251">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="11763-251">OUTPUTS</span></span>

### <span data-ttu-id="11763-252">System. Diagnostics. EventLogEntry.</span><span class="sxs-lookup"><span data-stu-id="11763-252">System.Diagnostics.EventLogEntry.</span></span> <span data-ttu-id="11763-253">System. Diagnostics. EventLog.</span><span class="sxs-lookup"><span data-stu-id="11763-253">System.Diagnostics.EventLog.</span></span> <span data-ttu-id="11763-254">System.String</span><span class="sxs-lookup"><span data-stu-id="11763-254">System.String</span></span>

<span data-ttu-id="11763-255">Se o parâmetro **LogName** for especificado, a saída será uma coleção de objetos **System. Diagnostics. EventLogEntry** .</span><span class="sxs-lookup"><span data-stu-id="11763-255">If the **LogName** parameter is specified, the output is a collection of **System.Diagnostics.EventLogEntry** objects.</span></span>

<span data-ttu-id="11763-256">Se apenas o parâmetro **list** for especificado, a saída será uma coleção de objetos **System. Diagnostics. EventLog** .</span><span class="sxs-lookup"><span data-stu-id="11763-256">If only the **List** parameter is specified, the output is a collection of **System.Diagnostics.EventLog** objects.</span></span>

<span data-ttu-id="11763-257">Se os parâmetros **list** e **AsString** forem especificados, a saída será uma coleção de objetos **System. String** .</span><span class="sxs-lookup"><span data-stu-id="11763-257">If both the **List** and **AsString** parameters are specified, the output is a collection of **System.String** objects.</span></span>

## <span data-ttu-id="11763-258">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="11763-258">NOTES</span></span>

<span data-ttu-id="11763-259">Os cmdlets `Get-EventLog` e `Get-WinEvent` não têm suporte no ambiente de pré-instalação do Windows (Windows PE).</span><span class="sxs-lookup"><span data-stu-id="11763-259">The cmdlets `Get-EventLog` and `Get-WinEvent` are not supported in the Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="11763-260">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="11763-260">RELATED LINKS</span></span>

[<span data-ttu-id="11763-261">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="11763-261">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="11763-262">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="11763-262">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="11763-263">Group-Object</span><span class="sxs-lookup"><span data-stu-id="11763-263">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="11763-264">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="11763-264">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="11763-265">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="11763-265">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="11763-266">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="11763-266">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="11763-267">Select-Object</span><span class="sxs-lookup"><span data-stu-id="11763-267">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="11763-268">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="11763-268">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="11763-269">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="11763-269">Write-EventLog</span></span>](Write-EventLog.md)
