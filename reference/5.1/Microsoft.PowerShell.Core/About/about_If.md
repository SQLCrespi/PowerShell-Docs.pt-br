---
description: Descreve um comando de linguagem que você pode usar para executar listas de instruções com base nos resultados de um ou mais testes condicionais.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_If
ms.openlocfilehash: 8b1be96167dab47e7e15e3e5b89c46126f117541
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196196"
---
# <a name="about-if"></a>Sobre se

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve um comando de linguagem que você pode usar para executar listas de instruções com base nos resultados de um ou mais testes condicionais.

## <a name="long-description"></a>DESCRIÇÃO LONGA
Você pode usar a `If` instrução para executar blocos de código se um teste condicional especificado for avaliado como true. Você também pode especificar um ou mais testes condicionais adicionais a serem executados se todos os testes anteriores forem avaliados como false. Por fim, você pode especificar um bloco de código adicional que será executado se nenhum outro teste condicional anterior for avaliado como verdadeiro.

### <a name="syntax"></a>Syntax

O exemplo a seguir mostra a `If` sintaxe da instrução:

```powershell
if (<test1>)
    {<statement list 1>}
[elseif (<test2>)
    {<statement list 2>}]
[else
    {<statement list 3>}]
```

Quando você executa uma `If` instrução, o PowerShell avalia a `<test1>` expressão condicional como true ou false. Se `<test1>` é verdadeiro, `<statement list 1>` é executado e o PowerShell sai da `If` instrução. Se `<test1>` for false, o PowerShell avaliará a condição especificada pela `<test2>` instrução condicional.

Se `<test2>` é verdadeiro, `<statement list 2>` é executado e o PowerShell sai da `If` instrução. Se `<test1>` e `<test2>` for avaliado como false, o `<statement list 3` bloco de código> será executado e o PowerShell sairá da instrução If.

Você pode usar várias instruções Elseif para encadear uma série de testes condicionais. Portanto, cada teste será executado somente se todos os testes anteriores forem falsos.
Se você precisar criar uma `If` instrução que contém muitas instruções ElseIf, considere usar uma instrução switch em vez disso.

Exemplos:

A instrução mais simples `If` contém um único comando e não contém nenhuma instrução ElseIf ou nenhuma instrução else. O exemplo a seguir mostra a forma mais simples da `If` instrução:

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
```

Neste exemplo, se a variável $a for maior que 2, a condição será avaliada como true e a lista de instruções será executada. No entanto, se $a for menor ou igual a 2 ou não for uma variável existente, a `If` instrução não exibirá uma mensagem.

Ao adicionar uma instrução else, uma mensagem é exibida quando $a é menor ou igual a 2. Como mostra o exemplo a seguir:

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
else {
    Write-Host ("The value $a is less than or equal to 2," +
        " is not created or is not initialized.")
}
```

Para refinar ainda mais este exemplo, você pode usar a instrução Elseif para exibir uma mensagem quando o valor de $a for igual a 2. Como mostra o exemplo a seguir:

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
elseif ($a -eq 2) {
    Write-Host "The value $a is equal to 2."
}
else {
    Write-Host ("The value $a is less than 2 or" +
        " was not created or initialized.")
}
```

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Switch](about_Switch.md)
