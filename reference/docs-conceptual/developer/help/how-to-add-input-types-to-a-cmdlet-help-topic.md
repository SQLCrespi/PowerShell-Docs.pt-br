---
ms.date: 09/12/2016
ms.topic: reference
title: Como adicionar tipos de entrada a um tópico de ajuda do cmdlet
description: Como adicionar tipos de entrada a um tópico de ajuda do cmdlet
ms.openlocfilehash: f2ad87c54230bcdd7e0ea708e9a1869daef7495f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "94391095"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a><span data-ttu-id="3274c-103">Como adicionar tipos de entrada a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="3274c-103">How to Add Input Types to a Cmdlet Help Topic</span></span>

<span data-ttu-id="3274c-104">Esta seção descreve como adicionar uma seção de **entradas** a um tópico de ajuda do cmdlet do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3274c-104">This section describes how to add an **INPUTS** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="3274c-105">A seção de **entradas** lista as classes .net de objetos que o cmdlet aceita como entrada do pipeline, seja por valor ou por nome de propriedade.</span><span class="sxs-lookup"><span data-stu-id="3274c-105">The **INPUTS** section lists the .NET classes of objects that the cmdlet accepts as input from the pipeline, either by value or by property name.</span></span>

<span data-ttu-id="3274c-106">Não há nenhum limite para o número de classes que você pode adicionar a uma seção de **entradas** .</span><span class="sxs-lookup"><span data-stu-id="3274c-106">There is no limit to the number of classes that you can add to an **INPUTS** section.</span></span> <span data-ttu-id="3274c-107">Os tipos de entrada são colocados em um `<command:inputTypes>` nó, com cada classe colocada em um `<command:inputType>` elemento.</span><span class="sxs-lookup"><span data-stu-id="3274c-107">The input types are enclosed in a `<command:inputTypes>` node, with each class enclosed in a `<command:inputType>` element.</span></span>

<span data-ttu-id="3274c-108">O esquema inclui dois `<maml:description>` elementos em cada `<command:inputType>` elemento.</span><span class="sxs-lookup"><span data-stu-id="3274c-108">The schema includes two `<maml:description>` elements in each `<command:inputType>` element.</span></span>
<span data-ttu-id="3274c-109">No entanto, o `Get-Help` cmdlet exibe apenas o conteúdo do `<command:inputType>/<maml:description>` elemento.</span><span class="sxs-lookup"><span data-stu-id="3274c-109">However, the `Get-Help` cmdlet displays only the content of the `<command:inputType>/<maml:description>` element.</span></span>

<span data-ttu-id="3274c-110">A partir do PowerShell 3,0, o `Get-Help` cmdlet exibe o conteúdo do `<maml:uri>` elemento.</span><span class="sxs-lookup"><span data-stu-id="3274c-110">Beginning in PowerShell 3.0, the `Get-Help` cmdlet displays the content of the `<maml:uri>` element.</span></span>
<span data-ttu-id="3274c-111">Esse elemento permite direcionar os usuários para tópicos que descrevem a classe .NET.</span><span class="sxs-lookup"><span data-stu-id="3274c-111">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="3274c-112">O XML a seguir mostra o `<maml:inputTypes>` nó.</span><span class="sxs-lookup"><span data-stu-id="3274c-112">The following XML shows the `<maml:inputTypes>` node.</span></span>

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

<span data-ttu-id="3274c-113">O XML a seguir mostra um exemplo de como usar o `<maml:inputTypes>` nó para documentar um tipo de entrada.</span><span class="sxs-lookup"><span data-stu-id="3274c-113">The following XML shows an example of using the `<maml:inputTypes>` node to document an input type.</span></span>

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name>System.DateTime</maml:name>
      <maml:uri>https://docs.microsoft.com/dotnet/api/system.datetime</maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```
