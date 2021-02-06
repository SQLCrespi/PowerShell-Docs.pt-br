---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/19/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-list?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-List
ms.openlocfilehash: d8410fbc2d3f29f0726f84ab151993a60ce95434
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598428"
---
# <span data-ttu-id="d5fbf-102">Format-List</span><span class="sxs-lookup"><span data-stu-id="d5fbf-102">Format-List</span></span>

## <span data-ttu-id="d5fbf-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d5fbf-103">SYNOPSIS</span></span>
<span data-ttu-id="d5fbf-104">Formata a saída como uma lista de propriedades na qual cada propriedade aparece em uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-104">Formats the output as a list of properties in which each property appears on a new line.</span></span>

## <span data-ttu-id="d5fbf-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d5fbf-105">SYNTAX</span></span>

```
Format-List [[-Property] <Object[]>] [-GroupBy <Object>] [-View <string>] [-ShowError]
[-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>] [<CommonParameters>]
```

## <span data-ttu-id="d5fbf-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d5fbf-106">DESCRIPTION</span></span>

<span data-ttu-id="d5fbf-107">O `Format-List` cmdlet formata a saída de um comando como uma lista de propriedades nas quais cada propriedade é exibida em uma linha separada.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-107">The `Format-List` cmdlet formats the output of a command as a list of properties in which each property is displayed on a separate line.</span></span> <span data-ttu-id="d5fbf-108">Você pode usar `Format-List` para formatar e exibir todas as propriedades ou de um objeto selecionado como uma lista (Format-List \*).</span><span class="sxs-lookup"><span data-stu-id="d5fbf-108">You can use `Format-List` to format and display all or selected properties of an object as a list (format-list \*).</span></span>

<span data-ttu-id="d5fbf-109">Como mais espaço está disponível para cada item em uma lista do que em uma tabela, o PowerShell exibe mais propriedades do objeto na lista e os valores de propriedade são menos prováveis de serem truncados.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-109">Because more space is available for each item in a list than in a table, PowerShell displays more properties of the object in the list, and the property values are less likely to be truncated.</span></span>

## <span data-ttu-id="d5fbf-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d5fbf-110">EXAMPLES</span></span>

### <span data-ttu-id="d5fbf-111">Exemplo 1: Formatar serviços de computador</span><span class="sxs-lookup"><span data-stu-id="d5fbf-111">Example 1: Format computer services</span></span>

```powershell
Get-Service | Format-List
```

<span data-ttu-id="d5fbf-112">Esse comando formata informações sobre os serviços no computador como uma lista.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-112">This command formats information about services on the computer as a list.</span></span> <span data-ttu-id="d5fbf-113">Por padrão, os serviços são formatados como uma tabela.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-113">By default, the services are formatted as a table.</span></span> <span data-ttu-id="d5fbf-114">O `Get-Service` cmdlet obtém os objetos que representam os serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-114">The `Get-Service` cmdlet gets objects representing the services on the computer.</span></span> <span data-ttu-id="d5fbf-115">O operador de pipeline (|) passa os resultados por meio do pipeline para `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="d5fbf-115">The pipeline operator (|) passes the results through the pipeline to `Format-List`.</span></span>
<span data-ttu-id="d5fbf-116">Em seguida, o `Format-List` comando formata as informações de serviço em uma lista e as envia para o cmdlet de saída padrão para exibição.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-116">Then, the `Format-List` command formats the service information in a list and sends it to the default output cmdlet for display.</span></span>

### <span data-ttu-id="d5fbf-117">Exemplo 2: Formatar arquivos PS1XML</span><span class="sxs-lookup"><span data-stu-id="d5fbf-117">Example 2: Format PS1XML files</span></span>

<span data-ttu-id="d5fbf-118">Esses comandos exibem informações sobre os arquivos PS1XML no diretório do PowerShell como uma lista.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-118">These commands display information about the PS1XML files in the PowerShell directory as a list.</span></span>

```powershell
$A = Get-ChildItem $pshome\*.ps1xml
Format-List -InputObject $A
```

<span data-ttu-id="d5fbf-119">O primeiro comando obtém os objetos que representam os arquivos e os armazena na `$A` variável.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-119">The first command gets the objects representing the files and stores them in the `$A` variable.</span></span>

<span data-ttu-id="d5fbf-120">O segundo comando usa `Format-List` para formatar informações sobre objetos armazenados no `$A` .</span><span class="sxs-lookup"><span data-stu-id="d5fbf-120">The second command uses `Format-List` to format information about objects stored in `$A`.</span></span> <span data-ttu-id="d5fbf-121">Esse comando usa o parâmetro **InputObject** para passar a variável para `Format-List` , que envia a saída formatada para o cmdlet de saída padrão para exibição.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-121">This command uses the **InputObject** parameter to pass the variable to `Format-List`, which then sends the formatted output to the default output cmdlet for display.</span></span>

### <span data-ttu-id="d5fbf-122">Exemplo 3: Formatar Propriedades do processo por nome</span><span class="sxs-lookup"><span data-stu-id="d5fbf-122">Example 3: Format process properties by name</span></span>

<span data-ttu-id="d5fbf-123">Este comando exibe o nome, a prioridade básica e a classe de prioridade de cada processo no computador.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-123">This command displays the name, base priority, and priority class of each process on the computer.</span></span>

```powershell
Get-Process | Format-List -Property name, basepriority, priorityclass
```

<span data-ttu-id="d5fbf-124">Ele usa o `Get-Process` cmdlet para obter um objeto que representa cada processo.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-124">It uses the `Get-Process` cmdlet to get an object representing each process.</span></span> <span data-ttu-id="d5fbf-125">O operador de pipeline (|) passa os objetos de processo por meio do pipeline para `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="d5fbf-125">The pipeline operator (|) passes the process objects through the pipeline to `Format-List`.</span></span> <span data-ttu-id="d5fbf-126">`Format-List` formata os processos como uma lista das propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-126">`Format-List` formats the processes as a list of the specified properties.</span></span> <span data-ttu-id="d5fbf-127">O nome do parâmetro de *Propriedade* é opcional, portanto, você pode omiti-lo.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-127">The *Property* parameter name is optional, so you can omit it.</span></span>

### <span data-ttu-id="d5fbf-128">Exemplo 4: Formatar todas as propriedades de um processo</span><span class="sxs-lookup"><span data-stu-id="d5fbf-128">Example 4: Format all properties for a process</span></span>

<span data-ttu-id="d5fbf-129">Esse comando exibe todas as propriedades do processo Winlogon.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-129">This command displays all of the properties of the Winlogon process.</span></span>

```powershell
Get-Process winlogon | Format-List -Property *
```

<span data-ttu-id="d5fbf-130">Ele usa o cmdlet Get-Process para obter um objeto que representa o processo do Winlogon.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-130">It uses the Get-Process cmdlet to get an object representing the Winlogon process.</span></span> <span data-ttu-id="d5fbf-131">O operador de pipeline (|) passa o objeto de processo do Winlogon por meio do pipeline para `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="d5fbf-131">The pipeline operator (|) passes the Winlogon process object through the pipeline to `Format-List`.</span></span> <span data-ttu-id="d5fbf-132">O comando usa o parâmetro *Property* para especificar as propriedades e o \* para indicar todas as propriedades.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-132">The command uses the *Property* parameter to specify the properties and the \* to indicate all properties.</span></span>
<span data-ttu-id="d5fbf-133">Como o nome do parâmetro de *Propriedade* é opcional, você pode omiti-lo e digitar o comando como `Format-List *` .</span><span class="sxs-lookup"><span data-stu-id="d5fbf-133">Because the name of the *Property* parameter is optional, you can omit it and type the command as `Format-List *`.</span></span> <span data-ttu-id="d5fbf-134">`Format-List` envia automaticamente os resultados para o cmdlet de saída padrão para exibição.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-134">`Format-List` automatically sends the results to the default output cmdlet for display.</span></span>

### <span data-ttu-id="d5fbf-135">Exemplo 5: erros de formato de solução de problemas</span><span class="sxs-lookup"><span data-stu-id="d5fbf-135">Example 5: Troubleshooting format errors</span></span>

<span data-ttu-id="d5fbf-136">Os exemplos a seguir mostram os resultados da adição dos parâmetros **DisplayError** ou **exerror** com uma expressão.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-136">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -DisplayError

DayOfWeek    : Friday
 $_ / $null  : #ERR

PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -ShowError

DayOfWeek    : Friday
 $_ / $null  :

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 7:59:23 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## <span data-ttu-id="d5fbf-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d5fbf-137">PARAMETERS</span></span>

### <span data-ttu-id="d5fbf-138">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="d5fbf-138">-DisplayError</span></span>

<span data-ttu-id="d5fbf-139">Indica que esse cmdlet exibe erros na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-139">Indicates that this cmdlet displays errors at the command line.</span></span> <span data-ttu-id="d5fbf-140">Esse parâmetro raramente é usado, mas pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-List` comando e as expressões não parecerem estar funcionando.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-140">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and the expressions do not appear to be working.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5fbf-141">-Expandir</span><span class="sxs-lookup"><span data-stu-id="d5fbf-141">-Expand</span></span>

<span data-ttu-id="d5fbf-142">Especifica o objeto de coleção formatado, bem como os objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-142">Specifies the formatted collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="d5fbf-143">Este parâmetro é projetado para formatar objetos que dão suporte à interface ICollection (System. Collections).</span><span class="sxs-lookup"><span data-stu-id="d5fbf-143">This parameter is designed to format objects that support the ICollection (System.Collections) interface.</span></span> <span data-ttu-id="d5fbf-144">O valor padrão é EnumOnly.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-144">The default value is EnumOnly.</span></span> <span data-ttu-id="d5fbf-145">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="d5fbf-145">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d5fbf-146">EnumOnly.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-146">EnumOnly.</span></span> <span data-ttu-id="d5fbf-147">Exibe as propriedades dos objetos contidos na coleção.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-147">Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="d5fbf-148">CoreOnly.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-148">CoreOnly.</span></span> <span data-ttu-id="d5fbf-149">Exibe as propriedades do objeto da coleção.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-149">Displays the properties of the collection object.</span></span>
- <span data-ttu-id="d5fbf-150">Both:</span><span class="sxs-lookup"><span data-stu-id="d5fbf-150">Both.</span></span> <span data-ttu-id="d5fbf-151">Exibe as propriedades do objeto da coleção e também as propriedades dos objetos contidos na coleção.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-151">Displays the properties of the collection object and the properties of objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5fbf-152">-Force</span><span class="sxs-lookup"><span data-stu-id="d5fbf-152">-Force</span></span>

<span data-ttu-id="d5fbf-153">Indica que esse cmdlet exibe todas as informações de erro.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-153">Indicates that this cmdlet displays all of the error information.</span></span> <span data-ttu-id="d5fbf-154">Use com o parâmetro **DisplayError** ou **exerror** .</span><span class="sxs-lookup"><span data-stu-id="d5fbf-154">Use with the **DisplayError** or **ShowError** parameter.</span></span> <span data-ttu-id="d5fbf-155">Por padrão, quando um objeto de erro é gravado para os fluxos de erro ou de exibição, apenas algumas das informações de erro são exibidas.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-155">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5fbf-156">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="d5fbf-156">-GroupBy</span></span>

<span data-ttu-id="d5fbf-157">Especifica a saída em grupos com base em um valor ou propriedade compartilhada.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-157">Specifies the output in groups based on a shared property or value.</span></span> <span data-ttu-id="d5fbf-158">Insira uma expressão ou uma propriedade da saída.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-158">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="d5fbf-159">O valor do parâmetro **GroupBy** pode ser uma nova propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-159">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="d5fbf-160">A propriedade calculada pode ser um bloco de script ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-160">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="d5fbf-161">Os pares de chave-valor válidos são:</span><span class="sxs-lookup"><span data-stu-id="d5fbf-161">Valid key-value pairs are:</span></span>

- <span data-ttu-id="d5fbf-162">Nome (ou rótulo)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="d5fbf-162">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="d5fbf-163">Expressão- `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="d5fbf-163">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="d5fbf-164">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="d5fbf-164">FormatString - `<string>`</span></span>

<span data-ttu-id="d5fbf-165">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="d5fbf-165">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5fbf-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d5fbf-166">-InputObject</span></span>

<span data-ttu-id="d5fbf-167">Especifica os objetos a serem formatados.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-167">Specifies the objects to be formatted.</span></span> <span data-ttu-id="d5fbf-168">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-168">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="d5fbf-169">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="d5fbf-169">-Property</span></span>

<span data-ttu-id="d5fbf-170">Especifica as propriedades do objeto que aparecem na exibição e a ordem em que aparecem.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-170">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="d5fbf-171">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-171">Wildcards are permitted.</span></span>

<span data-ttu-id="d5fbf-172">Se você omitir esse parâmetro, as propriedades a serem exibidas dependerão do objeto sendo exibido.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-172">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="d5fbf-173">O nome do parâmetro "Property" é opcional.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-173">The parameter name "Property" is optional.</span></span> <span data-ttu-id="d5fbf-174">Você não pode usar os parâmetros **Property** e **View** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-174">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="d5fbf-175">O valor do parâmetro **Property** pode ser uma nova propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-175">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="d5fbf-176">A propriedade calculada pode ser um bloco de script ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-176">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="d5fbf-177">Os pares de chave-valor válidos são:</span><span class="sxs-lookup"><span data-stu-id="d5fbf-177">Valid key-value pairs are:</span></span>

- <span data-ttu-id="d5fbf-178">Nome (ou rótulo)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="d5fbf-178">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="d5fbf-179">Expressão- `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="d5fbf-179">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="d5fbf-180">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="d5fbf-180">FormatString - `<string>`</span></span>

<span data-ttu-id="d5fbf-181">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="d5fbf-181">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d5fbf-182">-Erro</span><span class="sxs-lookup"><span data-stu-id="d5fbf-182">-ShowError</span></span>

<span data-ttu-id="d5fbf-183">Indica que o cmdlet envia erros por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-183">Indicates that the cmdlet sends errors through the pipeline.</span></span> <span data-ttu-id="d5fbf-184">Esse parâmetro raramente é usado, mas pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-List` comando e as expressões não parecerem estar funcionando.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-184">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and the expressions do not appear to be working.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5fbf-185">-Exibição</span><span class="sxs-lookup"><span data-stu-id="d5fbf-185">-View</span></span>

<span data-ttu-id="d5fbf-186">Especifica o nome de um formato de lista ou exibição alternativa.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-186">Specifies the name of an alternate list format or view.</span></span> <span data-ttu-id="d5fbf-187">Você não pode usar os parâmetros **Property** e **View** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-187">You cannot use the **Property** and **View** parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5fbf-188">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d5fbf-188">CommonParameters</span></span>

<span data-ttu-id="d5fbf-189">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-189">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d5fbf-190">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d5fbf-190">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d5fbf-191">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d5fbf-191">INPUTS</span></span>

### <span data-ttu-id="d5fbf-192">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="d5fbf-192">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="d5fbf-193">Você pode canalizar qualquer objeto para `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="d5fbf-193">You can pipe any object to `Format-List`.</span></span>

## <span data-ttu-id="d5fbf-194">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d5fbf-194">OUTPUTS</span></span>

### <span data-ttu-id="d5fbf-195">Microsoft. PowerShell. Commands. Internal. Format</span><span class="sxs-lookup"><span data-stu-id="d5fbf-195">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="d5fbf-196">`Format-List` Retorna os objetos de formato que representam a lista.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-196">`Format-List` returns the format objects that represent the list.</span></span>

## <span data-ttu-id="d5fbf-197">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d5fbf-197">NOTES</span></span>

<span data-ttu-id="d5fbf-198">Você também pode se referir a Format-List por seu alias interno, FL.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-198">You can also refer to Format-List by its built-in alias, FL.</span></span> <span data-ttu-id="d5fbf-199">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="d5fbf-199">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="d5fbf-200">Os cmdlets de formato, como `Format-List` , organizam os dados a serem exibidos, mas não os exibem.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-200">The format cmdlets, such as `Format-List`, arrange the data to be displayed but do not display it.</span></span>
<span data-ttu-id="d5fbf-201">Os dados são exibidos pelos recursos de saída do PowerShell e pelos cmdlets que contêm o verbo out (os cmdlets Out), como `Out-Host` ou `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="d5fbf-201">The data is displayed by the output features of PowerShell and by the cmdlets that contain the Out verb (the Out cmdlets), such as `Out-Host` or `Out-File`.</span></span>

<span data-ttu-id="d5fbf-202">Se você não usar um cmdlet de formato, o PowerShell aplicará esse formato padrão a cada objeto exibido.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-202">If you do not use a format cmdlet, PowerShell applies that default format for each object that it displays.</span></span>

<span data-ttu-id="d5fbf-203">O parâmetro **GroupBy** pressupõe que os objetos são classificados.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-203">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="d5fbf-204">Use Sort-Object antes `Format-List` de usar para agrupar os objetos.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-204">Use Sort-Object before using `Format-List` to group the objects.</span></span>

<span data-ttu-id="d5fbf-205">O parâmetro **View** permite especificar um formato alternativo para a tabela.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-205">The **View** parameter lets you specify an alternate format for the table.</span></span> <span data-ttu-id="d5fbf-206">Você pode usar os modos de exibição definidos nos `*.format.PS1XML` arquivos no diretório do PowerShell ou pode criar seus próprios modos de exibição em novos arquivos ps1xml e usar o cmdlet Update-FormatData para incluí-los no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-206">You can use the views defined in the `*.format.PS1XML` files in the PowerShell directory, or you can create your own views in new PS1XML files and use the Update-FormatData cmdlet to include them in PowerShell.</span></span>

<span data-ttu-id="d5fbf-207">O modo de exibição alternativo para o parâmetro de **exibição** deve usar o formato de lista, caso contrário, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="d5fbf-207">The alternate view for the **View** parameter must use the list format, otherwise, the command fails.</span></span> <span data-ttu-id="d5fbf-208">Se a exibição alternativa for uma tabela, use `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="d5fbf-208">If the alternate view is a table, use `Format-Table`.</span></span> <span data-ttu-id="d5fbf-209">Se a exibição alternativa não for uma lista ou uma tabela, use `Format-Custom` .</span><span class="sxs-lookup"><span data-stu-id="d5fbf-209">If the alternate view is not a list or a table, use `Format-Custom`.</span></span>

## <span data-ttu-id="d5fbf-210">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d5fbf-210">RELATED LINKS</span></span>

[<span data-ttu-id="d5fbf-211">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="d5fbf-211">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="d5fbf-212">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="d5fbf-212">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="d5fbf-213">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="d5fbf-213">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="d5fbf-214">Format-Table</span><span class="sxs-lookup"><span data-stu-id="d5fbf-214">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="d5fbf-215">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="d5fbf-215">Format-Wide</span></span>](Format-Wide.md)
