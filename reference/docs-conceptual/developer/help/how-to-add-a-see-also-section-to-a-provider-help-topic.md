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
# <a name="how-to-add-a-see-also-section-to-a-provider-help-topic"></a>Como adicionar uma seção “veja também” a um tópico de ajuda do provedor

Esta seção explica como preencher a seção **Consulte também** de um tópico de ajuda do provedor.

A seção **Consulte também** consiste em uma lista de tópicos relacionados ao provedor ou pode ajudar o usuário a entender melhor e usar o provedor. A lista de tópicos pode incluir a ajuda do cmdlet, a ajuda do provedor e os tópicos de ajuda conceitual ("sobre") no Windows PowerShell. Ele também pode incluir referências a livros, documentos e tópicos online, incluindo uma versão online do tópico de ajuda do provedor atual.

Quando você se referir a tópicos online, forneça o URI ou um termo de pesquisa em texto sem formatação. O cmdlet `Get-Help` não é vinculado ou Redirecionado a nenhum dos tópicos na lista. Além disso, o parâmetro `Online` do cmdlet `Get-Help` não funciona com a ajuda do provedor.

A seção ver também é criada a partir do elemento `RelatedLinks` e das marcas que ela contém. O XML a seguir mostra como adicionar as marcas.

### <a name="to-add-see-also-topics"></a>Para adicionar tópicos "Consulte também"

1. No arquivo *AssemblyName*. dll-help. xml, dentro do elemento `providerHelp`, adicione um elemento `RelatedLinks`. O elemento `RelatedLinks` deve ser o último elemento no elemento `providerHelp`. Apenas um elemento `RelatedLinks` é permitido em cada tópico da ajuda do provedor.

   Por exemplo:

    ```xml
    <providerHelp>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

2. Para cada tópico na seção **Consulte também** , dentro do elemento `RelatedLinks`, adicione um elemento `navigationLink`. Em seguida, dentro de cada elemento `navigationLink`, adicione um elemento `linkText` e um elemento `uri`. Se você não estiver usando o elemento `uri`, poderá adicioná-lo como um elemento vazio (\<URI/>).

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

3. Digite o nome do tópico entre as marcas de `linkText`. Se você estiver fornecendo um URI, digite-o entre as marcas de `uri`. Para indicar a versão online do tópico de ajuda do provedor atual, entre as marcas de `linkText`, digite "versão online:" em vez do nome do tópico. Normalmente, o link "versão online:" é o primeiro tópico na lista de tópicos consulte também.

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