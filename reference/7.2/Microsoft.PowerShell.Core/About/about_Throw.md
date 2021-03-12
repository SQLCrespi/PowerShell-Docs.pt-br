---
description: Descreve a palavra-chave Throw, que gera um erro de terminação.
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_throw?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Throw
ms.openlocfilehash: bef005f47583523f69a8b25651eb0ee5bfc5b224
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195843"
---
# <a name="about-throw"></a><span data-ttu-id="c5d5a-103">Sobre o throw</span><span class="sxs-lookup"><span data-stu-id="c5d5a-103">About Throw</span></span>

## <a name="short-description"></a><span data-ttu-id="c5d5a-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="c5d5a-104">Short description</span></span>
<span data-ttu-id="c5d5a-105">Descreve a palavra-chave Throw, que gera um erro de terminação.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-105">Describes the Throw keyword, which generates a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="c5d5a-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="c5d5a-106">Long description</span></span>

<span data-ttu-id="c5d5a-107">A palavra-chave Throw causa um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-107">The Throw keyword causes a terminating error.</span></span> <span data-ttu-id="c5d5a-108">Você pode usar a palavra-chave Throw para interromper o processamento de um comando, uma função ou um script.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-108">You can use the Throw keyword to stop the processing of a command, function, or script.</span></span>

<span data-ttu-id="c5d5a-109">Por exemplo, você pode usar a palavra-chave Throw no bloco de script de uma instrução If para responder a uma condição ou no bloco catch de uma instrução try-catch-finally.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-109">For example, you can use the Throw keyword in the script block of an If statement to respond to a condition or in the Catch block of a Try-Catch-Finally statement.</span></span> <span data-ttu-id="c5d5a-110">Você também pode usar a palavra-chave Throw em uma declaração de parâmetro para tornar obrigatório um parâmetro de função.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-110">You can also use the Throw keyword in a parameter declaration to make a function parameter mandatory.</span></span>

<span data-ttu-id="c5d5a-111">A palavra-chave Throw pode gerar qualquer objeto, como uma cadeia de caracteres de mensagem de usuário ou o objeto que causou o erro.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-111">The Throw keyword can throw any object, such as a user message string or the object that caused the error.</span></span>

## <a name="syntax"></a><span data-ttu-id="c5d5a-112">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c5d5a-112">Syntax</span></span>

<span data-ttu-id="c5d5a-113">A sintaxe da palavra-chave Throw é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="c5d5a-113">The syntax of the Throw keyword is as follows:</span></span>

```powershell
throw [<expression>]
```

<span data-ttu-id="c5d5a-114">A expressão na sintaxe Throw é opcional.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-114">The expression in the Throw syntax is optional.</span></span> <span data-ttu-id="c5d5a-115">Quando a instrução Throw não aparece em um bloco catch e não inclui uma expressão, ela gera um erro ScriptHalted.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-115">When the Throw statement does not appear in a Catch block, and it does not include an expression, it generates a ScriptHalted error.</span></span>

```powershell
C:\PS> throw

Exception: ScriptHalted
```

<span data-ttu-id="c5d5a-116">Se a palavra-chave Throw for usada em um bloco catch sem uma expressão, ela lançará a RuntimeException atual novamente.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-116">If the Throw keyword is used in a Catch block without an expression, it throws the current RuntimeException again.</span></span> <span data-ttu-id="c5d5a-117">Para obter mais informações, consulte about_Try_Catch_Finally.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-117">For more information, see about_Try_Catch_Finally.</span></span>

## <a name="throwing-a-string"></a><span data-ttu-id="c5d5a-118">Lançando uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c5d5a-118">Throwing a string</span></span>

<span data-ttu-id="c5d5a-119">A expressão opcional em uma instrução Throw pode ser uma cadeia de caracteres, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="c5d5a-119">The optional expression in a Throw statement can be a string, as shown in the following example:</span></span>

```powershell
C:\PS> throw "This is an error."

Exception: This is an error.
```

## <a name="throwing-other-objects"></a><span data-ttu-id="c5d5a-120">Lançando outros objetos</span><span class="sxs-lookup"><span data-stu-id="c5d5a-120">Throwing other objects</span></span>

<span data-ttu-id="c5d5a-121">A expressão também pode ser um objeto que gera o objeto que representa o processo do PowerShell, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="c5d5a-121">The expression can also be an object that throws the object that represents the PowerShell process, as shown in the following example:</span></span>

```powershell
C:\PS> throw (get-process Pwsh)

Exception: System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh)
```

<span data-ttu-id="c5d5a-122">Você pode usar a propriedade TargetObject do objeto ErrorRecord no $error variável automática para examinar o erro.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-122">You can use the TargetObject property of the ErrorRecord object in the $error automatic variable to examine the error.</span></span>

```powershell
C:\PS> $error[0].targetobject

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    125   174.44     229.57      23.61    1548   2 pwsh
     63    44.07      81.95       1.75    1732   2 pwsh
     63    43.32      77.65       1.48    9092   2 pwsh
```

<span data-ttu-id="c5d5a-123">Você também pode lançar um objeto ErrorRecord ou uma exceção .NET.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-123">You can also throw an ErrorRecord object or a .NET exception.</span></span> <span data-ttu-id="c5d5a-124">O exemplo a seguir usa a palavra-chave Throw para lançar um objeto System. FormatException.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-124">The following example uses the Throw keyword to throw a System.FormatException object.</span></span>

```powershell
C:\PS> $formatError = new-object system.formatexception

C:\PS> throw $formatError

OperationStopped: One of the identified items was in an invalid format.
```

## <a name="the-resulting-error"></a><span data-ttu-id="c5d5a-125">O erro resultante</span><span class="sxs-lookup"><span data-stu-id="c5d5a-125">The resulting error</span></span>

<span data-ttu-id="c5d5a-126">A palavra-chave Throw pode gerar um objeto ErrorRecord.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-126">The Throw keyword can generate an ErrorRecord object.</span></span> <span data-ttu-id="c5d5a-127">A propriedade Exception do objeto ErrorRecord contém um objeto RuntimeException.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-127">The Exception property of the ErrorRecord object contains a RuntimeException object.</span></span> <span data-ttu-id="c5d5a-128">O restante do objeto ErrorRecord e o objeto RuntimeException variam com o objeto que a palavra-chave Throw gera.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-128">The remainder of the ErrorRecord object and the RuntimeException object vary with the object that the Throw keyword throws.</span></span>

<span data-ttu-id="c5d5a-129">O objeto RunTimeexception é encapsulado em um objeto ErrorRecord e o objeto ErrorRecord é salvo automaticamente no $Error variável automática.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-129">The RunTimeException object is wrapped in an ErrorRecord object, and the ErrorRecord object is automatically saved in the $Error automatic variable.</span></span>

## <a name="using-throw-to-create-a-mandatory-parameter"></a><span data-ttu-id="c5d5a-130">Usando throw para criar um parâmetro obrigatório</span><span class="sxs-lookup"><span data-stu-id="c5d5a-130">Using Throw to create a mandatory parameter</span></span>

<span data-ttu-id="c5d5a-131">Ao contrário das versões anteriores do PowerShell, não use a palavra-chave Throw para validação de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-131">Unlike past versions of PowerShell, do not use the Throw keyword for parameter validation.</span></span> <span data-ttu-id="c5d5a-132">Consulte [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md) da maneira correta.</span><span class="sxs-lookup"><span data-stu-id="c5d5a-132">See [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md) for the correct way.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5d5a-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="c5d5a-133">See also</span></span>

- [<span data-ttu-id="c5d5a-134">about_Break</span><span class="sxs-lookup"><span data-stu-id="c5d5a-134">about_Break</span></span>](about_Break.md)
- [<span data-ttu-id="c5d5a-135">about_Continue</span><span class="sxs-lookup"><span data-stu-id="c5d5a-135">about_Continue</span></span>](about_Continue.md)
- [<span data-ttu-id="c5d5a-136">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="c5d5a-136">about_Scopes</span></span>](about_Scopes.md)
- [<span data-ttu-id="c5d5a-137">about_Trap</span><span class="sxs-lookup"><span data-stu-id="c5d5a-137">about_Trap</span></span>](about_Trap.md)
- [<span data-ttu-id="c5d5a-138">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="c5d5a-138">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)
