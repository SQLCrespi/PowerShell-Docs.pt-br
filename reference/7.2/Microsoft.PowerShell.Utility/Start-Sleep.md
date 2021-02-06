---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: e4d06fdd1d5a616c24a4dd7bec10ea4dadea4062
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595579"
---
# <span data-ttu-id="9dfd4-102">Start-Sleep</span><span class="sxs-lookup"><span data-stu-id="9dfd4-102">Start-Sleep</span></span>

## <span data-ttu-id="9dfd4-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9dfd4-103">SYNOPSIS</span></span>
<span data-ttu-id="9dfd4-104">Suspende a atividade em um script ou sessão pelo período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="9dfd4-104">Suspends the activity in a script or session for the specified period of time.</span></span>

## <span data-ttu-id="9dfd4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9dfd4-105">SYNTAX</span></span>

### <span data-ttu-id="9dfd4-106">Segundos (padrão)</span><span class="sxs-lookup"><span data-stu-id="9dfd4-106">Seconds (Default)</span></span>

```
Start-Sleep [-Seconds] <Double> [<CommonParameters>]
```

### <span data-ttu-id="9dfd4-107">Milissegundos</span><span class="sxs-lookup"><span data-stu-id="9dfd4-107">Milliseconds</span></span>

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## <span data-ttu-id="9dfd4-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9dfd4-108">DESCRIPTION</span></span>

<span data-ttu-id="9dfd4-109">O `Start-Sleep` cmdlet suspende a atividade em um script ou sessão pelo período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="9dfd4-109">The `Start-Sleep` cmdlet suspends the activity in a script or session for the specified period of time.</span></span> <span data-ttu-id="9dfd4-110">É possível utilizá-lo para várias tarefas, como aguardar a conclusão de uma operação ou pausar antes de repetir uma operação.</span><span class="sxs-lookup"><span data-stu-id="9dfd4-110">You can use it for many tasks, such as waiting for an operation to complete or pausing before repeating an operation.</span></span>

## <span data-ttu-id="9dfd4-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9dfd4-111">EXAMPLES</span></span>

### <span data-ttu-id="9dfd4-112">Exemplo 1: suspender todos os comandos por 15 segundos</span><span class="sxs-lookup"><span data-stu-id="9dfd4-112">Example 1: Sleep all commands for 15 seconds</span></span>

```powershell
Start-Sleep -s 15
```

### <span data-ttu-id="9dfd4-113">Exemplo 2: suspender todos os comandos por 1,5 segundos</span><span class="sxs-lookup"><span data-stu-id="9dfd4-113">Example 2: Sleep all commands for 1.5 seconds</span></span>

<span data-ttu-id="9dfd4-114">Este exemplo faz com que todos os comandos na sessão sejam suspensos por um e um semestre de segundos.</span><span class="sxs-lookup"><span data-stu-id="9dfd4-114">This example makes all the commands in the session sleep for one and one-half of a seconds.</span></span>

```powershell
Start-Sleep -Seconds 1.5
```

## <span data-ttu-id="9dfd4-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9dfd4-115">PARAMETERS</span></span>

### <span data-ttu-id="9dfd4-116">-Milissegundos</span><span class="sxs-lookup"><span data-stu-id="9dfd4-116">-Milliseconds</span></span>

<span data-ttu-id="9dfd4-117">Especifica por quanto tempo o recurso entra em suspensão, em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="9dfd4-117">Specifies how long the resource sleeps in milliseconds.</span></span> <span data-ttu-id="9dfd4-118">O parâmetro pode ser abreviado como **m**.</span><span class="sxs-lookup"><span data-stu-id="9dfd4-118">The parameter can be abbreviated as **m**.</span></span>

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

### <span data-ttu-id="9dfd4-119">-Segundos</span><span class="sxs-lookup"><span data-stu-id="9dfd4-119">-Seconds</span></span>

<span data-ttu-id="9dfd4-120">Especifica por quanto tempo o recurso entra em suspensão, em segundos.</span><span class="sxs-lookup"><span data-stu-id="9dfd4-120">Specifies how long the resource sleeps in seconds.</span></span> <span data-ttu-id="9dfd4-121">Você pode omitir o nome do parâmetro ou pode abreviar como **s**.</span><span class="sxs-lookup"><span data-stu-id="9dfd4-121">You can omit the parameter name or you can abbreviate it as **s**.</span></span> <span data-ttu-id="9dfd4-122">A partir do PowerShell 6.2.0, esse parâmetro agora aceita valores fracionários.</span><span class="sxs-lookup"><span data-stu-id="9dfd4-122">Beginning in PowerShell 6.2.0, this parameter now accepts fractional values.</span></span>

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

### <span data-ttu-id="9dfd4-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9dfd4-123">CommonParameters</span></span>

<span data-ttu-id="9dfd4-124">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9dfd4-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9dfd4-125">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9dfd4-125">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9dfd4-126">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9dfd4-126">INPUTS</span></span>

### <span data-ttu-id="9dfd4-127">System.Int32</span><span class="sxs-lookup"><span data-stu-id="9dfd4-127">System.Int32</span></span>

<span data-ttu-id="9dfd4-128">Você pode canalizar o número de segundos para `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="9dfd4-128">You can pipe the number of seconds to `Start-Sleep`.</span></span>

## <span data-ttu-id="9dfd4-129">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9dfd4-129">OUTPUTS</span></span>

### <span data-ttu-id="9dfd4-130">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9dfd4-130">None</span></span>

<span data-ttu-id="9dfd4-131">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="9dfd4-131">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="9dfd4-132">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9dfd4-132">NOTES</span></span>

- <span data-ttu-id="9dfd4-133">Você também pode consultar `Start-Sleep` por seu alias interno, `sleep` .</span><span class="sxs-lookup"><span data-stu-id="9dfd4-133">You can also refer to `Start-Sleep` by its built-in alias, `sleep`.</span></span> <span data-ttu-id="9dfd4-134">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="9dfd4-134">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="9dfd4-135">`Ctrl+C` é dividido de `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="9dfd4-135">`Ctrl+C` breaks out of `Start-Sleep`.</span></span>
  - <span data-ttu-id="9dfd4-136">`Ctrl+C` Não é interrompido de `[Threading.Thread]::Sleep` .</span><span class="sxs-lookup"><span data-stu-id="9dfd4-136">`Ctrl+C` does not break out of `[Threading.Thread]::Sleep`.</span></span> <span data-ttu-id="9dfd4-137">Para obter mais informações, consulte [método Thread. Sleep](/dotnet/api/system.threading.thread.sleep).</span><span class="sxs-lookup"><span data-stu-id="9dfd4-137">For more information, see [Thread.Sleep Method](/dotnet/api/system.threading.thread.sleep).</span></span>

## <span data-ttu-id="9dfd4-138">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9dfd4-138">RELATED LINKS</span></span>

