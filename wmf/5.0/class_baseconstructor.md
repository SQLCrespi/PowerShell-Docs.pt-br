---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: 424e0b7a4d62fc35e5040a7e425950e887021d7e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085874"
---
# <a name="call-base-class-constructor"></a><span data-ttu-id="ecebe-102">Chamar o construtor de classe base</span><span class="sxs-lookup"><span data-stu-id="ecebe-102">Call Base Class Constructor</span></span>

<span data-ttu-id="ecebe-103">Para chamar um construtor de classe base desde uma subclasse, use a palavra-chave **base**:</span><span class="sxs-lookup"><span data-stu-id="ecebe-103">To call a base class constructor from a subclass, use the keyword **base**:</span></span>

```powershell
class A
{
    [int]$a

    A([int]$a)
    {
        $this.a = $a
    }
}

class B : A
{
    B() : base(103) {}
}

[B]::new().a # return 103
```

<span data-ttu-id="ecebe-104">Se uma classe base tiver um construtor padrão (sem parâmetros), será possível omitir uma chamada explícita de construtor:</span><span class="sxs-lookup"><span data-stu-id="ecebe-104">If a base class has a default (no parameter) constructor, you can omit an explicit constructor call:</span></span>

```powershell
class C : B
{
    C([int]$c) {}
}
```
