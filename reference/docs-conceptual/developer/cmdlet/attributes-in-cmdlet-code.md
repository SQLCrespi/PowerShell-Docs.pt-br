---
ms.date: 09/13/2016
ms.topic: reference
title: Atributos no código do cmdlet
description: Atributos no código do cmdlet
ms.openlocfilehash: 296bb8bcb06ef660e97dc792d1ecf596cc7c2930
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653648"
---
# <a name="attributes-in-cmdlet-code"></a>Atributos no código do cmdlet

Para usar a funcionalidade comum fornecida pelo Windows PowerShell, as classes e as propriedades públicas definidas no código do cmdlet são decoradas com atributos. Por exemplo, a seguinte definição de classe usa o atributo cmdlet para identificar a classe Microsoft .NET Framework na qual o cmdlet **Get-proc** é implementado. (Esse cmdlet é usado como um exemplo neste documento e é semelhante ao `Get-Process` cmdlet fornecido pelo Windows PowerShell.)

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

Esses atributos são considerados metadados porque sua implementação é separada da implementação do código do cmdlet. Quando o tempo de execução do Windows PowerShell executa o cmdlet, ele reconhece os atributos e, em seguida, executa a ação apropriada para cada atributo.

Embora talvez você queira implementar sua própria versão da funcionalidade fornecida por esses atributos, um bom design de cmdlet usa essas funcionalidades comuns.

Para obter mais informações sobre os diferentes atributos que podem ser declarados em seus cmdlets, consulte [tipos de atributo](./attribute-types.md).

## <a name="see-also"></a>Consulte Também

[Tipos de atributo](./attribute-types.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
