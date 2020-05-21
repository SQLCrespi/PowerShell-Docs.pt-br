---
title: Associando entidades do Management OData | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 947a3add-3593-400d-8144-8b44c8adbe5e
caps.latest.revision: 5
ms.openlocfilehash: 4849735bf412497f5590b109c67760b6a197cb2b
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561719"
---
# <a name="associating-management-odata-entities"></a>Associar entidades OData de gerenciamento

Geralmente, é útil criar uma associação entre duas entidades do OData de gerenciamento diferentes. Por exemplo, um serviço OData de gerenciamento pode ter entidades que gerenciam um catálogo de produtos organizados em categorias e definir as entidades `Product` e `Category` . Ao associar essas duas entidades, um cliente pode obter informações sobre todos os produtos em uma categoria com uma única solicitação para o serviço Web.

Um exemplo que mostra como criar associações entre entidades pode ser baixado no [exemplo de associação](https://code.msdn.microsoft.com:443/windowsdesktop/Association-sample-0f0fa87e).

## <a name="creating-the-association-in-the-resource-schema-file"></a>Criando a associação no arquivo de esquema de recursos

O MOF a seguir define duas entidades. Criaremos uma associação entre elas.

```csharp
class Product {

[key] string ProductName;

// other fields ...
};

class Category {

[key] string CategoryName;

string Products[];

// other fields
}
```

A `Category` classe define uma propriedade que é uma matriz dos nomes dos produtos que pertencem a essa categoria.

Para associar duas entidades, você deve definir uma classe com o `Association` atributo no arquivo MOF do esquema de recursos para o serviço. A classe deve definir as duas entidades a serem associadas, chamadas `ends` da associação. O exemplo a seguir mostra uma definição de uma classe que define uma associação entre as entidades categoria e produtos.

```csharp
[Association]
class ProductCategory {
Category ref theCategory;
Product ref theProducts;
}
```

Você também deve alterar a declaração da propriedade Products na classe Category. Você usa a `AssociationClass` palavra-chave para especificar que a propriedade é uma extremidade da associação. A propriedade também deve ser definida como uma referência a uma entidade separada, em vez de uma matriz de cadeias de caracteres. Você faz isso usando a `ref` palavra-chave. O exemplo a seguir mostra a definição de propriedade para a associação.

```csharp
class Sample_Category {

[key] string CategoryName;

[AssociationClass("Sample_ProductCategory"),ToEnd("theProducts")]
Sample_Product ref AssociatedProducts[];
};
```

Por fim, você deve declarar a outra extremidade da Associação adicionando uma definição de propriedade à `Product` classe. Essa é uma referência a uma matriz ou a uma única entidade. Supondo que cada produto pertença a apenas uma categoria, a definição seria a seguinte.

```csharp
class Sample_Product {

[key] string ProductName;
[AssociationClass("Sample_ProductCategory"),ToEnd("theCategory")]
Sample_Category ref AssociatedCategory;
};
```

As propriedades que representam as duas extremidades da associação são chamadas de propriedades de navegação.

#### <a name="steps-for-associating-entities-in-the-resource-schema-file"></a>Etapas para associar entidades no arquivo de esquema de recursos

- Defina a associação como uma classe usando a `Association` palavra-chave.

- Defina as extremidades da Associação usando a palavra-chave AssociationClass para qualificar as propriedades das entidades associadas.

## <a name="creating-the-association-in-the-resource-mapping-xml-file"></a>Criando a associação no arquivo XML de mapeamento de recursos

Há três casos diferentes a serem considerados ao mapear uma associação no arquivo XML de mapeamento de recursos.

#### <a name="determining-how-to-associate-entities-in-the-resource-mapping-file"></a>Determinando como associar entidades no arquivo de mapeamento de recursos

- Se a propriedade de navegação estiver presente no subjacente. .NET Framework tipo e essa propriedade contém chaves estrangeiras, nenhum mapeamento explícito é necessário.

- Se a propriedade de navegação não existir no tipo de .NET Framework subjacente, você deverá especificar um cmdlet que recupere a lista de chaves das instâncias associadas. Você faz isso adicionando um `Association` elemento aninhado sob o `CmdletImplementation` elemento, seguindo os elementos que definem o `cmdlets` para os outros comandos CRUD.

  ```xml
  Class Name=" Category">
     <CmdletImplementation>
        <Query> ... </Query>
        <Associations>
           <Field>
              <Name>AssociatedProducts</Name>
              <GetReference>
                 <Cmdlet>Get-ProductsInCategory</Cmdlet>
                 <ParameterForThisObject>Category</ParameterForThisObject>
              </GetReference>
           </Field>
        </Associations>
     </CmdletImplementation>
  </Class>
  ```

- Se a propriedade de navegação existir no tipo de .NET Framework subjacente, mas ela contiver instâncias de objeto em vez de chaves estrangeiras, você deverá criar um cmdlet (escrevendo uma função ou script do Windows PowerShell) para recuperar as chaves estrangeiras. Em seguida, você especifica esse cmdlet no arquivo de mapeamento de recursos. Por exemplo, o script para recuperar as chaves se pareceria com o seguinte.

  ```
  Param(
      [string] $Key
      )

  (get-category $key).AssociatedProducts

  ```

  E o XML no arquivo de mapeamento de recursos se pareceria com o seguinte.

  ```xml
  Class Name=" Category">
     <CmdletImplementation>
        <Query> ... </Query>
        <Associations>
           <Field>
              <Name>AssociatedProducts</Name>
              <GetReference>
                 <Cmdlet>Get-ProductsInCategory.ps1</Cmdlet>
                 <ParameterForThisObject>Category</ParameterForThisObject>
              </GetReference>
           </Field>
        </Associations>
     </CmdletImplementation>
  </Class>
  ```

- Além de especificar um cmdlet para recuperar as entidades associadas, você também pode especificar cmdlets para adicionar e remover referências da coleção. O exemplo a seguir pressupõe que os cmdlets Add-ProductToCategory e remove-ProductFromCategory existam (eles também podem ser definidos em um script ou uma função como no exemplo anterior).

  ```xml
  Class Name="Sample.Category">
     <CmdletImplementation>
        <Query> ... </Query>
        <Associations>
           <Field>
              <Name>AssociatedProducts</Name>
              <GetReference>
  ...
              </GetReference>
        <AddReference>
     <CmdletName>"Add-ProductToCategory"</>
     <ParameterForThisObject>"Product"</>
     <ParameterForReferredObject>"Category"</>
        </AddReference>
        <RemoveReference>
     <CmdletName="Remove-ProductFromCategory"/>
     <ParameterForThisObject >"Product"</>
     <ParameterForReferredObject >"Category"</>
        </RemoveReference>
           </Field>
        </Associations>
     </CmdletImplementation>
  </Class>
  ```

## <a name="querying-associated-entities"></a>Consultando entidades associadas

O cliente pode recuperar uma lista das instâncias associadas a uma entidade criando consultas específicas.

#### <a name="constructing-queries-for-associated-entities"></a>Construindo consultas para entidades associadas

- Um cliente pode solicitar os detalhes de uma categoria sem recuperar seus produtos associados. Por exemplo, a solicitação a seguir obtém detalhes da `food` categoria.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')
  ```

  Para obter os produtos associados da categoria (mas não os detalhes da categoria em si, o cliente especifica a propriedade de navegação na solicitação.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/AssociatedProducts
  ```

- Para recuperar somente as URLs dos produtos, use o `$links` qualificador na solicitação.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/$links/AssociatedProducts
  ```

- O cliente pode obter os detalhes da categoria e seus produtos associados usando o `$expand` qualificador.

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')?$expand=AssociatedProducts
  ```

## <a name="see-also"></a>Consulte Também

[Criando um serviço Web de extensão do IIS do Management OData](./creating-a-management-odata-web-service.md)
