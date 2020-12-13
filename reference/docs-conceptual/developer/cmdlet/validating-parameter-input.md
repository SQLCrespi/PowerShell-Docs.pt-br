---
ms.date: 09/13/2016
ms.topic: reference
title: Validação de entrada de parâmetro
description: Validação de entrada de parâmetro
ms.openlocfilehash: a97b5c670e8c36463a85bbef1506f6311bdd5ec3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660391"
---
# <a name="validating-parameter-input"></a><span data-ttu-id="5132f-103">Validação de entrada de parâmetro</span><span class="sxs-lookup"><span data-stu-id="5132f-103">Validating Parameter Input</span></span>

<span data-ttu-id="5132f-104">O PowerShell pode validar os argumentos passados para parâmetros de cmdlet de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="5132f-104">PowerShell can validate the arguments passed to cmdlet parameters in several ways.</span></span>
<span data-ttu-id="5132f-105">O PowerShell pode validar o comprimento, o intervalo e o padrão dos caracteres do argumento.</span><span class="sxs-lookup"><span data-stu-id="5132f-105">PowerShell can validate the length, the range, and the pattern of the characters of the argument.</span></span>
<span data-ttu-id="5132f-106">Ele pode validar o número de argumentos disponíveis (a contagem).</span><span class="sxs-lookup"><span data-stu-id="5132f-106">It can validate the number of arguments available (the count).</span></span>
<span data-ttu-id="5132f-107">Essas regras de validação são definidas por atributos de validação que são declarados com o atributo Parameter em propriedades públicas da classe cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5132f-107">These validation rules are defined by validation attributes that are declared with the Parameter attribute on public properties of the cmdlet class.</span></span>

<span data-ttu-id="5132f-108">Para validar um argumento de parâmetro, o tempo de execução do PowerShell usa as informações fornecidas pelos atributos de validação para confirmar o valor do parâmetro antes da execução do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5132f-108">To validate a parameter argument, the PowerShell runtime uses the information provided by the validation attributes to confirm the value of the parameter before the cmdlet is run.</span></span>
<span data-ttu-id="5132f-109">Se a entrada do parâmetro não for válida, o usuário receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="5132f-109">If the parameter input is not valid, the user receives an error message.</span></span>
<span data-ttu-id="5132f-110">Cada parâmetro de validação define uma regra de validação que é imposta pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5132f-110">Each validation parameter defines a validation rule that is enforced by PowerShell.</span></span>

<span data-ttu-id="5132f-111">O PowerShell impõe as regras de validação com base nos atributos a seguir.</span><span class="sxs-lookup"><span data-stu-id="5132f-111">PowerShell enforces the validation rules based on the following attributes.</span></span>

### <a name="validatecount"></a><span data-ttu-id="5132f-112">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="5132f-112">ValidateCount</span></span>

<span data-ttu-id="5132f-113">Especifica o número mínimo e máximo de argumentos que um parâmetro pode aceitar.</span><span class="sxs-lookup"><span data-stu-id="5132f-113">Specifies the minimum and maximum number of arguments that a parameter can accept.</span></span>
<span data-ttu-id="5132f-114">Para obter mais informações, consulte [declaração de atributo ValidateCount](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="5132f-114">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="5132f-115">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="5132f-115">ValidateLength</span></span>

<span data-ttu-id="5132f-116">Especifica o número mínimo e máximo de caracteres no argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5132f-116">Specifies the minimum and maximum number of characters in the parameter argument.</span></span>
<span data-ttu-id="5132f-117">Para obter mais informações, consulte [declaração de atributo ValidateLength](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="5132f-117">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="5132f-118">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="5132f-118">ValidatePattern</span></span>

<span data-ttu-id="5132f-119">Especifica uma expressão regular que valida o argumento do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5132f-119">Specifies a regular expression that validates the parameter argument.</span></span>
<span data-ttu-id="5132f-120">Para obter mais informações, consulte [declaração de atributo ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="5132f-120">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="5132f-121">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="5132f-121">ValidateRange</span></span>

<span data-ttu-id="5132f-122">Especifica os valores mínimo e máximo do argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5132f-122">Specifies the minimum and maximum values of the parameter argument.</span></span>
<span data-ttu-id="5132f-123">Para obter mais informações, consulte [declaração de atributo ValidateRange](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="5132f-123">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="5132f-124">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="5132f-124">ValidateSet</span></span>

<span data-ttu-id="5132f-125">Especifica os valores válidos para o argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5132f-125">Specifies the valid values for the parameter argument.</span></span>
<span data-ttu-id="5132f-126">Para obter mais informações, consulte [declaração de atributo ValidateSet](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="5132f-126">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5132f-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5132f-127">See Also</span></span>

[<span data-ttu-id="5132f-128">Como validar a entrada de parâmetro</span><span class="sxs-lookup"><span data-stu-id="5132f-128">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

<span data-ttu-id="5132f-129">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="5132f-129">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
