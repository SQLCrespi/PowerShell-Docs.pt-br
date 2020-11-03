---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-String
ms.openlocfilehash: 665a0ca8332c4052b59362c7947e408ba811c5f2
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "93195283"
---
# <span data-ttu-id="4cd42-103">ConvertFrom-String</span><span class="sxs-lookup"><span data-stu-id="4cd42-103">ConvertFrom-String</span></span>

## <span data-ttu-id="4cd42-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4cd42-104">SYNOPSIS</span></span>
<span data-ttu-id="4cd42-105">Extrai e analisa as propriedades estruturadas do conteúdo da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4cd42-105">Extracts and parses structured properties from string content.</span></span>

## <span data-ttu-id="4cd42-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4cd42-106">SYNTAX</span></span>

### <span data-ttu-id="4cd42-107">ByDelimiter (padrão)</span><span class="sxs-lookup"><span data-stu-id="4cd42-107">ByDelimiter (Default)</span></span>

```
ConvertFrom-String [-Delimiter <String>] [-PropertyNames <String[]>] [-InputObject] <String>
 [<CommonParameters>]
```

### <span data-ttu-id="4cd42-108">TemplateParsing</span><span class="sxs-lookup"><span data-stu-id="4cd42-108">TemplateParsing</span></span>

```
ConvertFrom-String [-TemplateFile <String[]>] [-TemplateContent <String[]>] [-IncludeExtent] [-UpdateTemplate]
 [-InputObject] <String> [<CommonParameters>]
```

## <span data-ttu-id="4cd42-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4cd42-109">DESCRIPTION</span></span>

<span data-ttu-id="4cd42-110">O cmdlet **ConvertFrom-String** extrai e analisa as propriedades estruturadas do conteúdo da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4cd42-110">The **ConvertFrom-String** cmdlet extracts and parses structured properties from string content.</span></span>
<span data-ttu-id="4cd42-111">Esse cmdlet gera um objeto analisando o texto de um fluxo de texto tradicional.</span><span class="sxs-lookup"><span data-stu-id="4cd42-111">This cmdlet generates an object by parsing text from a traditional text stream.</span></span>
<span data-ttu-id="4cd42-112">Para cada cadeia de caracteres no pipeline, o cmdlet divide a entrada por um delimitador ou uma expressão de análise e atribui nomes de propriedade a cada um dos elementos de divisão resultantes.</span><span class="sxs-lookup"><span data-stu-id="4cd42-112">For each string in the pipeline, the cmdlet splits the input by either a delimiter or a parse expression, and then assigns property names to each of the resulting split elements.</span></span>
<span data-ttu-id="4cd42-113">Você pode fornecer esses nomes de propriedade; Se você não fizer isso, eles serão gerados automaticamente para você.</span><span class="sxs-lookup"><span data-stu-id="4cd42-113">You can provide these property names; if you do not, they are automatically generated for you.</span></span>

<span data-ttu-id="4cd42-114">O conjunto de parâmetros padrão do cmdlet, **ByDelimiter** , é dividido exatamente no delimitador de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="4cd42-114">The cmdlet's default parameter set, **ByDelimiter** , splits exactly on the regular expression delimiter.</span></span>
<span data-ttu-id="4cd42-115">Ele não executa a correspondência de aspas ou a saída de delimitador conforme o `Import-Csv` cmdlet faz.</span><span class="sxs-lookup"><span data-stu-id="4cd42-115">It does not perform quote matching or delimiter escaping as the `Import-Csv` cmdlet does.</span></span>

<span data-ttu-id="4cd42-116">O conjunto de parâmetros alternativo do cmdlet, **TemplateParsing** , gera elementos dos grupos que são capturados por uma expressão regular.</span><span class="sxs-lookup"><span data-stu-id="4cd42-116">The cmdlet's alternate parameter set, **TemplateParsing** , generates elements from the groups that are captured by a regular expression.</span></span> <span data-ttu-id="4cd42-117">Para obter mais informações sobre expressões regulares, consulte [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4cd42-117">For more information on regular expressions, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span>

<span data-ttu-id="4cd42-118">Esse cmdlet dá suporte a dois modos: análise delimitada básica e análise automaticamente gerada por exemplo.</span><span class="sxs-lookup"><span data-stu-id="4cd42-118">This cmdlet supports two modes: basic delimited parsing, and automatically-generated, example-driven parsing.</span></span>

<span data-ttu-id="4cd42-119">A análise delimitada, por padrão, divide a entrada no espaço em branco e atribui nomes de propriedade aos grupos resultantes.</span><span class="sxs-lookup"><span data-stu-id="4cd42-119">Delimited parsing, by default, splits the input at white space, and assigns property names to the resulting groups.</span></span>

<span data-ttu-id="4cd42-120">Você pode personalizar o delimitador canalizando os `ConvertFrom-String` resultados em um dos `Format-*` cmdlets ou pode usar o parâmetro **delimitador** .</span><span class="sxs-lookup"><span data-stu-id="4cd42-120">You can customize the delimiter by piping the `ConvertFrom-String` results into one of the `Format-*` cmdlets, or you can use the **Delimiter** parameter.</span></span>

<span data-ttu-id="4cd42-121">O cmdlet também dá suporte à análise orientada por exemplo gerada automaticamente, com base no [FlashExtract, trabalho de pesquisa da Microsoft Research](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples/).</span><span class="sxs-lookup"><span data-stu-id="4cd42-121">The cmdlet also supports automatically-generated, example-driven parsing based on the [FlashExtract, research work by Microsoft Research](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples/).</span></span>

## <span data-ttu-id="4cd42-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4cd42-122">EXAMPLES</span></span>

### <span data-ttu-id="4cd42-123">Exemplo 1: gerar um objeto com nomes de propriedade padrão</span><span class="sxs-lookup"><span data-stu-id="4cd42-123">Example 1: Generate an object with default property names</span></span>

```powershell
"Hello World" | ConvertFrom-String
```

```Output
P1    P2
--    --
Hello World
```

<span data-ttu-id="4cd42-124">Esse comando gera um objeto com nomes de propriedade padrão, **P1** e **P2** .</span><span class="sxs-lookup"><span data-stu-id="4cd42-124">This command generates an object with default property names, **P1** and **P2** .</span></span>

### <span data-ttu-id="4cd42-125">Exemplo 1A: Conheça o objeto gerado</span><span class="sxs-lookup"><span data-stu-id="4cd42-125">Example 1A: Get to know the generated object</span></span>

<span data-ttu-id="4cd42-126">Esse comando gera um objeto com as propriedades **P1** , **P2** ; as duas propriedades são do tipo **cadeia de caracteres** , por padrão.</span><span class="sxs-lookup"><span data-stu-id="4cd42-126">This command generates one object with properties **P1** , **P2** ; both properties are of **String** type, by default.</span></span>

```powershell
"Hello World" | ConvertFrom-String | Get-Member
```

```Output

   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
P1          NoteProperty string P1=Hello
P2          NoteProperty string P2=World
```

### <span data-ttu-id="4cd42-127">Exemplo 2: gerar um objeto com nomes de propriedade padrão usando um delimitador</span><span class="sxs-lookup"><span data-stu-id="4cd42-127">Example 2: Generate an object with default property names using a delimiter</span></span>

<span data-ttu-id="4cd42-128">Esse comando gera um objeto com um domínio e um nome de usuário usando a barra invertida ( `\` ) como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="4cd42-128">This command generates an object with a domain and username using the backslash (`\`) as the delimiter.</span></span> <span data-ttu-id="4cd42-129">O caractere de barra invertida deve ter um escape com outra barra invertida ao usar expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="4cd42-129">The backslash character must be escaped with another backslash when using regular expressions.</span></span>

```powershell
"Contoso\Administrator" | ConvertFrom-String -Delimiter "\\"
```

```Output
P1      P2
--      --
Contoso Administrator
```

### <span data-ttu-id="4cd42-130">Exemplo 3: gerar um objeto que contém duas propriedades nomeadas</span><span class="sxs-lookup"><span data-stu-id="4cd42-130">Example 3: Generate an object that contains two named properties</span></span>

<span data-ttu-id="4cd42-131">O exemplo a seguir cria objetos de entradas de arquivo de hosts do Windows.</span><span class="sxs-lookup"><span data-stu-id="4cd42-131">The following example creates objects from Windows hosts file entries.</span></span>

```powershell
$content = Get-Content C:\Windows\System32\drivers\etc\hosts
$content = $content -match "^[^#]"
$content | ConvertFrom-String -PropertyNames IP, Server
```

```Output
IP             Server
--             ------
192.168.7.10   W2012R2
192.168.7.20   W2016
192.168.7.101  WIN8
192.168.7.102  WIN10
```

<span data-ttu-id="4cd42-132">O `Get-Content` cmdlet armazena o conteúdo de um arquivo de hosts do Windows no `$content` .</span><span class="sxs-lookup"><span data-stu-id="4cd42-132">The `Get-Content` cmdlet stores the content of a Windows hosts file in `$content`.</span></span> <span data-ttu-id="4cd42-133">O segundo comando Remove todos os comentários no início do arquivo de hosts usando uma expressão regular que corresponde a qualquer linha que não comece com ( `#` ).</span><span class="sxs-lookup"><span data-stu-id="4cd42-133">The second command removes any comments at the beginning of the hosts file using a regular expression that matches any line that does not start with (`#`).</span></span> <span data-ttu-id="4cd42-134">O último comando converte o texto restante em objetos com propriedades de **servidor** e **IP** .</span><span class="sxs-lookup"><span data-stu-id="4cd42-134">The last command converts the remaining text into objects with **Server** and **IP** properties.</span></span>

### <span data-ttu-id="4cd42-135">Exemplo 4: Use uma expressão como o valor do parâmetro TemplateContent, salve os resultados em uma variável.</span><span class="sxs-lookup"><span data-stu-id="4cd42-135">Example 4: Use an expression as the value of the TemplateContent parameter, save the results in a variable.</span></span>

<span data-ttu-id="4cd42-136">Esse comando usa uma expressão como o valor do parâmetro **TemplateContent** .</span><span class="sxs-lookup"><span data-stu-id="4cd42-136">This command uses an expression as the value of the **TemplateContent** parameter.</span></span>
<span data-ttu-id="4cd42-137">A expressão é salva em uma variável para simplificar.</span><span class="sxs-lookup"><span data-stu-id="4cd42-137">The expression is saved in a variable for simplicity.</span></span>
<span data-ttu-id="4cd42-138">O Windows PowerShell agora compreende que a cadeia de caracteres usada no pipeline `ConvertFrom-String` tem três propriedades:</span><span class="sxs-lookup"><span data-stu-id="4cd42-138">Windows PowerShell understands now that the string that is used on the pipeline to `ConvertFrom-String` has three properties:</span></span>

- <span data-ttu-id="4cd42-139">**Nome**</span><span class="sxs-lookup"><span data-stu-id="4cd42-139">**Name**</span></span>
- <span data-ttu-id="4cd42-140">**phone**</span><span class="sxs-lookup"><span data-stu-id="4cd42-140">**phone**</span></span>
- <span data-ttu-id="4cd42-141">**age**</span><span class="sxs-lookup"><span data-stu-id="4cd42-141">**age**</span></span>

```powershell
$template = @'
{Name*:Phoebe Cat}, {phone:425-123-6789}, {age:6}
{Name*:Lucky Shot}, {phone:(206) 987-4321}, {age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789    6
Lucky Shot    (206) 987-4321  12
Elephant Wise 425-888-7766    87
Wild Shrimp   (111)  222-3333 1
```

<span data-ttu-id="4cd42-142">Cada linha na entrada é avaliada pelas correspondências de exemplo.</span><span class="sxs-lookup"><span data-stu-id="4cd42-142">Each line in the input is evaluated by the sample matches.</span></span> <span data-ttu-id="4cd42-143">Se a linha corresponder aos exemplos fornecidos no padrão, os valores serão extraídos e passados para a variável de saída.</span><span class="sxs-lookup"><span data-stu-id="4cd42-143">If the line matches the examples given in the pattern, values are extracted and passed to the output variable.</span></span>

<span data-ttu-id="4cd42-144">Os dados de exemplo, `$template` , fornecem dois formatos de telefone diferentes:</span><span class="sxs-lookup"><span data-stu-id="4cd42-144">The sample data, `$template`, provides two different phone formats:</span></span>

- `425-123-6789`
- `(206) 987-4321`

<span data-ttu-id="4cd42-145">Os dados de exemplo também fornecem dois formatos de idade diferentes:</span><span class="sxs-lookup"><span data-stu-id="4cd42-145">The sample data also provides two different age formats:</span></span>

- `6`
- `12`

<span data-ttu-id="4cd42-146">Isso implica que telefones como `(206) 987 4321` não serão reconhecidos, porque não há nenhum dado de exemplo que corresponda a esse padrão porque não há hifens.</span><span class="sxs-lookup"><span data-stu-id="4cd42-146">This implies that phones like `(206) 987 4321` will not be recognized, because there's no sample data that matches that pattern because there are no hyphens.</span></span>

### <span data-ttu-id="4cd42-147">Exemplo 5: especificando tipos de dados para as propriedades geradas</span><span class="sxs-lookup"><span data-stu-id="4cd42-147">Example 5: Specifying data types to the generated properties</span></span>

<span data-ttu-id="4cd42-148">Este é o mesmo exemplo do exemplo 4 acima.</span><span class="sxs-lookup"><span data-stu-id="4cd42-148">This is the same example as Example 4, above.</span></span>
<span data-ttu-id="4cd42-149">A diferença é que a cadeia de caracteres de padrão inclui um tipo de dados para cada propriedade desejada.</span><span class="sxs-lookup"><span data-stu-id="4cd42-149">The difference is that the pattern string includes a data type for each desired property.</span></span>

```powershell
$template = @'
{[string]Name*:Phoebe Cat}, {[string]phone:425-123-6789}, {[int]age:6}
{[string]Name*:Lucky Shot}, {[string]phone:(206) 987-4321}, {[int]age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789      6
Lucky Shot    (206) 987-4321   12
Elephant Wise 425-888-7766     87
Wild Shrimp   (111)  222-3333   1
```

```powershell
$PersonalData | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
age         NoteProperty int age=6
Name        NoteProperty string Name=Phoebe Cat
phone       NoteProperty string phone=425-123-6789
```

<span data-ttu-id="4cd42-150">O `Get-Member` cmdlet é usado para mostrar que a propriedade **age** é um inteiro.</span><span class="sxs-lookup"><span data-stu-id="4cd42-150">The `Get-Member` cmdlet is used to show that the **age** property is an integer.</span></span>

## <span data-ttu-id="4cd42-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4cd42-151">PARAMETERS</span></span>

### <span data-ttu-id="4cd42-152">-Delimitador</span><span class="sxs-lookup"><span data-stu-id="4cd42-152">-Delimiter</span></span>

<span data-ttu-id="4cd42-153">Especifica uma expressão regular que identifica o limite entre os elementos.</span><span class="sxs-lookup"><span data-stu-id="4cd42-153">Specifies a regular expression that identifies the boundary between elements.</span></span>
<span data-ttu-id="4cd42-154">Elementos que são criados pela divisão se tornam propriedades no objeto resultante.</span><span class="sxs-lookup"><span data-stu-id="4cd42-154">Elements that are created by the split become properties in the resulting object.</span></span>
<span data-ttu-id="4cd42-155">O delimitador é usado basicamente em uma chamada para o método **Split** do tipo `[System.Text.RegularExpressions.RegularExpression]` .</span><span class="sxs-lookup"><span data-stu-id="4cd42-155">The delimiter is ultimately used in a call to the **Split** method of the type `[System.Text.RegularExpressions.RegularExpression]`.</span></span>

```yaml
Type: System.String
Parameter Sets: ByDelimiter
Aliases: DEL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cd42-156">-IncludeExtent</span><span class="sxs-lookup"><span data-stu-id="4cd42-156">-IncludeExtent</span></span>

<span data-ttu-id="4cd42-157">Indica que esse cmdlet inclui uma propriedade de texto de extensão que é removida por padrão.</span><span class="sxs-lookup"><span data-stu-id="4cd42-157">Indicates that this cmdlet includes an extent text property that is removed by default.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: IE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cd42-158">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4cd42-158">-InputObject</span></span>

<span data-ttu-id="4cd42-159">Especifica cadeias de caracteres recebidas do pipeline ou uma variável que contém um objeto de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4cd42-159">Specifies strings received from the pipeline, or a variable that contains a string object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4cd42-160">-PropertyNames</span><span class="sxs-lookup"><span data-stu-id="4cd42-160">-PropertyNames</span></span>

<span data-ttu-id="4cd42-161">Especifica uma matriz de nomes de propriedade para a qual atribuir valores de divisão no objeto resultante.</span><span class="sxs-lookup"><span data-stu-id="4cd42-161">Specifies an array of property names to which to assign split values in the resulting object.</span></span>
<span data-ttu-id="4cd42-162">Cada linha de texto que você divide ou analisa gera elementos que representam valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="4cd42-162">Every line of text that you split or parse generates elements that represent property values.</span></span>
<span data-ttu-id="4cd42-163">Se o elemento for o resultado de um grupo de captura e esse grupo de captura for nomeado (por exemplo, `(?<name>)` ou `(?'name')` ), o nome desse grupo de captura será atribuído à propriedade.</span><span class="sxs-lookup"><span data-stu-id="4cd42-163">If the element is the result of a capture group, and that capture group is named (for example, `(?<name>)` or `(?'name')` ), then the name of that capture group is assigned to the property.</span></span>

<span data-ttu-id="4cd42-164">Se você fornecer quaisquer elementos na matriz **PropertyName** , esses nomes serão atribuídos às propriedades que ainda não foram nomeadas.</span><span class="sxs-lookup"><span data-stu-id="4cd42-164">If you provide any elements in the **PropertyName** array, those names are assigned to properties that have not yet been named.</span></span>

<span data-ttu-id="4cd42-165">Se você fornecer mais nomes de Propriedade do que os campos, o PowerShell ignorará os nomes de propriedade extras.</span><span class="sxs-lookup"><span data-stu-id="4cd42-165">If you provide more property names than there are fields, PowerShell ignores the extra property names.</span></span> <span data-ttu-id="4cd42-166">Se você não especificar nomes de propriedade suficientes para nomear todos os campos, o PowerShell atribuirá automaticamente nomes de propriedade numérica a quaisquer propriedades que não estejam nomeadas: **P1** , **P2** , etc.</span><span class="sxs-lookup"><span data-stu-id="4cd42-166">If you do not specify enough property names to name all fields, PowerShell automatically assigns numerical property names to any properties that are not named: **P1** , **P2** , etc.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByDelimiter
Aliases: PN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cd42-167">-TemplateContent</span><span class="sxs-lookup"><span data-stu-id="4cd42-167">-TemplateContent</span></span>

<span data-ttu-id="4cd42-168">Especifica uma expressão ou uma expressão salva como uma variável, que descreve as propriedades para as quais esse cmdlet atribui cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4cd42-168">Specifies an expression, or an expression saved as a variable, that describes the properties to which this cmdlet assigns strings.</span></span> <span data-ttu-id="4cd42-169">A sintaxe de uma especificação de campo de modelo é a seguinte: `{[optional-typecast]<name>:<example-value>}` .</span><span class="sxs-lookup"><span data-stu-id="4cd42-169">The syntax of a template field specification is the following: `{[optional-typecast]<name>:<example-value>}`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cd42-170">-TemplateFile</span><span class="sxs-lookup"><span data-stu-id="4cd42-170">-TemplateFile</span></span>

<span data-ttu-id="4cd42-171">Especifica um arquivo, como uma matriz, que contém um modelo para a análise desejada da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4cd42-171">Specifies a file, as an array, that contains a template for the desired parsing of the string.</span></span>
<span data-ttu-id="4cd42-172">No arquivo de modelo, as propriedades e seus valores são colocados entre colchetes, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="4cd42-172">In the template file, properties and their values are enclosed in brackets, as shown below.</span></span>
<span data-ttu-id="4cd42-173">Se uma propriedade, como a propriedade **Name** e suas outras propriedades associadas, aparecer várias vezes, você poderá adicionar um asterisco ( `*` ) para indicar que isso resulta em vários registros.</span><span class="sxs-lookup"><span data-stu-id="4cd42-173">If a property, such as the **Name** property and its associated other properties, appears multiple times, you can add an asterisk (`*`) to indicate that this results in multiple records.</span></span> <span data-ttu-id="4cd42-174">Isso evita a extração de várias propriedades em um único registro.</span><span class="sxs-lookup"><span data-stu-id="4cd42-174">This avoids extracting multiple properties into a single record.</span></span>

```
{Name*:David Chew}
{City:Redmond}, {State:WA}
{Name*:Evan Narvaez}    {Name*:Antonio Moreno}
{City:Issaquah}, {State:WA}
```

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cd42-175">-Updatetemplate</span><span class="sxs-lookup"><span data-stu-id="4cd42-175">-UpdateTemplate</span></span>

<span data-ttu-id="4cd42-176">Indica que esse cmdlet salva os resultados de um algoritmo de aprendizado em um comentário no arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="4cd42-176">Indicates that this cmdlet saves the results of a learning algorithm into a comment in the template file.</span></span>
<span data-ttu-id="4cd42-177">Isso torna o processo de aprendizado de algoritmo mais rápido.</span><span class="sxs-lookup"><span data-stu-id="4cd42-177">This makes the algorithm learning process faster.</span></span>
<span data-ttu-id="4cd42-178">Para usar esse parâmetro, você também deve especificar um arquivo de modelo com o parâmetro **TemplateFile** .</span><span class="sxs-lookup"><span data-stu-id="4cd42-178">To use this parameter, you must also specify a template file with the **TemplateFile** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: UT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cd42-179">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4cd42-179">CommonParameters</span></span>

<span data-ttu-id="4cd42-180">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="4cd42-180">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="4cd42-181">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="4cd42-181">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4cd42-182">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4cd42-182">INPUTS</span></span>

### <span data-ttu-id="4cd42-183">System.String</span><span class="sxs-lookup"><span data-stu-id="4cd42-183">System.String</span></span>

## <span data-ttu-id="4cd42-184">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4cd42-184">OUTPUTS</span></span>

## <span data-ttu-id="4cd42-185">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4cd42-185">NOTES</span></span>

## <span data-ttu-id="4cd42-186">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4cd42-186">RELATED LINKS</span></span>

[<span data-ttu-id="4cd42-187">ConvertFrom-cadeia de caracteres: análise de texto baseada em exemplo</span><span class="sxs-lookup"><span data-stu-id="4cd42-187">ConvertFrom-String: Example-based text parsing</span></span>](https://devblogs.microsoft.com/powershell/convertfrom-string-example-based-text-parsing/)

[<span data-ttu-id="4cd42-188">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="4cd42-188">ConvertFrom-StringData</span></span>](ConvertFrom-StringData.md)

[<span data-ttu-id="4cd42-189">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="4cd42-189">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="4cd42-190">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="4cd42-190">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)
