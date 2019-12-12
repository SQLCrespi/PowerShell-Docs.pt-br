---
title: Declaração de atributo de alias | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Alias attribute
- attributes, Alias
- Alias attribute, described
ms.assetid: d0df3a46-b1cc-42b9-beb1-e16bce254007
caps.latest.revision: 10
ms.openlocfilehash: 4d20672c5181c994c1b53624f6c42a301db11f26
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72370015"
---
# <a name="alias-attribute-declaration"></a>Declaração de atributo de alias

O atributo alias permite que o usuário especifique nomes diferentes para um parâmetro de cmdlet. Os aliases podem ser usados para fornecer atalhos para um nome de parâmetro ou podem fornecer nomes diferentes que são apropriados para cenários diferentes.

## <a name="syntax"></a>Sintaxe

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a>Parâmetros

é necessário `aliasName` (String []). Especifica um conjunto de nomes de alias separados por vírgula para o parâmetro de cmdlet.

## <a name="remarks"></a>Comentários

- O atributo alias é usado com o atributo Parameter quando você especifica um parâmetro de cmdlet. Para obter mais informações sobre como declarar esses atributos, consulte [como declarar parâmetros de cmdlet](./how-to-declare-cmdlet-parameters.md).

- Cada nome de alias deve ser exclusivo dentro de um cmdlet. O Windows PowerShell não verifica nomes de alias duplicados.

- O atributo alias é usado uma vez para cada parâmetro em um cmdlet.

- O atributo alias é definido pela classe [System. Management. Automation. AliasAttribute](/dotnet/api/System.Management.Automation.AliasAttribute) .

## <a name="see-also"></a>Consulte Também

[Aliases de parâmetro](./parameter-aliases.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
