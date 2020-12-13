---
ms.date: 09/13/2016
ms.topic: reference
title: Módulos e snap-ins
description: Módulos e snap-ins
ms.openlocfilehash: de4ff1de9a29b78d7783fe7ed0265f5516db1fb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658681"
---
# <a name="modules-and-snap-ins"></a><span data-ttu-id="888c1-103">Módulos e snap-ins</span><span class="sxs-lookup"><span data-stu-id="888c1-103">Modules and Snap-ins</span></span>

<span data-ttu-id="888c1-104">Os cmdlets podem ser adicionados a uma sessão usando módulos (introduzidos pelo Windows PowerShell 2,0) ou snap-ins. Depois que o cmdlet é adicionado à sessão, ele pode ser executado programaticamente por um aplicativo host ou interativamente na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="888c1-104">Cmdlets can be added to a session using modules (introduced by Windows PowerShell 2.0) or snap-ins. Once the cmdlet is added to the session it can be run programmatically by a host application or interactively at the command line.</span></span>

<span data-ttu-id="888c1-105">Recomendamos que você use módulos como o método de entrega para adicionar cmdlets a uma sessão pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="888c1-105">We recommend that you use modules as the delivery method for adding cmdlets to a session for the following reasons:</span></span>

- <span data-ttu-id="888c1-106">Os módulos permitem que você adicione cmdlets carregando o assembly no qual o cmdlet é definido.</span><span class="sxs-lookup"><span data-stu-id="888c1-106">Modules allow you to add cmdlets by loading the assembly where the cmdlet is defined.</span></span> <span data-ttu-id="888c1-107">Não há necessidade de implementar uma classe de snap-in.</span><span class="sxs-lookup"><span data-stu-id="888c1-107">There is no need to implement a snap-in class.</span></span>

- <span data-ttu-id="888c1-108">Os módulos permitem que você adicione outros recursos, como variáveis, funções, scripts, tipos e arquivos de formatação e muito mais.</span><span class="sxs-lookup"><span data-stu-id="888c1-108">Modules allow you to add other resources, such as variables, functions, scripts, types and formatting files, and more.</span></span>

- <span data-ttu-id="888c1-109">Os snap-ins podem ser usados somente para adicionar cmdlets e provedores à sessão.</span><span class="sxs-lookup"><span data-stu-id="888c1-109">Snap-ins can be used only to add cmdlets and providers to the session.</span></span>

## <a name="see-also"></a><span data-ttu-id="888c1-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="888c1-110">See Also</span></span>

[<span data-ttu-id="888c1-111">Escrever um módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="888c1-111">Writing a Windows PowerShell Module</span></span>](writing-a-windows-powershell-module.md)

<span data-ttu-id="888c1-112">[Writing a Windows PowerShell Cmdlet](../cmdlet/cmdlet-overview.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="888c1-112">[Writing a Windows PowerShell Cmdlet](../cmdlet/cmdlet-overview.md)</span></span>
