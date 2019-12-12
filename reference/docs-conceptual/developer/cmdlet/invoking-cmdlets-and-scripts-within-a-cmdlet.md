---
title: Invocando cmdlets e scripts dentro de um cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7040a5c-4a47-42df-a2ea-96b134a4ed9b
caps.latest.revision: 10
ms.openlocfilehash: f20708ff41d9a6de90090997a875ba5371eccd74
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364285"
---
# <a name="invoking-cmdlets-and-scripts-within-a-cmdlet"></a>Invocar cmdlets e scripts dentro de um cmdlet

Um cmdlet pode invocar outros cmdlets e scripts de dentro do método de processamento de entrada do cmdlet. Isso permite que você adicione a funcionalidade de cmdlets e scripts existentes ao seu cmdlet sem precisar reescrever o código.

## <a name="the-invoke-method"></a>O método Invoke

Todos os cmdlets podem invocar um cmdlet existente chamando o método [System. Management. Automation. cmdlet. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) de dentro de um método de processamento de entrada, como [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), que é substituído pelo cmdlet. No entanto, você pode invocar somente os cmdlets que derivam diretamente da classe [System. Management. Automation. cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) . Não é possível invocar um cmdlet derivado da classe [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) .

O método [System. Management. Automation. cmdlet. Invoke *](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) tem as variantes a seguir.

[System. Management. Automation. cmdlet. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) esta variante invoca o objeto cmdlet e retorna uma coleção de objetos de tipo "T".

[System. Management. Automation. cmdlet. Invoke](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) esta variante invoca o objeto cmdlet e retorna um emumerator com rigidez de tipos. Essa variante permite que o usuário use os objetos na coleção para executar operações personalizadas.

## <a name="examples"></a>Exemplos

|Exemplo|Descrição|
|-------------|-----------------|
|[Invocando cmdlets dentro de um cmdlet](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)|Este exemplo mostra como invocar um cmdlet de dentro de outro cmdlet.|
|[Invocando scripts dentro de um cmdlet](./how-to-invoke-scripts-within-a-cmdlet.md)|Este exemplo mostra como invocar um script que é fornecido para o cmdlet de dentro de outro cmdlet.|

## <a name="see-also"></a>Consulte Também

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
