---
ms.date: 07/29/2020
title: Novos recursos de linguagem no PowerShell 5.0
ms.openlocfilehash: dada39c4121a810c7ce87a642f232934152104e5
ms.sourcegitcommit: 339e5fc8a4cc18b4ff6956fe5180343588e40e30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87410165"
---
# <a name="new-language-features-in-powershell-50"></a>Novos recursos de linguagem no PowerShell 5.0

O PowerShell 5.0 trouxe a capacidade de definir classes e outros tipos definidos pelo usuário usando uma sintaxe formal e semântica que são semelhantes a outras linguagens de programação orientadas ao objeto. O objetivo é permitir que desenvolvedores e profissionais de TI adotem o PowerShell para uma grande variedade de casos de uso, simplificar o desenvolvimento de artefatos do PowerShell (como recursos DSC) e acelerar a cobertura de superfícies de gerenciamento.

O PowerShell 5.0 introduz os seguintes novos elementos de linguagem:

### <a name="class-keyword"></a>Palavra-chave class

A palavra-chave `class` define uma nova classe. Este é um tipo real do .NET Framework. Membros de classe são públicos, mas somente públicos dentro do escopo do módulo. Não é possível se referir ao nome de tipo como uma cadeia de caracteres (por exemplo, `New-Object` não funciona), e nesta versão não é possível usar um literal de tipo (por exemplo, `[MyClass]`) fora do arquivo de script ou módulo no qual a classe é definida.

```powershell
class MyClass
{
    ...
}
```

### <a name="enum-keyword-and-enumerations"></a>Palavra-chave Enum e enumerações

O suporte à palavra-chave `enum` foi adicionado e usa uma nova linha como o delimitador. No momento, não é possível definir um enumerador em relação a si mesmo. No entanto, é possível iniciar uma enumeração em relação a outra enumeração, conforme mostrado no exemplo a seguir. Além disso, o tipo base não pode ser especificado; ele é sempre `[int]`.

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

Um valor de enumeração deve ser uma constante de tempo de análise. Não é possível defini-lo como o resultado de um comando chamado.

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

Enums dão suporte a operações aritméticas, conforme mostrado no exemplo a seguir.

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="import-dscresource"></a>Import-DscResource

`Import-DscResource` agora é uma palavra-chave dinâmica real. O PowerShell analisa o módulo raiz do módulo especificado pesquisando classes que contêm o atributo **DscResource**.

### <a name="implementingassembly"></a>ImplementingAssembly

Um novo campo, **ImplementingAssembly**, foi adicionado a **ModuleInfo**. Ele é definido como o assembly dinâmico criado para um módulo de script, caso o script defina classes, ou como o assembly carregado para módulos binários. Ele não é definido quando **ModuleType** é **Manifest**.

A reflexão sobre o campo **ImplementingAssembly** descobre recursos em um módulo. Isso significa que é possível descobrir recursos escritos no PowerShell ou em outras linguagens gerenciadas.

## <a name="further-reading"></a>Leitura adicional

- [about_Classes](/powershell/module/microsoft.powershell.core/about/about_classes)
- [about_Enum](/powershell/module/microsoft.powershell.core/about/about_enum)
- [about_Classes_and_DSC](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)
