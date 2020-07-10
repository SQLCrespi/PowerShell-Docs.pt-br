---
title: Propriedades do sistema de tipo estendido
ms.date: 07/09/2020
ms.topic: conceptual
ms.openlocfilehash: 27da913b07dbc5f06ee46e5433208871168c36a5
ms.sourcegitcommit: d26e2237397483c6333abcf4331bd82f2e72b4e3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2020
ms.locfileid: "86217903"
---
# <a name="ets-properties"></a>Propriedades do ETS

As propriedades são membros que podem ser tratados como uma propriedade. Essencialmente, eles podem aparecer no lado esquerdo de uma expressão. As propriedades disponíveis incluem alias, código, observação e propriedades de script.

## <a name="alias-property"></a>Propriedade alias

Uma propriedade de alias é uma propriedade que faz referência a outra propriedade que o objeto **PSObject** contém. Ele é usado principalmente para renomear a propriedade referenciada. No entanto, ele também pode ser usado para converter o valor da propriedade referenciada em outro tipo. Em relação ao ETS, esse tipo de propriedade é sempre um membro estendido e é definido pela classe [PSAliasProperty](/dotnet/api/system.management.automation.psaliasproperty) . A classe inclui as propriedades a seguir.

- Propriedade **conversãotype** : o tipo CLR usado para converter o valor do membro referenciado.
- Propriedade **IsGettable** : indica se o valor da propriedade referenciada pode ser recuperado.
  Essa propriedade é determinada dinamicamente examinando a propriedade **IsGettable** da propriedade referenciada.
- **Propriedade** configurable: indica se o valor da propriedade referenciada pode ser definido. Essa propriedade é determinada dinamicamente examinando a **Propriedade** configurable da propriedade referenciada.
- Propriedade **MemberType** : uma constante de enumeração **AliasProperty** que define essa propriedade como uma propriedade de alias.
- Propriedade **ReferencedMemberName** : o nome da propriedade referenciada a qual este alias se refere.
- Propriedade **TypeNameOfValue** : o nome completo do tipo CLR do valor da propriedade referenciada.
- Propriedade **Value** : o valor da propriedade referenciada.

## <a name="code-property"></a>Propriedade de código

Uma propriedade de código é uma propriedade que é um getter e setter definido em uma linguagem CLR. Para que uma propriedade de código fique disponível, um desenvolvedor deve gravar a propriedade em alguma linguagem CLR, compilar e enviar o assembly resultante. Esse assembly deve estar disponível no runspace onde a propriedade de código é desejada. Em relação ao ETS, esse tipo de propriedade é sempre um membro estendido e é definido pela classe [PSCodeProperty](/dotnet/api/system.management.automation.pscodeproperty) . A classe inclui as propriedades a seguir.

- Propriedade **GetterCodeReference** : o método usado para obter o valor da propriedade de código.
- Propriedade **IsGettable** : indica se o valor da propriedade de código pode ser recuperado, se a propriedade **SetterCodeReference** : o método usado para definir o valor da propriedade de código.
- Propriedade configurable: indica se o valor **da propriedade de** código pode ser definido, se a propriedade **SetterCodeReference** não é nula.
- Propriedade **MemberType** : uma constante de enumeração **CodeProperty** que define essa propriedade como uma propriedade de código.
- Propriedade **SetterCodeReference** : o método usado para obter o valor da propriedade de código.
- Propriedade **TypeNameOfValue** : o tipo CLR do valor da propriedade de código que é retornado pela operação de obtenção de propriedades.
- Propriedade **Value** : o valor da Propriedade Code. Quando essa propriedade é recuperada, o código getter na propriedade GetterCodeReference é invocado, passando o objeto **PSObject** atual e retornando o valor retornado pela invocação. Quando essa propriedade é definida, o código setter na propriedade **SetterCodeReference** é invocado, passando o objeto **PSObject** atual como o primeiro argumento e o objeto usado para definir o valor como o segundo argumento.

## <a name="note-property"></a>Propriedade de observação

Uma propriedade Note é uma propriedade que tem um emparelhamento de nome/valor. Em relação ao ETS, esse tipo de propriedade é sempre um membro estendido e é definido pela classe [PSNoteProperty](/dotnet/api/system.management.automation.psnoteproperty) . A classe inclui as propriedades a seguir.

- Propriedade **IsGettable** : indica se o valor da propriedade Note pode ser recuperado.
- Propriedade configurable: indica se o valor **da propriedade Note** pode ser definido.
- Propriedade **MemberType** : uma constante de enumeração **NoteProperty** que define essa propriedade como uma propriedade de observação.
- Propriedade **TypeNameOfValue** : o nome de tipo totalmente qualificado do objeto retornado pela operação get da propriedade de observação.
- **Value**: o valor da propriedade note.

## <a name="powershell-property"></a>Propriedade do PowerShell

Uma propriedade do PowerShell é uma propriedade definida no objeto base ou uma propriedade que é disponibilizada por meio de um adaptador. Ele pode se referir a ambos os campos CLR, bem como propriedades CLR. Em relação ao ETS, esse tipo de propriedade pode ser um membro base ou um membro de adaptador e é definido pela classe [PSProperty](/dotnet/api/system.management.automation.psproperty) . A classe inclui as propriedades a seguir.

- Propriedade **IsGettable** : indica se o valor da propriedade base ou adaptada pode ser recuperado.
- Propriedade configurable: indica se o valor **da propriedade base** ou adaptada pode ser definido.
- Propriedade **MemberType** : uma constante de enumeração de propriedade que define essa propriedade como uma propriedade do PowerShell.
- Propriedade **TypeNameOfValue** : o nome totalmente qualificado do tipo de valor da propriedade. Por exemplo, para uma propriedade cujo valor é uma cadeia de caracteres, seu tipo de valor de propriedade é **System. String**.
- Propriedade **Value** : o valor da propriedade. Se a operação get ou Set for chamada em uma propriedade que não oferece suporte a essa operação, uma exceção **Getvalueexception** ou **setvalueexception** será gerada

## <a name="powershell-script-property"></a>Propriedade de script do PowerShell

Uma propriedade de script é uma propriedade que tem scripts getter e setter. Em relação ao ETS, esse tipo de propriedade é sempre um membro estendido e é definido pela classe [PSScriptProperty](/dotnet/api/system.management.automation.psscriptproperty) . A classe inclui as propriedades a seguir.

- Propriedade **GetterScript** : o script usado para recuperar o valor da propriedade de script.
- Propriedade **IsGettable** : indica se a propriedade **GetterScript** expõe um bloco de script.
- Propriedade conpropertyable: indica se **a propriedade** **SetterScript** expõe um bloco de script.
- Propriedade **MemberType** : uma constante de enumeração ScriptProperty que identifica essa propriedade como uma propriedade de script.
- Propriedade **SetterScript** : o script usado para definir o valor da propriedade de script.
- Propriedade **TypeNameOfValue** : o nome de tipo totalmente qualificado do objeto retornado pelo script getter. Nesse caso, **System. Object** é sempre retornado.
- Propriedade **Value** : o valor da propriedade script. Um get invoca o script getter e retorna o valor fornecido. Um conjunto invoca o script setter.
