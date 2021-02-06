---
description: Permite que você indique quais namespaces são usados na sessão.
Locale: en-US
ms.date: 01/19/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: ba3833f522265ad240d376b07c5add393c4b2721
ms.sourcegitcommit: 94d597c4fb38793bc49ca7610e2c9973b1e577c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "99598625"
---
# <a name="about-using"></a><span data-ttu-id="ac1d5-103">Sobre como usar o</span><span class="sxs-lookup"><span data-stu-id="ac1d5-103">About Using</span></span>

## <a name="short-description"></a><span data-ttu-id="ac1d5-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="ac1d5-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="ac1d5-105">Permite que você indique quais namespaces são usados na sessão.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-105">Allows you to indicate which namespaces are used in the session.</span></span>

## <a name="long-description"></a><span data-ttu-id="ac1d5-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="ac1d5-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="ac1d5-107">A `using` instrução permite que você especifique quais namespaces serão usados na sessão.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-107">The `using` statement allows you to specify which namespaces are used in the session.</span></span> <span data-ttu-id="ac1d5-108">A adição de namespaces simplifica o uso de classes e membros do .NET e permite que você importe classes de módulos de script e assemblies.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-108">Adding namespaces simplifies usage of .NET classes and member and allows you to import classes from script modules and assemblies.</span></span>

<span data-ttu-id="ac1d5-109">As `using` instruções devem vir antes de qualquer outra instrução em um script ou módulo.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-109">The `using` statements must come before any other statements in a script or module.</span></span> <span data-ttu-id="ac1d5-110">Nenhuma instrução sem marca de comentário pode precedê-la, incluindo parâmetros.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-110">No uncommented statement can precede it, including parameters.</span></span>

<span data-ttu-id="ac1d5-111">A `using` instrução não deve conter nenhuma variável.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-111">The `using` statement must not contain any variables.</span></span>

<span data-ttu-id="ac1d5-112">A `using` instrução não deve ser confundida com o `using:` modificador de escopo para variáveis.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-112">The `using` statement should not be confused with the `using:` scope modifier for variables.</span></span> <span data-ttu-id="ac1d5-113">Para obter mais informações, consulte [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="ac1d5-113">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="namespace-syntax"></a><span data-ttu-id="ac1d5-114">Sintaxe do namespace</span><span class="sxs-lookup"><span data-stu-id="ac1d5-114">Namespace syntax</span></span>

<span data-ttu-id="ac1d5-115">Para especificar os namespaces do .NET dos quais os tipos são resolvidos:</span><span class="sxs-lookup"><span data-stu-id="ac1d5-115">To specify .NET namespaces from which to resolve types:</span></span>

```
using namespace <.NET-namespace>
```

<span data-ttu-id="ac1d5-116">A especificação de um namespace torna mais fácil a referência de tipos por seus nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-116">Specifying a namespace makes it easier to reference types by their short names.</span></span>

## <a name="module-syntax"></a><span data-ttu-id="ac1d5-117">Sintaxe do módulo</span><span class="sxs-lookup"><span data-stu-id="ac1d5-117">Module syntax</span></span>

<span data-ttu-id="ac1d5-118">Para carregar classes de um módulo do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ac1d5-118">To load classes from a PowerShell module:</span></span>

```
using module <module-name>
```

<span data-ttu-id="ac1d5-119">O valor de `<module-name>` pode ser um nome de módulo, uma especificação de módulo completa ou um caminho para um arquivo de módulo.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-119">The value of `<module-name>` can be a module name, a full module specification, or a path to a module file.</span></span>

<span data-ttu-id="ac1d5-120">Quando `<module-name>` é um caminho, o caminho pode ser totalmente qualificado ou relativo.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-120">When `<module-name>` is a path, the path can be fully qualified or relative.</span></span> <span data-ttu-id="ac1d5-121">Um caminho relativo é resolvido em relação ao script que contém a instrução using.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-121">A relative path is resolved relative to the script that contains the using statement.</span></span>

<span data-ttu-id="ac1d5-122">Quando `<module-name>` é uma especificação de nome ou módulo, o PowerShell pesquisa o **PSModulePath** para o módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-122">When `<module-name>` is a name or module specification, PowerShell searches the **PSModulePath** for the specified module.</span></span>

<span data-ttu-id="ac1d5-123">Uma especificação de módulo é uma tabela de hash que tem as seguintes chaves.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-123">A module specification is a hash table that has the following keys.</span></span>

- <span data-ttu-id="ac1d5-124">`ModuleName` - **Necessário** Especifica o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-124">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="ac1d5-125">`GUID` - **Opcional** Especifica o GUID do módulo.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-125">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="ac1d5-126">Também é **necessário** especificar uma das três chaves abaixo.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-126">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="ac1d5-127">Essas chaves não podem ser usadas juntas.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-127">These keys can't be used together.</span></span>
  - <span data-ttu-id="ac1d5-128">`ModuleVersion` -Especifica uma versão mínima aceitável do módulo.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-128">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="ac1d5-129">`RequiredVersion` -Especifica uma versão exata e necessária do módulo.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-129">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="ac1d5-130">`MaximumVersion` -Especifica a versão máxima aceitável do módulo.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-130">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

<span data-ttu-id="ac1d5-131">A `using module` instrução importa classes do módulo raiz ( `ModuleToProcess` ) de um módulo de script ou de um módulo binário.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-131">The `using module` statement imports classes from the root module (`ModuleToProcess`) of a script module or binary module.</span></span> <span data-ttu-id="ac1d5-132">Ele não importa consistentemente classes definidas em módulos aninhados ou classes definidas em scripts que são originados no módulo.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-132">It does not consistently import classes defined in nested modules or classes defined in scripts that are dot-sourced into the module.</span></span> <span data-ttu-id="ac1d5-133">As classes que você deseja disponibilizar para usuários fora do módulo devem ser definidas no módulo raiz.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-133">Classes that you want to be available to users outside of the module should be defined in the root module.</span></span>

<span data-ttu-id="ac1d5-134">Durante o desenvolvimento de um módulo de script, é comum fazer alterações no código e, em seguida, carregar a nova versão do módulo usando `Import-Module` com o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="ac1d5-134">During development of a script module, it is common to make changes to the code then load the new version of the module using `Import-Module` with the **Force** parameter.</span></span> <span data-ttu-id="ac1d5-135">Isso funciona apenas para alterações nas funções no módulo raiz.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-135">This works for changes to functions in the root module only.</span></span> <span data-ttu-id="ac1d5-136">`Import-Module` não recarrega nenhum módulo aninhado.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-136">`Import-Module` does not reload any nested modules.</span></span> <span data-ttu-id="ac1d5-137">Além disso, não há como carregar nenhuma classe atualizada.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-137">Also, there is no way to load any updated classes.</span></span>

<span data-ttu-id="ac1d5-138">Para garantir que você esteja executando a versão mais recente, você deve descarregar o módulo usando o `Remove-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-138">To ensure that you are running the latest version, you must unload the module using the `Remove-Module` cmdlet.</span></span> <span data-ttu-id="ac1d5-139">`Remove-Module` Remove o módulo raiz, todos os módulos aninhados e todas as classes definidas nos módulos.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-139">`Remove-Module` removes the root module, all nested modules, and any classes defined in the modules.</span></span> <span data-ttu-id="ac1d5-140">Em seguida, você pode recarregar o módulo e as classes usando `Import-Module` e a `using module` instrução.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-140">Then you can reload the module and the classes using `Import-Module` and the `using module` statement.</span></span>

## <a name="assembly-syntax"></a><span data-ttu-id="ac1d5-141">Sintaxe do assembly</span><span class="sxs-lookup"><span data-stu-id="ac1d5-141">Assembly syntax</span></span>

<span data-ttu-id="ac1d5-142">Para pré-carregar tipos de um assembly .NET:</span><span class="sxs-lookup"><span data-stu-id="ac1d5-142">To preload types from a .NET assembly:</span></span>

```
using assembly <.NET-assembly-path>
```

<span data-ttu-id="ac1d5-143">Carregar um assembly sobrecarrega os tipos .NET desse assembly em um script no momento da análise.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-143">Loading an assembly preloads .NET types from that assembly into a script at parse time.</span></span> <span data-ttu-id="ac1d5-144">Isso permite que você crie novas classes do PowerShell que usam tipos do assembly pré-carregado.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-144">This allows you to create new PowerShell classes that use types from the preloaded assembly.</span></span>

<span data-ttu-id="ac1d5-145">Se você não estiver criando novas classes do PowerShell, use o `Add-Type` cmdlet em vez disso.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-145">If you are not creating new PowerShell classes, use the `Add-Type` cmdlet instead.</span></span> <span data-ttu-id="ac1d5-146">Para obter mais informações, consulte [Adicionar tipo](xref:Microsoft.PowerShell.Utility.Add-Type).</span><span class="sxs-lookup"><span data-stu-id="ac1d5-146">For more information, see [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span></span>

## <a name="examples"></a><span data-ttu-id="ac1d5-147">Exemplos</span><span class="sxs-lookup"><span data-stu-id="ac1d5-147">Examples</span></span>

### <a name="example-1---add-namespaces-for-typename-resolution"></a><span data-ttu-id="ac1d5-148">Exemplo 1-adicionar namespaces para resolução de TypeName</span><span class="sxs-lookup"><span data-stu-id="ac1d5-148">Example 1 - Add namespaces for typename resolution</span></span>

<span data-ttu-id="ac1d5-149">O script a seguir obtém o hash criptográfico para a cadeia de caracteres "Olá, Mundo".</span><span class="sxs-lookup"><span data-stu-id="ac1d5-149">The following script gets the cryptographic hash for the "Hello World" string.</span></span>

<span data-ttu-id="ac1d5-150">Observe como o `using namespace System.Text` e o `using namespace System.IO` simplificam as referências para `[UnicodeEncoding]` no `System.Text` e `[Stream]` `[MemoryStream]` no `System.IO` .</span><span class="sxs-lookup"><span data-stu-id="ac1d5-150">Note how the `using namespace System.Text` and `using namespace System.IO` simplify the references to `[UnicodeEncoding]` in `System.Text` and `[Stream]` and to `[MemoryStream]` in `System.IO`.</span></span>

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

### <a name="example-2---load-classes-from-a-script-module"></a><span data-ttu-id="ac1d5-151">Exemplo 2 – carregar classes de um módulo de script</span><span class="sxs-lookup"><span data-stu-id="ac1d5-151">Example 2 - Load classes from a script module</span></span>

<span data-ttu-id="ac1d5-152">Neste exemplo, temos um módulo de script do PowerShell chamado **CardGames** que define as seguintes classes:</span><span class="sxs-lookup"><span data-stu-id="ac1d5-152">In this example, we have a PowerShell script module named **CardGames** that defines the following classes:</span></span>

- <span data-ttu-id="ac1d5-153">**CardGames. deck**</span><span class="sxs-lookup"><span data-stu-id="ac1d5-153">**CardGames.Deck**</span></span>
- <span data-ttu-id="ac1d5-154">**CardGames. Card**</span><span class="sxs-lookup"><span data-stu-id="ac1d5-154">**CardGames.Card**</span></span>

<span data-ttu-id="ac1d5-155">`Import-Module` e a `#requires` instrução só importa as funções de módulo, aliases e variáveis, conforme definido pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-155">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="ac1d5-156">As classes não são importadas.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-156">Classes are not imported.</span></span> <span data-ttu-id="ac1d5-157">O `using module` comando importa o módulo e também carrega as definições de classe.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-157">The `using module` command imports the module and also loads the class definitions.</span></span>

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a><span data-ttu-id="ac1d5-158">Exemplo 3-carregar classes de um assembly</span><span class="sxs-lookup"><span data-stu-id="ac1d5-158">Example 3 - Load classes from an assembly</span></span>

<span data-ttu-id="ac1d5-159">Este exemplo carrega um assembly para que suas classes possam ser usadas para criar novas classes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac1d5-159">This example loads an assembly so that its classes can be used to create new PowerShell classes.</span></span> <span data-ttu-id="ac1d5-160">O script a seguir cria uma nova classe do PowerShell que é derivada da classe **DirectoryContext** .</span><span class="sxs-lookup"><span data-stu-id="ac1d5-160">The following script creates a new PowerShell class that is derived from **DirectoryContext** class.</span></span>

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
