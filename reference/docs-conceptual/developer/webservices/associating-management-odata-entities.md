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
ms.openlocfilehash: 44b718e024eb98ac562edb50076287a31f5edc6b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359805"
---
# <a name="associating-management-odata-entities"></a><span data-ttu-id="432d0-102">Associar entidades OData de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="432d0-102">Associating Management OData Entities</span></span>

<span data-ttu-id="432d0-103">Geralmente, é útil criar uma associação entre duas entidades do OData de gerenciamento diferentes.</span><span class="sxs-lookup"><span data-stu-id="432d0-103">It is often useful to create an association between two different Management OData entities.</span></span> <span data-ttu-id="432d0-104">Por exemplo, um serviço OData de gerenciamento pode ter entidades que gerenciam um catálogo de produtos organizados em categorias e definir as entidades `Product` e `Category`.</span><span class="sxs-lookup"><span data-stu-id="432d0-104">For example, a Management OData service could have entities that manage a catalogue of products that are organized in categories, and define the entities `Product` and `Category`.</span></span> <span data-ttu-id="432d0-105">Ao associar essas duas entidades, um cliente pode obter informações sobre todos os produtos em uma categoria com uma única solicitação para o serviço Web.</span><span class="sxs-lookup"><span data-stu-id="432d0-105">By associating these two entities, a client can get information about all of the products in a category with a single request to the web service.</span></span>

<span data-ttu-id="432d0-106">Um exemplo que mostra como criar associações entre entidades pode ser baixado no [exemplo de associação](https://code.msdn.microsoft.com:443/windowsdesktop/Association-sample-0f0fa87e).</span><span class="sxs-lookup"><span data-stu-id="432d0-106">A sample that shows how to create associations between entities can be downloaded at [Association sample](https://code.msdn.microsoft.com:443/windowsdesktop/Association-sample-0f0fa87e).</span></span>

## <a name="creating-the-association-in-the-resource-schema-file"></a><span data-ttu-id="432d0-107">Criando a associação no arquivo de esquema de recursos</span><span class="sxs-lookup"><span data-stu-id="432d0-107">Creating the Association in the resource schema file</span></span>

<span data-ttu-id="432d0-108">O MOF a seguir define duas entidades.</span><span class="sxs-lookup"><span data-stu-id="432d0-108">The following MOF defines two entities.</span></span> <span data-ttu-id="432d0-109">Criaremos uma associação entre elas.</span><span class="sxs-lookup"><span data-stu-id="432d0-109">We will create an association between them.</span></span>

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

<span data-ttu-id="432d0-110">A classe `Category` define uma propriedade que é uma matriz dos nomes dos produtos que pertencem a essa categoria.</span><span class="sxs-lookup"><span data-stu-id="432d0-110">The `Category` class defines a property that is an array of the names of the products that belong to that category.</span></span>

<span data-ttu-id="432d0-111">Para associar duas entidades, você deve definir uma classe com o atributo `Association` no arquivo MOF do esquema de recursos para o serviço.</span><span class="sxs-lookup"><span data-stu-id="432d0-111">To associate two entities, you must define a class with the `Association` attribute in the resource schema MOF file for the service.</span></span> <span data-ttu-id="432d0-112">A classe deve definir as duas entidades a serem associadas, chamadas `ends` da associação.</span><span class="sxs-lookup"><span data-stu-id="432d0-112">The class must define the two entities to be associated, called `ends` of the association.</span></span> <span data-ttu-id="432d0-113">O exemplo a seguir mostra uma definição de uma classe que define uma associação entre as entidades categoria e produtos.</span><span class="sxs-lookup"><span data-stu-id="432d0-113">The following example shows a definition of a class that defines an association between the Category and Products entities.</span></span>

```csharp
[Association]
class ProductCategory {
Category ref theCategory;
Product ref theProducts;
}
```

<span data-ttu-id="432d0-114">Você também deve alterar a declaração da propriedade Products na classe Category.</span><span class="sxs-lookup"><span data-stu-id="432d0-114">You must also change the declaration of the Products property in the Category class.</span></span> <span data-ttu-id="432d0-115">Use a palavra-chave `AssociationClass` para especificar que a propriedade é uma extremidade da associação.</span><span class="sxs-lookup"><span data-stu-id="432d0-115">You use the `AssociationClass` keyword to specify that the property is one end of the association.</span></span> <span data-ttu-id="432d0-116">A propriedade também deve ser definida como uma referência a uma entidade separada, em vez de uma matriz de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="432d0-116">The property must also be defined as a reference to a separate entity, rather than an array of strings.</span></span> <span data-ttu-id="432d0-117">Você faz isso usando a palavra-chave `ref`.</span><span class="sxs-lookup"><span data-stu-id="432d0-117">You do this by using the `ref` keyword.</span></span> <span data-ttu-id="432d0-118">O exemplo a seguir mostra a definição de propriedade para a associação.</span><span class="sxs-lookup"><span data-stu-id="432d0-118">The following example shows the property definition for the association.</span></span>

```csharp
class Sample_Category {

[key] string CategoryName;

[AssociationClass("Sample_ProductCategory"),ToEnd("theProducts")]
Sample_Product ref AssociatedProducts[];
};
```

<span data-ttu-id="432d0-119">Por fim, você deve declarar a outra extremidade da Associação adicionando uma definição de propriedade à classe `Product`.</span><span class="sxs-lookup"><span data-stu-id="432d0-119">Finally, you must declare the other end of the association by adding a property definition to the `Product` class.</span></span> <span data-ttu-id="432d0-120">Essa é uma referência a uma matriz ou a uma única entidade.</span><span class="sxs-lookup"><span data-stu-id="432d0-120">This is a reference to either an array or to a single entity.</span></span> <span data-ttu-id="432d0-121">Supondo que cada produto pertença a apenas uma categoria, a definição seria a seguinte.</span><span class="sxs-lookup"><span data-stu-id="432d0-121">Assuming that each product belongs to only one category, the definition would be as follows.</span></span>

```csharp
class Sample_Product {

[key] string ProductName;
[AssociationClass("Sample_ProductCategory"),ToEnd("theCategory")]
Sample_Category ref AssociatedCategory;
};
```

<span data-ttu-id="432d0-122">As propriedades que representam as duas extremidades da associação são chamadas de propriedades de navegação.</span><span class="sxs-lookup"><span data-stu-id="432d0-122">The properties that represent the two ends of the association are called navigation properties.</span></span>

#### <a name="steps-for-associating-entities-in-the-resource-schema-file"></a><span data-ttu-id="432d0-123">Etapas para associar entidades no arquivo de esquema de recursos</span><span class="sxs-lookup"><span data-stu-id="432d0-123">Steps for associating entities in the resource schema file</span></span>

- <span data-ttu-id="432d0-124">Defina a associação como uma classe usando a palavra-chave `Association`.</span><span class="sxs-lookup"><span data-stu-id="432d0-124">Define the association as a class by using the `Association` keyword.</span></span>

- <span data-ttu-id="432d0-125">Defina as extremidades da Associação usando a palavra-chave AssociationClass para qualificar as propriedades das entidades associadas.</span><span class="sxs-lookup"><span data-stu-id="432d0-125">Define the ends of the association by using the AssociationClass keyword to qualify properties of the associated entities.</span></span>

## <a name="creating-the-association-in-the-resource-mapping-xml-file"></a><span data-ttu-id="432d0-126">Criando a associação no arquivo XML de mapeamento de recursos</span><span class="sxs-lookup"><span data-stu-id="432d0-126">Creating the association in the resource mapping XML file</span></span>

<span data-ttu-id="432d0-127">Há três casos diferentes a serem considerados ao mapear uma associação no arquivo XML de mapeamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="432d0-127">There are three different cases to consider when mapping an association in the resource mapping XML file.</span></span>

#### <a name="determining-how-to-associate-entities-in-the-resource-mapping-file"></a><span data-ttu-id="432d0-128">Determinando como associar entidades no arquivo de mapeamento de recursos</span><span class="sxs-lookup"><span data-stu-id="432d0-128">Determining how to associate entities in the resource mapping file</span></span>

- <span data-ttu-id="432d0-129">Se a propriedade de navegação estiver presente no subjacente.</span><span class="sxs-lookup"><span data-stu-id="432d0-129">If the navigation property is present in the underlying.</span></span> <span data-ttu-id="432d0-130">.NET Framework tipo e essa propriedade contém chaves estrangeiras, nenhum mapeamento explícito é necessário.</span><span class="sxs-lookup"><span data-stu-id="432d0-130">.NET Framework type, and that property contains foreign keys, no explicit mapping is necessary.</span></span>

- <span data-ttu-id="432d0-131">Se a propriedade de navegação não existir no tipo de .NET Framework subjacente, você deverá especificar um cmdlet que recupere a lista de chaves das instâncias associadas.</span><span class="sxs-lookup"><span data-stu-id="432d0-131">If the navigation property does not exist in the underlying .NET Framework type, you must specify a cmdlet that retrieves the list of keys of the associated instances.</span></span> <span data-ttu-id="432d0-132">Você faz isso adicionando um elemento `Association` aninhado sob o elemento `CmdletImplementation`, seguindo os elementos que definem o `cmdlets` para os outros comandos CRUD.</span><span class="sxs-lookup"><span data-stu-id="432d0-132">You do this by adding an `Association` element nested under the `CmdletImplementation` element, following the elements that define the `cmdlets` for the other CRUD commands.</span></span>

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

- <span data-ttu-id="432d0-133">Se a propriedade de navegação existir no tipo de .NET Framework subjacente, mas ela contiver instâncias de objeto em vez de chaves estrangeiras, você deverá criar um cmdlet (escrevendo uma função ou script do Windows PowerShell) para recuperar as chaves estrangeiras.</span><span class="sxs-lookup"><span data-stu-id="432d0-133">If the navigation property does exist in the underlying .NET Framework type, but it contains object instances instead of foreign keys, then you must create a cmdlet (by writing a Windows PowerShell function or script) to retrieve the foreign keys.</span></span> <span data-ttu-id="432d0-134">Em seguida, você especifica esse cmdlet no arquivo de mapeamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="432d0-134">You then specify that cmdlet in the resource mapping file.</span></span> <span data-ttu-id="432d0-135">Por exemplo, o script para recuperar as chaves se pareceria com o seguinte.</span><span class="sxs-lookup"><span data-stu-id="432d0-135">For example, the script to retrieve the keys would look like the following.</span></span>

  ```
  Param(
      [string] $Key
      )

  (get-category $key).AssociatedProducts

  ```

  <span data-ttu-id="432d0-136">E o XML no arquivo de mapeamento de recursos se pareceria com o seguinte.</span><span class="sxs-lookup"><span data-stu-id="432d0-136">And the XML in the resource mapping file would look like the following.</span></span>

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

- <span data-ttu-id="432d0-137">Além de especificar um cmdlet para recuperar as entidades associadas, você também pode especificar cmdlets para adicionar e remover referências da coleção.</span><span class="sxs-lookup"><span data-stu-id="432d0-137">In addition to specifying a cmdlet to retrieve the associated entities, you can also specify cmdlets to add and remove references from the collection.</span></span> <span data-ttu-id="432d0-138">O exemplo a seguir pressupõe que os cmdlets Add-ProductToCategory e remove-ProductFromCategory existam (eles também podem ser definidos em um script ou uma função como no exemplo anterior).</span><span class="sxs-lookup"><span data-stu-id="432d0-138">The following example assumes that the Add-ProductToCategory and Remove-ProductFromCategory cmdlets exist (they can also be defined in a script or function as in the previous example).</span></span>

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

## <a name="querying-associated-entities"></a><span data-ttu-id="432d0-139">Consultando entidades associadas</span><span class="sxs-lookup"><span data-stu-id="432d0-139">Querying associated entities</span></span>

<span data-ttu-id="432d0-140">O cliente pode recuperar uma lista das instâncias associadas a uma entidade criando consultas específicas.</span><span class="sxs-lookup"><span data-stu-id="432d0-140">The client can retrieve a list of the instances associated with an entity by creating specific queries.</span></span>

#### <a name="constructing-queries-for-associated-entities"></a><span data-ttu-id="432d0-141">Construindo consultas para entidades associadas</span><span class="sxs-lookup"><span data-stu-id="432d0-141">Constructing queries for associated entities</span></span>

- <span data-ttu-id="432d0-142">Um cliente pode solicitar os detalhes de uma categoria sem recuperar seus produtos associados.</span><span class="sxs-lookup"><span data-stu-id="432d0-142">A client can request the details of a category without retrieving its associated products.</span></span> <span data-ttu-id="432d0-143">Por exemplo, a solicitação a seguir obtém detalhes da categoria de `food`.</span><span class="sxs-lookup"><span data-stu-id="432d0-143">For example, the following request gets details of the `food` category.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')
  ```

  <span data-ttu-id="432d0-144">Para obter os produtos associados da categoria (mas não os detalhes da categoria em si, o cliente especifica a propriedade de navegação na solicitação.</span><span class="sxs-lookup"><span data-stu-id="432d0-144">To get the associated products of the category (but not details of the category itself, the client specifies the navigation property in the request.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/AssociatedProducts
  ```

- <span data-ttu-id="432d0-145">Para recuperar somente as URLs dos produtos, use o qualificador `$links` na solicitação.</span><span class="sxs-lookup"><span data-stu-id="432d0-145">To retrieve only URLs of the products, use the `$links` qualifier in the request.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/$links/AssociatedProducts
  ```

- <span data-ttu-id="432d0-146">O cliente pode obter os detalhes da categoria e seus produtos associados usando o qualificador `$expand`.</span><span class="sxs-lookup"><span data-stu-id="432d0-146">The client can get both the category details and its associated products by using the `$expand` qualifier.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')?$expand=AssociatedProducts
  ```

## <a name="see-also"></a><span data-ttu-id="432d0-147">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="432d0-147">See Also</span></span>

[<span data-ttu-id="432d0-148">Criando um serviço Web de extensão do IIS do Management OData</span><span class="sxs-lookup"><span data-stu-id="432d0-148">Creating a Management OData IIS Extension Web Service</span></span>](./creating-a-management-odata-web-service.md)