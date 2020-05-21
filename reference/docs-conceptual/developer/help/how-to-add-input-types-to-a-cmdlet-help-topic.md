---
title: Como adicionar tipos de entrada a um tópico de ajuda de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 432798e4-5d69-46b1-9517-ff09bffaa4be
caps.latest.revision: 7
ms.openlocfilehash: 58b908be3149376547b075320b021421351b881e
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557049"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a>Como adicionar tipos de entrada a um tópico de ajuda do cmdlet

Esta seção descreve como adicionar uma seção de entradas a um tópico de ajuda do cmdlet® do Windows PowerShell. A seção de entradas lista as classes .NET de objetos que o cmdlet aceita como entrada do pipeline, seja por valor ou por nome de propriedade.

Não há nenhum limite para o número de classes que você pode adicionar a uma seção de entradas. Os tipos de entrada são colocados em um \< comando: inputTypes> nó, com cada classe colocada em um \< elemento Command: InputType>.

O esquema inclui dois \< elementos maml: description> em cada \< comando: InputType> elemento. No entanto, o `Get-Help` cmdlet exibe apenas o conteúdo do \< elemento comando: InputType>/ \< maml: Description>).

A partir do Windows PowerShell 3,0, o `Get-Help` cmdlet exibe o conteúdo do \< elemento maml: URI>. Esse elemento permite direcionar os usuários para tópicos que descrevem a classe .NET.

O XML a seguir mostra o \< nó maml: inputTypes>.

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

O XML a seguir mostra um exemplo de como usar o \< nó maml: inputTypes> para documentar um tipo de entrada.

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
