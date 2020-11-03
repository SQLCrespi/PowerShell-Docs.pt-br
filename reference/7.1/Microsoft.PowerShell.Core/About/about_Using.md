---
description: Permite que você indique quais namespaces são usados na sessão.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/29/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: eaf983ad03676b4ac57a3b35bc44f72036da55b4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195916"
---
# <a name="about-using"></a><span data-ttu-id="5d258-104">Sobre como usar o</span><span class="sxs-lookup"><span data-stu-id="5d258-104">About Using</span></span>

## <a name="short-description"></a><span data-ttu-id="5d258-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="5d258-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="5d258-106">Permite que você indique quais namespaces são usados na sessão.</span><span class="sxs-lookup"><span data-stu-id="5d258-106">Allows you to indicate which namespaces are used in the session.</span></span>

## <a name="long-description"></a><span data-ttu-id="5d258-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="5d258-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="5d258-108">A `using` instrução permite que você especifique quais namespaces serão usados na sessão.</span><span class="sxs-lookup"><span data-stu-id="5d258-108">The `using` statement allows you to specify which namespaces are used in the session.</span></span> <span data-ttu-id="5d258-109">A adição de namespaces simplifica o uso de classes e membros do .NET e permite que você importe classes de módulos de script e assemblies.</span><span class="sxs-lookup"><span data-stu-id="5d258-109">Adding namespaces simplifies usage of .NET classes and member and allows you to import classes from script modules and assemblies.</span></span>

<span data-ttu-id="5d258-110">As `using` instruções devem vir antes de qualquer outra instrução em um script.</span><span class="sxs-lookup"><span data-stu-id="5d258-110">The `using` statements must come before any other statements in a script.</span></span>

<span data-ttu-id="5d258-111">A `using` instrução não deve ser confundida com o `using:` modificador de escopo para variáveis.</span><span class="sxs-lookup"><span data-stu-id="5d258-111">The `using` statement should not be confused with the `using:` scope modifier for variables.</span></span> <span data-ttu-id="5d258-112">Para obter mais informações, consulte [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="5d258-112">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="5d258-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d258-113">Syntax</span></span>

<span data-ttu-id="5d258-114">Para especificar os namespaces do .NET dos quais os tipos são resolvidos:</span><span class="sxs-lookup"><span data-stu-id="5d258-114">To specify .NET namespaces from which to resolve types:</span></span>

```
using namespace <.NET-namespace>
```

<span data-ttu-id="5d258-115">Para carregar classes de um módulo do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5d258-115">To load classes from a PowerShell module:</span></span>

```
using module <module-name>
```

<span data-ttu-id="5d258-116">Para pré-carregar tipos de um assembly .NET:</span><span class="sxs-lookup"><span data-stu-id="5d258-116">To preload types from a .NET assembly:</span></span>

```
using assembly <.NET-assembly-path>
```

<span data-ttu-id="5d258-117">A especificação de um namespace torna mais fácil a referência de tipos por seus nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="5d258-117">Specifying a namespace makes it easier to reference types by their short names.</span></span>

<span data-ttu-id="5d258-118">Carregar um assembly sobrecarrega os tipos .NET desse assembly em um script no momento da análise.</span><span class="sxs-lookup"><span data-stu-id="5d258-118">Loading an assembly preloads .NET types from that assembly into a script at parse time.</span></span> <span data-ttu-id="5d258-119">Isso permite que você crie novas classes do PowerShell que usam tipos do assembly pré-carregado.</span><span class="sxs-lookup"><span data-stu-id="5d258-119">This allows you to create new PowerShell classes that use types from the preloaded assembly.</span></span>

<span data-ttu-id="5d258-120">Se você não estiver criando novas classes do PowerShell, use o `Add-Type` cmdlet em vez disso.</span><span class="sxs-lookup"><span data-stu-id="5d258-120">If you are not creating new PowerShell classes, use the `Add-Type` cmdlet instead.</span></span> <span data-ttu-id="5d258-121">Para obter mais informações, consulte [Adicionar tipo](xref:Microsoft.PowerShell.Utility.Add-Type).</span><span class="sxs-lookup"><span data-stu-id="5d258-121">For more information, see [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span></span>

## <a name="examples"></a><span data-ttu-id="5d258-122">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5d258-122">Examples</span></span>

### <a name="example-1---add-namespaces-for-typename-resolution"></a><span data-ttu-id="5d258-123">Exemplo 1-adicionar namespaces para resolução de TypeName</span><span class="sxs-lookup"><span data-stu-id="5d258-123">Example 1 - Add namespaces for typename resolution</span></span>

<span data-ttu-id="5d258-124">O script a seguir obtém o hash criptográfico para a cadeia de caracteres "Olá, Mundo".</span><span class="sxs-lookup"><span data-stu-id="5d258-124">The following script gets the cryptographic hash for the "Hello World" string.</span></span>

<span data-ttu-id="5d258-125">Observe como o `using namespace System.Text` e o `using namespace System.IO` simplificam as referências para `[UnicodeEncoding]` no `System.Text` e `[Stream]` `[MemoryStream]` no `System.IO` .</span><span class="sxs-lookup"><span data-stu-id="5d258-125">Note how the `using namespace System.Text` and `using namespace System.IO` simplify the references to `[UnicodeEncoding]` in `System.Text` and `[Stream]` and to `[MemoryStream]` in `System.IO`.</span></span>

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

### <a name="example-2---load-classes-from-a-script-module"></a><span data-ttu-id="5d258-126">Exemplo 2 – carregar classes de um módulo de script</span><span class="sxs-lookup"><span data-stu-id="5d258-126">Example 2 - Load classes from a script module</span></span>

<span data-ttu-id="5d258-127">Neste exemplo, temos um módulo de script do PowerShell chamado **CardGames** que define as seguintes classes:</span><span class="sxs-lookup"><span data-stu-id="5d258-127">In this example, we have a PowerShell script module named **CardGames** that defines the following classes:</span></span>

- <span data-ttu-id="5d258-128">**CardGames. deck**</span><span class="sxs-lookup"><span data-stu-id="5d258-128">**CardGames.Deck**</span></span>
- <span data-ttu-id="5d258-129">**CardGames. Card**</span><span class="sxs-lookup"><span data-stu-id="5d258-129">**CardGames.Card**</span></span>

<span data-ttu-id="5d258-130">`Import-Module` e a `#requires` instrução só importa as funções de módulo, aliases e variáveis, conforme definido pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="5d258-130">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="5d258-131">As classes não são importadas.</span><span class="sxs-lookup"><span data-stu-id="5d258-131">Classes are not imported.</span></span> <span data-ttu-id="5d258-132">O `using module` comando importa o módulo e também carrega as definições de classe.</span><span class="sxs-lookup"><span data-stu-id="5d258-132">The `using module` command imports the module and also loads the class definitions.</span></span>

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a><span data-ttu-id="5d258-133">Exemplo 3-carregar classes de um assembly</span><span class="sxs-lookup"><span data-stu-id="5d258-133">Example 3 - Load classes from an assembly</span></span>

<span data-ttu-id="5d258-134">Este exemplo carrega um assembly para que suas classes possam ser usadas para criar novas classes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d258-134">This example loads an assembly so that its classes can be used to create new PowerShell classes.</span></span> <span data-ttu-id="5d258-135">O script a seguir cria uma nova classe do PowerShell que é derivada da classe **DirectoryContext** .</span><span class="sxs-lookup"><span data-stu-id="5d258-135">The following script creates a new PowerShell class that is derived from **DirectoryContext** class.</span></span>

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

