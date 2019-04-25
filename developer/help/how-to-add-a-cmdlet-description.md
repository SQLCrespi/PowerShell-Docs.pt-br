---
title: Como adicionar uma descrição do Cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47af9d57-bd63-4596-816a-0b717418476b
caps.latest.revision: 10
ms.openlocfilehash: a2e4c4d42566d5a52006924eab02295c37cf3159
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083511"
---
# <a name="how-to-add-a-cmdlet-description"></a><span data-ttu-id="599d9-102">Como adicionar uma descrição do cmdlet</span><span class="sxs-lookup"><span data-stu-id="599d9-102">How to Add a Cmdlet Description</span></span>

<span data-ttu-id="599d9-103">Esta seção descreve como adicionar conteúdo que é exibido na seção de descrição do cmdlet Help.</span><span class="sxs-lookup"><span data-stu-id="599d9-103">This section describes how to add content that is displayed in the DESCRIPTION section of the cmdlet Help.</span></span> <span data-ttu-id="599d9-104">No arquivo de Ajuda, esse conteúdo é adicionado para o nó de comando para cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="599d9-104">In the Help file, this content is added to the Command node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="599d9-105">Para obter uma visão completa de um arquivo de Ajuda, abra um dos arquivos dll Help.xml localizado no diretório de instalação do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="599d9-105">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="599d9-106">Por exemplo, o arquivo de Microsoft.PowerShell.Commands.Management.dll Help.xml contém conteúdo para vários dos cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="599d9-106">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="to-add-a-description"></a><span data-ttu-id="599d9-107">Para adicionar uma descrição</span><span class="sxs-lookup"><span data-stu-id="599d9-107">To Add a Description</span></span>

- <span data-ttu-id="599d9-108">Comece explicando os recursos básicos do cmdlet em mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="599d9-108">Begin by explaining the basic features of the cmdlet in more detail.</span></span> <span data-ttu-id="599d9-109">Em muitos casos, você pode explicar os termos usados no nome do cmdlet e ilustrar conceitos familiarizados com um exemplo.</span><span class="sxs-lookup"><span data-stu-id="599d9-109">In many cases, you can explain the terms used in the cmdlet name and illustrate unfamiliar concepts with an example.</span></span> <span data-ttu-id="599d9-110">Por exemplo, se o cmdlet acrescenta dados a um arquivo, explique que ele adiciona dados ao final de um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="599d9-110">For example, if the cmdlet appends data to a file, explain that it adds data to the end of an existing file.</span></span>

- <span data-ttu-id="599d9-111">Para localizar todos os recursos do cmdlet, examine a lista de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="599d9-111">To find all of the features of the cmdlet, review the parameter list.</span></span> <span data-ttu-id="599d9-112">Descrever a função primária do cmdlet e, em seguida, incluir outras funções e recursos.</span><span class="sxs-lookup"><span data-stu-id="599d9-112">Describe the primary function of the cmdlet, and then include other functions and features.</span></span> <span data-ttu-id="599d9-113">Por exemplo, se a função principal do cmdlet é alterar uma propriedade, mas o cmdlet pode alterar todas as propriedades, que isso na descrição detalhada.</span><span class="sxs-lookup"><span data-stu-id="599d9-113">For example, if the main function of the cmdlet is to change one property, but the cmdlet can change all of the properties, say so in the detailed description.</span></span> <span data-ttu-id="599d9-114">Se os parâmetros do cmdlet permitem que os usuários solicitam informações de maneiras diferentes, explique-lo.</span><span class="sxs-lookup"><span data-stu-id="599d9-114">If the cmdlet parameters let the users solicit information in different ways, explain it.</span></span>

- <span data-ttu-id="599d9-115">Inclua informações sobre as maneiras que os usuários podem usar o cmdlet, além do óbvio usa.</span><span class="sxs-lookup"><span data-stu-id="599d9-115">Include information on ways that users can use the cmdlet, in addition to the obvious uses.</span></span> <span data-ttu-id="599d9-116">Por exemplo, você pode usar o objeto que o `Get-Host` cmdlet recupera para alterar a cor do texto na janela de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="599d9-116">For example, you can use the object that the `Get-Host` cmdlet retrieves to change the color of text in the Windows PowerShell command window.</span></span>

  <span data-ttu-id="599d9-117">Exemplo:  "O `Get-Acl` cmdlet obtém os objetos que representam o descritor de segurança de um arquivo ou recurso.</span><span class="sxs-lookup"><span data-stu-id="599d9-117">Example:  "The `Get-Acl` cmdlet gets objects that represent the security descriptor of a file or resource.</span></span> <span data-ttu-id="599d9-118">O descritor de segurança contém as listas de controle de acesso (ACLs) do recurso.</span><span class="sxs-lookup"><span data-stu-id="599d9-118">The security descriptor contains the access control lists (ACLs) of the resource.</span></span> <span data-ttu-id="599d9-119">A ACL especifica as permissões que os usuários e grupos de usuários têm acesso ao recurso."</span><span class="sxs-lookup"><span data-stu-id="599d9-119">The ACL specifies the permissions that users and user groups have to access the resource."</span></span>

- <span data-ttu-id="599d9-120">A descrição detalhada deve descrever o cmdlet, mas ele não deve descrever os conceitos que usa o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="599d9-120">The detailed description should describe the cmdlet, but it should not describe concepts that the cmdlet uses.</span></span> <span data-ttu-id="599d9-121">Colocar definições de conceito em observações adicionais.</span><span class="sxs-lookup"><span data-stu-id="599d9-121">Place concept definitions in Additional Notes.</span></span>

## <a name="see-also"></a><span data-ttu-id="599d9-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="599d9-122">See Also</span></span>

[<span data-ttu-id="599d9-123">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="599d9-123">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
