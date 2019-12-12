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
ms.openlocfilehash: 157cd64e286392f3fd770e1e34542682b1e63625
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365365"
---
# <a name="modules-and-snap-ins"></a><span data-ttu-id="a0b8b-102">Módulos e snap-ins</span><span class="sxs-lookup"><span data-stu-id="a0b8b-102">Modules and Snap-ins</span></span>

<span data-ttu-id="a0b8b-103">Os cmdlets podem ser adicionados a uma sessão usando módulos (introduzidos pelo Windows PowerShell 2,0) ou snap-ins. Depois que o cmdlet é adicionado à sessão, ele pode ser executado programaticamente por um aplicativo host ou interativamente na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="a0b8b-103">Cmdlets can be added to a session using modules (introduced by Windows PowerShell 2.0) or snap-ins. Once the cmdlet is added to the session it can be run programmatically by a host application or interactively at the command line.</span></span>

<span data-ttu-id="a0b8b-104">Recomendamos que você use módulos como o método de entrega para adicionar cmdlets a uma sessão pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="a0b8b-104">We recommend that you use modules as the delivery method for adding cmdlets to a session for the following reasons:</span></span>

- <span data-ttu-id="a0b8b-105">Os módulos permitem que você adicione cmdlets carregando o assembly no qual o cmdlet é definido.</span><span class="sxs-lookup"><span data-stu-id="a0b8b-105">Modules allow you to add cmdlets by loading the assembly where the cmdlet is defined.</span></span> <span data-ttu-id="a0b8b-106">Não há necessidade de implementar uma classe de snap-in.</span><span class="sxs-lookup"><span data-stu-id="a0b8b-106">There is no need to implement a snap-in class.</span></span>

- <span data-ttu-id="a0b8b-107">Os módulos permitem que você adicione outros recursos, como variáveis, funções, scripts, tipos e arquivos de formatação e muito mais.</span><span class="sxs-lookup"><span data-stu-id="a0b8b-107">Modules allow you to add other resources, such as variables, functions, scripts, types and formatting files, and more.</span></span>

- <span data-ttu-id="a0b8b-108">Os snap-ins podem ser usados somente para adicionar cmdlets e provedores à sessão.</span><span class="sxs-lookup"><span data-stu-id="a0b8b-108">Snap-ins can be used only to add cmdlets and providers to the session.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0b8b-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a0b8b-109">See Also</span></span>

[<span data-ttu-id="a0b8b-110">Escrevendo um módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0b8b-110">Writing a Windows PowerShell Module</span></span>](../module/writing-a-windows-powershell-module.md)

<span data-ttu-id="a0b8b-111">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="a0b8b-111">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
