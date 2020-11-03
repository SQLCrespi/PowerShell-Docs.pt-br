---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-EventLog
ms.openlocfilehash: 61fafc0670a24fd6ca057e4cf0c7179d90446b07
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193971"
---
# <span data-ttu-id="acd1a-103">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="acd1a-103">New-EventLog</span></span>

## <span data-ttu-id="acd1a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="acd1a-104">SYNOPSIS</span></span>
<span data-ttu-id="acd1a-105">Cria um novo log de eventos e uma nova origem do evento em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="acd1a-105">Creates a new event log and a new event source on a local or remote computer.</span></span>

## <span data-ttu-id="acd1a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="acd1a-106">SYNTAX</span></span>

```
New-EventLog [-LogName] <string> [-Source] <string[]> [[-ComputerName] <string[]>]
  [-CategoryResourceFile <string>] [-MessageResourceFile <string>] [-ParameterResourceFile <string>]
  [<CommonParameters>]
```

## <span data-ttu-id="acd1a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="acd1a-107">DESCRIPTION</span></span>

<span data-ttu-id="acd1a-108">Este cmdlet cria um novo log clássico de eventos em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="acd1a-108">This cmdlet creates a new classic event log on a local or remote computer.</span></span> <span data-ttu-id="acd1a-109">Ele também pode registrar uma origem de evento que grava no novo log ou em um log existente.</span><span class="sxs-lookup"><span data-stu-id="acd1a-109">It can also register an event source that writes to the new log or to an existing log.</span></span>

<span data-ttu-id="acd1a-110">Os cmdlets que contêm o substantivo EventLog (os cmdlets do log de eventos) só funcionam em logs clássicos de eventos.</span><span class="sxs-lookup"><span data-stu-id="acd1a-110">The cmdlets that contain the EventLog noun (the Event log cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="acd1a-111">Para obter eventos de logs que usam a tecnologia de log de eventos do Windows no Windows Vista e versões posteriores do Windows, use o `Get-WinEvent` .</span><span class="sxs-lookup"><span data-stu-id="acd1a-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of Windows, use `Get-WinEvent`.</span></span>

## <span data-ttu-id="acd1a-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="acd1a-112">EXAMPLES</span></span>

### <span data-ttu-id="acd1a-113">Exemplo 1-criar um novo log de eventos</span><span class="sxs-lookup"><span data-stu-id="acd1a-113">Example 1 - create a new event log</span></span>

<span data-ttu-id="acd1a-114">Este comando cria o log de eventos TestLog no computador local e registra uma nova origem para ele.</span><span class="sxs-lookup"><span data-stu-id="acd1a-114">This command creates the TestLog event log on the local computer and registers a new source for it.</span></span>

```powershell
New-EventLog -source TestApp -LogName TestLog -MessageResourceFile C:\Test\TestApp.dll
```

### <span data-ttu-id="acd1a-115">Exemplo 2-adicionar uma nova origem do evento a um log existente</span><span class="sxs-lookup"><span data-stu-id="acd1a-115">Example 2 - add a new event source to an existing log</span></span>

<span data-ttu-id="acd1a-116">Este comando adiciona uma nova origem de eventos, NewTestApp, no log de aplicativo do computador remoto Servidor01.</span><span class="sxs-lookup"><span data-stu-id="acd1a-116">This command adds a new event source, NewTestApp, to the Application log on the Server01 remote computer.</span></span>

```powershell
$file = "C:\Program Files\TestApps\NewTestApp.dll"
New-EventLog -ComputerName Server01 -Source NewTestApp -LogName Application -MessageResourceFile $file -CategoryResourceFile $file
```

<span data-ttu-id="acd1a-117">O comando requer que o arquivo NewTestApp.dll esteja localizado no computador Servidor01.</span><span class="sxs-lookup"><span data-stu-id="acd1a-117">The command requires that the NewTestApp.dll file is located on the Server01 computer.</span></span>

## <span data-ttu-id="acd1a-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="acd1a-118">PARAMETERS</span></span>

### <span data-ttu-id="acd1a-119">-CategoryResourceFile</span><span class="sxs-lookup"><span data-stu-id="acd1a-119">-CategoryResourceFile</span></span>

<span data-ttu-id="acd1a-120">Especifica o caminho para o arquivo que contém as cadeias de categorias para os eventos da origem.</span><span class="sxs-lookup"><span data-stu-id="acd1a-120">Specifies the path to the file that contains category strings for the source events.</span></span> <span data-ttu-id="acd1a-121">Esse arquivo também é conhecido como o arquivo de mensagem de categoria.</span><span class="sxs-lookup"><span data-stu-id="acd1a-121">This file is also known as the Category Message File.</span></span>

<span data-ttu-id="acd1a-122">O arquivo deve estar presente no computador no qual o log de eventos está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="acd1a-122">The file must be present on the computer on which the event log is being created.</span></span> <span data-ttu-id="acd1a-123">Este parâmetro não cria nem move arquivos.</span><span class="sxs-lookup"><span data-stu-id="acd1a-123">This parameter does not create or move files.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="acd1a-124">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="acd1a-124">-ComputerName</span></span>

<span data-ttu-id="acd1a-125">Cria os novos logs de eventos nos computadores especificados.</span><span class="sxs-lookup"><span data-stu-id="acd1a-125">Creates the new event logs on the specified computers.</span></span> <span data-ttu-id="acd1a-126">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="acd1a-126">The default is the local computer.</span></span>

<span data-ttu-id="acd1a-127">O nome NetBIOS, o endereço IP ou o nome de domínio totalmente qualificado de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="acd1a-127">The NetBIOS name, IP address, or fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="acd1a-128">Para especificar o computador local, digite o nome do computador, um ponto (.) ou "localhost".</span><span class="sxs-lookup"><span data-stu-id="acd1a-128">To specify the local computer, type the computer name, a dot (.), or "localhost".</span></span>

<span data-ttu-id="acd1a-129">Esse parâmetro não depende da comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="acd1a-129">This parameter does not rely on PowerShell remoting.</span></span> <span data-ttu-id="acd1a-130">Você pode usar o parâmetro **ComputerName** de `Get-EventLog` mesmo que o computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="acd1a-130">You can use the **ComputerName** parameter of `Get-EventLog` even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 3
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="acd1a-131">-LogName</span><span class="sxs-lookup"><span data-stu-id="acd1a-131">-LogName</span></span>

<span data-ttu-id="acd1a-132">Especifica o nome do log de eventos.</span><span class="sxs-lookup"><span data-stu-id="acd1a-132">Specifies the name of the event log.</span></span>

<span data-ttu-id="acd1a-133">Se o log não existir, o `New-EventLog` criará o log e usará esse valor para as propriedades **log** e **LogDisplayName** do novo log de eventos.</span><span class="sxs-lookup"><span data-stu-id="acd1a-133">If the log does not exist, `New-EventLog` creates the log and uses this value for the **Log** and **LogDisplayName** properties of the new event log.</span></span> <span data-ttu-id="acd1a-134">Se o log existir, o registrará `New-EventLog` uma nova origem para o log de eventos.</span><span class="sxs-lookup"><span data-stu-id="acd1a-134">If the log exists, `New-EventLog` registers a new source for the event log.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="acd1a-135">-MessageResourceFile</span><span class="sxs-lookup"><span data-stu-id="acd1a-135">-MessageResourceFile</span></span>

<span data-ttu-id="acd1a-136">Especifica o caminho para o arquivo que contém as cadeias de formatação de mensagens para os eventos da origem.</span><span class="sxs-lookup"><span data-stu-id="acd1a-136">Specifies the path to the file that contains message formatting strings for the source events.</span></span>
<span data-ttu-id="acd1a-137">Esse arquivo também é conhecido como o arquivo de mensagem de evento.</span><span class="sxs-lookup"><span data-stu-id="acd1a-137">This file is also known as the Event Message File.</span></span>

<span data-ttu-id="acd1a-138">O arquivo deve estar presente no computador no qual o log de eventos está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="acd1a-138">The file must be present on the computer on which the event log is being created.</span></span>
<span data-ttu-id="acd1a-139">Este parâmetro não cria nem move arquivos.</span><span class="sxs-lookup"><span data-stu-id="acd1a-139">This parameter does not create or move files.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="acd1a-140">-ParameterResourceFile</span><span class="sxs-lookup"><span data-stu-id="acd1a-140">-ParameterResourceFile</span></span>

<span data-ttu-id="acd1a-141">Especifica o caminho para o arquivo que contém cadeias de caracteres usadas para substituições de parâmetro nas descrições de eventos.</span><span class="sxs-lookup"><span data-stu-id="acd1a-141">Specifies the path to the file that contains strings used for parameter substitutions in event descriptions.</span></span> <span data-ttu-id="acd1a-142">Este arquivo também é conhecido como o arquivo de mensagem de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="acd1a-142">This file is also known as the Parameter Message File.</span></span>

<span data-ttu-id="acd1a-143">O arquivo deve estar presente no computador no qual o log de eventos está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="acd1a-143">The file must be present on the computer on which the event log is being created.</span></span>
<span data-ttu-id="acd1a-144">Este parâmetro não cria nem move arquivos.</span><span class="sxs-lookup"><span data-stu-id="acd1a-144">This parameter does not create or move files.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="acd1a-145">-Source</span><span class="sxs-lookup"><span data-stu-id="acd1a-145">-Source</span></span>

<span data-ttu-id="acd1a-146">Especifica os nomes das origens do log de eventos, como os programas aplicativos que gravam no log de eventos.</span><span class="sxs-lookup"><span data-stu-id="acd1a-146">Specifies the names of the event log sources, such as application programs that write to the event log.</span></span> <span data-ttu-id="acd1a-147">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="acd1a-147">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="acd1a-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="acd1a-148">CommonParameters</span></span>

<span data-ttu-id="acd1a-149">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="acd1a-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="acd1a-150">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="acd1a-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="acd1a-151">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="acd1a-151">INPUTS</span></span>

### <span data-ttu-id="acd1a-152">Nenhum</span><span class="sxs-lookup"><span data-stu-id="acd1a-152">None</span></span>

<span data-ttu-id="acd1a-153">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="acd1a-153">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="acd1a-154">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="acd1a-154">OUTPUTS</span></span>

### <span data-ttu-id="acd1a-155">System. Diagnostics. EventLogEntry</span><span class="sxs-lookup"><span data-stu-id="acd1a-155">System.Diagnostics.EventLogEntry</span></span>

## <span data-ttu-id="acd1a-156">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="acd1a-156">NOTES</span></span>

<span data-ttu-id="acd1a-157">Para usar `New-EventLog` o no Windows Vista e versões posteriores do Windows, abra o PowerShell com a opção "executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="acd1a-157">To use `New-EventLog` on Windows Vista and later versions of Windows, open PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="acd1a-158">Para criar uma origem de evento no Windows Vista, Windows XP Professional ou Windows Server 2003, você deve ser um membro do grupo Administradores do computador.</span><span class="sxs-lookup"><span data-stu-id="acd1a-158">To create an event source in Windows Vista, Windows XP Professional, or Windows Server 2003, you must be a member of the Administrators group on the computer.</span></span>

<span data-ttu-id="acd1a-159">Quando você cria um novo log de eventos e uma nova origem de evento, o sistema registra a nova origem para o novo log, mas o log não é criado até que a primeira entrada seja gravada nele.</span><span class="sxs-lookup"><span data-stu-id="acd1a-159">When you create a new event log and a new event source, the system registers the new source for the new log, but the log is not created until the first entry is written to it.</span></span>

<span data-ttu-id="acd1a-160">O sistema operacional armazena os logs de eventos como arquivos.</span><span class="sxs-lookup"><span data-stu-id="acd1a-160">The operating system stores event logs as files.</span></span>

<span data-ttu-id="acd1a-161">Quando você cria um novo log de eventos, o arquivo associado é armazenado no `$env:SystemRoot\System32\Config` diretório no computador especificado.</span><span class="sxs-lookup"><span data-stu-id="acd1a-161">When you create a new event log, the associated file is stored in the `$env:SystemRoot\System32\Config` directory on the specified computer.</span></span>

<span data-ttu-id="acd1a-162">O nome do arquivo é os oito primeiros caracteres da propriedade **log** com uma extensão de nome de arquivo. evt.</span><span class="sxs-lookup"><span data-stu-id="acd1a-162">The file name is the first eight characters of the **Log** property with an .evt file name extension.</span></span>

## <span data-ttu-id="acd1a-163">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="acd1a-163">RELATED LINKS</span></span>

[<span data-ttu-id="acd1a-164">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="acd1a-164">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="acd1a-165">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="acd1a-165">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="acd1a-166">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="acd1a-166">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="acd1a-167">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="acd1a-167">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="acd1a-168">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="acd1a-168">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="acd1a-169">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="acd1a-169">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="acd1a-170">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="acd1a-170">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="acd1a-171">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="acd1a-171">Write-EventLog</span></span>](Write-EventLog.md)
