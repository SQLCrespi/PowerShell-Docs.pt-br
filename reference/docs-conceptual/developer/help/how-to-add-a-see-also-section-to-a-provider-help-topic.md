---
title: Como adicionar uma seção Consulte também a um tópico de ajuda do provedor | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c754ac3-cee3-4c13-9bad-e499c8a68a09
caps.latest.revision: 4
ms.openlocfilehash: 1c1b7f4cf56ea2f9e30438a60e7bee29d87b80ba
ms.sourcegitcommit: bc9a4904c2b1561386d748fc9ac242699d2f1694
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76995947"
---
# <a name="how-to-add-a-see-also-section-to-a-provider-help-topic"></a><span data-ttu-id="ceeef-102">Como adicionar uma seção “veja também” a um tópico de ajuda do provedor</span><span class="sxs-lookup"><span data-stu-id="ceeef-102">How to Add a See Also Section to a Provider Help Topic</span></span>

<span data-ttu-id="ceeef-103">Esta seção explica como preencher a seção **Consulte também** de um tópico de ajuda do provedor.</span><span class="sxs-lookup"><span data-stu-id="ceeef-103">This section explains how to populate the **SEE ALSO** section of a provider help topic.</span></span>

<span data-ttu-id="ceeef-104">A seção **Consulte também** consiste em uma lista de tópicos relacionados ao provedor ou pode ajudar o usuário a entender melhor e usar o provedor.</span><span class="sxs-lookup"><span data-stu-id="ceeef-104">The **SEE ALSO** section consists of a list of topics that are related to the provider or might help the user better understand and use the provider.</span></span> <span data-ttu-id="ceeef-105">A lista de tópicos pode incluir a ajuda do cmdlet, a ajuda do provedor e os tópicos de ajuda conceitual ("sobre") no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ceeef-105">The topic list can include cmdlet help, provider help and conceptual ("about") help topics in Windows PowerShell.</span></span> <span data-ttu-id="ceeef-106">Ele também pode incluir referências a livros, documentos e tópicos online, incluindo uma versão online do tópico de ajuda do provedor atual.</span><span class="sxs-lookup"><span data-stu-id="ceeef-106">It can also include references to books, paper, and online topics, including an online version of the current provider help topic.</span></span>

<span data-ttu-id="ceeef-107">Quando você se referir a tópicos online, forneça o URI ou um termo de pesquisa em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="ceeef-107">When you refer to online topics, provide the URI or a search term in plain text.</span></span> <span data-ttu-id="ceeef-108">O cmdlet `Get-Help` não é vinculado ou Redirecionado a nenhum dos tópicos na lista.</span><span class="sxs-lookup"><span data-stu-id="ceeef-108">The `Get-Help` cmdlet does not link or redirect to any of the topics in the list.</span></span> <span data-ttu-id="ceeef-109">Além disso, o parâmetro `Online` do cmdlet `Get-Help` não funciona com a ajuda do provedor.</span><span class="sxs-lookup"><span data-stu-id="ceeef-109">Also, the `Online` parameter of the `Get-Help` cmdlet does not work with provider help.</span></span>

<span data-ttu-id="ceeef-110">A seção ver também é criada a partir do elemento `RelatedLinks` e das marcas que ela contém.</span><span class="sxs-lookup"><span data-stu-id="ceeef-110">The See Also section is created from the `RelatedLinks` element and the tags that it contains.</span></span> <span data-ttu-id="ceeef-111">O XML a seguir mostra como adicionar as marcas.</span><span class="sxs-lookup"><span data-stu-id="ceeef-111">The following XML shows how to add the tags.</span></span>

### <a name="to-add-see-also-topics"></a><span data-ttu-id="ceeef-112">Para adicionar tópicos "Consulte também"</span><span class="sxs-lookup"><span data-stu-id="ceeef-112">To Add "SEE ALSO" Topics</span></span>

1. <span data-ttu-id="ceeef-113">No arquivo *AssemblyName*. dll-help. xml, dentro do elemento `providerHelp`, adicione um elemento `RelatedLinks`.</span><span class="sxs-lookup"><span data-stu-id="ceeef-113">In the *AssemblyName*.dll-help.xml file, within the `providerHelp` element, add a `RelatedLinks` element.</span></span> <span data-ttu-id="ceeef-114">O elemento `RelatedLinks` deve ser o último elemento no elemento `providerHelp`.</span><span class="sxs-lookup"><span data-stu-id="ceeef-114">The `RelatedLinks` element should be the last element in the `providerHelp` element.</span></span> <span data-ttu-id="ceeef-115">Apenas um elemento `RelatedLinks` é permitido em cada tópico da ajuda do provedor.</span><span class="sxs-lookup"><span data-stu-id="ceeef-115">Only one `RelatedLinks` element is permitted in each provider help topic.</span></span>

   <span data-ttu-id="ceeef-116">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ceeef-116">For example:</span></span>

    ```xml
    <providerHelp>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

2. <span data-ttu-id="ceeef-117">Para cada tópico na seção **Consulte também** , dentro do elemento `RelatedLinks`, adicione um elemento `navigationLink`.</span><span class="sxs-lookup"><span data-stu-id="ceeef-117">For each topic in the **SEE ALSO** section, within the `RelatedLinks` element, add a `navigationLink` element.</span></span> <span data-ttu-id="ceeef-118">Em seguida, dentro de cada elemento `navigationLink`, adicione um elemento `linkText` e um elemento `uri`.</span><span class="sxs-lookup"><span data-stu-id="ceeef-118">Then, within each `navigationLink` element, add one `linkText` element and one `uri` element.</span></span> <span data-ttu-id="ceeef-119">Se você não estiver usando o elemento `uri`, poderá adicioná-lo como um elemento vazio (\<URI/>).</span><span class="sxs-lookup"><span data-stu-id="ceeef-119">If you are not using the `uri` element, you can add it as an empty element (\<uri/>).</span></span>

   <span data-ttu-id="ceeef-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ceeef-120">For example:</span></span>

    ```xml
    <providerHelp>
        <RelatedLinks>
            <navigationLink>
                <linkText> </linkText>
                <uri> </uri>
            </navigationLink>
        </RelatedLinks>
    </providerHelp>
    ```

3. <span data-ttu-id="ceeef-121">Digite o nome do tópico entre as marcas de `linkText`.</span><span class="sxs-lookup"><span data-stu-id="ceeef-121">Type the topic name between the `linkText` tags.</span></span> <span data-ttu-id="ceeef-122">Se você estiver fornecendo um URI, digite-o entre as marcas de `uri`.</span><span class="sxs-lookup"><span data-stu-id="ceeef-122">If you are providing a URI, type it between the `uri` tags.</span></span> <span data-ttu-id="ceeef-123">Para indicar a versão online do tópico de ajuda do provedor atual, entre as marcas de `linkText`, digite "versão online:" em vez do nome do tópico.</span><span class="sxs-lookup"><span data-stu-id="ceeef-123">To indicate the online version of the current provider help topic, between the `linkText` tags, type "Online version:" instead of the topic name.</span></span> <span data-ttu-id="ceeef-124">Normalmente, o link "versão online:" é o primeiro tópico na lista de tópicos consulte também.</span><span class="sxs-lookup"><span data-stu-id="ceeef-124">Typically, the "Online version:" link is the first topic in the SEE ALSO topic list.</span></span>

   <span data-ttu-id="ceeef-125">O exemplo a seguir inclui três tópicos de consulte também.</span><span class="sxs-lookup"><span data-stu-id="ceeef-125">The following example include three SEE ALSO topics.</span></span> <span data-ttu-id="ceeef-126">A primeira refere-se à versão online do tópico atual.</span><span class="sxs-lookup"><span data-stu-id="ceeef-126">The first refer to the online version of the current topic.</span></span> <span data-ttu-id="ceeef-127">O segundo se refere a um tópico de ajuda de cmdlet do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ceeef-127">The second refers to a Windows PowerShell cmdlet help topic.</span></span> <span data-ttu-id="ceeef-128">O terceiro se refere a outro tópico online.</span><span class="sxs-lookup"><span data-stu-id="ceeef-128">The third refers to another online topic.</span></span>

    ```xml
    <providerHelp>
        <RelatedLinks>
            <navigationLink>
                <linkText> Online version: </linkText>
                <uri>http://www.fabrikam.com/help/myFunction.htm</uri>
            </navigationLink>
            <navigationLink>
                <linkText> about_functions </linkText>
                <uri/>
            </navigationLink>
            <navigationLink>
                <linkText> Windows PowerShell Getting Started Guide </linkText>
                <uri>https://go.microsoft.com/fwlink/?LinkID=89597<uri/>
            </navigationLink>
        </RelatedLinks>
    </providerHelp>
    ```