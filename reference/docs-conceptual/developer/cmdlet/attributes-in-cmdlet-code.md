---
title: Atributos no código do cmdlet | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1f92e329d304754d5596cef0c95dc597aca3a538
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774908"
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

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
