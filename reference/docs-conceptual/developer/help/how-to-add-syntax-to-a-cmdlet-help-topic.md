---
ms.date: 09/12/2016
ms.topic: reference
title: Como adicionar sintaxe a um tópico de ajuda do cmdlet
description: Como adicionar sintaxe a um tópico de ajuda do cmdlet
ms.openlocfilehash: bcc037d22051c162cd0f70702da17afe7ed9c01a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659079"
---
# <a name="how-to-add-syntax-to-a-cmdlet-help-topic"></a><span data-ttu-id="d7fee-103">Como adicionar sintaxe a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="d7fee-103">How to Add Syntax to a Cmdlet Help Topic</span></span>

<span data-ttu-id="d7fee-104">Antes de começar a codificar o XML para o diagrama de sintaxe no arquivo de ajuda do cmdlet, leia esta seção para obter uma visão clara do tipo de dados que você precisa fornecer, como os atributos de parâmetro e como esses dados são exibidos no diagrama de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="d7fee-104">Before you start to code the XML for the syntax diagram in the cmdlet Help file, read this section to get a clear picture of the kind of data you need to provide, such as the parameter attributes, and how that data is displayed in the syntax diagram..</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="d7fee-105">Atributos de parâmetro</span><span class="sxs-lookup"><span data-stu-id="d7fee-105">Parameter Attributes</span></span>

- <span data-ttu-id="d7fee-106">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d7fee-106">Required</span></span>
  - <span data-ttu-id="d7fee-107">Se for true, o parâmetro deverá aparecer em todos os comandos que usam o conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d7fee-107">If true, the parameter must appear in all commands that use the parameter set.</span></span>
  - <span data-ttu-id="d7fee-108">Se for false, o parâmetro será opcional em todos os comandos que usam o conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d7fee-108">If false, the parameter is optional in all commands that use the parameter set.</span></span>
- <span data-ttu-id="d7fee-109">Posição</span><span class="sxs-lookup"><span data-stu-id="d7fee-109">Position</span></span>
  - <span data-ttu-id="d7fee-110">Se nomeado, o nome do parâmetro será obrigatório.</span><span class="sxs-lookup"><span data-stu-id="d7fee-110">If named, the parameter name is required.</span></span>
  - <span data-ttu-id="d7fee-111">Se posicional, o nome do parâmetro será opcional.</span><span class="sxs-lookup"><span data-stu-id="d7fee-111">If positional, the parameter name is optional.</span></span> <span data-ttu-id="d7fee-112">Quando é omitido, o valor do parâmetro deve estar na posição especificada no comando.</span><span class="sxs-lookup"><span data-stu-id="d7fee-112">When it is omitted, the parameter value must be in the specified position in the command.</span></span> <span data-ttu-id="d7fee-113">Por exemplo, se o valor for position = "1", o valor do parâmetro deverá ser o primeiro ou apenas o valor do parâmetro não nomeado no comando.</span><span class="sxs-lookup"><span data-stu-id="d7fee-113">For example, if the value is position="1", the parameter value must be the first or only unnamed parameter value in the command.</span></span>
- <span data-ttu-id="d7fee-114">Entrada do pipeline</span><span class="sxs-lookup"><span data-stu-id="d7fee-114">Pipeline Input</span></span>
  - <span data-ttu-id="d7fee-115">Se verdadeiro (ByValue), você pode canalizar a entrada para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d7fee-115">If true (ByValue), you can pipe input to the parameter.</span></span> <span data-ttu-id="d7fee-116">A entrada é associada ao parâmetro ("Bound to"), mesmo se o nome da propriedade e o tipo de objeto não corresponderem ao tipo esperado.</span><span class="sxs-lookup"><span data-stu-id="d7fee-116">The input is associated with ("bound to") the parameter even if the property name and the object type do not match the expected type.</span></span>
    <span data-ttu-id="d7fee-117">Os componentes de associação de parâmetro do PowerShell tentam converter a entrada para o tipo correto e apresentar falha no comando somente quando o tipo não puder ser convertido.</span><span class="sxs-lookup"><span data-stu-id="d7fee-117">The PowerShell parameter binding components try to convert the input to the correct type and fail the command only when the type cannot be converted.</span></span> <span data-ttu-id="d7fee-118">Somente um parâmetro em um conjunto de parâmetros pode ser associado por valor.</span><span class="sxs-lookup"><span data-stu-id="d7fee-118">Only one parameter in a parameter set can be associated by value.</span></span>
  - <span data-ttu-id="d7fee-119">Se verdadeiro (ByPropertyName), você pode canalizar a entrada para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d7fee-119">If true (ByPropertyName), you can pipe input to the parameter.</span></span> <span data-ttu-id="d7fee-120">No entanto, a entrada é associada ao parâmetro somente quando o nome do parâmetro corresponde ao nome de uma propriedade do objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="d7fee-120">However, the input is associated with the parameter only when the parameter name matches the name of a property of the input object.</span></span> <span data-ttu-id="d7fee-121">Por exemplo, se o nome do parâmetro for `Path` , os objetos canalizados para o cmdlet serão associados a esse parâmetro somente quando o objeto tiver uma propriedade chamada Path.</span><span class="sxs-lookup"><span data-stu-id="d7fee-121">For example, if the parameter name is `Path`, objects piped to the cmdlet are associated with that parameter only when the object has a property named path.</span></span>
  - <span data-ttu-id="d7fee-122">Se true (ByValue, ByPropertyName), você poderá canalizar a entrada para o parâmetro pelo nome da propriedade ou por valor.</span><span class="sxs-lookup"><span data-stu-id="d7fee-122">If true (ByValue, ByPropertyName), you can pipe input to the parameter either by property name or by value.</span></span> <span data-ttu-id="d7fee-123">Somente um parâmetro em um conjunto de parâmetros pode ser associado por valor.</span><span class="sxs-lookup"><span data-stu-id="d7fee-123">Only one parameter in a parameter set can be associated by value.</span></span>
  - <span data-ttu-id="d7fee-124">Se for false, não será possível canalizar a entrada para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d7fee-124">If false, you cannot pipe input to this parameter.</span></span>
- <span data-ttu-id="d7fee-125">Global</span><span class="sxs-lookup"><span data-stu-id="d7fee-125">Globbing</span></span>
  - <span data-ttu-id="d7fee-126">Se for true, o texto que o usuário digitar para o valor do parâmetro poderá incluir caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="d7fee-126">If true, the text that the user types for the parameter value can include wildcard characters.</span></span>
  - <span data-ttu-id="d7fee-127">Se for false, o texto que o usuário digitar para o valor do parâmetro não poderá incluir caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="d7fee-127">If false, the text that the user types for the parameter value cannot include wildcard characters.</span></span>

### <a name="parameter-value-attributes"></a><span data-ttu-id="d7fee-128">Atributos de valor do parâmetro</span><span class="sxs-lookup"><span data-stu-id="d7fee-128">Parameter Value Attributes</span></span>

- <span data-ttu-id="d7fee-129">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d7fee-129">Required</span></span>
  - <span data-ttu-id="d7fee-130">Se for true, o valor especificado deverá ser usado sempre que usar o parâmetro em um comando.</span><span class="sxs-lookup"><span data-stu-id="d7fee-130">If true, the specified value must be used whenever using the parameter in a command.</span></span>
  - <span data-ttu-id="d7fee-131">Se for false, o valor do parâmetro será opcional.</span><span class="sxs-lookup"><span data-stu-id="d7fee-131">If false, the parameter value is optional.</span></span> <span data-ttu-id="d7fee-132">Normalmente, um valor é opcional somente quando é um dos vários valores válidos para um parâmetro, como em um tipo enumerado.</span><span class="sxs-lookup"><span data-stu-id="d7fee-132">Typically, a value is optional only when it is one of several valid values for a parameter, such as in an enumerated type.</span></span>

<span data-ttu-id="d7fee-133">O atributo **necessário** de um valor de parâmetro é diferente do atributo **necessário** de um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d7fee-133">The **Required** attribute of a parameter value is different from the **Required** attribute of a parameter.</span></span>

<span data-ttu-id="d7fee-134">O atributo Required de um parâmetro indica se o parâmetro (e seu valor) deve ser incluído ao invocar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7fee-134">The required attribute of a parameter indicates whether the parameter (and its value) must be included when invoking the cmdlet.</span></span> <span data-ttu-id="d7fee-135">Por outro lado, o atributo Required de um valor de parâmetro é usado somente quando o parâmetro é incluído no comando.</span><span class="sxs-lookup"><span data-stu-id="d7fee-135">In contrast, the required attribute of a parameter value is used only when the parameter is included in the command.</span></span> <span data-ttu-id="d7fee-136">Indica se esse valor específico deve ser usado com o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d7fee-136">It indicates whether that particular value must be used with the parameter.</span></span>

<span data-ttu-id="d7fee-137">Normalmente, os valores de parâmetro que são espaços reservados são necessários e os valores de parâmetros que são literais não são necessários, pois eles são um dos vários valores que podem ser usados com o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d7fee-137">Typically, parameter values that are placeholders are required and parameter values that are literal are not required, because they are one of several values that might be used with the parameter.</span></span>

### <a name="gathering-syntax-information"></a><span data-ttu-id="d7fee-138">Coletando informações de sintaxe</span><span class="sxs-lookup"><span data-stu-id="d7fee-138">Gathering Syntax Information</span></span>

1. <span data-ttu-id="d7fee-139">Comece com o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7fee-139">Start with the cmdlet name.</span></span>

   ```
   SYNTAX
       Get-Tech
   ```

1. <span data-ttu-id="d7fee-140">Liste todos os parâmetros do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7fee-140">List all the parameters of the cmdlet.</span></span> <span data-ttu-id="d7fee-141">Digite um hífen ( `-` ) (ASCII 45) antes de cada nome de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d7fee-141">Type a hyphen (`-`) (ASCII 45) before each parameter name.</span></span>
   <span data-ttu-id="d7fee-142">Separe os parâmetros em conjuntos de parâmetros (alguns cmdlets podem ter apenas um conjunto de parâmetros).</span><span class="sxs-lookup"><span data-stu-id="d7fee-142">Separate the parameters into parameter sets (some cmdlets may have only one parameter set).</span></span> <span data-ttu-id="d7fee-143">Neste exemplo, o cmdlet Get-Tech tem dois conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d7fee-143">In this example the Get-Tech cmdlet has two parameter sets.</span></span>

   ```
   SYNTAX
       Get-Tech -name -type
       Get-Tech -ID -list -type
   ```

   <span data-ttu-id="d7fee-144">Inicie cada conjunto de parâmetros com o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7fee-144">Start each parameter set with the cmdlet name.</span></span>

   <span data-ttu-id="d7fee-145">Liste o conjunto de parâmetros padrão primeiro.</span><span class="sxs-lookup"><span data-stu-id="d7fee-145">List the default parameter set first.</span></span> <span data-ttu-id="d7fee-146">O parâmetro padrão é especificado pela classe cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7fee-146">The default parameter is specified by the cmdlet class.</span></span>

   <span data-ttu-id="d7fee-147">Para cada conjunto de parâmetros, liste seu parâmetro exclusivo primeiro, a menos que haja parâmetros posicionais que devem aparecer primeiro.</span><span class="sxs-lookup"><span data-stu-id="d7fee-147">For each parameter set, list its unique parameter first, unless there are positional parameters that must appear first.</span></span> <span data-ttu-id="d7fee-148">No exemplo anterior, os parâmetros Name e ID são parâmetros exclusivos para os dois conjuntos de parâmetros (cada conjunto de parâmetros deve ter um parâmetro que seja exclusivo para esse conjunto de parâmetros).</span><span class="sxs-lookup"><span data-stu-id="d7fee-148">In the previous example, the Name and ID parameters are unique parameters for the two parameter sets (each parameter set must have one parameter that is unique to that parameter set).</span></span> <span data-ttu-id="d7fee-149">Isso torna mais fácil para os usuários identificar qual parâmetro eles precisam fornecer para o conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d7fee-149">This makes it easier for users to identify what parameter they need to supply for the parameter set.</span></span>

   <span data-ttu-id="d7fee-150">Liste os parâmetros na ordem em que eles devem aparecer no comando.</span><span class="sxs-lookup"><span data-stu-id="d7fee-150">List the parameters in the order that they should appear in the command.</span></span> <span data-ttu-id="d7fee-151">Se o pedido não for importante, liste os parâmetros relacionados juntos ou liste os parâmetros usados com mais frequência primeiro.</span><span class="sxs-lookup"><span data-stu-id="d7fee-151">If the order does not matter, list related parameters together, or list the most frequently used parameters first.</span></span>

   <span data-ttu-id="d7fee-152">Certifique-se de listar os parâmetros WhatIf e Confirm se o cmdlet der suporte para ShouldProcess.</span><span class="sxs-lookup"><span data-stu-id="d7fee-152">Be sure to list the WhatIf and Confirm parameters if the cmdlet supports ShouldProcess.</span></span>

   <span data-ttu-id="d7fee-153">Não liste os parâmetros comuns (como Verbose, Debug e ErrorAction) em seu diagrama de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="d7fee-153">Do not list the common parameters (such as Verbose, Debug, and ErrorAction) in your syntax diagram.</span></span> <span data-ttu-id="d7fee-154">O `Get-Help` cmdlet adiciona essas informações para você quando ele exibir o tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="d7fee-154">The `Get-Help` cmdlet adds that information for you when it displays the Help topic.</span></span>

1. <span data-ttu-id="d7fee-155">Adicione os valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d7fee-155">Add the parameter values.</span></span> <span data-ttu-id="d7fee-156">No PowerShell, os valores de parâmetro são representados por seu tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="d7fee-156">In PowerShell, parameter values are represented by their .NET type.</span></span>
   <span data-ttu-id="d7fee-157">No entanto, o nome do tipo pode ser abreviado, como "String" para System. String.</span><span class="sxs-lookup"><span data-stu-id="d7fee-157">However, the type name can be abbreviated, such as "string" for System.String.</span></span>

   ```
   SYNTAX
       Get-Tech -name string -type basic advanced
       Get-Tech -ID int -list -type basic advanced
   ```

   <span data-ttu-id="d7fee-158">Abreviar os tipos contanto que seu significado esteja claro, como **cadeia de caracteres** para **System. String** e **int** para **System. Int32**.</span><span class="sxs-lookup"><span data-stu-id="d7fee-158">Abbreviate types as long as their meaning is clear, such as **string** for **System.String** and **int** for **System.Int32**.</span></span>

   <span data-ttu-id="d7fee-159">Lista todos os valores de enumerações, como o `-type` parâmetro no exemplo anterior, que pode ser definido como **básico** ou **avançado**.</span><span class="sxs-lookup"><span data-stu-id="d7fee-159">List all values of enumerations, such as the `-type` parameter in the previous example, which can be set to **basic** or **advanced**.</span></span>

   <span data-ttu-id="d7fee-160">Parâmetros de switch, como `-list` no exemplo anterior, não têm valores.</span><span class="sxs-lookup"><span data-stu-id="d7fee-160">Switch parameters, such as `-list` in the previous example, do not have values.</span></span>

1. <span data-ttu-id="d7fee-161">Adicione colchetes angulares aos valores de parâmetros que são espaços reservados, em comparação com os valores de parâmetro que são literais.</span><span class="sxs-lookup"><span data-stu-id="d7fee-161">Add angle brackets to parameters values that are placeholder, as compared to parameter values that are literals.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> -type basic advanced
       Get-Tech -ID <int> -list -type basic advanced
   ```

1. <span data-ttu-id="d7fee-162">Coloque os parâmetros opcionais e seus valores entre colchetes.</span><span class="sxs-lookup"><span data-stu-id="d7fee-162">Enclose optional parameters and their vales in square brackets.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

1. <span data-ttu-id="d7fee-163">Coloque os nomes de parâmetros opcionais (para parâmetros posicionais) entre colchetes.</span><span class="sxs-lookup"><span data-stu-id="d7fee-163">Enclose optional parameters names (for positional parameters) in square brackets.</span></span> <span data-ttu-id="d7fee-164">O nome dos parâmetros que são posicionais, como o parâmetro Name no exemplo a seguir, não precisa ser incluído no comando.</span><span class="sxs-lookup"><span data-stu-id="d7fee-164">The name for parameters that are positional, such as the Name parameter in the following example, do not have to be included in the command.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

1. <span data-ttu-id="d7fee-165">Se um valor de parâmetro puder conter vários valores, como uma lista de nomes no parâmetro Name, adicione um par de colchetes diretamente após o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d7fee-165">If a parameter value can contain multiple values, such as a list of names in the Name parameter, add a pair of square brackets directly following the parameter value.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type basic advanced]
       Get-Tech -ID <int[]> [-list] [-type basic advanced]
   ```

1. <span data-ttu-id="d7fee-166">Se o usuário puder escolher parâmetros ou valores de parâmetro, como o parâmetro de tipo, coloque as opções entre chaves e separe-as com o símbolo exclusivo ou (;).</span><span class="sxs-lookup"><span data-stu-id="d7fee-166">If the user can choose from parameters or parameter values, such as the Type parameter, enclose the choices in curly brackets and separate them with the exclusive OR symbol(;).</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

1. <span data-ttu-id="d7fee-167">Se o valor do parâmetro precisar usar formatação específica, como aspas ou parênteses, mostre o formato na sintaxe.</span><span class="sxs-lookup"><span data-stu-id="d7fee-167">If the parameter value must use specific formatting, such as quotation marks or parentheses, show the format in the syntax.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <"string[]"> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

## <a name="coding-the-syntax-diagram-xml"></a><span data-ttu-id="d7fee-168">Codificando o XML do diagrama de sintaxe</span><span class="sxs-lookup"><span data-stu-id="d7fee-168">Coding the Syntax Diagram XML</span></span>

<span data-ttu-id="d7fee-169">O nó de sintaxe do XML começa imediatamente após o nó de descrição, que termina com a `</maml:description>` marca.</span><span class="sxs-lookup"><span data-stu-id="d7fee-169">The syntax node of the XML begins immediately after the description node, which ends with the `</maml:description>` tag.</span></span> <span data-ttu-id="d7fee-170">Para obter informações sobre como coletar os dados usados no diagrama de sintaxe, consulte [coletando informações de sintaxe](#gathering-syntax-information).</span><span class="sxs-lookup"><span data-stu-id="d7fee-170">For information about gathering the data used in the syntax diagram, see [Gathering Syntax Information](#gathering-syntax-information).</span></span>

### <a name="adding-a-syntax-node"></a><span data-ttu-id="d7fee-171">Adicionando um nó de sintaxe</span><span class="sxs-lookup"><span data-stu-id="d7fee-171">Adding a Syntax Node</span></span>

<span data-ttu-id="d7fee-172">O diagrama de sintaxe exibido no tópico de ajuda do cmdlet é gerado a partir dos dados no nó sintaxe do XML.</span><span class="sxs-lookup"><span data-stu-id="d7fee-172">The syntax diagram displayed in the cmdlet Help topic is generated from the data in the syntax node of the XML.</span></span> <span data-ttu-id="d7fee-173">O nó de sintaxe é colocado em um par, se houver `<command:syntax>` marcas.</span><span class="sxs-lookup"><span data-stu-id="d7fee-173">The syntax node is enclosed in a pair if `<command:syntax>` tags.</span></span> <span data-ttu-id="d7fee-174">Com cada conjunto de parâmetros do cmdlet incluído em um par de `<command:syntaxitem>` marcas.</span><span class="sxs-lookup"><span data-stu-id="d7fee-174">With each parameter set of the cmdlet enclosed in a pair of `<command:syntaxitem>` tags.</span></span> <span data-ttu-id="d7fee-175">Não há nenhum limite para o número de `<command:syntaxitem>` marcas que você pode adicionar.</span><span class="sxs-lookup"><span data-stu-id="d7fee-175">There is no limit to the number of `<command:syntaxitem>` tags that you can add.</span></span>

<span data-ttu-id="d7fee-176">O exemplo a seguir mostra um nó de sintaxe que tem nós de item de sintaxe para dois conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d7fee-176">The following example shows a syntax node that has syntax item nodes for two parameter sets.</span></span>

```xml
<command:syntax>
  <command:syntaxItem>
    ...
    <!--Parameter Set 1 (default parameter set) parameters go here-->
    ...
  </command:syntaxItem>
  <command:syntaxItem>
    ...
    <!--Parameter Set 2 parameters go here-->
    ...
  </command:syntaxItem>
</command:syntax>
```

### <a name="adding-the-cmdlet-name-to-the-parameter-set-data"></a><span data-ttu-id="d7fee-177">Adicionando o nome do cmdlet aos dados do conjunto de parâmetros</span><span class="sxs-lookup"><span data-stu-id="d7fee-177">Adding the Cmdlet Name to the Parameter Set Data</span></span>

<span data-ttu-id="d7fee-178">Cada conjunto de parâmetros do cmdlet é especificado em um nó de item de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="d7fee-178">Each parameter set of the cmdlet is specified in a syntax item node.</span></span> <span data-ttu-id="d7fee-179">Cada nó de sintaxe do item começa com um par de `<maml:name>` marcas que incluem o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7fee-179">Each syntax item node begins with a pair of `<maml:name>` tags that include the name of the cmdlet.</span></span>

<span data-ttu-id="d7fee-180">O exemplo a seguir inclui um nó de sintaxe que tem nós de item de sintaxe para dois conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d7fee-180">The following example includes a syntax node that has syntax item nodes for two parameter sets.</span></span>

```xml
<command:syntax>
  <command:syntaxItem>
    <maml:name>Cmdlet-Name</maml:name>
  </command:syntaxItem>
  <command:syntaxItem>
    <maml:name>Cmdlet-Name</maml:name>
  </command:syntaxItem>
</command:syntax>
```

### <a name="adding-parameters"></a><span data-ttu-id="d7fee-181">Adicionando parâmetros</span><span class="sxs-lookup"><span data-stu-id="d7fee-181">Adding Parameters</span></span>

<span data-ttu-id="d7fee-182">Cada parâmetro adicionado ao nó de item de sintaxe é especificado dentro de um par de `<command:parameter>` marcas.</span><span class="sxs-lookup"><span data-stu-id="d7fee-182">Each parameter added to the syntax item node is specified within a pair of `<command:parameter>` tags.</span></span> <span data-ttu-id="d7fee-183">Você precisa de um par de `<command:parameter>` marcas para cada parâmetro incluído no conjunto de parâmetros, com a exceção dos parâmetros comuns fornecidos pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7fee-183">You need a pair of `<command:parameter>` tags for each parameter included in the parameter set, with the exception of the common parameters that are provided by PowerShell.</span></span>

<span data-ttu-id="d7fee-184">Os atributos da marca de abertura `<command:parameter>` determinam como o parâmetro aparece no diagrama de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="d7fee-184">The attributes of the opening `<command:parameter>` tag determine how the parameter appears in the syntax diagram.</span></span> <span data-ttu-id="d7fee-185">Para obter informações sobre atributos de parâmetro, consulte [atributos de parâmetro](#parameter-attributes).</span><span class="sxs-lookup"><span data-stu-id="d7fee-185">For information on parameter attributes, see [Parameter Attributes](#parameter-attributes).</span></span>

> [!NOTE]
> <span data-ttu-id="d7fee-186">A `<command:parameter>` marca dá suporte a um elemento filho `<maml:description>` cujo conteúdo nunca é exibido.</span><span class="sxs-lookup"><span data-stu-id="d7fee-186">The `<command:parameter>` tag supports a child element `<maml:description>` whose content is never displayed.</span></span> <span data-ttu-id="d7fee-187">As descrições de parâmetro são especificadas no nó de parâmetro do XML.</span><span class="sxs-lookup"><span data-stu-id="d7fee-187">The parameter descriptions are specified in the parameter node of the XML.</span></span> <span data-ttu-id="d7fee-188">Para evitar inconsistências entre as informações no item de sintaxe bodes e o nó de parâmetro, omita o ( `<maml:description>` ou deixe-o vazio.</span><span class="sxs-lookup"><span data-stu-id="d7fee-188">To avoid inconsistencies between the information in the syntax item bodes and the parameter node, omit the (`<maml:description>` or leave it empty.</span></span>

<span data-ttu-id="d7fee-189">O exemplo a seguir inclui um nó de item de sintaxe para um conjunto de parâmetros com dois parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d7fee-189">The following example includes a syntax item node for a parameter set with two parameters.</span></span>

```xml
<command:syntaxItem>
  <maml:name>Cmdlet-Name</maml:name>
  <command:parameter required="true" globbing="true"
    pipelineInput="true (ByValue)" position="1">
    <maml:name>ParameterName1</maml:name>
    <command:parameterValue required="true">
      string[]
    </command:parameterValue>
  </command:parameter>
  <command:parameter required="true" globbing="true"
    pipelineInput="true (ByPropertyName)">
    <maml:name>ParameterName2</maml:name>
    <command:parameterValue required="true">
      int32[]
    </command:parameterValue>
  </command:parameter>
</command:syntaxItem>
```
