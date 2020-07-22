---
title: Como adicionar parâmetros dinâmicos a um tópico de ajuda do provedor
ms.date: 09/13/2016
ms.openlocfilehash: ddf964292ee7bf477767a2ca17c717aef84bad51
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893451"
---
# <a name="how-to-add-dynamic-parameters-to-a-provider-help-topic"></a><span data-ttu-id="d69c7-102">Como adicionar parâmetros dinâmicos a um tópico de ajuda do provedor</span><span class="sxs-lookup"><span data-stu-id="d69c7-102">How to Add Dynamic Parameters to a Provider Help Topic</span></span>

<span data-ttu-id="d69c7-103">Esta seção explica como preencher a seção de **parâmetros dinâmicos** de um tópico de ajuda do provedor.</span><span class="sxs-lookup"><span data-stu-id="d69c7-103">This section explains how to populate the **DYNAMIC PARAMETERS** section of a provider help topic.</span></span>

<span data-ttu-id="d69c7-104">*Parâmetros dinâmicos* são parâmetros de um cmdlet ou função que estão disponíveis somente em condições especificadas.</span><span class="sxs-lookup"><span data-stu-id="d69c7-104">*Dynamic parameters* are parameters of a cmdlet or function that are available only under specified conditions.</span></span>

<span data-ttu-id="d69c7-105">Os parâmetros dinâmicos documentados em um tópico de ajuda do provedor são os parâmetros dinâmicos que o provedor adiciona ao cmdlet ou função quando o cmdlet ou a função é usada na unidade do provedor.</span><span class="sxs-lookup"><span data-stu-id="d69c7-105">The dynamic parameters that are documented in a provider help topic are the dynamic parameters that the provider adds to the cmdlet or function when the cmdlet or function is used in the provider drive.</span></span>

<span data-ttu-id="d69c7-106">Os parâmetros dinâmicos também podem ser documentados na ajuda do cmdlet personalizado para um provedor.</span><span class="sxs-lookup"><span data-stu-id="d69c7-106">Dynamic parameters can also be documented in custom cmdlet help for a provider.</span></span> <span data-ttu-id="d69c7-107">Ao escrever a ajuda do provedor e a ajuda do cmdlet personalizado para um provedor, inclua a documentação do parâmetro dinâmico em ambos os documentos.</span><span class="sxs-lookup"><span data-stu-id="d69c7-107">When writing both provider help and custom cmdlet help for a provider, include the dynamic parameter documentation in both documents.</span></span>

<span data-ttu-id="d69c7-108">Se um provedor não implementar nenhum parâmetro dinâmico, o tópico da ajuda do provedor conterá um `DynamicParameters` elemento vazio.</span><span class="sxs-lookup"><span data-stu-id="d69c7-108">If a provider does not implement any dynamic parameters, the provider help topic contains an empty `DynamicParameters` element.</span></span>

### <a name="to-add-dynamic-parameters"></a><span data-ttu-id="d69c7-109">Para adicionar parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="d69c7-109">To Add Dynamic Parameters</span></span>

1. <span data-ttu-id="d69c7-110">No `<AssemblyName>.dll-help.xml` arquivo, dentro do `providerHelp` elemento, adicione um `DynamicParameters` elemento.</span><span class="sxs-lookup"><span data-stu-id="d69c7-110">In the `<AssemblyName>.dll-help.xml` file, within the `providerHelp` element, add a `DynamicParameters` element.</span></span> <span data-ttu-id="d69c7-111">O `DynamicParameters` elemento deve aparecer após o `Tasks` elemento e antes do `RelatedLinks` elemento.</span><span class="sxs-lookup"><span data-stu-id="d69c7-111">The `DynamicParameters` element should appear after the `Tasks` element and before the `RelatedLinks` element.</span></span>

   <span data-ttu-id="d69c7-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d69c7-112">For example:</span></span>

    ```xml
    <providerHelp>
        <Tasks>
        </Tasks>
        <DynamicParameters>
        </DynamicParameters>
        <RelatedLinks>
        </RelatedLinks>
    </providerHelp>
    ```

   <span data-ttu-id="d69c7-113">Se o provedor não implementar nenhum parâmetro dinâmico, o `DynamicParameters` elemento poderá ficar vazio.</span><span class="sxs-lookup"><span data-stu-id="d69c7-113">If the provider does not implement any dynamic parameters, the `DynamicParameters` element can be empty.</span></span>

1. <span data-ttu-id="d69c7-114">Dentro do `DynamicParameters` elemento, para cada parâmetro dinâmico, adicione um `DynamicParameter` elemento.</span><span class="sxs-lookup"><span data-stu-id="d69c7-114">Within the `DynamicParameters` element, for each dynamic parameter, add a `DynamicParameter` element.</span></span>

   <span data-ttu-id="d69c7-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d69c7-115">For example:</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
        </DynamicParameter>
    </DynamicParameters>
    ```

1. <span data-ttu-id="d69c7-116">Em cada `DynamicParameter` elemento, adicione um `Name` `CmdletSupported` elemento e.</span><span class="sxs-lookup"><span data-stu-id="d69c7-116">In each `DynamicParameter` element, add a `Name` and `CmdletSupported` element.</span></span>

   - <span data-ttu-id="d69c7-117">Nome-especifica o nome do parâmetro</span><span class="sxs-lookup"><span data-stu-id="d69c7-117">Name - Specifies the parameter name</span></span>
   - <span data-ttu-id="d69c7-118">CmdletSupported-especifica os cmdlets nos quais o parâmetro é válido.</span><span class="sxs-lookup"><span data-stu-id="d69c7-118">CmdletSupported - Specifies the cmdlets in which the parameter is valid.</span></span> <span data-ttu-id="d69c7-119">Digite uma lista separada por vírgulas de nomes de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d69c7-119">Type a comma-separated list of cmdlet names.</span></span>

   <span data-ttu-id="d69c7-120">Por exemplo, o XML a seguir documenta o `Encoding` parâmetro dinâmico que o provedor do sistema de arquivos do Windows PowerShell adiciona aos `Add-Content` `Get-Content` `Set-Content` cmdlets,,.</span><span class="sxs-lookup"><span data-stu-id="d69c7-120">For example, the following XML documents the `Encoding` dynamic parameter that the Windows PowerShell FileSystem provider adds to the `Add-Content`, `Get-Content`, `Set-Content` cmdlets.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
    </DynamicParameters>

    ```

1. <span data-ttu-id="d69c7-121">Em cada `DynamicParameter` elemento, adicione um `Type` elemento.</span><span class="sxs-lookup"><span data-stu-id="d69c7-121">In each `DynamicParameter` element, add a `Type` element.</span></span> <span data-ttu-id="d69c7-122">O `Type` elemento é um contêiner para o `Name` elemento que contém o tipo .net do valor do parâmetro dinâmico.</span><span class="sxs-lookup"><span data-stu-id="d69c7-122">The `Type` element is a container for the `Name` element which contains the .NET type of the value of the dynamic parameter.</span></span>

   <span data-ttu-id="d69c7-123">Por exemplo, o XML a seguir mostra que o tipo .NET do `Encoding` parâmetro dinâmico é a enumeração [FileSystemCmdletProviderEncoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) .</span><span class="sxs-lookup"><span data-stu-id="d69c7-123">For example, the following XML shows that the .NET type of the `Encoding` dynamic parameter is the [FileSystemCmdletProviderEncoding](/dotnet/api/microsoft.powershell.commands.filesystemcmdletproviderencoding) enumeration.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
            <Type>
                <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
            <Type>
    ...
    </DynamicParameters>
    ```

1. <span data-ttu-id="d69c7-124">Adicione o `Description` elemento, que contém uma breve descrição do parâmetro dinâmico.</span><span class="sxs-lookup"><span data-stu-id="d69c7-124">Add the `Description` element, which contains a brief description of the dynamic parameter.</span></span> <span data-ttu-id="d69c7-125">Ao compor a descrição, use as diretrizes indicadas para todos os parâmetros de cmdlet em [como adicionar informações de parâmetro](./how-to-add-parameter-information.md).</span><span class="sxs-lookup"><span data-stu-id="d69c7-125">When composing the description, use the guidelines prescribed for all cmdlet parameters in [How to Add Parameter Information](./how-to-add-parameter-information.md).</span></span>

   <span data-ttu-id="d69c7-126">Por exemplo, o XML a seguir inclui a descrição do `Encoding` parâmetro dinâmico.</span><span class="sxs-lookup"><span data-stu-id="d69c7-126">For example, the following XML includes the description of the `Encoding` dynamic parameter.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
            <Name> Encoding </Name>
            <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
            <Type>
                <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
            <Type>
            <Description> Specifies the encoding of the output file that contains the content. </Description>
    ...
    </DynamicParameters>
    ```

1. <span data-ttu-id="d69c7-127">Adicione o `PossibleValues` elemento e seus elementos filho.</span><span class="sxs-lookup"><span data-stu-id="d69c7-127">Add the `PossibleValues` element and its child elements.</span></span> <span data-ttu-id="d69c7-128">Juntos, esses elementos descrevem os valores do parâmetro dinâmico.</span><span class="sxs-lookup"><span data-stu-id="d69c7-128">Together, these elements describe the values of the dynamic parameter.</span></span> <span data-ttu-id="d69c7-129">Esse elemento é projetado para valores enumerados.</span><span class="sxs-lookup"><span data-stu-id="d69c7-129">This element is designed for enumerated values.</span></span> <span data-ttu-id="d69c7-130">Se o parâmetro dinâmico não receber um valor, como é o caso com um parâmetro de opção, ou os valores não podem ser enumerados, adicione um `PossibleValues` elemento vazio.</span><span class="sxs-lookup"><span data-stu-id="d69c7-130">If the dynamic parameter does not take a value, such as is the case with a switch parameter, or the values cannot be enumerated, add an empty `PossibleValues` element.</span></span>

   <span data-ttu-id="d69c7-131">A tabela a seguir lista e descreve o `PossibleValues` elemento e seus elementos filho.</span><span class="sxs-lookup"><span data-stu-id="d69c7-131">The following table lists and describes the `PossibleValues` element and its child elements.</span></span>

   - <span data-ttu-id="d69c7-132">PossibleValues-este elemento é um contêiner.</span><span class="sxs-lookup"><span data-stu-id="d69c7-132">PossibleValues - This element is a container.</span></span> <span data-ttu-id="d69c7-133">Seus elementos filho são descritos abaixo.</span><span class="sxs-lookup"><span data-stu-id="d69c7-133">Its child elements are described below.</span></span> <span data-ttu-id="d69c7-134">Adicione um `PossibleValues` elemento a cada tópico da ajuda do provedor.</span><span class="sxs-lookup"><span data-stu-id="d69c7-134">Add one `PossibleValues` element to each provider help topic.</span></span> <span data-ttu-id="d69c7-135">O elemento pode estar vazio.</span><span class="sxs-lookup"><span data-stu-id="d69c7-135">The element can be empty.</span></span>
   - <span data-ttu-id="d69c7-136">Possívelvalue-esse elemento é um contêiner.</span><span class="sxs-lookup"><span data-stu-id="d69c7-136">PossibleValue - This element is a container.</span></span> <span data-ttu-id="d69c7-137">Seus elementos filho são descritos abaixo.</span><span class="sxs-lookup"><span data-stu-id="d69c7-137">Its child elements are described below.</span></span> <span data-ttu-id="d69c7-138">Adicione um `PossibleValue` elemento para cada valor do parâmetro dinâmico.</span><span class="sxs-lookup"><span data-stu-id="d69c7-138">Add one `PossibleValue` element for each value of the dynamic parameter.</span></span>
   - <span data-ttu-id="d69c7-139">Valor-especifica o nome do valor.</span><span class="sxs-lookup"><span data-stu-id="d69c7-139">Value - Specifies the value name.</span></span>
   - <span data-ttu-id="d69c7-140">Descrição-Este elemento contém um `Para` elemento.</span><span class="sxs-lookup"><span data-stu-id="d69c7-140">Description - This element contains a `Para` element.</span></span> <span data-ttu-id="d69c7-141">O texto no `Para` elemento descreve o valor que é nomeado no `Value` elemento.</span><span class="sxs-lookup"><span data-stu-id="d69c7-141">The text in the `Para` element describes the value that is named in the `Value` element.</span></span>

   <span data-ttu-id="d69c7-142">Por exemplo, o XML a seguir mostra um `PossibleValue` elemento do `Encoding` parâmetro dinâmico.</span><span class="sxs-lookup"><span data-stu-id="d69c7-142">For example, the following XML shows one `PossibleValue` element of the `Encoding` dynamic parameter.</span></span>

    ```xml
    <DynamicParameters/>
        <DynamicParameter>
    ...
            <Description> Specifies the encoding of the output file that contains the content. </Description>
            <PossibleValues>
                <PossibleValue>
                    <Value> ASCII </Value>
                    <Description>
                        <para> Uses the encoding for the ASCII (7-bit) character set. </para>
                    </Description>
                </PossibleValue>
    ...
            </PossibleValues>
    </DynamicParameters>
    ```

## <a name="example"></a><span data-ttu-id="d69c7-143">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d69c7-143">Example</span></span>

<span data-ttu-id="d69c7-144">O exemplo a seguir mostra o `DynamicParameters` elemento do `Encoding` parâmetro dinâmico.</span><span class="sxs-lookup"><span data-stu-id="d69c7-144">The following example shows the `DynamicParameters` element of the `Encoding` dynamic parameter.</span></span>

```xml
<DynamicParameters/>
    <DynamicParameter>
        <Name> Encoding </Name>
        <CmdletSupported> Add-Content, Get-Content, Set-Content </CmdletSupported>
        <Type>
            <Name> Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding </Name>
        <Type>
        <Description> Specifies the encoding of the output file that contains the content. </Description>
        <PossibleValues>
            <PossibleValue>
                <Value> ASCII </Value>
                <Description>
                    <para> Uses the encoding for the ASCII (7-bit) character set. </para>
                </Description>
            </PossibleValue>
            <PossibleValue>
                <Value> Unicode </Value>
                <Description>
                    <para> Encodes in UTF-16 format using the little-endian byte order. </para>
                </Description>
            </PossibleValue>
        </PossibleValues>
</DynamicParameters>
```
