---
description: Descreve como as variáveis armazenam valores que podem ser usados no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Variables
ms.openlocfilehash: 59a611cf49635f0391d3f3cc18bcf6d06a688638
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196138"
---
# <a name="about-variables"></a><span data-ttu-id="054a2-104">Sobre variáveis</span><span class="sxs-lookup"><span data-stu-id="054a2-104">About Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="054a2-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="054a2-105">Short description</span></span>

<span data-ttu-id="054a2-106">Descreve como as variáveis armazenam valores que podem ser usados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="054a2-106">Describes how variables store values that can be used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="054a2-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="054a2-107">Long description</span></span>

<span data-ttu-id="054a2-108">Você pode armazenar todos os tipos de valores em variáveis do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="054a2-108">You can store all types of values in PowerShell variables.</span></span> <span data-ttu-id="054a2-109">Por exemplo, armazene os resultados de comandos e armazene os elementos que são usados em comandos e expressões, como nomes, caminhos, configurações e valores.</span><span class="sxs-lookup"><span data-stu-id="054a2-109">For example, store the results of commands, and store elements that are used in commands and expressions, such as names, paths, settings, and values.</span></span>

<span data-ttu-id="054a2-110">Uma variável é uma unidade de memória na qual os valores são armazenados.</span><span class="sxs-lookup"><span data-stu-id="054a2-110">A variable is a unit of memory in which values are stored.</span></span> <span data-ttu-id="054a2-111">No PowerShell, as variáveis são representadas por cadeias de caracteres de texto que começam com um cifrão ( `$` ), como `$a` , `$process` ou `$my_var` .</span><span class="sxs-lookup"><span data-stu-id="054a2-111">In PowerShell, variables are represented by text strings that begin with a dollar sign (`$`), such as `$a`, `$process`, or `$my_var`.</span></span>

<span data-ttu-id="054a2-112">Nomes de variáveis não diferenciam maiúsculas de minúsculas e podem incluir espaços e caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="054a2-112">Variable names aren't case-sensitive, and can include spaces and special characters.</span></span> <span data-ttu-id="054a2-113">Porém, os nomes de variáveis que incluem caracteres especiais e espaços são difíceis de usar e devem ser evitados.</span><span class="sxs-lookup"><span data-stu-id="054a2-113">But, variable names that include special characters and spaces are difficult to use and should be avoided.</span></span> <span data-ttu-id="054a2-114">Para obter mais informações, consulte [nomes de variáveis que incluem caracteres especiais](#variable-names-that-include-special-characters).</span><span class="sxs-lookup"><span data-stu-id="054a2-114">For more information, see [Variable names that include special characters](#variable-names-that-include-special-characters).</span></span>

<span data-ttu-id="054a2-115">Há vários tipos diferentes de variáveis no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="054a2-115">There are several different types of variables in PowerShell.</span></span>

- <span data-ttu-id="054a2-116">Variáveis criadas pelo usuário: as variáveis criadas pelo usuário são criadas e mantidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="054a2-116">User-created variables: User-created variables are created and maintained by the user.</span></span> <span data-ttu-id="054a2-117">Por padrão, as variáveis que você cria na linha de comando do PowerShell existem somente enquanto a janela do PowerShell está aberta.</span><span class="sxs-lookup"><span data-stu-id="054a2-117">By default, the variables that you create at the PowerShell command line exist only while the PowerShell window is open.</span></span> <span data-ttu-id="054a2-118">Quando as janelas do PowerShell são fechadas, as variáveis são excluídas.</span><span class="sxs-lookup"><span data-stu-id="054a2-118">When the PowerShell windows is closed, the variables are deleted.</span></span> <span data-ttu-id="054a2-119">Para salvar uma variável, adicione-a ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="054a2-119">To save a variable, add it to your PowerShell profile.</span></span> <span data-ttu-id="054a2-120">Você também pode criar variáveis em scripts com escopo global, de script ou local.</span><span class="sxs-lookup"><span data-stu-id="054a2-120">You can also create variables in scripts with global, script, or local scope.</span></span>

- <span data-ttu-id="054a2-121">Variáveis automáticas: as variáveis automáticas armazenam o estado do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="054a2-121">Automatic variables: Automatic variables store the state of PowerShell.</span></span> <span data-ttu-id="054a2-122">Essas variáveis são criadas pelo PowerShell e o PowerShell altera seus valores conforme necessário para manter sua precisão.</span><span class="sxs-lookup"><span data-stu-id="054a2-122">These variables are created by PowerShell, and PowerShell changes their values as required to maintain their accuracy.</span></span> <span data-ttu-id="054a2-123">Os usuários não podem alterar o valor dessas variáveis.</span><span class="sxs-lookup"><span data-stu-id="054a2-123">Users can't change the value of these variables.</span></span> <span data-ttu-id="054a2-124">Por exemplo, a `$PSHOME` variável armazena o caminho para o diretório de instalação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="054a2-124">For example, the `$PSHOME` variable stores the path to the PowerShell installation directory.</span></span>

  <span data-ttu-id="054a2-125">Para obter mais informações, uma lista e uma descrição das variáveis automáticas, consulte [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="054a2-125">For more information, a list, and a description of the automatic variables, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

- <span data-ttu-id="054a2-126">Variáveis de preferência: variáveis de preferência armazenam preferências do usuário para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="054a2-126">Preference variables: Preference variables store user preferences for PowerShell.</span></span> <span data-ttu-id="054a2-127">Essas variáveis são criadas pelo PowerShell e preenchidas com valores padrão.</span><span class="sxs-lookup"><span data-stu-id="054a2-127">These variables are created by PowerShell and are populated with default values.</span></span> <span data-ttu-id="054a2-128">Os usuários podem alterar os valores dessas variáveis.</span><span class="sxs-lookup"><span data-stu-id="054a2-128">Users can change the values of these variables.</span></span> <span data-ttu-id="054a2-129">Por exemplo, a `$MaximumHistoryCount` variável determina o número máximo de entradas no histórico de sessão.</span><span class="sxs-lookup"><span data-stu-id="054a2-129">For example, the `$MaximumHistoryCount` variable determines the maximum number of entries in the session history.</span></span>

  <span data-ttu-id="054a2-130">Para obter mais informações, uma lista e uma descrição das variáveis de preferência, consulte [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="054a2-130">For more information, a list, and a description of the preference variables, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

## <a name="working-with-variables"></a><span data-ttu-id="054a2-131">Trabalhando com variáveis</span><span class="sxs-lookup"><span data-stu-id="054a2-131">Working with variables</span></span>

<span data-ttu-id="054a2-132">Para criar uma nova variável, use uma instrução de atribuição para atribuir um valor à variável.</span><span class="sxs-lookup"><span data-stu-id="054a2-132">To create a new variable, use an assignment statement to assign a value to the variable.</span></span> <span data-ttu-id="054a2-133">Você não precisa declarar a variável antes de usá-la.</span><span class="sxs-lookup"><span data-stu-id="054a2-133">You don't have to declare the variable before using it.</span></span> <span data-ttu-id="054a2-134">O valor padrão de todas as variáveis é `$null` .</span><span class="sxs-lookup"><span data-stu-id="054a2-134">The default value of all variables is `$null`.</span></span>

<span data-ttu-id="054a2-135">Para obter uma lista de todas as variáveis em sua sessão do PowerShell, digite `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="054a2-135">To get a list of all the variables in your PowerShell session, type `Get-Variable`.</span></span> <span data-ttu-id="054a2-136">Os nomes de variáveis são exibidos sem o sinal de dólar ( `$` ) precedente que é usado para referenciar variáveis.</span><span class="sxs-lookup"><span data-stu-id="054a2-136">The variable names are displayed without the preceding dollar (`$`) sign that is used to reference variables.</span></span>

<span data-ttu-id="054a2-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="054a2-137">For example:</span></span>

```powershell
$MyVariable = 1, 2, 3

$Path = "C:\Windows\System32"
```

<span data-ttu-id="054a2-138">As variáveis são úteis para armazenar os resultados dos comandos.</span><span class="sxs-lookup"><span data-stu-id="054a2-138">Variables are useful for storing the results of commands.</span></span>

<span data-ttu-id="054a2-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="054a2-139">For example:</span></span>

```powershell
$Processes = Get-Process

$Today = (Get-Date).DateTime
```

<span data-ttu-id="054a2-140">Para exibir o valor de uma variável, digite o nome da variável, precedido por um cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="054a2-140">To display the value of a variable, type the variable name, preceded by a dollar sign (`$`).</span></span>

<span data-ttu-id="054a2-141">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="054a2-141">For example:</span></span>

```powershell
$MyVariable
```

```Output
1
2
3
```

```powershell
$Today
```

```Output
Tuesday, September 3, 2019 09:46:46
```

<span data-ttu-id="054a2-142">Para alterar o valor de uma variável, atribua um novo valor à variável.</span><span class="sxs-lookup"><span data-stu-id="054a2-142">To change the value of a variable, assign a new value to the variable.</span></span>

<span data-ttu-id="054a2-143">Os exemplos a seguir exibem o valor da `$MyVariable` variável, altera o valor da variável e, em seguida, exibe o novo valor.</span><span class="sxs-lookup"><span data-stu-id="054a2-143">The following examples display the value of the `$MyVariable` variable, changes the value of the variable, and then displays the new value.</span></span>

```powershell
$MyVariable = 1, 2, 3
$MyVariable
```

```Output
1
2
3
```

```powershell
$MyVariable = "The green cat."
$MyVariable
```

```Output
The green cat.
```

<span data-ttu-id="054a2-144">Para excluir o valor de uma variável, use o `Clear-Variable` cmdlet ou altere o valor para `$null` .</span><span class="sxs-lookup"><span data-stu-id="054a2-144">To delete the value of a variable, use the `Clear-Variable` cmdlet or change the value to `$null`.</span></span>

```powershell
Clear-Variable -Name MyVariable
```

```powershell
$MyVariable = $null
```

<span data-ttu-id="054a2-145">Para excluir a variável, use [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) ou [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item).</span><span class="sxs-lookup"><span data-stu-id="054a2-145">To delete the variable, use [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) or [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item).</span></span>

```powershell
Remove-Variable -Name MyVariable
```

```powershell
Remove-Item -Path Variable:\MyVariable
```

## <a name="types-of-variables"></a><span data-ttu-id="054a2-146">Tipos de variáveis</span><span class="sxs-lookup"><span data-stu-id="054a2-146">Types of variables</span></span>

<span data-ttu-id="054a2-147">Você pode armazenar qualquer tipo de objeto em uma variável, incluindo inteiros, cadeias de caracteres, matrizes e tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="054a2-147">You can store any type of object in a variable, including integers, strings, arrays, and hash tables.</span></span> <span data-ttu-id="054a2-148">E os objetos que representam processos, serviços, logs de eventos e computadores.</span><span class="sxs-lookup"><span data-stu-id="054a2-148">And, objects that represent processes, services, event logs, and computers.</span></span>

<span data-ttu-id="054a2-149">As variáveis do PowerShell são tipificadas de forma flexível, o que significa que elas não são limitadas a um tipo específico de objeto.</span><span class="sxs-lookup"><span data-stu-id="054a2-149">PowerShell variables are loosely typed, which means that they aren't limited to a particular type of object.</span></span> <span data-ttu-id="054a2-150">Uma única variável pode até mesmo conter uma coleção, ou matriz, de diferentes tipos de objetos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="054a2-150">A single variable can even contain a collection, or array, of different types of objects at the same time.</span></span>

<span data-ttu-id="054a2-151">O tipo de dados de uma variável é determinado pelos tipos .NET dos valores da variável.</span><span class="sxs-lookup"><span data-stu-id="054a2-151">The data type of a variable is determined by the .NET types of the values of the variable.</span></span> <span data-ttu-id="054a2-152">Para exibir o tipo de objeto de uma variável, use [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member).</span><span class="sxs-lookup"><span data-stu-id="054a2-152">To view a variable's object type, use [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member).</span></span>

<span data-ttu-id="054a2-153">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="054a2-153">For example:</span></span>

```powershell
$a = 12                         # System.Int32
$a = "Word"                     # System.String
$a = 12, "Word"                 # array of System.Int32, System.String
$a = Get-ChildItem C:\Windows   # FileInfo and DirectoryInfo types
```

<span data-ttu-id="054a2-154">Você pode usar um atributo de tipo e uma notação de conversão para garantir que uma variável só possa conter tipos de objeto ou objetos específicos que possam ser convertidos nesse tipo.</span><span class="sxs-lookup"><span data-stu-id="054a2-154">You can use a type attribute and cast notation to ensure that a variable can contain only specific object types or objects that can be converted to that type.</span></span> <span data-ttu-id="054a2-155">Se você tentar atribuir um valor de outro tipo, o PowerShell tentará converter o valor em seu tipo.</span><span class="sxs-lookup"><span data-stu-id="054a2-155">If you try to assign a value of another type, PowerShell tries to convert the value to its type.</span></span> <span data-ttu-id="054a2-156">Se o tipo não puder ser convertido, a instrução de atribuição falhará.</span><span class="sxs-lookup"><span data-stu-id="054a2-156">If the type can't be converted, the assignment statement fails.</span></span>

<span data-ttu-id="054a2-157">Para usar notação de conversão, insira um nome de tipo, entre colchetes, antes do nome da variável (no lado esquerdo da instrução de atribuição).</span><span class="sxs-lookup"><span data-stu-id="054a2-157">To use cast notation, enter a type name, enclosed in brackets, before the variable name (on the left side of the assignment statement).</span></span> <span data-ttu-id="054a2-158">O exemplo a seguir cria uma `$number` variável que pode conter apenas inteiros, uma `$words` variável que pode conter apenas cadeias de caracteres e uma `$dates` variável que pode conter somente objetos **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="054a2-158">The following example creates a `$number` variable that can contain only integers, a `$words` variable that can contain only strings, and a `$dates` variable that can contain only **DateTime** objects.</span></span>

```powershell
[int]$number = 8
$number = "12345"  # The string is converted to an integer.
$number = "Hello"
```

```Output
Cannot convert value "Hello" to type "System.Int32". Error: "Input string was
 not in a correct format."
At line:1 char:1
+ $number = "Hello"
+ ~~~~~~~~~~~~~~~~~
+ CategoryInfo          : MetadataError: (:) [],
    ArgumentTransformationMetadataException
+ FullyQualifiedErrorId : RuntimeException
```

```powershell
[string]$words = "Hello"
$words = 2       # The integer is converted to a string.
$words += 10     # The plus (+) sign concatenates the strings.
$words
```

```Output
210
```

```powershell
[datetime] $dates = "09/12/91"  # The string is converted to a DateTime object.
$dates
```

```Output
Thursday, September 12, 1991 00:00:00
```

```powershell
$dates = 10    # The integer is converted to a DateTime object.
$dates
```

```Output
Monday, January 1, 0001 00:00:00
```

## <a name="using-variables-in-commands-and-expressions"></a><span data-ttu-id="054a2-159">Usando variáveis em comandos e expressões</span><span class="sxs-lookup"><span data-stu-id="054a2-159">Using variables in commands and expressions</span></span>

<span data-ttu-id="054a2-160">Para usar uma variável em um comando ou expressão, digite o nome da variável, precedido pelo sinal de dólar ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="054a2-160">To use a variable in a command or expression, type the variable name, preceded by the dollar (`$`) sign.</span></span>

<span data-ttu-id="054a2-161">Se o nome da variável e o sinal de dólar não estiverem entre aspas, ou se estiverem dentro das marcas de aspas duplas `"` , o valor da variável será usado no comando ou na expressão.</span><span class="sxs-lookup"><span data-stu-id="054a2-161">If the variable name and dollar sign aren't enclosed in quotation marks, or if they're enclosed in double quotation (`"`) marks, the value of the variable is used in the command or expression.</span></span>

<span data-ttu-id="054a2-162">Se o nome da variável e o cifrão estiverem entre aspas simples ( `'` ), o nome da variável será usado na expressão.</span><span class="sxs-lookup"><span data-stu-id="054a2-162">If the variable name and dollar sign are enclosed in single quotation (`'`) marks, the variable name is used in the expression.</span></span>

<span data-ttu-id="054a2-163">Para obter mais informações sobre como usar aspas no PowerShell, consulte [about_Quoting_Rules](about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="054a2-163">For more information about using quotation marks in PowerShell, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

<span data-ttu-id="054a2-164">Este exemplo obtém o valor da `$PROFILE` variável, que é o caminho para o arquivo de perfil de usuário do PowerShell no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="054a2-164">This example gets the value of the `$PROFILE` variable, which is the path to the PowerShell user profile file in the PowerShell console.</span></span>

```powershell
$PROFILE
```

```Output
C:\Users\User01\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1
```

<span data-ttu-id="054a2-165">Neste exemplo, são mostrados dois comandos que podem abrir o perfil do PowerShell no **notepad.exe** .</span><span class="sxs-lookup"><span data-stu-id="054a2-165">In this example, two commands are shown that can open the PowerShell profile in **notepad.exe** .</span></span> <span data-ttu-id="054a2-166">O exemplo com marcas de aspas duplas ( `"` ) usa o valor da variável.</span><span class="sxs-lookup"><span data-stu-id="054a2-166">The example with double-quote (`"`) marks uses the variable's value.</span></span>

```powershell
notepad $PROFILE

notepad "$PROFILE"
```

<span data-ttu-id="054a2-167">Os exemplos a seguir usam marcas de aspas simples ( `'` ) que tratam a variável como texto literal.</span><span class="sxs-lookup"><span data-stu-id="054a2-167">The following examples use single-quote (`'`) marks that treat the variable as literal text.</span></span>

```powershell
'$PROFILE'
```

```Output
$PROFILE
```

```powershell
'Use the $PROFILE variable.'
```

```Output
Use the $PROFILE variable.
```

## <a name="variable-names-that-include-special-characters"></a><span data-ttu-id="054a2-168">Nomes de variáveis que incluem caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="054a2-168">Variable names that include special characters</span></span>

<span data-ttu-id="054a2-169">Os nomes de variáveis começam com um sinal de dólar ( `$` ) e podem incluir caracteres alfanuméricos e caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="054a2-169">Variable names begin with a dollar (`$`) sign and can include alphanumeric characters and special characters.</span></span> <span data-ttu-id="054a2-170">O comprimento do nome da variável é limitado apenas pela memória disponível.</span><span class="sxs-lookup"><span data-stu-id="054a2-170">The variable name length is limited only by available memory.</span></span>

<span data-ttu-id="054a2-171">A prática recomendada é que os nomes de variáveis incluam apenas caracteres alfanuméricos e o caractere sublinhado ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="054a2-171">The best practice is that variable names include only alphanumeric characters and the underscore (`_`) character.</span></span> <span data-ttu-id="054a2-172">Nomes de variáveis que incluem espaços e outros caracteres especiais são difíceis de usar e devem ser evitados.</span><span class="sxs-lookup"><span data-stu-id="054a2-172">Variable names that include spaces and other special characters, are difficult to use and should be avoided.</span></span>

<span data-ttu-id="054a2-173">Os nomes de variáveis alfanuméricas podem conter estes caracteres:</span><span class="sxs-lookup"><span data-stu-id="054a2-173">Alphanumeric variable names can contain these characters:</span></span>

- <span data-ttu-id="054a2-174">Caracteres Unicode destas categorias: **Lu** , **ll** , **lt** , **LM** , **lo** ou **ND** .</span><span class="sxs-lookup"><span data-stu-id="054a2-174">Unicode characters from these categories: **Lu** , **Ll** , **Lt** , **Lm** , **Lo** , or **Nd** .</span></span>
- <span data-ttu-id="054a2-175">Caractere de sublinhado ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="054a2-175">Underscore (`_`) character.</span></span>
- <span data-ttu-id="054a2-176">Caractere de ponto de interrogação ( `?` ).</span><span class="sxs-lookup"><span data-stu-id="054a2-176">Question mark (`?`) character.</span></span>

<span data-ttu-id="054a2-177">A lista a seguir contém as descrições de categoria Unicode.</span><span class="sxs-lookup"><span data-stu-id="054a2-177">The following list contains the Unicode category descriptions.</span></span> <span data-ttu-id="054a2-178">Para obter mais informações, consulte [UnicodeCategory](/dotnet/api/system.globalization.unicodecategory).</span><span class="sxs-lookup"><span data-stu-id="054a2-178">For more information, see [UnicodeCategory](/dotnet/api/system.globalization.unicodecategory).</span></span>

- <span data-ttu-id="054a2-179">**Lu** -UppercaseLetter</span><span class="sxs-lookup"><span data-stu-id="054a2-179">**Lu** - UppercaseLetter</span></span>
- <span data-ttu-id="054a2-180">**Ll** -LowercaseLetter</span><span class="sxs-lookup"><span data-stu-id="054a2-180">**Ll** - LowercaseLetter</span></span>
- <span data-ttu-id="054a2-181">**Lt** -TitlecaseLetter</span><span class="sxs-lookup"><span data-stu-id="054a2-181">**Lt** - TitlecaseLetter</span></span>
- <span data-ttu-id="054a2-182">**LM** -ModifierLetter</span><span class="sxs-lookup"><span data-stu-id="054a2-182">**Lm** - ModifierLetter</span></span>
- <span data-ttu-id="054a2-183">**Lo** OtherLetter</span><span class="sxs-lookup"><span data-stu-id="054a2-183">**Lo** - OtherLetter</span></span>
- <span data-ttu-id="054a2-184">**ND** -DecimalDigitNumber</span><span class="sxs-lookup"><span data-stu-id="054a2-184">**Nd** - DecimalDigitNumber</span></span>

<span data-ttu-id="054a2-185">Para criar ou exibir um nome de variável que inclua espaços ou caracteres especiais, coloque o nome da variável com os caracteres de chaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="054a2-185">To create or display a variable name that includes spaces or special characters, enclose the variable name with the curly braces (`{}`) characters.</span></span>
<span data-ttu-id="054a2-186">As chaves direcionam o PowerShell para interpretar os caracteres do nome da variável como literais.</span><span class="sxs-lookup"><span data-stu-id="054a2-186">The curly braces direct PowerShell to interpret the variable name's characters as literals.</span></span>

<span data-ttu-id="054a2-187">Os nomes de variável de caracteres especiais podem conter estes caracteres:</span><span class="sxs-lookup"><span data-stu-id="054a2-187">Special character variable names can contain these characters:</span></span>

- <span data-ttu-id="054a2-188">Qualquer caractere Unicode, com as seguintes exceções:</span><span class="sxs-lookup"><span data-stu-id="054a2-188">Any Unicode character, with the following exceptions:</span></span>
  - <span data-ttu-id="054a2-189">O caractere de fechamento de chave ( `}` ) (U + 007D).</span><span class="sxs-lookup"><span data-stu-id="054a2-189">The closing curly brace (`}`) character (U+007D).</span></span>
  - <span data-ttu-id="054a2-190">O caractere de acento grave ( `` ` `` ) (U + 0060).</span><span class="sxs-lookup"><span data-stu-id="054a2-190">The backtick (`` ` ``) character (U+0060).</span></span> <span data-ttu-id="054a2-191">A marca de fim é usada para escapar caracteres Unicode para que sejam tratados como literais.</span><span class="sxs-lookup"><span data-stu-id="054a2-191">The backtick is used to escape Unicode characters so they're treated as literals.</span></span>

<span data-ttu-id="054a2-192">O PowerShell tem variáveis reservadas, como,, `$$` `$?` `$^` e `$_` que contêm caracteres alfanuméricos e especiais.</span><span class="sxs-lookup"><span data-stu-id="054a2-192">PowerShell has reserved variables such as `$$`, `$?`, `$^`, and `$_` that contain alphanumeric and special characters.</span></span> <span data-ttu-id="054a2-193">Para obter mais informações, consulte [about_Automatic_Variables](about_automatic_variables.md).</span><span class="sxs-lookup"><span data-stu-id="054a2-193">For more information, see [about_Automatic_Variables](about_automatic_variables.md).</span></span>

<span data-ttu-id="054a2-194">Por exemplo, o comando a seguir cria a variável chamada `save-items` .</span><span class="sxs-lookup"><span data-stu-id="054a2-194">For example, the following command creates the variable named `save-items`.</span></span> <span data-ttu-id="054a2-195">As chaves ( `{}` ) são necessárias porque o nome da variável inclui um `-` caractere especial hífen ().</span><span class="sxs-lookup"><span data-stu-id="054a2-195">The curly braces (`{}`) are needed because variable name includes a hyphen (`-`) special character.</span></span>

```powershell
${save-items} = "a", "b", "c"
${save-items}
```

```Output
a
b
c
```

<span data-ttu-id="054a2-196">O comando a seguir obtém os itens filho no diretório que é representado pela `ProgramFiles(x86)` variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="054a2-196">The following command gets the child items in the directory that is represented by the `ProgramFiles(x86)` environment variable.</span></span>

```powershell
Get-ChildItem ${env:ProgramFiles(x86)}
```

<span data-ttu-id="054a2-197">Para fazer referência a um nome de variável que inclui chaves, coloque o nome da variável entre chaves e use o caractere de acento grave para escapar das chaves.</span><span class="sxs-lookup"><span data-stu-id="054a2-197">To reference a variable name that includes braces, enclose the variable name in braces, and use the backtick character to escape the braces.</span></span> <span data-ttu-id="054a2-198">Por exemplo, para criar um tipo nomeado de variável `this{value}is` :</span><span class="sxs-lookup"><span data-stu-id="054a2-198">For example, to create a variable named `this{value}is` type:</span></span>

```powershell
${this`{value`}is} = "This variable name uses braces and backticks."
${this`{value`}is}
```

```Output
This variable name uses braces and backticks.
```

## <a name="variables-and-scope"></a><span data-ttu-id="054a2-199">Variáveis e escopo</span><span class="sxs-lookup"><span data-stu-id="054a2-199">Variables and scope</span></span>

<span data-ttu-id="054a2-200">Por padrão, as variáveis só estão disponíveis no escopo em que são criadas.</span><span class="sxs-lookup"><span data-stu-id="054a2-200">By default, variables are only available in the scope in which they're created.</span></span>

<span data-ttu-id="054a2-201">Por exemplo, uma variável que você cria em uma função está disponível somente dentro da função.</span><span class="sxs-lookup"><span data-stu-id="054a2-201">For example, a variable that you create in a function is available only within the function.</span></span> <span data-ttu-id="054a2-202">Uma variável que você cria em um script está disponível somente dentro do script.</span><span class="sxs-lookup"><span data-stu-id="054a2-202">A variable that you create in a script is available only within the script.</span></span> <span data-ttu-id="054a2-203">Se você criar um ponto-fonte do script, a variável será adicionada ao escopo atual.</span><span class="sxs-lookup"><span data-stu-id="054a2-203">If you dot-source the script, the variable is added to the current scope.</span></span> <span data-ttu-id="054a2-204">Para obter mais informações, consulte [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="054a2-204">For more information, see [about_Scopes](about_Scopes.md).</span></span>

<span data-ttu-id="054a2-205">Você pode usar um modificador de escopo para alterar o escopo padrão da variável.</span><span class="sxs-lookup"><span data-stu-id="054a2-205">You can use a scope modifier to change the default scope of the variable.</span></span> <span data-ttu-id="054a2-206">A expressão a seguir cria uma variável chamada `Computers` .</span><span class="sxs-lookup"><span data-stu-id="054a2-206">The following expression creates a variable named `Computers`.</span></span> <span data-ttu-id="054a2-207">A variável tem um escopo global, mesmo quando ela é criada em um script ou uma função.</span><span class="sxs-lookup"><span data-stu-id="054a2-207">The variable has a global scope, even when it's created in a script or function.</span></span>

```powershell
$Global:Computers = "Server01"
```

<span data-ttu-id="054a2-208">Para qualquer script ou comando que é executado fora da sessão, você precisa do `Using` modificador de escopo para inserir valores de variáveis do escopo da sessão de chamada, para que o código fora da sessão possa acessá-los.</span><span class="sxs-lookup"><span data-stu-id="054a2-208">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span>

<span data-ttu-id="054a2-209">Para obter mais informações, consulte [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="054a2-209">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="saving-variables"></a><span data-ttu-id="054a2-210">Salvando variáveis</span><span class="sxs-lookup"><span data-stu-id="054a2-210">Saving variables</span></span>

<span data-ttu-id="054a2-211">As variáveis que você cria estão disponíveis somente na sessão em que você as cria.</span><span class="sxs-lookup"><span data-stu-id="054a2-211">Variables that you create are available only in the session in which you create them.</span></span> <span data-ttu-id="054a2-212">Eles são perdidos quando você fecha sua sessão.</span><span class="sxs-lookup"><span data-stu-id="054a2-212">They're lost when you close your session.</span></span>

<span data-ttu-id="054a2-213">Para criar a variável em cada sessão do PowerShell que você iniciar, adicione a variável ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="054a2-213">To create the variable in every PowerShell session that you start, add the variable to your PowerShell profile.</span></span>

<span data-ttu-id="054a2-214">Por exemplo, para alterar o valor da `$VerbosePreference` variável em cada sessão do PowerShell, adicione o seguinte comando ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="054a2-214">For example, to change the value of the `$VerbosePreference` variable in every PowerShell session, add the following command to your PowerShell profile.</span></span>

```powershell
$VerbosePreference = "Continue"
```

<span data-ttu-id="054a2-215">Você pode adicionar esse comando ao seu perfil do PowerShell abrindo o `$PROFILE` arquivo em um editor de texto, como **notepad.exe** .</span><span class="sxs-lookup"><span data-stu-id="054a2-215">You can add this command to your PowerShell profile by opening the `$PROFILE` file in a text editor, such as **notepad.exe** .</span></span> <span data-ttu-id="054a2-216">Para obter mais informações sobre perfis do PowerShell, consulte [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="054a2-216">For more information about PowerShell profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="the-variable-drive"></a><span data-ttu-id="054a2-217">A unidade Variable:</span><span class="sxs-lookup"><span data-stu-id="054a2-217">The Variable: drive</span></span>

<span data-ttu-id="054a2-218">O provedor de variáveis do PowerShell cria uma `Variable:` unidade que parece e age como uma unidade do sistema de arquivos, mas contém as variáveis em sua sessão e seus valores.</span><span class="sxs-lookup"><span data-stu-id="054a2-218">The PowerShell Variable provider creates a `Variable:` drive that looks and acts like a file system drive, but it contains the variables in your session and their values.</span></span>

<span data-ttu-id="054a2-219">Para alterar para a `Variable:` unidade, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="054a2-219">To change to the `Variable:` drive, use the following command:</span></span>

```powershell
Set-Location Variable:
```

<span data-ttu-id="054a2-220">Para listar os itens e variáveis na `Variable:` unidade, use os `Get-Item` `Get-ChildItem` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="054a2-220">To list the items and variables in the `Variable:` drive, use the `Get-Item` or `Get-ChildItem` cmdlets.</span></span>

```powershell
Get-ChildItem Variable:
```

<span data-ttu-id="054a2-221">Para obter o valor de uma variável específica, use a notação do sistema de arquivos para especificar o nome da unidade e o nome da variável.</span><span class="sxs-lookup"><span data-stu-id="054a2-221">To get the value of a particular variable, use file system notation to specify the name of the drive and the name of the variable.</span></span> <span data-ttu-id="054a2-222">Por exemplo, para obter a `$PSCulture` variável automática, use o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="054a2-222">For example, to get the `$PSCulture` automatic variable, use the following command.</span></span>

```powershell
Get-Item Variable:\PSCulture
```

```Output
Name                           Value
----                           -----
PSCulture                      en-US
```

<span data-ttu-id="054a2-223">Para exibir mais informações sobre a `Variable:` unidade e o provedor de variáveis do PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="054a2-223">To display more information about the `Variable:` drive and the PowerShell Variable provider, type:</span></span>

```powershell
Get-Help Variable
```

## <a name="variable-syntax-with-provider-paths"></a><span data-ttu-id="054a2-224">Sintaxe de variável com caminhos de provedor</span><span class="sxs-lookup"><span data-stu-id="054a2-224">Variable syntax with provider paths</span></span>

<span data-ttu-id="054a2-225">Você pode prefixar um caminho de provedor com o sinal de dólar ( `$` ) e acessar o conteúdo de qualquer provedor que implemente a interface [IContentCmdletProvider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) .</span><span class="sxs-lookup"><span data-stu-id="054a2-225">You can prefix a provider path with the dollar (`$`) sign, and access the content of any provider that implements the [IContentCmdletProvider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) interface.</span></span>

<span data-ttu-id="054a2-226">Os seguintes provedores internos do PowerShell dão suporte a esta notação:</span><span class="sxs-lookup"><span data-stu-id="054a2-226">The following built-in PowerShell providers support this notation:</span></span>

- [<span data-ttu-id="054a2-227">about_Environment_Provider</span><span class="sxs-lookup"><span data-stu-id="054a2-227">about_Environment_Provider</span></span>](about_Environment_Provider.md)
- [<span data-ttu-id="054a2-228">about_Variable_Provider</span><span class="sxs-lookup"><span data-stu-id="054a2-228">about_Variable_Provider</span></span>](about_Variable_Provider.md)
- [<span data-ttu-id="054a2-229">about_Function_Provider</span><span class="sxs-lookup"><span data-stu-id="054a2-229">about_Function_Provider</span></span>](about_Function_Provider.md)
- [<span data-ttu-id="054a2-230">about_Alias_Provider</span><span class="sxs-lookup"><span data-stu-id="054a2-230">about_Alias_Provider</span></span>](about_Alias_Provider.md)

## <a name="the-variable-cmdlets"></a><span data-ttu-id="054a2-231">Os cmdlets variáveis</span><span class="sxs-lookup"><span data-stu-id="054a2-231">The variable cmdlets</span></span>

<span data-ttu-id="054a2-232">O PowerShell inclui um conjunto de cmdlets que são projetados para gerenciar variáveis.</span><span class="sxs-lookup"><span data-stu-id="054a2-232">PowerShell includes a set of cmdlets that are designed to manage variables.</span></span>

<span data-ttu-id="054a2-233">Para listar os cmdlets, digite:</span><span class="sxs-lookup"><span data-stu-id="054a2-233">To list the cmdlets, type:</span></span>

```powershell
Get-Command -Noun Variable
```

<span data-ttu-id="054a2-234">Para obter ajuda para um cmdlet específico, digite:</span><span class="sxs-lookup"><span data-stu-id="054a2-234">To get help for a specific cmdlet, type:</span></span>

```powershell
Get-Help <cmdlet-name>
```

| <span data-ttu-id="054a2-235">Nome do Cmdlet</span><span class="sxs-lookup"><span data-stu-id="054a2-235">Cmdlet Name</span></span>       | <span data-ttu-id="054a2-236">Descrição</span><span class="sxs-lookup"><span data-stu-id="054a2-236">Description</span></span>                                |
| ---------------   | ------------------------------------------ |
| `Clear-Variable`  | <span data-ttu-id="054a2-237">Excluir o valor de uma variável.</span><span class="sxs-lookup"><span data-stu-id="054a2-237">Deletes the value of a variable.</span></span>           |
| `Get-Variable`    | <span data-ttu-id="054a2-238">Obtém as variáveis no console atual.</span><span class="sxs-lookup"><span data-stu-id="054a2-238">Gets the variables in the current console.</span></span> |
| `New-Variable`    | <span data-ttu-id="054a2-239">Cria uma nova variável.</span><span class="sxs-lookup"><span data-stu-id="054a2-239">Creates a new variable.</span></span>                    |
| `Remove-Variable` | <span data-ttu-id="054a2-240">Exclui uma variável e seu valor.</span><span class="sxs-lookup"><span data-stu-id="054a2-240">Deletes a variable and its value.</span></span>          |
| `Set-Variable`    | <span data-ttu-id="054a2-241">Altera o valor de uma variável.</span><span class="sxs-lookup"><span data-stu-id="054a2-241">Changes the value of a variable.</span></span>           |

## <a name="see-also"></a><span data-ttu-id="054a2-242">Confira também</span><span class="sxs-lookup"><span data-stu-id="054a2-242">See also</span></span>

[<span data-ttu-id="054a2-243">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="054a2-243">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="054a2-244">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="054a2-244">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="054a2-245">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="054a2-245">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="054a2-246">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="054a2-246">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="054a2-247">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="054a2-247">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="054a2-248">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="054a2-248">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="054a2-249">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="054a2-249">about_Remote_Variables</span></span>](about_Remote_Variables.md)
