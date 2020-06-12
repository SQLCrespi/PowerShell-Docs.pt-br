---
title: Controle de fluxo
description: O PowerShell fornece métodos para criar loops, tomar decisões e controlar logicamente o fluxo de código em scripts.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 4f0d7b7f5f3c12bb9475af5aed42b2d32cfbc14d
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84437987"
---
# <a name="chapter-6---flow-control"></a>Capítulo 6 – Controle de fluxo

## <a name="scripting"></a>Scripting

Quando você passa da escrita de comandos de uma linha do PowerShell para a escrita de scripts, isso parece muito mais complicado do que realmente é. Um script não é nada mais do que os comandos idênticos ou semelhantes que você executará de maneira interativa no console do PowerShell, exceto que eles são salvos como um arquivo `.PS1`. Há alguns constructos de script que você poderá usar como um loop `foreach` em vez do cmdlet `ForEach-Object`. Para iniciantes, as diferenças podem ser confusas, especialmente quando você considera que `foreach` é um constructo de script e um alias para o cmdlet `ForEach-Object`.

## <a name="looping"></a>Loop

Uma das grandes vantagens do PowerShell é que, logo que você descobre como fazer algo para um item, é quase tão fácil realizar a mesma tarefa para centenas de itens. Basta executar um loop pelos itens usando um dos vários tipos diferentes de loops no PowerShell.

### <a name="foreach-object"></a>ForEach-Object

`ForEach-Object` é um cmdlet para iterar em itens de um pipeline, como é o caso dos comandos de uma linha do PowerShell. `ForEach-Object` transmite os objetos por meio do pipeline.

Embora o parâmetro **Module** de `Get-Command` aceite vários valores que são cadeias de caracteres, ele só os aceita por meio da entrada de pipeline pelo nome da propriedade ou por meio da entrada de parâmetro. No cenário a seguir, se eu quiser direcionar duas cadeias de caracteres por valor para `Get-Command` para uso com o parâmetro **Module**, precisarei usar o cmdlet `ForEach-Object`.

```powershell
'ActiveDirectory', 'SQLServer' |
   ForEach-Object {Get-Command -Module $_} |
     Group-Object -Property ModuleName -NoElement |
         Sort-Object -Property Count -Descending
```

```Output
Count Name
----- ----
  147 ActiveDirectory
   82 SqlServer
```

No exemplo anterior, `$_` é o objeto atual. No PowerShell versão 3.0 em diante, `$PSItem` pode ser usado em vez de `$_`. Porém, acho que os usuários mais experientes do PowerShell ainda preferem usar `$_`, já que ele é compatível com versões anteriores e leva menos tempo para digitar.

Ao usar a palavra-chave `foreach`, você precisará armazenar todos os itens na memória antes de iterar neles, o que pode ser difícil se você não sabe com quantos itens está trabalhando.

```powershell
$ComputerName = 'DC01', 'WEB01'
foreach ($Computer in $ComputerName) {
  Get-ADComputer -Identity $Computer
}
```

```Output
DistinguishedName : CN=DC01,OU=Domain Controllers,DC=mikefrobbins,DC=com
DNSHostName       : dc01.mikefrobbins.com
Enabled           : True
Name              : DC01
ObjectClass       : computer
ObjectGUID        : c38da20c-a484-469d-ba4c-bab3fb71ae8e
SamAccountName    : DC01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1001
UserPrincipalName :

DistinguishedName : CN=WEB01,CN=Computers,DC=mikefrobbins,DC=com
DNSHostName       : web01.mikefrobbins.com
Enabled           : True
Name              : WEB01
ObjectClass       : computer
ObjectGUID        : 33aa530e-1e31-40d8-8c78-76a18b673c33
SamAccountName    : WEB01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1107
UserPrincipalName :
```

É necessário muitas vezes um loop, como `foreach` ou `ForEach-Object`. Caso contrário, você receberá uma mensagem de erro.

```powershell
Get-ADComputer -Identity 'DC01', 'WEB01'
```

```Output
Get-ADComputer : Cannot convert 'System.Object[]' to the type
'Microsoft.ActiveDirectory.Management.ADComputer' required by parameter 'Identity'.
Specified method is not supported.
At line:1 char:26
+ Get-ADComputer -Identity 'DC01', 'WEB01'
+                          ```````````````
    + CategoryInfo          : InvalidArgument: (:) [Get-ADComputer], ParameterBindingExc
   eption
    + FullyQualifiedErrorId : CannotConvertArgument,Microsoft.ActiveDirectory.Management
   .Commands.GetADComputer
```

Em outras ocasiões, você pode obter os mesmos resultados eliminando o loop por completo. Consulte a ajuda do cmdlet para entender as opções.

```powershell
'DC01', 'WEB01' | Get-ADComputer
```

```Output
DistinguishedName : CN=DC01,OU=Domain Controllers,DC=mikefrobbins,DC=com
DNSHostName       : dc01.mikefrobbins.com
Enabled           : True
Name              : DC01
ObjectClass       : computer
ObjectGUID        : c38da20c-a484-469d-ba4c-bab3fb71ae8e
SamAccountName    : DC01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1001
UserPrincipalName :

DistinguishedName : CN=WEB01,CN=Computers,DC=mikefrobbins,DC=com
DNSHostName       : web01.mikefrobbins.com
Enabled           : True
Name              : WEB01
ObjectClass       : computer
ObjectGUID        : 33aa530e-1e31-40d8-8c78-76a18b673c33
SamAccountName    : WEB01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1107
UserPrincipalName :
```

Como você pode ver nos exemplos anteriores, o parâmetro **Identity** para `Get-ADComputer` aceita apenas um só valor quando fornecido por meio da entrada de parâmetro, mas permite vários itens quando a entrada é fornecida por meio da entrada de pipeline.

### <a name="for"></a>For (para)

Um loop `for` itera enquanto uma condição especificada é verdadeira. O loop `for` não é algo que utilizo com frequência, mas ele tem usos próprios.

```powershell
for ($i = 1; $i -lt 5; $i++) {
  Write-Output "Sleeping for $i seconds"
  Start-Sleep -Seconds $i
}
```

```Output
Sleeping for 1 seconds
Sleeping for 2 seconds
Sleeping for 3 seconds
Sleeping for 4 seconds
```

No exemplo anterior, o loop vai iterar quatro vezes começando com o número um e continuar, desde que a variável do contador `$i` seja menor que 5. Ele será suspenso por um total de dez segundos.

### <a name="do"></a>O que fazer

Há dois loops `do` diferentes no PowerShell. `Do Until` é executado enquanto a condição especificada é falsa.

```powershell
$number = Get-Random -Minimum 1 -Maximum 10
do {
  $guess = Read-Host -Prompt "What's your guess?"
  if ($guess -lt $number) {
    Write-Output 'Too low!'
  }
  elseif ($guess -gt $number) {
    Write-Output 'Too high!'
  }
}
until ($guess -eq $number)
```

```Output
What's your guess?: 1
Too low!
What's your guess?: 2
Too low!
What's your guess?: 3
```

O exemplo anterior é um jogo de números que continua até que o valor adivinhado seja igual ao mesmo número gerado pelo cmdlet `Get-Random`.

`Do While` é justamente o oposto. Ele é executado desde que a condição especificada seja avaliada como verdadeira.

```powershell
$number = Get-Random -Minimum 1 -Maximum 10
do {
  $guess = Read-Host -Prompt "What's your guess?"
  if ($guess -lt $number) {
    Write-Output 'Too low!'
  } elseif ($guess -gt $number) {
    Write-Output 'Too high!'
  }
}
while ($guess -ne $number)
```

```Output
What's your guess?: 1
Too low!
What's your guess?: 2
Too low!
What's your guess?: 3
Too low!
What's your guess?: 4
```

Os mesmos resultados são obtidos com um loop `Do While`, revertendo a condição de teste para não é igual a.

Os loops `Do` sempre são executados pelo menos uma vez porque a condição é avaliada no final do loop.

### <a name="while"></a>While

De modo semelhante ao loop `Do While`, um loop `While` é executado, desde que a condição especificada seja verdadeira. No entanto, a diferença é que um loop `While` avalia a condição na parte superior do loop antes da execução de qualquer código. Portanto, ele não é executado se a condição é avaliada como falsa.

```powershell
$date = Get-Date -Date 'November 22'
while ($date.DayOfWeek -ne 'Thursday') {
  $date = $date.AddDays(1)
}
Write-Output $date
```

```Output
Thursday, November 23, 2017 12:00:00 AM
```

O exemplo anterior calcula quando será o Dia de Ação de Graças nos Estados Unidos. Ele sempre cai na quarta quinta-feira de novembro. Portanto, o loop começa com o dia 22 de novembro e adiciona um dia enquanto o dia da semana não é igual a quinta-feira. Se o dia 22 for uma quinta-feira, o loop não será executado.

## <a name="break-continue-and-return"></a>Interromper, continuar e retornar

`Break` foi projetado para interromper um loop. Ele também é comumente usado com a instrução `switch`.

```powershell
for ($i = 1; $i -lt 5; $i++) {
  Write-Output "Sleeping for $i seconds"
  Start-Sleep -Seconds $i
  break
}
```

```Output
Sleeping for 1 seconds
```

A instrução `break` mostrada no exemplo anterior faz com que o loop saia na primeira iteração.

Continue foi projetado para ir para a próxima iteração de um loop.

```powershell
while ($i -lt 5) {
  $i += 1
  if ($i -eq 3) {
    continue
  }
  Write-Output $i
}
```

```Output
1
2
4
5
```

O exemplo anterior produzirá os números 1, 2, 4 e 5. Ele ignora o número 3 e continua com a próxima iteração do loop. De modo semelhante ao `break`, `continue` é interrompido do loop, exceto apenas para a iteração atual. A execução continua com a próxima iteração em vez de interromper o loop e parar.

Return foi projetado para sair do escopo existente.

```powershell
$number = 1..10
foreach ($n in $number) {
  if ($n -ge 4) {
    Return $n
  }
}
```

```Output
4
```

Observe que, no exemplo anterior, o retorno produz o primeiro resultado e, em seguida, sai do loop. Encontre uma explicação mais completa da instrução result em um dos meus artigos de blog: ["A palavra-chave return do PowerShell"][].

## <a name="summary"></a>Resumo

Neste capítulo, você aprendeu mais sobre os diferentes tipos de loops existentes no PowerShell.

## <a name="review"></a>Revisão

1. Qual é a diferença entre o cmdlet `ForEach-Object` e o constructo de script foreach?
1. Qual é a principal vantagem de usar um loop While em vez de um loop Do While ou Do Until?
1. Qual é diferença entre as instruções break e continue?

## <a name="recommended-reading"></a>Leitura recomendada

- [ForEach-Object][]
- [about_ForEach][]
- [about_For][]
- [about_Do][]
- [about_While][]
- [about_Break][]
- [about_Continue][]
- [about_Return][]

<!-- link references -->
[ForEach-Object]: /powershell/module/microsoft.powershell.core/foreach-object
[about_ForEach]: /powershell/module/microsoft.powershell.core/about/about_foreach
[about_For]: /powershell/module/microsoft.powershell.core/about/about_for
[about_Do]: /powershell/module/microsoft.powershell.core/about/about_do
[about_While]: /powershell/module/microsoft.powershell.core/about/about_while
[about_Break]: /powershell/module/microsoft.powershell.core/about/about_break
[about_Continue]: /powershell/module/microsoft.powershell.core/about/about_continue
[about_Return]: /powershell/module/microsoft.powershell.core/about/about_return
["A palavra-chave return do PowerShell"]: https://mikefrobbins.com/2015/07/23/the-powershell-return-keyword/
