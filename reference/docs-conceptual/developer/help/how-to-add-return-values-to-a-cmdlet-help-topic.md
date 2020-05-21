---
title: Como adicionar valores de retorno a um tópico de ajuda de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a52ab737-753c-4d04-8af7-758d5c805e18
caps.latest.revision: 7
ms.openlocfilehash: a5618b72827d8ef70201437c4a99ea8bf68cdfd3
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83565536"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a>Como adicionar valores retornados a um tópico de ajuda do cmdlet

Esta seção descreve como adicionar uma seção de saídas a um tópico de ajuda do cmdlet® do Windows PowerShell. A seção de saídas lista as classes .NET de objetos que o cmdlet retorna ou passa o pipeline.

Não há nenhum limite para o número de classes que você pode adicionar à seção de saídas. Os tipos de retorno de um cmdlet são colocados em um \< comando: returnvalues> nó, com cada classe colocada em um \< elemento Command: ReturnValue>.

Se um cmdlet não gerar nenhuma saída, use esta seção para indicar que não há nenhuma saída. Por exemplo, no lugar do nome da classe, escreva "None" e forneça uma breve explicação. Se o cmdlet gerar a saída condicionalmente, use este nó para explicar as condições e descrever a saída condicional.

O esquema inclui dois \< elementos maml: description> em cada \< comando: ReturnValue> elemento. No entanto, o `Get-Help` cmdlet exibe somente o conteúdo do \< comando: ReturnValue>/ \< maml: Description> elemento.

A partir do Windows PowerShell 3,0, o `Get-Help` cmdlet exibe o conteúdo do \< elemento maml: URI>. Esse elemento permite direcionar os usuários para tópicos que descrevem a classe .NET.

O XML a seguir mostra o \< nó maml: returnvalues>.

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> Class Name </maml:name>
      <maml:uri>  URI of a topic that describes the class </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
       <maml:para> Brief description <maml:para>

</maml:description>
  </command: returnValue>
</command: returnValues>
```

O XML a seguir mostra um exemplo de como usar o \< nó maml: returnvalues> para documentar um tipo de saída.

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```
