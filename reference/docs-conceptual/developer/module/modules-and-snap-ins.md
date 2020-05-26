---
title: Módulos e snap-ins | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d342f91-23e0-467f-8de2-f9657d820693
caps.latest.revision: 6
ms.openlocfilehash: b3d8209ea7e3e8353e73ebce1531991ec9519c74
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811655"
---
# <a name="modules-and-snap-ins"></a><span data-ttu-id="06741-102">Módulos e snap-ins</span><span class="sxs-lookup"><span data-stu-id="06741-102">Modules and Snap-ins</span></span>

<span data-ttu-id="06741-103">Os cmdlets podem ser adicionados a uma sessão usando módulos (introduzidos pelo Windows PowerShell 2,0) ou snap-ins. Depois que o cmdlet é adicionado à sessão, ele pode ser executado programaticamente por um aplicativo host ou interativamente na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="06741-103">Cmdlets can be added to a session using modules (introduced by Windows PowerShell 2.0) or snap-ins. Once the cmdlet is added to the session it can be run programmatically by a host application or interactively at the command line.</span></span>

<span data-ttu-id="06741-104">Recomendamos que você use módulos como o método de entrega para adicionar cmdlets a uma sessão pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="06741-104">We recommend that you use modules as the delivery method for adding cmdlets to a session for the following reasons:</span></span>

- <span data-ttu-id="06741-105">Os módulos permitem que você adicione cmdlets carregando o assembly no qual o cmdlet é definido.</span><span class="sxs-lookup"><span data-stu-id="06741-105">Modules allow you to add cmdlets by loading the assembly where the cmdlet is defined.</span></span> <span data-ttu-id="06741-106">Não há necessidade de implementar uma classe de snap-in.</span><span class="sxs-lookup"><span data-stu-id="06741-106">There is no need to implement a snap-in class.</span></span>

- <span data-ttu-id="06741-107">Os módulos permitem que você adicione outros recursos, como variáveis, funções, scripts, tipos e arquivos de formatação e muito mais.</span><span class="sxs-lookup"><span data-stu-id="06741-107">Modules allow you to add other resources, such as variables, functions, scripts, types and formatting files, and more.</span></span>

- <span data-ttu-id="06741-108">Os snap-ins podem ser usados somente para adicionar cmdlets e provedores à sessão.</span><span class="sxs-lookup"><span data-stu-id="06741-108">Snap-ins can be used only to add cmdlets and providers to the session.</span></span>

## <a name="see-also"></a><span data-ttu-id="06741-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="06741-109">See Also</span></span>

[<span data-ttu-id="06741-110">Escrever um módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="06741-110">Writing a Windows PowerShell Module</span></span>](writing-a-windows-powershell-module.md)

[<span data-ttu-id="06741-111">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="06741-111">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/cmdlet-overview.md)
