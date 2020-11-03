---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pshostprocessinfo?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSHostProcessInfo
ms.openlocfilehash: 196b9bc1cb1e318e334e4002e83d73a466b6578d
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193140"
---
# <span data-ttu-id="af702-103">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="af702-103">Get-PSHostProcessInfo</span></span>

## <span data-ttu-id="af702-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="af702-104">SYNOPSIS</span></span>
<span data-ttu-id="af702-105">Obtém informações de processo sobre o host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af702-105">Gets process information about the PowerShell host.</span></span>

## <span data-ttu-id="af702-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="af702-106">SYNTAX</span></span>

### <span data-ttu-id="af702-107">ProcessNameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="af702-107">ProcessNameParameterSet (Default)</span></span>

```
Get-PSHostProcessInfo [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="af702-108">ProcessParameterSet</span><span class="sxs-lookup"><span data-stu-id="af702-108">ProcessParameterSet</span></span>

```
Get-PSHostProcessInfo [-Process] <Process[]> [<CommonParameters>]
```

### <span data-ttu-id="af702-109">ProcessIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="af702-109">ProcessIdParameterSet</span></span>

```
Get-PSHostProcessInfo [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="af702-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="af702-110">DESCRIPTION</span></span>

<span data-ttu-id="af702-111">O `Get-PSHostProcessInfo` cmdlet obtém informações sobre os processos de host do PowerShell em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="af702-111">The `Get-PSHostProcessInfo` cmdlet gets information about PowerShell host processes running on the local computer.</span></span>

<span data-ttu-id="af702-112">A partir do PowerShell 6,2, esse cmdlet tem suporte em plataformas que não são do Windows.</span><span class="sxs-lookup"><span data-stu-id="af702-112">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="af702-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="af702-113">EXAMPLES</span></span>

### <span data-ttu-id="af702-114">1: obter uma lista de hosts do PowerShell em execução no sistema</span><span class="sxs-lookup"><span data-stu-id="af702-114">1: Get a list of PowerShell hosts running on the system</span></span>

```powershell
Get-PSHostProcessInfo
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
powershell      11204 DefaultAppDomain
pwsh            13912 DefaultAppDomain
```

### <span data-ttu-id="af702-115">2: obter informações do host do PowerShell para um nome de processo específico</span><span class="sxs-lookup"><span data-stu-id="af702-115">2: Get PowerShell host information for a specific process name</span></span>

```powershell
Get-PSHostProcessInfo -Name pwsh
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
pwsh            13912 DefaultAppDomain
```

## <span data-ttu-id="af702-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="af702-116">PARAMETERS</span></span>

### <span data-ttu-id="af702-117">-Id</span><span class="sxs-lookup"><span data-stu-id="af702-117">-Id</span></span>

<span data-ttu-id="af702-118">Especifica um processo pela ID do processo.</span><span class="sxs-lookup"><span data-stu-id="af702-118">Specifies a process by the process ID.</span></span> <span data-ttu-id="af702-119">Para obter uma ID de processo, execute o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="af702-119">To get a process ID, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="af702-120">-Name</span><span class="sxs-lookup"><span data-stu-id="af702-120">-Name</span></span>

<span data-ttu-id="af702-121">Especifica um processo pelo nome do processo.</span><span class="sxs-lookup"><span data-stu-id="af702-121">Specifies a process by the process name.</span></span> <span data-ttu-id="af702-122">Para obter um nome de processo, execute o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="af702-122">To get a process name, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="af702-123">-Processo</span><span class="sxs-lookup"><span data-stu-id="af702-123">-Process</span></span>

<span data-ttu-id="af702-124">Especifica um processo pelo objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="af702-124">Specifies a process by the process object.</span></span> <span data-ttu-id="af702-125">A maneira mais simples de usar esse parâmetro é salvar os resultados de um `Get-Process` comando que retorne o processo que você deseja inserir em uma variável e, em seguida, especificar a variável como o valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="af702-125">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

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

### <span data-ttu-id="af702-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="af702-126">CommonParameters</span></span>

<span data-ttu-id="af702-127">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="af702-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="af702-128">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="af702-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="af702-129">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="af702-129">INPUTS</span></span>

### <span data-ttu-id="af702-130">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="af702-130">System.Diagnostics.Process</span></span>

<span data-ttu-id="af702-131">É possível canalizar um objeto de **processo** `Get-Process` a partir desse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="af702-131">You can pipe a **Process** object from `Get-Process` to this cmdlet.</span></span>

## <span data-ttu-id="af702-132">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="af702-132">OUTPUTS</span></span>

### <span data-ttu-id="af702-133">Microsoft. PowerShell. Commands. PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="af702-133">Microsoft.PowerShell.Commands.PSHostProcessInfo</span></span>

## <span data-ttu-id="af702-134">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="af702-134">NOTES</span></span>

## <span data-ttu-id="af702-135">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="af702-135">RELATED LINKS</span></span>

[<span data-ttu-id="af702-136">Get-Process</span><span class="sxs-lookup"><span data-stu-id="af702-136">Get-Process</span></span>](../Microsoft.PowerShell.Management/get-process.md)
