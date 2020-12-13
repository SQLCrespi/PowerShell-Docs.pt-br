---
ms.date: 09/13/2016
ms.topic: reference
title: Como adicionar uma descrição do cmdlet
description: Como adicionar uma descrição do cmdlet
ms.openlocfilehash: 08d21a281881678423bbe3c382279875ed2868db
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651225"
---
# <a name="how-to-add-a-cmdlet-description"></a><span data-ttu-id="a2a8d-103">Como adicionar uma descrição do cmdlet</span><span class="sxs-lookup"><span data-stu-id="a2a8d-103">How to Add a Cmdlet Description</span></span>

<span data-ttu-id="a2a8d-104">Esta seção descreve como adicionar conteúdo exibido na seção **Descrição** da ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-104">This section describes how to add content that is displayed in the **DESCRIPTION** section of the cmdlet Help.</span></span> <span data-ttu-id="a2a8d-105">No arquivo de ajuda, esse conteúdo é adicionado ao nó de **comando** para cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-105">In the Help file, this content is added to the **Command** node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="a2a8d-106">Para obter uma exibição completa de um arquivo de ajuda, abra um dos `dll-Help.xml` arquivos localizados no diretório de instalação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-106">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the PowerShell installation directory.</span></span> <span data-ttu-id="a2a8d-107">Por exemplo, o `Microsoft.PowerShell.Commands.Management.dll-Help.xml` arquivo contém conteúdo para vários cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-107">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

### <a name="to-add-a-description"></a><span data-ttu-id="a2a8d-108">Para adicionar uma descrição</span><span class="sxs-lookup"><span data-stu-id="a2a8d-108">To Add a Description</span></span>

- <span data-ttu-id="a2a8d-109">Comece explicando os recursos básicos do cmdlet em mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-109">Begin by explaining the basic features of the cmdlet in more detail.</span></span> <span data-ttu-id="a2a8d-110">Em muitos casos, você pode explicar os termos usados no nome do cmdlet e ilustrar conceitos desconhecidos com um exemplo.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-110">In many cases, you can explain the terms used in the cmdlet name and illustrate unfamiliar concepts with an example.</span></span> <span data-ttu-id="a2a8d-111">Por exemplo, se o cmdlet acrescentar dados a um arquivo, explique que ele adiciona dados ao final de um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-111">For example, if the cmdlet appends data to a file, explain that it adds data to the end of an existing file.</span></span>

- <span data-ttu-id="a2a8d-112">Para localizar todos os recursos do cmdlet, examine a lista de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-112">To find all of the features of the cmdlet, review the parameter list.</span></span> <span data-ttu-id="a2a8d-113">Descreva a função principal do cmdlet e, em seguida, inclua outras funções e recursos.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-113">Describe the primary function of the cmdlet, and then include other functions and features.</span></span> <span data-ttu-id="a2a8d-114">Por exemplo, se a função main do cmdlet for alterar uma propriedade, mas o cmdlet puder alterar todas as propriedades, digamos que na descrição detalhada.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-114">For example, if the main function of the cmdlet is to change one property, but the cmdlet can change all of the properties, say so in the detailed description.</span></span> <span data-ttu-id="a2a8d-115">Se os parâmetros do cmdlet permitirem que os usuários solicitem informações de maneiras diferentes, explique isso.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-115">If the cmdlet parameters let the users solicit information in different ways, explain it.</span></span>

- <span data-ttu-id="a2a8d-116">Inclua informações sobre as maneiras como os usuários podem usar o cmdlet, além dos usos óbvios.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-116">Include information on ways that users can use the cmdlet, in addition to the obvious uses.</span></span> <span data-ttu-id="a2a8d-117">Por exemplo, você pode usar o objeto que o `Get-Host` cmdlet recupera para alterar a cor do texto na janela de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-117">For example, you can use the object that the `Get-Host` cmdlet retrieves to change the color of text in the Windows PowerShell command window.</span></span>

  <span data-ttu-id="a2a8d-118">Exemplo: "o `Get-Acl` cmdlet obtém objetos que representam o descritor de segurança de um arquivo ou recurso.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-118">Example: "The `Get-Acl` cmdlet gets objects that represent the security descriptor of a file or resource.</span></span> <span data-ttu-id="a2a8d-119">O descritor de segurança contém as listas de controle de acesso (ACLs) do recurso.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-119">The security descriptor contains the access control lists (ACLs) of the resource.</span></span> <span data-ttu-id="a2a8d-120">A ACL especifica as permissões que os usuários e grupos de usuários têm para acessar o recurso. "</span><span class="sxs-lookup"><span data-stu-id="a2a8d-120">The ACL specifies the permissions that users and user groups have to access the resource."</span></span>

- <span data-ttu-id="a2a8d-121">A descrição detalhada deve descrever o cmdlet, mas não deve descrever os conceitos que o cmdlet usa.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-121">The detailed description should describe the cmdlet, but it should not describe concepts that the cmdlet uses.</span></span> <span data-ttu-id="a2a8d-122">Coloque as definições de conceito em observações adicionais.</span><span class="sxs-lookup"><span data-stu-id="a2a8d-122">Place concept definitions in Additional Notes.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2a8d-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a2a8d-123">See Also</span></span>

[<span data-ttu-id="a2a8d-124">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2a8d-124">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
