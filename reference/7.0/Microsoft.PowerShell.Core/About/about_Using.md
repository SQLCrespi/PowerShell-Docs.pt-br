---
description: Permite que você indique quais namespaces são usados na sessão.
Locale: en-US
ms.date: 11/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: 798b7bc9759c7c88eb612d0eb47bdb92c015cc18
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892014"
---
# <a name="about-using"></a><span data-ttu-id="13c40-103">Sobre como usar o</span><span class="sxs-lookup"><span data-stu-id="13c40-103">About Using</span></span>

## <a name="short-description"></a><span data-ttu-id="13c40-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="13c40-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="13c40-105">Permite que você indique quais namespaces são usados na sessão.</span><span class="sxs-lookup"><span data-stu-id="13c40-105">Allows you to indicate which namespaces are used in the session.</span></span>

## <a name="long-description"></a><span data-ttu-id="13c40-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="13c40-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="13c40-107">A `using` instrução permite que você especifique quais namespaces serão usados na sessão.</span><span class="sxs-lookup"><span data-stu-id="13c40-107">The `using` statement allows you to specify which namespaces are used in the session.</span></span> <span data-ttu-id="13c40-108">A adição de namespaces simplifica o uso de classes e membros do .NET e permite que você importe classes de módulos de script e assemblies.</span><span class="sxs-lookup"><span data-stu-id="13c40-108">Adding namespaces simplifies usage of .NET classes and member and allows you to import classes from script modules and assemblies.</span></span>

<span data-ttu-id="13c40-109">As `using` instruções devem vir antes de qualquer outra instrução em um script.</span><span class="sxs-lookup"><span data-stu-id="13c40-109">The `using` statements must come before any other statements in a script.</span></span>

<span data-ttu-id="13c40-110">A `using` instrução não deve ser confundida com o `using:` modificador de escopo para variáveis.</span><span class="sxs-lookup"><span data-stu-id="13c40-110">The `using` statement should not be confused with the `using:` scope modifier for variables.</span></span> <span data-ttu-id="13c40-111">Para obter mais informações, consulte [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="13c40-111">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="namespace-syntax"></a><span data-ttu-id="13c40-112">Sintaxe do namespace</span><span class="sxs-lookup"><span data-stu-id="13c40-112">Namespace syntax</span></span>

<span data-ttu-id="13c40-113">Para especificar os namespaces do .NET dos quais os tipos são resolvidos:</span><span class="sxs-lookup"><span data-stu-id="13c40-113">To specify .NET namespaces from which to resolve types:</span></span>

```
using namespace <.NET-namespace>
```

<span data-ttu-id="13c40-114">A especificação de um namespace torna mais fácil a referência de tipos por seus nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="13c40-114">Specifying a namespace makes it easier to reference types by their short names.</span></span>

## <a name="module-syntax"></a><span data-ttu-id="13c40-115">Sintaxe do módulo</span><span class="sxs-lookup"><span data-stu-id="13c40-115">Module syntax</span></span>

<span data-ttu-id="13c40-116">Para carregar classes de um módulo do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="13c40-116">To load classes from a PowerShell module:</span></span>

```
using module <module-name>
```

<span data-ttu-id="13c40-117">O valor de `<module-name>` pode ser um nome de módulo, uma especificação de módulo completa ou um caminho para um arquivo de módulo.</span><span class="sxs-lookup"><span data-stu-id="13c40-117">The value of `<module-name>` can be a module name, a full module specification, or a path to a module file.</span></span>

<span data-ttu-id="13c40-118">Quando `<module-name>` é um caminho, o caminho pode ser totalmente qualificado ou relativo.</span><span class="sxs-lookup"><span data-stu-id="13c40-118">When `<module-name>` is a path, the path can be fully qualified or relative.</span></span> <span data-ttu-id="13c40-119">Um caminho relativo é resolvido em relação ao script que contém a instrução using.</span><span class="sxs-lookup"><span data-stu-id="13c40-119">A relative path is resolved relative to the script that contains the using statement.</span></span>

> [!NOTE]
> <span data-ttu-id="13c40-120">Quando o caminho relativo contém uma barra ( `/` ), o PowerShell trata o caminho como relativo ao local atual, em vez de ser relativo ao local do script.</span><span class="sxs-lookup"><span data-stu-id="13c40-120">When the relative path contains a forward slash (`/`), PowerShell treats the path as relative to the current location rather than relative to the script location.</span></span> <span data-ttu-id="13c40-121">Esse bug é corrigido no PowerShell 7,1.</span><span class="sxs-lookup"><span data-stu-id="13c40-121">This bug is fixed in PowerShell 7.1.</span></span>

<span data-ttu-id="13c40-122">Quando `<module-name>` é uma especificação de nome ou módulo, o PowerShell pesquisa o **PSModulePath** para o módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="13c40-122">When `<module-name>` is a name or module specification, PowerShell searches the **PSModulePath** for the specified module.</span></span>

<span data-ttu-id="13c40-123">Uma especificação de módulo é uma tabela de hash que tem as seguintes chaves.</span><span class="sxs-lookup"><span data-stu-id="13c40-123">A module specification is a hash table that has the following keys.</span></span>

- <span data-ttu-id="13c40-124">`ModuleName` - **Necessário** Especifica o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="13c40-124">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="13c40-125">`GUID` - **Opcional** Especifica o GUID do módulo.</span><span class="sxs-lookup"><span data-stu-id="13c40-125">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="13c40-126">Também é **necessário** especificar uma das três chaves abaixo.</span><span class="sxs-lookup"><span data-stu-id="13c40-126">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="13c40-127">Essas chaves não podem ser usadas juntas.</span><span class="sxs-lookup"><span data-stu-id="13c40-127">These keys can't be used together.</span></span>
  - <span data-ttu-id="13c40-128">`ModuleVersion` -Especifica uma versão mínima aceitável do módulo.</span><span class="sxs-lookup"><span data-stu-id="13c40-128">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="13c40-129">`RequiredVersion` -Especifica uma versão exata e necessária do módulo.</span><span class="sxs-lookup"><span data-stu-id="13c40-129">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="13c40-130">`MaximumVersion` -Especifica a versão máxima aceitável do módulo.</span><span class="sxs-lookup"><span data-stu-id="13c40-130">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

## <a name="assembly-syntax"></a><span data-ttu-id="13c40-131">Sintaxe do assembly</span><span class="sxs-lookup"><span data-stu-id="13c40-131">Assembly syntax</span></span>

<span data-ttu-id="13c40-132">Para pré-carregar tipos de um assembly .NET:</span><span class="sxs-lookup"><span data-stu-id="13c40-132">To preload types from a .NET assembly:</span></span>

```
using assembly <.NET-assembly-path>
```

<span data-ttu-id="13c40-133">Carregar um assembly sobrecarrega os tipos .NET desse assembly em um script no momento da análise.</span><span class="sxs-lookup"><span data-stu-id="13c40-133">Loading an assembly preloads .NET types from that assembly into a script at parse time.</span></span> <span data-ttu-id="13c40-134">Isso permite que você crie novas classes do PowerShell que usam tipos do assembly pré-carregado.</span><span class="sxs-lookup"><span data-stu-id="13c40-134">This allows you to create new PowerShell classes that use types from the preloaded assembly.</span></span>

<span data-ttu-id="13c40-135">Se você não estiver criando novas classes do PowerShell, use o `Add-Type` cmdlet em vez disso.</span><span class="sxs-lookup"><span data-stu-id="13c40-135">If you are not creating new PowerShell classes, use the `Add-Type` cmdlet instead.</span></span> <span data-ttu-id="13c40-136">Para obter mais informações, consulte [Adicionar tipo](xref:Microsoft.PowerShell.Utility.Add-Type).</span><span class="sxs-lookup"><span data-stu-id="13c40-136">For more information, see [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span></span>

## <a name="examples"></a><span data-ttu-id="13c40-137">Exemplos</span><span class="sxs-lookup"><span data-stu-id="13c40-137">Examples</span></span>

### <a name="example-1---add-namespaces-for-typename-resolution"></a><span data-ttu-id="13c40-138">Exemplo 1-adicionar namespaces para resolução de TypeName</span><span class="sxs-lookup"><span data-stu-id="13c40-138">Example 1 - Add namespaces for typename resolution</span></span>

<span data-ttu-id="13c40-139">O script a seguir obtém o hash criptográfico para a cadeia de caracteres "Olá, Mundo".</span><span class="sxs-lookup"><span data-stu-id="13c40-139">The following script gets the cryptographic hash for the "Hello World" string.</span></span>

<span data-ttu-id="13c40-140">Observe como o `using namespace System.Text` e o `using namespace System.IO` simplificam as referências para `[UnicodeEncoding]` no `System.Text` e `[Stream]` `[MemoryStream]` no `System.IO` .</span><span class="sxs-lookup"><span data-stu-id="13c40-140">Note how the `using namespace System.Text` and `using namespace System.IO` simplify the references to `[UnicodeEncoding]` in `System.Text` and `[Stream]` and to `[MemoryStream]` in `System.IO`.</span></span>

```powershell
using namespace System.Text
using namespace System.IO

[string]$string = "Hello World"
## Valid values are "SHA1", "SHA256", "SHA384", "SHA512", "MD5"
[string]$algorithm = "SHA256"

[byte[]]$stringbytes = [UnicodeEncoding]::Unicode.GetBytes($string)

[Stream]$memorystream = [MemoryStream]::new($stringbytes)
$hashfromstream = Get-FileHash -InputStream $memorystream `
  -Algorithm $algorithm
$hashfromstream.Hash.ToString()
```

### <a name="example-2---load-classes-from-a-script-module"></a><span data-ttu-id="13c40-141">Exemplo 2 – carregar classes de um módulo de script</span><span class="sxs-lookup"><span data-stu-id="13c40-141">Example 2 - Load classes from a script module</span></span>

<span data-ttu-id="13c40-142">Neste exemplo, temos um módulo de script do PowerShell chamado **CardGames** que define as seguintes classes:</span><span class="sxs-lookup"><span data-stu-id="13c40-142">In this example, we have a PowerShell script module named **CardGames** that defines the following classes:</span></span>

- <span data-ttu-id="13c40-143">**CardGames. deck**</span><span class="sxs-lookup"><span data-stu-id="13c40-143">**CardGames.Deck**</span></span>
- <span data-ttu-id="13c40-144">**CardGames. Card**</span><span class="sxs-lookup"><span data-stu-id="13c40-144">**CardGames.Card**</span></span>

<span data-ttu-id="13c40-145">`Import-Module` e a `#requires` instrução só importa as funções de módulo, aliases e variáveis, conforme definido pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="13c40-145">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="13c40-146">As classes não são importadas.</span><span class="sxs-lookup"><span data-stu-id="13c40-146">Classes are not imported.</span></span> <span data-ttu-id="13c40-147">O `using module` comando importa o módulo e também carrega as definições de classe.</span><span class="sxs-lookup"><span data-stu-id="13c40-147">The `using module` command imports the module and also loads the class definitions.</span></span>

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a><span data-ttu-id="13c40-148">Exemplo 3-carregar classes de um assembly</span><span class="sxs-lookup"><span data-stu-id="13c40-148">Example 3 - Load classes from an assembly</span></span>

<span data-ttu-id="13c40-149">Este exemplo carrega um assembly para que suas classes possam ser usadas para criar novas classes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13c40-149">This example loads an assembly so that its classes can be used to create new PowerShell classes.</span></span> <span data-ttu-id="13c40-150">O script a seguir cria uma nova classe do PowerShell que é derivada da classe **DirectoryContext** .</span><span class="sxs-lookup"><span data-stu-id="13c40-150">The following script creates a new PowerShell class that is derived from **DirectoryContext** class.</span></span>

```powershell
using assembly 'C:\Program Files\PowerShell\7\System.DirectoryServices.dll'
using namespace System.DirectoryServices.ActiveDirectory

class myDirectoryClass : System.DirectoryServices.ActiveDirectory.DirectoryContext
{

  [DirectoryContext]$domain

  myDirectoryClass([DirectoryContextType]$ctx) : base($ctx)
  {
    $this.domain = [DirectoryContext]::new([DirectoryContextType]$ctx)
  }

}

$myDomain = [myDirectoryClass]::new([DirectoryContextType]::Domain)
$myDomain
```

```Output
domain                                                    Name UserName ContextType
------                                                    ---- -------- -----------
System.DirectoryServices.ActiveDirectory.DirectoryContext                    Domain
```
