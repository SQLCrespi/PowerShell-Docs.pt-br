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
ms.openlocfilehash: ad0fe5c63b145c681f14328d5ef5a8784a035e26
ms.sourcegitcommit: bc9a4904c2b1561386d748fc9ac242699d2f1694
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76995943"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a>Como adicionar valores retornados a um tópico de ajuda do cmdlet

Esta seção descreve como adicionar uma seção de saídas a um tópico de ajuda do cmdlet® do Windows PowerShell. A seção de saídas lista as classes .NET de objetos que o cmdlet retorna ou passa o pipeline.

Não há nenhum limite para o número de classes que você pode adicionar à seção de saídas. Os tipos de retorno de um cmdlet são colocados em um \<comando: returnValues > nó, com cada classe colocada em um elemento \<Command: returnValue >.

Se um cmdlet não gerar nenhuma saída, use esta seção para indicar que não há nenhuma saída. Por exemplo, no lugar do nome da classe, escreva "None" e forneça uma breve explicação. Se o cmdlet gerar a saída condicionalmente, use este nó para explicar as condições e descrever a saída condicional.

O esquema inclui dois elementos \<maml: Description > em cada \<comando: returnValue > elemento. No entanto, o cmdlet `Get-Help` exibe somente o conteúdo do comando \<: returnValue >/\<maml: Description > elemento.

A partir do Windows PowerShell 3,0, o cmdlet `Get-Help` exibe o conteúdo do elemento \<maml: URI >. Esse elemento permite direcionar os usuários para tópicos que descrevem a classe .NET.

O XML a seguir mostra o \<maml: returnValues > nó.

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

O XML a seguir mostra um exemplo de como usar o \<maml: returnValues > nó para documentar um tipo de saída.

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



