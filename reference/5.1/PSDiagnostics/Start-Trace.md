---
external help file: PSDiagnostics-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/start-trace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Trace
ms.openlocfilehash: cbdb40edf85dd4645552f6e096a99384532b4443
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193695"
---
# <span data-ttu-id="805da-103">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="805da-103">Start-Trace</span></span>

## <span data-ttu-id="805da-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="805da-104">SYNOPSIS</span></span>
<span data-ttu-id="805da-105">Iniciar uma sessão de log de rastreamento de eventos.</span><span class="sxs-lookup"><span data-stu-id="805da-105">Start an Event Trace logging session.</span></span>

## <span data-ttu-id="805da-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="805da-106">SYNTAX</span></span>

```
Start-Trace [-SessionName] <String> [[-OutputFilePath] <String>] [[-ProviderFilePath] <String>]
 [-ETS] [-Format <String>] [-MinBuffers <Int32>] [-MaxBuffers <Int32>]
 [-BufferSizeInKB <Int32>] [-MaxLogFileSizeInMB <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="805da-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="805da-107">DESCRIPTION</span></span>
<span data-ttu-id="805da-108">Esse cmdlet inicia uma sessão de log de rastreamento de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="805da-108">This cmdlet starts a Windows Event Trace logging session.</span></span>

<span data-ttu-id="805da-109">Esse cmdlet é usado pelos seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="805da-109">This cmdlet is used by the following cmdlets:</span></span>

- `Enable-PSWSManCombinedTrace`
- `Enable-WSManTrace`

<span data-ttu-id="805da-110">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="805da-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="805da-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="805da-111">EXAMPLES</span></span>

### <span data-ttu-id="805da-112">Exemplo 1: iniciar uma sessão de log de rastreamento do WSMan</span><span class="sxs-lookup"><span data-stu-id="805da-112">Example 1: Start a WSMan Trace logging session</span></span>

```powershell
Start-Trace -SessionName 'wsmlog' -ETS -OutputFilePath "$env:windir\system32\wsmtraces.log" -Format 'bincirc' -MinBuffers 16 -MaxBuffers 256 -BufferSizeInKb 64 -MaxLogFileSizeInMB 256 -ProviderFilePath "$env:windir\system32\wsmtraceproviders.txt"
```

## <span data-ttu-id="805da-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="805da-113">PARAMETERS</span></span>

### <span data-ttu-id="805da-114">-BufferSizeInKB</span><span class="sxs-lookup"><span data-stu-id="805da-114">-BufferSizeInKB</span></span>
<span data-ttu-id="805da-115">Tamanho do buffer da sessão de rastreamento de eventos em kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="805da-115">Event Trace Session buffer size in kilobytes (KB).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="805da-116">-ETS</span><span class="sxs-lookup"><span data-stu-id="805da-116">-ETS</span></span>
<span data-ttu-id="805da-117">Envie comandos para sessões de rastreamento de eventos diretamente sem salvar ou agendar.</span><span class="sxs-lookup"><span data-stu-id="805da-117">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="805da-118">-Formato</span><span class="sxs-lookup"><span data-stu-id="805da-118">-Format</span></span>
<span data-ttu-id="805da-119">Especifica o formato de log para o coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="805da-119">Specifies the log format for the data collector.</span></span> <span data-ttu-id="805da-120">Para o formato de banco de dados SQL, você deve usar a opção **OutputFilePath** na linha de comando com o `dsn!log` valor.</span><span class="sxs-lookup"><span data-stu-id="805da-120">For SQL database format, you must use the **OutputFilePath** option in the command line with the `dsn!log` value.</span></span> <span data-ttu-id="805da-121">O padrão é binary (bin).</span><span class="sxs-lookup"><span data-stu-id="805da-121">The default is binary (bin).</span></span> <span data-ttu-id="805da-122">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="805da-122">The possible values are:</span></span>

- <span data-ttu-id="805da-123">bin-binário</span><span class="sxs-lookup"><span data-stu-id="805da-123">bin - binary</span></span>
- <span data-ttu-id="805da-124">bincirc-Binary com log circular</span><span class="sxs-lookup"><span data-stu-id="805da-124">bincirc - binary with circular logging</span></span>
- <span data-ttu-id="805da-125">CSV – valores separados por vírgula</span><span class="sxs-lookup"><span data-stu-id="805da-125">csv - Comma-separated values</span></span>
- <span data-ttu-id="805da-126">TSV-valores separados por tabulação</span><span class="sxs-lookup"><span data-stu-id="805da-126">tsv - Tab-separated values</span></span>
- <span data-ttu-id="805da-127">SQL-banco de dados SQL</span><span class="sxs-lookup"><span data-stu-id="805da-127">sql - SQL database</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:
Accepted values: bin, bincirc, csv, tsv, sql

Required: False
Position: Named
Default value: bin
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="805da-128">-MaxBuffers</span><span class="sxs-lookup"><span data-stu-id="805da-128">-MaxBuffers</span></span>
<span data-ttu-id="805da-129">Define o número máximo de buffers de sessão de rastreamento de eventos.</span><span class="sxs-lookup"><span data-stu-id="805da-129">Sets the maximum number of Event Trace Session buffers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 256
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="805da-130">-MaxLogFileSizeInMB</span><span class="sxs-lookup"><span data-stu-id="805da-130">-MaxLogFileSizeInMB</span></span>
<span data-ttu-id="805da-131">Define o tamanho máximo do arquivo de log em megabytes (MB) ou número de registros para logs SQL.</span><span class="sxs-lookup"><span data-stu-id="805da-131">Sets the maximum log file size in megabytes (MB) or number of records for SQL logs.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0 (no limit)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="805da-132">-MinBuffers</span><span class="sxs-lookup"><span data-stu-id="805da-132">-MinBuffers</span></span>
<span data-ttu-id="805da-133">Define o número mínimo de buffers de sessão de rastreamento de eventos.</span><span class="sxs-lookup"><span data-stu-id="805da-133">Sets the minimum number of Event Trace Session buffers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="805da-134">-OutputFilePath</span><span class="sxs-lookup"><span data-stu-id="805da-134">-OutputFilePath</span></span>
<span data-ttu-id="805da-135">Caminho do arquivo de log de saída ou do DSN e do nome do conjunto de logs em um banco de dados SQL.</span><span class="sxs-lookup"><span data-stu-id="805da-135">Path of the output log file or the DSN and log set name in a SQL database.</span></span> <span data-ttu-id="805da-136">O caminho padrão é `$env:systemdrive\PerfLogs\Admin`.</span><span class="sxs-lookup"><span data-stu-id="805da-136">The default path is `$env:systemdrive\PerfLogs\Admin`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: $env:systemdrive\PerfLogs\Admin
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="805da-137">-ProviderFilePath</span><span class="sxs-lookup"><span data-stu-id="805da-137">-ProviderFilePath</span></span>
<span data-ttu-id="805da-138">Arquivo que lista vários provedores de rastreamento de eventos a serem habilitados.</span><span class="sxs-lookup"><span data-stu-id="805da-138">File listing multiple Event Trace providers to enable.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="805da-139">-SESSIONNAME</span><span class="sxs-lookup"><span data-stu-id="805da-139">-SessionName</span></span>
<span data-ttu-id="805da-140">O nome da sessão de rastreamento de eventos.</span><span class="sxs-lookup"><span data-stu-id="805da-140">The name of the Event Trace session.</span></span> <span data-ttu-id="805da-141">Para interromper uma sessão de rastreamento, você deve saber o nome da sessão.</span><span class="sxs-lookup"><span data-stu-id="805da-141">To stop a trace session you must know the session name.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="805da-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="805da-142">CommonParameters</span></span>

<span data-ttu-id="805da-143">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="805da-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="805da-144">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="805da-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="805da-145">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="805da-145">INPUTS</span></span>

### <span data-ttu-id="805da-146">Nenhum</span><span class="sxs-lookup"><span data-stu-id="805da-146">None</span></span>

## <span data-ttu-id="805da-147">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="805da-147">OUTPUTS</span></span>

### <span data-ttu-id="805da-148">System.Object</span><span class="sxs-lookup"><span data-stu-id="805da-148">System.Object</span></span>

## <span data-ttu-id="805da-149">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="805da-149">NOTES</span></span>

## <span data-ttu-id="805da-150">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="805da-150">RELATED LINKS</span></span>

[<span data-ttu-id="805da-151">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="805da-151">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="805da-152">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="805da-152">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="805da-153">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="805da-153">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="805da-154">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="805da-154">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="805da-155">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="805da-155">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="805da-156">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="805da-156">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
