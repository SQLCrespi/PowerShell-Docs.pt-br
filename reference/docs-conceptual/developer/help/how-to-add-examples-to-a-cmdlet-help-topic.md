---
title: Como adicionar exemplos a um tópico de ajuda de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f723b21-8f95-4981-8b6e-4f07c22d601a
caps.latest.revision: 5
ms.openlocfilehash: b6f8aef76a5f4b5dc1a60425541856ead9a9c77a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368105"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a>Como adicionar exemplos a um tópico de ajuda do cmdlet

## <a name="things-to-know-about-examples-in-cmdlet-help"></a>Coisas que você precisa saber sobre exemplos na ajuda do cmdlet

- Lista todos os nomes de parâmetro no comando, mesmo quando os nomes de parâmetro são opcionais. Isso ajuda o usuário a interpretar o comando facilmente.

- Evite aliases e nomes de parâmetros parciais, embora eles funcionem no Windows PowerShell®.

- Na descrição do exemplo, explique o racional da construção do comando. Explique por que você escolheu parâmetros e valores específicos e como você usa variáveis.

- Se o comando usar expressões, explique-as em detalhes.

- Se o comando usar propriedades e métodos de objetos, especialmente propriedades que não aparecem na exibição padrão, use o exemplo como uma oportunidade para informar ao usuário sobre o objeto.

## <a name="help-views-that-display-examples"></a>Exibições de ajuda que exibem exemplos

Os exemplos aparecem apenas nas exibições detalhadas e completas da ajuda do cmdlet.

## <a name="adding-an-examples-node"></a>Adicionando um nó de exemplos

O XML a seguir mostra como adicionar um nó de exemplos que contém um único nó de exemplo. Adicione nós de exemplo adicionais para cada um dos exemplos que você deseja incluir no tópico.

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a>Adicionando um título de exemplo

O XML a seguir mostra como adicionar um título para o exemplo. O título é usado para definir o exemplo de separação de outros exemplos. O Windows PowerShell® usa um cabeçalho padrão que inclui um número de exemplo sequencial.

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a>Adicionando caracteres precedentes

O XML a seguir mostra como adicionar caracteres, como o prompt do Windows PowerShell, que são exibidos imediatamente antes do comando de exemplo (sem nenhum espaço intermediário). O Windows PowerShell® usa o prompt do Windows PowerShell: C:\PS >.

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

O XML a seguir mostra como adicionar uma descrição para o exemplo. O Windows PowerShell® usa um único conjunto de marcas \<maml: para > para a descrição, mesmo que várias marcas \<maml: para > possam ser usadas.

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

O XML a seguir mostra como adicionar a saída do comando. As informações dos resultados do comando são opcionais, mas, em alguns casos, é útil demonstrar o efeito de usar parâmetros específicos. O Windows PowerShell® usa dois conjuntos de marcas em branco \<maml: para > para separar a saída do comando do comando.

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