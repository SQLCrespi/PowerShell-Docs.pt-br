---
description: Descreve a palavra-chave Throw, que gera um erro de terminação.
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_throw?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Throw
ms.openlocfilehash: e573722154fff99363b26806064ec17c8903bfd8
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103194169"
---
# <a name="about-throw"></a><span data-ttu-id="a5a18-103">Sobre o throw</span><span class="sxs-lookup"><span data-stu-id="a5a18-103">About Throw</span></span>

## <a name="short-description"></a><span data-ttu-id="a5a18-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="a5a18-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="a5a18-105">Descreve a palavra-chave Throw, que gera um erro de terminação.</span><span class="sxs-lookup"><span data-stu-id="a5a18-105">Describes the Throw keyword, which generates a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="a5a18-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="a5a18-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="a5a18-107">A palavra-chave Throw causa um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="a5a18-107">The Throw keyword causes a terminating error.</span></span> <span data-ttu-id="a5a18-108">Você pode usar a palavra-chave Throw para interromper o processamento de um comando, uma função ou um script.</span><span class="sxs-lookup"><span data-stu-id="a5a18-108">You can use the Throw keyword to stop the processing of a command, function, or script.</span></span>

<span data-ttu-id="a5a18-109">Por exemplo, você pode usar a palavra-chave Throw no bloco de script de uma instrução If para responder a uma condição ou no bloco catch de uma instrução try-catch-finally.</span><span class="sxs-lookup"><span data-stu-id="a5a18-109">For example, you can use the Throw keyword in the script block of an If statement to respond to a condition or in the Catch block of a Try-Catch-Finally statement.</span></span> <span data-ttu-id="a5a18-110">Você também pode usar a palavra-chave Throw em uma declaração de parâmetro para tornar obrigatório um parâmetro de função.</span><span class="sxs-lookup"><span data-stu-id="a5a18-110">You can also use the Throw keyword in a parameter declaration to make a function parameter mandatory.</span></span>

<span data-ttu-id="a5a18-111">A palavra-chave Throw pode gerar qualquer objeto, como uma cadeia de caracteres de mensagem de usuário ou o objeto que causou o erro.</span><span class="sxs-lookup"><span data-stu-id="a5a18-111">The Throw keyword can throw any object, such as a user message string or the object that caused the error.</span></span>

## <a name="syntax"></a><span data-ttu-id="a5a18-112">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a5a18-112">SYNTAX</span></span>

<span data-ttu-id="a5a18-113">A sintaxe da palavra-chave Throw é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="a5a18-113">The syntax of the Throw keyword is as follows:</span></span>

```powershell
throw [<expression>]
```

<span data-ttu-id="a5a18-114">A expressão na sintaxe Throw é opcional.</span><span class="sxs-lookup"><span data-stu-id="a5a18-114">The expression in the Throw syntax is optional.</span></span> <span data-ttu-id="a5a18-115">Quando a instrução Throw não aparece em um bloco catch e não inclui uma expressão, ela gera um erro ScriptHalted.</span><span class="sxs-lookup"><span data-stu-id="a5a18-115">When the Throw statement does not appear in a Catch block, and it does not include an expression, it generates a ScriptHalted error.</span></span>

```powershell
C:\PS> throw

ScriptHalted
At line:1 char:6
+ throw <<<<
+ CategoryInfo          : OperationStopped: (:) [], RuntimeException
+ FullyQualifiedErrorId : ScriptHalted
```

<span data-ttu-id="a5a18-116">Se a palavra-chave Throw for usada em um bloco catch sem uma expressão, ela lançará a RuntimeException atual novamente.</span><span class="sxs-lookup"><span data-stu-id="a5a18-116">If the Throw keyword is used in a Catch block without an expression, it throws the current RuntimeException again.</span></span> <span data-ttu-id="a5a18-117">Para obter mais informações, consulte about_Try_Catch_Finally.</span><span class="sxs-lookup"><span data-stu-id="a5a18-117">For more information, see about_Try_Catch_Finally.</span></span>

## <a name="throwing-a-string"></a><span data-ttu-id="a5a18-118">LANÇANDO UMA CADEIA DE CARACTERES</span><span class="sxs-lookup"><span data-stu-id="a5a18-118">THROWING A STRING</span></span>

<span data-ttu-id="a5a18-119">A expressão opcional em uma instrução Throw pode ser uma cadeia de caracteres, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="a5a18-119">The optional expression in a Throw statement can be a string, as shown in the following example:</span></span>

```powershell
C:\PS> throw "This is an error."

This is an error.
At line:1 char:6
+ throw <<<<  "This is an error."
+ CategoryInfo          : OperationStopped: (This is an error.:String) [], R
untimeException
+ FullyQualifiedErrorId : This is an error.
```

## <a name="throwing-other-objects"></a><span data-ttu-id="a5a18-120">LANÇANDO OUTROS OBJETOS</span><span class="sxs-lookup"><span data-stu-id="a5a18-120">THROWING OTHER OBJECTS</span></span>

<span data-ttu-id="a5a18-121">A expressão também pode ser um objeto que gera o objeto que representa o processo do PowerShell, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="a5a18-121">The expression can also be an object that throws the object that represents the PowerShell process, as shown in the following example:</span></span>

```powershell
C:\PS> throw (get-process PowerShell)

System.Diagnostics.Process (PowerShell)
At line:1 char:6
+ throw <<<<  (get-process PowerShell)
+ CategoryInfo          : OperationStopped: (System.Diagnostics.Process (Pow
erShell):Process) [],
RuntimeException
+ FullyQualifiedErrorId : System.Diagnostics.Process (PowerShell)
```

<span data-ttu-id="a5a18-122">Você pode usar a propriedade TargetObject do objeto ErrorRecord no $error variável automática para examinar o erro.</span><span class="sxs-lookup"><span data-stu-id="a5a18-122">You can use the TargetObject property of the ErrorRecord object in the $error automatic variable to examine the error.</span></span>

```powershell
C:\PS> $error[0].targetobject

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
319      26    61016      70864   568     3.28   5548 PowerShell
```

<span data-ttu-id="a5a18-123">Você também pode lançar um objeto ErrorRecord ou uma exceção de estrutura de Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="a5a18-123">You can also throw an ErrorRecord object or a Microsoft .NET Framework exception.</span></span> <span data-ttu-id="a5a18-124">O exemplo a seguir usa a palavra-chave Throw para lançar um objeto System. FormatException.</span><span class="sxs-lookup"><span data-stu-id="a5a18-124">The following example uses the Throw keyword to throw a System.FormatException object.</span></span>

```powershell
C:\PS> $formatError = new-object system.formatexception

C:\PS> throw $formatError

One of the identified items was in an invalid format.
At line:1 char:6
+ throw <<<<  $formatError
+ CategoryInfo          : OperationStopped: (:) [], FormatException
+ FullyQualifiedErrorId : One of the identified items was in an invalid
format.
```

## <a name="resulting-error"></a><span data-ttu-id="a5a18-125">ERRO RESULTANTE</span><span class="sxs-lookup"><span data-stu-id="a5a18-125">RESULTING ERROR</span></span>

<span data-ttu-id="a5a18-126">A palavra-chave Throw pode gerar um objeto ErrorRecord.</span><span class="sxs-lookup"><span data-stu-id="a5a18-126">The Throw keyword can generate an ErrorRecord object.</span></span> <span data-ttu-id="a5a18-127">A propriedade Exception do objeto ErrorRecord contém um objeto RuntimeException.</span><span class="sxs-lookup"><span data-stu-id="a5a18-127">The Exception property of the ErrorRecord object contains a RuntimeException object.</span></span> <span data-ttu-id="a5a18-128">O restante do objeto ErrorRecord e o objeto RuntimeException variam com o objeto que a palavra-chave Throw gera.</span><span class="sxs-lookup"><span data-stu-id="a5a18-128">The remainder of the ErrorRecord object and the RuntimeException object vary with the object that the Throw keyword throws.</span></span>

<span data-ttu-id="a5a18-129">O objeto RunTimeexception é encapsulado em um objeto ErrorRecord e o objeto ErrorRecord é salvo automaticamente no $Error variável automática.</span><span class="sxs-lookup"><span data-stu-id="a5a18-129">The RunTimeException object is wrapped in an ErrorRecord object, and the ErrorRecord object is automatically saved in the $Error automatic variable.</span></span>

## <a name="using-throw-to-create-a-mandatory-parameter"></a><span data-ttu-id="a5a18-130">USANDO THROW PARA CRIAR UM PARÂMETRO OBRIGATÓRIO</span><span class="sxs-lookup"><span data-stu-id="a5a18-130">USING THROW TO CREATE A MANDATORY PARAMETER</span></span>

<span data-ttu-id="a5a18-131">Você pode usar a palavra-chave Throw para tornar obrigatório um parâmetro de função.</span><span class="sxs-lookup"><span data-stu-id="a5a18-131">You can use the Throw keyword to make a function parameter mandatory.</span></span>

<span data-ttu-id="a5a18-132">Essa é uma alternativa ao uso do parâmetro obrigatório da palavra-chave Parameter.</span><span class="sxs-lookup"><span data-stu-id="a5a18-132">This is an alternative to using the Mandatory parameter of the Parameter keyword.</span></span> <span data-ttu-id="a5a18-133">Quando você usa o parâmetro obrigatório, o sistema solicita ao usuário o valor de parâmetro necessário.</span><span class="sxs-lookup"><span data-stu-id="a5a18-133">When you use the Mandatory parameter, the system prompts the user for the required parameter value.</span></span> <span data-ttu-id="a5a18-134">Quando você usa a palavra-chave Throw, o comando para e exibe o registro de erro.</span><span class="sxs-lookup"><span data-stu-id="a5a18-134">When you use the Throw keyword, the command stops and displays the error record.</span></span>

<span data-ttu-id="a5a18-135">Por exemplo, a palavra-chave Throw na subexpressão de parâmetro torna o parâmetro Path um parâmetro necessário na função.</span><span class="sxs-lookup"><span data-stu-id="a5a18-135">For example, the Throw keyword in the parameter subexpression makes the Path parameter a required parameter in the function.</span></span>

<span data-ttu-id="a5a18-136">Nesse caso, a palavra-chave Throw gera uma cadeia de caracteres de mensagem, mas é a presença da palavra-chave Throw que gera o erro de encerramento se o parâmetro Path não for especificado.</span><span class="sxs-lookup"><span data-stu-id="a5a18-136">In this case, the Throw keyword throws a message string, but it is the presence of the Throw keyword that generates the terminating error if the Path parameter is not specified.</span></span> <span data-ttu-id="a5a18-137">A expressão a seguir Throw é opcional.</span><span class="sxs-lookup"><span data-stu-id="a5a18-137">The expression that follows Throw is optional.</span></span>

```powershell
function Get-XMLFiles
{
  param ($path = $(throw "The Path parameter is required."))
  dir -path $path\*.xml -recurse |
    sort lastwritetime |
      ft lastwritetime, attributes, name  -auto
}
```

## <a name="see-also"></a><span data-ttu-id="a5a18-138">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="a5a18-138">SEE ALSO</span></span>

[<span data-ttu-id="a5a18-139">about_Break</span><span class="sxs-lookup"><span data-stu-id="a5a18-139">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="a5a18-140">about_Continue</span><span class="sxs-lookup"><span data-stu-id="a5a18-140">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="a5a18-141">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="a5a18-141">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="a5a18-142">about_Trap</span><span class="sxs-lookup"><span data-stu-id="a5a18-142">about_Trap</span></span>](about_Trap.md)

[<span data-ttu-id="a5a18-143">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="a5a18-143">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)
