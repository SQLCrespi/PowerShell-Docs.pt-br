---
description: Descreve como o PowerShell analisa os comandos.
Locale: en-US
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parsing?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parsing
ms.openlocfilehash: a5ce30b2ad9aff7dd8b54e7a62937013a61cd278
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596813"
---
# <a name="about-parsing"></a>Sobre a análise

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve como o PowerShell analisa os comandos.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Quando você insere um comando no prompt de comando, o PowerShell quebra o texto do comando em uma série de segmentos chamados _tokens_ e, em seguida, determina como interpretar cada token.

Por exemplo, se você digitar:

```powershell
Write-Host book
```

O PowerShell quebra o comando em dois tokens `Write-Host` e, em seguida `book` , interpreta cada token independentemente usando um dos dois modos de análise principais: modo de expressão e modo de argumento.

> [!NOTE]
> Como o PowerShell analisa a entrada de comando, ele tenta resolver os nomes de comando para cmdlets ou executáveis nativos. Se um nome de comando não tiver uma correspondência exata, o PowerShell precederá `Get-` o comando como um verbo padrão. Por exemplo, o PowerShell analisa `Process` como `Get-Process` . Não é recomendável usar esse recurso pelos seguintes motivos:
>
> - Ele é ineficiente. Isso faz com que o PowerShell pesquise várias vezes.
> - Programas externos com o mesmo nome são resolvidos primeiro, portanto, você não pode executar o cmdlet pretendido.
> - `Get-Help` e `Get-Command` não reconhecem nomes sem verbos.

### <a name="expression-mode"></a>Modo de expressão

O modo de expressão destina-se à combinação de expressões, necessário para manipulação de valor em uma linguagem de script. As expressões são representações de valores na sintaxe do PowerShell e podem ser simples ou compostas, por exemplo:

As expressões literais são representações diretas de seus valores: 

```powershell
'hello', 32
```

Expressões variáveis carregam o valor da variável à qual fazem referência: 

```powershell
$x, $script:path
```
Os operadores combinam outras expressões para avaliação: 

```powershell
- 12, -not $Quiet, 3 + 7, $input.Length -gt 1
```

- Os _literais de cadeia de caracteres_ devem estar entre aspas.
- Os _números_ são tratados como valores numéricos em vez de uma série de caracteres (a menos que tenham escape).
- _Operadores_, incluindo operadores unários como `-` e `-not` e operadores binários como `+` e `-gt` , são interpretados como operadores e aplicam suas respectivas operações em seus argumentos (operandos).
- As _expressões de atributo e de conversão_ são analisadas como expressões e aplicadas a expressões subordinadas, por exemplo, `[int] '7'` .
- _Referências de variáveis_ são avaliadas para seus valores, mas _nivelamento_ (ou seja, colar conjuntos de parâmetros predefinidos) é proibido e causa um erro de analisador.
- Qualquer outra coisa será tratada como um comando a ser invocado.

### <a name="argument-mode"></a>Modo de argumento

Durante a análise, o PowerShell primeiro procura interpretar a entrada como uma expressão. Mas quando uma invocação de comando é encontrada, a análise continua no modo de argumento.

O modo de argumento é projetado para a análise de argumentos e parâmetros para comandos em um ambiente de Shell. Toda a entrada é tratada como uma cadeia de caracteres expansível, a menos que use uma das seguintes sintaxes:

- Cifrão ( `$` ) inicia uma referência de variável (somente se ela for seguida por um nome de variável válido, caso contrário, ela será interpretada como parte da cadeia de caracteres expansível).
- Aspas ( `'` e `"` ) iniciar valores de cadeia de caracteres
- Parênteses ( `(` e `)` ) demarcam novas expressões.
- Expressões inseridas de operador de subexpressão ( `$(` ... `)` ) demarcates.
- Chaves ( `{` e `}` ) demarcar novos blocos de script.
- O sinal de arroba inicial ( `@` ) inicia as sintaxes de expressão, como nivelamento ( `@args` ), matrizes ( `@(1,2,3)` ) e tabelas de hash ( `@{a=1;b=2}` ).
- Vírgulas ( `,` ) introduzem listas passadas como matrizes, exceto quando o comando a ser chamado é um aplicativo nativo; nesse caso, eles são interpretados como parte da cadeia de caracteres expansível. Não há suporte para vírgulas iniciais, consecutivas ou à direita.

<!--
01234567890123456789012345678901234567890123456789012345678901234567890123456789
-->
Os valores das expressões inseridas são convertidos em cadeias de caracteres.

A tabela a seguir fornece vários exemplos de valores processados no modo de expressão e no modo de argumento e na avaliação desses valores. Supomos que o valor da variável `a` é `4` .

|       Exemplo        |    Modo    |      Result       |
| -------------------- | ---------- | ----------------- |
| `2`                  | Expression | 2 (inteiro)       |
| `` `2``              | Expression | "2" (comando)     |
| `echo 2`             | Expression | 2 (inteiro)       |
| `2+2`                | Expression | 4 (inteiro)       |
| `echo 2+2`           | Argumento   | "2 + 2" (cadeia de caracteres)    |
| `echo(2+2)`          | Expression | 4 (inteiro)       |
| `$a`                 | Expression | 4 (inteiro)       |
| `echo $a`            | Expression | 4 (inteiro)       |
| `$a+2`               | Expression | 6 (inteiro)       |
| `echo $a+2`          | Argumento   | 4 + 2 (cadeia de caracteres)      |
| `$-`                 | Argumento   | "$-" (comando)    |
| `echo $-`            | Argumento   | "$-" (cadeia de caracteres)     |
| `a$a`                | Expression | "a $ a" (comando)   |
| `echo a$a`           | Argumento   | "A4" (cadeia de caracteres)     |
| `a'$a'`              | Expression | "a $ a" (comando)   |
| `echo a'$a'`         | Argumento   | "a $ a" (cadeia de caracteres)    |
| `a"$a"`              | Expression | "a $ a" (comando)   |
| `echo a"$a"`         | Argumento   | "A4" (cadeia de caracteres)     |
| `a$(2)`              | Expression | "a $ (2)" (comando) |
| `echo a$(2)`         | Argumento   | "a2" (cadeia de caracteres)     |

Cada token pode ser interpretado como um tipo de objeto, como booliano ou cadeia de caracteres. O PowerShell tenta determinar o tipo de objeto a partir da expressão.
O tipo de objeto depende do tipo de parâmetro esperado por um comando e se o PowerShell sabe como converter o argumento para o tipo correto. A tabela a seguir mostra vários exemplos dos tipos atribuídos aos valores retornados pelas expressões.

|       Exemplo          |    Modo    |     Result      |
| ---------------------- | ---------- | --------------- |
| `Write-Output !1`      | argumento   | "! 1" (cadeia de caracteres)   |
| `Write-Output (!1)`    | expressão | Falso (booliano) |
| `Write-Output (2)`     | expressão | 2 (inteiro)     |
| `Set-Variable AB A,B`  | argumento   | ' A ', ' B ' (matriz) |
| `CMD /CECHO A,B`       | argumento   | ' A, B ' (cadeia de caracteres)  |
| `CMD /CECHO $AB`       | expressão | ' A ', ' B ' (matriz) |
| `CMD /CECHO :$AB`      | argumento   | ': A B ' (cadeia de caracteres) |

O símbolo de análise de parada ( `--%` ), introduzido no powershell 3,0, direciona o PowerShell para evitar a interpretação de entrada como comandos ou expressões do PowerShell.

Ao chamar um programa executável no PowerShell, coloque o símbolo de interrupção de análise antes dos argumentos do programa. Essa técnica é muito mais fácil do que usar caracteres de escape para evitar a interpretação indiferente.

Quando ele encontra um símbolo de análise de parada, o PowerShell trata os caracteres restantes na linha como um literal. A única interpretação que ele executa é substituir valores de variáveis de ambiente que usam notação padrão do Windows, como `%USERPROFILE%` .

O símbolo de interrupção de análise entra em vigor somente até o próximo caractere de nova linha ou de pipeline. Você não pode usar um caractere de continuação ( `` ` `` ) para estender seu efeito ou usar um delimitador de comando ( `;` ) para encerrar seu efeito.

Por exemplo, o comando a seguir chama o programa **icacls** .

```powershell
icacls X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

Para executar esse comando no PowerShell 2,0, você deve usar caracteres de escape para impedir que o PowerShell interprete incorretamente os parênteses.

```powershell
icacls X:\VMS /grant Dom\HVAdmin:`(CI`)`(OI`)F
```

A partir do PowerShell 3,0, você pode usar o símbolo de interrupção de análise.

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

O PowerShell envia a seguinte cadeia de caracteres de comando para o programa **icacls** :

`X:\VMS /grant Dom\HVAdmin:(CI)(OI)F`

> [!NOTE]
> O símbolo de análise de parada destina-se somente ao uso em plataformas Windows.

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Command_Syntax](about_Command_Syntax.md)
