---
description: Permite que você indique quais namespaces são usados na sessão.
Locale: en-US
ms.date: 11/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: bbea815f93ba503fcce550dec28736630fec5a51
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890756"
---
# <a name="about-using"></a>Sobre como usar o

## <a name="short-description"></a>DESCRIÇÃO BREVE
Permite que você indique quais namespaces são usados na sessão.

## <a name="long-description"></a>DESCRIÇÃO LONGA

A `using` instrução permite que você especifique quais namespaces serão usados na sessão. A adição de namespaces simplifica o uso de classes e membros do .NET e permite que você importe classes de módulos de script e assemblies.

As `using` instruções devem vir antes de qualquer outra instrução em um script.

A `using` instrução não deve ser confundida com o `using:` modificador de escopo para variáveis. Para obter mais informações, consulte [about_Remote_Variables](about_Remote_Variables.md).

## <a name="namespace-syntax"></a>Sintaxe do namespace

Para especificar os namespaces do .NET dos quais os tipos são resolvidos:

```
using namespace <.NET-namespace>
```

A especificação de um namespace torna mais fácil a referência de tipos por seus nomes curtos.

## <a name="module-syntax"></a>Sintaxe do módulo

Para carregar classes de um módulo do PowerShell:

```
using module <module-name>
```

O valor de `<module-name>` pode ser um nome de módulo, uma especificação de módulo completa ou um caminho para um arquivo de módulo.

Quando `<module-name>` é um caminho, o caminho pode ser totalmente qualificado ou relativo. Um caminho relativo é resolvido em relação ao script que contém a instrução using.

Quando `<module-name>` é uma especificação de nome ou módulo, o PowerShell pesquisa o **PSModulePath** para o módulo especificado.

Uma especificação de módulo é uma tabela de hash que tem as seguintes chaves.

- `ModuleName` - **Necessário** Especifica o nome do módulo.
- `GUID` - **Opcional** Especifica o GUID do módulo.
- Também é **necessário** especificar uma das três chaves abaixo. Essas chaves não podem ser usadas juntas.
  - `ModuleVersion` -Especifica uma versão mínima aceitável do módulo.
  - `RequiredVersion` -Especifica uma versão exata e necessária do módulo.
  - `MaximumVersion` -Especifica a versão máxima aceitável do módulo.

## <a name="assembly-syntax"></a>Sintaxe do assembly

Para pré-carregar tipos de um assembly .NET:

```
using assembly <.NET-assembly-path>
```

Carregar um assembly sobrecarrega os tipos .NET desse assembly em um script no momento da análise. Isso permite que você crie novas classes do PowerShell que usam tipos do assembly pré-carregado.

Se você não estiver criando novas classes do PowerShell, use o `Add-Type` cmdlet em vez disso. Para obter mais informações, consulte [Adicionar tipo](xref:Microsoft.PowerShell.Utility.Add-Type).

## <a name="examples"></a>Exemplos

### <a name="example-1---add-namespaces-for-typename-resolution"></a>Exemplo 1-adicionar namespaces para resolução de TypeName

O script a seguir obtém o hash criptográfico para a cadeia de caracteres "Olá, Mundo".

Observe como o `using namespace System.Text` e o `using namespace System.IO` simplificam as referências para `[UnicodeEncoding]` no `System.Text` e `[Stream]` `[MemoryStream]` no `System.IO` .

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

### <a name="example-2---load-classes-from-a-script-module"></a>Exemplo 2 – carregar classes de um módulo de script

Neste exemplo, temos um módulo de script do PowerShell chamado **CardGames** que define as seguintes classes:

- **CardGames. deck**
- **CardGames. Card**

`Import-Module` e a `#requires` instrução só importa as funções de módulo, aliases e variáveis, conforme definido pelo módulo. As classes não são importadas. O `using module` comando importa o módulo e também carrega as definições de classe.

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a>Exemplo 3-carregar classes de um assembly

Este exemplo carrega um assembly para que suas classes possam ser usadas para criar novas classes do PowerShell. O script a seguir cria uma nova classe do PowerShell que é derivada da classe **DirectoryContext** .

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
