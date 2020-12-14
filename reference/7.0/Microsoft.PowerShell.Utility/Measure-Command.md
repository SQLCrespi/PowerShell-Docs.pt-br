---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-command?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Command
ms.openlocfilehash: a7aed986ccd94472fe2dc89a43cc6b4d054494ca
ms.sourcegitcommit: 165d10405d9db3a68c417a239d3181378fd02b9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96935911"
---
# <span data-ttu-id="edb04-103">Measure-Command</span><span class="sxs-lookup"><span data-stu-id="edb04-103">Measure-Command</span></span>

## <span data-ttu-id="edb04-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="edb04-104">SYNOPSIS</span></span>
<span data-ttu-id="edb04-105">Mede o tempo de execução de cmdlets e blocos de script.</span><span class="sxs-lookup"><span data-stu-id="edb04-105">Measures the time it takes to run script blocks and cmdlets.</span></span>

## <span data-ttu-id="edb04-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="edb04-106">SYNTAX</span></span>

```
Measure-Command [-InputObject <PSObject>] [-Expression] <ScriptBlock> [<CommonParameters>]
```

## <span data-ttu-id="edb04-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="edb04-107">DESCRIPTION</span></span>

<span data-ttu-id="edb04-108">O `Measure-Command` cmdlet executa um bloco de script ou cmdlet internamente, vezes a execução da operação e retorna o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="edb04-108">The `Measure-Command` cmdlet runs a script block or cmdlet internally, times the execution of the operation, and returns the execution time.</span></span>

> [!NOTE]
> <span data-ttu-id="edb04-109">Blocos de script executados por `Measure-Command` execução no escopo atual, não um escopo filho.</span><span class="sxs-lookup"><span data-stu-id="edb04-109">Script blocks run by `Measure-Command` run in the current scope, not a child scope.</span></span>

## <span data-ttu-id="edb04-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="edb04-110">EXAMPLES</span></span>

### <span data-ttu-id="edb04-111">Exemplo 1: medir um comando</span><span class="sxs-lookup"><span data-stu-id="edb04-111">Example 1: Measure a command</span></span>

<span data-ttu-id="edb04-112">Este exemplo mede o tempo necessário para executar um `Get-EventLog` comando que obtém os eventos no log de eventos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="edb04-112">This example measures the time it takes to run a `Get-EventLog` command that gets the events in the Windows PowerShell event log.</span></span>

```powershell
Measure-Command { Get-EventLog "windows powershell" }
```

### <span data-ttu-id="edb04-113">Exemplo 2: comparar duas saídas de Measure-Command</span><span class="sxs-lookup"><span data-stu-id="edb04-113">Example 2: Compare two outputs from Measure-Command</span></span>

<span data-ttu-id="edb04-114">O primeiro comando mede o tempo necessário para processar um comando recursivo `Get-ChildItem` que usa o parâmetro **Path** para obter apenas os `.txt` arquivos no `C:\Windows` diretório e seus subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="edb04-114">The first command measures the time it takes to process a recursive `Get-ChildItem` command that uses the **Path** parameter to get only `.txt` files in the `C:\Windows` directory and its subdirectories.</span></span>

<span data-ttu-id="edb04-115">O segundo comando mede o tempo necessário para processar um comando recursivo `Get-ChildItem` que usa o parâmetro ' específico do provedor '.</span><span class="sxs-lookup"><span data-stu-id="edb04-115">The second command measures the time it takes to process a recursive `Get-ChildItem` command that uses the provider-specific \` parameter.</span></span>

<span data-ttu-id="edb04-116">Esses comandos mostram o valor do uso de um filtro específico do provedor em comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="edb04-116">These commands show the value of using a provider-specific filter in PowerShell commands.</span></span>

```powershell
Measure-Command { Get-ChildItem -Path C:\Windows\*.txt -Recurse }
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 8
Milliseconds      : 618
Ticks             : 86182763
TotalDays         : 9.9748568287037E-05
TotalHours        : 0.00239396563888889
TotalMinutes      : 0.143637938333333
TotalSeconds      : 8.6182763
TotalMilliseconds : 8618.2763
```

```powershell
Measure-Command {Get-ChildItem C:\Windows -Filter "*.txt" -Recurse}
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 1
Milliseconds      : 140
Ticks             : 11409189
TotalDays         : 1.32050798611111E-05
TotalHours        : 0.000316921916666667
TotalMinutes      : 0.019015315
TotalSeconds      : 1.1409189
TotalMilliseconds : 1140.9189
```

### <span data-ttu-id="edb04-117">Exemplo 3: entrada de encanamento para Measure-Command</span><span class="sxs-lookup"><span data-stu-id="edb04-117">Example 3: Piping input to Measure-Command</span></span>

<span data-ttu-id="edb04-118">Os objetos que são canalizados para `Measure-Command` estão disponíveis para o bloco de script que é passado para o parâmetro **expression** .</span><span class="sxs-lookup"><span data-stu-id="edb04-118">Objects that are piped to `Measure-Command` are available to the script block that is passed to the **Expression** parameter.</span></span> <span data-ttu-id="edb04-119">O bloco de script é executado uma vez para cada objeto no pipeline.</span><span class="sxs-lookup"><span data-stu-id="edb04-119">The script block is executed once for each object on the pipeline.</span></span>

```powershell
# Perform a simple operation to demonstrate the InputObject parameter
# Note that no output is displayed.
10, 20, 50 | Measure-Command -Expression { for ($i=0; $i -lt $_; $i++) {$i} }
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 12
Ticks             : 122672
TotalDays         : 1.41981481481481E-07
TotalHours        : 3.40755555555556E-06
TotalMinutes      : 0.000204453333333333
TotalSeconds      : 0.0122672
TotalMilliseconds : 12.2672
```

### <span data-ttu-id="edb04-120">Exemplo 4: exibindo a saída do comando medido</span><span class="sxs-lookup"><span data-stu-id="edb04-120">Example 4: Displaying output of measured command</span></span>

<span data-ttu-id="edb04-121">Para exibir a saída da expressão no `Measure-Command` , você pode usar um pipe para `Out-Default` .</span><span class="sxs-lookup"><span data-stu-id="edb04-121">To display output of expression in `Measure-Command` you can use a pipe to `Out-Default`.</span></span>

```powershell
# Perform the same operation as above adding Out-Default to every execution.
# This will show that the ScriptBlock is in fact executing for every item.
10, 20, 50 | Measure-Command -Expression {for ($i=0; $i -lt $_; $i++) {$i}; "$($_)" | Out-Default }
```

```Output
10
20
50


Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 11
Ticks             : 113745
TotalDays         : 1.31649305555556E-07
TotalHours        : 3.15958333333333E-06
TotalMinutes      : 0.000189575
TotalSeconds      : 0.0113745
TotalMilliseconds : 11.3745
```

### <span data-ttu-id="edb04-122">Exemplo 5: medindo a execução em um escopo filho</span><span class="sxs-lookup"><span data-stu-id="edb04-122">Example 5: Measuring execution in a child scope</span></span>

<span data-ttu-id="edb04-123">`Measure-Command` executa o bloco de script no escopo atual, de modo que o bloco de script pode modificar valores no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="edb04-123">`Measure-Command` runs the script block in the current scope, so the script block can modify values in the current scope.</span></span> <span data-ttu-id="edb04-124">Para evitar alterações no escopo atual, você deve encapsular o bloco de script entre chaves ( `{}` ) e usar o operador de invocação ( `&` ) para executar o bloco em um escopo filho.</span><span class="sxs-lookup"><span data-stu-id="edb04-124">To avoid changes to the current scope, you must wrap the script block in braces (`{}`) and use the invocation operator (`&`) to execute the block in a child scope.</span></span>

```powershell
$foo = 'Value 1'
$null = Measure-Command { $foo = 'Value 2' }
$foo
$null = Measure-Command { & { $foo = 'Value 3' } }
$foo
```

```Output
Value 2
Value 2
```

<span data-ttu-id="edb04-125">Para obter mais informações sobre o operador de invocação, consulte [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md#call-operator-).</span><span class="sxs-lookup"><span data-stu-id="edb04-125">For more information about the invocation operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md#call-operator-).</span></span>

## <span data-ttu-id="edb04-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="edb04-126">PARAMETERS</span></span>

### <span data-ttu-id="edb04-127">-Expressão</span><span class="sxs-lookup"><span data-stu-id="edb04-127">-Expression</span></span>

<span data-ttu-id="edb04-128">Especifica a expressão que está sendo cronometrada.</span><span class="sxs-lookup"><span data-stu-id="edb04-128">Specifies the expression that is being timed.</span></span> <span data-ttu-id="edb04-129">Coloque a expressão entre chaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="edb04-129">Enclose the expression in braces (`{}`).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="edb04-130">-InputObject</span><span class="sxs-lookup"><span data-stu-id="edb04-130">-InputObject</span></span>

<span data-ttu-id="edb04-131">Objetos vinculados ao parâmetro **InputObject** são entradas opcionais para o bloco de script passado para o parâmetro **expression** .</span><span class="sxs-lookup"><span data-stu-id="edb04-131">Objects bound to the **InputObject** parameter are optional input for the script block passed to the **Expression** parameter.</span></span> <span data-ttu-id="edb04-132">Dentro do bloco de script, `$_` pode ser usado para referenciar o objeto atual no pipeline.</span><span class="sxs-lookup"><span data-stu-id="edb04-132">Inside the script block, `$_` can be used to reference the current object in the pipeline.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="edb04-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="edb04-133">CommonParameters</span></span>

<span data-ttu-id="edb04-134">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="edb04-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="edb04-135">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="edb04-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="edb04-136">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="edb04-136">INPUTS</span></span>

### <span data-ttu-id="edb04-137">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="edb04-137">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="edb04-138">É possível canalizar um objeto para `Measure-Command` .</span><span class="sxs-lookup"><span data-stu-id="edb04-138">You can pipe an object to `Measure-Command`.</span></span>

## <span data-ttu-id="edb04-139">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="edb04-139">OUTPUTS</span></span>

### <span data-ttu-id="edb04-140">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="edb04-140">System.TimeSpan</span></span>

<span data-ttu-id="edb04-141">`Measure-Command` Retorna um objeto de período de tempo que representa o resultado.</span><span class="sxs-lookup"><span data-stu-id="edb04-141">`Measure-Command` returns a time span object that represents the result.</span></span>

## <span data-ttu-id="edb04-142">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="edb04-142">NOTES</span></span>

## <span data-ttu-id="edb04-143">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="edb04-143">RELATED LINKS</span></span>

[<span data-ttu-id="edb04-144">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="edb04-144">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="edb04-145">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="edb04-145">Trace-Command</span></span>](Trace-Command.md)
