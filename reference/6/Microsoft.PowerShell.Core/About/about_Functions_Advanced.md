---
description: Apresenta funções avançadas que são uma maneira de criar cmdlets usando scripts.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced
ms.openlocfilehash: f7e100122169b3ecb25be4d32fc72a67fea7b7cf
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195736"
---
# <a name="about-functions-advanced"></a>Sobre as funções avançadas

## <a name="short-description"></a>DESCRIÇÃO BREVE
Apresenta funções avançadas que são uma maneira de criar cmdlets usando scripts.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Um cmdlet é um único comando que participa da semântica do pipeline do PowerShell. Isso inclui cmdlets binários, funções de script avançadas, CDXML e fluxos de trabalho.

As funções avançadas permitem criar cmdlets que são gravados como uma função do PowerShell. As funções avançadas facilitam a criação de cmdlets sem a necessidade de escrever e compilar um cmdlet binário. Os cmdlets binários são classes .NET que são escritas em uma linguagem .NET, como C#.

As funções avançadas usam o `CmdletBinding` atributo para identificá-las como funções que atuam como cmdlets. O `CmdletBinding` atributo é semelhante ao atributo cmdlet usado em classes de cmdlet compiladas para identificar a classe como um cmdlet. Para obter mais informações sobre esse atributo, consulte [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).

O exemplo a seguir mostra uma função que aceita um nome e, em seguida, imprime uma saudação usando o nome fornecido. Observe também que essa função define um nome que inclui um par de verbo (envio) e substantivo (saudação) como o par verbo-substantivo de um cmdlet compilado. No entanto, não é necessário que as funções tenham um nome de verbo-substantivo.

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

Os parâmetros da função são declarados usando o atributo Parameter.
Esse atributo pode ser usado sozinha ou pode ser combinado com o atributo alias ou com vários outros atributos de validação de parâmetro. Para obter mais informações sobre como declarar parâmetros (incluindo parâmetros dinâmicos que são adicionados em tempo de execução), consulte [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).

O trabalho real da função anterior é executado no bloco Process, que é equivalente ao método ProcessingRecord que é usado por cmdlets compilados para processar os dados que são passados para o cmdlet. Esse bloco, juntamente com os blocos Begin e end, é descrito no tópico [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) .

As funções avançadas diferem dos cmdlets compilados das seguintes maneiras:

- A associação de parâmetro de função avançada não gera uma exceção quando uma matriz de cadeias de caracteres está associada a um parâmetro booliano.
- O atributo ValidateSet e o atributo ValidatePattern não podem passar parâmetros nomeados.
- As funções avançadas não podem ser usadas em transações.

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Functions](about_Functions.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)
