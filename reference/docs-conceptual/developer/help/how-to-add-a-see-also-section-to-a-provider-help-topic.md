---
title: Como adicionar uma seção “veja também” a um tópico de ajuda do provedor
ms.date: 09/12/2016
ms.openlocfilehash: 54adf4bb941888583eb749b7b5322b27d84c7af7
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893468"
---
# <a name="how-to-add-a-see-also-section-to-a-provider-help-topic"></a><span data-ttu-id="a5f3d-102">Como adicionar uma seção “veja também” a um tópico de ajuda do provedor</span><span class="sxs-lookup"><span data-stu-id="a5f3d-102">How to Add a See Also Section to a Provider Help Topic</span></span>

<span data-ttu-id="a5f3d-103">Esta seção explica como preencher a seção **Consulte também** de um tópico de ajuda do provedor.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-103">This section explains how to populate the **SEE ALSO** section of a provider help topic.</span></span>

<span data-ttu-id="a5f3d-104">A seção **Consulte também** consiste em uma lista de tópicos relacionados ao provedor ou pode ajudar o usuário a entender melhor e usar o provedor.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-104">The **SEE ALSO** section consists of a list of topics that are related to the provider or might help the user better understand and use the provider.</span></span> <span data-ttu-id="a5f3d-105">A lista de tópicos pode incluir a ajuda do cmdlet, a ajuda do provedor e os tópicos de ajuda conceitual ("sobre") no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-105">The topic list can include cmdlet help, provider help and conceptual ("about") help topics in Windows PowerShell.</span></span> <span data-ttu-id="a5f3d-106">Ele também pode incluir referências a livros, documentos e tópicos online, incluindo uma versão online do tópico de ajuda do provedor atual.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-106">It can also include references to books, paper, and online topics, including an online version of the current provider help topic.</span></span>

<span data-ttu-id="a5f3d-107">Quando você se referir a tópicos online, forneça o URI ou um termo de pesquisa em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-107">When you refer to online topics, provide the URI or a search term in plain text.</span></span> <span data-ttu-id="a5f3d-108">O `Get-Help` cmdlet não é vinculado ou Redirecionado a nenhum dos tópicos na lista.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-108">The `Get-Help` cmdlet does not link or redirect to any of the topics in the list.</span></span> <span data-ttu-id="a5f3d-109">Além disso, o `Online` parâmetro do `Get-Help` cmdlet não funciona com a ajuda do provedor.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-109">Also, the `Online` parameter of the `Get-Help` cmdlet does not work with provider help.</span></span>

<span data-ttu-id="a5f3d-110">A seção **Ver também** é criada a partir do `RelatedLinks` elemento e das marcas que ela contém.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-110">The **See Also** section is created from the `RelatedLinks` element and the tags that it contains.</span></span>
<span data-ttu-id="a5f3d-111">O XML a seguir mostra como adicionar as marcas.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-111">The following XML shows how to add the tags.</span></span>

### <a name="to-add-see-also-topics"></a><span data-ttu-id="a5f3d-112">Para adicionar, consulte também tópicos</span><span class="sxs-lookup"><span data-stu-id="a5f3d-112">To Add SEE ALSO Topics</span></span>

1. <span data-ttu-id="a5f3d-113">No `<AssemblyName>.dll-help.xml` arquivo, dentro do `providerHelp` elemento, adicione um `RelatedLinks` elemento.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-113">In the `<AssemblyName>.dll-help.xml` file, within the `providerHelp` element, add a `RelatedLinks` element.</span></span> <span data-ttu-id="a5f3d-114">O `RelatedLinks` elemento deve ser o último elemento no `providerHelp` elemento.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-114">The `RelatedLinks` element should be the last element in the `providerHelp` element.</span></span> <span data-ttu-id="a5f3d-115">Somente um `RelatedLinks` elemento é permitido em cada tópico da ajuda do provedor.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-115">Only one `RelatedLinks` element is permitted in each provider help topic.</span></span>

   <span data-ttu-id="a5f3d-116">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a5f3d-116">For example:</span></span>

    ```xml
    <providerHelp>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

1. <span data-ttu-id="a5f3d-117">Para cada tópico na seção **Consulte também** , dentro do `RelatedLinks` elemento, adicione um `navigationLink` elemento.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-117">For each topic in the **SEE ALSO** section, within the `RelatedLinks` element, add a `navigationLink` element.</span></span> <span data-ttu-id="a5f3d-118">Em seguida, dentro de cada `navigationLink` elemento, adicione um `linkText` elemento e um `uri` elemento.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-118">Then, within each `navigationLink` element, add one `linkText` element and one `uri` element.</span></span> <span data-ttu-id="a5f3d-119">Se você não estiver usando o `uri` elemento, poderá adicioná-lo como um elemento vazio ( \<uri/> ).</span><span class="sxs-lookup"><span data-stu-id="a5f3d-119">If you are not using the `uri` element, you can add it as an empty element (\<uri/>).</span></span>

   <span data-ttu-id="a5f3d-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a5f3d-120">For example:</span></span>

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

1. <span data-ttu-id="a5f3d-121">Digite o nome do tópico entre as `linkText` marcas.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-121">Type the topic name between the `linkText` tags.</span></span> <span data-ttu-id="a5f3d-122">Se você estiver fornecendo um URI, digite-o entre as `uri` marcas.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-122">If you are providing a URI, type it between the `uri` tags.</span></span> <span data-ttu-id="a5f3d-123">Para indicar a versão online do tópico de ajuda do provedor atual, entre as `linkText` marcas, digite "versão online:" em vez do nome do tópico.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-123">To indicate the online version of the current provider help topic, between the `linkText` tags, type "Online version:" instead of the topic name.</span></span> <span data-ttu-id="a5f3d-124">Normalmente, o link "versão online:" é o primeiro tópico na lista de tópicos consulte também.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-124">Typically, the "Online version:" link is the first topic in the SEE ALSO topic list.</span></span>

   <span data-ttu-id="a5f3d-125">O exemplo a seguir inclui três tópicos de consulte também.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-125">The following example include three SEE ALSO topics.</span></span> <span data-ttu-id="a5f3d-126">A primeira refere-se à versão online do tópico atual.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-126">The first refer to the online version of the current topic.</span></span> <span data-ttu-id="a5f3d-127">O segundo se refere a um tópico de ajuda de cmdlet do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-127">The second refers to a Windows PowerShell cmdlet help topic.</span></span> <span data-ttu-id="a5f3d-128">O terceiro se refere a outro tópico online.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-128">The third refers to another online topic.</span></span>

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
