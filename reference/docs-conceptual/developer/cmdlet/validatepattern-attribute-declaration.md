---
ms.date: 09/13/2016
ms.topic: reference
title: Declaração de atributo ValidatePattern
description: Declaração de atributo ValidatePattern
ms.openlocfilehash: 364f63d2c52563eaefe64bcbb2bbae511bccb074
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646176"
---
# <a name="validatepattern-attribute-declaration"></a><span data-ttu-id="cc322-103">Declaração de atributo ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="cc322-103">ValidatePattern Attribute Declaration</span></span>

<span data-ttu-id="cc322-104">O atributo ValidatePattern especifica um padrão de expressão regular que valida o argumento de um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cc322-104">The ValidatePattern attribute specifies a regular expression pattern that validates the argument of a cmdlet parameter.</span></span> <span data-ttu-id="cc322-105">Esse atributo também pode ser usado pelas funções do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc322-105">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="cc322-106">Quando ValidatePattern é invocado em um cmdlet, o tempo de execução do Windows PowerShell converte o argumento do parâmetro cmdlet em uma cadeia de caracteres e, em seguida, compara essa cadeia de caracteres com o padrão fornecido pelo atributo ValidatePattern.</span><span class="sxs-lookup"><span data-stu-id="cc322-106">When ValidatePattern is invoked within a cmdlet, the Windows PowerShell runtime converts the argument of the cmdlet parameter to a string and then compares that string to the pattern supplied by the ValidatePattern attribute.</span></span> <span data-ttu-id="cc322-107">O cmdlet será executado somente se a representação de cadeia de caracteres convertida do argumento e a correspondência de padrão fornecida.</span><span class="sxs-lookup"><span data-stu-id="cc322-107">The cmdlet is run only if the converted string representation of the argument and the supplied pattern match.</span></span> <span data-ttu-id="cc322-108">Se eles não corresponderem, um erro será gerado pelo tempo de execução do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc322-108">If they do not match, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="cc322-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cc322-109">Syntax</span></span>

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="cc322-110">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="cc322-110">Parameters</span></span>

<span data-ttu-id="cc322-111">`RegexString` ([System. String](/dotnet/api/System.String)) necessário.</span><span class="sxs-lookup"><span data-stu-id="cc322-111">`RegexString` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="cc322-112">Especifica uma expressão regular que valida o argumento do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="cc322-112">Specifies a regular expression that validates the parameter argument.</span></span>

<span data-ttu-id="cc322-113">Opções ([System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) parâmetro nomeado opcional.</span><span class="sxs-lookup"><span data-stu-id="cc322-113">Options ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) Optional named parameter.</span></span> <span data-ttu-id="cc322-114">Especifica uma combinação de bits-bit que indica os sinalizadores [System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) que especificam opções de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="cc322-114">Specifies a bitwise combination of [System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) flags that specify regular expression options.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc322-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="cc322-115">Remarks</span></span>

- <span data-ttu-id="cc322-116">Esse atributo pode ser usado apenas uma vez por parâmetro.</span><span class="sxs-lookup"><span data-stu-id="cc322-116">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="cc322-117">Você pode usar o `Option` parâmetro do atributo para definir ainda mais o padrão.</span><span class="sxs-lookup"><span data-stu-id="cc322-117">You can use the `Option` parameter of the attribute to further define the pattern.</span></span> <span data-ttu-id="cc322-118">Por exemplo, você pode tornar o padrão diferenciar maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="cc322-118">For example, you can make the pattern case sensitive.</span></span>

- <span data-ttu-id="cc322-119">Se esse atributo for aplicado a uma coleção, cada elemento na coleção deverá corresponder ao padrão.</span><span class="sxs-lookup"><span data-stu-id="cc322-119">If this attribute is applied to a collection, each element in the collection must match the pattern.</span></span>

- <span data-ttu-id="cc322-120">O atributo ValidatePattern é definido pela classe [System. Management. Automation. Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) .</span><span class="sxs-lookup"><span data-stu-id="cc322-120">The ValidatePattern attribute is defined by the [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc322-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cc322-121">See Also</span></span>

[<span data-ttu-id="cc322-122">System. Management. Automation. Validatepatternattribute</span><span class="sxs-lookup"><span data-stu-id="cc322-122">System.Management.Automation.Validatepatternattribute</span></span>](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

<span data-ttu-id="cc322-123">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="cc322-123">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
