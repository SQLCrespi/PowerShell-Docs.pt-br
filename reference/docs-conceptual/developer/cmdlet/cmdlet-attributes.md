---
title: Atributos de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes [PowerShell SDK]
- attributes [PowerShell SDK], described
ms.assetid: d3f4f652-d929-4c27-9358-9baa390a094c
caps.latest.revision: 14
ms.openlocfilehash: 326cd408e86402974569fc76d5e473be5a56f0b6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369955"
---
# <a name="cmdlet-attributes"></a>Atributos de cmdlet

O Windows PowerShell define vários atributos que você pode usar para adicionar funcionalidade comum aos seus cmdlets sem implementar essa funcionalidade dentro de seu próprio código. Isso inclui o atributo cmdlet que identifica uma classe Microsoft .NET Framework como uma classe de cmdlet, o atributo OutputType que especifica os tipos de .NET Framework retornados pelo cmdlet, o atributo de parâmetro que identifica as propriedades públicas como cmdlet parâmetros e muito mais.

## <a name="in-this-section"></a>Nesta seção

[Atributos no código do cmdlet](./attributes-in-cmdlet-code.md) Descreve o benefício de usar atributos no código de cmdlet.

[Tipos de atributo](./attribute-types.md) Descreve os diferentes atributos que podem decorar uma classe de cmdlet.

[Declaração de atributo de alias](./alias-attribute-declaration.md) Descreve como definir aliases para um nome de parâmetro de cmdlet.

[Declaração de atributo de cmdlet](./cmdlet-attribute-declaration.md) Descreve como definir uma classe de .NET Framework como um cmdlet.

[Declaração de atributo de credencial](./credential-attribute-declaration.md) Descreve como adicionar suporte para converter a entrada de cadeia de caracteres em um objeto [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) .

[Declaração de atributo OutputType](./outputtype-attribute-declaration.md) Descreve como especificar os tipos de .NET Framework retornados pelo cmdlet.

[Declaração de atributo de parâmetro](./parameter-attribute-declaration.md) Descreve como definir os parâmetros de um cmdlet.

[Declaração de atributo ValidateCount](./validatecount-attribute-declaration.md) Descreve como definir quantos argumentos são permitidos para um parâmetro.

[Declaração de atributo ValidateLength](./validatelength-attribute-declaration.md) Descreve como definir o comprimento (em caracteres) de um argumento de parâmetro.

[Declaração de atributo ValidatePattern](./validatepattern-attribute-declaration.md) Descreve como definir os padrões válidos para um argumento de parâmetro.

[Declaração de atributo ValidateRange](./validaterange-attribute-declaration.md) Descreve como definir o intervalo válido para um argumento de parâmetro.

[Declaração de atributo ValidateSet](./validateset-attribute-declaration.md) Descreve como definir os valores possíveis para um argumento de parâmetro.

## <a name="reference"></a>Referência

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
