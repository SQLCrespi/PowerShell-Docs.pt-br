---
ms.date: 09/12/2016
ms.topic: reference
title: Como adicionar valores retornados a um tópico de ajuda do cmdlet
description: Como adicionar valores retornados a um tópico de ajuda do cmdlet
ms.openlocfilehash: 8c556821a257451a320916231cb20fc82e75ebb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "94389735"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a>Como adicionar valores retornados a um tópico de ajuda do cmdlet

Esta seção descreve como adicionar uma seção de saídas a um tópico de ajuda do cmdlet do PowerShell. A seção de **saídas** lista as classes .net de objetos que o cmdlet retorna ou passa o pipeline.

Não há nenhum limite para o número de classes que você pode adicionar à seção de **saídas** . Os tipos de retorno de um cmdlet são colocados em um `<command:returnValues>` nó, com cada classe colocada em um `<command:returnValue>` elemento.

Se um cmdlet não gerar nenhuma saída, use esta seção para indicar que não há nenhuma saída. Por exemplo, no lugar do nome da classe, escreva **nenhum** e forneça uma breve explicação. Se o cmdlet gerar a saída condicionalmente, use este nó para explicar as condições e descrever a saída condicional.

O esquema inclui dois `<maml:description>` elementos em cada `<command:returnValue>` elemento.
No entanto, o `Get-Help` cmdlet exibe apenas o conteúdo do `<command:returnValue>/<maml:description>` elemento.

A partir do PowerShell 3,0, o `Get-Help` cmdlet exibe o conteúdo do `<maml:uri>` elemento.
Esse elemento permite direcionar os usuários para tópicos que descrevem a classe .NET.

O XML a seguir mostra o `<maml:returnValues>` nó.

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

O XML a seguir mostra um exemplo de como usar o `<maml:returnValues>` nó para documentar um tipo de saída.

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://docs.microsoft.com/dotnet/api/system.datetime </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```
