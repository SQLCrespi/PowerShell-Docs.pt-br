---
title: Invocando cmdlets e scripts dentro de um cmdlet | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 3d5f76242c02763c41b81215bbb031e19869066a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786570"
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

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
