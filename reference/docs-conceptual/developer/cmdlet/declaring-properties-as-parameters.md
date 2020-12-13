---
ms.date: 09/13/2016
ms.topic: reference
title: Declarar propriedades como parâmetros
description: Declarar propriedades como parâmetros
ms.openlocfilehash: ade7928e2ca277da8bbd1a5e04997bd1d05f1e5d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653149"
---
# <a name="declaring-properties-as-parameters"></a>Declarar propriedades como parâmetros

Este tópico fornece informações básicas que você deve entender antes de declarar os parâmetros de um cmdlet.

Para declarar os parâmetros de um cmdlet dentro de sua classe de cmdlet, defina as propriedades públicas que representam cada parâmetro e, em seguida, adicione um ou mais atributos de parâmetro a cada propriedade. O tempo de execução do Windows PowerShell usa os atributos de parâmetro para identificar a propriedade como um parâmetro de cmdlet. A sintaxe básica para declarar o atributo de parâmetro é `[Parameter()]` .

Aqui está um exemplo de uma propriedade definida como um parâmetro obrigatório.

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

Aqui estão algumas coisas para se lembrar dos parâmetros.

- Um parâmetro deve ser explicitamente marcado como público. Parâmetros que não estão marcados como padrão público para interno e não serão encontrados pelo tempo de execução do Windows PowerShell.

- Os parâmetros devem ser definidos como Microsoft .NET tipos de estrutura para fornecer melhor validação de parâmetro. Por exemplo, parâmetros que são restritos a um valor de um conjunto de valores devem ser definidos como um tipo de enumeração. Os parâmetros que usam um valor de Uniform Resource Identifier (URI) devem ser do tipo [System. URI](/dotnet/api/System.Uri).

- Evite parâmetros de cadeia de caracteres básicos para todas as propriedades de texto de forma livre.

- Você pode adicionar um parâmetro a qualquer número de conjuntos de parâmetros. Para obter mais informações sobre conjuntos de parâmetros, consulte [conjuntos de parâmetros de cmdlet](./cmdlet-parameter-sets.md).

O Windows PowerShell também fornece um conjunto de parâmetros comuns que estão disponíveis automaticamente para todos os cmdlets. Para obter mais informações sobre esses parâmetros e seus aliases, consulte [parâmetros comuns do cmdlet](./common-parameter-names.md).

## <a name="see-also"></a>Consulte Também

[Parâmetros comuns do cmdlet](./common-parameter-names.md)

[Tipos de parâmetro de cmdlet](./types-of-cmdlet-parameters.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
