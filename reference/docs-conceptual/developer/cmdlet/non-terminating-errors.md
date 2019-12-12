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
# <a name="non-terminating-errors"></a>Erros de não encerramento

Este tópico discute o método usado para relatar erros de não encerramento. Ele também aborda como chamar o método de dentro do cmdlet.

Quando ocorre um erro de não finalização, o cmdlet deve relatar esse erro chamando o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) . Quando o cmdlet relata um erro de não finalização, o cmdlet pode continuar a operar nesse objeto de entrada e em outros objetos de pipeline de entrada. Se o cmdlet chamar o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) , o cmdlet poderá gravar um registro de erro que descreve a condição que causou o erro de não finalização. Para obter mais informações sobre registros de erro, consulte [registros de erro do Windows PowerShell](./windows-powershell-error-records.md).

Os cmdlets podem chamar [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) conforme a necessidade de dentro de seus métodos de processamento de entrada. No entanto, os cmdlets podem chamar [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) somente a partir do thread que chamou o método [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)ou [System. Management. Automation. cmdlet.](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) endprocessation Input. Não chame [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) de outro thread. Em vez disso, comunique os erros de volta para o thread principal.

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[Sistema. Management. Automation. cmdlet. endprocessation](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[Registros de erro do Windows PowerShell](./windows-powershell-error-records.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
