---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/join-string?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Join-String
ms.openlocfilehash: 96f4385c899a50a361fb6df55b40d1ce77225a5b
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103196292"
---
# <span data-ttu-id="8404b-102">Join-String</span><span class="sxs-lookup"><span data-stu-id="8404b-102">Join-String</span></span>

## <span data-ttu-id="8404b-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8404b-103">SYNOPSIS</span></span>
<span data-ttu-id="8404b-104">Combina objetos do pipeline em uma única cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8404b-104">Combines objects from the pipeline into a single string.</span></span>

## <span data-ttu-id="8404b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8404b-105">SYNTAX</span></span>

### <span data-ttu-id="8404b-106">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="8404b-106">Default (Default)</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-UseCulture] [-InputObject <PSObject[]>] [<CommonParameters>]
```

### <span data-ttu-id="8404b-107">SingleQuote</span><span class="sxs-lookup"><span data-stu-id="8404b-107">SingleQuote</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-SingleQuote] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="8404b-108">DoubleQuote</span><span class="sxs-lookup"><span data-stu-id="8404b-108">DoubleQuote</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-DoubleQuote] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="8404b-109">Formatar</span><span class="sxs-lookup"><span data-stu-id="8404b-109">Format</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-FormatString <String>] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="8404b-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8404b-110">DESCRIPTION</span></span>

<span data-ttu-id="8404b-111">O `Join-String` cmdlet une ou combina texto de objetos de pipeline em uma única cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8404b-111">The `Join-String` cmdlet joins, or combines, text from pipeline objects into a single string.</span></span>

<span data-ttu-id="8404b-112">Se nenhum parâmetro for especificado, os objetos de pipeline serão convertidos em uma cadeia de caracteres e Unidos com o separador padrão `$OFS` .</span><span class="sxs-lookup"><span data-stu-id="8404b-112">If no parameters are specified, the pipeline objects are converted to a string and joined with the default separator `$OFS`.</span></span>

<span data-ttu-id="8404b-113">Ao especificar um nome de propriedade, o valor da propriedade é convertido em uma cadeia de caracteres e Unido a uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8404b-113">By specifying a property name, the property's value is converted to a string and joined into a string.</span></span>

<span data-ttu-id="8404b-114">Em vez de um nome de propriedade, um bloco de script pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="8404b-114">Instead of a property name, a script block can be used.</span></span> <span data-ttu-id="8404b-115">O resultado do bloco de script é convertido em uma cadeia de caracteres antes de ser associado para formar o resultado.</span><span class="sxs-lookup"><span data-stu-id="8404b-115">The script block's result is converted to a string before it's joined to form the result.</span></span> <span data-ttu-id="8404b-116">Ele pode combinar o texto da propriedade de um objeto ou o resultado do objeto que foi convertido em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8404b-116">It can either combine the text of an object's property or the result of the object that was converted to a string.</span></span>

<span data-ttu-id="8404b-117">Esse cmdlet foi introduzido no PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="8404b-117">This cmdlet was introduced in PowerShell 6.2.</span></span>

## <span data-ttu-id="8404b-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8404b-118">EXAMPLES</span></span>

### <span data-ttu-id="8404b-119">Exemplo 1: unir nomes de diretório</span><span class="sxs-lookup"><span data-stu-id="8404b-119">Example 1: Join directory names</span></span>

<!-- markdownlint-disable MD038 -->
<span data-ttu-id="8404b-120">Este exemplo une nomes de diretório, encapsula a saída entre aspas duplas e separa os nomes de diretório com uma vírgula e um espaço ( `, ` ).</span><span class="sxs-lookup"><span data-stu-id="8404b-120">This example joins directory names, wraps the output in double-quotes, and separates the directory names with a comma and space (`, `).</span></span> <span data-ttu-id="8404b-121">A saída é um objeto de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8404b-121">The output is a string object.</span></span>

```powershell
Get-ChildItem -Directory C:\ | Join-String -Property Name -DoubleQuote -Separator ', '
```

```Output
"PerfLogs", "Program Files", "Program Files (x86)", "Users", "Windows"
```

<span data-ttu-id="8404b-122">`Get-ChildItem` usa o parâmetro **Directory** para obter todos os nomes de diretório para a `C:\` unidade.</span><span class="sxs-lookup"><span data-stu-id="8404b-122">`Get-ChildItem` uses the **Directory** parameter to get all the directory names for the `C:\` drive.</span></span>
<span data-ttu-id="8404b-123">Os objetos são enviados ao pipeline para `Join-String` .</span><span class="sxs-lookup"><span data-stu-id="8404b-123">The objects are sent down the pipeline to `Join-String`.</span></span> <span data-ttu-id="8404b-124">O parâmetro **Property** especifica os nomes de diretório.</span><span class="sxs-lookup"><span data-stu-id="8404b-124">The **Property** parameter specifies the directory names.</span></span> <span data-ttu-id="8404b-125">O parâmetro **DoubleQuote** encapsula os nomes de diretório com aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="8404b-125">The **DoubleQuote** parameter wraps the directory names with double-quote marks.</span></span>
<span data-ttu-id="8404b-126">O parâmetro **Separator** especifica a utilização de uma vírgula e um espaço ( `, ` ) para separar os nomes de diretório.</span><span class="sxs-lookup"><span data-stu-id="8404b-126">The **Separator** parameter specifies to use a comma and space (`, `) to separate the directory names.</span></span>

<span data-ttu-id="8404b-127">Os `Get-ChildItem` objetos são **System. IO. DirectoryInfo** e `Join-String` converte os objetos em **System. String**.</span><span class="sxs-lookup"><span data-stu-id="8404b-127">The `Get-ChildItem` objects are **System.IO.DirectoryInfo** and `Join-String` converts the objects to **System.String**.</span></span>

### <span data-ttu-id="8404b-128">Exemplo 2: usar uma subcadeia de caracteres de propriedade para unir nomes de diretório</span><span class="sxs-lookup"><span data-stu-id="8404b-128">Example 2: Use a property substring to join directory names</span></span>

<span data-ttu-id="8404b-129">Este exemplo usa um método substring para obter as primeiras quatro letras de nomes de diretório, encapsula a saída em aspas simples e separa os nomes de diretório com um ponto-e-vírgula ( `;` ).</span><span class="sxs-lookup"><span data-stu-id="8404b-129">This example uses a substring method to get the first four letters of directory names, wraps the output in single-quotes, and separates the directory names with a semicolon (`;`).</span></span>

```powershell
Get-ChildItem -Directory C:\ | Join-String -Property {$_.Name.SubString(0,4)} -SingleQuote -Separator ';'
```

```Output
'Perf';'Prog';'Prog';'User';'Wind'
```

<span data-ttu-id="8404b-130">`Get-ChildItem` usa o parâmetro **Directory** para obter todos os nomes de diretório para a `C:\` unidade.</span><span class="sxs-lookup"><span data-stu-id="8404b-130">`Get-ChildItem` uses the **Directory** parameter to get all the directory names for the `C:\` drive.</span></span>
<span data-ttu-id="8404b-131">Os objetos são enviados ao pipeline para `Join-String` .</span><span class="sxs-lookup"><span data-stu-id="8404b-131">The objects are sent down the pipeline to `Join-String`.</span></span>

<span data-ttu-id="8404b-132">O bloco de script de parâmetro de **Propriedade** usa variável automática ( `$_` ) para especificar a subcadeia de caracteres de propriedade de **nome** de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="8404b-132">The **Property** parameter script block uses automatic variable (`$_`) to specify each object's **Name** property substring.</span></span> <span data-ttu-id="8404b-133">A subcadeia de caracteres Obtém as primeiras quatro letras de cada nome de diretório.</span><span class="sxs-lookup"><span data-stu-id="8404b-133">The substring gets the first four letters of each directory name.</span></span> <span data-ttu-id="8404b-134">A subcadeia de caracteres especifica as posições de início e término do caractere.</span><span class="sxs-lookup"><span data-stu-id="8404b-134">The substring specifies the character start and end positions.</span></span> <span data-ttu-id="8404b-135">O parâmetro **SingleQuote** encapsula os nomes de diretório com marcas de aspas simples.</span><span class="sxs-lookup"><span data-stu-id="8404b-135">The **SingleQuote** parameter wraps the directory names with single-quote marks.</span></span> <span data-ttu-id="8404b-136">O parâmetro **Separator** especifica o uso de um ponto e vírgula ( `;` ) para separar os nomes de diretório.</span><span class="sxs-lookup"><span data-stu-id="8404b-136">The **Separator** parameter specifies to use a semicolon (`;`) to separate the directory names.</span></span>

<span data-ttu-id="8404b-137">Para obter mais informações sobre variáveis automáticas e subcadeias de caracteres, consulte [about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md) e [substring](/dotnet/api/system.string.substring).</span><span class="sxs-lookup"><span data-stu-id="8404b-137">For more information about automatic variables and substrings, see [about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md) and [Substring](/dotnet/api/system.string.substring).</span></span>

### <span data-ttu-id="8404b-138">Exemplo 3: exibir a saída de junção em uma linha separada</span><span class="sxs-lookup"><span data-stu-id="8404b-138">Example 3: Display join output on a separate line</span></span>

<span data-ttu-id="8404b-139">Este exemplo une nomes de serviço a cada serviço em uma linha separada e recuado por uma guia.</span><span class="sxs-lookup"><span data-stu-id="8404b-139">This example joins service names with each service on a separate line and indented by a tab.</span></span>

```powershell
Get-Service -Name se* | Join-String -Property Name -Separator "`r`n`t" -OutputPrefix "Services:`n`t"
```

```Output
Services:
    seclogon
    SecurityHealthService
    SEMgrSvc
    SENS
    Sense
    SensorDataService
    SensorService
    SensrSvc
    SessionEnv
```

<span data-ttu-id="8404b-140">`Get-Service` usa o parâmetro **Name** com para especificar serviços que começam com `se*` .</span><span class="sxs-lookup"><span data-stu-id="8404b-140">`Get-Service` uses the **Name** parameter with to specify services that begin with `se*`.</span></span> <span data-ttu-id="8404b-141">O asterisco ( `*` ) é um curinga para qualquer caractere.</span><span class="sxs-lookup"><span data-stu-id="8404b-141">The asterisk (`*`) is a wildcard for any character.</span></span>

<span data-ttu-id="8404b-142">Os objetos são enviados ao pipeline para o `Join-String` que usa o parâmetro **Property** para especificar os nomes de serviço.</span><span class="sxs-lookup"><span data-stu-id="8404b-142">The objects are sent down the pipeline to `Join-String` that uses the **Property** parameter to specify the service names.</span></span> <span data-ttu-id="8404b-143">O parâmetro **Separator** especifica três caracteres especiais que representam um retorno de carro ( `` `r `` ), nova linha ( `` `n `` ) e tabulação ( `` `t `` ).</span><span class="sxs-lookup"><span data-stu-id="8404b-143">The **Separator** parameter specifies three special characters that represent a carriage return (`` `r ``), newline (`` `n ``), and tab (`` `t ``).</span></span> <span data-ttu-id="8404b-144">O **OutputPrefix** insere um rótulo **Serviços:** com uma nova linha e uma guia antes da primeira linha de saída.</span><span class="sxs-lookup"><span data-stu-id="8404b-144">The **OutputPrefix** inserts a label **Services:** with a new line and tab before the first line of output.</span></span>

<span data-ttu-id="8404b-145">Para obter mais informações sobre caracteres especiais, consulte [about_special_characters](..//microsoft.powershell.core/about/about_special_characters.md).</span><span class="sxs-lookup"><span data-stu-id="8404b-145">For more information about special characters, see [about_Special_Characters](..//microsoft.powershell.core/about/about_special_characters.md).</span></span>

### <span data-ttu-id="8404b-146">Exemplo 4: criar uma definição de classe a partir de um objeto</span><span class="sxs-lookup"><span data-stu-id="8404b-146">Example 4: Create a class definition from an object</span></span>

<span data-ttu-id="8404b-147">Este exemplo gera uma definição de classe do PowerShell usando um objeto existente como modelo.</span><span class="sxs-lookup"><span data-stu-id="8404b-147">This example generates a PowerShell class definition using an existing object as a template.</span></span>

<span data-ttu-id="8404b-148">Este exemplo de código usa nivelamento para reduzir o tamanho da linha e melhorar a legibilidade.</span><span class="sxs-lookup"><span data-stu-id="8404b-148">This code sample uses splatting to reduce the line length and improve readability.</span></span> <span data-ttu-id="8404b-149">Para obter mais informações, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="8404b-149">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

```powershell
$obj = [pscustomobject] @{Name = "Joe"; Age = 42}
$parms = @{
  Property = "Name"
  FormatString = '  ${0}'
  OutputPrefix = "class {`n"
  OutputSuffix = "`n}`n"
  Separator = "`n"
}
$obj.PSObject.Properties | Join-String @parms
```

```Output
class {
  $Name
  $Age
}
```

## <span data-ttu-id="8404b-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8404b-150">PARAMETERS</span></span>

### <span data-ttu-id="8404b-151">-DoubleQuote</span><span class="sxs-lookup"><span data-stu-id="8404b-151">-DoubleQuote</span></span>

<span data-ttu-id="8404b-152">Encapsula o valor da cadeia de caracteres de cada objeto de pipeline em aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="8404b-152">Wraps the string value of each pipeline object in double-quotes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DoubleQuote
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8404b-153">-FormatString</span><span class="sxs-lookup"><span data-stu-id="8404b-153">-FormatString</span></span>

<span data-ttu-id="8404b-154">Uma cadeia de caracteres de formato que especifica como cada item deve ser formatado.</span><span class="sxs-lookup"><span data-stu-id="8404b-154">A format string that specifies how each item should be formatted.</span></span>

```yaml
Type: System.String
Parameter Sets: Format
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8404b-155">-InputObject</span><span class="sxs-lookup"><span data-stu-id="8404b-155">-InputObject</span></span>

<span data-ttu-id="8404b-156">Especifica o texto a ser Unido.</span><span class="sxs-lookup"><span data-stu-id="8404b-156">Specifies the text to be joined.</span></span> <span data-ttu-id="8404b-157">Insira uma variável que contenha o texto ou digite um comando ou uma expressão que obtenha os objetos para ingressar em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8404b-157">Enter a variable that contains the text, or type a command or expression that gets the objects to join into strings.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8404b-158">-OutputPrefix</span><span class="sxs-lookup"><span data-stu-id="8404b-158">-OutputPrefix</span></span>

<span data-ttu-id="8404b-159">Texto que é inserido antes da cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="8404b-159">Text that's inserted before the output string.</span></span> <span data-ttu-id="8404b-160">A cadeia de caracteres pode conter caracteres especiais, como retorno de carro ( `` `r `` ), nova linha ( `` `n `` ) e tabulação ( `` `t `` ).</span><span class="sxs-lookup"><span data-stu-id="8404b-160">The string can contain special characters such as carriage return (`` `r ``), newline (`` `n ``), and tab (`` `t ``).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: op

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8404b-161">-OutputSuffix</span><span class="sxs-lookup"><span data-stu-id="8404b-161">-OutputSuffix</span></span>

<span data-ttu-id="8404b-162">O texto que é anexado à cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="8404b-162">Text that's appended to the output string.</span></span> <span data-ttu-id="8404b-163">A cadeia de caracteres pode conter caracteres especiais, como retorno de carro ( `` `r `` ), nova linha ( `` `n `` ) e tabulação ( `` `t `` ).</span><span class="sxs-lookup"><span data-stu-id="8404b-163">The string can contain special characters such as carriage return (`` `r ``), newline (`` `n ``), and tab (`` `t ``).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8404b-164">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="8404b-164">-Property</span></span>

<span data-ttu-id="8404b-165">O nome de uma propriedade ou uma expressão de propriedade que projetará o objeto de pipeline em texto.</span><span class="sxs-lookup"><span data-stu-id="8404b-165">The name of a property, or a property expression, that will project the pipeline object to text.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.PSPropertyExpression
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8404b-166">-Separador</span><span class="sxs-lookup"><span data-stu-id="8404b-166">-Separator</span></span>

<span data-ttu-id="8404b-167">Texto ou caracteres como uma vírgula ou ponto e vírgula que é inserido entre o texto de cada objeto de pipeline.</span><span class="sxs-lookup"><span data-stu-id="8404b-167">Text or characters such as a comma or semicolon that's inserted between the text for each pipeline object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8404b-168">-SingleQuote</span><span class="sxs-lookup"><span data-stu-id="8404b-168">-SingleQuote</span></span>

<span data-ttu-id="8404b-169">Encapsula o valor da cadeia de caracteres de cada objeto de pipeline entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="8404b-169">Wraps the string value of each pipeline object in single quotes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SingleQuote
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8404b-170">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="8404b-170">-UseCulture</span></span>

<span data-ttu-id="8404b-171">Usa o separador de lista para a cultura atual como o delimitador de item.</span><span class="sxs-lookup"><span data-stu-id="8404b-171">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="8404b-172">Para localizar o separador de lista para uma cultura, use o seguinte comando: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="8404b-172">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8404b-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8404b-173">CommonParameters</span></span>

<span data-ttu-id="8404b-174">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8404b-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8404b-175">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8404b-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8404b-176">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8404b-176">INPUTS</span></span>

### <span data-ttu-id="8404b-177">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="8404b-177">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="8404b-178">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8404b-178">OUTPUTS</span></span>

### <span data-ttu-id="8404b-179">System.String</span><span class="sxs-lookup"><span data-stu-id="8404b-179">System.String</span></span>

## <span data-ttu-id="8404b-180">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8404b-180">NOTES</span></span>

## <span data-ttu-id="8404b-181">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8404b-181">RELATED LINKS</span></span>

[<span data-ttu-id="8404b-182">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="8404b-182">about_Automatic_Variables</span></span>](../microsoft.powershell.core/about/about_automatic_variables.md)

[<span data-ttu-id="8404b-183">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="8404b-183">about_Special_Characters</span></span>](..//microsoft.powershell.core/about/about_special_characters.md)

[<span data-ttu-id="8404b-184">Subcadeia</span><span class="sxs-lookup"><span data-stu-id="8404b-184">Substring</span></span>](/dotnet/api/system.string.substring)

