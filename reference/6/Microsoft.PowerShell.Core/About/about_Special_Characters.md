---
description: Descreve as sequências de caracteres especiais que controlam como o PowerShell interpreta os próximos caracteres na sequência.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 04/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_special_characters?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Special_Characters
ms.openlocfilehash: d9e09aa2800538beb363ccbcf2a193c727200869
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195621"
---
# <a name="about-special-characters"></a>Sobre caracteres especiais

## <a name="short-description"></a>Descrição breve

Descreve as sequências de caracteres especiais que controlam como o PowerShell interpreta os próximos caracteres na sequência.

## <a name="long-description"></a>Descrição longa

O PowerShell dá suporte a um conjunto de sequências de caracteres especiais que são usadas para representar caracteres que não fazem parte do conjunto de caracteres padrão. As sequências normalmente são conhecidas como _sequências de escape_ .

As seqüências de escape começam com o caractere de acento grave, conhecido como acentuação (ASCII 96), e diferenciam maiúsculas de minúsculas. O caractere de acento grave também pode ser chamado de _caractere de escape_ .

As seqüências de escape são interpretadas somente quando contidas em cadeias de caracteres com aspas duplas ( `"` ).

O PowerShell reconhece estas sequências de escape:

|  Sequência   |       Descrição       |
| ----------- | ----------------------- |
| `` `0 ``    | Nulo                    |
| `` `a ``    | Alerta                   |
| `` `b ``    | Backspace               |
| `` `e ``    | Escape                  |
| `` `f ``    | Avanço de formulário               |
| `` `n ``    | Nova linha                |
| `` `r ``    | Retorno de carro         |
| `` `t ``    | Guia horizontal          |
| `` `u{x} `` | Sequência de escape Unicode |
| `` `v ``    | Guia vertical            |

O PowerShell também tem um token especial para marcar onde você deseja que a análise pare. Todos os caracteres que seguem esse token são usados como valores literais que não são interpretados.

Token de análise especial:

| Sequência |            Descrição             |
| -------- | ---------------------------------- |
| `--%`    | Pare a análise de qualquer coisa que segue |

## <a name="null-0"></a>NULL (' 0)

O caractere nulo ( `` `0 `` ) aparece como um espaço vazio na saída do PowerShell.
Essa funcionalidade permite que você use o PowerShell para ler e processar arquivos de texto que usam caracteres nulos, como a terminação de cadeia de caracteres ou indicadores de encerramento de registro. O caractere especial nulo não é equivalente à `$null` variável, que armazena um valor **nulo** .

## <a name="alert-a"></a>Alerta (' a)

O caractere alerta ( `` `a `` ) envia um sinal de bipe para o palestrante do computador.
Você pode usar esse caractere para avisar um usuário sobre uma ação iminente. O exemplo a seguir envia dois sinais de bipe para o palestrante do computador local.

```powershell
for ($i = 0; $i -le 1; $i++){"`a"}
```

## <a name="backspace-b"></a>Backspace (' b)

O caractere de Backspace ( `` `b `` ) move o cursor para trás, mas não exclui nenhum caractere.

O exemplo grava a palavra **backup** e, em seguida, move o cursor duas vezes.
Em seguida, na nova posição, o grava um espaço seguido pela palavra de **saída** .

```powershell
"backup`b`b out"
```

```Output
back out
```

## <a name="escape-e"></a>Escape (' e)

O caractere de escape ( `` `e `` ) é usado com mais frequência para especificar uma sequência de terminais virtual (sequência de escape ANSI) que modifica a cor do texto e outros atributos de texto, como negrito e sublinhado. Essas sequências também podem ser usadas para posicionamento e rolagem do cursor. O host do PowerShell deve dar suporte a sequências de terminais virtuais. Você pode verificar o valor booliano de `$Host.UI.SupportsVirtualTerminal` para determinar se essas sequências ANSI têm suporte.

Para obter mais informações sobre sequências de escape ANSI, consulte [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).

O exemplo a seguir gera um texto com uma cor de primeiro plano verde.

```powershell
$fgColor = 32 # green
"`e[${fgColor}mGreen text`e[0m"
```

```Output
Green text
```

## <a name="form-feed-f"></a>Feed de formulário (' f)

O caractere de feed de formulário ( `` `f `` ) é uma instrução de impressão que ejeta a página atual e continua imprimindo na próxima página. O caractere de feed de formulário afeta apenas os documentos impressos. Ele não afeta a saída da tela.

## <a name="new-line-n"></a>Nova linha (' n)

O caractere de nova linha ( `` `n `` ) insere uma quebra de linha imediatamente após o caractere.

Este exemplo mostra como usar o caractere de nova linha para criar quebras de linha em um `Write-Host` comando.

```powershell
"There are two line breaks to create a blank line`n`nbetween the words."
```

```Output
There are two line breaks to create a blank line

between the words.
```

## <a name="carriage-return-r"></a>Retorno de carro (' r)

O caractere de retorno de carro ( `` `r `` ) move o cursor de saída para o início da linha atual e continua gravando. Todos os caracteres na linha atual são substituídos.

Neste exemplo, o texto antes do retorno de carro é substituído.

```powershell
Write-Host "These characters are overwritten.`rI want this text instead "
```

Observe que o texto antes do `` `r `` caractere não é excluído, ele é substituído.

```Output
I want this text instead written.
```

## <a name="horizontal-tab-t"></a>Guia horizontal (t)

O caractere de tabulação horizontal ( `` `t `` ) avança para a próxima parada de tabulação e continua gravando nesse ponto. Por padrão, o console do PowerShell tem uma parada de tabulação em cada oitavo espaço.

Este exemplo insere duas guias entre cada coluna.

```powershell
"Column1`t`tColumn2`t`tColumn3"
```

```Output
Column1         Column2         Column3
```

## <a name="unicode-character-ux"></a>Caractere Unicode (' u {x})

A sequência de escape Unicode ( `` `u{x} `` ) permite que você especifique qualquer caractere Unicode pela representação hexadecimal de seu ponto de código. Isso inclui caracteres Unicode acima do plano multilíngue básico (> `0xFFFF` ), que inclui os caracteres de Emoji como o caractere de **polegar para cima** ( `` `u{1F44D} `` ). A sequência de escape Unicode requer pelo menos um dígito hexadecimal e dá suporte a até seis dígitos hexadecimais. O valor hexadecimal máximo para a sequência é `10FFFF` .

Este exemplo gera o símbolo de **seta para cima** (&#x2195;).

```powershell
"`u{2195}"
```

## <a name="vertical-tab-v"></a>Guia vertical (' v)

O caractere de tabulação horizontal ( `` `v `` ) avança para a próxima parada de tabulação vertical e grava a saída restante nesse ponto. Isso não tem efeito no console do Windows padrão.

```powershell
Write-Host "There is a vertical tab`vbetween the words."
```

O exemplo a seguir mostra a saída que você obteria em uma impressora ou em um host de console diferente.

```Output
There is a vertical tab
                       between the words.
```

## <a name="stop-parsing-token---"></a>Token de análise de parada (--%)

O token Stop-analisation ( `--%` ) impede que o PowerShell interprete cadeias de caracteres como comandos e expressões do PowerShell. Isso permite que essas cadeias de caracteres sejam passadas para outros programas para interpretação.

Coloque o token de análise de parada após o nome do programa e os argumentos do programa que podem causar erros.

Neste exemplo, o `Icacls` comando usa o token de interrupção de análise.

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

O PowerShell envia a cadeia de caracteres a seguir para `Icacls` .

```
X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

Veja a seguir outro exemplo. A função **adargs** gera os valores passados para ele. Neste exemplo, passamos a variável chamada `$HOME` para a função duas vezes.

```powershell
function showArgs {
  "`$args = " + ($args -join '|')
}

showArgs $HOME --% $HOME
```

Você pode ver na saída que, para o primeiro parâmetro, a variável `$HOME` é interpretada pelo PowerShell para que o valor da variável seja passado para a função. O segundo uso do `$HOME` vem após o token de análise de parada, portanto, a cadeia de caracteres "$Home" é passada para a função sem interpretação.

```Output
$args = C:\Users\username|--%|$HOME
```

Para obter mais informações sobre o token da análise de parada, consulte [about_Parsing](about_Parsing.md).

## <a name="see-also"></a>Confira também

[about_Quoting_Rules](about_Quoting_Rules.md)
