---
title: Descobrir o PowerShell
ms.date: 03/12/2021
ms.custom: chnoring
ms.reviewer: sewhee
description: Saiba o que é o PowerShell e alguns comandos essenciais usados para descobrir mais sobre o PowerShell.
ms.openlocfilehash: 34bbd465a918224c203e7243834e7fb3a3a6070c
ms.sourcegitcommit: 16a02ae47d1a85b01692101aa0aa6e91e1ba398e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104729979"
---
# <a name="discover-powershell"></a>Descobrir o PowerShell

O PowerShell é um shell de linha de comando e uma linguagem de script integrados. Ele começou no Windows. Destinava-se a ajudar com a automação de tarefas de administração, mas agora cresceu para se tornar multiplataforma e pode ser usado para uma variedade de tarefas.

A característica que faz o PowerShell ser exclusivo é que ele aceita e retorna objetos .NET, em vez de um texto.
Esse fato facilita a conexão de diferentes comandos na série, em um _pipeline_.

> [!NOTE]
> Os pipelines serão abordados mais detalhadamente nesta série de tutoriais.

Mesmo assim, talvez seja necessário _processar_ os resultados um pouco.

## <a name="what-can-powershell--be-used-for"></a>Para o que o PowerShell pode ser usado?

O uso do PowerShell aumentou desde a época em que ele era somente Windows. Ele ainda é usado para a automação de tarefas do Windows, mas hoje, você pode usá-lo para uma variedade de tarefas como:

- **Gerenciamento de nuvem**. O PowerShell pode ser usado para gerenciar recursos da nuvem. Por exemplo, você pode recuperar informações sobre recursos da nuvem, bem como atualizar ou implantar novos recursos.
- **CI/CD**. Ele também pode ser usado como parte de um pipeline de integração contínua/implantação contínua.
- **Automatizar tarefas para o Active Directory e o Exchange**. Você pode usá-lo para automatizar quase todas as tarefas do Windows, como a criação de usuários no Active Directory e as caixas de correio no Exchange.

Há muitas outras áreas de uso, mas a lista acima já indica que o PowerShell tem feito bastante sucesso.

## <a name="who-uses-powershell"></a>Quem usa o PowerShell?

O PowerShell é muito eficiente e muitas pessoas, trabalhando em diversas funções, podem se beneficiar do uso dele. Tradicionalmente, o PowerShell vem sendo usado pela função Administrador do sistema, mas já está sendo usado por pessoas que se intitulam Engenheiros de DevOps e de nuvem e, até mesmo, desenvolvedores.

## <a name="powershell-cmdlets"></a>Cmdlets do PowerShell

O PowerShell é fornecido com centenas de comandos pré-instalados. Os comandos do PowerShell são chamados de cmdlets (pronuncia-se "command-lets").

O nome de cada cmdlet consiste em um par de "verbo-substantivo"; por exemplo, `Get-Process`. Essa convenção de nomenclatura facilita o entendimento da função do cmdlet. Também facilita a localização do comando procurado. Ao procurar um cmdlet para uso, você pode filtrar pelo verbo ou pelo substantivo.

### <a name="using-cmdlets-to-explore-powershell"></a>Como usar cmdlets para explorar o PowerShell

Quando você usa o PowerShell pela primeira vez, ele pode parecer intimidador, pois parece muito difícil de aprender.
No entanto, o PowerShell foi projetado para ajudar você a aprender um pouco de cada vez, conforme a sua necessidade.

O PowerShell inclui cmdlets que ajudam você a descobri-lo. Usando estes três cmdlets, você pode descobrir quais comandos estão disponíveis, o que eles fazem e em quais tipos eles operam.

- `Get-Verb`. A execução desse comando retorna uma lista de verbos seguidos pela maioria dos comandos.
  Além disso, a resposta descreve o que esses verbos fazem. Como a maioria dos comandos segue essa nomenclatura, ela define as expectativas sobre o que um comando faz, o que ajuda você a escolher o comando apropriado, mas também como nomear um comando, caso você esteja criando um.
- `Get-Command`. Esse comando recupera uma lista de todos os comandos instalados no computador.
- `Get-Member`. Ele opera na saída baseada em objeto e pode descobrir quais objetos, propriedades e métodos estão disponíveis para um comando.
- `Get-Help`. A invocação desse comando com o nome de um comando como argumento exibe uma página de ajuda que descreve várias partes de um comando.

Usando esses comandos, você pode descobrir quase tudo do que precisa saber sobre o PowerShell.

### <a name="verb"></a>Verbo

O verbo é um conceito importante no PowerShell. É um padrão de nomenclatura seguido pela maioria dos cmdlets. Também é um padrão de nomenclatura que você deve seguir depois de escrever comandos próprios. A ideia é que o _verbo_ indica o que você está tentando fazer: ler dados ou talvez alterá-los. O PowerShell tem uma lista padronizada de verbos. Para obter uma lista completa de todos os verbos possíveis, use o cmdlet `Get-Verb`:

```powershell
Get-Verb
```

A saída da execução dele é uma longa lista de verbos. O que é informativo sobre a resposta é que ela também mostra mais contexto, o que esse verbo deve fazer. Veja a primeira linha da saída:

```output
Verb        AliasPrefix Group          Description
----        ----------- -----          -----------
Add         a           Common         Adds a resource to a container, or attaches an item to ano…
```

## <a name="find-commands-with-get-command"></a>Localizar comandos com Get-Command

O cmdlet `Get-Command` retorna uma lista de todos os comandos disponíveis instalados no sistema.
No entanto, a lista que você recebe é bem grande. Para facilitar a localização dos comandos, limite o volume de informações retornado. Você pode filtrar a resposta usando parâmetros ou cmdlets auxiliares.

### <a name="filter-on-name"></a>Filtragem por nome

Você pode filtrar a saída de `Get-Command` usando diferentes parâmetros. Esse tipo de filtragem consiste em consultar uma propriedade específica no comando. A ideia é que você especifica a propriedade para filtragem e fornece uma cadeia de caracteres para correspondência. Portanto, você obterá uma comparação semelhante a esta:

```powershell
Get-Command -Name '*Process'
```

Neste ponto, a filtragem está tentando fazer uma correspondência exata com o argumento de cadeia de caracteres fornecido.
Caso deseje ter mais flexibilidade na comparação, use um curinga `*`, que faz a correspondência de padrões. O seguinte código procura todos os comandos cujo nome termina com Process:

Acima, o parâmetro `-Name` é usado para filtragem. Além de `-Name`, você também pode fazer a filtragem por `-ParameterName` e `-Type`, por exemplo.

### <a name="filtering-on-noun-and-verb"></a>Filtragem por substantivo e verbo

Você viu como fazer a filtragem por `-Name` e descobriu que há outros parâmetros que também podem ser usados para a filtragem. Os verbos e os substantivos são algo que também podem ser usados na filtragem. Essa filtragem é direcionada a uma parte do nome de um comando.

- **Filtragem por verbo**. A parte do verbo do nome de um comando é a parte mais à esquerda. No comando `Get-Process`, a parte do verbo é `Get`. Para fazer a filtragem na parte do verbo, especifique `-Verb` como um parâmetro desta maneira:

   ```powershell
   Get-Command -Verb 'Get'
   ```

   O comando acima listará todos os comandos em que a parte do verbo é `Get`.

- **Filtragem por substantivo**. A parte mais à direita de um comando é a parte do substantivo. Enquanto o verbo deve estar entre os verbos retornados da invocação `Get-Verb`, um substantivo pode ser qualquer coisa. No comando `Get-Process`, a parte do substantivo é `Process`. Para fazer a filtragem por substantivo, especifique `-Noun` como um parâmetro e um argumento de cadeia de caracteres desta maneira:

   ```powershell
   Get-Command -Noun U*
   ```

Na filtragem, o uso apenas do verbo ou do substantivo ainda pode gerar um resultado grande. Para restringir a pesquisa, é bom combinar os dois parâmetros, como o exemplo abaixo:

```powershell
Get-Command -Verb Get -Noun U*
```

O resultado da pesquisa acima ficará parecido com este:

```output
CommandType     Name                         Version    Source
-----------     ----                         -------    ------
Cmdlet          Get-UICulture                7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Unique                   7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-Uptime                   7.0.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-UsageAggregates          2.0.0      Az.Billing
```

Assim, você limitou muito a saída sabendo o verbo e como ele é chamado.

### <a name="use-helper-cmdlets-to-filter-results"></a>Usar cmdlets auxiliares para filtrar os resultados

Além de usar parâmetros para filtragem, use também comandos para ajudar você com essa tarefa. Estes são alguns comandos que podem funcionar como filtros:

- `Select-Object`. É um comando muito versátil que ajuda você a selecionar propriedades específicas de um ou mais objetos. Além disso, com o uso de parâmetros, você pode limitar a resposta retornada. Este é um exemplo do uso de `Select-Object` para solicitar um número limitado de registros:

   ```powershell
   Get-Command | Select-Object -First 3
   ```

   O resultado da pesquisa acima são os três primeiros comandos, contados do início. O resultado será parecido com este:

   ```output
   CommandType     Name                                               Version    Source
   -----------     ----                                               -------    ------
   Alias           Add-AdlAnalyticsDataSource                         1.0.2      Az.DataLakeAnalytics
   Alias           Add-AdlAnalyticsFirewallRule                       1.0.2      Az.DataLakeAnalytics
   Alias           Add-AdlStoreFirewallRule                           1.3.0      Az.DataLakeStore
   ```

   Vale a pena examinar esse comando mais detalhadamente na [documentação de Select-Object](/powershell/module/microsoft.powershell.utility/select-object), pois ele pode fazer muitas outras coisas

- `Where-Object`. O objeto Where ajuda você a selecionar objetos de uma coleção com base nos valores das propriedades. O comando usa uma expressão na qual você pode expressar quais colunas deseja usar para a correspondência com determinados valores. Para localizar todos os objetos de processo em que o `ProcessName` começa com `p`, use `Where-Object` desta forma:

  ```powershell
  Get-Process | Where-Object {$_.ProcessName -Like "p*"}
  ```

  Acima, o cmdlet `Get-Process` produz uma coleção de objetos de processo. Para filtrar a resposta, _redirecione_ o comando `Where-Object`. O uso de um pipe significa que dois ou mais comandos são conectados por meio de um caractere de barra vertical `|`. A ideia é que a saída de um comando sirva como a entrada do próximo, lido da esquerda para a direita. O `Where-Object` usa uma expressão para filtragem. A própria expressão usa o operador `-Like` e o argumento de cadeia de caracteres que é uma expressão curinga.

## <a name="explore-objects-with-get-member"></a>Explorar objetos com Get-Member

Depois que você conseguir localizar o cmdlet desejado, o ideal será saber mais sobre o que ele produz, a saída. A saída é interessante por vários motivos, como:

- **Autônomo**. Você pode executar apenas um cmdlet e desejar exibir a saída em um tipo de relatório. A pergunta a ser feita é se o comando produz uma saída que funciona para você ou se ela precisa ser alterada.
- **Quando usado em um pipeline**. No PowerShell, é comum conectar vários comandos em um pipeline para buscar dados, filtrá-los e, por fim, transformá-los. Para que um comando se ajuste a um pipeline, você precisa examinar a entrada e a saída produzidas por ele. A ideia é que a saída de um comando seja usada como a entrada de outro.

O cmdlet `Get-Member` exibe as propriedades e os métodos do resultado. Além disso, ele mostra o tipo do objeto. Redirecione a saída que deseja inspecionar para `Get-Member`.

```powershell
Get-Process | Get-Member
```

O resultado exibe o tipo de retorno como `TypeName`, e todas as propriedades e os métodos do objeto. Veja um trecho desse resultado:

```output
TypeName: System.Diagnostics.Process

Name        MemberType     Definition
----        ----------     ----------
Handles     AliasProperty  Handles = Handlecount
Name        AliasProperty  Name = ProcessName
```

Um objeto geralmente tem muitas propriedades e métodos. Para encontrar com mais facilidade o que você está procurando, filtre os resultados. Usando o parâmetro `-MemberType`, você pode especificar, por exemplo, a visualização de todos os métodos, como no exemplo abaixo:

```powershell
Get-Process | Get-Member -MemberType Method
```

Quando você recebe uma resposta, o PowerShell geralmente exibe apenas algumas propriedades. Na resposta acima, as propriedades `Name`, `MemberType` e `Definition` foram exibidas. Para alterar essa exibição, use o cmdlet `Select-Object`. `Select-Object` permite que você especifique as colunas que deseja ver. Você pode fornecê-lo com o nome da coluna, uma lista separada por vírgula ou um curinga `*`. Veja um exemplo em que `Select-Object` é usado para recuperar `Name` e `Definition`:

```powershell
Get-Process | Get-Member | Select-Object Name, Definition
```

### <a name="search-by-type"></a>Pesquisa por tipo

Outra maneira de abordar a pesquisa do comando desejado é procurar todos os comandos que operam no mesmo tipo. Quando usou `Get-Member`, você obteve o tipo de retorno como a primeira linha da resposta, desta forma:

```output
TypeName: System.Diagnostics.Process
```

Agora você pode usar esse tipo e pesquisar comandos da seguinte maneira:

```powershell
Get-Command -ParameterType Process
```

O resultado da invocação do comando acima é uma lista com os comandos que só operam no tipo `Process`:

```output
CommandType     Name                         Version    Source
-----------     ----                         -------    ------
Cmdlet          Debug-Process                7.0.0.0    Microsoft.PowerShell.Managem…
Cmdlet          Enter-PSHostProcess          7.1.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-Process                  7.0.0.0    Microsoft.PowerShell.Managem…
Cmdlet          Get-PSHostProcessInfo        7.1.0.0    Microsoft.PowerShell.Core
Cmdlet          Stop-Process                 7.0.0.0    Microsoft.PowerShell.Managem…
Cmdlet          Wait-Process                 7.0.0.0    Microsoft.PowerShell.Managem…
```

Como você pode ver, saber o tipo de um comando pode restringir muito a sua pesquisa com os comandos que podem ser interessantes para você.

## <a name="exercise---calling-your-first-command"></a>Exercício – Como chamar seu primeiro comando

Neste exercício, você aprenderá a executar seu primeiro comando.

1. Inicie um console do PowerShell digitando `pwsh`:

   ```powershell
   pwsh
   ```

1. Execute o seguinte `$PSVersionTable.PSVersion`:

   ```powershell
   $PSVersionTable.PSVersion
   ```

   A saída será parecida com esta:

   ```output
   Major  Minor  Patch  PreReleaseLabel BuildLabel
   -----  -----  -----  --------------- ----------
   7      1      0
   ```

   Parabéns! Você executou com êxito seu primeiro comando e conseguiu obter informações sobre a versão do PowerShell instalada no sistema.

## <a name="exercise---find-related-commands"></a>Exercício – Localizar comandos relacionados

Neste exercício, sua meta é aprender mais sobre um comando. Ao fazer isso, você também encontrará informações como em que tipo ele opera e quais outros comandos semelhantes operam no mesmo tipo.

1. Verifique se você tem um shell do PowerShell iniciado
1. Execute o comando `Get-Process`:

   ```powershell
   Get-Process | Get-Member | Select-Object TypeName -Unique
   ```

   A saída será semelhante a esta:

   ```output
   TypeName
   --------
   System.Diagnostics.Process
   --------
   ```

   O que você recebe são os tipos retornados pelo comando `Get-Command`. Neste ponto, agora você pode descobrir qual outro comando também opera nesses tipos.

1. Execute o comando `Get-Command`:

   ```powershell
   Get-Command -ParameterType Process
   ```

   A saída será semelhante a esta:

   ```output
   CommandType     Name                         Version    Source
    -----------     ----                        -------    ------
    Cmdlet          Debug-Process               7.0.0.0    Microsoft.PowerShell.Managem…
    Cmdlet          Enter-PSHostProcess         7.1.0.0    Microsoft.PowerShell.Core
    Cmdlet          Get-Process                 7.0.0.0    Microsoft.PowerShell.Managem…
    Cmdlet          Get-PSHostProcessInfo       7.1.0.0    Microsoft.PowerShell.Core
    Cmdlet          Stop-Process                7.0.0.0    Microsoft.PowerShell.Managem…
    Cmdlet          Wait-Process                7.0.0.0    Microsoft.PowerShell.Managem…
   ```

   Parabéns! Você conseguiu encontrar outros comandos que operam no mesmo tipo `Process`.
   O uso de `Get-Member` é um bom ponto de partida para entender quais outros comandos você deve conferir em seguida.

## <a name="summary"></a>Resumo

Nesta primeira parte, você aprendeu o que é o PowerShell e em quais áreas ele pode ser usado. Depois, você aprendeu sobre os cmdlets, em particular, sobre `Get-Command`, `Get-Verb` e `Get-Member`. Saber esses cmdlets é importante, pois eles ensinam você a como aprender. Na próxima parte, você aprenderá a usar o eficiente sistema de ajuda.

### <a name="additional-resources"></a>Recursos adicionais

- [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command)
- [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)
