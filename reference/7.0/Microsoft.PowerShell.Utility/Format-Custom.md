---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-custom?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Custom
ms.openlocfilehash: f78f562aba1b6cbbc2abe404c8db508de1525f5f
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195170"
---
# <span data-ttu-id="a0bea-103">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="a0bea-103">Format-Custom</span></span>

## <span data-ttu-id="a0bea-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a0bea-104">SYNOPSIS</span></span>
<span data-ttu-id="a0bea-105">Usa um modo de exibição personalizado para formatar a saída.</span><span class="sxs-lookup"><span data-stu-id="a0bea-105">Uses a customized view to format the output.</span></span>

## <span data-ttu-id="a0bea-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a0bea-106">SYNTAX</span></span>

```
Format-Custom [[-Property] <Object[]>] [-Depth <Int32>] [-GroupBy <Object>] [-View <String>]
 [-ShowError] [-DisplayError] [-Force] [-Expand <String>] [-InputObject <PSObject>]
 [<CommonParameters>]
```

## <span data-ttu-id="a0bea-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a0bea-107">DESCRIPTION</span></span>

<span data-ttu-id="a0bea-108">O `Format-Custom` cmdlet formata a saída de um comando conforme definido em uma exibição alternativa.</span><span class="sxs-lookup"><span data-stu-id="a0bea-108">The `Format-Custom` cmdlet formats the output of a command as defined in an alternate view.</span></span>
<span data-ttu-id="a0bea-109">`Format-Custom` foi projetado para exibir modos de exibição que não são apenas tabelas ou apenas listas.</span><span class="sxs-lookup"><span data-stu-id="a0bea-109">`Format-Custom` is designed to display views that are not just tables or just lists.</span></span> <span data-ttu-id="a0bea-110">Você pode usar os modos de exibição definidos no PowerShell ou pode criar seus próprios modos de exibição em um novo `format.ps1xml` arquivo e usar o `Update-FormatData` cmdlet para adicioná-los ao PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0bea-110">You can use the views defined in PowerShell, or you can create your own views in a new `format.ps1xml` file and use the `Update-FormatData` cmdlet to add them to PowerShell.</span></span>

## <span data-ttu-id="a0bea-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a0bea-111">EXAMPLES</span></span>

### <span data-ttu-id="a0bea-112">Exemplo 1: Formatar a saída com uma exibição personalizada</span><span class="sxs-lookup"><span data-stu-id="a0bea-112">Example 1: Format output with a custom view</span></span>

```powershell
Get-Command Start-Transcript | Format-Custom -View MyView
```

<span data-ttu-id="a0bea-113">Esse comando formata informações sobre o `Start-Transcript` cmdlet no formato definido pelo modo de exibição MyView, uma exibição personalizada criada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="a0bea-113">This command formats information about the `Start-Transcript` cmdlet in the format defined by the MyView view, a custom view created by the user.</span></span> <span data-ttu-id="a0bea-114">Para executar esse comando com êxito, você deve primeiro criar um novo arquivo PS1XML, definir o modo de exibição **MyView** e, em seguida, usar o `Update-FormatData` comando para adicionar o arquivo PS1XML ao PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0bea-114">To run this command successfully, you must first create a new PS1XML file, define the **MyView** view, and then use the `Update-FormatData` command to add the PS1XML file to PowerShell.</span></span>

### <span data-ttu-id="a0bea-115">Exemplo 2: Formatar a saída com a exibição padrão</span><span class="sxs-lookup"><span data-stu-id="a0bea-115">Example 2: Format output with the default view</span></span>

```powershell
Get-Process Winlogon | Format-Custom
```

<span data-ttu-id="a0bea-116">Esse comando formata informações sobre o processo **Winlogon** em uma exibição personalizada alternativa.</span><span class="sxs-lookup"><span data-stu-id="a0bea-116">This command formats information about the **Winlogon** process in an alternate customized view.</span></span>
<span data-ttu-id="a0bea-117">Como o comando não usa o parâmetro **View** , o `Format-Custom` usa uma exibição personalizada padrão para formatar os dados.</span><span class="sxs-lookup"><span data-stu-id="a0bea-117">Because the command does not use the **View** parameter, `Format-Custom` uses a default custom view to format the data.</span></span>

### <span data-ttu-id="a0bea-118">Exemplo 3: Solucionando problemas de erros de formato</span><span class="sxs-lookup"><span data-stu-id="a0bea-118">Example 3: Troubleshooting format errors</span></span>

<span data-ttu-id="a0bea-119">Os exemplos a seguir mostram os resultados da adição dos parâmetros **DisplayError** ou **exerror** com uma expressão.</span><span class="sxs-lookup"><span data-stu-id="a0bea-119">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -DisplayError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  = #ERR
}


PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -ShowError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  =
}

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 8:01:04 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## <span data-ttu-id="a0bea-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a0bea-120">PARAMETERS</span></span>

### <span data-ttu-id="a0bea-121">-Profundidade</span><span class="sxs-lookup"><span data-stu-id="a0bea-121">-Depth</span></span>

<span data-ttu-id="a0bea-122">Especifica o número de colunas a exibir.</span><span class="sxs-lookup"><span data-stu-id="a0bea-122">Specifies the number of columns in the display.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0bea-123">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="a0bea-123">-DisplayError</span></span>

<span data-ttu-id="a0bea-124">Exibe eventuais erros na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="a0bea-124">Displays errors at the command line.</span></span> <span data-ttu-id="a0bea-125">Esse parâmetro raramente é usado, mas pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-Custom` comando e as expressões não parecerem estar funcionando.</span><span class="sxs-lookup"><span data-stu-id="a0bea-125">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="a0bea-126">-Expandir</span><span class="sxs-lookup"><span data-stu-id="a0bea-126">-Expand</span></span>

<span data-ttu-id="a0bea-127">Formata o objeto da coleção, bem como os objetos presentes na coleção.</span><span class="sxs-lookup"><span data-stu-id="a0bea-127">Formats the collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="a0bea-128">Esse parâmetro é projetado para formatar objetos que dão suporte à interface **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="a0bea-128">This parameter is designed to format objects that support the **System.Collections.ICollection** interface.</span></span> <span data-ttu-id="a0bea-129">O valor padrão é **EnumOnly** .</span><span class="sxs-lookup"><span data-stu-id="a0bea-129">The default value is **EnumOnly** .</span></span>

<span data-ttu-id="a0bea-130">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="a0bea-130">Valid values are:</span></span>

- <span data-ttu-id="a0bea-131">EnumOnly: exibe as propriedades dos objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="a0bea-131">EnumOnly: Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="a0bea-132">CoreOnly: exibe as propriedades do objeto de coleção.</span><span class="sxs-lookup"><span data-stu-id="a0bea-132">CoreOnly: Displays the properties of the collection object.</span></span>
- <span data-ttu-id="a0bea-133">Ambos: exibe as propriedades do objeto de coleção e os objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="a0bea-133">Both: Displays the properties of the collection object and the objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: EnumOnly
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0bea-134">-Force</span><span class="sxs-lookup"><span data-stu-id="a0bea-134">-Force</span></span>

<span data-ttu-id="a0bea-135">Faz com que o cmdlet exiba todas as informações de erro.</span><span class="sxs-lookup"><span data-stu-id="a0bea-135">Directs the cmdlet to display all of the error information.</span></span> <span data-ttu-id="a0bea-136">Use com os parâmetros **DisplayError** ou **exerror** .</span><span class="sxs-lookup"><span data-stu-id="a0bea-136">Use with the **DisplayError** or **ShowError** parameters.</span></span> <span data-ttu-id="a0bea-137">Por padrão, quando um objeto de erro é gravado para os fluxos de erro ou de exibição, apenas algumas das informações de erro são exibidas.</span><span class="sxs-lookup"><span data-stu-id="a0bea-137">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

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

### <span data-ttu-id="a0bea-138">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="a0bea-138">-GroupBy</span></span>

<span data-ttu-id="a0bea-139">Formata a saída em grupos com base em uma propriedade ou valor compartilhado.</span><span class="sxs-lookup"><span data-stu-id="a0bea-139">Formats the output in groups based on a shared property or value.</span></span> <span data-ttu-id="a0bea-140">Insira uma expressão ou uma propriedade da saída.</span><span class="sxs-lookup"><span data-stu-id="a0bea-140">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="a0bea-141">O valor do parâmetro **GroupBy** pode ser uma nova propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="a0bea-141">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="a0bea-142">A propriedade calculada pode ser um bloco de script ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="a0bea-142">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="a0bea-143">Os pares de chave-valor válidos são:</span><span class="sxs-lookup"><span data-stu-id="a0bea-143">Valid key-value pairs are:</span></span>

- <span data-ttu-id="a0bea-144">Nome (ou rótulo)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="a0bea-144">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="a0bea-145">Expressão- `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="a0bea-145">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="a0bea-146">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="a0bea-146">FormatString - `<string>`</span></span>

<span data-ttu-id="a0bea-147">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="a0bea-147">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="a0bea-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a0bea-148">-InputObject</span></span>

<span data-ttu-id="a0bea-149">Especifica os objetos a serem formatados.</span><span class="sxs-lookup"><span data-stu-id="a0bea-149">Specifies the objects to be formatted.</span></span> <span data-ttu-id="a0bea-150">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="a0bea-150">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="a0bea-151">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="a0bea-151">-Property</span></span>

<span data-ttu-id="a0bea-152">Especifica as propriedades do objeto que aparecem na exibição e a ordem em que aparecem.</span><span class="sxs-lookup"><span data-stu-id="a0bea-152">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="a0bea-153">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a0bea-153">Wildcards are permitted.</span></span>

<span data-ttu-id="a0bea-154">Se você omitir esse parâmetro, as propriedades a serem exibidas dependerão do objeto sendo exibido.</span><span class="sxs-lookup"><span data-stu-id="a0bea-154">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="a0bea-155">A **Propriedade** nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="a0bea-155">The parameter name **Property** is optional.</span></span> <span data-ttu-id="a0bea-156">Você não pode usar os parâmetros **Property** e **View** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="a0bea-156">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="a0bea-157">O valor do parâmetro **Property** pode ser uma nova propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="a0bea-157">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="a0bea-158">A propriedade calculada pode ser um bloco de script ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="a0bea-158">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="a0bea-159">Os pares de chave-valor válidos são:</span><span class="sxs-lookup"><span data-stu-id="a0bea-159">Valid key-value pairs are:</span></span>

- <span data-ttu-id="a0bea-160">Expressão- `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="a0bea-160">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="a0bea-161">Detalhado `<int32>`</span><span class="sxs-lookup"><span data-stu-id="a0bea-161">Depth - `<int32>`</span></span>

<span data-ttu-id="a0bea-162">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="a0bea-162">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="a0bea-163">-Erro</span><span class="sxs-lookup"><span data-stu-id="a0bea-163">-ShowError</span></span>

<span data-ttu-id="a0bea-164">Envia erros por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="a0bea-164">Sends errors through the pipeline.</span></span> <span data-ttu-id="a0bea-165">Esse parâmetro raramente é usado, mas pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-Custom` comando e as expressões não parecerem estar funcionando.</span><span class="sxs-lookup"><span data-stu-id="a0bea-165">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="a0bea-166">-Exibição</span><span class="sxs-lookup"><span data-stu-id="a0bea-166">-View</span></span>

<span data-ttu-id="a0bea-167">Especifica o nome de um formato ou exibição alternativo.</span><span class="sxs-lookup"><span data-stu-id="a0bea-167">Specifies the name of an alternate format or view.</span></span> <span data-ttu-id="a0bea-168">Se você omitir esse parâmetro, o `Format-Custom` usará uma exibição personalizada padrão.</span><span class="sxs-lookup"><span data-stu-id="a0bea-168">If you omit this parameter, `Format-Custom` uses a default custom view.</span></span> <span data-ttu-id="a0bea-169">Você não pode usar os parâmetros **Property** e **View** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="a0bea-169">You cannot use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="a0bea-170">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a0bea-170">CommonParameters</span></span>

<span data-ttu-id="a0bea-171">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a0bea-171">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a0bea-172">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a0bea-172">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a0bea-173">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a0bea-173">INPUTS</span></span>

### <span data-ttu-id="a0bea-174">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="a0bea-174">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="a0bea-175">Você pode canalizar qualquer objeto para `Format-Custom` .</span><span class="sxs-lookup"><span data-stu-id="a0bea-175">You can pipe any object to `Format-Custom`.</span></span>

## <span data-ttu-id="a0bea-176">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a0bea-176">OUTPUTS</span></span>

### <span data-ttu-id="a0bea-177">Microsoft. PowerShell. Commands. Internal. Format</span><span class="sxs-lookup"><span data-stu-id="a0bea-177">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="a0bea-178">`Format-Custom` Retorna os objetos de formato que representam a exibição.</span><span class="sxs-lookup"><span data-stu-id="a0bea-178">`Format-Custom` returns the format objects that represent the display.</span></span>

## <span data-ttu-id="a0bea-179">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a0bea-179">NOTES</span></span>

<span data-ttu-id="a0bea-180">`Format-Custom` foi projetado para exibir modos de exibição que não são apenas tabelas ou apenas listas.</span><span class="sxs-lookup"><span data-stu-id="a0bea-180">`Format-Custom` is designed to display views that are not just tables or just lists.</span></span> <span data-ttu-id="a0bea-181">Para exibir uma exibição de tabela alternativa, use `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="a0bea-181">To display an alternate table view, use `Format-Table`.</span></span> <span data-ttu-id="a0bea-182">Para exibir uma exibição de lista alternativa, use `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="a0bea-182">To display an alternate list view, use `Format-List`.</span></span>

<span data-ttu-id="a0bea-183">Você também pode consultar `Format-Custom` por seu alias interno, `fc` .</span><span class="sxs-lookup"><span data-stu-id="a0bea-183">You can also refer to `Format-Custom` by its built-in alias, `fc`.</span></span> <span data-ttu-id="a0bea-184">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="a0bea-184">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="a0bea-185">O parâmetro **GroupBy** pressupõe que os objetos são classificados.</span><span class="sxs-lookup"><span data-stu-id="a0bea-185">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="a0bea-186">Antes `Format-Custom` de usar o para agrupar os objetos, use `Sort-Object` para classificá-los.</span><span class="sxs-lookup"><span data-stu-id="a0bea-186">Before using `Format-Custom` to group the objects, use `Sort-Object` to sort them.</span></span>

## <span data-ttu-id="a0bea-187">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a0bea-187">RELATED LINKS</span></span>

[<span data-ttu-id="a0bea-188">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="a0bea-188">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="a0bea-189">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="a0bea-189">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="a0bea-190">Format-List</span><span class="sxs-lookup"><span data-stu-id="a0bea-190">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="a0bea-191">Format-Table</span><span class="sxs-lookup"><span data-stu-id="a0bea-191">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="a0bea-192">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="a0bea-192">Format-Wide</span></span>](Format-Wide.md)

[<span data-ttu-id="a0bea-193">Get-Process</span><span class="sxs-lookup"><span data-stu-id="a0bea-193">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)
