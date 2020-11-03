---
description: Explica as seções de dados, que isolam cadeias de caracteres de texto e outros dados somente leitura da lógica de script.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_data_sections?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Data_Sections
ms.openlocfilehash: d45339bae42b1131e1dfb9618413a34e250a578e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196226"
---
# <a name="about-data-sections"></a><span data-ttu-id="49150-104">Sobre seções de dados</span><span class="sxs-lookup"><span data-stu-id="49150-104">About Data Sections</span></span>

## <a name="short-description"></a><span data-ttu-id="49150-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="49150-105">Short Description</span></span>
<span data-ttu-id="49150-106">Explica as seções de dados, que isolam cadeias de caracteres de texto e outros dados somente leitura da lógica de script.</span><span class="sxs-lookup"><span data-stu-id="49150-106">Explains Data sections, which isolate text strings and other read-only data from script logic.</span></span>

## <a name="long-description"></a><span data-ttu-id="49150-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="49150-107">Long Description</span></span>

<span data-ttu-id="49150-108">Os scripts projetados para o PowerShell podem ter uma ou mais seções de dados que contêm apenas dados.</span><span class="sxs-lookup"><span data-stu-id="49150-108">Scripts that are designed for PowerShell can have one or more Data sections that contain only data.</span></span> <span data-ttu-id="49150-109">Você pode incluir uma ou mais seções de dados em qualquer script, função ou função avançada.</span><span class="sxs-lookup"><span data-stu-id="49150-109">You can include one or more Data sections in any script, function, or advanced function.</span></span> <span data-ttu-id="49150-110">O conteúdo da seção de dados é restrito a um subconjunto especificado da linguagem de script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49150-110">The content of the Data section is restricted to a specified subset of the PowerShell scripting language.</span></span>

<span data-ttu-id="49150-111">Separar dados da lógica de código torna mais fácil identificar e gerenciar a lógica e os dados.</span><span class="sxs-lookup"><span data-stu-id="49150-111">Separating data from code logic makes it easier to identify and manage both logic and data.</span></span> <span data-ttu-id="49150-112">Ele permite que você tenha arquivos de recurso de cadeia de caracteres separados para texto, como mensagens de erro e cadeias de caracteres de ajuda.</span><span class="sxs-lookup"><span data-stu-id="49150-112">It lets you have separate string resource files for text, such as error messages and Help strings.</span></span> <span data-ttu-id="49150-113">Ele também isola a lógica de código, que facilita os testes de segurança e validação.</span><span class="sxs-lookup"><span data-stu-id="49150-113">It also isolates the code logic, which facilitates security and validation tests.</span></span>

<span data-ttu-id="49150-114">No PowerShell, a seção de dados é usada para dar suporte à internacionalização de script.</span><span class="sxs-lookup"><span data-stu-id="49150-114">In PowerShell, the Data section is used to support script internationalization.</span></span>
<span data-ttu-id="49150-115">Você pode usar seções de dados para facilitar a tarefa de isolar, localizar e processar cadeias de caracteres que serão convertidas em muitas linguagens de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="49150-115">You can use Data sections to make it easier to isolate, locate, and process strings that will be translated into many user interface (UI) languages.</span></span>

<span data-ttu-id="49150-116">A seção de dados é um recurso do PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="49150-116">The Data section is a PowerShell 2.0 feature.</span></span> <span data-ttu-id="49150-117">Scripts com seções de dados não serão executados no PowerShell 1,0 sem revisão.</span><span class="sxs-lookup"><span data-stu-id="49150-117">Scripts with Data sections will not run in PowerShell 1.0 without revision.</span></span>

### <a name="syntax"></a><span data-ttu-id="49150-118">Syntax</span><span class="sxs-lookup"><span data-stu-id="49150-118">Syntax</span></span>

<span data-ttu-id="49150-119">A sintaxe de uma seção de dados é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="49150-119">The syntax for a Data section is as follows:</span></span>

```
DATA [<variable-name>] [-supportedCommand <cmdlet-name>] {
    <Permitted content>
}
```

<span data-ttu-id="49150-120">A palavra-chave data é necessária.</span><span class="sxs-lookup"><span data-stu-id="49150-120">The Data keyword is required.</span></span> <span data-ttu-id="49150-121">Não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="49150-121">It is not case-sensitive.</span></span> <span data-ttu-id="49150-122">O conteúdo permitido é limitado aos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="49150-122">The permitted content is limited to the following elements:</span></span>

- <span data-ttu-id="49150-123">Todos os operadores do PowerShell, exceto `-match`</span><span class="sxs-lookup"><span data-stu-id="49150-123">All PowerShell operators, except `-match`</span></span>
- <span data-ttu-id="49150-124">`If``Else`instruções, e `ElseIf`</span><span class="sxs-lookup"><span data-stu-id="49150-124">`If`, `Else`, and `ElseIf` statements</span></span>
- <span data-ttu-id="49150-125">As seguintes variáveis automáticas:,,, `$PsCulture` `$PsUICulture` `$True` `$False` e `$Null`</span><span class="sxs-lookup"><span data-stu-id="49150-125">The following automatic variables: `$PsCulture`, `$PsUICulture`, `$True`, `$False`, and `$Null`</span></span>
- <span data-ttu-id="49150-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="49150-126">Comments</span></span>
- <span data-ttu-id="49150-127">Pipelines</span><span class="sxs-lookup"><span data-stu-id="49150-127">Pipelines</span></span>
- <span data-ttu-id="49150-128">Instruções separadas por ponto e vírgula ( `;` )</span><span class="sxs-lookup"><span data-stu-id="49150-128">Statements separated by semicolons (`;`)</span></span>
- <span data-ttu-id="49150-129">Literais, como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="49150-129">Literals, such as the following:</span></span>

  ```powershell
  a
  1
  1,2,3
  "PowerShell 2.0"
  @( "red", "green", "blue" )
  @{ a = 0x1; b = "great"; c ="script" }
  [XML] @'
  <p> Hello, World </p>
  '@
  ```

- <span data-ttu-id="49150-130">Cmdlets que são permitidos em uma seção de dados.</span><span class="sxs-lookup"><span data-stu-id="49150-130">Cmdlets that are permitted in a Data section.</span></span> <span data-ttu-id="49150-131">Por padrão, somente o `ConvertFrom-StringData` cmdlet é permitido.</span><span class="sxs-lookup"><span data-stu-id="49150-131">By default, only the `ConvertFrom-StringData` cmdlet is permitted.</span></span>
- <span data-ttu-id="49150-132">Cmdlets que você permite em uma seção de dados usando o `-SupportedCommand` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="49150-132">Cmdlets that you permit in a Data section by using the `-SupportedCommand` parameter.</span></span>

<span data-ttu-id="49150-133">Ao usar o `ConvertFrom-StringData` cmdlet em uma seção de dados, você pode colocar os pares de chave-valor em cadeias de caracteres entre aspas simples ou com aspas duplas ou em cadeias de caracteres de aspas simples ou com aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="49150-133">When you use the `ConvertFrom-StringData` cmdlet in a Data section, you can enclose the key-value pairs in single-quoted or double-quoted strings or in single-quoted or double-quoted here-strings.</span></span> <span data-ttu-id="49150-134">No entanto, as cadeias de caracteres que contêm variáveis e subexpressões devem ser colocadas entre cadeias de caracteres entre aspas simples ou em cadeias de caracteres entre aspas simples para que as variáveis não sejam expandidas e as subexpressãos não sejam executáveis.</span><span class="sxs-lookup"><span data-stu-id="49150-134">However, strings that contain variables and subexpressions must be enclosed in single-quoted strings or in single-quoted here-strings so that the variables are not expanded and the subexpressions are not executable.</span></span>

### <a name="-supportedcommand"></a><span data-ttu-id="49150-135">-SupportedCommand</span><span class="sxs-lookup"><span data-stu-id="49150-135">-SupportedCommand</span></span>

<span data-ttu-id="49150-136">O `-SupportedCommand` parâmetro permite que você indique que um cmdlet ou função gera apenas dados.</span><span class="sxs-lookup"><span data-stu-id="49150-136">The `-SupportedCommand` parameter allows you to indicate that a cmdlet or function generates only data.</span></span> <span data-ttu-id="49150-137">Ele foi projetado para permitir que os usuários incluam cmdlets e funções em uma seção de dados que foram escritos ou testados.</span><span class="sxs-lookup"><span data-stu-id="49150-137">It is designed to allow users to include cmdlets and functions in a data section that they have written or tested.</span></span>

<span data-ttu-id="49150-138">O valor de `-SupportedCommand` é uma lista separada por vírgulas de um ou mais nomes de cmdlet ou de função.</span><span class="sxs-lookup"><span data-stu-id="49150-138">The value of `-SupportedCommand` is a comma-separated list of one or more cmdlet or function names.</span></span>

<span data-ttu-id="49150-139">Por exemplo, a seção de dados a seguir inclui um cmdlet escrito pelo usuário, `Format-XML` , que formata dados em um arquivo XML:</span><span class="sxs-lookup"><span data-stu-id="49150-139">For example, the following data section includes a user-written cmdlet, `Format-XML`, that formats data in an XML file:</span></span>

```powershell
DATA -supportedCommand Format-Xml
{
    Format-Xml -Strings string1, string2, string3
}
```

### <a name="using-a-data-section"></a><span data-ttu-id="49150-140">Usando uma seção de dados</span><span class="sxs-lookup"><span data-stu-id="49150-140">Using a Data Section</span></span>

<span data-ttu-id="49150-141">Para usar o conteúdo de uma seção de dados, atribua-a a uma variável e use a notação variável para acessar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="49150-141">To use the content of a Data section, assign it to a variable and use variable notation to access the content.</span></span>

<span data-ttu-id="49150-142">Por exemplo, a seção de dados a seguir contém um `ConvertFrom-StringData` comando que converte a cadeia de caracteres here em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="49150-142">For example, the following data section contains a `ConvertFrom-StringData` command that converts the here-string into a hash table.</span></span> <span data-ttu-id="49150-143">A tabela de hash é atribuída à `$TextMsgs` variável.</span><span class="sxs-lookup"><span data-stu-id="49150-143">The hash table is assigned to the `$TextMsgs` variable.</span></span>

<span data-ttu-id="49150-144">A `$TextMsgs` variável não faz parte da seção de dados.</span><span class="sxs-lookup"><span data-stu-id="49150-144">The `$TextMsgs` variable is not part of the data section.</span></span>

```powershell
$TextMsgs = DATA {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

<span data-ttu-id="49150-145">Para acessar as chaves e os valores na tabela de hash no `$TextMsgs` , use os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="49150-145">To access the keys and values in hash table in `$TextMsgs`, use the following commands.</span></span>

```powershell
$TextMsgs.Text001
$TextMsgs.Text002
```

<span data-ttu-id="49150-146">Como alternativa, você pode colocar o nome da variável na definição da seção de dados.</span><span class="sxs-lookup"><span data-stu-id="49150-146">Alternately, you can put the variable name in the definition of the Data section.</span></span> <span data-ttu-id="49150-147">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="49150-147">For example:</span></span>

```powershell
DATA TextMsgs {
    ConvertFrom-StringData -StringData @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}

$TextMsgs
```

<span data-ttu-id="49150-148">O resultado é o mesmo que o exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="49150-148">The result is the same as the previous example.</span></span>

```Output
Name                           Value
----                           -----
Text001                        Windows 7
Text002                        Windows Server 2008 R2
```

### <a name="examples"></a><span data-ttu-id="49150-149">Exemplos</span><span class="sxs-lookup"><span data-stu-id="49150-149">Examples</span></span>

<span data-ttu-id="49150-150">Cadeias de dados simples.</span><span class="sxs-lookup"><span data-stu-id="49150-150">Simple data strings.</span></span>

```powershell
DATA {
    "Thank you for using my PowerShell Organize.pst script."
    "It is provided free of charge to the community."
    "I appreciate your comments and feedback."
}
```

<span data-ttu-id="49150-151">Cadeias de caracteres que incluem variáveis permitidas.</span><span class="sxs-lookup"><span data-stu-id="49150-151">Strings that include permitted variables.</span></span>

```powershell
DATA {
    if ($null) {
        "To get help for this cmdlet, type get-help new-dictionary."
    }
}
```

<span data-ttu-id="49150-152">Uma cadeia de caracteres aqui entre aspas simples que usa o `ConvertFrom-StringData` cmdlet:</span><span class="sxs-lookup"><span data-stu-id="49150-152">A single-quoted here-string that uses the `ConvertFrom-StringData` cmdlet:</span></span>

```powershell
DATA {
    ConvertFrom-StringData -stringdata @'
Text001 = Windows 7
Text002 = Windows Server 2008 R2
'@
}
```

<span data-ttu-id="49150-153">Uma cadeia de caracteres aqui com aspas duplas que usa o `ConvertFrom-StringData` cmdlet:</span><span class="sxs-lookup"><span data-stu-id="49150-153">A double-quoted here-string that uses the `ConvertFrom-StringData` cmdlet:</span></span>

```powershell
DATA  {
    ConvertFrom-StringData -stringdata @"
Msg1 = To start, press any key.
Msg2 = To exit, type "quit".
"@
}
```

<span data-ttu-id="49150-154">Uma seção de dados que inclui um cmdlet escrito pelo usuário que gera dados:</span><span class="sxs-lookup"><span data-stu-id="49150-154">A data section that includes a user-written cmdlet that generates data:</span></span>

```powershell
DATA -supportedCommand Format-XML {
    Format-Xml -strings string1, string2, string3
}
```

## <a name="see-also"></a><span data-ttu-id="49150-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="49150-155">See Also</span></span>

[<span data-ttu-id="49150-156">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="49150-156">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="49150-157">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="49150-157">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="49150-158">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="49150-158">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="49150-159">about_If</span><span class="sxs-lookup"><span data-stu-id="49150-159">about_If</span></span>](about_If.md)

[<span data-ttu-id="49150-160">about_Operators</span><span class="sxs-lookup"><span data-stu-id="49150-160">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="49150-161">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="49150-161">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="49150-162">about_Script_Internationalization</span><span class="sxs-lookup"><span data-stu-id="49150-162">about_Script_Internationalization</span></span>](about_Script_Internationalization.md)

[<span data-ttu-id="49150-163">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="49150-163">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)

[<span data-ttu-id="49150-164">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="49150-164">Import-LocalizedData</span></span>](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)
