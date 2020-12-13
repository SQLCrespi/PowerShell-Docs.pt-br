---
ms.date: 09/13/2016
ms.topic: reference
title: Declaração de atributo OutputType
description: Declaração de atributo OutputType
ms.openlocfilehash: b5e33346e9ac29c13323781d62daffab892573a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646458"
---
# <a name="outputtype-attribute-declaration"></a>Declaração de atributo OutputType

O `OutputType` atributo identifica os tipos de .NET Framework retornados por um cmdlet, uma função ou um script.

## <a name="syntax"></a>Sintaxe

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a>Parâmetros

Digite ( `string[]` ou `Type[]` ) obrigatório. Especifica os tipos retornados pela função de cmdlet ou script.

ParameterSetName (String []) opcional. Especifica os conjuntos de parâmetros que retornam os tipos especificados no `type` parâmetro.

providerCmdlet opcional. Especifica o cmdlet do provedor que retorna os tipos especificados no `type` parâmetro.

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
