---
title: Como adicionar tipos de entrada a um tópico de ajuda do cmdlet
ms.date: 09/12/2016
ms.openlocfilehash: d41c49ff48cf361c2ba694d11576e84a9367eef5
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893417"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a>Como adicionar tipos de entrada a um tópico de ajuda do cmdlet

Esta seção descreve como adicionar uma seção de **entradas** a um tópico de ajuda do cmdlet do PowerShell. A seção de **entradas** lista as classes .net de objetos que o cmdlet aceita como entrada do pipeline, seja por valor ou por nome de propriedade.

Não há nenhum limite para o número de classes que você pode adicionar a uma seção de **entradas** . Os tipos de entrada são colocados em um `<command:inputTypes>` nó, com cada classe colocada em um `<command:inputType>` elemento.

O esquema inclui dois `<maml:description>` elementos em cada `<command:inputType>` elemento.
No entanto, o `Get-Help` cmdlet exibe apenas o conteúdo do `<command:inputType>/<maml:description>` elemento.

A partir do PowerShell 3,0, o `Get-Help` cmdlet exibe o conteúdo do `<maml:uri>` elemento.
Esse elemento permite direcionar os usuários para tópicos que descrevem a classe .NET.

O XML a seguir mostra o `<maml:inputTypes>` nó.

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> Class name </maml:name>
      <maml:uri>  URI of a topic that describes the class </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Brief description </maml:para>
    </maml:description>
  </command:inputType>
</command:inputTypes>
```

O XML a seguir mostra um exemplo de como usar o `<maml:inputTypes>` nó para documentar um tipo de entrada.

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```
