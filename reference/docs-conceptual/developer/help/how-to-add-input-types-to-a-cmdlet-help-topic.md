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
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a><span data-ttu-id="8f74f-102">Como adicionar tipos de entrada a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="8f74f-102">How to Add Input Types to a Cmdlet Help Topic</span></span>

<span data-ttu-id="8f74f-103">Esta seção descreve como adicionar uma seção de **entradas** a um tópico de ajuda do cmdlet do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f74f-103">This section describes how to add an **INPUTS** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="8f74f-104">A seção de **entradas** lista as classes .net de objetos que o cmdlet aceita como entrada do pipeline, seja por valor ou por nome de propriedade.</span><span class="sxs-lookup"><span data-stu-id="8f74f-104">The **INPUTS** section lists the .NET classes of objects that the cmdlet accepts as input from the pipeline, either by value or by property name.</span></span>

<span data-ttu-id="8f74f-105">Não há nenhum limite para o número de classes que você pode adicionar a uma seção de **entradas** .</span><span class="sxs-lookup"><span data-stu-id="8f74f-105">There is no limit to the number of classes that you can add to an **INPUTS** section.</span></span> <span data-ttu-id="8f74f-106">Os tipos de entrada são colocados em um `<command:inputTypes>` nó, com cada classe colocada em um `<command:inputType>` elemento.</span><span class="sxs-lookup"><span data-stu-id="8f74f-106">The input types are enclosed in a `<command:inputTypes>` node, with each class enclosed in a `<command:inputType>` element.</span></span>

<span data-ttu-id="8f74f-107">O esquema inclui dois `<maml:description>` elementos em cada `<command:inputType>` elemento.</span><span class="sxs-lookup"><span data-stu-id="8f74f-107">The schema includes two `<maml:description>` elements in each `<command:inputType>` element.</span></span>
<span data-ttu-id="8f74f-108">No entanto, o `Get-Help` cmdlet exibe apenas o conteúdo do `<command:inputType>/<maml:description>` elemento.</span><span class="sxs-lookup"><span data-stu-id="8f74f-108">However, the `Get-Help` cmdlet displays only the content of the `<command:inputType>/<maml:description>` element.</span></span>

<span data-ttu-id="8f74f-109">A partir do PowerShell 3,0, o `Get-Help` cmdlet exibe o conteúdo do `<maml:uri>` elemento.</span><span class="sxs-lookup"><span data-stu-id="8f74f-109">Beginning in PowerShell 3.0, the `Get-Help` cmdlet displays the content of the `<maml:uri>` element.</span></span>
<span data-ttu-id="8f74f-110">Esse elemento permite direcionar os usuários para tópicos que descrevem a classe .NET.</span><span class="sxs-lookup"><span data-stu-id="8f74f-110">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="8f74f-111">O XML a seguir mostra o `<maml:inputTypes>` nó.</span><span class="sxs-lookup"><span data-stu-id="8f74f-111">The following XML shows the `<maml:inputTypes>` node.</span></span>

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

<span data-ttu-id="8f74f-112">O XML a seguir mostra um exemplo de como usar o `<maml:inputTypes>` nó para documentar um tipo de entrada.</span><span class="sxs-lookup"><span data-stu-id="8f74f-112">The following XML shows an example of using the `<maml:inputTypes>` node to document an input type.</span></span>

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
