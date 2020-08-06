---
title: Módulos e snap-ins | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 07cdc55fd6d1462130f1a81deb30056623a525e6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787301"
---
# <a name="modules-and-snap-ins"></a><span data-ttu-id="8e727-102">Módulos e snap-ins</span><span class="sxs-lookup"><span data-stu-id="8e727-102">Modules and Snap-ins</span></span>

<span data-ttu-id="8e727-103">Os cmdlets podem ser adicionados a uma sessão usando módulos (introduzidos pelo Windows PowerShell 2,0) ou snap-ins. Depois que o cmdlet é adicionado à sessão, ele pode ser executado programaticamente por um aplicativo host ou interativamente na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="8e727-103">Cmdlets can be added to a session using modules (introduced by Windows PowerShell 2.0) or snap-ins. Once the cmdlet is added to the session it can be run programmatically by a host application or interactively at the command line.</span></span>

<span data-ttu-id="8e727-104">Recomendamos que você use módulos como o método de entrega para adicionar cmdlets a uma sessão pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="8e727-104">We recommend that you use modules as the delivery method for adding cmdlets to a session for the following reasons:</span></span>

- <span data-ttu-id="8e727-105">Os módulos permitem que você adicione cmdlets carregando o assembly no qual o cmdlet é definido.</span><span class="sxs-lookup"><span data-stu-id="8e727-105">Modules allow you to add cmdlets by loading the assembly where the cmdlet is defined.</span></span> <span data-ttu-id="8e727-106">Não há necessidade de implementar uma classe de snap-in.</span><span class="sxs-lookup"><span data-stu-id="8e727-106">There is no need to implement a snap-in class.</span></span>

- <span data-ttu-id="8e727-107">Os módulos permitem que você adicione outros recursos, como variáveis, funções, scripts, tipos e arquivos de formatação e muito mais.</span><span class="sxs-lookup"><span data-stu-id="8e727-107">Modules allow you to add other resources, such as variables, functions, scripts, types and formatting files, and more.</span></span>

- <span data-ttu-id="8e727-108">Os snap-ins podem ser usados somente para adicionar cmdlets e provedores à sessão.</span><span class="sxs-lookup"><span data-stu-id="8e727-108">Snap-ins can be used only to add cmdlets and providers to the session.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e727-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8e727-109">See Also</span></span>

[<span data-ttu-id="8e727-110">Escrevendo um módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e727-110">Writing a Windows PowerShell Module</span></span>](writing-a-windows-powershell-module.md)

[<span data-ttu-id="8e727-111">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e727-111">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/cmdlet-overview.md)
