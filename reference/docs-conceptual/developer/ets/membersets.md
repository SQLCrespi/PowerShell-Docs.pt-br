---
title: Conjuntos de membros do sistema de tipos estendidos
ms.date: 07/09/2020
ms.openlocfilehash: 3f4e44ed7b498bb7c4a71f7b131270ed4f2ef981
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786247"
---
# <a name="ets-member-sets"></a>Conjuntos de membros do ETS

Os conjuntos de Membros permitem que você Particione os membros do objeto **PSObject** em dois subconjuntos para que os membros dos subconjuntos possam ser referenciados juntos pelo nome do subconjunto. Os dois tipos de subconjuntos incluem conjuntos de propriedades e conjuntos de membros. Por exemplo, como o PowerShell usa conjuntos de membros, há um conjunto de propriedades específico chamado **DefaultDisplayPropertySet** que é usado para determinar, em tempo de execução, quais propriedades serão exibidas para um determinado objeto **PSObject** .

## <a name="property-sets"></a>Conjuntos de propriedades

Os conjuntos de propriedades podem incluir qualquer número de propriedades de um tipo de **PSObject** . Em geral, um conjunto de propriedades pode ser usado sempre que uma coleção de Propriedades (do mesmo tipo) é necessária. O conjunto de propriedades é criado chamando o `PSPropertySet(System.String,System.Collections.Generic.IEnumerable{System.String})` Construtor com o nome do conjunto de propriedades e os nomes das propriedades referenciadas. O objeto **PSPropertySet** criado pode ser usado como um alias que aponta para as propriedades no conjunto. A classe [PSPropertySet](/dotnet/api/system.management.automation.pspropertyset) tem as propriedades e os métodos a seguir.

- Propriedade **IsInstance** : Obtém um valor **booliano** que indica a origem da propriedade.
- Propriedade **MemberType** : Obtém o tipo de propriedades no conjunto de propriedades.
- Propriedade **Name** : Obtém o nome do conjunto de propriedades.
- Propriedade **ReferencedPropertyNames** : Obtém os nomes das propriedades no conjunto de propriedades.
- Propriedade **TypeNameOfValue** : Obtém uma constante de enumeração **PropertySet** que define esse conjunto como um conjunto de propriedades.
- Propriedade **Value** : Obtém ou define o objeto **PSPropertySet** .
- `PSPropertySet.Copy`método: faz uma cópia exata do objeto **PSPropertySet** .
- `PSMemberSet.ToString`método: converte o objeto **PSPropertySet** em uma cadeia de caracteres.

## <a name="member-sets"></a>Conjuntos de membros

Os conjuntos de membros podem incluir qualquer número de membros estendidos de qualquer tipo. O conjunto de membros é criado chamando o`PSMemberSet(System.String,System.Collections.Generic.IEnumerable{System.Management.Automation.PSMemberInfo})`
Construtor com o nome do conjunto de membros e os nomes dos membros referenciados. O objeto **PSPropertySet** criado pode ser usado como um alias que aponta para os membros no conjunto. A classe [PSMemberSet](/dotnet/api/system.management.automation.psmemberset) tem as propriedades e os métodos a seguir.

- Propriedade **IsInstance** : Obtém um valor **booliano** que indica a origem do membro.
- Propriedade **Members** : Obtém todos os membros do conjunto de membros.
- Propriedade **MemberType** : Obtém uma constante de enumeração **MemberSet** que define esse conjunto como um conjunto de membros.
- Propriedade **Methods** : Obtém os métodos incluídos no conjunto de membros.
- Propriedade **Properties** : Obtém as propriedades incluídas no conjunto de membros.
- Propriedade **TypeNameOfValue** : Obtém uma constante de enumeração **MemberSet** que define esse conjunto como um conjunto de membros.
- Propriedade **Value** : Obtém o objeto **PSMemberSet** .
- `PSMemberSet.Copy`método: faz uma cópia exata do objeto **PSMemberSet** .
- `PSMemberSet.ToString`método: converte o objeto **PSMemberSet** em uma cadeia de caracteres.
