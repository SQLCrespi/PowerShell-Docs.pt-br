---
title: Declaração de atributo ValidatePattern | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidatePattern
- ValidatePattern attribute, described
- ValidatePattern attribute
ms.assetid: 87b811be-6d93-4e7d-b9d0-c567a19bb0ef
caps.latest.revision: 13
ms.openlocfilehash: 5edcb65a6fbe1cb2fe2d0efe3f763fb84628b049
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067120"
---
# <a name="validatepattern-attribute-declaration"></a><span data-ttu-id="f80bf-102">Declaração de atributo ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="f80bf-102">ValidatePattern Attribute Declaration</span></span>

<span data-ttu-id="f80bf-103">O atributo ValidatePattern Especifica um padrão de expressão regular que valida o argumento de um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f80bf-103">The ValidatePattern attribute specifies a regular expression pattern that validates the argument of a cmdlet parameter.</span></span> <span data-ttu-id="f80bf-104">Esse atributo também pode ser usado por funções do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f80bf-104">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="f80bf-105">Quando ValidatePattern é chamado dentro de um cmdlet, o tempo de execução do Windows PowerShell converte o argumento do parâmetro de cmdlet em uma cadeia de caracteres e, em seguida, compara o padrão fornecido pelo atributo ValidatePattern essa cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f80bf-105">When ValidatePattern is invoked within a cmdlet, the Windows PowerShell runtime converts the argument of the cmdlet parameter to a string and then compares that string to the pattern supplied by the ValidatePattern attribute.</span></span> <span data-ttu-id="f80bf-106">O cmdlet é executado somente se corresponderem a representação de cadeia de caracteres convertida de argumento e o padrão fornecido.</span><span class="sxs-lookup"><span data-stu-id="f80bf-106">The cmdlet is run only if the converted string representation of the argument and the supplied pattern match.</span></span> <span data-ttu-id="f80bf-107">Se eles não coincidirem, um erro é gerado pelo tempo de execução do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f80bf-107">If they do not match, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="f80bf-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f80bf-108">Syntax</span></span>

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="f80bf-109">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f80bf-109">Parameters</span></span>

<span data-ttu-id="f80bf-110">`RegexString` ([System. String](/dotnet/api/System.String)) necessário.</span><span class="sxs-lookup"><span data-stu-id="f80bf-110">`RegexString` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="f80bf-111">Especifica uma expressão regular que valida o argumento do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="f80bf-111">Specifies a regular expression that validates the parameter argument.</span></span>

<span data-ttu-id="f80bf-112">Opções ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) parâmetro nomeado opcional.</span><span class="sxs-lookup"><span data-stu-id="f80bf-112">Options ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) Optional named parameter.</span></span> <span data-ttu-id="f80bf-113">Especifica uma combinação bit a bit dos [System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) sinalizadores que especificam opções de expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="f80bf-113">Specifies a bitwise combination of [System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) flags that specify regular expression options.</span></span>

## <a name="remarks"></a><span data-ttu-id="f80bf-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="f80bf-114">Remarks</span></span>

- <span data-ttu-id="f80bf-115">Esse atributo pode ser usado apenas uma vez por parâmetro.</span><span class="sxs-lookup"><span data-stu-id="f80bf-115">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="f80bf-116">Você pode usar o `Option` parâmetro do atributo para definir ainda mais o padrão.</span><span class="sxs-lookup"><span data-stu-id="f80bf-116">You can use the `Option` parameter of the attribute to further define the pattern.</span></span> <span data-ttu-id="f80bf-117">Por exemplo, você pode fazer o padrão de maiusculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f80bf-117">For example, you can make the pattern case sensitive.</span></span>

- <span data-ttu-id="f80bf-118">Se esse atributo é aplicado a uma coleção, cada elemento da coleção deve corresponder ao padrão.</span><span class="sxs-lookup"><span data-stu-id="f80bf-118">If this attribute is applied to a collection, each element in the collection must match the pattern.</span></span>

- <span data-ttu-id="f80bf-119">O atributo ValidatePattern é definido pela [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) classe.</span><span class="sxs-lookup"><span data-stu-id="f80bf-119">The ValidatePattern attribute is defined by the [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="f80bf-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f80bf-120">See Also</span></span>

[<span data-ttu-id="f80bf-121">System.Management.Automation.Validatepatternattribute</span><span class="sxs-lookup"><span data-stu-id="f80bf-121">System.Management.Automation.Validatepatternattribute</span></span>](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

<span data-ttu-id="f80bf-122">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f80bf-122">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
