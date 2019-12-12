---
title: Conceitos de relatório de erros | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- non-terminating errors [PowerShell SDK]
- errors [PowerShell SDK], described
- terminating errors [PowerShell SDK]
- errors [PowerShell SDK]
ms.assetid: 0dce97c0-bd9a-4691-8ca3-e8d5dea902c5
caps.latest.revision: 11
ms.openlocfilehash: 2f185e415e3effc2cf09a282ca1167e3bcfb7d6a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364615"
---
# <a name="error-reporting-concepts"></a><span data-ttu-id="1a92d-102">Conceitos de relatórios de erro</span><span class="sxs-lookup"><span data-stu-id="1a92d-102">Error Reporting Concepts</span></span>

<span data-ttu-id="1a92d-103">O Windows PowerShell fornece dois mecanismos para relatar erros: um mecanismo para *encerrar erros* e outro mecanismo para *erros de não encerramento*.</span><span class="sxs-lookup"><span data-stu-id="1a92d-103">Windows PowerShell provides two mechanisms for reporting errors: one mechanism for *terminating errors* and another mechanism for *non-terminating errors*.</span></span> <span data-ttu-id="1a92d-104">É importante que o cmdlet Relate erros corretamente para que o aplicativo host que está executando seus cmdlets possa reagir de maneira apropriada.</span><span class="sxs-lookup"><span data-stu-id="1a92d-104">It is important for your cmdlet to report errors correctly so that the host application that is running your cmdlets can react in an appropriate manner.</span></span>

<span data-ttu-id="1a92d-105">O cmdlet deve chamar o método [System. Management. Automation. cmdlet. ThrowTerminatingError \*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) quando ocorrer um erro que não deve ou não permitir que o cmdlet continue a processar seus objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="1a92d-105">Your cmdlet should call the [System.Management.Automation.Cmdlet.Throwterminatingerror\*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) method when an error occurs that does not or should not allow the cmdlet to continue to process its input objects.</span></span> <span data-ttu-id="1a92d-106">O cmdlet deve chamar o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) para relatar erros de não finalização quando o cmdlet puder continuar processando os objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="1a92d-106">Your cmdlet should call the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report non-terminating errors when the cmdlet can continue processing the input objects.</span></span> <span data-ttu-id="1a92d-107">Os dois métodos fornecem um registro de erro que o aplicativo host pode usar para investigar a causa do erro.</span><span class="sxs-lookup"><span data-stu-id="1a92d-107">Both methods provide an error record that the host application can use to investigate the cause of the error.</span></span>

<span data-ttu-id="1a92d-108">Use as diretrizes a seguir para determinar se um erro é um erro de encerramento ou de não finalização.</span><span class="sxs-lookup"><span data-stu-id="1a92d-108">Use the following guidelines to determine whether an error is a terminating or non-terminating error.</span></span>

- <span data-ttu-id="1a92d-109">Um erro será um erro de encerramento se ele impedir que o cmdlet continue a processar o objeto atual ou de processar com êxito outros objetos de entrada, independentemente de seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="1a92d-109">An error is a terminating error if it prevents your cmdlet from continuing to process the current object or from successfully processing any further input objects, regardless of their content.</span></span>

- <span data-ttu-id="1a92d-110">Um erro será um erro de encerramento se você não quiser que o cmdlet continue a processar o objeto atual ou quaisquer outros objetos de entrada, independentemente de seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="1a92d-110">An error is a terminating error if you do not want your cmdlet to continue processing the current object or any further input objects, regardless of their content.</span></span>

- <span data-ttu-id="1a92d-111">Um erro será um erro de encerramento se ocorrer em um cmdlet que não aceita nem retorna um objeto ou se ele ocorrer em um cmdlet que aceita ou retorna apenas um objeto.</span><span class="sxs-lookup"><span data-stu-id="1a92d-111">An error is a terminating error if it occurs in a cmdlet that does not accept or return an object or if it occurs in a cmdlet that accepts or returns only one object.</span></span>

- <span data-ttu-id="1a92d-112">Um erro será um erro de não finalização se você quiser que o cmdlet continue a processar o objeto atual e quaisquer outros objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="1a92d-112">An error is a non-terminating error if you want your cmdlet to continue processing the current object and any further input objects.</span></span>

- <span data-ttu-id="1a92d-113">Um erro será um erro de não finalização se ele estiver relacionado a um objeto de entrada ou subconjunto de objetos de entrada específico.</span><span class="sxs-lookup"><span data-stu-id="1a92d-113">An error is a non-terminating error if it is related to a specific input object or subset of input objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a92d-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1a92d-114">See Also</span></span>

[<span data-ttu-id="1a92d-115">System. Management. Automation. cmdlet. ThrowTerminatingError \*</span><span class="sxs-lookup"><span data-stu-id="1a92d-115">System.Management.Automation.Cmdlet.Throwterminatingerror\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[<span data-ttu-id="1a92d-116">System. Management. Automation. cmdlet. WriteError</span><span class="sxs-lookup"><span data-stu-id="1a92d-116">System.Management.Automation.Cmdlet.WriteError</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="1a92d-117">Registros de erro do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a92d-117">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

<span data-ttu-id="1a92d-118">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="1a92d-118">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
