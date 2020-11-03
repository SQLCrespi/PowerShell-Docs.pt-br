---
description: Descreve os operadores que conectam instruções no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logical_operators?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logical_Operators
ms.openlocfilehash: 483217e929d55097b56eade801682ea4484d2624
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196500"
---
# <a name="about_logical_operators"></a>about_Logical_Operators

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve os operadores que conectam instruções no PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Os operadores lógicos do PowerShell conectam expressões e instruções, permitindo que você use uma única expressão para testar várias condições.

Por exemplo, a instrução a seguir usa o operador and e o operador OR para conectar três instruções condicionais. A instrução é verdadeira somente quando o valor de $a é maior que o valor de $b e $a ou $b é menor que
20.

```powershell
($a -gt $b) -and (($a -lt 20) -or ($b -lt 20))
```

O PowerShell dá suporte aos seguintes operadores lógicos.

|Operador|Descrição                        |Exemplo                   |
|--------|-----------------------------------|--------------------------|
|`-and`  |AND Lógico. VERDADEIRO quando ambos        |`(1 -eq 1) -and (1 -eq 2)`|
|        |as instruções são verdadeiras.               |`False`                   |
|`-or`   |OR Lógico. VERDADEIRO quando o       |`(1 -eq 1) -or (1 -eq 2)` |
|        |a instrução é verdadeira.                 |`True`                    |
|`-xor`  |Lógico exclusivo ou. VERDADEIRO quando    |`(1 -eq 1) -xor (2 -eq 2)`|
|        |apenas uma instrução é verdadeira         |`False`                   |
|`-not`  |Não lógico. Nega a instrução |`-not (1 -eq 1)`          |
|        |a seguir.                      |`False`                   |
|`!`     |Mesmo que `-not`                     |`!(1 -eq 1)`              |
|        |                                   |`False`                   |

 Observação:

Os exemplos anteriores também usam o operador de comparação igual a `-eq` . Para obter mais informações, consulte [about_Comparison_Operators](about_Comparison_Operators.md). Os exemplos também usam os valores Boolianos de inteiros. O inteiro 0 tem um valor de FALSE. Todos os outros inteiros têm um valor de TRUE.

A sintaxe dos operadores lógicos é a seguinte:

```
<statement> {-AND | -OR | -XOR} <statement>
{! | -NOT} <statement>
```

As instruções que usam os operadores lógicos retornam valores Boolianos (TRUE ou FALSE).

Os operadores lógicos do PowerShell avaliam apenas as instruções necessárias para determinar o valor da verdade da instrução. Se o operando esquerdo em uma instrução que contém o operador and for FALSE, o operando direito não será avaliado.
Se o operando esquerdo em uma instrução que contém a instrução ou for TRUE, o operando direito não será avaliado. Como resultado, você pode usar essas instruções da mesma maneira que usaria a `If` instrução.

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Operators](about_Operators.md)

[Compare-Object](xref:Microsoft.PowerShell.Utility.Compare-Object)

[about_Comparison_operators](about_Comparison_Operators.md)

[about_If](about_If.md)
