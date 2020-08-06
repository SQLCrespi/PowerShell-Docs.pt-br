---
title: Declaração de atributo ValidatePattern | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidatePattern
- ValidatePattern attribute, described
- ValidatePattern attribute
ms.openlocfilehash: 713fa7a46a8eeefdbfd679a5e8436285fac085f8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787794"
---
# <a name="validatepattern-attribute-declaration"></a><span data-ttu-id="9d05e-102">Declaração de atributo ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="9d05e-102">ValidatePattern Attribute Declaration</span></span>

<span data-ttu-id="9d05e-103">O atributo ValidatePattern especifica um padrão de expressão regular que valida o argumento de um parâmetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9d05e-103">The ValidatePattern attribute specifies a regular expression pattern that validates the argument of a cmdlet parameter.</span></span> <span data-ttu-id="9d05e-104">Esse atributo também pode ser usado pelas funções do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d05e-104">This attribute can also be used by Windows PowerShell functions.</span></span>

<span data-ttu-id="9d05e-105">Quando ValidatePattern é invocado em um cmdlet, o tempo de execução do Windows PowerShell converte o argumento do parâmetro cmdlet em uma cadeia de caracteres e, em seguida, compara essa cadeia de caracteres com o padrão fornecido pelo atributo ValidatePattern.</span><span class="sxs-lookup"><span data-stu-id="9d05e-105">When ValidatePattern is invoked within a cmdlet, the Windows PowerShell runtime converts the argument of the cmdlet parameter to a string and then compares that string to the pattern supplied by the ValidatePattern attribute.</span></span> <span data-ttu-id="9d05e-106">O cmdlet será executado somente se a representação de cadeia de caracteres convertida do argumento e a correspondência de padrão fornecida.</span><span class="sxs-lookup"><span data-stu-id="9d05e-106">The cmdlet is run only if the converted string representation of the argument and the supplied pattern match.</span></span> <span data-ttu-id="9d05e-107">Se eles não corresponderem, um erro será gerado pelo tempo de execução do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d05e-107">If they do not match, an error is thrown by the Windows PowerShell runtime.</span></span>

## <a name="syntax"></a><span data-ttu-id="9d05e-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9d05e-108">Syntax</span></span>

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a><span data-ttu-id="9d05e-109">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9d05e-109">Parameters</span></span>

<span data-ttu-id="9d05e-110">`RegexString`([System. String](/dotnet/api/System.String)) necessário.</span><span class="sxs-lookup"><span data-stu-id="9d05e-110">`RegexString` ([System.String](/dotnet/api/System.String)) Required.</span></span> <span data-ttu-id="9d05e-111">Especifica uma expressão regular que valida o argumento do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="9d05e-111">Specifies a regular expression that validates the parameter argument.</span></span>

<span data-ttu-id="9d05e-112">Opções ([System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) parâmetro nomeado opcional.</span><span class="sxs-lookup"><span data-stu-id="9d05e-112">Options ([System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) Optional named parameter.</span></span> <span data-ttu-id="9d05e-113">Especifica uma combinação de bits-bit que indica os sinalizadores [System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) que especificam opções de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="9d05e-113">Specifies a bitwise combination of [System.Text.Regularexpressions.Regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) flags that specify regular expression options.</span></span>

## <a name="remarks"></a><span data-ttu-id="9d05e-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="9d05e-114">Remarks</span></span>

- <span data-ttu-id="9d05e-115">Esse atributo pode ser usado apenas uma vez por parâmetro.</span><span class="sxs-lookup"><span data-stu-id="9d05e-115">This attribute can be used only once per parameter.</span></span>

- <span data-ttu-id="9d05e-116">Você pode usar o `Option` parâmetro do atributo para definir ainda mais o padrão.</span><span class="sxs-lookup"><span data-stu-id="9d05e-116">You can use the `Option` parameter of the attribute to further define the pattern.</span></span> <span data-ttu-id="9d05e-117">Por exemplo, você pode tornar o padrão diferenciar maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9d05e-117">For example, you can make the pattern case sensitive.</span></span>

- <span data-ttu-id="9d05e-118">Se esse atributo for aplicado a uma coleção, cada elemento na coleção deverá corresponder ao padrão.</span><span class="sxs-lookup"><span data-stu-id="9d05e-118">If this attribute is applied to a collection, each element in the collection must match the pattern.</span></span>

- <span data-ttu-id="9d05e-119">O atributo ValidatePattern é definido pela classe [System. Management. Automation. Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) .</span><span class="sxs-lookup"><span data-stu-id="9d05e-119">The ValidatePattern attribute is defined by the [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d05e-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9d05e-120">See Also</span></span>

[<span data-ttu-id="9d05e-121">System. Management. Automation. Validatepatternattribute</span><span class="sxs-lookup"><span data-stu-id="9d05e-121">System.Management.Automation.Validatepatternattribute</span></span>](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[<span data-ttu-id="9d05e-122">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d05e-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
