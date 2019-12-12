---
title: Como declarar conjuntos de parâmetros | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46905eb9-64d7-4c55-9c2a-7bc7bf04e14b
caps.latest.revision: 10
ms.openlocfilehash: 6c2e5891a8e3f24969c12a2e57dc5ae8caa68e41
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365605"
---
# <a name="how-to-declare-parameter-sets"></a>Como declarar conjuntos de parâmetros

Este exemplo mostra como definir dois conjuntos de parâmetros quando você declara os parâmetros para um cmdlet. Cada conjunto de parâmetros tem um parâmetro exclusivo e um parâmetro compartilhado que é usado por ambos os conjuntos de parâmetros. Para obter mais informações sobre conjuntos de parâmetros, incluindo como especificar o conjunto de parâmetros padrão, consulte [conjuntos de parâmetros de cmdlet](./cmdlet-parameter-sets.md).

> [!IMPORTANT]
> Sempre que possível, defina o parâmetro exclusivo de um conjunto de parâmetros como um parâmetro necessário. No entanto, se você quiser que o cmdlet seja executado sem especificar parâmetros, o parâmetro exclusivo poderá ser um parâmetro opcional. Por exemplo, o parâmetro exclusivo do cmdlet `Get-Command` é opcional.

## <a name="how-to-define-two-parameter-sets"></a>Como definir dois conjuntos de parâmetros

1. Adicione a palavra-chave `ParameterSet` ao atributo de parâmetro para o parâmetro exclusivo do primeiro conjunto de parâmetros.

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test01")]
   public string UserName
   {
     get { return userName; }
     set { userName = value; }
   }
   private string userName;
   ```

2. Adicione a palavra-chave `ParameterSet` ao atributo Parameter para o parâmetro exclusivo do segundo conjunto de parâmetros.

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test02")]
   public string ComputerName
   {
     get { return computerName; }
     set { computerName = value; }
   }
   private string computerName;
   ```

3. Para o parâmetro que pertence a ambos os conjuntos de parâmetros, adicione um atributo de parâmetro para cada conjunto de parâmetros e, em seguida, adicione a palavra-chave `ParameterSet` a cada conjunto. Em cada atributo de parâmetro, você pode especificar como esse parâmetro é definido. Um parâmetro pode ser opcional em um conjunto e obrigatório em outro.

   ```csharp
   [Parameter(Mandatory= true, ParameterSetName = "Test01")]
   [Parameter(ParameterSetName = "Test02")]
   public string SharedParam
   {
       get { return sharedParam; }
       set { sharedParam = value; }
   }
   private string sharedParam;
   ```

## <a name="see-also"></a>Consulte Também

[Conjuntos de parâmetros de cmdlet](./cmdlet-parameter-sets.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
