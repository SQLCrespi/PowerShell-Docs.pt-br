---
title: Como adicionar exemplos para um tópico de ajuda | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f723b21-8f95-4981-8b6e-4f07c22d601a
caps.latest.revision: 5
ms.openlocfilehash: b6f8aef76a5f4b5dc1a60425541856ead9a9c77a
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855122"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a>Como adicionar exemplos a um tópico de ajuda do cmdlet

## <a name="things-to-know-about-examples-in-cmdlet-help"></a>É importante saber sobre exemplos na Ajuda do Cmdlet

- Liste todos os nomes de parâmetro no comando, mesmo quando os nomes de parâmetro são opcionais. Isso ajuda o usuário a interpretar o comando com facilidade.

- Evite aliases e nomes de parâmetros parcial, mesmo que eles funcionem em Windows PowerShell®.

- Na descrição do exemplo, explique racional para a construção do comando. Explique por que você escolheu determinado parâmetros e valores, e como você pode usar variáveis.

- Se o comando usa expressões, explicaremos em detalhes.

- Se o comando usa as propriedades e métodos dos objetos, especialmente as propriedades que não aparecem na exibição padrão, use o exemplo de como uma oportunidade de informar ao usuário sobre o objeto.

## <a name="help-views-that-display-examples"></a>Exibições de Ajuda que exibem exemplos

Exemplos aparecem somente nas exibições detalhadas e completo de Ajuda do cmdlet.

## <a name="adding-an-examples-node"></a>Adicionando um nó de exemplos

O XML a seguir mostra como adicionar um nó de exemplos que contém um único nó de exemplo. Adicione nós adicionais de exemplo para cada exemplos que você deseja incluir no tópico.

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a>Adicionar um título de exemplo

O XML a seguir mostra como adicionar um título para o exemplo. O título é usado para definir o exemplo além dos outros exemplos. Windows PowerShell® usa um cabeçalho padrão que inclui um número sequencial de exemplo.

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a>Adição de caracteres que os precedem

O XML a seguir mostra como adicionar caracteres, como o prompt do Windows PowerShell, que são exibidos imediatamente antes do comando de exemplo (sem espaços intermediários). Windows PowerShell® usa o prompt do Windows PowerShell: C:\PS>.

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

O XML a seguir mostra como adicionar o comando real do exemplo. Ao adicionar o comando, digite o nome inteiro (não use alias) dos cmdlets e parâmetros. Além disso, use caracteres minúsculos sempre que possível.

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

O XML a seguir mostra como adicionar uma descrição para o exemplo. Windows PowerShell® usa um único conjunto de \<MAML: para > marcas para a descrição, mesmo que vários \<MAML: para > marcas podem ser usadas.

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

## <a name="adding-example-output"></a>Adicionando a saída de exemplo

O XML a seguir mostra como adicionar a saída do comando. As informações de resultados do comando são opcionais, mas em alguns casos, é útil para demonstrar o efeito do uso de parâmetros específicos. Windows PowerShell® usa dois conjuntos de espaço em branco \<MAML: para > marcas para separar a saída do comando do comando.

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