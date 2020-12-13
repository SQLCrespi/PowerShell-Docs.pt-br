---
ms.date: 09/13/2016
ms.topic: reference
title: Atributos de cmdlet
description: Atributos de cmdlet
ms.openlocfilehash: 6a106f33cb34c6c33b88a981815543bc9af4e4ba
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653510"
---
# <a name="cmdlet-attributes"></a><span data-ttu-id="8e815-103">Atributos de cmdlet</span><span class="sxs-lookup"><span data-stu-id="8e815-103">Cmdlet Attributes</span></span>

<span data-ttu-id="8e815-104">O Windows PowerShell define vários atributos que você pode usar para adicionar funcionalidade comum aos seus cmdlets sem implementar essa funcionalidade dentro de seu próprio código.</span><span class="sxs-lookup"><span data-stu-id="8e815-104">Windows PowerShell defines several attributes that you can use to add common functionality to your cmdlets without implementing that functionality within your own code.</span></span> <span data-ttu-id="8e815-105">Isso inclui o atributo cmdlet que identifica uma classe Microsoft .NET Framework como uma classe de cmdlet, o atributo OutputType que especifica os tipos de .NET Framework retornados pelo cmdlet, o atributo de parâmetro que identifica as propriedades públicas como parâmetros de cmdlet e muito mais.</span><span class="sxs-lookup"><span data-stu-id="8e815-105">This includes the Cmdlet attribute that identifies a Microsoft .NET Framework class as a cmdlet class, the OutputType attribute that specifies the .NET Framework types returned by the cmdlet, the Parameter attribute that identifies public properties as cmdlet parameters, and more.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8e815-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="8e815-106">In This Section</span></span>

<span data-ttu-id="8e815-107">[Atributos no código do cmdlet](./attributes-in-cmdlet-code.md) Descreve o benefício de usar atributos no código de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8e815-107">[Attributes in Cmdlet Code](./attributes-in-cmdlet-code.md) Describes the benefit of using attributes in cmdlet code.</span></span>

<span data-ttu-id="8e815-108">[Tipos de atributo](./attribute-types.md) Descreve os diferentes atributos que podem decorar uma classe de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8e815-108">[Attribute Types](./attribute-types.md) Describes the different attributes that can decorate a cmdlet class.</span></span>

<span data-ttu-id="8e815-109">[Declaração de atributo de alias](./alias-attribute-declaration.md) Descreve como definir aliases para um nome de parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8e815-109">[Alias Attribute Declaration](./alias-attribute-declaration.md) Describes how to define aliases for a cmdlet parameter name.</span></span>

<span data-ttu-id="8e815-110">[Declaração de atributo de cmdlet](./cmdlet-attribute-declaration.md) Descreve como definir uma classe de .NET Framework como um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8e815-110">[Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md) Describes how to define a .NET Framework class as a cmdlet.</span></span>

<span data-ttu-id="8e815-111">[Declaração de atributo de credencial](./credential-attribute-declaration.md) Descreve como adicionar suporte para converter a entrada de cadeia de caracteres em um objeto [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) .</span><span class="sxs-lookup"><span data-stu-id="8e815-111">[Credential Attribute Declaration](./credential-attribute-declaration.md) Describes how to add support for converting string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span>

<span data-ttu-id="8e815-112">[Declaração de atributo OutputType](./outputtype-attribute-declaration.md) Descreve como especificar os tipos de .NET Framework retornados pelo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8e815-112">[OutputType attribute Declaration](./outputtype-attribute-declaration.md) Describes how to specify the .NET Framework types returned by the cmdlet.</span></span>

<span data-ttu-id="8e815-113">[Declaração de atributo de parâmetro](./parameter-attribute-declaration.md) Descreve como definir os parâmetros de um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8e815-113">[Parameter Attribute Declaration](./parameter-attribute-declaration.md) Describes how to define the parameters of a cmdlet.</span></span>

<span data-ttu-id="8e815-114">[Declaração de atributo ValidateCount](./validatecount-attribute-declaration.md) Descreve como definir quantos argumentos são permitidos para um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e815-114">[ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md) Describes how to define how many arguments are allowed for a parameter.</span></span>

<span data-ttu-id="8e815-115">[Declaração de atributo ValidateLength](./validatelength-attribute-declaration.md) Descreve como definir o comprimento (em caracteres) de um argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e815-115">[ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md) Describes how to define the length (in characters) of a parameter argument.</span></span>

<span data-ttu-id="8e815-116">[Declaração de atributo ValidatePattern](./validatepattern-attribute-declaration.md) Descreve como definir os padrões válidos para um argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e815-116">[ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md) Describes how to define the valid patterns for a parameter argument.</span></span>

<span data-ttu-id="8e815-117">[Declaração de atributo ValidateRange](./validaterange-attribute-declaration.md) Descreve como definir o intervalo válido para um argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e815-117">[ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md) Describes how to define the valid range for a parameter argument.</span></span>

<span data-ttu-id="8e815-118">[Declaração de atributo ValidateSet](./validateset-attribute-declaration.md) Descreve como definir os valores possíveis para um argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8e815-118">[ValidateSet Attribute Declaration](./validateset-attribute-declaration.md) Describes how to define the possible values for a parameter argument.</span></span>

## <a name="reference"></a><span data-ttu-id="8e815-119">Referência</span><span class="sxs-lookup"><span data-stu-id="8e815-119">Reference</span></span>

<span data-ttu-id="8e815-120">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="8e815-120">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
