---
description: Descreve um comando de linguagem que você pode usar para executar instruções com base em um teste condicional.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 3/4/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_for?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_For
ms.openlocfilehash: 28d901c62ccc17febb74412a773710f4d5b5a4be
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196027"
---
# <a name="about-for"></a>Sobre o para

## <a name="short-description"></a>Descrição breve
Descreve um comando de linguagem que você pode usar para executar instruções com base em um teste condicional.

## <a name="long-description"></a>Descrição longa

A `For` instrução (também conhecida como `For` loop) é uma construção de linguagem que você pode usar para criar um loop que executa comandos em um bloco de comando enquanto uma condição especificada é avaliada como `$true` .

Um uso típico do `For` loop é iterar uma matriz de valores e operar em um subconjunto desses valores. Na maioria dos casos, se você quiser iterar todos os valores em uma matriz, considere usar uma `Foreach` instrução.

### <a name="syntax"></a>Syntax

O seguinte mostra a `For` sintaxe da instrução.

```
for (<Init>; <Condition>; <Repeat>)
{
    <Statement list>
}
```

O espaço reservado de **inicialização** representa um ou mais comandos que são executados antes do início do loop. Normalmente, você usa a parte **init** da instrução para criar e inicializar uma variável com um valor inicial.

Essa variável será então a base para a condição a ser testada na próxima parte da `For` instrução.

O espaço reservado da **condição** representa a parte da `For` instrução que é resolvida para `$true` um `$false` valor ou **booliano** . O PowerShell avalia a condição toda vez que o `For` loop é executado. Se a instrução for `$true` , os comandos no bloco de comando serão executados e a instrução será avaliada novamente. Se a condição ainda for `$true` , os comandos na **lista de instruções** serão executados novamente. O loop é repetido até que a condição se torne `$false` .

O espaço reservado de **repetição** representa um ou mais comandos, separados por vírgulas, que são executados cada vez que o loop se repete. Normalmente, isso é usado para modificar uma variável que é testada dentro da parte da **condição** da instrução.

O espaço reservado da **lista de instruções** representa um conjunto de um ou mais comandos que são executados cada vez que o loop é inserido ou repetido. O conteúdo da **lista de instruções** está entre chaves.

### <a name="support-for-multiple-operations"></a>Suporte para várias operações

As sintaxes a seguir têm suporte para várias operações de atribuição na instrução **init** :

```powershell
# Comma separated assignment expressions enclosed in parenthesis.
for (($i = 0), ($j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}

# Sub-expression using the semicolon to separate statements.
for ($($i = 0;$j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}
```

As sintaxes a seguir têm suporte para várias operações de atribuição na instrução **REPEAT** :

```powershell
# Comma separated assignment expressions.
for (($i = 0), ($j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}

# Comma separated assignment expressions enclosed in parenthesis.
for (($i = 0), ($j = 0); $i -lt 10; ($i++), ($j++))
{
    "`$i:$i"
    "`$j:$j"
}

# Sub-expression using the semicolon to separate statements.
for ($($i = 0;$j = 0); $i -lt 10; $($i++;$j++))
{
    "`$i:$i"
    "`$j:$j"
}
```

> [!NOTE]
> Operações diferentes de pré ou pós-incremento podem não funcionar com todas as sintaxes.

Para várias **condições** , use operadores lógicos, conforme demonstrado pelo exemplo a seguir.

```powershell
for (($i = 0), ($j = 0); $i -lt 10 -and $j -lt 10; $i++,$j++)
{
    "`$i:$i"
    "`$j:$j"
}
```

Para obter mais informações, consulte [about_Logical_Operators](about_Logical_Operators.md).

### <a name="examples"></a>Exemplos

No mínimo, uma `For` instrução requer o parêntese em torno da parte de **init** , da **condição** e da **repetição** da instrução e de um comando entre chaves na parte da **lista de instruções** da instrução.

Observe que os exemplos futuros mostram intencionalmente o código fora da `For` instrução. Em exemplos posteriores, o código é integrado à `For` instrução.

Por exemplo, a instrução a seguir `For` exibe continuamente o valor da `$i` variável até que você interrompa manualmente o comando pressionando CTRL + C.

```powershell
$i = 1
for (;;)
{
    Write-Host $i
}
```

Você pode adicionar outros comandos à lista de instruções para que o valor de `$i` seja incrementado em 1 cada vez que o loop for executado, como mostra o exemplo a seguir.

```powershell
for (;;)
{
    $i++; Write-Host $i
}
```

Até que você saia do comando pressionando CTRL + C, essa instrução exibirá continuamente o valor da `$i` variável à medida que ela for incrementada em 1 cada vez que o loop for executado.

Em vez de alterar o valor da variável na lista de instruções, parte da `For` instrução, você pode usar a parte de **repetição** da `For` instrução, como a seguir.

```powershell
$i=1
for (;;$i++)
{
    Write-Host $i
}
```

Essa instrução ainda será repetida indefinidamente até que você se divida do comando pressionando CTRL + C.

Você pode encerrar o `For` loop usando uma *condição* . Você pode inserir uma condição usando a parte da **condição** da `For` instrução. O `For` loop é encerrado quando a condição é avaliada como `$false` .

No exemplo a seguir, o `For` loop é executado enquanto o valor de `$i` é menor ou igual a 10.

```powershell
$i=1
for(;$i -le 10;$i++)
{
    Write-Host $i
}
```

Em vez de criar e inicializar a variável fora da `For` instrução, você pode executar essa tarefa dentro do `For` loop usando a parte **init** da `For` instrução.

```powershell
for($i=1; $i -le 10; $i++){Write-Host $i}
```

Você pode usar retornos de carro em vez de ponto e vírgula para delimitar as partes de **inicialização** , **condição** e **repetição** da `For` instrução. O exemplo a seguir mostra um `For` que usa essa sintaxe alternativa.

```powershell
for ($i = 0
  $i -lt 10
  $i++){
  $i
}
```

Essa forma alternativa da `For` instrução funciona nos arquivos de script do PowerShell e no prompt de comando do PowerShell. No entanto, é mais fácil usar a `For` sintaxe da instrução com ponto e vírgula quando você insere comandos interativos no prompt de comando.

O `For` loop é mais flexível do que o `Foreach` loop porque permite incrementar valores em uma matriz ou coleção usando padrões. No exemplo a seguir, a `$i` variável é incrementada por 2 na parte de **repetição** da `For` instrução.

```powershell
for ($i = 0; $i -le 20; $i += 2)
{
    Write-Host $i
}
```

O `For` loop também pode ser gravado em uma linha como no exemplo a seguir.

```powershell
for ($i = 0; $i -lt 10; $i++) { Write-Host $i }
```

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Foreach](about_Foreach.md)
