---
title: Como criar o arquivo de ajuda do cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a88dd89-6beb-494f-9e2a-6b10baed1a8d
caps.latest.revision: 17
ms.openlocfilehash: b5a5f3e187634b38ba3ce3da18a7ad64ccc09ce2
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893009"
---
# <a name="how-to-create-the-cmdlet-help-file"></a><span data-ttu-id="0d41e-102">Como criar o arquivo de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="0d41e-102">How to Create the Cmdlet Help File</span></span>

<span data-ttu-id="0d41e-103">Esta seção descreve como criar um arquivo XML válido que contém conteúdo para tópicos de ajuda do cmdlet do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d41e-103">This section describes how to create a valid XML file that contains content for Windows PowerShell cmdlet Help topics.</span></span> <span data-ttu-id="0d41e-104">Esta seção discute como nomear o arquivo de ajuda, como adicionar os cabeçalhos XML apropriados e como adicionar nós que conterám as diferentes seções do conteúdo de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0d41e-104">This section discusses how to name the Help file, how to add the appropriate XML headers, and how to add nodes that will contain the different sections of the cmdlet Help content.</span></span>

> [!NOTE]
> <span data-ttu-id="0d41e-105">Para obter uma exibição completa de um arquivo de ajuda, abra um dos `dll-Help.xml` arquivos localizados no diretório de instalação do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d41e-105">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="0d41e-106">Por exemplo, o `Microsoft.PowerShell.Commands.Management.dll-Help.xml` arquivo contém conteúdo para vários cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d41e-106">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

### <a name="how-to-create-a-cmdlet-help-file"></a><span data-ttu-id="0d41e-107">Como criar um arquivo de ajuda de cmdlet</span><span class="sxs-lookup"><span data-stu-id="0d41e-107">How to Create a Cmdlet Help File</span></span>

1. <span data-ttu-id="0d41e-108">Crie um arquivo de texto e salve-o usando a codificação UTF8.</span><span class="sxs-lookup"><span data-stu-id="0d41e-108">Create a text file and save it using UTF8 encoding.</span></span> <span data-ttu-id="0d41e-109">O nome do arquivo deve ter o seguinte formato para que o Windows PowerShell possa detectá-lo como um arquivo de ajuda de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0d41e-109">The filename must have the following format so that Windows PowerShell can detect it as a cmdlet Help file.</span></span>

   `<PSSnapInAssemblyName>.dll-Help.xml`

1. <span data-ttu-id="0d41e-110">Adicione os cabeçalhos XML a seguir ao arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="0d41e-110">Add the following XML headers to the text file.</span></span> <span data-ttu-id="0d41e-111">Lembre-se de que o arquivo será validado em relação ao esquema MAML (Microsoft assistência Markup Language).</span><span class="sxs-lookup"><span data-stu-id="0d41e-111">Be aware that the file will be validated against the Microsoft Assistance Markup Language (MAML) schema.</span></span> <span data-ttu-id="0d41e-112">Atualmente, o PowerShell não fornece nenhuma ferramenta para validar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="0d41e-112">Currently, PowerShell does not provide any tools to validate the file.</span></span>

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

1. <span data-ttu-id="0d41e-113">Adicione um nó de **comando** ao arquivo de ajuda de cmdlet para cada cmdlet no assembly.</span><span class="sxs-lookup"><span data-stu-id="0d41e-113">Add a **Command** node to the cmdlet Help file for each cmdlet in the assembly.</span></span> <span data-ttu-id="0d41e-114">Cada nó dentro do nó de **comando** se relaciona às diferentes seções do tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0d41e-114">Each node within the **Command** node relates to the different sections of the cmdlet Help topic.</span></span>

   <span data-ttu-id="0d41e-115">A tabela a seguir lista o elemento XML para cada nó, seguido por uma descrição de cada nó.</span><span class="sxs-lookup"><span data-stu-id="0d41e-115">The following table lists the XML element for each node, followed by a descriptions of each node.</span></span>

   |           <span data-ttu-id="0d41e-116">Nó</span><span class="sxs-lookup"><span data-stu-id="0d41e-116">Node</span></span>           |                                                                                                     <span data-ttu-id="0d41e-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="0d41e-117">Description</span></span>                                                                                                     |
   | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | `<details>`              | <span data-ttu-id="0d41e-118">Adiciona conteúdo para as seções nome e Sinopse do tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0d41e-118">Adds content for the NAME and SYNOPSIS sections of the cmdlet Help topic.</span></span> <span data-ttu-id="0d41e-119">Para obter mais informações, consulte [como adicionar o nome do cmdlet e Sinopse](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="0d41e-119">For more information, see [How to Add the Cmdlet Name and Synopsis](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md).</span></span> |
   | `<maml:description>`     | <span data-ttu-id="0d41e-120">Adiciona o conteúdo da seção Descrição do tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0d41e-120">Adds content for the DESCRIPTION section of the cmdlet Help topic.</span></span> <span data-ttu-id="0d41e-121">Para obter mais informações, consulte [como adicionar a descrição detalhada a um tópico de ajuda de cmdlet](./how-to-add-a-cmdlet-description.md).</span><span class="sxs-lookup"><span data-stu-id="0d41e-121">For more information, see [How to Add the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span>                    |
   | `<command:syntax>`       | <span data-ttu-id="0d41e-122">Adiciona o conteúdo da seção de sintaxe do tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0d41e-122">Adds content for the SYNTAX section of the cmdlet Help topic.</span></span> <span data-ttu-id="0d41e-123">Para obter mais informações, consulte [como adicionar sintaxe a um tópico de ajuda de cmdlet](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="0d41e-123">For more information, see [How to Add Syntax to a Cmdlet Help Topic](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span></span>                                  |
   | `<command:parameters>`   | <span data-ttu-id="0d41e-124">Adiciona o conteúdo da seção de parâmetros do tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0d41e-124">Adds content for the PARAMETERS section of the cmdlet Help topic.</span></span> <span data-ttu-id="0d41e-125">Para obter mais informações, consulte [como adicionar parâmetros a um tópico de ajuda de cmdlet](./how-to-add-parameter-information.md).</span><span class="sxs-lookup"><span data-stu-id="0d41e-125">For more information, see [How to Add Parameters to a Cmdlet Help Topic](./how-to-add-parameter-information.md).</span></span>                                  |
   | `<command:inputTypes>`   | <span data-ttu-id="0d41e-126">Adiciona o conteúdo da seção entradas do tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0d41e-126">Adds content for the INPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="0d41e-127">Para obter mais informações, consulte [como adicionar tipos de entrada a um tópico de ajuda de cmdlet](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="0d41e-127">For more information, see [How to Add Input Types to a Cmdlet Help Topic](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span></span>                        |
   | `<command:returnValues>` | <span data-ttu-id="0d41e-128">Adiciona o conteúdo da seção de saídas do tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0d41e-128">Adds content for the OUTPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="0d41e-129">Para obter mais informações, consulte [como adicionar valores de retorno a um tópico de ajuda de cmdlet](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="0d41e-129">For more information, see [How to Add Return Values to a Cmdlet Help Topic](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span></span>                   |
   | `<maml:alertset>`        | <span data-ttu-id="0d41e-130">Adiciona o conteúdo da seção observações do tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0d41e-130">Adds content for the NOTES section of the cmdlet Help topic.</span></span> <span data-ttu-id="0d41e-131">Para obter mais informações, consulte [como adicionar anotações a um tópico de ajuda do cmdlet](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="0d41e-131">For more information, see [How to add Notes to a Cmdlet Help Topic](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span></span>                                      |
   | `<command:examples>`     | <span data-ttu-id="0d41e-132">Adiciona o conteúdo para a seção exemplos do tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0d41e-132">Adds content for the EXAMPLES section of the cmdlet Help topic.</span></span> <span data-ttu-id="0d41e-133">Para obter mais informações, consulte [como adicionar exemplos a um tópico de ajuda de cmdlet](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="0d41e-133">For more information, see [How to Add Examples to a Cmdlet Help Topic](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span></span>                            |
   | `<maml:relatedLinks>`    | <span data-ttu-id="0d41e-134">Adiciona o conteúdo da seção LINKS relacionados do tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0d41e-134">Adds content for the RELATED LINKS section of the cmdlet Help topic.</span></span> <span data-ttu-id="0d41e-135">Para obter mais informações, consulte [como adicionar links relacionados a um tópico de ajuda de cmdlet](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span><span class="sxs-lookup"><span data-stu-id="0d41e-135">For more information, see [How to Add Related Links to a Cmdlet Help Topic](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span></span>             |

## <a name="example"></a><span data-ttu-id="0d41e-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0d41e-136">Example</span></span>

 <span data-ttu-id="0d41e-137">Aqui está um exemplo de um nó de **comando** que inclui os nós das várias seções do tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0d41e-137">Here is an example of a **Command** node that includes the nodes for the various sections of the cmdlet Help topic.</span></span>

```xml
<command:command
  xmlns:maml="https://schemas.microsoft.com/maml/2004/10"
  xmlns:command="https://schemas.microsoft.com/maml/dev/command/2004/10"
  xmlns:dev="https://schemas.microsoft.com/maml/dev/2004/10">
  <command:details>
    <!--Add name an synopsis here-->
  </command:details>
  <maml:description>
    <!--Add detailed description here-->
  </maml:description>
  <command:syntax>
    <!--Add syntax information here-->
  </command:syntax>
  <command:parameters>
    <!--Add parameter information here-->
  </command:parameters>
  <command:inputTypes>
    <!--Add input type information here-->
  </command:inputTypes>
  <command:returnValues>
    <!--Add return value information here-->
  </command:returnValues>
  <maml:alertSet>
    <!--Add Note information here-->
  </maml:alertSet>
  <command:examples>
    <!--Add cmdlet examples here-->
  </command:examples>
  <maml:relatedLinks>
    <!--Add links to related content here-->
  </maml:relatedLinks>
</command:command>
```

## <a name="see-also"></a><span data-ttu-id="0d41e-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0d41e-138">See Also</span></span>

 [<span data-ttu-id="0d41e-139">Como adicionar o nome do cmdlet e Sinopse</span><span class="sxs-lookup"><span data-stu-id="0d41e-139">How to Add the Cmdlet Name and Synopsis</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="0d41e-140">Como adicionar a descrição detalhada a um tópico de ajuda de cmdlet</span><span class="sxs-lookup"><span data-stu-id="0d41e-140">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="0d41e-141">Como adicionar sintaxe a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="0d41e-141">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="0d41e-142">Como adicionar parâmetros a um tópico de ajuda de cmdlet</span><span class="sxs-lookup"><span data-stu-id="0d41e-142">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="0d41e-143">Como adicionar tipos de entrada a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="0d41e-143">How to Add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="0d41e-144">Como adicionar valores retornados a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="0d41e-144">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="0d41e-145">Como adicionar anotações a um tópico de ajuda de cmdlet</span><span class="sxs-lookup"><span data-stu-id="0d41e-145">How to add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="0d41e-146">Como adicionar exemplos a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="0d41e-146">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="0d41e-147">Como adicionar links relacionados a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="0d41e-147">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="0d41e-148">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d41e-148">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
