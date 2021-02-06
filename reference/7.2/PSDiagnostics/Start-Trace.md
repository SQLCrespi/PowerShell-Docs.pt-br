---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/start-trace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Trace
ms.openlocfilehash: b1c6a596f3dc35028b928c3a6b5459a805bc2512
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598207"
---
# <span data-ttu-id="d7045-102">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="d7045-102">Start-Trace</span></span>

## <span data-ttu-id="d7045-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d7045-103">SYNOPSIS</span></span>
<span data-ttu-id="d7045-104">Iniciar uma sessão de log de rastreamento de eventos.</span><span class="sxs-lookup"><span data-stu-id="d7045-104">Start an Event Trace logging session.</span></span>

## <span data-ttu-id="d7045-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d7045-105">SYNTAX</span></span>

```
Start-Trace [-SessionName] <String> [[-OutputFilePath] <String>] [[-ProviderFilePath] <String>]
 [-ETS] [-Format <String>] [-MinBuffers <Int32>] [-MaxBuffers <Int32>]
 [-BufferSizeInKB <Int32>] [-MaxLogFileSizeInMB <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="d7045-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d7045-106">DESCRIPTION</span></span>
<span data-ttu-id="d7045-107">Esse cmdlet inicia uma sessão de log de rastreamento de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="d7045-107">This cmdlet starts a Windows Event Trace logging session.</span></span>

<span data-ttu-id="d7045-108">Esse cmdlet é usado pelos seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="d7045-108">This cmdlet is used by the following cmdlets:</span></span>

- `Enable-PSWSManCombinedTrace`
- `Enable-WSManTrace`

<span data-ttu-id="d7045-109">Você deve executar este cmdlet em uma sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="d7045-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="d7045-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d7045-110">EXAMPLES</span></span>

### <span data-ttu-id="d7045-111">Exemplo 1: iniciar uma sessão de log de rastreamento do WSMan</span><span class="sxs-lookup"><span data-stu-id="d7045-111">Example 1: Start a WSMan Trace logging session</span></span>

```powershell
Start-Trace -SessionName 'wsmlog' -ETS -OutputFilePath "$env:windir\system32\wsmtraces.log" -Format 'bincirc' -MinBuffers 16 -MaxBuffers 256 -BufferSizeInKb 64 -MaxLogFileSizeInMB 256 -ProviderFilePath "$env:windir\system32\wsmtraceproviders.txt"
```

## <span data-ttu-id="d7045-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d7045-112">PARAMETERS</span></span>

### <span data-ttu-id="d7045-113">-BufferSizeInKB</span><span class="sxs-lookup"><span data-stu-id="d7045-113">-BufferSizeInKB</span></span>
<span data-ttu-id="d7045-114">Tamanho do buffer da sessão de rastreamento de eventos em kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="d7045-114">Event Trace Session buffer size in kilobytes (KB).</span></span>

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

### <span data-ttu-id="d7045-115">-ETS</span><span class="sxs-lookup"><span data-stu-id="d7045-115">-ETS</span></span>
<span data-ttu-id="d7045-116">Envie comandos para sessões de rastreamento de eventos diretamente sem salvar ou agendar.</span><span class="sxs-lookup"><span data-stu-id="d7045-116">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="d7045-117">-Formato</span><span class="sxs-lookup"><span data-stu-id="d7045-117">-Format</span></span>
<span data-ttu-id="d7045-118">Especifica o formato de log para o coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="d7045-118">Specifies the log format for the data collector.</span></span> <span data-ttu-id="d7045-119">Para o formato de banco de dados SQL, você deve usar a opção **OutputFilePath** na linha de comando com o `dsn!log` valor.</span><span class="sxs-lookup"><span data-stu-id="d7045-119">For SQL database format, you must use the **OutputFilePath** option in the command line with the `dsn!log` value.</span></span> <span data-ttu-id="d7045-120">O padrão é binary (bin).</span><span class="sxs-lookup"><span data-stu-id="d7045-120">The default is binary (bin).</span></span> <span data-ttu-id="d7045-121">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="d7045-121">The possible values are:</span></span>

- <span data-ttu-id="d7045-122">bin-binário</span><span class="sxs-lookup"><span data-stu-id="d7045-122">bin - binary</span></span>
- <span data-ttu-id="d7045-123">bincirc-Binary com log circular</span><span class="sxs-lookup"><span data-stu-id="d7045-123">bincirc - binary with circular logging</span></span>
- <span data-ttu-id="d7045-124">CSV – valores separados por vírgula</span><span class="sxs-lookup"><span data-stu-id="d7045-124">csv - Comma-separated values</span></span>
- <span data-ttu-id="d7045-125">TSV-valores separados por tabulação</span><span class="sxs-lookup"><span data-stu-id="d7045-125">tsv - Tab-separated values</span></span>
- <span data-ttu-id="d7045-126">SQL-banco de dados SQL</span><span class="sxs-lookup"><span data-stu-id="d7045-126">sql - SQL database</span></span>

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

### <span data-ttu-id="d7045-127">-MaxBuffers</span><span class="sxs-lookup"><span data-stu-id="d7045-127">-MaxBuffers</span></span>
<span data-ttu-id="d7045-128">Define o número máximo de buffers de sessão de rastreamento de eventos.</span><span class="sxs-lookup"><span data-stu-id="d7045-128">Sets the maximum number of Event Trace Session buffers.</span></span>

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

### <span data-ttu-id="d7045-129">-MaxLogFileSizeInMB</span><span class="sxs-lookup"><span data-stu-id="d7045-129">-MaxLogFileSizeInMB</span></span>
<span data-ttu-id="d7045-130">Define o tamanho máximo do arquivo de log em megabytes (MB) ou número de registros para logs SQL.</span><span class="sxs-lookup"><span data-stu-id="d7045-130">Sets the maximum log file size in megabytes (MB) or number of records for SQL logs.</span></span>

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

### <span data-ttu-id="d7045-131">-MinBuffers</span><span class="sxs-lookup"><span data-stu-id="d7045-131">-MinBuffers</span></span>
<span data-ttu-id="d7045-132">Define o número mínimo de buffers de sessão de rastreamento de eventos.</span><span class="sxs-lookup"><span data-stu-id="d7045-132">Sets the minimum number of Event Trace Session buffers.</span></span>

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

### <span data-ttu-id="d7045-133">-OutputFilePath</span><span class="sxs-lookup"><span data-stu-id="d7045-133">-OutputFilePath</span></span>
<span data-ttu-id="d7045-134">Caminho do arquivo de log de saída ou do DSN e do nome do conjunto de logs em um banco de dados SQL.</span><span class="sxs-lookup"><span data-stu-id="d7045-134">Path of the output log file or the DSN and log set name in a SQL database.</span></span> <span data-ttu-id="d7045-135">O caminho padrão é `$env:systemdrive\PerfLogs\Admin`.</span><span class="sxs-lookup"><span data-stu-id="d7045-135">The default path is `$env:systemdrive\PerfLogs\Admin`.</span></span>

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

### <span data-ttu-id="d7045-136">-ProviderFilePath</span><span class="sxs-lookup"><span data-stu-id="d7045-136">-ProviderFilePath</span></span>
<span data-ttu-id="d7045-137">Arquivo que lista vários provedores de rastreamento de eventos a serem habilitados.</span><span class="sxs-lookup"><span data-stu-id="d7045-137">File listing multiple Event Trace providers to enable.</span></span>

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

### <span data-ttu-id="d7045-138">-SESSIONNAME</span><span class="sxs-lookup"><span data-stu-id="d7045-138">-SessionName</span></span>
<span data-ttu-id="d7045-139">O nome da sessão de rastreamento de eventos.</span><span class="sxs-lookup"><span data-stu-id="d7045-139">The name of the Event Trace session.</span></span> <span data-ttu-id="d7045-140">Para interromper uma sessão de rastreamento, você deve saber o nome da sessão.</span><span class="sxs-lookup"><span data-stu-id="d7045-140">To stop a trace session you must know the session name.</span></span>

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

### <span data-ttu-id="d7045-141">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d7045-141">CommonParameters</span></span>

<span data-ttu-id="d7045-142">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d7045-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d7045-143">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d7045-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d7045-144">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d7045-144">INPUTS</span></span>

### <span data-ttu-id="d7045-145">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d7045-145">None</span></span>

## <span data-ttu-id="d7045-146">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d7045-146">OUTPUTS</span></span>

### <span data-ttu-id="d7045-147">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d7045-147">None</span></span>

## <span data-ttu-id="d7045-148">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d7045-148">NOTES</span></span>

## <span data-ttu-id="d7045-149">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d7045-149">RELATED LINKS</span></span>

[<span data-ttu-id="d7045-150">Rastreamento de eventos</span><span class="sxs-lookup"><span data-stu-id="d7045-150">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="d7045-151">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="d7045-151">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="d7045-152">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="d7045-152">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="d7045-153">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="d7045-153">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="d7045-154">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="d7045-154">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="d7045-155">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="d7045-155">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

