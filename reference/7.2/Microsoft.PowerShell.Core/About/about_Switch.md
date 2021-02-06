---
description: Explica como usar uma opção para manipular várias `If` instruções.
Locale: en-US
ms.date: 05/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_switch?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Switch
ms.openlocfilehash: 5ca12fe1d5052c1589c5dfecca8cf08cf68901e8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596198"
---
# <a name="about-switch"></a>Sobre o comutador

## <a name="short-description"></a>Descrição breve
Explica como usar uma opção para manipular várias `If` instruções.

## <a name="long-description"></a>Descrição longa

Para verificar uma condição em um script ou uma função, use uma `If` instrução. A `If` instrução pode verificar muitos tipos de condições, incluindo o valor de variáveis e as propriedades de objetos.

Para verificar várias condições, use uma `Switch` instrução. A `Switch` instrução é equivalente a uma série de `If` instruções, mas é mais simples. A `Switch` instrução lista cada condição e uma ação opcional. Se uma condição for obtida, a ação será executada.

A `Switch` instrução pode usar as `$_` `$switch` variáveis and automáticas. Para obter mais informações, consulte [about_Automatic_Variables](about_Automatic_Variables.md).

Uma `Switch` instrução básica tem o seguinte formato:

```powershell
Switch (<test-value>)
{
    <condition> {<action>}
    <condition> {<action>}
}
```

Por exemplo, a instrução a seguir `Switch` compara o valor de teste, 3, para cada uma das condições. Quando o valor de teste corresponde à condição, a ação é executada.

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."}
    4 {"It is four."}
}
```

```Output
It is three.
```

Neste exemplo simples, o valor é comparado a cada condição na lista, mesmo que haja uma correspondência para o valor 3. A instrução a seguir `Switch` tem duas condições para um valor de 3. Ele demonstra que, por padrão, todas as condições são testadas.

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."}
    4 {"It is four."}
    3 {"Three again."}
}
```

```Output
It is three.
Three again.
```

Para direcionar o `Switch` para parar de comparar após uma correspondência, use a `Break` instrução. A `Break` instrução encerra a `Switch` instrução.

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."; Break}
    4 {"It is four."}
    3 {"Three again."}
}
```

```Output
It is three.
```

Se o valor de teste for uma coleção, como uma matriz, cada item na coleção será avaliado na ordem em que aparece. Os exemplos a seguir avaliam 4 e depois 2.

```powershell
switch (4, 2)
{
    1 {"It is one." }
    2 {"It is two." }
    3 {"It is three." }
    4 {"It is four." }
    3 {"Three again."}
}
```

```Output
It is four.
It is two.
```

Todas as `Break` instruções se aplicam à coleção, não a cada valor, conforme mostrado no exemplo a seguir. A `Switch` instrução é encerrada pela `Break` instrução na condição do valor 4.

```powershell
switch (4, 2)
{
    1 {"It is one."; Break}
    2 {"It is two." ; Break }
    3 {"It is three." ; Break }
    4 {"It is four." ; Break }
    3 {"Three again."}
}
```

```Output
It is four.
```

### <a name="syntax"></a>Syntax

A `Switch` sintaxe de instrução completa é a seguinte:

```
switch [-regex|-wildcard|-exact][-casesensitive] (<value>)
{
    "string"|number|variable|{ expression } { statementlist }
    default { statementlist }
}
```

ou

```
switch [-regex|-wildcard|-exact][-casesensitive] -file filename
{
    "string"|number|variable|{ expression } { statementlist }
    default { statementlist }
}
```

Se nenhum parâmetro for usado, `Switch` o terá o mesmo que usar o parâmetro **exato** . Ele executa uma correspondência que não diferencia maiúsculas de minúsculas para o valor. Se o valor for uma coleção, cada elemento será avaliado na ordem em que ele aparece.

A `Switch` instrução deve incluir pelo menos uma instrução de condição.

A `Default` cláusula é disparada quando o valor não corresponde a nenhuma das condições. É equivalente a uma `Else` cláusula em uma `If` instrução. Somente uma `Default` cláusula é permitida em cada `Switch` instrução.

`Switch` tem os seguintes parâmetros:

- **Curinga** – indica que a condição é uma cadeia de caracteres curinga. Se a cláusula match não for uma cadeia de caracteres, o parâmetro será ignorado. A comparação não diferencia maiúsculas de minúsculas.
- **Exact** -indica que a cláusula Match, se for uma cadeia de caracteres, deve corresponder exatamente. Se a cláusula match não for uma cadeia de caracteres, esse parâmetro será ignorado. A comparação não diferencia maiúsculas de minúsculas.
- **CaseSensitive** -executa uma correspondência que diferencia maiúsculas de minúsculas. Se a cláusula match não for uma cadeia de caracteres, esse parâmetro será ignorado.
- **Arquivo**-obtém entrada de um arquivo em vez de uma instrução Value. Se vários parâmetros de **arquivo** forem incluídos, somente o último será usado. Cada linha do arquivo é lida e avaliada pela `Switch` instrução. A comparação não diferencia maiúsculas de minúsculas.
- **Regex** -executa a correspondência de expressão regular do valor para a condição. Se a cláusula match não for uma cadeia de caracteres, esse parâmetro será ignorado.
  A comparação não diferencia maiúsculas de minúsculas. A `$matches` variável automática está disponível para uso dentro do bloco de instrução correspondente.

> [!NOTE]
> Ao especificar valores conflitantes, como **Regex** e **wildcard**, o último parâmetro especificado tem precedência e todos os parâmetros conflitantes são ignorados. Também são permitidas várias instâncias de parâmetros. No entanto, apenas o último parâmetro usado é efetivo.

Neste exemplo, um objeto que não é uma cadeia de caracteres ou dados numéricos é passado para o `Switch` . O `Switch` executa uma coerção de cadeia de caracteres no objeto e avalia o resultado.

```powershell
$test = @{
    Test  = 'test'
    Test2 = 'test2'
}

$test.ToString()

switch -Exact ($test)
{
    'System.Collections.Hashtable'
    {
        'Hashtable string coercion'
    }
    'test'
    {
        'Hashtable value'
    }
}
```

```Output
System.Collections.Hashtable
Hashtable string coercion
```

Neste exemplo, não há nenhum caso correspondente, portanto, não há nenhuma saída.

```powershell
switch ("fourteen")
{
    1 {"It is one."; Break}
    2 {"It is two."; Break}
    3 {"It is three."; Break}
    4 {"It is four."; Break}
    "fo*" {"That's too many."}
}
```

Ao adicionar a `Default` cláusula, você pode executar uma ação quando nenhuma outra condição for realizada com sucesso.

```powershell
switch ("fourteen")
{
    1 {"It is one."; Break}
    2 {"It is two."; Break}
    3 {"It is three."; Break}
    4 {"It is four."; Break}
    "fo*" {"That's too many."}
    Default {
        "No matches"
    }
}
```

```Output
No matches
```

Para a palavra "quatorze" corresponder a um caso, você deve usar `-Wildcard` o `-Regex` parâmetro ou.

```powershell
   PS> switch -Wildcard ("fourteen")
       {
           1 {"It is one."; Break}
           2 {"It is two."; Break}
           3 {"It is three."; Break}
           4 {"It is four."; Break}
           "fo*" {"That's too many."}
       }
 ```

```Output
That's too many.
```

O exemplo a seguir usa o `-Regex` parâmetro.

```powershell
$target = 'https://bing.com'
switch -Regex ($target)
{
    '^ftp\://.*$' { "$_ is an ftp address"; Break }
    '^\w+@\w+\.com|edu|org$' { "$_ is an email address"; Break }
    '^(http[s]?)\://.*$' { "$_ is a web address that uses $($matches[1])"; Break }
}
```

```Output
https://bing.com is a web address that uses https
```

Uma condição de instrução switch pode ser:

- Uma expressão cujo valor é comparado ao valor de entrada
- Um bloco de script que deve retornar `$true` se uma condição for atendida.

A `$_` variável automática contém o valor passado para a instrução switch e está disponível para avaliação e uso dentro do escopo das instruções Condition.

A ação para cada condição é independente das ações em outras condições.

O exemplo a seguir demonstra o uso de blocos de script como `Switch` condições de instrução.

```powershell
switch ("Test")
{
    {$_ -is [String]} {
        "Found a string"
    }
    "Test" {
        "This $_ executes as well"
    }
}
```

```Output
Found a string
This Test executes as well
```

Se o valor corresponder a várias condições, a ação para cada condição será executada. Para alterar esse comportamento, use as `Break` `Continue` palavras-chave ou.

A `Break` palavra-chave interrompe o processamento e sai da `Switch` instrução.

A `Continue` palavra-chave para o processamento do valor atual, mas continua processando quaisquer valores subsequentes.

O exemplo a seguir processa uma matriz de números e exibe se eles são ímpares ou até mesmo. Números negativos são ignorados com a `Continue` palavra-chave. Se um número não-numérico for encontrado, a execução será encerrada com a `Break` palavra-chave.

```powershell
switch (1,4,-1,3,"Hello",2,1)
{
    {$_ -lt 0} { Continue }
    {$_ -isnot [Int32]} { Break }
    {$_ % 2} {
        "$_ is Odd"
    }
    {-not ($_ % 2)} {
        "$_ is Even"
    }
}
```

```Output
1 is Odd
4 is Even
3 is Odd
```

## <a name="see-also"></a>Consulte também

[about_Break](about_Break.md)

[about_Continue](about_Continue.md)

[about_If](about_If.md)

[about_Script_Blocks](about_Script_Blocks.md)
