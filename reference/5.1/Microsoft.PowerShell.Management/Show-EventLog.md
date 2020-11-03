---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-EventLog
ms.openlocfilehash: e8dbcf1aa4280c0481714a8a9fb24f2e5ef79ffe
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193918"
---
# <span data-ttu-id="01d49-103">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="01d49-103">Show-EventLog</span></span>

## <span data-ttu-id="01d49-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="01d49-104">SYNOPSIS</span></span>
<span data-ttu-id="01d49-105">Exibe os logs de eventos do local ou de um computador remoto no Visualizador de eventos.</span><span class="sxs-lookup"><span data-stu-id="01d49-105">Displays the event logs of the local or a remote computer in Event Viewer.</span></span>

## <span data-ttu-id="01d49-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="01d49-106">SYNTAX</span></span>

```
Show-EventLog [[-ComputerName] <String>] [<CommonParameters>]
```

## <span data-ttu-id="01d49-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="01d49-107">DESCRIPTION</span></span>
<span data-ttu-id="01d49-108">O cmdlet **Show-EventLog** abre Visualizador de eventos no computador local e exibe todos os logs de eventos clássicos no computador local ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="01d49-108">The **Show-EventLog** cmdlet opens Event Viewer on the local computer and displays in it all of the classic event logs on the local computer or a remote computer.</span></span>

<span data-ttu-id="01d49-109">Para abrir Visualizador de Eventos no Windows Vista e versões posteriores do sistema operacional Windows, o usuário atual deve ser um membro do grupo Administradores no computador local.</span><span class="sxs-lookup"><span data-stu-id="01d49-109">To open Event Viewer on Windows Vista and later versions of the Windows operating system, the current user must be a member of the Administrators group on the local computer.</span></span>

<span data-ttu-id="01d49-110">Os cmdlets que contêm o substantivo **EventLog** (os cmdlets **EventLog** ) só funcionam em logs de eventos clássicos.</span><span class="sxs-lookup"><span data-stu-id="01d49-110">The cmdlets that contain the **EventLog** noun (the **EventLog** cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="01d49-111">Para obter eventos de logs que usam a tecnologia de log de eventos do Windows no Windows Vista e versões posteriores do sistema operacional Windows, use o cmdlet Get-WinEvent.</span><span class="sxs-lookup"><span data-stu-id="01d49-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use the Get-WinEvent cmdlet.</span></span>

## <span data-ttu-id="01d49-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="01d49-112">EXAMPLES</span></span>

### <span data-ttu-id="01d49-113">Exemplo 1: Exibir logs de eventos para o computador local</span><span class="sxs-lookup"><span data-stu-id="01d49-113">Example 1: Display event logs for the local computer</span></span>

```
PS C:\> Show-EventLog
```

<span data-ttu-id="01d49-114">Esse comando abre o Visualizador de eventos e exibe nos logs de eventos clássicos no computador local.</span><span class="sxs-lookup"><span data-stu-id="01d49-114">This command opens Event Viewer and displays in it the classic event logs on the local computer.</span></span>

### <span data-ttu-id="01d49-115">Exemplo 2: Exibir logs de eventos para um computador remoto</span><span class="sxs-lookup"><span data-stu-id="01d49-115">Example 2: Display event logs for a remote computer</span></span>

```
PS C:\> Show-EventLog -ComputerName "Server01"
```

<span data-ttu-id="01d49-116">Esse comando abre o Visualizador de eventos e exibe os logs de eventos clássicos no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="01d49-116">This command opens Event Viewer and displays in it the classic event logs on the Server01 computer.</span></span>

## <span data-ttu-id="01d49-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="01d49-117">PARAMETERS</span></span>

### <span data-ttu-id="01d49-118">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="01d49-118">-ComputerName</span></span>
<span data-ttu-id="01d49-119">Especifica um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="01d49-119">Specifies a remote computer.</span></span>
<span data-ttu-id="01d49-120">**Show-EventLog** exibe os logs de eventos do computador especificado em Visualizador de eventos no computador local.</span><span class="sxs-lookup"><span data-stu-id="01d49-120">**Show-EventLog** displays the event logs from the specified computer in Event Viewer on the local computer.</span></span>
<span data-ttu-id="01d49-121">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="01d49-121">The default is the local computer.</span></span>

<span data-ttu-id="01d49-122">Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="01d49-122">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>

<span data-ttu-id="01d49-123">Esse parâmetro não depende da comunicação remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01d49-123">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="01d49-124">Você pode usar o parâmetro *ComputerName* , mesmo que seu computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="01d49-124">You can use the *ComputerName* parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01d49-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="01d49-125">CommonParameters</span></span>
<span data-ttu-id="01d49-126">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="01d49-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="01d49-127">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="01d49-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="01d49-128">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="01d49-128">INPUTS</span></span>

### <span data-ttu-id="01d49-129">Nenhum</span><span class="sxs-lookup"><span data-stu-id="01d49-129">None</span></span>
<span data-ttu-id="01d49-130">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="01d49-130">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="01d49-131">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="01d49-131">OUTPUTS</span></span>

### <span data-ttu-id="01d49-132">Nenhum</span><span class="sxs-lookup"><span data-stu-id="01d49-132">None</span></span>
<span data-ttu-id="01d49-133">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="01d49-133">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="01d49-134">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="01d49-134">NOTES</span></span>

* <span data-ttu-id="01d49-135">O prompt de comando do Windows PowerShell retorna assim que o Visualizador de eventos é aberto.</span><span class="sxs-lookup"><span data-stu-id="01d49-135">The Windows PowerShell command prompt returns as soon as Event Viewer opens.</span></span> <span data-ttu-id="01d49-136">É possível trabalhar na sessão atual enquanto o Visualizador de eventos está aberto.</span><span class="sxs-lookup"><span data-stu-id="01d49-136">You can work in the current session while Event Viewer is open.</span></span>

  <span data-ttu-id="01d49-137">Como esse cmdlet exige uma interface do usuário, ele não funciona em instalações Server Core do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="01d49-137">Because this cmdlet requires a user interface, it does not work on Server Core installations of Windows Server.</span></span>

*

## <span data-ttu-id="01d49-138">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="01d49-138">RELATED LINKS</span></span>

[<span data-ttu-id="01d49-139">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="01d49-139">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="01d49-140">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="01d49-140">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="01d49-141">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="01d49-141">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="01d49-142">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="01d49-142">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="01d49-143">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="01d49-143">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="01d49-144">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="01d49-144">Write-EventLog</span></span>](Write-EventLog.md)
