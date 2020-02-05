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
ms.openlocfilehash: 37af16d0279b6487c78f90eb19bcfe5c152ed9e7
ms.sourcegitcommit: bc9a4904c2b1561386d748fc9ac242699d2f1694
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76996050"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a><span data-ttu-id="79140-102">Como adicionar tipos de entrada a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="79140-102">How to Add Input Types to a Cmdlet Help Topic</span></span>

<span data-ttu-id="79140-103">Esta seção descreve como adicionar uma seção de entradas a um tópico de ajuda do cmdlet® do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79140-103">This section describes how to add an INPUTS section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="79140-104">A seção de entradas lista as classes .NET de objetos que o cmdlet aceita como entrada do pipeline, seja por valor ou por nome de propriedade.</span><span class="sxs-lookup"><span data-stu-id="79140-104">The INPUTS section lists the .NET classes of objects that the cmdlet accepts as input from the pipeline, either by value or by property name.</span></span>

<span data-ttu-id="79140-105">Não há nenhum limite para o número de classes que você pode adicionar a uma seção de entradas.</span><span class="sxs-lookup"><span data-stu-id="79140-105">There is no limit to the number of classes that you can add to an INPUTS section.</span></span> <span data-ttu-id="79140-106">Os tipos de entrada são colocados em um comando \<: inputTypes > nó, com cada classe colocada em um \<comando: inputType > elemento.</span><span class="sxs-lookup"><span data-stu-id="79140-106">The input types are enclosed in a \<command:inputTypes> node, with each class enclosed in a  \<command:inputType> element.</span></span>

<span data-ttu-id="79140-107">O esquema inclui dois elementos \<maml: Description > em cada \<comando: inputType > elemento.</span><span class="sxs-lookup"><span data-stu-id="79140-107">The schema includes two \<maml:description> elements in each \<command:inputType> element.</span></span> <span data-ttu-id="79140-108">No entanto, o cmdlet `Get-Help` exibe apenas o conteúdo do elemento comando \<: inputType >/\<maml: Description >).</span><span class="sxs-lookup"><span data-stu-id="79140-108">However, the `Get-Help` cmdlet displays only the content of the \<command:inputType>/\<maml:description>) element.</span></span>

<span data-ttu-id="79140-109">A partir do Windows PowerShell 3,0, o cmdlet `Get-Help` exibe o conteúdo do elemento \<maml: URI >.</span><span class="sxs-lookup"><span data-stu-id="79140-109">Beginning in Windows PowerShell 3.0, the `Get-Help` cmdlet displays the content of the \<maml:uri> element.</span></span> <span data-ttu-id="79140-110">Esse elemento permite direcionar os usuários para tópicos que descrevem a classe .NET.</span><span class="sxs-lookup"><span data-stu-id="79140-110">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="79140-111">O XML a seguir mostra o nó \<maml: inputTypes >.</span><span class="sxs-lookup"><span data-stu-id="79140-111">The following XML shows the \<maml:inputTypes> node.</span></span>

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

<span data-ttu-id="79140-112">O XML a seguir mostra um exemplo de como usar o nó \<maml: inputTypes > para documentar um tipo de entrada.</span><span class="sxs-lookup"><span data-stu-id="79140-112">The following XML shows an example of using the \<maml:inputTypes> node to document an input type.</span></span>

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