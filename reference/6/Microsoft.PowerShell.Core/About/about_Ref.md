---
description: Descreve como criar e usar uma variável de tipo de referência. Você pode usar variáveis de tipo de referência para permitir que uma função altere o valor de uma variável que é passada para ela.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 08/24/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_ref?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Ref
ms.openlocfilehash: fefc0f002db0b9591b2d23e148db381f7413871f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195665"
---
# <a name="about-ref"></a>Sobre ref

## <a name="short-description"></a>Descrição breve
Descreve como criar e usar uma variável de tipo de referência. Você pode usar variáveis de tipo de referência para permitir que uma função altere o valor de uma variável que é passada para ela.

## <a name="long-description"></a>Descrição longa

Você pode passar variáveis para funções *por referência* ou *por valor* .

Ao passar uma variável *por valor* , você está passando uma cópia dos dados.

No exemplo a seguir, a função altera o valor da variável passada para ela. No PowerShell, os inteiros são tipos de valor para que sejam passados por valor.
Portanto, o valor de `$var` é inalterado fora do escopo da função.

```powershell
Function Test($data)
{
    $data = 3
}

$var = 10
Test -data $var
$var
```

```output
10
```

No exemplo a seguir, uma variável que contém um `Hashtable` é passada para uma função. `Hashtable` é um tipo de objeto, portanto, por padrão, ele é passado para a função *por referência* .

Ao passar uma variável *por referência* , a função pode alterar os dados e essa alteração persiste após a execução da função.

```powershell
Function Test($data)
{
    $data.Test = "New Text"
}

$var = @{}
Test -data $var
$var
```

```output
Name                           Value
----                           -----
Test                           New Text
```

A função adiciona um novo par chave-valor que persiste fora do escopo da função.

### <a name="writing-functions-to-accept-reference-parameters"></a>Gravando funções para aceitar parâmetros de referência

Você pode codificar suas funções para obter um parâmetro como uma referência, independentemente do tipo de dados passado. Isso requer que você especifique o tipo de parâmetros como `System.Management.Automation.PSReference` , ou `[ref]` .

Ao usar referências, você deve usar a `Value` Propriedade do `System.Management.Automation.PSReference` tipo para acessar seus dados.

```powershell
Function Test([ref]$data)
{
    $data.Value = 3
}
```

Para passar uma variável para um parâmetro que espera uma referência, você deve digitar Cast a Variable como uma referência.

> [!NOTE]
> Os colchetes e os parênteses são necessários.

```powershell
$var = 10
Test -data ([ref]$var)
$var
```

```output
3
```

### <a name="passing-references-to-net-methods"></a>Passando referências para métodos .NET

Alguns métodos .NET podem exigir que você passe uma variável como referência. Quando a definição do método usa as palavras-chave `in` , `out` , ou `ref` em um parâmetro, ela espera uma referência.

```powershell
[int] | Get-Member -Static -Name TryParse
```

```output
Name     MemberType Definition
----     ---------- ----------
TryParse Method     static bool TryParse(string s, [ref] int result)
```

O `TryParse` método tenta analisar uma cadeia de caracteres como um inteiro. Se o método for bem-sucedido, ele retornará `$true` e o resultado será armazenado na variável que você passou **por referência** .

```
PS> $number = 0
PS> [int]::TryParse("15", ([ref]$number))
True
PS> $number
15
```

### <a name="references-and-scopes"></a>Referências e escopos

As referências permitem que o valor de uma variável no escopo pai seja alterado em um escopo filho.

```powershell
# Create a value type variable.
$i = 0
# Create a reference type variable.
$iRef = [ref]0
# Invoke a scriptblock to attempt to change both values.
&{$i++;$iRef.Value++}
# Output the results.
"`$i = $i;`$iRef = $($iRef.Value)"
```

```output
$i = 0;$iRef = 1
```

Somente a variável do tipo de referência foi alterada.

## <a name="see-also"></a>Confira também

[about_Variables](about_Variables.md)

[about_Environment_Variables](about_Environment_Variables.md)

[about_Functions](about_Functions.md)

[about_Script_Blocks](about_Script_Blocks.md)

[about_Scopes](about_scopes.md)
