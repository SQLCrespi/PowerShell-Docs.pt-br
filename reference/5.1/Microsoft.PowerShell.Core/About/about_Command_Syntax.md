---
description: Descreve os diagramas de sintaxe usados no PowerShell.
Locale: en-US
ms.date: 06/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_command_syntax?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Command_Syntax
ms.openlocfilehash: ff7a243a584ee336c0356200f5ba68fde55e0836
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194609"
---
# <a name="about-command-syntax"></a><span data-ttu-id="00b35-103">Sobre a sintaxe do comando</span><span class="sxs-lookup"><span data-stu-id="00b35-103">About Command Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="00b35-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="00b35-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="00b35-105">Descreve os diagramas de sintaxe usados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00b35-105">Describes the syntax diagrams that are used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="00b35-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="00b35-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="00b35-107">Os cmdlets [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) e [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) exibem diagramas de sintaxe para ajudá-lo a construir comandos corretamente.</span><span class="sxs-lookup"><span data-stu-id="00b35-107">The [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) and [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) cmdlets display syntax diagrams to help you construct commands correctly.</span></span> <span data-ttu-id="00b35-108">Este tópico explica como interpretar os diagramas de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="00b35-108">This topic explains how to interpret the syntax diagrams.</span></span>

## <a name="syntax-diagrams"></a><span data-ttu-id="00b35-109">DIAGRAMAS DE SINTAXE</span><span class="sxs-lookup"><span data-stu-id="00b35-109">SYNTAX DIAGRAMS</span></span>

<span data-ttu-id="00b35-110">Cada parágrafo em um diagrama de sintaxe de comando representa uma forma válida do comando.</span><span class="sxs-lookup"><span data-stu-id="00b35-110">Each paragraph in a command syntax diagram represents a valid form of the command.</span></span>

<span data-ttu-id="00b35-111">Para construir um comando, siga o diagrama de sintaxe da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="00b35-111">To construct a command, follow the syntax diagram from left to right.</span></span> <span data-ttu-id="00b35-112">Selecione entre os parâmetros opcionais e forneça valores para os espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="00b35-112">Select from among the optional parameters and provide values for the placeholders.</span></span>

<span data-ttu-id="00b35-113">O PowerShell usa a seguinte notação para diagramas de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="00b35-113">PowerShell uses the following notation for syntax diagrams.</span></span>

```powershell
<command-name> -<Required Parameter Name> <Required Parameter Value>
[-<Optional Parameter Name> <Optional Parameter Value>]
[-<Optional Switch Parameters>]
[-<Optional Parameter Name>] <Required Parameter Value>
```

<span data-ttu-id="00b35-114">Veja a seguir a sintaxe do cmdlet [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias) .</span><span class="sxs-lookup"><span data-stu-id="00b35-114">The following is the syntax for the [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias) cmdlet.</span></span>

```powershell
New-Alias [-Name] <string> [-Value] <string> [-Description <string>]
[-Force] [-Option {None | ReadOnly | Constant | Private | AllScope}]
[-PassThru] [-Scope <string>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

<span data-ttu-id="00b35-115">A sintaxe é capitalizada para facilitar a leitura, mas o PowerShell não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="00b35-115">The syntax is capitalized for readability, but PowerShell is case-insensitive.</span></span>

<span data-ttu-id="00b35-116">O diagrama de sintaxe tem os elementos a seguir.</span><span class="sxs-lookup"><span data-stu-id="00b35-116">The syntax diagram has the following elements.</span></span>

## <a name="command-name"></a><span data-ttu-id="00b35-117">Nome de comando</span><span class="sxs-lookup"><span data-stu-id="00b35-117">Command name</span></span>

<span data-ttu-id="00b35-118">Os comandos sempre começam com um nome de comando, como `New-Alias` .</span><span class="sxs-lookup"><span data-stu-id="00b35-118">Commands always begin with a command name, such as `New-Alias`.</span></span> <span data-ttu-id="00b35-119">Digite o nome do comando ou seu alias, como "GCM" para `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="00b35-119">Type the command name or its alias, such a "gcm" for `Get-Command`.</span></span>

## <a name="parameters"></a><span data-ttu-id="00b35-120">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="00b35-120">Parameters</span></span>

<span data-ttu-id="00b35-121">Os parâmetros de um comando são opções que determinam o que o comando faz.</span><span class="sxs-lookup"><span data-stu-id="00b35-121">The parameters of a command are options that determine what the command does.</span></span>
<span data-ttu-id="00b35-122">Alguns parâmetros usam um "valor" que é entrada do usuário para o comando.</span><span class="sxs-lookup"><span data-stu-id="00b35-122">Some parameters take a "value" which is user input to the command.</span></span>

<span data-ttu-id="00b35-123">Por exemplo, o `Get-Help` comando tem um parâmetro de **nome** que permite especificar o nome do tópico para o qual a ajuda é exibida.</span><span class="sxs-lookup"><span data-stu-id="00b35-123">For example, the `Get-Help` command has a **Name** parameter that lets you specify the name of the topic for which help is displayed.</span></span> <span data-ttu-id="00b35-124">O nome do tópico é o valor do parâmetro **Name** .</span><span class="sxs-lookup"><span data-stu-id="00b35-124">The topic name is the value of the **Name** parameter.</span></span>

<span data-ttu-id="00b35-125">Em um comando do PowerShell, os nomes de parâmetros sempre começam com um hífen.</span><span class="sxs-lookup"><span data-stu-id="00b35-125">In a PowerShell command, parameter names always begin with a hyphen.</span></span>
<span data-ttu-id="00b35-126">O hífen informa ao PowerShell que o item no comando é um nome de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="00b35-126">The hyphen tells PowerShell that the item in the command is a parameter name.</span></span>

<span data-ttu-id="00b35-127">Por exemplo, para usar o parâmetro Name de `New-Alias` , digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="00b35-127">For example, to use the Name parameter of `New-Alias`, you type the following:</span></span>

```powershell
-Name
```

<span data-ttu-id="00b35-128">Os parâmetros podem ser obrigatórios ou opcionais.</span><span class="sxs-lookup"><span data-stu-id="00b35-128">Parameters can be mandatory or optional.</span></span> <span data-ttu-id="00b35-129">Em um diagrama de sintaxe, os itens opcionais são colocados entre colchetes `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="00b35-129">In a syntax diagram, optional items are enclosed in brackets `[ ]`.</span></span>

<span data-ttu-id="00b35-130">Para obter mais informações sobre parâmetros, consulte [about_Parameters](about_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="00b35-130">For more information about parameters, see [about_Parameters](about_Parameters.md).</span></span>

## <a name="parameter-values"></a><span data-ttu-id="00b35-131">Valores dos parâmetros</span><span class="sxs-lookup"><span data-stu-id="00b35-131">Parameter Values</span></span>

<span data-ttu-id="00b35-132">Um valor de parâmetro é a entrada que o parâmetro pega.</span><span class="sxs-lookup"><span data-stu-id="00b35-132">A parameter value is the input that the parameter takes.</span></span> <span data-ttu-id="00b35-133">Como o Windows PowerShell se baseia na estrutura de Microsoft .NET, os valores de parâmetro são representados no diagrama de sintaxe por seu tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="00b35-133">Because Windows PowerShell is based on the Microsoft .NET Framework, parameter values are represented in the syntax diagram by their .NET type.</span></span>

<span data-ttu-id="00b35-134">Por exemplo, o parâmetro Name de `Get-Help` usa um valor de "String", que é uma cadeia de caracteres de texto, como uma única palavra ou várias palavras entre aspas.</span><span class="sxs-lookup"><span data-stu-id="00b35-134">For example, the Name parameter of `Get-Help` takes a "String" value, which is a text string, such as a single word or multiple words enclosed in quotation marks.</span></span>

```powershell
[-Name] <string>
```

<span data-ttu-id="00b35-135">O tipo .NET de um valor de parâmetro é colocado entre colchetes angulares `< >` para indicar que ele é um espaço reservado para um valor e não um literal que você digita em um comando.</span><span class="sxs-lookup"><span data-stu-id="00b35-135">The .NET type of a parameter value is enclosed in angle brackets `< >` to indicate that it is placeholder for a value and not a literal that you type in a command.</span></span>

<span data-ttu-id="00b35-136">Para usar o parâmetro, substitua o espaço reservado do tipo .NET por um objeto que tenha o tipo .NET especificado.</span><span class="sxs-lookup"><span data-stu-id="00b35-136">To use the parameter, replace the .NET type placeholder with an object that has the specified .NET type.</span></span>

<span data-ttu-id="00b35-137">Por exemplo, para usar o parâmetro **Name** , digite "-Name" seguido por uma cadeia de caracteres, como a seguinte:</span><span class="sxs-lookup"><span data-stu-id="00b35-137">For example, to use the **Name** parameter, type "-Name" followed by a string, such as the following:</span></span>

```powershell
-Name MyAlias
```

## <a name="parameters-with-no-values"></a><span data-ttu-id="00b35-138">Parâmetros sem valores</span><span class="sxs-lookup"><span data-stu-id="00b35-138">Parameters with no values</span></span>

<span data-ttu-id="00b35-139">Alguns parâmetros não aceitam entrada, portanto, não têm um valor de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="00b35-139">Some parameters do not accept input, so they do not have a parameter value.</span></span>
<span data-ttu-id="00b35-140">Parâmetros sem valores são chamados de "parâmetros de switch" porque eles funcionam como opções on/off.</span><span class="sxs-lookup"><span data-stu-id="00b35-140">Parameters without values are called "switch parameters" because they work like on/off switches.</span></span> <span data-ttu-id="00b35-141">Você os inclui (ativado) ou os omite (desativado) de um comando.</span><span class="sxs-lookup"><span data-stu-id="00b35-141">You include them (on) or you omit them (off) from a command.</span></span>

<span data-ttu-id="00b35-142">Para usar um parâmetro de opção, basta digitar o nome do parâmetro, precedido por um hífen.</span><span class="sxs-lookup"><span data-stu-id="00b35-142">To use a switch parameter, just type the parameter name, preceded by a hyphen.</span></span>

<span data-ttu-id="00b35-143">Por exemplo, para usar o parâmetro **WhatIf** do `New-Alias` cmdlet, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="00b35-143">For example, to use the **WhatIf** parameter of the `New-Alias` cmdlet, type the following:</span></span>

```powershell
-WhatIf
```

## <a name="parameter-sets"></a><span data-ttu-id="00b35-144">Conjuntos de parâmetros</span><span class="sxs-lookup"><span data-stu-id="00b35-144">Parameter Sets</span></span>

<span data-ttu-id="00b35-145">Os parâmetros de um comando são listados em conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="00b35-145">The parameters of a command are listed in parameter sets.</span></span> <span data-ttu-id="00b35-146">Os conjuntos de parâmetros são semelhantes aos parágrafos de um diagrama de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="00b35-146">Parameter sets look like the paragraphs of a syntax diagram.</span></span>

<span data-ttu-id="00b35-147">O `New-Alias` cmdlet tem um conjunto de parâmetros, mas muitos cmdlets têm vários conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="00b35-147">The `New-Alias` cmdlet has one parameter set, but many cmdlets have multiple parameter sets.</span></span> <span data-ttu-id="00b35-148">Alguns dos parâmetros de cmdlet são exclusivos para um conjunto de parâmetros e outros aparecem em vários conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="00b35-148">Some of the cmdlet parameters are unique to a parameter set, and others appear in multiple parameter sets.</span></span> <span data-ttu-id="00b35-149">Cada conjunto de parâmetros representa o formato de um comando válido.</span><span class="sxs-lookup"><span data-stu-id="00b35-149">Each parameter set represents the format of a valid command.</span></span> <span data-ttu-id="00b35-150">Um conjunto de parâmetros inclui apenas parâmetros que podem ser usados juntos em um comando.</span><span class="sxs-lookup"><span data-stu-id="00b35-150">A parameter set includes only parameters that can be used together in a command.</span></span> <span data-ttu-id="00b35-151">Se os parâmetros não puderem ser usados no mesmo comando, eles aparecerão em conjuntos de parâmetros separados.</span><span class="sxs-lookup"><span data-stu-id="00b35-151">If parameters cannot be used in the same command, they appear in separate parameter sets.</span></span>

<span data-ttu-id="00b35-152">Por exemplo, o cmdlet [Get-aleatório](xref:Microsoft.PowerShell.Utility.Get-Random) tem os seguintes conjuntos de parâmetros:</span><span class="sxs-lookup"><span data-stu-id="00b35-152">For example, the [Get-Random](xref:Microsoft.PowerShell.Utility.Get-Random) cmdlet has the following parameter sets:</span></span>

```powershell
Get-Random [[-Maximum] <Object>] [-Minimum <Object>] [-SetSeed <int>]
[<CommonParameters>]

Get-Random [-InputObject] <Object[]> [-Count <int>] [-SetSeed <int>]
[<CommonParameters>]
```

<span data-ttu-id="00b35-153">O primeiro conjunto de parâmetros, que retorna um número aleatório, tem os parâmetros **mínimo** e **máximo** .</span><span class="sxs-lookup"><span data-stu-id="00b35-153">The first parameter set, which returns a random number, has the **Minimum** and **Maximum** parameters.</span></span> <span data-ttu-id="00b35-154">O segundo conjunto de parâmetros, que retorna um objeto selecionado aleatoriamente de um conjunto de objetos, inclui os parâmetros **InputObject** e **Count** .</span><span class="sxs-lookup"><span data-stu-id="00b35-154">The second parameter set, which returns a randomly selected object from a set of objects, includes the **InputObject** and **Count** parameters.</span></span> <span data-ttu-id="00b35-155">Ambos os conjuntos de parâmetros têm o parâmetro **setsemente** e os parâmetros comuns.</span><span class="sxs-lookup"><span data-stu-id="00b35-155">Both parameter sets have the **SetSeed** parameter and the common parameters.</span></span>

<span data-ttu-id="00b35-156">Esses conjuntos de parâmetros indicam que você pode usar os parâmetros **InputObject** e **Count** no mesmo comando, mas não pode usar os parâmetros **Maximum** e **Count** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="00b35-156">These parameter sets indicate that you can use the **InputObject** and **Count** parameters in the same command, but you cannot use the **Maximum** and **Count** parameters in the same command.</span></span>

<span data-ttu-id="00b35-157">Você indica qual conjunto de parâmetros deseja usar usando os parâmetros nesse conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="00b35-157">You indicate which parameter set you want to use by using the parameters in that parameter set.</span></span>

<span data-ttu-id="00b35-158">No entanto, cada cmdlet também tem um conjunto de parâmetros padrão.</span><span class="sxs-lookup"><span data-stu-id="00b35-158">However, every cmdlet also has a default parameter set.</span></span> <span data-ttu-id="00b35-159">O conjunto de parâmetros padrão é usado quando você não especifica parâmetros que são exclusivos para um conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="00b35-159">The default parameter set is used when you do not specify parameters that are unique to a parameter set.</span></span> <span data-ttu-id="00b35-160">Por exemplo, se você usar `Get-Random` sem parâmetros, o Windows PowerShell pressupõe que você está usando o conjunto de parâmetros **Number** e retorna um número aleatório.</span><span class="sxs-lookup"><span data-stu-id="00b35-160">For example, if you use `Get-Random` without parameters, Windows PowerShell assumes that you are using the **Number** parameter set and it returns a random number.</span></span>

<span data-ttu-id="00b35-161">Em cada conjunto de parâmetros, os parâmetros aparecem na ordem de posição.</span><span class="sxs-lookup"><span data-stu-id="00b35-161">In each parameter set, the parameters appear in position order.</span></span> <span data-ttu-id="00b35-162">A ordem dos parâmetros em um comando só é importante quando você omite os nomes de parâmetro opcionais.</span><span class="sxs-lookup"><span data-stu-id="00b35-162">The order of parameters in a command matters only when you omit the optional parameter names.</span></span> <span data-ttu-id="00b35-163">Quando os nomes de parâmetro são omitidos, o PowerShell atribui valores aos parâmetros por posição e tipo.</span><span class="sxs-lookup"><span data-stu-id="00b35-163">When parameter names are omitted, PowerShell assigns values to parameters by position and type.</span></span> <span data-ttu-id="00b35-164">Para obter mais informações sobre a posição do parâmetro, consulte `about_Parameters` .</span><span class="sxs-lookup"><span data-stu-id="00b35-164">For more information about parameter position, see `about_Parameters`.</span></span>

## <a name="symbols-in-syntax-diagrams"></a><span data-ttu-id="00b35-165">Símbolos em diagramas de sintaxe</span><span class="sxs-lookup"><span data-stu-id="00b35-165">Symbols in Syntax Diagrams</span></span>

<span data-ttu-id="00b35-166">O diagrama de sintaxe lista o nome do comando, os parâmetros de comando e os valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="00b35-166">The syntax diagram lists the command name, the command parameters, and the parameter values.</span></span> <span data-ttu-id="00b35-167">Ele também usa símbolos para mostrar como construir um comando válido.</span><span class="sxs-lookup"><span data-stu-id="00b35-167">It also uses symbols to show how to construct a valid command.</span></span>

<span data-ttu-id="00b35-168">Os diagramas de sintaxe usam os seguintes símbolos:</span><span class="sxs-lookup"><span data-stu-id="00b35-168">The syntax diagrams use the following symbols:</span></span>

- <span data-ttu-id="00b35-169">Um hífen `-` indica um nome de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="00b35-169">A hyphen `-` indicates a parameter name.</span></span> <span data-ttu-id="00b35-170">Em um comando, digite o hífen imediatamente antes do nome do parâmetro sem espaços intermediários, conforme mostrado no diagrama de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="00b35-170">In a command, type the hyphen immediately before the parameter name with no intervening spaces, as shown in the syntax diagram.</span></span>

  <span data-ttu-id="00b35-171">Por exemplo, para usar o parâmetro **Name** de `New-Alias` , digite:</span><span class="sxs-lookup"><span data-stu-id="00b35-171">For example, to use the **Name** parameter of `New-Alias`, type:</span></span>

  ```powershell
  -Name
  ```

- <span data-ttu-id="00b35-172">Colchetes angulares `<>` indicam texto de espaço reservado.</span><span class="sxs-lookup"><span data-stu-id="00b35-172">Angle brackets `<>` indicate placeholder text.</span></span> <span data-ttu-id="00b35-173">Você não digita os colchetes angulares ou o texto do espaço reservado em um comando.</span><span class="sxs-lookup"><span data-stu-id="00b35-173">You do not type the angle brackets or the placeholder text in a command.</span></span> <span data-ttu-id="00b35-174">Em vez disso, substitua-o pelo item que ele descreve.</span><span class="sxs-lookup"><span data-stu-id="00b35-174">Instead, you replace it with the item that it describes.</span></span>

  <span data-ttu-id="00b35-175">Os colchetes angulares são usados para identificar o tipo .NET do valor que um parâmetro pega.</span><span class="sxs-lookup"><span data-stu-id="00b35-175">Angle brackets are used to identify the .NET type of the value that a parameter takes.</span></span> <span data-ttu-id="00b35-176">Por exemplo, para usar o parâmetro **Name** do `New-Alias` cmdlet, você substitui o `<string>` por uma cadeia de caracteres, que é uma única palavra ou um grupo de palavras que são colocadas entre aspas.</span><span class="sxs-lookup"><span data-stu-id="00b35-176">For example, to use the **Name** parameter of the `New-Alias` cmdlet, you replace the `<string>` with a string, which is a single word or a group of words that are enclosed in quotation marks.</span></span>

- <span data-ttu-id="00b35-177">Os colchetes `[ ]` indicam itens opcionais.</span><span class="sxs-lookup"><span data-stu-id="00b35-177">Brackets `[ ]` indicate optional items.</span></span> <span data-ttu-id="00b35-178">Um parâmetro e seu valor podem ser opcionais ou o nome de um parâmetro obrigatório pode ser opcional.</span><span class="sxs-lookup"><span data-stu-id="00b35-178">A parameter and its value can be optional, or the name of a required parameter can be optional.</span></span>

  <span data-ttu-id="00b35-179">Por exemplo, o parâmetro de **Descrição** de `New-Alias` e seu valor são colocados entre colchetes porque ambos são opcionais.</span><span class="sxs-lookup"><span data-stu-id="00b35-179">For example, the **Description** parameter of `New-Alias` and its value are enclosed in brackets because they are both optional.</span></span>

  ```powershell
  [-Description <string>]
  ```

  <span data-ttu-id="00b35-180">Os colchetes também indicam que o valor do parâmetro de nome `<string>` é necessário, mas o nome do parâmetro, "Name", é opcional.</span><span class="sxs-lookup"><span data-stu-id="00b35-180">The brackets also indicate that the Name parameter value `<string>` is required, but the parameter name, "Name", is optional.</span></span>

  ```powershell
  [-Name] <string>
  ```

- <span data-ttu-id="00b35-181">Um colchete à direita e à esquerda `[]` anexado a um tipo .net indica que o parâmetro pode aceitar um ou vários valores desse tipo.</span><span class="sxs-lookup"><span data-stu-id="00b35-181">A right and left bracket `[]` appended to a .NET type indicates that the parameter can accept one or multiple values of that type.</span></span> <span data-ttu-id="00b35-182">Digite os valores em uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="00b35-182">Enter the values in a comma-separated list.</span></span>

  <span data-ttu-id="00b35-183">Por exemplo, o parâmetro **Name** do `New-Alias` cmdlet usa apenas uma cadeia de caracteres, mas o parâmetro **Name** de [Get-Process](xref:Microsoft.PowerShell.Management.Get-Process) pode usar uma ou várias cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="00b35-183">For example, the **Name** parameter of the `New-Alias` cmdlet takes only one string, but the **Name** parameter of [Get-Process](xref:Microsoft.PowerShell.Management.Get-Process) can take one or many strings.</span></span>

  ```powershell
  New-Alias [-Name] <string>

  New-Alias -Name MyAlias
  ```

  ```powershell
  Get-Process [-Name] <string[]>

  Get-Process -Name Explorer, Winlogon, Services
  ```

- <span data-ttu-id="00b35-184">Chaves `{}` indicam uma "Enumeração", que é um conjunto de valores válidos para um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="00b35-184">Braces `{}` indicate an "enumeration," which is a set of valid values for a parameter.</span></span>

  <span data-ttu-id="00b35-185">Os valores nas chaves são separados por barras verticais `|` .</span><span class="sxs-lookup"><span data-stu-id="00b35-185">The values in the braces are separated by vertical bars `|`.</span></span> <span data-ttu-id="00b35-186">Essas barras indicam uma opção "exclusiva ou", o que significa que você pode escolher apenas um valor do conjunto de valores que estão listados dentro das chaves.</span><span class="sxs-lookup"><span data-stu-id="00b35-186">These bars indicate an "exclusive OR" choice, meaning that you can choose only one value from the set of values that are listed inside the braces.</span></span>

  <span data-ttu-id="00b35-187">Por exemplo, a sintaxe para o `New-Alias` cmdlet inclui a seguinte enumeração de valor para o parâmetro de **opção** :</span><span class="sxs-lookup"><span data-stu-id="00b35-187">For example, the syntax for the `New-Alias` cmdlet includes the following value enumeration for the **Option** parameter:</span></span>

  ```powershell
  -Option {None | ReadOnly | Constant | Private | AllScope}
  ```

  <span data-ttu-id="00b35-188">As chaves e as barras verticais indicam que você pode escolher qualquer um dos valores listados para o parâmetro de **opção** , como "ReadOnly" ou "alscope".</span><span class="sxs-lookup"><span data-stu-id="00b35-188">The braces and vertical bars indicate that you can choose any one of the listed values for the **Option** parameter, such as "ReadOnly" or "AllScope".</span></span>

  ```powershell
  -Option ReadOnly
  ```

## <a name="optional-items"></a><span data-ttu-id="00b35-189">Itens opcionais</span><span class="sxs-lookup"><span data-stu-id="00b35-189">Optional Items</span></span>

<span data-ttu-id="00b35-190">Os colchetes `[]` envolvem itens opcionais.</span><span class="sxs-lookup"><span data-stu-id="00b35-190">Brackets `[]` surround optional items.</span></span> <span data-ttu-id="00b35-191">Por exemplo, na `New-Alias` Descrição da sintaxe do cmdlet, o parâmetro de **escopo** é opcional.</span><span class="sxs-lookup"><span data-stu-id="00b35-191">For example, in the `New-Alias` cmdlet syntax description, the **Scope** parameter is optional.</span></span> <span data-ttu-id="00b35-192">Isso é indicado na sintaxe pelos colchetes em volta do nome do parâmetro e do tipo:</span><span class="sxs-lookup"><span data-stu-id="00b35-192">This is indicated in the syntax by the brackets around the parameter name and type:</span></span>

```powershell
[-Scope <string>]
```

<span data-ttu-id="00b35-193">Ambos os exemplos a seguir são usos corretos do `New-Alias` cmdlet:</span><span class="sxs-lookup"><span data-stu-id="00b35-193">Both the following examples are correct uses of the `New-Alias` cmdlet:</span></span>

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd -Value Update-TypeData -Scope Global
```

<span data-ttu-id="00b35-194">Um nome de parâmetro pode ser opcional, mesmo se o valor para esse parâmetro for necessário.</span><span class="sxs-lookup"><span data-stu-id="00b35-194">A parameter name can be optional even if the value for that parameter is required.</span></span> <span data-ttu-id="00b35-195">Isso é indicado na sintaxe pelos colchetes em volta do nome do parâmetro, mas não do tipo de parâmetro, como neste exemplo do `New-Alias` cmdlet:</span><span class="sxs-lookup"><span data-stu-id="00b35-195">This is indicated in the syntax by the brackets around the parameter name but not the parameter type, as in this example from the `New-Alias` cmdlet:</span></span>

```powershell
[-Name] <string> [-Value] <string>
```

<span data-ttu-id="00b35-196">Os comandos a seguir usam corretamente o `New-Alias` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="00b35-196">The following commands correctly use the `New-Alias` cmdlet.</span></span> <span data-ttu-id="00b35-197">Os comandos produzem o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="00b35-197">The commands produce the same result.</span></span>

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd Update-TypeData
New-Alias utd -Value Update-TypeData
New-Alias utd Update-TypeData
```

<span data-ttu-id="00b35-198">Se o nome do parâmetro não estiver incluído na instrução como tipada, o Windows PowerShell tentará usar a posição dos argumentos para atribuir os valores aos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="00b35-198">If the parameter name is not included in the statement as typed, Windows PowerShell tries to use the position of the arguments to assign the values to parameters.</span></span>

<span data-ttu-id="00b35-199">O exemplo a seguir não está completo:</span><span class="sxs-lookup"><span data-stu-id="00b35-199">The following example is not complete:</span></span>

```powershell
New-Alias utd
```

<span data-ttu-id="00b35-200">Esse cmdlet requer valores para os parâmetros **Name** e **Value** .</span><span class="sxs-lookup"><span data-stu-id="00b35-200">This cmdlet requires values for both the **Name** and **Value** parameters.</span></span>

<span data-ttu-id="00b35-201">Em exemplos de sintaxe, os colchetes também são usados na nomeação e na conversão para tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="00b35-201">In syntax examples, brackets are also used in naming and casting to .NET Framework types.</span></span> <span data-ttu-id="00b35-202">Nesse contexto, os colchetes não indicam que um elemento é opcional.</span><span class="sxs-lookup"><span data-stu-id="00b35-202">In this context, brackets do not indicate an element is optional.</span></span>

## <a name="see-also"></a><span data-ttu-id="00b35-203">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="00b35-203">SEE ALSO</span></span>

- [<span data-ttu-id="00b35-204">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="00b35-204">about_Parameters</span></span>](about_Parameters.md)
- [<span data-ttu-id="00b35-205">Get-Command</span><span class="sxs-lookup"><span data-stu-id="00b35-205">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)
- [<span data-ttu-id="00b35-206">Get-Help</span><span class="sxs-lookup"><span data-stu-id="00b35-206">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)
