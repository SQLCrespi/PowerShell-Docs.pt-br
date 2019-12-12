---
title: Erros de não encerramento | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 468dabd6-bfeb-448d-8e09-0996db516edd
caps.latest.revision: 8
ms.openlocfilehash: 5f804756e0e3e867832f15f50967fd6987f160a5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369595"
---
# <a name="non-terminating-errors"></a><span data-ttu-id="3b908-102">Erros de não encerramento</span><span class="sxs-lookup"><span data-stu-id="3b908-102">Non-Terminating Errors</span></span>

<span data-ttu-id="3b908-103">Este tópico discute o método usado para relatar erros de não encerramento.</span><span class="sxs-lookup"><span data-stu-id="3b908-103">This topic discusses the method used to report non-terminating errors.</span></span> <span data-ttu-id="3b908-104">Ele também aborda como chamar o método de dentro do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3b908-104">It also discusses how to call the method from within the cmdlet.</span></span>

<span data-ttu-id="3b908-105">Quando ocorre um erro de não finalização, o cmdlet deve relatar esse erro chamando o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) .</span><span class="sxs-lookup"><span data-stu-id="3b908-105">When a non-terminating error occurs, the cmdlet should report this error by calling the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method.</span></span> <span data-ttu-id="3b908-106">Quando o cmdlet relata um erro de não finalização, o cmdlet pode continuar a operar nesse objeto de entrada e em outros objetos de pipeline de entrada.</span><span class="sxs-lookup"><span data-stu-id="3b908-106">When the cmdlet reports a non-terminating error, the cmdlet can continue to operate on this input object and on further incoming pipeline objects.</span></span> <span data-ttu-id="3b908-107">Se o cmdlet chamar o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) , o cmdlet poderá gravar um registro de erro que descreve a condição que causou o erro de não finalização.</span><span class="sxs-lookup"><span data-stu-id="3b908-107">If the cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method, the cmdlet can write an error record that describes the condition that caused the non-terminating error.</span></span> <span data-ttu-id="3b908-108">Para obter mais informações sobre registros de erro, consulte [registros de erro do Windows PowerShell](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="3b908-108">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

<span data-ttu-id="3b908-109">Os cmdlets podem chamar [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) conforme a necessidade de dentro de seus métodos de processamento de entrada.</span><span class="sxs-lookup"><span data-stu-id="3b908-109">Cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) as necessary from within their input processing methods.</span></span> <span data-ttu-id="3b908-110">No entanto, os cmdlets podem chamar [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) somente a partir do thread que chamou o método [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)ou [System. Management. Automation. cmdlet.](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) endprocessation Input.</span><span class="sxs-lookup"><span data-stu-id="3b908-110">However, cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) only from the thread that called the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), or [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) input processing method.</span></span> <span data-ttu-id="3b908-111">Não chame [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) de outro thread.</span><span class="sxs-lookup"><span data-stu-id="3b908-111">Do not call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) from another thread.</span></span> <span data-ttu-id="3b908-112">Em vez disso, comunique os erros de volta para o thread principal.</span><span class="sxs-lookup"><span data-stu-id="3b908-112">Instead, communicate errors back to the main thread.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b908-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3b908-113">See Also</span></span>

[<span data-ttu-id="3b908-114">System. Management. Automation. cmdlet. WriteError</span><span class="sxs-lookup"><span data-stu-id="3b908-114">System.Management.Automation.Cmdlet.WriteError</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="3b908-115">System. Management. Automation. cmdlet. BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="3b908-115">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="3b908-116">System. Management. Automation. cmdlet. ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="3b908-116">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="3b908-117">Sistema. Management. Automation. cmdlet. endprocessation</span><span class="sxs-lookup"><span data-stu-id="3b908-117">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="3b908-118">Registros de erro do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b908-118">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

<span data-ttu-id="3b908-119">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="3b908-119">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
