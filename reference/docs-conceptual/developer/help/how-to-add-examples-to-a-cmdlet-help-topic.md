---
ms.date: 09/12/2016
ms.topic: reference
title: Como adicionar exemplos a um tópico de ajuda do cmdlet
description: Como adicionar exemplos a um tópico de ajuda do cmdlet
ms.openlocfilehash: 6b72e29c93740b7953d9b68fc8e68c02eb2f4dee
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654727"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a>Como adicionar exemplos a um tópico de ajuda do cmdlet

## <a name="things-to-know-about-examples-in-cmdlet-help"></a>Coisas que você precisa saber sobre exemplos na ajuda do cmdlet

- Lista todos os nomes de parâmetro no comando, mesmo quando os nomes de parâmetro são opcionais. Isso ajuda o usuário a interpretar o comando facilmente.

- Evite aliases e nomes de parâmetros parciais, embora eles funcionem no PowerShell.

- Na descrição do exemplo, explique o racional da construção do comando. Explique por que você escolheu parâmetros e valores específicos e como você usa variáveis.

- Se o comando usar expressões, explique-as em detalhes.

- Se o comando usar propriedades e métodos de objetos, especialmente propriedades que não aparecem na exibição padrão, use o exemplo como uma oportunidade para informar ao usuário sobre o objeto.

## <a name="help-views-that-display-examples"></a>Exibições de ajuda que exibem exemplos

Os exemplos aparecem apenas nas exibições detalhadas e completas da ajuda do cmdlet.

## <a name="adding-an-examples-node"></a>Adicionando um nó de exemplos

O XML a seguir mostra como adicionar um nó de **exemplos** que contém um único nó de **exemplo** . Adicione nós de exemplo adicionais para cada um dos exemplos que você deseja incluir no tópico.

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a>Adicionando um título de exemplo

O XML a seguir mostra como adicionar um **título** para o exemplo. O **título** é usado para definir o exemplo de separação de outros exemplos. O PowerShell usa um cabeçalho padrão que inclui um número de exemplo sequencial.

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a>Adicionando caracteres precedentes

O XML a seguir mostra como adicionar caracteres, como o prompt do Windows PowerShell, que são exibidos imediatamente antes do comando de exemplo (sem nenhum espaço intermediário). O PowerShell usa o prompt do Windows PowerShell: `C:\PS>` .

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
</command:example>
</command:examples>
```

## <a name="adding-the-command"></a>Adicionando o comando

O XML a seguir mostra como adicionar o comando real do exemplo. Ao adicionar o comando, digite o nome completo (não use alias) de cmdlets e parâmetros. Além disso, use caracteres minúsculos sempre que possível.

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
</command:example>
</command:examples>
```

## <a name="adding-a-description"></a>Adicionando uma descrição

O XML a seguir mostra como adicionar uma descrição para o exemplo. O PowerShell usa um único conjunto de `<maml:para>` marcas para a descrição, embora várias `<maml:para>` marcas possam ser usadas.

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
    <dev:remarks>
      <maml:para> command description </maml:para>
    </dev:remarks>
</command:example>
</command:examples>
```

## <a name="adding-example-output"></a>Adicionando saída de exemplo

O XML a seguir mostra como adicionar a saída do comando. As informações dos resultados do comando são opcionais, mas, em alguns casos, é útil demonstrar o efeito de usar parâmetros específicos.
O PowerShell usa dois conjuntos de `<maml:para>` marcas em branco para separar a saída do comando do comando.

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
    <dev:remarks>
      <maml:para> command description </maml:para>
      <maml:para></maml:para>
      <maml:para></maml:para>
      <maml:para> command output </maml:para>
</dev:remarks>
</command:example>
</command:examples>
```
