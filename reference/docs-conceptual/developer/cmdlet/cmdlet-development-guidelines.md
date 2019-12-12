---
title: Diretrizes de desenvolvimento de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- development guidelines [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], development guidelines
ms.assetid: c30cc3c0-e958-4a8f-b81f-1e38de772f13
caps.latest.revision: 14
ms.openlocfilehash: 89c7682e87fa6f389349fc44275be0d2ffc83957
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369915"
---
# <a name="cmdlet-development-guidelines"></a><span data-ttu-id="f02ef-102">Diretrizes para desenvolvimento de cmdlets</span><span class="sxs-lookup"><span data-stu-id="f02ef-102">Cmdlet Development Guidelines</span></span>

<span data-ttu-id="f02ef-103">Os tópicos nesta seção fornecem diretrizes de desenvolvimento que você pode usar para produzir cmdlets bem formados.</span><span class="sxs-lookup"><span data-stu-id="f02ef-103">The topics in this section provide development guidelines that you can use to produce well-formed cmdlets.</span></span> <span data-ttu-id="f02ef-104">Aproveitando a funcionalidade comum fornecida pelo tempo de execução do Windows PowerShell e seguindo essas diretrizes, você pode desenvolver cmdlets robustos com esforço mínimo e fornecer ao usuário uma experiência consistente.</span><span class="sxs-lookup"><span data-stu-id="f02ef-104">By leveraging the common functionality provided by the Windows PowerShell runtime and by following these guidelines, you can develop robust cmdlets with minimal effort and provide the user with a consistent experience.</span></span> <span data-ttu-id="f02ef-105">Além disso, você reduzirá a carga de teste porque a funcionalidade comum não requer a reteste.</span><span class="sxs-lookup"><span data-stu-id="f02ef-105">Additionally, you will reduce the test burden because common functionality does not require retesting.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f02ef-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f02ef-106">In This Section</span></span>

- [<span data-ttu-id="f02ef-107">Diretrizes de desenvolvimento necessárias</span><span class="sxs-lookup"><span data-stu-id="f02ef-107">Required Development Guidelines</span></span>](./required-development-guidelines.md)

- [<span data-ttu-id="f02ef-108">Diretrizes de desenvolvimento altamente incentivadas</span><span class="sxs-lookup"><span data-stu-id="f02ef-108">Strongly Encouraged Development Guidelines</span></span>](./strongly-encouraged-development-guidelines.md)

- [<span data-ttu-id="f02ef-109">Diretrizes de desenvolvimento de consultoria</span><span class="sxs-lookup"><span data-stu-id="f02ef-109">Advisory Development Guidelines</span></span>](./advisory-development-guidelines.md)

## <a name="see-also"></a><span data-ttu-id="f02ef-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f02ef-110">See Also</span></span>

<span data-ttu-id="f02ef-111">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f02ef-111">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>

[<span data-ttu-id="f02ef-112">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f02ef-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
