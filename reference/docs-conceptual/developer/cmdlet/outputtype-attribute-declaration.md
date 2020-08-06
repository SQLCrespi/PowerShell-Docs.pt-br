---
title: Declaração de atributo OutputType | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a4cc874031bba092cfef6041bef0e19e6af3f09c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786536"
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
