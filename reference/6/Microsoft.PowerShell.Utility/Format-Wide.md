---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-wide?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Wide
ms.openlocfilehash: 820835065e73cdabb07e47b238041d0b8e375d2f
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195172"
---
# <span data-ttu-id="3cf3a-103">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="3cf3a-103">Format-Wide</span></span>

## <span data-ttu-id="3cf3a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3cf3a-104">SYNOPSIS</span></span>
<span data-ttu-id="3cf3a-105">Formata objetos como uma tabela ampla que exibe apenas uma propriedade de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-105">Formats objects as a wide table that displays only one property of each object.</span></span>

## <span data-ttu-id="3cf3a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3cf3a-106">SYNTAX</span></span>

```
Format-Wide [[-Property] <Object>] [-AutoSize] [-Column <int>] [-GroupBy <Object>] [-View <string>]
  [-ShowError] [-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>]
  [<CommonParameters>]
```

## <span data-ttu-id="3cf3a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3cf3a-107">DESCRIPTION</span></span>

<span data-ttu-id="3cf3a-108">O `Format-Wide` cmdlet formata objetos como uma tabela larga que exibe apenas uma propriedade de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-108">The `Format-Wide` cmdlet formats objects as a wide table that displays only one property of each object.</span></span> <span data-ttu-id="3cf3a-109">Você pode usar o parâmetro **Property** para determinar qual propriedade é exibida.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-109">You can use the **Property** parameter to determine which property is displayed.</span></span>

## <span data-ttu-id="3cf3a-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3cf3a-110">EXAMPLES</span></span>

### <span data-ttu-id="3cf3a-111">Exemplo 1: Formatar nomes de arquivos no diretório atual</span><span class="sxs-lookup"><span data-stu-id="3cf3a-111">Example 1: Format names of files in the current directory</span></span>

<span data-ttu-id="3cf3a-112">Esse comando exibe os nomes dos arquivos no diretório atual em três colunas na tela.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-112">This command displays the names of files in the current directory in three columns across the screen.</span></span>

```powershell
Get-ChildItem | Format-Wide -Column 3
```

<span data-ttu-id="3cf3a-113">O cmdlet Get-ChildItem obtém os objetos que representam cada arquivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-113">The Get-ChildItem cmdlet gets objects representing each file in the directory.</span></span> <span data-ttu-id="3cf3a-114">O operador de pipeline (|) passa os objetos de arquivo por meio do pipeline para `Format-Wide` , que os formata para saída.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-114">The pipeline operator (|) passes the file objects through the pipeline to `Format-Wide`, which formats them for output.</span></span> <span data-ttu-id="3cf3a-115">O parâmetro **Column** especifica o número de colunas.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-115">The **Column** parameter specifies the number of columns.</span></span>

### <span data-ttu-id="3cf3a-116">Exemplo 2: Formatar nomes de chaves do registro</span><span class="sxs-lookup"><span data-stu-id="3cf3a-116">Example 2: Format names of registry keys</span></span>

<span data-ttu-id="3cf3a-117">Esse comando exibe os nomes das chaves do registro na chave HKEY_CURRENT_USER\Software\Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-117">This command displays the names of registry keys in the HKEY_CURRENT_USER\Software\Microsoft key.</span></span>

```powershell
Get-ChildItem HKCU:\software\microsoft | Format-Wide -Property pschildname -AutoSize
```

<span data-ttu-id="3cf3a-118">O cmdlet Get-ChildItem obtém os objetos que representam as chaves.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-118">The Get-ChildItem cmdlet gets objects representing the keys.</span></span> <span data-ttu-id="3cf3a-119">O caminho é especificado como HKCU:, uma das unidades expostas pelo provedor de registro do PowerShell, seguido pelo caminho da chave.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-119">The path is specified as HKCU:, one of the drives exposed by the PowerShell Registry provider, followed by the key path.</span></span> <span data-ttu-id="3cf3a-120">O operador de pipeline (|) passa os objetos de chave do registro por meio do pipeline para `Format-Wide` , que os formata para saída.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-120">The pipeline operator (|) passes the registry key objects through the pipeline to `Format-Wide`, which formats them for output.</span></span> <span data-ttu-id="3cf3a-121">O parâmetro **Property** especifica o nome da propriedade e o parâmetro **AutoSize** ajusta as colunas para facilitar a leitura.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-121">The **Property** parameter specifies the name of the property, and the **AutoSize** parameter adjusts the columns for readability.</span></span>

### <span data-ttu-id="3cf3a-122">Exemplo 3: Solucionando problemas de erros de formato</span><span class="sxs-lookup"><span data-stu-id="3cf3a-122">Example 3: Troubleshooting format errors</span></span>

<span data-ttu-id="3cf3a-123">Os exemplos a seguir mostram os resultados da adição dos parâmetros **DisplayError** ou **exerror** com uma expressão.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-123">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
PS /> Get-Date | Format-Wide { $_ / $null } -DisplayError


#ERR

PS /> Get-Date | Format-Wide { $_ / $null } -ShowError


Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 8:18:01 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## <span data-ttu-id="3cf3a-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3cf3a-124">PARAMETERS</span></span>

### <span data-ttu-id="3cf3a-125">-AutoSize</span><span class="sxs-lookup"><span data-stu-id="3cf3a-125">-AutoSize</span></span>

<span data-ttu-id="3cf3a-126">Ajusta o tamanho da coluna e o número de colunas com base na largura dos dados.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-126">Adjusts the column size and number of columns based on the width of the data.</span></span> <span data-ttu-id="3cf3a-127">Por padrão, o número de colunas e seu tamanho são determinados pelo modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-127">By default, the column size and number are determined by the view.</span></span> <span data-ttu-id="3cf3a-128">Você não pode usar os parâmetros **AutoSize** e **Column** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-128">You cannot use the **AutoSize** and **Column** parameters in the same command.</span></span>

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

### <span data-ttu-id="3cf3a-129">-Coluna</span><span class="sxs-lookup"><span data-stu-id="3cf3a-129">-Column</span></span>

<span data-ttu-id="3cf3a-130">Especifica o número de colunas a exibir.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-130">Specifies the number of columns in the display.</span></span> <span data-ttu-id="3cf3a-131">Você não pode usar os parâmetros **AutoSize** e **Column** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-131">You cannot use the **AutoSize** and **Column** parameters in the same command.</span></span>

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

### <span data-ttu-id="3cf3a-132">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="3cf3a-132">-DisplayError</span></span>

<span data-ttu-id="3cf3a-133">Exibe eventuais erros na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-133">Displays errors at the command line.</span></span> <span data-ttu-id="3cf3a-134">Esse parâmetro raramente é usado, mas pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-Wide` comando e as expressões não parecerem estar funcionando.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-134">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Wide` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="3cf3a-135">-Expandir</span><span class="sxs-lookup"><span data-stu-id="3cf3a-135">-Expand</span></span>

<span data-ttu-id="3cf3a-136">Formata o objeto da coleção, bem como os objetos presentes na coleção.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-136">Formats the collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="3cf3a-137">Este parâmetro é projetado para formatar objetos que dão suporte à interface ICollection (System. Collections).</span><span class="sxs-lookup"><span data-stu-id="3cf3a-137">This parameter is designed to format objects that support the ICollection (System.Collections) interface.</span></span> <span data-ttu-id="3cf3a-138">O valor padrão é **EnumOnly** .</span><span class="sxs-lookup"><span data-stu-id="3cf3a-138">The default value is **EnumOnly** .</span></span>

<span data-ttu-id="3cf3a-139">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="3cf3a-139">Valid values are:</span></span>

- <span data-ttu-id="3cf3a-140">EnumOnly: exibe as propriedades dos objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-140">EnumOnly: Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="3cf3a-141">CoreOnly: exibe as propriedades do objeto de coleção.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-141">CoreOnly: Displays the properties of the collection object.</span></span>
- <span data-ttu-id="3cf3a-142">Ambos: exibe as propriedades do objeto de coleção e as propriedades de objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-142">Both: Displays the properties of the collection object and the properties of objects in the collection.</span></span>

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

### <span data-ttu-id="3cf3a-143">-Force</span><span class="sxs-lookup"><span data-stu-id="3cf3a-143">-Force</span></span>

<span data-ttu-id="3cf3a-144">Indica que esse cmdlet substitui as restrições que impedem o sucesso do comando, apenas para que as alterações não comprometam a segurança.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-144">Indicates that this cmdlet overrides restrictions that prevent the command from succeeding, just so the changes do not compromise security.</span></span> <span data-ttu-id="3cf3a-145">Por exemplo, o **Force** substituirá o atributo somente leitura ou criar diretórios para concluir um caminho de arquivo, mas não tentará alterar permissões de arquivo.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-145">For example, **Force** will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.</span></span>

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

### <span data-ttu-id="3cf3a-146">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="3cf3a-146">-GroupBy</span></span>

<span data-ttu-id="3cf3a-147">Formata a saída em grupos com base em uma propriedade ou valor compartilhado.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-147">Formats the output in groups based on a shared property or value.</span></span> <span data-ttu-id="3cf3a-148">Insira uma expressão ou uma propriedade da saída.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-148">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="3cf3a-149">O valor do parâmetro **GroupBy** pode ser uma nova propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-149">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="3cf3a-150">A propriedade calculada pode ser um bloco de script ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-150">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="3cf3a-151">Os pares de chave-valor válidos são:</span><span class="sxs-lookup"><span data-stu-id="3cf3a-151">Valid key-value pairs are:</span></span>

- <span data-ttu-id="3cf3a-152">Nome (ou rótulo)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="3cf3a-152">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="3cf3a-153">Expressão- `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="3cf3a-153">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="3cf3a-154">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="3cf3a-154">FormatString - `<string>`</span></span>

<span data-ttu-id="3cf3a-155">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="3cf3a-155">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="3cf3a-156">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3cf3a-156">-InputObject</span></span>

<span data-ttu-id="3cf3a-157">Especifica os objetos a serem formatados.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-157">Specifies the objects to format.</span></span> <span data-ttu-id="3cf3a-158">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-158">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="3cf3a-159">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="3cf3a-159">-Property</span></span>

<span data-ttu-id="3cf3a-160">Especifica as propriedades do objeto que aparecem na exibição e a ordem em que aparecem.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-160">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="3cf3a-161">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-161">Wildcards are permitted.</span></span>

<span data-ttu-id="3cf3a-162">Se você omitir esse parâmetro, as propriedades a serem exibidas dependerão do objeto sendo exibido.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-162">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="3cf3a-163">O nome do parâmetro "Property" é opcional.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-163">The parameter name "Property" is optional.</span></span> <span data-ttu-id="3cf3a-164">Você não pode usar os parâmetros **Property** e **View** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-164">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="3cf3a-165">O valor do parâmetro **Property** pode ser uma nova propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-165">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="3cf3a-166">A propriedade calculada pode ser um bloco de script ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-166">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="3cf3a-167">Os pares de chave-valor válidos são:</span><span class="sxs-lookup"><span data-stu-id="3cf3a-167">Valid key-value pairs are:</span></span>

- <span data-ttu-id="3cf3a-168">Expressão- `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="3cf3a-168">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="3cf3a-169">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="3cf3a-169">FormatString - `<string>`</span></span>

<span data-ttu-id="3cf3a-170">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="3cf3a-170">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3cf3a-171">-Erro</span><span class="sxs-lookup"><span data-stu-id="3cf3a-171">-ShowError</span></span>

<span data-ttu-id="3cf3a-172">Envia erros por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-172">Sends errors through the pipeline.</span></span> <span data-ttu-id="3cf3a-173">Esse parâmetro raramente é usado, mas pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-Wide` comando e as expressões não parecerem estar funcionando.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-173">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Wide` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="3cf3a-174">-Exibição</span><span class="sxs-lookup"><span data-stu-id="3cf3a-174">-View</span></span>

<span data-ttu-id="3cf3a-175">Especifica o nome de um formato ou exibição de tabela alternativa.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-175">Specifies the name of an alternate table format or view.</span></span> <span data-ttu-id="3cf3a-176">Você não pode usar os parâmetros **Property** e **View** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-176">You cannot use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="3cf3a-177">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3cf3a-177">CommonParameters</span></span>

<span data-ttu-id="3cf3a-178">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-178">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3cf3a-179">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3cf3a-179">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3cf3a-180">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3cf3a-180">INPUTS</span></span>

### <span data-ttu-id="3cf3a-181">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="3cf3a-181">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="3cf3a-182">Você pode canalizar qualquer objeto para `Format-Wide` .</span><span class="sxs-lookup"><span data-stu-id="3cf3a-182">You can pipe any object to `Format-Wide`.</span></span>

## <span data-ttu-id="3cf3a-183">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3cf3a-183">OUTPUTS</span></span>

### <span data-ttu-id="3cf3a-184">Microsoft. PowerShell. Commands. Internal. Format</span><span class="sxs-lookup"><span data-stu-id="3cf3a-184">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="3cf3a-185">`Format-Wide` retorna objetos de formato que representam a tabela.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-185">`Format-Wide` returns format objects that represent the table.</span></span>

## <span data-ttu-id="3cf3a-186">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3cf3a-186">NOTES</span></span>

<span data-ttu-id="3cf3a-187">Você também pode consultar `Format-Wide` por seu alias interno, `fw` .</span><span class="sxs-lookup"><span data-stu-id="3cf3a-187">You can also refer to `Format-Wide` by its built-in alias, `fw`.</span></span> <span data-ttu-id="3cf3a-188">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="3cf3a-188">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="3cf3a-189">O parâmetro **GroupBy** pressupõe que os objetos são classificados.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-189">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="3cf3a-190">Use `Sort-Object` antes `Format-Custom` de usar o para agrupar os objetos.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-190">Use `Sort-Object` before using `Format-Custom` to group the objects.</span></span>

<span data-ttu-id="3cf3a-191">O parâmetro **View** permite especificar um formato alternativo para a tabela.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-191">The **View** parameter lets you specify an alternate format for the table.</span></span> <span data-ttu-id="3cf3a-192">Você pode usar as exibições definidas nos `*.format.PS1XML` arquivos no diretório do PowerShell ou pode criar suas próprias exibições em novos arquivos ps1xml e usar o `Update-FormatData` cmdlet para incluí-las no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-192">You can use the views defined in the `*.format.PS1XML` files in the PowerShell directory or you can create your own views in new PS1XML files and use the `Update-FormatData` cmdlet to include them in PowerShell.</span></span>

<span data-ttu-id="3cf3a-193">A exibição alternativa para o parâmetro de **exibição** deve usar o formato de tabela; caso contrário, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-193">The alternate view for the **View** parameter must use table format; if it does not, the command fails.</span></span> <span data-ttu-id="3cf3a-194">Se a exibição alternativa for uma lista, use `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="3cf3a-194">If the alternate view is a list, use `Format-List`.</span></span> <span data-ttu-id="3cf3a-195">Se o modo de exibição alternativo não é uma lista nem uma tabela, use o Format-Custom.</span><span class="sxs-lookup"><span data-stu-id="3cf3a-195">If the alternate view is neither a list nor a table, use Format-Custom.</span></span>

## <span data-ttu-id="3cf3a-196">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3cf3a-196">RELATED LINKS</span></span>

[<span data-ttu-id="3cf3a-197">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="3cf3a-197">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="3cf3a-198">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="3cf3a-198">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="3cf3a-199">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="3cf3a-199">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="3cf3a-200">Format-List</span><span class="sxs-lookup"><span data-stu-id="3cf3a-200">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="3cf3a-201">Format-Table</span><span class="sxs-lookup"><span data-stu-id="3cf3a-201">Format-Table</span></span>](Format-Table.md)
