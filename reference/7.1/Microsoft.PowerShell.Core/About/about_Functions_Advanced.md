---
description: Apresenta funções avançadas que são uma maneira de criar cmdlets usando scripts.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced
ms.openlocfilehash: 8f6964ee0b916163ea18e20ddbdf95d68e24f3fa
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196351"
---
# <a name="about-functions-advanced"></a><span data-ttu-id="f0854-104">Sobre as funções avançadas</span><span class="sxs-lookup"><span data-stu-id="f0854-104">About Functions Advanced</span></span>

## <a name="short-description"></a><span data-ttu-id="f0854-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="f0854-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="f0854-106">Apresenta funções avançadas que são uma maneira de criar cmdlets usando scripts.</span><span class="sxs-lookup"><span data-stu-id="f0854-106">Introduces advanced functions that are a way to create cmdlets using scripts.</span></span>

## <a name="long-description"></a><span data-ttu-id="f0854-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="f0854-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="f0854-108">Um cmdlet é um único comando que participa da semântica do pipeline do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0854-108">A cmdlet is a single command that participates in the pipeline semantics of PowerShell.</span></span> <span data-ttu-id="f0854-109">Isso inclui cmdlets binários, funções de script avançadas, CDXML e fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f0854-109">This includes binary cmdlets, advanced script functions, CDXML, and Workflows.</span></span>

<span data-ttu-id="f0854-110">As funções avançadas permitem criar cmdlets que são gravados como uma função do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0854-110">Advanced functions allow you create cmdlets that are written as a PowerShell function.</span></span> <span data-ttu-id="f0854-111">As funções avançadas facilitam a criação de cmdlets sem a necessidade de escrever e compilar um cmdlet binário.</span><span class="sxs-lookup"><span data-stu-id="f0854-111">Advanced functions make it easier to create cmdlets without having to write and compile a binary cmdlet.</span></span> <span data-ttu-id="f0854-112">Os cmdlets binários são classes .NET que são escritas em uma linguagem .NET, como C#.</span><span class="sxs-lookup"><span data-stu-id="f0854-112">Binary cmdlets are .NET classes that are written in a .NET language such as C#.</span></span>

<span data-ttu-id="f0854-113">As funções avançadas usam o `CmdletBinding` atributo para identificá-las como funções que atuam como cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f0854-113">Advanced functions use the `CmdletBinding` attribute to identify them as functions that act like cmdlets.</span></span> <span data-ttu-id="f0854-114">O `CmdletBinding` atributo é semelhante ao atributo cmdlet usado em classes de cmdlet compiladas para identificar a classe como um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f0854-114">The `CmdletBinding` attribute is similar to the Cmdlet attribute that is used in compiled cmdlet classes to identify the class as a cmdlet.</span></span> <span data-ttu-id="f0854-115">Para obter mais informações sobre esse atributo, consulte [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span><span class="sxs-lookup"><span data-stu-id="f0854-115">For more information about this attribute, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>

<span data-ttu-id="f0854-116">O exemplo a seguir mostra uma função que aceita um nome e, em seguida, imprime uma saudação usando o nome fornecido.</span><span class="sxs-lookup"><span data-stu-id="f0854-116">The following example shows a function that accepts a name and then prints a greeting using the supplied name.</span></span> <span data-ttu-id="f0854-117">Observe também que essa função define um nome que inclui um par de verbo (envio) e substantivo (saudação) como o par verbo-substantivo de um cmdlet compilado.</span><span class="sxs-lookup"><span data-stu-id="f0854-117">Also notice that this function defines a name that includes a verb (Send) and noun (Greeting) pair like the verb-noun pair of a compiled cmdlet.</span></span> <span data-ttu-id="f0854-118">No entanto, não é necessário que as funções tenham um nome de verbo-substantivo.</span><span class="sxs-lookup"><span data-stu-id="f0854-118">However, functions are not required to have a verb-noun name.</span></span>

```powershell
function Send-Greeting
{
    [CmdletBinding()]
    Param(
        [Parameter(Mandatory=$true)]
        [string] $Name
    )

    Process
    {
        Write-Host ("Hello " + $Name + "!")
    }
}
```

<span data-ttu-id="f0854-119">Os parâmetros da função são declarados usando o atributo Parameter.</span><span class="sxs-lookup"><span data-stu-id="f0854-119">The parameters of the function are declared by using the Parameter attribute.</span></span>
<span data-ttu-id="f0854-120">Esse atributo pode ser usado sozinha ou pode ser combinado com o atributo alias ou com vários outros atributos de validação de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="f0854-120">This attribute can be used alone, or it can be combined with the Alias attribute or with several other parameter validation attributes.</span></span> <span data-ttu-id="f0854-121">Para obter mais informações sobre como declarar parâmetros (incluindo parâmetros dinâmicos que são adicionados em tempo de execução), consulte [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f0854-121">For more information about how to declare parameters (including dynamic parameters that are added at runtime), see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

<span data-ttu-id="f0854-122">O trabalho real da função anterior é executado no bloco Process, que é equivalente ao método ProcessingRecord que é usado por cmdlets compilados para processar os dados que são passados para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f0854-122">The actual work of the previous function is performed in the Process block, which is equivalent to the ProcessingRecord method that is used by compiled cmdlets to process the data that is passed to the cmdlet.</span></span> <span data-ttu-id="f0854-123">Esse bloco, juntamente com os blocos Begin e end, é descrito no tópico [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) .</span><span class="sxs-lookup"><span data-stu-id="f0854-123">This block, along with the Begin and End blocks, is described in the [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) topic.</span></span>

<span data-ttu-id="f0854-124">As funções avançadas diferem dos cmdlets compilados das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="f0854-124">Advanced functions differ from compiled cmdlets in the following ways:</span></span>

- <span data-ttu-id="f0854-125">A associação de parâmetro de função avançada não gera uma exceção quando uma matriz de cadeias de caracteres está associada a um parâmetro booliano.</span><span class="sxs-lookup"><span data-stu-id="f0854-125">Advanced function parameter binding does not throw an exception when an array of strings is bound to a Boolean parameter.</span></span>
- <span data-ttu-id="f0854-126">O atributo ValidateSet e o atributo ValidatePattern não podem passar parâmetros nomeados.</span><span class="sxs-lookup"><span data-stu-id="f0854-126">The ValidateSet attribute and the ValidatePattern attribute cannot pass named parameters.</span></span>
- <span data-ttu-id="f0854-127">As funções avançadas não podem ser usadas em transações.</span><span class="sxs-lookup"><span data-stu-id="f0854-127">Advanced functions cannot be used in transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0854-128">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="f0854-128">SEE ALSO</span></span>

[<span data-ttu-id="f0854-129">about_Functions</span><span class="sxs-lookup"><span data-stu-id="f0854-129">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="f0854-130">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="f0854-130">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="f0854-131">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="f0854-131">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="f0854-132">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="f0854-132">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="f0854-133">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="f0854-133">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)
