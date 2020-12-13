---
ms.date: 09/13/2016
ms.topic: reference
title: Como adicionar a sinopse e o nome do cmdlet a um tópico de ajuda do cmdlet
description: Como adicionar a sinopse e o nome do cmdlet a um tópico de ajuda do cmdlet
ms.openlocfilehash: aeeb0cdd1d6d17b88067928ff952dc57a9441917
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659051"
---
# <a name="how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic"></a><span data-ttu-id="38d9d-103">Como adicionar a sinopse e o nome do cmdlet a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="38d9d-103">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>

<span data-ttu-id="38d9d-104">Esta seção descreve como adicionar conteúdo exibido nas seções **nome** e **Sinopse** da ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38d9d-104">This section describes how to add content that is displayed in the **NAME** and **SYNOPSIS** sections of the cmdlet help.</span></span> <span data-ttu-id="38d9d-105">No arquivo de ajuda, esse conteúdo é adicionado ao nó de comando para cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38d9d-105">In the Help file, this content is added to the Command node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="38d9d-106">Para obter uma exibição completa de um arquivo de ajuda, abra um dos `dll-Help.xml` arquivos localizados no diretório de instalação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38d9d-106">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the PowerShell installation directory.</span></span> <span data-ttu-id="38d9d-107">Por exemplo, o `Microsoft.PowerShell.Commands.Management.dll-Help.xml` arquivo contém conteúdo para vários cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38d9d-107">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

## <a name="to-add-the-cmdlet-name-and-a-synopsis"></a><span data-ttu-id="38d9d-108">Para adicionar o nome do cmdlet e uma sinopse</span><span class="sxs-lookup"><span data-stu-id="38d9d-108">To Add the Cmdlet Name and a Synopsis</span></span>

- <span data-ttu-id="38d9d-109">A ajuda do cmdlet pode exibir duas descrições para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38d9d-109">The cmdlet Help can display two descriptions for the cmdlet.</span></span> <span data-ttu-id="38d9d-110">A primeira descrição é uma breve descrição que é conhecida como Sinopse.</span><span class="sxs-lookup"><span data-stu-id="38d9d-110">The first description is a short description that is referred to as the synopsis.</span></span> <span data-ttu-id="38d9d-111">A segunda descrição é uma descrição mais detalhada que é abordada na [adição da descrição detalhada a um tópico de ajuda de cmdlet](./how-to-add-a-cmdlet-description.md).</span><span class="sxs-lookup"><span data-stu-id="38d9d-111">The second description is a more detailed description that is discussed in [Adding the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span>
  <span data-ttu-id="38d9d-112">Ambas as descrições devem ser escritas como um único parágrafo.</span><span class="sxs-lookup"><span data-stu-id="38d9d-112">Both these descriptions should be written as a single paragraph.</span></span>

- <span data-ttu-id="38d9d-113">Na Sinopse, não repita o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38d9d-113">In the synopsis do not repeat the cmdlet name.</span></span> <span data-ttu-id="38d9d-114">Informar ao usuário que o `Get-Server` cmdlet obtém um servidor é breve, mas não é informativo.</span><span class="sxs-lookup"><span data-stu-id="38d9d-114">Informing the user that the `Get-Server` cmdlet gets a server is brief, but not informative.</span></span> <span data-ttu-id="38d9d-115">Em vez disso, use sinônimos e adicione detalhes à descrição.</span><span class="sxs-lookup"><span data-stu-id="38d9d-115">Instead, use synonyms and add details to the description.</span></span>

  <span data-ttu-id="38d9d-116">Exemplo: "Obtém um objeto que representa um computador local ou remoto".</span><span class="sxs-lookup"><span data-stu-id="38d9d-116">Example: "Gets an object that represents a local or remote computer."</span></span>

- <span data-ttu-id="38d9d-117">Use verbos simples, como "Get", "Create" e "Change" na Sinopse.</span><span class="sxs-lookup"><span data-stu-id="38d9d-117">Use simple verbs like "get", "create", and "change" in the synopsis.</span></span> <span data-ttu-id="38d9d-118">Evite usar "set" porque ele é vago e palavras sofisticadas, como "Modify".</span><span class="sxs-lookup"><span data-stu-id="38d9d-118">Avoid using "set" because it is vague, and fancy words such as "modify."</span></span>

  <span data-ttu-id="38d9d-119">Exemplo: "Obtém informações sobre a assinatura Authenticode em um arquivo".</span><span class="sxs-lookup"><span data-stu-id="38d9d-119">Example: "Gets information about the Authenticode signature in a file."</span></span>

- <span data-ttu-id="38d9d-120">Gravar no Active Voice.</span><span class="sxs-lookup"><span data-stu-id="38d9d-120">Write in active voice.</span></span> <span data-ttu-id="38d9d-121">Por exemplo, "usar o objeto TimeSpan..." é muito mais claro do que "o objeto TimeSpan pode ser usado para..."</span><span class="sxs-lookup"><span data-stu-id="38d9d-121">For example, "Use the TimeSpan object..." is much clearer than "the TimeSpan object can be used to..."</span></span>

- <span data-ttu-id="38d9d-122">Evite o verbo "display" ao descrever os cmdlets que obtêm objetos.</span><span class="sxs-lookup"><span data-stu-id="38d9d-122">Avoid the verb "display" when describing cmdlets that get objects.</span></span> <span data-ttu-id="38d9d-123">Embora o Windows PowerShell exiba dados de cmdlet, é importante introduzir os usuários ao conceito que o cmdlet retorna .NET Framework objetos cujos dados podem não ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="38d9d-123">Although Windows PowerShell displays cmdlet data, it is important to introduce users to the concept that the cmdlet returns .NET Framework objects whose data may not be displayed.</span></span> <span data-ttu-id="38d9d-124">Se você enfatizar a exibição, o usuário pode não perceber que o cmdlet pode ter retornado muitas outras propriedades e métodos úteis que não são exibidos.</span><span class="sxs-lookup"><span data-stu-id="38d9d-124">If you emphasize the display, the user might not realize that the cmdlet may have returned many other useful properties and methods that are not displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="38d9d-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38d9d-125">See Also</span></span>

[<span data-ttu-id="38d9d-126">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38d9d-126">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
