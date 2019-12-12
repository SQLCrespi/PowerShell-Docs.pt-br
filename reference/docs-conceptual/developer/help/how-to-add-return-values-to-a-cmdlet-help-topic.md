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
ms.openlocfilehash: b21811e5a5a819c3d5c4a55fcbe685a84819b71d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367795"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a><span data-ttu-id="57af6-102">Como adicionar valores retornados a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="57af6-102">How to Add Return Values to a Cmdlet Help Topic</span></span>

<span data-ttu-id="57af6-103">Esta seção descreve como adicionar uma seção de saídas a um tópico de ajuda do cmdlet® do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57af6-103">This section describes how to add an OUTPUTS section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="57af6-104">A seção de saídas lista as classes .NET de objetos que o cmdlet retorna ou passa o pipeline.</span><span class="sxs-lookup"><span data-stu-id="57af6-104">The OUTPUTS section lists the .NET classes of objects that the cmdlet returns or passes down the pipeline.</span></span>

<span data-ttu-id="57af6-105">Não há nenhum limite para o número de classes que você pode adicionar à seção de saídas.</span><span class="sxs-lookup"><span data-stu-id="57af6-105">There is no limit to the number of classes that you can add to the OUTPUTS section.</span></span> <span data-ttu-id="57af6-106">Os tipos de retorno de um cmdlet são colocados em um \<comando: returnValues > nó, com cada classe colocada em um elemento \<Command: returnValue >.</span><span class="sxs-lookup"><span data-stu-id="57af6-106">The return types of a cmdlet are enclosed in a \<command:returnValues> node, with each class enclosed in a \<command:returnValue> element.</span></span>

<span data-ttu-id="57af6-107">Se um cmdlet não gerar nenhuma saída, use esta seção para indicar que não há nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="57af6-107">If a cmdlet does not generate any output, use this section to indicate that there is no output.</span></span> <span data-ttu-id="57af6-108">Por exemplo, no lugar do nome da classe, escreva "None" e forneça uma breve explicação.</span><span class="sxs-lookup"><span data-stu-id="57af6-108">For example, in place of the class name, write "None" and provide a brief explanation.</span></span> <span data-ttu-id="57af6-109">Se o cmdlet gerar a saída condicionalmente, use este nó para explicar as condições e descrever a saída condicional.</span><span class="sxs-lookup"><span data-stu-id="57af6-109">If the cmdlet generates output conditionally, use this node to explain the conditions and describe the conditional output.</span></span>

<span data-ttu-id="57af6-110">O esquema inclui dois elementos \<maml: Description > em cada \<comando: returnValue > elemento.</span><span class="sxs-lookup"><span data-stu-id="57af6-110">The schema includes two \<maml:description> elements in each \<command:returnValue> element.</span></span> <span data-ttu-id="57af6-111">No entanto, o cmdlet `Get-Help` exibe somente o conteúdo do comando \<: returnValue >/\<maml: Description > elemento.</span><span class="sxs-lookup"><span data-stu-id="57af6-111">However, the `Get-Help` cmdlet displays only the content of the \<command:returnValue>/\<maml:description> element.</span></span>

<span data-ttu-id="57af6-112">A partir do Windows PowerShell 3,0, o cmdlet `Get-Help` exibe o conteúdo do elemento \<maml: URI >.</span><span class="sxs-lookup"><span data-stu-id="57af6-112">Beginning in Windows PowerShell 3.0, the `Get-Help` cmdlet displays the content of the \<maml:uri> element.</span></span> <span data-ttu-id="57af6-113">Esse elemento permite direcionar os usuários para tópicos que descrevem a classe .NET.</span><span class="sxs-lookup"><span data-stu-id="57af6-113">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="57af6-114">O XML a seguir mostra o \<maml: returnValues > nó.</span><span class="sxs-lookup"><span data-stu-id="57af6-114">The following XML shows the \<maml:returnValues> node.</span></span>

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

<span data-ttu-id="57af6-115">O XML a seguir mostra um exemplo de como usar o \<maml: returnValues > nó para documentar um tipo de saída.</span><span class="sxs-lookup"><span data-stu-id="57af6-115">The following XML shows an example of using the \<maml:returnValues> node to document an output type.</span></span>

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  http://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```



