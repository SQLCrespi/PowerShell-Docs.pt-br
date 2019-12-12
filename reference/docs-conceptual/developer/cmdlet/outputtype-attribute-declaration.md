---
title: Declaração de atributo OutputType | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a97a98ee-ffc0-42f0-a9a6-b0717b39c798
caps.latest.revision: 5
ms.openlocfilehash: 7aa6fa407e509a31c4066c4f73ae01b02b2f338c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365335"
---
# <a name="outputtype-attribute-declaration"></a>Declaração de atributo OutputType

O atributo `OutputType` identifica os tipos de .NET Framework retornados por um cmdlet, uma função ou um script.

## <a name="syntax"></a>Sintaxe

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a>Parâmetros

Digite (`string[]` ou `Type[]`) necessário. Especifica os tipos retornados pela função de cmdlet ou script.

ParameterSetName (String []) opcional. Especifica os conjuntos de parâmetros que retornam os tipos especificados no parâmetro `type`.

providerCmdlet opcional. Especifica o cmdlet do provedor que retorna os tipos especificados no parâmetro `type`.

## <a name="see-also"></a>Consulte Também

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
