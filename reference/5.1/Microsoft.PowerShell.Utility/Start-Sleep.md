---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 3/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: e4add39c09b6123aaf8c9302529346a6b1dec391
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193732"
---
# <span data-ttu-id="d7a26-103">Start-Sleep</span><span class="sxs-lookup"><span data-stu-id="d7a26-103">Start-Sleep</span></span>

## <span data-ttu-id="d7a26-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d7a26-104">SYNOPSIS</span></span>
<span data-ttu-id="d7a26-105">Suspende a atividade em um script ou sessão pelo período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="d7a26-105">Suspends the activity in a script or session for the specified period of time.</span></span>

## <span data-ttu-id="d7a26-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d7a26-106">SYNTAX</span></span>

### <span data-ttu-id="d7a26-107">Segundos (padrão)</span><span class="sxs-lookup"><span data-stu-id="d7a26-107">Seconds (Default)</span></span>

```
Start-Sleep [-Seconds] <Int32> [<CommonParameters>]
```

### <span data-ttu-id="d7a26-108">Milissegundos</span><span class="sxs-lookup"><span data-stu-id="d7a26-108">Milliseconds</span></span>

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## <span data-ttu-id="d7a26-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d7a26-109">DESCRIPTION</span></span>

<span data-ttu-id="d7a26-110">O `Start-Sleep` cmdlet suspende a atividade em um script ou sessão pelo período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="d7a26-110">The `Start-Sleep` cmdlet suspends the activity in a script or session for the specified period of time.</span></span>
<span data-ttu-id="d7a26-111">É possível utilizá-lo para várias tarefas, como aguardar a conclusão de uma operação ou pausar antes de repetir uma operação.</span><span class="sxs-lookup"><span data-stu-id="d7a26-111">You can use it for many tasks, such as waiting for an operation to complete or pausing before repeating an operation.</span></span>

## <span data-ttu-id="d7a26-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d7a26-112">EXAMPLES</span></span>

### <span data-ttu-id="d7a26-113">Exemplo 1: suspender todos os comandos por 15 segundos</span><span class="sxs-lookup"><span data-stu-id="d7a26-113">Example 1: Sleep all commands for 15 seconds</span></span>

```powershell
Start-Sleep -s 15
```

<span data-ttu-id="d7a26-114">Esse comando faz com que todos os comandos na sessão fiquem em suspensão por 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="d7a26-114">This command makes all commands in the session sleep for 15 seconds.</span></span>

### <span data-ttu-id="d7a26-115">Exemplo 2: suspender todos os comandos</span><span class="sxs-lookup"><span data-stu-id="d7a26-115">Example 2: Sleep all commands</span></span>

```powershell
Start-Sleep -m 500
```

<span data-ttu-id="d7a26-116">Esse comando faz todos os comandos na sessão fiquem em suspensão por meio segundo (500 milissegundos).</span><span class="sxs-lookup"><span data-stu-id="d7a26-116">This command makes all the commands in the session sleep for one-half of a second (500 milliseconds).</span></span>

## <span data-ttu-id="d7a26-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d7a26-117">PARAMETERS</span></span>

### <span data-ttu-id="d7a26-118">-Milissegundos</span><span class="sxs-lookup"><span data-stu-id="d7a26-118">-Milliseconds</span></span>

<span data-ttu-id="d7a26-119">Especifica por quanto tempo o recurso entra em suspensão, em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="d7a26-119">Specifies how long the resource sleeps in milliseconds.</span></span>
<span data-ttu-id="d7a26-120">O parâmetro pode ser abreviado como **m** .</span><span class="sxs-lookup"><span data-stu-id="d7a26-120">The parameter can be abbreviated as **m** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: Milliseconds
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d7a26-121">-Segundos</span><span class="sxs-lookup"><span data-stu-id="d7a26-121">-Seconds</span></span>

<span data-ttu-id="d7a26-122">Especifica por quanto tempo o recurso entra em suspensão, em segundos.</span><span class="sxs-lookup"><span data-stu-id="d7a26-122">Specifies how long the resource sleeps in seconds.</span></span>
<span data-ttu-id="d7a26-123">Você pode omitir o nome do parâmetro ( **segundos** ) ou pode abreviar como **s** .</span><span class="sxs-lookup"><span data-stu-id="d7a26-123">You can omit the parameter name ( **Seconds** ), or you can abbreviate it as **s** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: Seconds
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d7a26-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d7a26-124">CommonParameters</span></span>

<span data-ttu-id="d7a26-125">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d7a26-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d7a26-126">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d7a26-126">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d7a26-127">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d7a26-127">INPUTS</span></span>

### <span data-ttu-id="d7a26-128">System.Int32</span><span class="sxs-lookup"><span data-stu-id="d7a26-128">System.Int32</span></span>

<span data-ttu-id="d7a26-129">Você pode canalizar o número de segundos para `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="d7a26-129">You can pipe the number of seconds to `Start-Sleep`.</span></span>

## <span data-ttu-id="d7a26-130">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d7a26-130">OUTPUTS</span></span>

### <span data-ttu-id="d7a26-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d7a26-131">None</span></span>

<span data-ttu-id="d7a26-132">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="d7a26-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="d7a26-133">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d7a26-133">NOTES</span></span>

- <span data-ttu-id="d7a26-134">Você também pode consultar `Start-Sleep` por seu alias interno, `sleep` .</span><span class="sxs-lookup"><span data-stu-id="d7a26-134">You can also refer to `Start-Sleep` by its built-in alias, `sleep`.</span></span> <span data-ttu-id="d7a26-135">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="d7a26-135">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="d7a26-136">`Ctrl+C` é dividido de `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="d7a26-136">`Ctrl+C` breaks out of `Start-Sleep`.</span></span>
  - <span data-ttu-id="d7a26-137">`Ctrl+C` Não é interrompido de `[Threading.Thread]::Sleep` .</span><span class="sxs-lookup"><span data-stu-id="d7a26-137">`Ctrl+C` does not break out of `[Threading.Thread]::Sleep`.</span></span> <span data-ttu-id="d7a26-138">Para obter mais informações, consulte [método Thread. Sleep](/dotnet/api/system.threading.thread.sleep).</span><span class="sxs-lookup"><span data-stu-id="d7a26-138">For more information, see [Thread.Sleep Method](/dotnet/api/system.threading.thread.sleep).</span></span>

## <span data-ttu-id="d7a26-139">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d7a26-139">RELATED LINKS</span></span>
