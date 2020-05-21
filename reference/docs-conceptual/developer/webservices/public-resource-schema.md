---
title: Esquema de recursos públicos | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e67298ee-a773-4402-8afb-d97ad0e030e5
caps.latest.revision: 4
ms.openlocfilehash: 52244ee7496b99e11f0306e93728736fc9c51be5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564696"
---
# <a name="public-resource-schema"></a>Esquema de recursos públicos

O Management OData usa o MOF para definir recursos e suas propriedades. As propriedades de uma entidade do Management OData correspondem diretamente às propriedades do tipo gerenciado retornado pelo cmdlet subjacente.

## <a name="defining-a-resource"></a>Definindo um recurso

Cada recurso corresponde a um objeto retornado por um cmdlet do Windows PowerShell. No arquivo MOF de recurso público, você define um recurso declarando uma classe. A classe consiste em propriedades que correspondem às propriedades do objeto. Por exemplo, no exemplo a seguir, a classe [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) é representada pelo MOF a seguir.

```csharp
class PswsTest_Process
{
    [Key] SInt32 Id;
    [Required] SInt32 BasePriority;
    [Required] SInt32 HandleCount;
    [Required] string MachineName;
    [Required] SInt32 MainWindowHandle;

    ...
};
```

Cada nome de propriedade é precedido por um tipo de dados. Os tipos de dados neste exemplo correspondem aos tipos de dados CLR primitivos no .NET Framework, mas as propriedades também podem ser referências a outros recursos ou tipos complexos, que são descritos posteriormente.

O `Key` qualificador indica que uma propriedade é usada para identificar exclusivamente uma instância de recurso. Um recurso pode ter mais de uma chave.

O `Required` qualificador indica que a propriedade é necessária. Se uma propriedade for rotulada com o `Key` qualificador, ela será considerada necessária e o `Required` qualificador não será necessário.

### <a name="complex-data-types"></a>Tipos de dados complexos

As propriedades de entidades podem ter tipos de dados complexos. Tipos de dados complexos são tipos compostos de outros tipos, semelhantes a structs na linguagem de programação C. Um tipo complexo é declarado no arquivo MOF como uma classe com o `ComplexType` qualificador, como no exemplo a seguir.

```csharp
[ComplexType]
class PswsTest_ProcessModule
{
    String ModuleName;
    String FileName;
};
```

Para declarar uma propriedade de entidade como um tipo complexo, declare-a como um `string` tipo com o `EmbeddedInstance` qualificador, incluindo o nome do tipo complexo. O exemplo a seguir mostra a declaração de uma propriedade do `PswsTest_ProcessModule` tipo declarado no exemplo anterior.

```csharp
[Required, EmbeddedInstance("PswsTest_ProcessModule")] String Modules[];
```

### <a name="associating-entities"></a>Associando entidades

Você pode associar duas entidades usando os qualificadores Association e AssociationClass. Para obter mais informações, consulte [associando entidades do Management OData](./associating-management-odata-entities.md).

### <a name="derived-types"></a>Tipos derivados

Você pode derivar um tipo de outro tipo. O tipo derivado herda todas as propriedades do tipo do qual deriva, além de quaisquer propriedades explicitamente derivadas. O exemplo a seguir mostra uma declaração de tipo e, em seguida, uma declaração de dois tipos derivados desse tipo.

```csharp
Class Product {

    [Key] String ProductName;

};

Class DairyProduct : Product {

    Uint16 PercentFat;
};
Class POPProduct : Product {

    Boolean IsCarbonated;
};
```
