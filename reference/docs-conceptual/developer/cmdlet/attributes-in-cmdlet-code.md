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
# <a name="attributes-in-cmdlet-code"></a><span data-ttu-id="d29f3-102">Atributos no código do cmdlet</span><span class="sxs-lookup"><span data-stu-id="d29f3-102">Attributes in Cmdlet Code</span></span>

<span data-ttu-id="d29f3-103">Para usar a funcionalidade comum fornecida pelo Windows PowerShell, as classes e as propriedades públicas definidas no código do cmdlet são decoradas com atributos.</span><span class="sxs-lookup"><span data-stu-id="d29f3-103">To use the common functionality provided by Windows PowerShell, the classes and public properties defined in the cmdlet code are decorated with attributes.</span></span> <span data-ttu-id="d29f3-104">Por exemplo, a seguinte definição de classe usa o atributo cmdlet para identificar a classe Microsoft .NET Framework na qual o cmdlet **Get-proc** é implementado.</span><span class="sxs-lookup"><span data-stu-id="d29f3-104">For example, the following class definition uses the Cmdlet attribute to identify the Microsoft .NET Framework class in which the **Get-Proc** cmdlet is implemented.</span></span> <span data-ttu-id="d29f3-105">(Esse cmdlet é usado como um exemplo neste documento e é semelhante ao `Get-Process` cmdlet fornecido pelo Windows PowerShell.)</span><span class="sxs-lookup"><span data-stu-id="d29f3-105">(This cmdlet is used as an example in this document, and is similar to the `Get-Process` cmdlet provided by Windows PowerShell.)</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

<span data-ttu-id="d29f3-106">Esses atributos são considerados metadados porque sua implementação é separada da implementação do código do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d29f3-106">These attributes are considered metadata because their implementation is separate from the implementation of the cmdlet code.</span></span> <span data-ttu-id="d29f3-107">Quando o tempo de execução do Windows PowerShell executa o cmdlet, ele reconhece os atributos e, em seguida, executa a ação apropriada para cada atributo.</span><span class="sxs-lookup"><span data-stu-id="d29f3-107">When the Windows PowerShell runtime runs the cmdlet, it recognizes the attributes and then performs the appropriate action for each attribute.</span></span>

<span data-ttu-id="d29f3-108">Embora talvez você queira implementar sua própria versão da funcionalidade fornecida por esses atributos, um bom design de cmdlet usa essas funcionalidades comuns.</span><span class="sxs-lookup"><span data-stu-id="d29f3-108">Although you might want to implement your own version of the functionality provided by these attributes, a good cmdlet design uses these common functionalities.</span></span>

<span data-ttu-id="d29f3-109">Para obter mais informações sobre os diferentes atributos que podem ser declarados em seus cmdlets, consulte [tipos de atributo](./attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="d29f3-109">For more information about the different attributes that can be declared in your cmdlets, see [Attribute Types](./attribute-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d29f3-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d29f3-110">See Also</span></span>

[<span data-ttu-id="d29f3-111">Tipos de atributo</span><span class="sxs-lookup"><span data-stu-id="d29f3-111">Attribute Types</span></span>](./attribute-types.md)

[<span data-ttu-id="d29f3-112">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d29f3-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
