---
ms.date: 09/13/2016
ms.topic: reference
title: Como declarar conjuntos de parâmetros
description: Como declarar conjuntos de parâmetros
ms.openlocfilehash: bd4d504a9fe6c7f7626901c49bc08851244f0995
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667055"
---
# <a name="how-to-declare-parameter-sets"></a>Como declarar conjuntos de parâmetros

Este exemplo mostra como definir dois conjuntos de parâmetros quando você declara os parâmetros para um cmdlet. Cada conjunto de parâmetros tem um parâmetro exclusivo e um parâmetro compartilhado que é usado por ambos os conjuntos de parâmetros. Para obter mais informações sobre conjuntos de parâmetros, incluindo como especificar o conjunto de parâmetros padrão, consulte [conjuntos de parâmetros de cmdlet](./cmdlet-parameter-sets.md).

> [!IMPORTANT]
> Sempre que possível, defina o parâmetro exclusivo de um conjunto de parâmetros como um parâmetro necessário. No entanto, se você quiser que o cmdlet seja executado sem especificar parâmetros, o parâmetro exclusivo poderá ser um parâmetro opcional. Por exemplo, o parâmetro exclusivo do `Get-Command` cmdlet é opcional.

## <a name="how-to-define-two-parameter-sets"></a>Como definir dois conjuntos de parâmetros

1. Adicione a `ParameterSet` palavra-chave ao atributo de parâmetro para o parâmetro exclusivo do primeiro conjunto de parâmetros.

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

2. Adicione a `ParameterSet` palavra-chave ao atributo de parâmetro para o parâmetro exclusivo do segundo conjunto de parâmetros.

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

3. Para o parâmetro que pertence a ambos os conjuntos de parâmetros, adicione um atributo de parâmetro para cada conjunto de parâmetros e, em seguida, adicione a `ParameterSet` palavra-chave a cada conjunto. Em cada atributo de parâmetro, você pode especificar como esse parâmetro é definido. Um parâmetro pode ser opcional em um conjunto e obrigatório em outro.

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

[Conjuntos de parâmetros do cmdlet](./cmdlet-parameter-sets.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
