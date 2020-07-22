---
title: Como adicionar valores retornados a um tópico de ajuda do cmdlet
ms.date: 09/12/2016
ms.openlocfilehash: c164556cd06b332d04857987360c98f740a150b5
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893349"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a><span data-ttu-id="ca308-102">Como adicionar valores retornados a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="ca308-102">How to Add Return Values to a Cmdlet Help Topic</span></span>

<span data-ttu-id="ca308-103">Esta seção descreve como adicionar uma seção de saídas a um tópico de ajuda do cmdlet do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca308-103">This section describes how to add an OUTPUTS section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="ca308-104">A seção de **saídas** lista as classes .net de objetos que o cmdlet retorna ou passa o pipeline.</span><span class="sxs-lookup"><span data-stu-id="ca308-104">The **OUTPUTS** section lists the .NET classes of objects that the cmdlet returns or passes down the pipeline.</span></span>

<span data-ttu-id="ca308-105">Não há nenhum limite para o número de classes que você pode adicionar à seção de **saídas** .</span><span class="sxs-lookup"><span data-stu-id="ca308-105">There is no limit to the number of classes that you can add to the **OUTPUTS** section.</span></span> <span data-ttu-id="ca308-106">Os tipos de retorno de um cmdlet são colocados em um `<command:returnValues>` nó, com cada classe colocada em um `<command:returnValue>` elemento.</span><span class="sxs-lookup"><span data-stu-id="ca308-106">The return types of a cmdlet are enclosed in a `<command:returnValues>` node, with each class enclosed in a `<command:returnValue>` element.</span></span>

<span data-ttu-id="ca308-107">Se um cmdlet não gerar nenhuma saída, use esta seção para indicar que não há nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="ca308-107">If a cmdlet does not generate any output, use this section to indicate that there is no output.</span></span> <span data-ttu-id="ca308-108">Por exemplo, no lugar do nome da classe, escreva **nenhum** e forneça uma breve explicação.</span><span class="sxs-lookup"><span data-stu-id="ca308-108">For example, in place of the class name, write **None** and provide a brief explanation.</span></span> <span data-ttu-id="ca308-109">Se o cmdlet gerar a saída condicionalmente, use este nó para explicar as condições e descrever a saída condicional.</span><span class="sxs-lookup"><span data-stu-id="ca308-109">If the cmdlet generates output conditionally, use this node to explain the conditions and describe the conditional output.</span></span>

<span data-ttu-id="ca308-110">O esquema inclui dois `<maml:description>` elementos em cada `<command:returnValue>` elemento.</span><span class="sxs-lookup"><span data-stu-id="ca308-110">The schema includes two `<maml:description>` elements in each `<command:returnValue>` element.</span></span>
<span data-ttu-id="ca308-111">No entanto, o `Get-Help` cmdlet exibe apenas o conteúdo do `<command:returnValue>/<maml:description>` elemento.</span><span class="sxs-lookup"><span data-stu-id="ca308-111">However, the `Get-Help` cmdlet displays only the content of the `<command:returnValue>/<maml:description>` element.</span></span>

<span data-ttu-id="ca308-112">A partir do PowerShell 3,0, o `Get-Help` cmdlet exibe o conteúdo do `<maml:uri>` elemento.</span><span class="sxs-lookup"><span data-stu-id="ca308-112">Beginning in PowerShell 3.0, the `Get-Help` cmdlet displays the content of the `<maml:uri>` element.</span></span>
<span data-ttu-id="ca308-113">Esse elemento permite direcionar os usuários para tópicos que descrevem a classe .NET.</span><span class="sxs-lookup"><span data-stu-id="ca308-113">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="ca308-114">O XML a seguir mostra o `<maml:returnValues>` nó.</span><span class="sxs-lookup"><span data-stu-id="ca308-114">The following XML shows the `<maml:returnValues>` node.</span></span>

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

<span data-ttu-id="ca308-115">O XML a seguir mostra um exemplo de como usar o `<maml:returnValues>` nó para documentar um tipo de saída.</span><span class="sxs-lookup"><span data-stu-id="ca308-115">The following XML shows an example of using the `<maml:returnValues>` node to document an output type.</span></span>

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
