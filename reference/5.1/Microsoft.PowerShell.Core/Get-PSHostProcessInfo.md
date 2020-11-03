---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pshostprocessinfo?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSHostProcessInfo
ms.openlocfilehash: 5f3579e002030715d7e5926de5f6209cd61b0367
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193322"
---
# <span data-ttu-id="d3862-103">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="d3862-103">Get-PSHostProcessInfo</span></span>

## <span data-ttu-id="d3862-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d3862-104">SYNOPSIS</span></span>
<span data-ttu-id="d3862-105">Obtém informações de processo sobre o host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3862-105">Gets process information about the PowerShell host.</span></span>

## <span data-ttu-id="d3862-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d3862-106">SYNTAX</span></span>

### <span data-ttu-id="d3862-107">ProcessNameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="d3862-107">ProcessNameParameterSet (Default)</span></span>

```
Get-PSHostProcessInfo [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="d3862-108">ProcessParameterSet</span><span class="sxs-lookup"><span data-stu-id="d3862-108">ProcessParameterSet</span></span>

```
Get-PSHostProcessInfo [-Process] <Process[]> [<CommonParameters>]
```

### <span data-ttu-id="d3862-109">ProcessIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="d3862-109">ProcessIdParameterSet</span></span>

```
Get-PSHostProcessInfo [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="d3862-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d3862-110">DESCRIPTION</span></span>

<span data-ttu-id="d3862-111">O `Get-PSHostProcessInfo` cmdlet obtém informações sobre os processos de host do PowerShell em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="d3862-111">The `Get-PSHostProcessInfo` cmdlet gets information about PowerShell host processes running on the local computer.</span></span>

<span data-ttu-id="d3862-112">A partir do PowerShell 6,2, esse cmdlet tem suporte em plataformas que não são do Windows.</span><span class="sxs-lookup"><span data-stu-id="d3862-112">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="d3862-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d3862-113">EXAMPLES</span></span>

### <span data-ttu-id="d3862-114">1: obter uma lista de hosts do PowerShell em execução no sistema</span><span class="sxs-lookup"><span data-stu-id="d3862-114">1: Get a list of PowerShell hosts running on the system</span></span>

```powershell
Get-PSHostProcessInfo
```

```Output
ProcessName ProcessId AppDomainName    MainWindowTitle
----------- --------- -------------    ---------------
powershell      14676 DefaultAppDomain Windows PowerShell
powershell       5184 DefaultAppDomain Windows PowerShell
```

### <span data-ttu-id="d3862-115">2: obter informações do host do PowerShell para um processo específico</span><span class="sxs-lookup"><span data-stu-id="d3862-115">2: Get PowerShell host information for a specific process</span></span>

```powershell
Get-PSHostProcessInfo -Id 14676
```

```Output
ProcessName ProcessId AppDomainName    MainWindowTitle
----------- --------- -------------    ---------------
powershell      14676 DefaultAppDomain Windows PowerShell
```

## <span data-ttu-id="d3862-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d3862-116">PARAMETERS</span></span>

### <span data-ttu-id="d3862-117">-Id</span><span class="sxs-lookup"><span data-stu-id="d3862-117">-Id</span></span>

<span data-ttu-id="d3862-118">Especifica um processo pela ID do processo.</span><span class="sxs-lookup"><span data-stu-id="d3862-118">Specifies a process by the process ID.</span></span> <span data-ttu-id="d3862-119">Para obter uma ID de processo, execute o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d3862-119">To get a process ID, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="d3862-120">-Name</span><span class="sxs-lookup"><span data-stu-id="d3862-120">-Name</span></span>

<span data-ttu-id="d3862-121">Especifica um processo pelo nome do processo.</span><span class="sxs-lookup"><span data-stu-id="d3862-121">Specifies a process by the process name.</span></span> <span data-ttu-id="d3862-122">Para obter um nome de processo, execute o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d3862-122">To get a process name, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="d3862-123">-Processo</span><span class="sxs-lookup"><span data-stu-id="d3862-123">-Process</span></span>

<span data-ttu-id="d3862-124">Especifica um processo pelo objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="d3862-124">Specifies a process by the process object.</span></span> <span data-ttu-id="d3862-125">A maneira mais simples de usar esse parâmetro é salvar os resultados de um `Get-Process` comando que retorne o processo que você deseja inserir em uma variável e, em seguida, especificar a variável como o valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d3862-125">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

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

### <span data-ttu-id="d3862-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d3862-126">CommonParameters</span></span>

<span data-ttu-id="d3862-127">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d3862-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d3862-128">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d3862-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d3862-129">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d3862-129">INPUTS</span></span>

### <span data-ttu-id="d3862-130">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="d3862-130">System.Diagnostics.Process</span></span>

<span data-ttu-id="d3862-131">É possível canalizar um objeto de **processo** `Get-Process` a partir desse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d3862-131">You can pipe a **Process** object from `Get-Process` to this cmdlet.</span></span>

## <span data-ttu-id="d3862-132">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d3862-132">OUTPUTS</span></span>

### <span data-ttu-id="d3862-133">Microsoft. PowerShell. Commands. PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="d3862-133">Microsoft.PowerShell.Commands.PSHostProcessInfo</span></span>

## <span data-ttu-id="d3862-134">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d3862-134">NOTES</span></span>

## <span data-ttu-id="d3862-135">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d3862-135">RELATED LINKS</span></span>

[<span data-ttu-id="d3862-136">Get-Process</span><span class="sxs-lookup"><span data-stu-id="d3862-136">Get-Process</span></span>](../Microsoft.PowerShell.Management/get-process.md)
