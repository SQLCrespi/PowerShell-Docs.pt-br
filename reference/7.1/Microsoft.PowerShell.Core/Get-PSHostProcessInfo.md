---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pshostprocessinfo?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSHostProcessInfo
ms.openlocfilehash: 655cc02e10bdb11092412271c16a002ab89089c3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194757"
---
# <span data-ttu-id="846b5-103">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="846b5-103">Get-PSHostProcessInfo</span></span>

## <span data-ttu-id="846b5-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="846b5-104">SYNOPSIS</span></span>
<span data-ttu-id="846b5-105">Obtém informações de processo sobre o host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="846b5-105">Gets process information about the PowerShell host.</span></span>

## <span data-ttu-id="846b5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="846b5-106">SYNTAX</span></span>

### <span data-ttu-id="846b5-107">ProcessNameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="846b5-107">ProcessNameParameterSet (Default)</span></span>

```
Get-PSHostProcessInfo [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="846b5-108">ProcessParameterSet</span><span class="sxs-lookup"><span data-stu-id="846b5-108">ProcessParameterSet</span></span>

```
Get-PSHostProcessInfo [-Process] <Process[]> [<CommonParameters>]
```

### <span data-ttu-id="846b5-109">ProcessIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="846b5-109">ProcessIdParameterSet</span></span>

```
Get-PSHostProcessInfo [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="846b5-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="846b5-110">DESCRIPTION</span></span>

<span data-ttu-id="846b5-111">O `Get-PSHostProcessInfo` cmdlet obtém informações sobre os processos de host do PowerShell em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="846b5-111">The `Get-PSHostProcessInfo` cmdlet gets information about PowerShell host processes running on the local computer.</span></span>

<span data-ttu-id="846b5-112">A partir do PowerShell 6,2, esse cmdlet tem suporte em plataformas que não são do Windows.</span><span class="sxs-lookup"><span data-stu-id="846b5-112">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="846b5-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="846b5-113">EXAMPLES</span></span>

### <span data-ttu-id="846b5-114">1: obter uma lista de hosts do PowerShell em execução no sistema</span><span class="sxs-lookup"><span data-stu-id="846b5-114">1: Get a list of PowerShell hosts running on the system</span></span>

```powershell
Get-PSHostProcessInfo
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
powershell      11204 DefaultAppDomain
pwsh            13912 DefaultAppDomain
```

### <span data-ttu-id="846b5-115">2: obter informações do host do PowerShell para um nome de processo específico</span><span class="sxs-lookup"><span data-stu-id="846b5-115">2: Get PowerShell host information for a specific process name</span></span>

```powershell
Get-PSHostProcessInfo -Name pwsh
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
pwsh            13912 DefaultAppDomain
```

## <span data-ttu-id="846b5-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="846b5-116">PARAMETERS</span></span>

### <span data-ttu-id="846b5-117">-Id</span><span class="sxs-lookup"><span data-stu-id="846b5-117">-Id</span></span>

<span data-ttu-id="846b5-118">Especifica um processo pela ID do processo.</span><span class="sxs-lookup"><span data-stu-id="846b5-118">Specifies a process by the process ID.</span></span> <span data-ttu-id="846b5-119">Para obter uma ID de processo, execute o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="846b5-119">To get a process ID, run the `Get-Process` cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: ProcessIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="846b5-120">-Name</span><span class="sxs-lookup"><span data-stu-id="846b5-120">-Name</span></span>

<span data-ttu-id="846b5-121">Especifica um processo pelo nome do processo.</span><span class="sxs-lookup"><span data-stu-id="846b5-121">Specifies a process by the process name.</span></span> <span data-ttu-id="846b5-122">Para obter um nome de processo, execute o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="846b5-122">To get a process name, run the `Get-Process` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="846b5-123">-Processo</span><span class="sxs-lookup"><span data-stu-id="846b5-123">-Process</span></span>

<span data-ttu-id="846b5-124">Especifica um processo pelo objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="846b5-124">Specifies a process by the process object.</span></span> <span data-ttu-id="846b5-125">A maneira mais simples de usar esse parâmetro é salvar os resultados de um `Get-Process` comando que retorne o processo que você deseja inserir em uma variável e, em seguida, especificar a variável como o valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="846b5-125">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: ProcessParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="846b5-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="846b5-126">CommonParameters</span></span>

<span data-ttu-id="846b5-127">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="846b5-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="846b5-128">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="846b5-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="846b5-129">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="846b5-129">INPUTS</span></span>

### <span data-ttu-id="846b5-130">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="846b5-130">System.Diagnostics.Process</span></span>

<span data-ttu-id="846b5-131">É possível canalizar um objeto de **processo** `Get-Process` a partir desse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="846b5-131">You can pipe a **Process** object from `Get-Process` to this cmdlet.</span></span>

## <span data-ttu-id="846b5-132">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="846b5-132">OUTPUTS</span></span>

### <span data-ttu-id="846b5-133">Microsoft. PowerShell. Commands. PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="846b5-133">Microsoft.PowerShell.Commands.PSHostProcessInfo</span></span>

## <span data-ttu-id="846b5-134">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="846b5-134">NOTES</span></span>

## <span data-ttu-id="846b5-135">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="846b5-135">RELATED LINKS</span></span>

[<span data-ttu-id="846b5-136">Get-Process</span><span class="sxs-lookup"><span data-stu-id="846b5-136">Get-Process</span></span>](../Microsoft.PowerShell.Management/get-process.md)

