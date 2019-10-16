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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369955"
---
# <a name="cmdlet-attributes"></a><span data-ttu-id="dcaf8-102">Atributos de cmdlet</span><span class="sxs-lookup"><span data-stu-id="dcaf8-102">Cmdlet Attributes</span></span>

<span data-ttu-id="dcaf8-103">O Windows PowerShell define vários atributos que você pode usar para adicionar funcionalidade comum aos seus cmdlets sem implementar essa funcionalidade dentro de seu próprio código.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-103">Windows PowerShell defines several attributes that you can use to add common functionality to your cmdlets without implementing that functionality within your own code.</span></span> <span data-ttu-id="dcaf8-104">Isso inclui o atributo cmdlet que identifica uma classe Microsoft .NET Framework como uma classe de cmdlet, o atributo OutputType que especifica os tipos de .NET Framework retornados pelo cmdlet, o atributo de parâmetro que identifica as propriedades públicas como cmdlet parâmetros e muito mais.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-104">This includes the Cmdlet attribute that identifies a Microsoft .NET Framework class as a cmdlet class, the OutputType attribute that specifies the .NET Framework types returned by the cmdlet, the Parameter attribute that identifies public properties as cmdlet parameters, and more.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="dcaf8-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="dcaf8-105">In This Section</span></span>

<span data-ttu-id="dcaf8-106">[Atributos no código do cmdlet](./attributes-in-cmdlet-code.md) Descreve o benefício de usar atributos no código de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-106">[Attributes in Cmdlet Code](./attributes-in-cmdlet-code.md) Describes the benefit of using attributes in cmdlet code.</span></span>

<span data-ttu-id="dcaf8-107">[Tipos de atributo](./attribute-types.md) Descreve os diferentes atributos que podem decorar uma classe de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-107">[Attribute Types](./attribute-types.md) Describes the different attributes that can decorate a cmdlet class.</span></span>

<span data-ttu-id="dcaf8-108">[Declaração de atributo de alias](./alias-attribute-declaration.md) Descreve como definir aliases para um nome de parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-108">[Alias Attribute Declaration](./alias-attribute-declaration.md) Describes how to define aliases for a cmdlet parameter name.</span></span>

<span data-ttu-id="dcaf8-109">[Declaração de atributo de cmdlet](./cmdlet-attribute-declaration.md) Descreve como definir uma classe de .NET Framework como um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-109">[Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md) Describes how to define a .NET Framework class as a cmdlet.</span></span>

<span data-ttu-id="dcaf8-110">[Declaração de atributo de credencial](./credential-attribute-declaration.md) Descreve como adicionar suporte para converter a entrada de cadeia de caracteres em um objeto [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) .</span><span class="sxs-lookup"><span data-stu-id="dcaf8-110">[Credential Attribute Declaration](./credential-attribute-declaration.md) Describes how to add support for converting string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span>

<span data-ttu-id="dcaf8-111">[Declaração de atributo OutputType](./outputtype-attribute-declaration.md) Descreve como especificar os tipos de .NET Framework retornados pelo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-111">[OutputType attribute Declaration](./outputtype-attribute-declaration.md) Describes how to specify the .NET Framework types returned by the cmdlet.</span></span>

<span data-ttu-id="dcaf8-112">[Declaração de atributo de parâmetro](./parameter-attribute-declaration.md) Descreve como definir os parâmetros de um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-112">[Parameter Attribute Declaration](./parameter-attribute-declaration.md) Describes how to define the parameters of a cmdlet.</span></span>

<span data-ttu-id="dcaf8-113">[Declaração de atributo ValidateCount](./validatecount-attribute-declaration.md) Descreve como definir quantos argumentos são permitidos para um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-113">[ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md) Describes how to define how many arguments are allowed for a parameter.</span></span>

<span data-ttu-id="dcaf8-114">[Declaração de atributo ValidateLength](./validatelength-attribute-declaration.md) Descreve como definir o comprimento (em caracteres) de um argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-114">[ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md) Describes how to define the length (in characters) of a parameter argument.</span></span>

<span data-ttu-id="dcaf8-115">[Declaração de atributo ValidatePattern](./validatepattern-attribute-declaration.md) Descreve como definir os padrões válidos para um argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-115">[ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md) Describes how to define the valid patterns for a parameter argument.</span></span>

<span data-ttu-id="dcaf8-116">[Declaração de atributo ValidateRange](./validaterange-attribute-declaration.md) Descreve como definir o intervalo válido para um argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-116">[ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md) Describes how to define the valid range for a parameter argument.</span></span>

<span data-ttu-id="dcaf8-117">[Declaração de atributo ValidateSet](./validateset-attribute-declaration.md) Descreve como definir os valores possíveis para um argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="dcaf8-117">[ValidateSet Attribute Declaration](./validateset-attribute-declaration.md) Describes how to define the possible values for a parameter argument.</span></span>

## <a name="reference"></a><span data-ttu-id="dcaf8-118">Referência</span><span class="sxs-lookup"><span data-stu-id="dcaf8-118">Reference</span></span>

<span data-ttu-id="dcaf8-119">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="dcaf8-119">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
