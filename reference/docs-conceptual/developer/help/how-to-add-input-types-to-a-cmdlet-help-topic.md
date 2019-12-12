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
ms.openlocfilehash: f213605dda0132051d983f8608515325e815c455
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361235"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a>Como adicionar tipos de entrada a um tópico de ajuda do cmdlet

Esta seção descreve como adicionar uma seção de entradas a um tópico de ajuda do cmdlet® do Windows PowerShell. A seção de entradas lista as classes .NET de objetos que o cmdlet aceita como entrada do pipeline, seja por valor ou por nome de propriedade.

Não há nenhum limite para o número de classes que você pode adicionar a uma seção de entradas. Os tipos de entrada são colocados em um comando \<: inputTypes > nó, com cada classe colocada em um \<comando: inputType > elemento.

O esquema inclui dois elementos \<maml: Description > em cada \<comando: inputType > elemento. No entanto, o cmdlet `Get-Help` exibe apenas o conteúdo do elemento comando \<: inputType >/\<maml: Description >).

A partir do Windows PowerShell 3,0, o cmdlet `Get-Help` exibe o conteúdo do elemento \<maml: URI >. Esse elemento permite direcionar os usuários para tópicos que descrevem a classe .NET.

O XML a seguir mostra o nó \<maml: inputTypes >.

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

O XML a seguir mostra um exemplo de como usar o nó \<maml: inputTypes > para documentar um tipo de entrada.

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  http://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```