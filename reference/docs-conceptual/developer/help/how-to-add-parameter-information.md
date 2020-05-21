---
title: Como adicionar informações de parâmetro | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf6c1442-60aa-477a-8f30-ab02b1b11039
caps.latest.revision: 7
ms.openlocfilehash: b9ccca75c2d9126e84a7f486ffe803042a742b62
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83565553"
---
# <a name="how-to-add-parameter-information"></a><span data-ttu-id="aa4de-102">Como adicionar informações de parâmetro</span><span class="sxs-lookup"><span data-stu-id="aa4de-102">How to Add Parameter Information</span></span>

<span data-ttu-id="aa4de-103">Esta seção descreve como adicionar conteúdo exibido na seção de parâmetros do tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aa4de-103">This section describes how to add content that is displayed in the PARAMETERS section of the cmdlet Help topic.</span></span> <span data-ttu-id="aa4de-104">A seção de parâmetros do tópico da ajuda lista cada um dos parâmetros do cmdlet e fornece uma descrição detalhada de cada parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa4de-104">The PARAMETERS section of the Help topic lists each of the parameters of the cmdlet and provides a detailed description of each parameter.</span></span>

<span data-ttu-id="aa4de-105">O conteúdo da seção de parâmetros deve ser consistente com o conteúdo da seção de sintaxe do tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="aa4de-105">The content of the PARAMETERS section should be consistent with the content of the SYNTAX section of the Help topic.</span></span> <span data-ttu-id="aa4de-106">É responsabilidade do autor da ajuda garantir que o nó sintaxe e parâmetros contenha elementos XML semelhantes.</span><span class="sxs-lookup"><span data-stu-id="aa4de-106">It is the responsibility of the Help author to make sure that both the Syntax and Parameters node contain similar XML elements.</span></span>

> [!NOTE]
> <span data-ttu-id="aa4de-107">Para obter uma exibição completa de um arquivo de ajuda, abra um dos arquivos dll-Help. xml localizados no diretório de instalação do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa4de-107">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="aa4de-108">Por exemplo, o arquivo Microsoft. PowerShell. Commands. Management. dll-Help. xml contém conteúdo para vários cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa4de-108">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="to-add-parameters"></a><span data-ttu-id="aa4de-109">Para adicionar parâmetros</span><span class="sxs-lookup"><span data-stu-id="aa4de-109">To Add Parameters</span></span>

1. <span data-ttu-id="aa4de-110">Abra o arquivo de ajuda do cmdlet e localize o nó de comando para o cmdlet que você está documentando.</span><span class="sxs-lookup"><span data-stu-id="aa4de-110">Open the cmdlet Help file and locate the Command node for the cmdlet you are documenting.</span></span> <span data-ttu-id="aa4de-111">Se você estiver adicionando um novo cmdlet, precisará criar um novo nó de comando.</span><span class="sxs-lookup"><span data-stu-id="aa4de-111">If you are adding a new cmdlet you will need to create a new Command node.</span></span> <span data-ttu-id="aa4de-112">O arquivo de ajuda conterá um nó de comando para cada cmdlet para o qual você está fornecendo o conteúdo da ajuda.</span><span class="sxs-lookup"><span data-stu-id="aa4de-112">Your Help file will contain a Command node for each cmdlet that you are providing Help content for.</span></span> <span data-ttu-id="aa4de-113">Aqui está um exemplo de um nó de comando em branco.</span><span class="sxs-lookup"><span data-stu-id="aa4de-113">Here is an example of a blank Command node.</span></span>

    ```xml
    <command:command>
    </command:command>
    ```

2. <span data-ttu-id="aa4de-114">No nó de comando, localize o nó descrição e adicione um nó de parâmetros, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="aa4de-114">Within the Command node, locate the Description node and add a Parameters node as shown below.</span></span> <span data-ttu-id="aa4de-115">Apenas um nó de parâmetros é permitido e deve seguir imediatamente o nó de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="aa4de-115">Only one Parameters node is allowed, and it should immediately follow the Syntax node.</span></span>

    ```xml
    <command:command>
      <command:details></command:details>
      <maml:description></maml:description>
      <command:syntax></command:syntax>
      <command:parameters>
      </command:Parameters>
    </command:command>
    ```

3. <span data-ttu-id="aa4de-116">Dentro do nó parâmetros, adicione um nó de parâmetro para cada parâmetro do cmdlet, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="aa4de-116">Within the Parameters node, add a Parameter node for each parameter of the cmdlet as shown below.</span></span>

   <span data-ttu-id="aa4de-117">Neste exemplo, um nó de parâmetro é adicionado para três parâmetros.</span><span class="sxs-lookup"><span data-stu-id="aa4de-117">In this example, a Parameter node is added for three parameters.</span></span>

    ```xml
    <command:parameters>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
    </command:Parameters>
    ```

   <span data-ttu-id="aa4de-118">Como essas são as mesmas marcas XML que são usadas no nó de sintaxe, e como os parâmetros especificados aqui devem corresponder aos parâmetros especificados pelo nó de sintaxe, você pode copiar os nós de parâmetro do nó de sintaxe e colá-los no nó de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="aa4de-118">Because these are the same XML tags that are used in the Syntax node, and because the parameters specified here must match the parameters specified by the Syntax node, you can copy the Parameter nodes from the Syntax node and paste them into the Parameters node.</span></span> <span data-ttu-id="aa4de-119">No entanto, certifique-se de copiar apenas uma instância de um nó de parâmetro, mesmo que o parâmetro seja especificado em vários conjuntos de parâmetros na sintaxe.</span><span class="sxs-lookup"><span data-stu-id="aa4de-119">However, be sure to copy only one instance of a Parameter node, even if the parameter is specified in multiple parameter sets in the syntax.</span></span>

4. <span data-ttu-id="aa4de-120">Para cada nó de parâmetro, defina os valores de atributo que definem as características de cada parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa4de-120">For each Parameter node, set the attribute values that define the characteristics of each parameter.</span></span> <span data-ttu-id="aa4de-121">Esses atributos incluem o seguinte: Required, globaling, PipelineInput e Position.</span><span class="sxs-lookup"><span data-stu-id="aa4de-121">These attributes include the following: required, globbing, pipelineinput, and position.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
      </command:parameter>
      <command:parameter required="false" globbing="false"
               pipelineInput="false" position="named">
      </command:parameter>
      <command:parameter required="false" globbing="false"
               pipelineInput="false" position="named" ></command:parameter>
    </command:Parameters>
    ```

5. <span data-ttu-id="aa4de-122">Para cada nó de parâmetro, adicione o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa4de-122">For each Parameter node, add the name of the parameter.</span></span> <span data-ttu-id="aa4de-123">Aqui está um exemplo do nome do parâmetro adicionado ao nó do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa4de-123">Here is an example of the parameter name added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
      </command:parameter>
    </command:Parameters>
    ```

6. <span data-ttu-id="aa4de-124">Para cada nó de parâmetro, adicione a descrição do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa4de-124">For each Parameter node, add the description of the parameter.</span></span> <span data-ttu-id="aa4de-125">Aqui está um exemplo da descrição do parâmetro adicionada ao nó de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa4de-125">Here is an example of the parameter description added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
      </command:parameter>
    </command:parameters>
    ```

7. <span data-ttu-id="aa4de-126">Para cada nó de parâmetro, adicione o tipo de .NET Framework do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa4de-126">For each Parameter node, add the .NET Framework type of the parameter.</span></span> <span data-ttu-id="aa4de-127">O tipo de parâmetro é exibido junto com o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa4de-127">The parameter type is displayed along with the parameter name.</span></span>

   <span data-ttu-id="aa4de-128">Aqui está um exemplo do parâmetro .NET Framework tipo adicionado ao nó de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa4de-128">Here is an example of the parameter .NET Framework type added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
        <dev:type> Add .NET Framework type... </dev:type>
      </command:parameter>
    </command:parameters>
    ```

8. <span data-ttu-id="aa4de-129">Para cada nó de parâmetro, adicione o valor padrão do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa4de-129">For each Parameter node, add the default value of the parameter.</span></span> <span data-ttu-id="aa4de-130">A sentença a seguir é adicionada à descrição do parâmetro quando o conteúdo é exibido: "DefaultValue" é o padrão.</span><span class="sxs-lookup"><span data-stu-id="aa4de-130">The following sentence is added to the parameter description when the content is displayed: "DefaultValue" is the default.</span></span>

   <span data-ttu-id="aa4de-131">Aqui está um exemplo do valor padrão do parâmetro que é adicionado ao nó do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa4de-131">Here is an example of the parameter default value is added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
        <dev:type> Add .NET Framework type... </dev:type>
        <dev:defaultvalue> Add default value...</dev:defaultvalue>
      </command:parameter>
    </command:parameters>
    ```

9. <span data-ttu-id="aa4de-132">Para cada parâmetro que tem vários valores, adicione um nó de valores possíveis.</span><span class="sxs-lookup"><span data-stu-id="aa4de-132">For each Parameter that has multiple values, add a possible values node.</span></span>

   <span data-ttu-id="aa4de-133">Aqui está um exemplo de um nó de valores possíveis que define dois valores possíveis para o parâmetro</span><span class="sxs-lookup"><span data-stu-id="aa4de-133">Here is an example of the of a possible values node that defines two possible values for the parameter</span></span>

    ```xml
    <dev:possiblevalues>
      <dev:possiblevalue>
        <dev:value>Unknown</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      /dev:possiblevalue>
      <dev:possiblevalue>
        <dev:value>String</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      </dev:possibleValue>
    </dev:possiblevalues>
    ```

<span data-ttu-id="aa4de-134">Aqui estão algumas coisas a serem lembradas ao adicionar parâmetros.</span><span class="sxs-lookup"><span data-stu-id="aa4de-134">Here are some things to remember when adding parameters.</span></span>

- <span data-ttu-id="aa4de-135">Os atributos do parâmetro não são exibidos em todas as exibições do tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aa4de-135">The attributes of the parameter are not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="aa4de-136">No entanto, eles são exibidos em uma tabela após a descrição do parâmetro quando o usuário solicita a exibição completa (Get-Help \< cmdlets>-Full) ou parâmetro (Get-Help \< cmdlets>-Parameter) do tópico.</span><span class="sxs-lookup"><span data-stu-id="aa4de-136">However, they are displayed in a table following the parameter description when the user asks for the Full (Get-Help \<cmdletname> -full) or Parameter (Get-Help \<cmdletname> -parameter) view of the topic.</span></span>

- <span data-ttu-id="aa4de-137">A descrição do parâmetro é uma das partes mais importantes de um tópico de ajuda de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aa4de-137">The parameter description is one of the most important parts of a cmdlet Help topic.</span></span> <span data-ttu-id="aa4de-138">A descrição deve ser breve, bem como completa.</span><span class="sxs-lookup"><span data-stu-id="aa4de-138">The description should be brief, as well as thorough.</span></span> <span data-ttu-id="aa4de-139">Além disso, lembre-se de que se a descrição do parâmetro se tornar muito longa, como quando dois parâmetros interagem entre si, você pode adicionar mais conteúdo na seção anotações do tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aa4de-139">Also, remember that if the parameter description becomes too long, such as when two parameters interact with each other, you can add more content in the NOTES section of the cmdlet Help topic.</span></span>

  <span data-ttu-id="aa4de-140">A descrição do parâmetro fornece dois tipos de informações.</span><span class="sxs-lookup"><span data-stu-id="aa4de-140">The parameter description provides two types of information.</span></span>

- <span data-ttu-id="aa4de-141">O que o cmdlet faz quando o parâmetro é usado.</span><span class="sxs-lookup"><span data-stu-id="aa4de-141">What the cmdlet does when the parameter is used.</span></span>

- <span data-ttu-id="aa4de-142">O que é um valor válido para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa4de-142">What a legal value is for the parameter.</span></span>

- <span data-ttu-id="aa4de-143">Como os valores de parâmetro são expressos como objetos .NET Framework, os usuários precisam de mais informações sobre esses valores do que em uma ajuda de linha de comando tradicional.</span><span class="sxs-lookup"><span data-stu-id="aa4de-143">Because the parameter values are expressed as .NET Framework objects, users need more information about these values than they would in a traditional command-line Help.</span></span> <span data-ttu-id="aa4de-144">Informe ao usuário que tipo de dados o parâmetro foi projetado para aceitar e inclua exemplos.</span><span class="sxs-lookup"><span data-stu-id="aa4de-144">Tell the user what type of data the parameter is designed to accept, and include examples.</span></span>

<span data-ttu-id="aa4de-145">O valor padrão do parâmetro é o valor que será usado se o parâmetro não for especificado na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="aa4de-145">The default value of the parameter is the value that is used if the parameter is not specified on the command line.</span></span> <span data-ttu-id="aa4de-146">Observe que o valor padrão é opcional e não é necessário para alguns parâmetros, como os parâmetros necessários.</span><span class="sxs-lookup"><span data-stu-id="aa4de-146">Note that the default value is optional, and is not needed for some parameters, such as required parameters.</span></span> <span data-ttu-id="aa4de-147">No entanto, você deve especificar um valor padrão para a maioria dos parâmetros opcionais.</span><span class="sxs-lookup"><span data-stu-id="aa4de-147">However, you should specify a default value for most optional parameters.</span></span>

<span data-ttu-id="aa4de-148">O valor padrão ajuda o usuário a entender o efeito de não usar o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa4de-148">The default value helps the user to understand the effect of not using the parameter.</span></span> <span data-ttu-id="aa4de-149">Descreva o valor padrão muito especificamente, como o "diretório atual" ou o "diretório de instalação do Windows PowerShell ($pshome)" para um caminho opcional.</span><span class="sxs-lookup"><span data-stu-id="aa4de-149">Describe the default value very specifically, such as the "Current directory" or the "Windows PowerShell installation directory ($pshome)" for an optional path.</span></span> <span data-ttu-id="aa4de-150">Você também pode escrever uma frase que descreve o padrão, como a seguinte frase usada para o `PassThru` parâmetro: "Se PassThru não for especificado, o cmdlet não passa objetos pelo pipeline".</span><span class="sxs-lookup"><span data-stu-id="aa4de-150">You can also write a sentence that describes the default, such as the following sentence used for the `PassThru` parameter: "If PassThru is not specified, the cmdlet does not pass objects down the pipeline."</span></span>  <span data-ttu-id="aa4de-151">Além disso, como o valor é exibido em oposto ao nome do campo "**valor padrão**", não é necessário incluir o termo "valor padrão" na entrada.</span><span class="sxs-lookup"><span data-stu-id="aa4de-151">Also, because the value is displayed opposite the field name "**Default value**", you do not need to include the term "default value" in the entry.</span></span>

<span data-ttu-id="aa4de-152">O valor padrão do parâmetro não é exibido em todas as exibições do tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aa4de-152">The default value of the parameter is not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="aa4de-153">No entanto, ele é exibido em uma tabela (juntamente com os atributos de parâmetro) após a descrição do parâmetro quando o usuário solicita a exibição completa (Get-Help \< cmdlets>-Full) ou parâmetro (Get-Help \< cmdlets>-Parameter) do tópico.</span><span class="sxs-lookup"><span data-stu-id="aa4de-153">However, it is displayed in a table (along with the parameter attributes) following the parameter description when the user asks for the Full (Get-Help \<cmdletname> -full) or Parameter (Get-Help \<cmdletname> -parameter) view of the topic.</span></span>

<span data-ttu-id="aa4de-154">O XML a seguir mostra um par de `<dev:defaultValue>` marcas adicionadas ao `<command:parameter>` nó.</span><span class="sxs-lookup"><span data-stu-id="aa4de-154">The following XML shows a pair of `<dev:defaultValue>` tags added to the `<command:parameter>` node.</span></span> <span data-ttu-id="aa4de-155">Observe que o valor padrão segue imediatamente após a marca de fechamento `</command:parameterValue>` (quando o valor do parâmetro é especificado) ou a `</maml:description>` marca de fechamento da descrição do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa4de-155">Notice that the default value follows immediately after the closing `</command:parameterValue>` tag (when the parameter value is specified) or the closing `</maml:description>` tag of the parameter description.</span></span> <span data-ttu-id="aa4de-156">nome.</span><span class="sxs-lookup"><span data-stu-id="aa4de-156">name.</span></span>

```xml
<command:parameters>
  <command:parameter required="true" globbing="true"
           pipelineInput="false" position="named">
    <maml:name> Parameter name </maml:name>
    <maml:description>
      <maml:para> Parameter Description </maml:para>
    </maml:description>
    <command:parameterValue required="true">
      Value
    </command:parameterValue>
    <dev:defaultValue> Default parameter value </dev:defaultValue>
  </command:parameter>
</command:parameters>
```

<span data-ttu-id="aa4de-157">Adicionar valores para tipos enumerados</span><span class="sxs-lookup"><span data-stu-id="aa4de-157">Add Values for Enumerated Types</span></span>

<span data-ttu-id="aa4de-158">Se o parâmetro tiver vários valores ou valores de um tipo enumerado, você poderá usar um \< nó dev: possibleValues> opcional.</span><span class="sxs-lookup"><span data-stu-id="aa4de-158">If the parameter has multiple values or values of an enumerated type, you can use an optional \<dev:possibleValues> node.</span></span> <span data-ttu-id="aa4de-159">Esse nó permite que você especifique um nome e uma descrição para vários valores.</span><span class="sxs-lookup"><span data-stu-id="aa4de-159">This node allows you to specify a name and description for multiple values.</span></span>

<span data-ttu-id="aa4de-160">Lembre-se de que as descrições dos valores enumerados não aparecem em nenhum dos modos de exibição padrão da ajuda exibidos pelo `Get-Help` cmdlet, mas outros visualizadores da ajuda podem exibir esse conteúdo em suas exibições.</span><span class="sxs-lookup"><span data-stu-id="aa4de-160">Be aware that the descriptions of the enumerated values do not appear in any of the default Help views displayed by the `Get-Help` cmdlet, but other Help viewers may display this content in their views.</span></span>

<span data-ttu-id="aa4de-161">O XML a seguir mostra um `<dev:possibleValues>` nó com dois valores especificados.</span><span class="sxs-lookup"><span data-stu-id="aa4de-161">The following XML shows a `<dev:possibleValues>` node with two values specified.</span></span>

```xml
<command:parameters>
  <command:parameter required="true" globbing="true"
           pipelineInput="false" position="named">
    <maml:name> Parameter name </maml:name>
    <maml:description>
      <maml:para> Parameter Description </maml:para>
    </maml:description>
    <command:parameterValue required="true">
      Value
    </command:parameterValue>
    <dev:defaultValue> Default parameter value </dev:defaultValue>
    <dev:possibleValues>
      <dev:possibleValue>
        <dev:value> Value 1 </dev:value>
        <maml:description>
          <maml:para> Description 1 </maml:para>
        </maml:description>
      <dev:possibleValue>
      <dev:possibleValue>
        <dev:value> Value 2 </dev:value>
        <maml:description>
          <maml:para> Description 2 </maml:para>
        </maml:description>
      <dev:possibleValue>
    </dev:possibleValues>
  </command:parameter>
</command:parameters>
```
