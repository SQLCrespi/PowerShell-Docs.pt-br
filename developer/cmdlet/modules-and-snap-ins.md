---
title: Módulos e Snap-ins | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d342f91-23e0-467f-8de2-f9657d820693
caps.latest.revision: 6
ms.openlocfilehash: 157cd64e286392f3fd770e1e34542682b1e63625
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067613"
---
# <a name="modules-and-snap-ins"></a><span data-ttu-id="948e6-102">Módulos e snap-ins</span><span class="sxs-lookup"><span data-stu-id="948e6-102">Modules and Snap-ins</span></span>

<span data-ttu-id="948e6-103">Cmdlets podem ser adicionados a uma sessão usando o snap-ins ou módulos (introduzidos pelo Windows PowerShell 2.0). Depois que o cmdlet é adicionado à sessão, que ele pode ser executado programaticamente por um aplicativo host ou interativamente na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="948e6-103">Cmdlets can be added to a session using modules (introduced by Windows PowerShell 2.0) or snap-ins. Once the cmdlet is added to the session it can be run programmatically by a host application or interactively at the command line.</span></span>

<span data-ttu-id="948e6-104">É recomendável que você use módulos como o método de entrega para adicionar os cmdlets para uma sessão pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="948e6-104">We recommend that you use modules as the delivery method for adding cmdlets to a session for the following reasons:</span></span>

- <span data-ttu-id="948e6-105">Módulos permitem que você adicionar cmdlets carregando o assembly em que o cmdlet é definido.</span><span class="sxs-lookup"><span data-stu-id="948e6-105">Modules allow you to add cmdlets by loading the assembly where the cmdlet is defined.</span></span> <span data-ttu-id="948e6-106">Não é necessário implementar uma classe de snap-in.</span><span class="sxs-lookup"><span data-stu-id="948e6-106">There is no need to implement a snap-in class.</span></span>

- <span data-ttu-id="948e6-107">Os módulos permitem que você adicione outros recursos, como variáveis, funções, scripts, tipos e formatação arquivos e muito mais.</span><span class="sxs-lookup"><span data-stu-id="948e6-107">Modules allow you to add other resources, such as variables, functions, scripts, types and formatting files, and more.</span></span>

- <span data-ttu-id="948e6-108">Snap-ins podem ser usados apenas para adicionar os cmdlets e provedores para a sessão.</span><span class="sxs-lookup"><span data-stu-id="948e6-108">Snap-ins can be used only to add cmdlets and providers to the session.</span></span>

## <a name="see-also"></a><span data-ttu-id="948e6-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="948e6-109">See Also</span></span>

[<span data-ttu-id="948e6-110">Escrevendo um módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="948e6-110">Writing a Windows PowerShell Module</span></span>](../module/writing-a-windows-powershell-module.md)

<span data-ttu-id="948e6-111">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="948e6-111">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
