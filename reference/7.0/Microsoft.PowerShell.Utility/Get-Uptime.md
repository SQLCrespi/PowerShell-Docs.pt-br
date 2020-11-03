---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uptime?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Uptime
ms.openlocfilehash: a04be33767c9e0435de9693fbd5e07d66705b5d1
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193180"
---
# <span data-ttu-id="fdbee-102">Get-Uptime</span><span class="sxs-lookup"><span data-stu-id="fdbee-102">Get-Uptime</span></span>

## <span data-ttu-id="fdbee-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fdbee-103">SYNOPSIS</span></span>
<span data-ttu-id="fdbee-104">Obter o **período** desde a última inicialização.</span><span class="sxs-lookup"><span data-stu-id="fdbee-104">Get the **TimeSpan** since last boot.</span></span>

## <span data-ttu-id="fdbee-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fdbee-105">SYNTAX</span></span>

### <span data-ttu-id="fdbee-106">TimeSpan (padrão)</span><span class="sxs-lookup"><span data-stu-id="fdbee-106">Timespan (Default)</span></span>

```
Get-Uptime [<CommonParameters>]
```

### <span data-ttu-id="fdbee-107">Depois</span><span class="sxs-lookup"><span data-stu-id="fdbee-107">Since</span></span>

```
Get-Uptime [-Since] [<CommonParameters>]
```

## <span data-ttu-id="fdbee-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fdbee-108">DESCRIPTION</span></span>

<span data-ttu-id="fdbee-109">Esse cmdlet retorna o tempo decorrido desde a última inicialização do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="fdbee-109">This cmdlet returns the time elapsed since the last boot of the operating system.</span></span>

<span data-ttu-id="fdbee-110">O `Get-Uptime` cmdlet foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="fdbee-110">The `Get-Uptime` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="fdbee-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fdbee-111">EXAMPLES</span></span>

### <span data-ttu-id="fdbee-112">Exemplo 1-mostrar o tempo desde a última inicialização</span><span class="sxs-lookup"><span data-stu-id="fdbee-112">Example 1 - Show time since last boot</span></span>

```powershell
Get-Uptime
```

```Output
Days              : 9
Hours             : 0
Minutes           : 9
Seconds           : 45
Milliseconds      : 0
Ticks             : 7781850000000
TotalDays         : 9.00677083333333
TotalHours        : 216.1625
TotalMinutes      : 12969.75
TotalSeconds      : 778185
TotalMilliseconds : 778185000
```

### <span data-ttu-id="fdbee-113">Exemplo 2 – mostrar a hora da última inicialização</span><span class="sxs-lookup"><span data-stu-id="fdbee-113">Example 2 - Show the time of the last boot</span></span>

```powershell
Get-Uptime -Since
```

```Output
Tuesday, June 18, 2019 2:34:56 PM
```

## <span data-ttu-id="fdbee-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fdbee-114">PARAMETERS</span></span>

### <span data-ttu-id="fdbee-115">-Desde</span><span class="sxs-lookup"><span data-stu-id="fdbee-115">-Since</span></span>

<span data-ttu-id="fdbee-116">Faz com que o cmdlet retorne um objeto **DateTime** que representa a última vez em que o sistema operacional foi inicializado.</span><span class="sxs-lookup"><span data-stu-id="fdbee-116">Cause the cmdlet to return a **DateTime** object representing the last time that the operating system was booted.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Since
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fdbee-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fdbee-117">CommonParameters</span></span>

<span data-ttu-id="fdbee-118">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fdbee-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fdbee-119">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fdbee-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fdbee-120">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fdbee-120">INPUTS</span></span>

### <span data-ttu-id="fdbee-121">Nenhum</span><span class="sxs-lookup"><span data-stu-id="fdbee-121">None</span></span>

## <span data-ttu-id="fdbee-122">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fdbee-122">OUTPUTS</span></span>

### <span data-ttu-id="fdbee-123">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="fdbee-123">System.TimeSpan</span></span>

<span data-ttu-id="fdbee-124">Esse é o tipo de retorno padrão quando nenhum parâmetro é usado.</span><span class="sxs-lookup"><span data-stu-id="fdbee-124">This is the default return type when no parameters are used.</span></span>

### <span data-ttu-id="fdbee-125">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="fdbee-125">System.DateTime</span></span>

<span data-ttu-id="fdbee-126">Esse tipo é retornado ao usar o parâmetro **Since** .</span><span class="sxs-lookup"><span data-stu-id="fdbee-126">This type is returned when using the **Since** parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="fdbee-127">Se a inicialização rápida do Windows estiver habilitada, o Windows não atualizará o valor armazenado em **LastBootUpTime** .</span><span class="sxs-lookup"><span data-stu-id="fdbee-127">If Windows fast startup is enabled, Windows does not update the value stored in **LastBootUpTime** .</span></span> <span data-ttu-id="fdbee-128">Para desabilitar a inicialização rápida, execute o seguinte comando: `Powercfg -h off` .</span><span class="sxs-lookup"><span data-stu-id="fdbee-128">To disable fast startup, run the following command: `Powercfg -h off`.</span></span>
>
> <span data-ttu-id="fdbee-129">Para obter mais informações sobre a inicialização rápida do Windows, consulte como [diferenciar a inicialização rápida de Wake-from-Hibernation](/windows-hardware/drivers/kernel/distinguishing-fast-startup-from-wake-from-hibernation).</span><span class="sxs-lookup"><span data-stu-id="fdbee-129">For more information about Windows fast startup, see [Distinguishing Fast Startup from Wake-from-Hibernation](/windows-hardware/drivers/kernel/distinguishing-fast-startup-from-wake-from-hibernation).</span></span>

## <span data-ttu-id="fdbee-130">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fdbee-130">NOTES</span></span>

<span data-ttu-id="fdbee-131">No Windows, o valor retornado é o mesmo que a propriedade **LastBootUpTime** da classe **Win32_OperatingSystem** no WMI.</span><span class="sxs-lookup"><span data-stu-id="fdbee-131">On Windows, the value returned is the same as the **LastBootUpTime** property of the **Win32_OperatingSystem** class in WMI.</span></span>

## <span data-ttu-id="fdbee-132">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fdbee-132">RELATED LINKS</span></span>

[<span data-ttu-id="fdbee-133">Win32_OperatingSystem</span><span class="sxs-lookup"><span data-stu-id="fdbee-133">Win32_OperatingSystem</span></span>](/windows/win32/cimwin32prov/win32-operatingsystem#properties)
