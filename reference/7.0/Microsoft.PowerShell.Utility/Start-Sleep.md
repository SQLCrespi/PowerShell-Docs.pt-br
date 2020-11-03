---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: 535cad057db406eaa48259288e34da6da4ed1cbb
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192853"
---
# <span data-ttu-id="73ab7-103">Start-Sleep</span><span class="sxs-lookup"><span data-stu-id="73ab7-103">Start-Sleep</span></span>

## <span data-ttu-id="73ab7-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="73ab7-104">SYNOPSIS</span></span>
<span data-ttu-id="73ab7-105">Suspende a atividade em um script ou sessão pelo período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="73ab7-105">Suspends the activity in a script or session for the specified period of time.</span></span>

## <span data-ttu-id="73ab7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="73ab7-106">SYNTAX</span></span>

### <span data-ttu-id="73ab7-107">Segundos (padrão)</span><span class="sxs-lookup"><span data-stu-id="73ab7-107">Seconds (Default)</span></span>

```
Start-Sleep [-Seconds] <Double> [<CommonParameters>]
```

### <span data-ttu-id="73ab7-108">Milissegundos</span><span class="sxs-lookup"><span data-stu-id="73ab7-108">Milliseconds</span></span>

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## <span data-ttu-id="73ab7-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="73ab7-109">DESCRIPTION</span></span>

<span data-ttu-id="73ab7-110">O `Start-Sleep` cmdlet suspende a atividade em um script ou sessão pelo período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="73ab7-110">The `Start-Sleep` cmdlet suspends the activity in a script or session for the specified period of time.</span></span> <span data-ttu-id="73ab7-111">É possível utilizá-lo para várias tarefas, como aguardar a conclusão de uma operação ou pausar antes de repetir uma operação.</span><span class="sxs-lookup"><span data-stu-id="73ab7-111">You can use it for many tasks, such as waiting for an operation to complete or pausing before repeating an operation.</span></span>

## <span data-ttu-id="73ab7-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="73ab7-112">EXAMPLES</span></span>

### <span data-ttu-id="73ab7-113">Exemplo 1: suspender todos os comandos por 15 segundos</span><span class="sxs-lookup"><span data-stu-id="73ab7-113">Example 1: Sleep all commands for 15 seconds</span></span>

```powershell
Start-Sleep -s 15
```

### <span data-ttu-id="73ab7-114">Exemplo 2: suspender todos os comandos por 1,5 segundos</span><span class="sxs-lookup"><span data-stu-id="73ab7-114">Example 2: Sleep all commands for 1.5 seconds</span></span>

<span data-ttu-id="73ab7-115">Este exemplo faz com que todos os comandos na sessão sejam suspensos por um e um semestre de segundos.</span><span class="sxs-lookup"><span data-stu-id="73ab7-115">This example makes all the commands in the session sleep for one and one-half of a seconds.</span></span>

```powershell
Start-Sleep -Seconds 1.5
```

## <span data-ttu-id="73ab7-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="73ab7-116">PARAMETERS</span></span>

### <span data-ttu-id="73ab7-117">-Milissegundos</span><span class="sxs-lookup"><span data-stu-id="73ab7-117">-Milliseconds</span></span>

<span data-ttu-id="73ab7-118">Especifica por quanto tempo o recurso entra em suspensão, em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="73ab7-118">Specifies how long the resource sleeps in milliseconds.</span></span> <span data-ttu-id="73ab7-119">O parâmetro pode ser abreviado como **m** .</span><span class="sxs-lookup"><span data-stu-id="73ab7-119">The parameter can be abbreviated as **m** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: Milliseconds
Aliases: ms

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="73ab7-120">-Segundos</span><span class="sxs-lookup"><span data-stu-id="73ab7-120">-Seconds</span></span>

<span data-ttu-id="73ab7-121">Especifica por quanto tempo o recurso entra em suspensão, em segundos.</span><span class="sxs-lookup"><span data-stu-id="73ab7-121">Specifies how long the resource sleeps in seconds.</span></span> <span data-ttu-id="73ab7-122">Você pode omitir o nome do parâmetro ou pode abreviar como **s** .</span><span class="sxs-lookup"><span data-stu-id="73ab7-122">You can omit the parameter name or you can abbreviate it as **s** .</span></span> <span data-ttu-id="73ab7-123">A partir do PowerShell 6.2.0, esse parâmetro agora aceita valores fracionários.</span><span class="sxs-lookup"><span data-stu-id="73ab7-123">Beginning in PowerShell 6.2.0, this parameter now accepts fractional values.</span></span>

```yaml
Type: System.Double
Parameter Sets: Seconds
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="73ab7-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="73ab7-124">CommonParameters</span></span>

<span data-ttu-id="73ab7-125">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="73ab7-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="73ab7-126">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="73ab7-126">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="73ab7-127">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="73ab7-127">INPUTS</span></span>

### <span data-ttu-id="73ab7-128">System.Int32</span><span class="sxs-lookup"><span data-stu-id="73ab7-128">System.Int32</span></span>

<span data-ttu-id="73ab7-129">Você pode canalizar o número de segundos para `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="73ab7-129">You can pipe the number of seconds to `Start-Sleep`.</span></span>

## <span data-ttu-id="73ab7-130">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="73ab7-130">OUTPUTS</span></span>

### <span data-ttu-id="73ab7-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="73ab7-131">None</span></span>

<span data-ttu-id="73ab7-132">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="73ab7-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="73ab7-133">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="73ab7-133">NOTES</span></span>

- <span data-ttu-id="73ab7-134">Você também pode consultar `Start-Sleep` por seu alias interno, `sleep` .</span><span class="sxs-lookup"><span data-stu-id="73ab7-134">You can also refer to `Start-Sleep` by its built-in alias, `sleep`.</span></span> <span data-ttu-id="73ab7-135">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="73ab7-135">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="73ab7-136">`Ctrl+C` é dividido de `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="73ab7-136">`Ctrl+C` breaks out of `Start-Sleep`.</span></span>
  - <span data-ttu-id="73ab7-137">`Ctrl+C` Não é interrompido de `[Threading.Thread]::Sleep` .</span><span class="sxs-lookup"><span data-stu-id="73ab7-137">`Ctrl+C` does not break out of `[Threading.Thread]::Sleep`.</span></span> <span data-ttu-id="73ab7-138">Para obter mais informações, consulte [método Thread. Sleep](/dotnet/api/system.threading.thread.sleep).</span><span class="sxs-lookup"><span data-stu-id="73ab7-138">For more information, see [Thread.Sleep Method](/dotnet/api/system.threading.thread.sleep).</span></span>

## <span data-ttu-id="73ab7-139">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="73ab7-139">RELATED LINKS</span></span>
