---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pshostprocessinfo?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSHostProcessInfo
ms.openlocfilehash: 6528d25ea706ac63927ef3d23cf661489caae8aa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598414"
---
# <span data-ttu-id="15e6d-102">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="15e6d-102">Get-PSHostProcessInfo</span></span>

## <span data-ttu-id="15e6d-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="15e6d-103">SYNOPSIS</span></span>
<span data-ttu-id="15e6d-104">Obtém informações de processo sobre o host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15e6d-104">Gets process information about the PowerShell host.</span></span>

## <span data-ttu-id="15e6d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="15e6d-105">SYNTAX</span></span>

### <span data-ttu-id="15e6d-106">ProcessNameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="15e6d-106">ProcessNameParameterSet (Default)</span></span>

```
Get-PSHostProcessInfo [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="15e6d-107">ProcessParameterSet</span><span class="sxs-lookup"><span data-stu-id="15e6d-107">ProcessParameterSet</span></span>

```
Get-PSHostProcessInfo [-Process] <Process[]> [<CommonParameters>]
```

### <span data-ttu-id="15e6d-108">ProcessIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="15e6d-108">ProcessIdParameterSet</span></span>

```
Get-PSHostProcessInfo [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="15e6d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="15e6d-109">DESCRIPTION</span></span>

<span data-ttu-id="15e6d-110">O `Get-PSHostProcessInfo` cmdlet obtém informações sobre os processos de host do PowerShell em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="15e6d-110">The `Get-PSHostProcessInfo` cmdlet gets information about PowerShell host processes running on the local computer.</span></span>

<span data-ttu-id="15e6d-111">A partir do PowerShell 6,2, esse cmdlet tem suporte em plataformas que não são do Windows.</span><span class="sxs-lookup"><span data-stu-id="15e6d-111">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="15e6d-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="15e6d-112">EXAMPLES</span></span>

### <span data-ttu-id="15e6d-113">1: obter uma lista de hosts do PowerShell em execução no sistema</span><span class="sxs-lookup"><span data-stu-id="15e6d-113">1: Get a list of PowerShell hosts running on the system</span></span>

```powershell
Get-PSHostProcessInfo
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
powershell      11204 DefaultAppDomain
pwsh            13912 DefaultAppDomain
```

### <span data-ttu-id="15e6d-114">2: obter informações do host do PowerShell para um nome de processo específico</span><span class="sxs-lookup"><span data-stu-id="15e6d-114">2: Get PowerShell host information for a specific process name</span></span>

```powershell
Get-PSHostProcessInfo -Name pwsh
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
pwsh            13912 DefaultAppDomain
```

## <span data-ttu-id="15e6d-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="15e6d-115">PARAMETERS</span></span>

### <span data-ttu-id="15e6d-116">-Id</span><span class="sxs-lookup"><span data-stu-id="15e6d-116">-Id</span></span>

<span data-ttu-id="15e6d-117">Especifica um processo pela ID do processo.</span><span class="sxs-lookup"><span data-stu-id="15e6d-117">Specifies a process by the process ID.</span></span> <span data-ttu-id="15e6d-118">Para obter uma ID de processo, execute o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="15e6d-118">To get a process ID, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="15e6d-119">-Name</span><span class="sxs-lookup"><span data-stu-id="15e6d-119">-Name</span></span>

<span data-ttu-id="15e6d-120">Especifica um processo pelo nome do processo.</span><span class="sxs-lookup"><span data-stu-id="15e6d-120">Specifies a process by the process name.</span></span> <span data-ttu-id="15e6d-121">Para obter um nome de processo, execute o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="15e6d-121">To get a process name, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="15e6d-122">-Processo</span><span class="sxs-lookup"><span data-stu-id="15e6d-122">-Process</span></span>

<span data-ttu-id="15e6d-123">Especifica um processo pelo objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="15e6d-123">Specifies a process by the process object.</span></span> <span data-ttu-id="15e6d-124">A maneira mais simples de usar esse parâmetro é salvar os resultados de um `Get-Process` comando que retorne o processo que você deseja inserir em uma variável e, em seguida, especificar a variável como o valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="15e6d-124">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

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

### <span data-ttu-id="15e6d-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="15e6d-125">CommonParameters</span></span>

<span data-ttu-id="15e6d-126">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="15e6d-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="15e6d-127">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="15e6d-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="15e6d-128">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="15e6d-128">INPUTS</span></span>

### <span data-ttu-id="15e6d-129">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="15e6d-129">System.Diagnostics.Process</span></span>

<span data-ttu-id="15e6d-130">É possível canalizar um objeto de **processo** `Get-Process` a partir desse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="15e6d-130">You can pipe a **Process** object from `Get-Process` to this cmdlet.</span></span>

## <span data-ttu-id="15e6d-131">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="15e6d-131">OUTPUTS</span></span>

### <span data-ttu-id="15e6d-132">Microsoft. PowerShell. Commands. PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="15e6d-132">Microsoft.PowerShell.Commands.PSHostProcessInfo</span></span>

## <span data-ttu-id="15e6d-133">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="15e6d-133">NOTES</span></span>

## <span data-ttu-id="15e6d-134">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="15e6d-134">RELATED LINKS</span></span>

[<span data-ttu-id="15e6d-135">Get-Process</span><span class="sxs-lookup"><span data-stu-id="15e6d-135">Get-Process</span></span>](../Microsoft.PowerShell.Management/get-process.md)

