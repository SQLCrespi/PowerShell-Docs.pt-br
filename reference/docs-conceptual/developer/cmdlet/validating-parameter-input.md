---
title: Validando entrada de parâmetro | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parameters, validation rules
- validation, examples
- validation
ms.assetid: 3f15bf20-a068-4a7d-a170-bc43f755d1fe
caps.latest.revision: 14
ms.openlocfilehash: 171e3e974619e197a0bcc9dfc759297005e34568
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363505"
---
# <a name="validating-parameter-input"></a><span data-ttu-id="b5355-102">Validação de entrada de parâmetro</span><span class="sxs-lookup"><span data-stu-id="b5355-102">Validating Parameter Input</span></span>

<span data-ttu-id="b5355-103">O PowerShell pode validar os argumentos passados para parâmetros de cmdlet de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="b5355-103">PowerShell can validate the arguments passed to cmdlet parameters in several ways.</span></span>
<span data-ttu-id="b5355-104">O PowerShell pode validar o comprimento, o intervalo e o padrão dos caracteres do argumento.</span><span class="sxs-lookup"><span data-stu-id="b5355-104">PowerShell can validate the length, the range, and the pattern of the characters of the argument.</span></span>
<span data-ttu-id="b5355-105">Ele pode validar o número de argumentos disponíveis (a contagem).</span><span class="sxs-lookup"><span data-stu-id="b5355-105">It can validate the number of arguments available (the count).</span></span>
<span data-ttu-id="b5355-106">Essas regras de validação são definidas por atributos de validação que são declarados com o atributo Parameter em propriedades públicas da classe cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b5355-106">These validation rules are defined by validation attributes that are declared with the Parameter attribute on public properties of the cmdlet class.</span></span>

<span data-ttu-id="b5355-107">Para validar um argumento de parâmetro, o tempo de execução do PowerShell usa as informações fornecidas pelos atributos de validação para confirmar o valor do parâmetro antes da execução do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b5355-107">To validate a parameter argument, the PowerShell runtime uses the information provided by the validation attributes to confirm the value of the parameter before the cmdlet is run.</span></span>
<span data-ttu-id="b5355-108">Se a entrada do parâmetro não for válida, o usuário receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="b5355-108">If the parameter input is not valid, the user receives an error message.</span></span>
<span data-ttu-id="b5355-109">Cada parâmetro de validação define uma regra de validação que é imposta pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5355-109">Each validation parameter defines a validation rule that is enforced by PowerShell.</span></span>

<span data-ttu-id="b5355-110">O PowerShell impõe as regras de validação com base nos atributos a seguir.</span><span class="sxs-lookup"><span data-stu-id="b5355-110">PowerShell enforces the validation rules based on the following attributes.</span></span>

### <a name="validatecount"></a><span data-ttu-id="b5355-111">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="b5355-111">ValidateCount</span></span>

<span data-ttu-id="b5355-112">Especifica o número mínimo e máximo de argumentos que um parâmetro pode aceitar.</span><span class="sxs-lookup"><span data-stu-id="b5355-112">Specifies the minimum and maximum number of arguments that a parameter can accept.</span></span>
<span data-ttu-id="b5355-113">Para obter mais informações, consulte [declaração de atributo ValidateCount](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="b5355-113">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="b5355-114">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="b5355-114">ValidateLength</span></span>

<span data-ttu-id="b5355-115">Especifica o número mínimo e máximo de caracteres no argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b5355-115">Specifies the minimum and maximum number of characters in the parameter argument.</span></span>
<span data-ttu-id="b5355-116">Para obter mais informações, consulte [declaração de atributo ValidateLength](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="b5355-116">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="b5355-117">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="b5355-117">ValidatePattern</span></span>

<span data-ttu-id="b5355-118">Especifica uma expressão regular que valida o argumento do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b5355-118">Specifies a regular expression that validates the parameter argument.</span></span>
<span data-ttu-id="b5355-119">Para obter mais informações, consulte [declaração de atributo ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="b5355-119">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="b5355-120">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="b5355-120">ValidateRange</span></span>

<span data-ttu-id="b5355-121">Especifica os valores mínimo e máximo do argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b5355-121">Specifies the minimum and maximum values of the parameter argument.</span></span>
<span data-ttu-id="b5355-122">Para obter mais informações, consulte [declaração de atributo ValidateRange](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="b5355-122">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="b5355-123">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="b5355-123">ValidateSet</span></span>

<span data-ttu-id="b5355-124">Especifica os valores válidos para o argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b5355-124">Specifies the valid values for the parameter argument.</span></span>
<span data-ttu-id="b5355-125">Para obter mais informações, consulte [declaração de atributo ValidateSet](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="b5355-125">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b5355-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b5355-126">See Also</span></span>

[<span data-ttu-id="b5355-127">Como validar a entrada de parâmetro</span><span class="sxs-lookup"><span data-stu-id="b5355-127">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

<span data-ttu-id="b5355-128">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="b5355-128">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
