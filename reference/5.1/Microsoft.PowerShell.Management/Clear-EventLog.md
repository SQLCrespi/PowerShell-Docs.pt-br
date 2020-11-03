---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-EventLog
ms.openlocfilehash: 695a13d4fbbf60caadeed994c1aa9c36432be917
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194207"
---
# <span data-ttu-id="61cbc-103">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="61cbc-103">Clear-EventLog</span></span>

## <span data-ttu-id="61cbc-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="61cbc-104">SYNOPSIS</span></span>
<span data-ttu-id="61cbc-105">Limpa todas as entradas de logs de eventos especificados nos computadores locais ou remotos.</span><span class="sxs-lookup"><span data-stu-id="61cbc-105">Clears all entries from specified event logs on the local or remote computers.</span></span>

## <span data-ttu-id="61cbc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="61cbc-106">SYNTAX</span></span>

```
Clear-EventLog [-LogName] <String[]> [[-ComputerName] <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="61cbc-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="61cbc-107">DESCRIPTION</span></span>

<span data-ttu-id="61cbc-108">O `Clear-EventLog` cmdlet exclui todas as entradas dos logs de eventos especificados no computador local ou em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="61cbc-108">The `Clear-EventLog` cmdlet deletes all of the entries from the specified event logs on the local computer or on remote computers.</span></span>
<span data-ttu-id="61cbc-109">Para usar `Clear-EventLog` o, você deve ser um membro do grupo Administradores no computador afetado.</span><span class="sxs-lookup"><span data-stu-id="61cbc-109">To use `Clear-EventLog`, you must be a member of the Administrators group on the affected computer.</span></span>

<span data-ttu-id="61cbc-110">Os cmdlets que contêm o substantivo **EventLog** (os cmdlets EventLog) só funcionam em logs de eventos clássicos.</span><span class="sxs-lookup"><span data-stu-id="61cbc-110">The cmdlets that contain the **EventLog** noun (the EventLog cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="61cbc-111">Para obter eventos de logs que usam a tecnologia de log de eventos do Windows no Windows Vista e versões posteriores do Windows, use o cmdlet Get-WinEvent.</span><span class="sxs-lookup"><span data-stu-id="61cbc-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of Windows, use the Get-WinEvent cmdlet.</span></span>

## <span data-ttu-id="61cbc-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="61cbc-112">EXAMPLES</span></span>

### <span data-ttu-id="61cbc-113">Exemplo 1: limpar tipos de log de eventos específicos do computador local</span><span class="sxs-lookup"><span data-stu-id="61cbc-113">Example 1: Clear specific event log types from the local computer</span></span>

```powershell
Clear-EventLog "Windows PowerShell"
```

<span data-ttu-id="61cbc-114">Esse comando limpa as entradas do log de eventos do Windows PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="61cbc-114">This command clears the entries from the Windows PowerShell event log on the local computer.</span></span>

### <span data-ttu-id="61cbc-115">Exemplo 2: limpar vários tipos de log específicos dos computadores locais e remotos</span><span class="sxs-lookup"><span data-stu-id="61cbc-115">Example 2: Clear specific multiple log types from the local and remote computers</span></span>

```powershell
Clear-EventLog -LogName ODiag, OSession -ComputerName localhost, Server02
```

<span data-ttu-id="61cbc-116">Esse comando limpa todas as entradas nos logs de ODiag (diagnóstico de Microsoft Office) e Microsoft Office sessões (OSession) no computador local e no computador remoto Server02.</span><span class="sxs-lookup"><span data-stu-id="61cbc-116">This command clears all of the entries in the Microsoft Office Diagnostics (ODiag) and Microsoft Office Sessions (OSession) logs on the local computer and the Server02 remote computer.</span></span>

### <span data-ttu-id="61cbc-117">Exemplo 3: limpar todos os logs nos computadores especificados e exibir a lista de log de eventos</span><span class="sxs-lookup"><span data-stu-id="61cbc-117">Example 3: Clear all logs on the specified computers then display the event log list</span></span>

```powershell
Clear-EventLog -LogName application, system -confirm
```

<span data-ttu-id="61cbc-118">Este comando solicita sua confirmação antes de excluir as entradas nos logs de eventos especificados.</span><span class="sxs-lookup"><span data-stu-id="61cbc-118">This command prompts you for confirmation before deleting the entries in the specified event logs.</span></span>

### <span data-ttu-id="61cbc-119">Exemplo 4: limpar todos os logs nos computadores especificados e exibir a lista de log de eventos</span><span class="sxs-lookup"><span data-stu-id="61cbc-119">Example 4: Clear all logs on the specified computers then display the event log list</span></span>

```powershell
function clear-all-event-logs ($computerName="localhost")
{
   $logs = Get-EventLog -ComputerName $computername -List | ForEach-Object {$_.Log}
   $logs | ForEach-Object {Clear-EventLog -ComputerName $computername -LogName $_ }
   Get-EventLog -ComputerName $computername -list
}

clear-all-event-logs -ComputerName Server01
```

```Output
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded           0 Application
15,168      0 OverwriteAsNeeded           0 DFS Replication
512         7 OverwriteOlder              0 DxStudio
20,480      0 OverwriteAsNeeded           0 Hardware Events
512         7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
16,384      0 OverwriteAsNeeded           0 Microsoft Office Diagnostics
16,384      0 OverwriteAsNeeded           0 Microsoft Office Sessions
30,016      0 OverwriteAsNeeded           1 Security
15,168      0 OverwriteAsNeeded           2 System
15,360      0 OverwriteAsNeeded           0 Windows PowerShell
```

<span data-ttu-id="61cbc-120">Essa função limpa todos os logs de eventos nos computadores especificados e, em seguida, exibe a lista do log de eventos resultante.</span><span class="sxs-lookup"><span data-stu-id="61cbc-120">This function clears all event logs on the specified computers and then displays the resulting event log list.</span></span>

<span data-ttu-id="61cbc-121">Observe que algumas entradas foram adicionadas aos logs System e Security depois de os logs serem limpos, mas antes de serem exibidos.</span><span class="sxs-lookup"><span data-stu-id="61cbc-121">Notice that a few entries were added to the System and Security logs after the logs were cleared but before they were displayed.</span></span>

## <span data-ttu-id="61cbc-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="61cbc-122">PARAMETERS</span></span>

### <span data-ttu-id="61cbc-123">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="61cbc-123">-ComputerName</span></span>

<span data-ttu-id="61cbc-124">Especifica um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="61cbc-124">Specifies a remote computer.</span></span>
<span data-ttu-id="61cbc-125">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="61cbc-125">The default is the local computer.</span></span>

<span data-ttu-id="61cbc-126">Digite o nome NetBIOS, um endereço IP (protocolo de Internet) ou um nome de domínio totalmente qualificado de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="61cbc-126">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="61cbc-127">Para especificar o computador local, digite o nome do computador, um ponto (.) ou "localhost".</span><span class="sxs-lookup"><span data-stu-id="61cbc-127">To specify the local computer, type the computer name, a dot (.), or "localhost".</span></span>

<span data-ttu-id="61cbc-128">Esse parâmetro não depende da comunicação remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61cbc-128">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="61cbc-129">Você pode usar o parâmetro **ComputerName** de `Get-EventLog` mesmo que o computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="61cbc-129">You can use the **ComputerName** parameter of `Get-EventLog` even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: 1
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="61cbc-130">-LogName</span><span class="sxs-lookup"><span data-stu-id="61cbc-130">-LogName</span></span>

<span data-ttu-id="61cbc-131">Especifica os logs de evento.</span><span class="sxs-lookup"><span data-stu-id="61cbc-131">Specifies the event logs.</span></span>
<span data-ttu-id="61cbc-132">Insira o nome do log (o valor da propriedade Log; não o LogDisplayName) de um ou mais logs de eventos, separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="61cbc-132">Enter the log name (the value of the Log property; not the LogDisplayName) of one or more event logs, separated by commas.</span></span>
<span data-ttu-id="61cbc-133">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="61cbc-133">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="61cbc-134">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="61cbc-134">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="61cbc-135">-Confirm</span><span class="sxs-lookup"><span data-stu-id="61cbc-135">-Confirm</span></span>

<span data-ttu-id="61cbc-136">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="61cbc-136">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="61cbc-137">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="61cbc-137">-WhatIf</span></span>

<span data-ttu-id="61cbc-138">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="61cbc-138">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="61cbc-139">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="61cbc-139">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="61cbc-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="61cbc-140">CommonParameters</span></span>

<span data-ttu-id="61cbc-141">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="61cbc-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="61cbc-142">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="61cbc-142">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="61cbc-143">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="61cbc-143">INPUTS</span></span>

### <span data-ttu-id="61cbc-144">Nenhum</span><span class="sxs-lookup"><span data-stu-id="61cbc-144">None</span></span>

<span data-ttu-id="61cbc-145">Não é possível canalizar objetos para `Clear-EventLog` .</span><span class="sxs-lookup"><span data-stu-id="61cbc-145">You cannot pipe objects to `Clear-EventLog`.</span></span>

## <span data-ttu-id="61cbc-146">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="61cbc-146">OUTPUTS</span></span>

### <span data-ttu-id="61cbc-147">Nenhum</span><span class="sxs-lookup"><span data-stu-id="61cbc-147">None</span></span>

<span data-ttu-id="61cbc-148">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="61cbc-148">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="61cbc-149">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="61cbc-149">NOTES</span></span>

- <span data-ttu-id="61cbc-150">Para usar `Clear-EventLog` o Windows Vista e versões posteriores do Windows, inicie o Windows PowerShell com a opção "executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="61cbc-150">To use `Clear-EventLog` on Windows Vista and later versions of Windows, start Windows PowerShell with the "Run as administrator" option.</span></span>

## <span data-ttu-id="61cbc-151">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="61cbc-151">RELATED LINKS</span></span>

[<span data-ttu-id="61cbc-152">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="61cbc-152">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="61cbc-153">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="61cbc-153">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="61cbc-154">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="61cbc-154">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="61cbc-155">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="61cbc-155">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="61cbc-156">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="61cbc-156">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="61cbc-157">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="61cbc-157">Write-EventLog</span></span>](Write-EventLog.md)
