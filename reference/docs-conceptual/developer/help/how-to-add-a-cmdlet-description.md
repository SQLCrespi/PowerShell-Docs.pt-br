---
title: Como adicionar uma descrição de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47af9d57-bd63-4596-816a-0b717418476b
caps.latest.revision: 10
ms.openlocfilehash: a2e4c4d42566d5a52006924eab02295c37cf3159
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361275"
---
# <a name="how-to-add-a-cmdlet-description"></a><span data-ttu-id="48de7-102">Como adicionar uma descrição do cmdlet</span><span class="sxs-lookup"><span data-stu-id="48de7-102">How to Add a Cmdlet Description</span></span>

<span data-ttu-id="48de7-103">Esta seção descreve como adicionar conteúdo exibido na seção Descrição da ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="48de7-103">This section describes how to add content that is displayed in the DESCRIPTION section of the cmdlet Help.</span></span> <span data-ttu-id="48de7-104">No arquivo de ajuda, esse conteúdo é adicionado ao nó de comando para cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="48de7-104">In the Help file, this content is added to the Command node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="48de7-105">Para obter uma exibição completa de um arquivo de ajuda, abra um dos arquivos dll-Help. xml localizados no diretório de instalação do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48de7-105">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="48de7-106">Por exemplo, o arquivo Microsoft. PowerShell. Commands. Management. dll-Help. xml contém conteúdo para vários cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48de7-106">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="to-add-a-description"></a><span data-ttu-id="48de7-107">Para adicionar uma descrição</span><span class="sxs-lookup"><span data-stu-id="48de7-107">To Add a Description</span></span>

- <span data-ttu-id="48de7-108">Comece explicando os recursos básicos do cmdlet em mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="48de7-108">Begin by explaining the basic features of the cmdlet in more detail.</span></span> <span data-ttu-id="48de7-109">Em muitos casos, você pode explicar os termos usados no nome do cmdlet e ilustrar conceitos desconhecidos com um exemplo.</span><span class="sxs-lookup"><span data-stu-id="48de7-109">In many cases, you can explain the terms used in the cmdlet name and illustrate unfamiliar concepts with an example.</span></span> <span data-ttu-id="48de7-110">Por exemplo, se o cmdlet acrescentar dados a um arquivo, explique que ele adiciona dados ao final de um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="48de7-110">For example, if the cmdlet appends data to a file, explain that it adds data to the end of an existing file.</span></span>

- <span data-ttu-id="48de7-111">Para localizar todos os recursos do cmdlet, examine a lista de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="48de7-111">To find all of the features of the cmdlet, review the parameter list.</span></span> <span data-ttu-id="48de7-112">Descreva a função principal do cmdlet e, em seguida, inclua outras funções e recursos.</span><span class="sxs-lookup"><span data-stu-id="48de7-112">Describe the primary function of the cmdlet, and then include other functions and features.</span></span> <span data-ttu-id="48de7-113">Por exemplo, se a função main do cmdlet for alterar uma propriedade, mas o cmdlet puder alterar todas as propriedades, digamos que na descrição detalhada.</span><span class="sxs-lookup"><span data-stu-id="48de7-113">For example, if the main function of the cmdlet is to change one property, but the cmdlet can change all of the properties, say so in the detailed description.</span></span> <span data-ttu-id="48de7-114">Se os parâmetros do cmdlet permitirem que os usuários solicitem informações de maneiras diferentes, explique isso.</span><span class="sxs-lookup"><span data-stu-id="48de7-114">If the cmdlet parameters let the users solicit information in different ways, explain it.</span></span>

- <span data-ttu-id="48de7-115">Inclua informações sobre as maneiras como os usuários podem usar o cmdlet, além dos usos óbvios.</span><span class="sxs-lookup"><span data-stu-id="48de7-115">Include information on ways that users can use the cmdlet, in addition to the obvious uses.</span></span> <span data-ttu-id="48de7-116">Por exemplo, você pode usar o objeto que o cmdlet `Get-Host` recupera para alterar a cor do texto na janela de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48de7-116">For example, you can use the object that the `Get-Host` cmdlet retrieves to change the color of text in the Windows PowerShell command window.</span></span>

  <span data-ttu-id="48de7-117">Exemplo: "o cmdlet `Get-Acl` obtém objetos que representam o descritor de segurança de um arquivo ou recurso.</span><span class="sxs-lookup"><span data-stu-id="48de7-117">Example:  "The `Get-Acl` cmdlet gets objects that represent the security descriptor of a file or resource.</span></span> <span data-ttu-id="48de7-118">O descritor de segurança contém as listas de controle de acesso (ACLs) do recurso.</span><span class="sxs-lookup"><span data-stu-id="48de7-118">The security descriptor contains the access control lists (ACLs) of the resource.</span></span> <span data-ttu-id="48de7-119">A ACL especifica as permissões que os usuários e grupos de usuários têm para acessar o recurso. "</span><span class="sxs-lookup"><span data-stu-id="48de7-119">The ACL specifies the permissions that users and user groups have to access the resource."</span></span>

- <span data-ttu-id="48de7-120">A descrição detalhada deve descrever o cmdlet, mas não deve descrever os conceitos que o cmdlet usa.</span><span class="sxs-lookup"><span data-stu-id="48de7-120">The detailed description should describe the cmdlet, but it should not describe concepts that the cmdlet uses.</span></span> <span data-ttu-id="48de7-121">Coloque as definições de conceito em observações adicionais.</span><span class="sxs-lookup"><span data-stu-id="48de7-121">Place concept definitions in Additional Notes.</span></span>

## <a name="see-also"></a><span data-ttu-id="48de7-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="48de7-122">See Also</span></span>

[<span data-ttu-id="48de7-123">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="48de7-123">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
