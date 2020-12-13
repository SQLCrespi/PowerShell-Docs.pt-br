---
ms.date: 07/09/2020
ms.topic: reference
title: Métodos de classe do sistema de tipo estendido
description: Métodos de classe do sistema de tipo estendido
ms.openlocfilehash: b53604a36e0a0c3587f345262e8f274e3a2c4859
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660381"
---
# <a name="ets-class-methods"></a>Métodos de classe ETS

Os métodos ETS são membros que podem receber argumentos, podem retornar resultados e não podem aparecer no lado esquerdo de uma expressão. Os métodos que estão disponíveis no ETS incluem código, Windows PowerShell e métodos de script.

> [!NOTE]
> De scripts, os métodos são acessados usando a mesma sintaxe que outros membros com a adição de parênteses no final do nome do método.

## <a name="code-methods"></a>Métodos de código

Um método de código é um membro estendido que é definido em uma linguagem CLR. Ele fornece funcionalidade semelhante a um método definido em um objeto base; no entanto, um método de código pode ser adicionado dinamicamente a um objeto **PSObject** . Para que um método de código fique disponível, um desenvolvedor deve gravar a propriedade em alguma linguagem CLR, compilar e enviar o assembly resultante. Esse assembly deve estar disponível no runspace onde o método de código é desejado. Lembre-se de que uma implementação de método de código deve ser thread-safe. O acesso a esses métodos é feito por meio de objetos [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) que fornecem os métodos públicos e as propriedades a seguir.

- `PSCodeMethod.Copy` método: faz uma cópia exata do objeto **PSCodeMethod** .
- `PSCodeMethod.Invoke(System.Object[])` método: invoca o método de código subjacente.
- `PSCodeMethod.ToString` método: converte o objeto **PSCodeMethod** em uma cadeia de caracteres.
- `PSCodeMethod.CodeReference` Propriedade: Obtém o método subjacente no qual o método de código se baseia.
- Propriedade **PSMemberInfo. IsInstance** : Obtém um valor **booliano** que indica a origem do membro.
- Propriedade **PSCodeMethod. MemberType** : Obtém uma constante de enumeração **PSMemberTypes. CodeMethod** que identifica esse método como um método de código.
- Propriedade **PSMemberInfo.Name** : Obtém o nome do método de código subjacente.
- Propriedade **PSCodeMethod. OverloadDefinitions** : Obtém uma definição de todas as sobrecargas do método de código subjacente.
- Propriedade **PSCodeMethod. TypeNameOfValue** : Obtém o nome completo do método de código.
- Propriedade **PSMemberInfo. Value** : Obtém o objeto **PSCodeMethod** .

## <a name="windows-powershell-methods"></a>Métodos do Windows PowerShell

Um método do PowerShell é um método CLR definido no objeto base ou torna-se acessível por meio de um adaptador. O acesso a esses métodos é feito por meio de objetos **PSMethod** que fornecem os métodos públicos e as propriedades a seguir.

- `PSMethod.Copy` método: faz uma cópia exata do objeto **PSMethod** .
- `PSMethod.Invoke(System.Object[])` método: invoca o método subjacente.
- `PSMethod.ToString` método: converte o objeto **PSMethod** em uma cadeia de caracteres.
- Propriedade **PSMemberInfo. IsInstance** : Obtém um valor **booliano** que indica a origem do membro.
- Propriedade **PSMethod. MemberType** : Obtém uma constante de enumeração **PSMemberTypes. Method** que identifica esse método como um método do PowerShell.
- Propriedade **PSMemberInfo.Name** : Obtém o nome do método subjacente.
- Propriedade **PSMethod. OverloadDefinitions** : Obtém as definições de todas as sobrecargas do método subjacente.
- Propriedade **PSMethod. TypeNameOfValue** : Obtém o tipo ETS deste método.
- Propriedade **PSMemberInfo. Value** : Obtém o objeto **PSMethod** .

## <a name="script-methods"></a>Métodos de script

Um método de script é um membro estendido que é definido na linguagem do PowerShell. Ele fornece funcionalidade semelhante a um método definido em um objeto base; no entanto, um método de script pode ser adicionado dinamicamente a um objeto **PSObject** . O acesso a esses métodos é feito por meio de objetos [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) que fornecem os métodos públicos e as propriedades a seguir.

- `PSScriptMethod.Copy` método: faz uma cópia exata do objeto **PSScriptMethod** .
- `PSScriptMethod.Invoke(System.Object[])` método: invoca o método de script subjacente.
- `PSScriptMethod.ToString` método: converte o objeto **PSScriptMethod** em uma cadeia de caracteres.
- Propriedade **PSMemberInfo. IsInstance** : Obtém um valor **booliano** que indica a origem do membro.
- Propriedade **PSScriptMethod. MemberType** : Obtém uma constante de enumeração **PSMemberTypes. ScriptMethod** que identifica esse método como um método de script.
- Propriedade **PSMemberInfo.Name** : Obtém o nome do método de código subjacente.
- Propriedade **PSScriptMethod. OverloadDefinitions** : Obtém as definições de todas as sobrecargas do método de script subjacente.
- Propriedade **PSScriptMethod. TypeNameOfValue** : Obtém o tipo ETS deste método.
- Propriedade **PSScriptMethod. script** : Obtém o script usado para invocar o método.
- Propriedade **PSMemberInfo. Value** : Obtém o objeto **PSScriptMethod** .
