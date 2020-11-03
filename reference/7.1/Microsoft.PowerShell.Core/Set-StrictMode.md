---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-strictmode?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StrictMode
ms.openlocfilehash: c68b8a7e106b9bac56199684a926f3dabe006e7b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194568"
---
# <span data-ttu-id="9c0e3-103">Set-StrictMode</span><span class="sxs-lookup"><span data-stu-id="9c0e3-103">Set-StrictMode</span></span>

## <span data-ttu-id="9c0e3-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9c0e3-104">SYNOPSIS</span></span>
<span data-ttu-id="9c0e3-105">Estabelece e impõe regras de codificação em expressões, scripts e blocos de script.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-105">Establishes and enforces coding rules in expressions, scripts, and script blocks.</span></span>

## <span data-ttu-id="9c0e3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9c0e3-106">SYNTAX</span></span>

### <span data-ttu-id="9c0e3-107">Versão (padrão)</span><span class="sxs-lookup"><span data-stu-id="9c0e3-107">Version (Default)</span></span>

```
Set-StrictMode -Version <Version> [<CommonParameters>]
```

### <span data-ttu-id="9c0e3-108">Desativado</span><span class="sxs-lookup"><span data-stu-id="9c0e3-108">Off</span></span>

```
Set-StrictMode [-Off] [<CommonParameters>]
```

## <span data-ttu-id="9c0e3-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c0e3-109">DESCRIPTION</span></span>

<span data-ttu-id="9c0e3-110">O `Set-StrictMode` cmdlet configura o modo estrito para o escopo atual e todos os escopos filho e ativa e desativa.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-110">The `Set-StrictMode` cmdlet configures strict mode for the current scope and all child scopes, and turns it on and off.</span></span> <span data-ttu-id="9c0e3-111">Quando o modo estrito está ativado, o PowerShell gera um erro de encerramento quando o conteúdo de uma expressão, script ou bloco de script viola as regras básicas de codificação de práticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-111">When strict mode is on, PowerShell generates a terminating error when the content of an expression, script, or script block violates basic best-practice coding rules.</span></span>

<span data-ttu-id="9c0e3-112">Use o parâmetro **version** para determinar quais regras de codificação são impostas.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-112">Use the **Version** parameter to determine which coding rules are enforced.</span></span>

<span data-ttu-id="9c0e3-113">`Set-PSDebug -Strict` o cmdlet ativa o modo estrito para o escopo global.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-113">`Set-PSDebug -Strict` cmdlet turns on strict mode for the global scope.</span></span> <span data-ttu-id="9c0e3-114">`Set-StrictMode` afeta apenas o escopo atual e seus escopos filho.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-114">`Set-StrictMode` affects only the current scope and its child scopes.</span></span> <span data-ttu-id="9c0e3-115">Portanto, você pode usá-lo em um script ou função para substituir a configuração herdada do escopo global.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-115">Therefore, you can use it in a script or function to override the setting inherited from the global scope.</span></span>

<span data-ttu-id="9c0e3-116">Quando `Set-StrictMode` está desativado, o PowerShell tem os seguintes comportamentos:</span><span class="sxs-lookup"><span data-stu-id="9c0e3-116">When `Set-StrictMode` is off, PowerShell has the following behaviors:</span></span>

- <span data-ttu-id="9c0e3-117">Presumidas variáveis não inicializadas devem ter um valor de 0 (zero) ou `$Null` , dependendo do tipo</span><span class="sxs-lookup"><span data-stu-id="9c0e3-117">Uninitialized variables are assumed to have a value of 0 (zero) or `$Null`, depending on type</span></span>
- <span data-ttu-id="9c0e3-118">Referências a propriedades não existentes retornam `$Null`</span><span class="sxs-lookup"><span data-stu-id="9c0e3-118">References to non-existent properties return `$Null`</span></span>
- <span data-ttu-id="9c0e3-119">Os resultados da sintaxe de função incorreta variam de acordo com as condições de erro</span><span class="sxs-lookup"><span data-stu-id="9c0e3-119">Results of improper function syntax vary with the error conditions</span></span>
- <span data-ttu-id="9c0e3-120">A tentativa de recuperar um valor usando um índice inválido em uma matriz retorna `$Null`</span><span class="sxs-lookup"><span data-stu-id="9c0e3-120">Attempting to retrieve a value using an invalid index in an array returns `$Null`</span></span>

## <span data-ttu-id="9c0e3-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9c0e3-121">EXAMPLES</span></span>

### <span data-ttu-id="9c0e3-122">Exemplo 1: ativar o modo estrito como a versão 1,0</span><span class="sxs-lookup"><span data-stu-id="9c0e3-122">Example 1: Turn on strict mode as version 1.0</span></span>

```powershell
# Strict mode is off by default.
$a -gt 5
```

```Output
False
```

```powershell
Set-StrictMode -Version 1.0
$a -gt 5
```

```Output
The variable $a cannot be retrieved because it has not been set yet.

At line:1 char:3
+ $a <<<<  -gt 5
+ CategoryInfo          : InvalidOperation: (a:Token) [], RuntimeException
+ FullyQualifiedErrorId : VariableIsUndefined
```

<span data-ttu-id="9c0e3-123">Com o modo estrito definido como a versão 1,0, as tentativas de fazer referência a variáveis que não são inicializadas falham.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-123">With strict mode set to version 1.0, attempts to reference variables that are not initialized fail.</span></span>

### <span data-ttu-id="9c0e3-124">Exemplo 2: ativar o modo estrito como a versão 2,0</span><span class="sxs-lookup"><span data-stu-id="9c0e3-124">Example 2: Turn on strict mode as version 2.0</span></span>

```powershell
# Strict mode is off by default.
function add ($a, $b) {
    '$a = ' + $a
    '$b = ' + $b
    '$a+$b = ' + ($a + $b)
}
add 3 4
```

```Output
$a = 3
$b = 4
$a+$b = 7
```

```powershell
add(3,4)
```

```Output
$a = 3 4
$b =
$a+$b = 3 4
```

```powershell
Set-StrictMode -Version 2.0
add(3,4)
```

```Output
The function or command was called like a method. Parameters should be separated by spaces,
as described in 'Get-Help about_Parameter.'
At line:1 char:4
+ add <<<< (3,4)
+ CategoryInfo          : InvalidOperation: (:) [], RuntimeException
+ FullyQualifiedErrorId : StrictModeFunctionCallWithParens
```

```powershell
Set-StrictMode -Off
$string = "This is a string."
$string.Month -eq $null
```

```Output
True
```

```powershell
Set-StrictMode -Version 2.0
$string = "This is a string."
$string.Month -eq $null
```

```Output
Property 'Month' cannot be found on this object; make sure it exists.
At line:1 char:9
+ $string. <<<< month
+ CategoryInfo          : InvalidOperation: (.:OperatorToken) [], RuntimeException
+ FullyQualifiedErrorId : PropertyNotFoundStrict
```

<span data-ttu-id="9c0e3-125">Esse comando ativa o modo estrito e o define para a versão 2,0.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-125">This command turns strict mode on and sets it to version 2.0.</span></span> <span data-ttu-id="9c0e3-126">Como resultado, o PowerShell retornará um erro se você usar a sintaxe do método, que usa parênteses e vírgulas, para uma chamada de função ou para referenciar variáveis não inicializadas ou Propriedades inexistentes.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-126">As a result, PowerShell returns an error if you use method syntax, which uses parentheses and commas, for a function call or reference uninitialized variables or non-existent properties.</span></span>

<span data-ttu-id="9c0e3-127">A saída de exemplo mostra o efeito do modo estrito da versão 2,0.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-127">The sample output shows the effect of version 2.0 strict mode.</span></span>

<span data-ttu-id="9c0e3-128">Sem o modo estrito versão 2.0, o valor "(3,4)" é interpretado como um único objeto de matriz ao qual nada é adicionado.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-128">Without version 2.0 strict mode, the "(3,4)" value is interpreted as a single array object to which nothing is added.</span></span> <span data-ttu-id="9c0e3-129">Usando o modo estrito da versão 2,0, ele é corretamente interpretado como sintaxe com falha para enviar dois valores.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-129">By using version 2.0 strict mode, it is correctly interpreted as faulty syntax for submitting two values.</span></span>

<span data-ttu-id="9c0e3-130">Sem a versão 2,0, a referência à propriedade **month** não existente de uma cadeia de caracteres retorna apenas `$Null` .</span><span class="sxs-lookup"><span data-stu-id="9c0e3-130">Without version 2.0, the reference to the non-existent **Month** property of a string returns only `$Null`.</span></span> <span data-ttu-id="9c0e3-131">Usando a versão 2,0, ela é interpretada corretamente como um erro de referência.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-131">By using version 2.0, it is interpreted correctly as a reference error.</span></span>

### <span data-ttu-id="9c0e3-132">Exemplo 3: ativar o modo estrito como a versão 3,0</span><span class="sxs-lookup"><span data-stu-id="9c0e3-132">Example 3: Turn on strict mode as version 3.0</span></span>

<span data-ttu-id="9c0e3-133">Com o modo estrito definido como **desativado** , índices inválidos ou fora dos limites resultam em valores nulos de retorno de resultados.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-133">With strict mode set to **Off** , invalid or out of bounds indexes result return null values.</span></span>

```powershell
# Strict mode is off by default.
$a = @(1)
$a[2] -eq $null
$a['abc'] -eq $null
```

```Output
True
True
```

```powershell
Set-StrictMode -Version 3
$a = @(1)
$a[2] -eq $null
$a['abc'] -eq $null
```

```Output
Index was outside the bounds of the array.
At line:1 char:1
+ $a[2] -eq $null
+ ~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (:) [], IndexOutOfRangeException
    + FullyQualifiedErrorId : System.IndexOutOfRangeException

Cannot convert value "abc" to type "System.Int32". Error: "Input string was not in a correct format."
At line:1 char:1
+ $a['abc'] -eq $null
+ ~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [], RuntimeException
    + FullyQualifiedErrorId : InvalidCastFromStringToInteger
```

<span data-ttu-id="9c0e3-134">Com o modo estrito definido para a versão 3 ou superior, índices inválidos ou fora dos limites resultam em erros.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-134">With strict mode set to version 3 or higher, invalid or out of bounds indexes result in errors.</span></span>

## <span data-ttu-id="9c0e3-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9c0e3-135">PARAMETERS</span></span>

### <span data-ttu-id="9c0e3-136">-Desativado</span><span class="sxs-lookup"><span data-stu-id="9c0e3-136">-Off</span></span>

<span data-ttu-id="9c0e3-137">Indica que esse cmdlet desativa o modo estrito para o escopo atual e todos os escopos filho.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-137">Indicates that this cmdlet turns strict mode off for the current scope and all child scopes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Off
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c0e3-138">-Version</span><span class="sxs-lookup"><span data-stu-id="9c0e3-138">-Version</span></span>

<span data-ttu-id="9c0e3-139">Especifica as condições que causam um erro no modo estrito.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-139">Specifies the conditions that cause an error in strict mode.</span></span> <span data-ttu-id="9c0e3-140">Esse parâmetro aceita qualquer número de versão válido do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-140">This parameter accepts any valid PowerShell version number.</span></span> <span data-ttu-id="9c0e3-141">Qualquer número maior que 3 é tratado como o **mais recente** .</span><span class="sxs-lookup"><span data-stu-id="9c0e3-141">Any number higher than 3 is treated as **Latest** .</span></span>

<span data-ttu-id="9c0e3-142">Os valores efetivos para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="9c0e3-142">The effective values for this parameter are:</span></span>

- <span data-ttu-id="9c0e3-143">1.0</span><span class="sxs-lookup"><span data-stu-id="9c0e3-143">1.0</span></span>
  - <span data-ttu-id="9c0e3-144">Proíbe referências a variáveis não inicializadas, exceto para variáveis não inicializadas em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-144">Prohibits references to uninitialized variables, except for uninitialized variables in strings.</span></span>
- <span data-ttu-id="9c0e3-145">2.0</span><span class="sxs-lookup"><span data-stu-id="9c0e3-145">2.0</span></span>
  - <span data-ttu-id="9c0e3-146">Proíbe referências a variáveis não inicializadas.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-146">Prohibits references to uninitialized variables.</span></span> <span data-ttu-id="9c0e3-147">Isso inclui variáveis não inicializadas em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-147">This includes uninitialized variables in strings.</span></span>
  - <span data-ttu-id="9c0e3-148">Proíbe referências a propriedades não existentes de um objeto.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-148">Prohibits references to non-existent properties of an object.</span></span>
  - <span data-ttu-id="9c0e3-149">Proíbe chamadas de função que usam a sintaxe para chamar métodos.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-149">Prohibits function calls that use the syntax for calling methods.</span></span>
- <span data-ttu-id="9c0e3-150">3.0</span><span class="sxs-lookup"><span data-stu-id="9c0e3-150">3.0</span></span>
  - <span data-ttu-id="9c0e3-151">Proíbe referências a variáveis não inicializadas.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-151">Prohibits references to uninitialized variables.</span></span> <span data-ttu-id="9c0e3-152">Isso inclui variáveis não inicializadas em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-152">This includes uninitialized variables in strings.</span></span>
  - <span data-ttu-id="9c0e3-153">Proíbe referências a propriedades não existentes de um objeto.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-153">Prohibits references to non-existent properties of an object.</span></span>
  - <span data-ttu-id="9c0e3-154">Proíbe chamadas de função que usam a sintaxe para chamar métodos.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-154">Prohibits function calls that use the syntax for calling methods.</span></span>
  - <span data-ttu-id="9c0e3-155">Proibir fora dos limites ou índices de matriz não resolvidos.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-155">Prohibit out of bounds or unresolvable array indexes.</span></span>
- <span data-ttu-id="9c0e3-156">Última</span><span class="sxs-lookup"><span data-stu-id="9c0e3-156">Latest</span></span>
  - <span data-ttu-id="9c0e3-157">Seleciona a versão mais recente disponível.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-157">Selects the latest version available.</span></span> <span data-ttu-id="9c0e3-158">A versão mais recente é a mais estrita.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-158">The latest version is the most strict.</span></span> <span data-ttu-id="9c0e3-159">Use esse valor para garantir que os scripts usem a versão mais estrita disponível, mesmo quando novas versões forem adicionadas ao PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-159">Use this value to make sure that scripts use the strictest available version, even when new versions are added to PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="9c0e3-160">Usando uma **versão** do **mais recente** em scripts.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-160">Using a **Version** of **Latest** in scripts.</span></span> <span data-ttu-id="9c0e3-161">O significado da **mais recente** pode mudar em novas versões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-161">The meaning of **Latest** can change in new releases of PowerShell.</span></span> <span data-ttu-id="9c0e3-162">Portanto, um script escrito para uma versão mais antiga do PowerShell que o usa `Set-StrictMode -Version Latest` está sujeito a regras mais restritivas quando executado em uma versão mais recente do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-162">Therefore, a script written for an older version of PowerShell that uses `Set-StrictMode -Version Latest` is subject to more restrictive rules when run in a newer version of PowerShell.</span></span>

```yaml
Type: System.Version
Parameter Sets: Version
Aliases: v

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c0e3-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9c0e3-163">CommonParameters</span></span>

<span data-ttu-id="9c0e3-164">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9c0e3-165">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9c0e3-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9c0e3-166">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9c0e3-166">INPUTS</span></span>

### <span data-ttu-id="9c0e3-167">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9c0e3-167">None</span></span>

<span data-ttu-id="9c0e3-168">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-168">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="9c0e3-169">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9c0e3-169">OUTPUTS</span></span>

### <span data-ttu-id="9c0e3-170">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9c0e3-170">None</span></span>

<span data-ttu-id="9c0e3-171">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-171">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="9c0e3-172">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9c0e3-172">NOTES</span></span>

<span data-ttu-id="9c0e3-173">`Set-StrictMode` entra em vigor somente no escopo no qual ele está definido e em seus escopos filho.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-173">`Set-StrictMode` is effective only in the scope in which it is set and in its child scopes.</span></span> <span data-ttu-id="9c0e3-174">Para obter mais informações sobre escopos no PowerShell, consulte [about_Scopes](about/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="9c0e3-174">For more information about scopes in PowerShell, see [about_Scopes](about/about_Scopes.md).</span></span>

## <span data-ttu-id="9c0e3-175">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9c0e3-175">RELATED LINKS</span></span>

[<span data-ttu-id="9c0e3-176">Set-PSDebug</span><span class="sxs-lookup"><span data-stu-id="9c0e3-176">Set-PSDebug</span></span>](Set-PSDebug.md)

