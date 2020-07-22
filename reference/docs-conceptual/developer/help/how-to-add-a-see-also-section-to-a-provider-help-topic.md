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
# <a name="how-to-add-a-see-also-section-to-a-provider-help-topic"></a>Como adicionar uma seção “veja também” a um tópico de ajuda do provedor

Esta seção explica como preencher a seção **Consulte também** de um tópico de ajuda do provedor.

A seção **Consulte também** consiste em uma lista de tópicos relacionados ao provedor ou pode ajudar o usuário a entender melhor e usar o provedor. A lista de tópicos pode incluir a ajuda do cmdlet, a ajuda do provedor e os tópicos de ajuda conceitual ("sobre") no Windows PowerShell. Ele também pode incluir referências a livros, documentos e tópicos online, incluindo uma versão online do tópico de ajuda do provedor atual.

Quando você se referir a tópicos online, forneça o URI ou um termo de pesquisa em texto sem formatação. O `Get-Help` cmdlet não é vinculado ou Redirecionado a nenhum dos tópicos na lista. Além disso, o `Online` parâmetro do `Get-Help` cmdlet não funciona com a ajuda do provedor.

A seção **Ver também** é criada a partir do `RelatedLinks` elemento e das marcas que ela contém.
O XML a seguir mostra como adicionar as marcas.

### <a name="to-add-see-also-topics"></a>Para adicionar, consulte também tópicos

1. No `<AssemblyName>.dll-help.xml` arquivo, dentro do `providerHelp` elemento, adicione um `RelatedLinks` elemento. O `RelatedLinks` elemento deve ser o último elemento no `providerHelp` elemento. Somente um `RelatedLinks` elemento é permitido em cada tópico da ajuda do provedor.

   Por exemplo:

    ```xml
    <providerHelp>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

1. Para cada tópico na seção **Consulte também** , dentro do `RelatedLinks` elemento, adicione um `navigationLink` elemento. Em seguida, dentro de cada `navigationLink` elemento, adicione um `linkText` elemento e um `uri` elemento. Se você não estiver usando o `uri` elemento, poderá adicioná-lo como um elemento vazio ( \<uri/> ).

   Por exemplo:

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

1. Digite o nome do tópico entre as `linkText` marcas. Se você estiver fornecendo um URI, digite-o entre as `uri` marcas. Para indicar a versão online do tópico de ajuda do provedor atual, entre as `linkText` marcas, digite "versão online:" em vez do nome do tópico. Normalmente, o link "versão online:" é o primeiro tópico na lista de tópicos consulte também.

   O exemplo a seguir inclui três tópicos de consulte também. A primeira refere-se à versão online do tópico atual. O segundo se refere a um tópico de ajuda de cmdlet do Windows PowerShell. O terceiro se refere a outro tópico online.

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
