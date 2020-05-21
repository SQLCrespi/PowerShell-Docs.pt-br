---
title: Como adicionar o nome do cmdlet e Sinopse a um tópico de ajuda de cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d0e1eb1-a962-4406-9625-175cfa3364ad
caps.latest.revision: 10
ms.openlocfilehash: 5b4c04a14c3d86c7a3b94b768e8fb59116d8c6f5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560620"
---
# <a name="how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic"></a><span data-ttu-id="6d12f-102">Como adicionar a sinopse e o nome do cmdlet a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="6d12f-102">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>

<span data-ttu-id="6d12f-103">Esta seção descreve como adicionar conteúdo exibido nas seções nome e Sinopse da ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6d12f-103">This section describes how to add content that is displayed in the NAME and SYNOPSIS sections of the cmdlet help.</span></span> <span data-ttu-id="6d12f-104">No arquivo de ajuda, esse conteúdo é adicionado ao nó de comando para cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6d12f-104">In the Help file, this content is added to the Command node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="6d12f-105">Para obter uma exibição completa de um arquivo de ajuda, abra um dos arquivos dll-Help. xml localizados no diretório de instalação do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d12f-105">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="6d12f-106">Por exemplo, o arquivo Microsoft. PowerShell. Commands. Management. dll-Help. xml contém conteúdo para vários cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d12f-106">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="to-add-the-cmdlet-name-and-a-synopsis"></a><span data-ttu-id="6d12f-107">Para adicionar o nome do cmdlet e uma sinopse</span><span class="sxs-lookup"><span data-stu-id="6d12f-107">To Add the Cmdlet Name and a Synopsis</span></span>

- <span data-ttu-id="6d12f-108">A ajuda do cmdlet pode exibir duas descrições para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6d12f-108">The cmdlet Help can display two descriptions for the cmdlet.</span></span> <span data-ttu-id="6d12f-109">A primeira descrição é uma breve descrição que é conhecida como Sinopse.</span><span class="sxs-lookup"><span data-stu-id="6d12f-109">The first description is a short description that is referred to as the synopsis.</span></span> <span data-ttu-id="6d12f-110">A segunda descrição é uma descrição mais detalhada que é abordada na [adição da descrição detalhada a um tópico de ajuda de cmdlet](./how-to-add-a-cmdlet-description.md).</span><span class="sxs-lookup"><span data-stu-id="6d12f-110">The second description is a more detailed description that is discussed in [Adding the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span> <span data-ttu-id="6d12f-111">Ambas as descrições devem ser escritas como um único parágrafo.</span><span class="sxs-lookup"><span data-stu-id="6d12f-111">Both these descriptions should be written as a single paragraph.</span></span>

- <span data-ttu-id="6d12f-112">Na Sinopse, não repita o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6d12f-112">In the synopsis do not repeat the cmdlet name.</span></span> <span data-ttu-id="6d12f-113">Informando ao usuário que o cmdlet Get-Server Obtém um servidor é curto, mas não é informativo.</span><span class="sxs-lookup"><span data-stu-id="6d12f-113">Informing the user that the Get-Server cmdlet gets a server is brief, but not informative.</span></span> <span data-ttu-id="6d12f-114">Em vez disso, use sinônimos e adicione detalhes à descrição.</span><span class="sxs-lookup"><span data-stu-id="6d12f-114">Instead, use synonyms and add details to the description.</span></span>

  <span data-ttu-id="6d12f-115">Exemplo: "Obtém um objeto que representa um computador local ou remoto".</span><span class="sxs-lookup"><span data-stu-id="6d12f-115">Example: "Gets an object that represents a local or remote computer."</span></span>

- <span data-ttu-id="6d12f-116">Use verbos simples, como "Get", "Create" e "Change" na Sinopse.</span><span class="sxs-lookup"><span data-stu-id="6d12f-116">Use simple verbs like "get", "create", and "change" in the synopsis.</span></span> <span data-ttu-id="6d12f-117">Evite usar "set" porque ele é vago e palavras sofisticadas, como "Modify".</span><span class="sxs-lookup"><span data-stu-id="6d12f-117">Avoid using "set" because it is vague, and fancy words such as "modify."</span></span>

  <span data-ttu-id="6d12f-118">Exemplo: "Obtém informações sobre a assinatura Authenticode em um arquivo".</span><span class="sxs-lookup"><span data-stu-id="6d12f-118">Example: "Gets information about the Authenticode signature in a file."</span></span>

- <span data-ttu-id="6d12f-119">Gravar no Active Voice.</span><span class="sxs-lookup"><span data-stu-id="6d12f-119">Write in active voice.</span></span> <span data-ttu-id="6d12f-120">Por exemplo, "usar o objeto TimeSpan..." é muito mais claro do que "o objeto TimeSpan pode ser usado para..."</span><span class="sxs-lookup"><span data-stu-id="6d12f-120">For example, "Use the TimeSpan object..." is much clearer than "the TimeSpan object can be used to..."</span></span>

- <span data-ttu-id="6d12f-121">Evite o verbo "display" ao descrever os cmdlets que obtêm objetos.</span><span class="sxs-lookup"><span data-stu-id="6d12f-121">Avoid the verb "display" when describing cmdlets that get objects.</span></span> <span data-ttu-id="6d12f-122">Embora o Windows PowerShell exiba dados de cmdlet, é importante introduzir os usuários ao conceito que o cmdlet retorna .NET Framework objetos cujos dados podem não ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="6d12f-122">Although Windows PowerShell displays cmdlet data, it is important to introduce users to the concept that the cmdlet returns .NET Framework objects whose data may not be displayed.</span></span> <span data-ttu-id="6d12f-123">Se você enfatizar a exibição, o usuário pode não perceber que o cmdlet pode ter retornado muitas outras propriedades e métodos úteis que não são exibidos.</span><span class="sxs-lookup"><span data-stu-id="6d12f-123">If you emphasize the display, the user might not realize that the cmdlet may have returned many other useful properties and methods that are not displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d12f-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6d12f-124">See Also</span></span>

 [<span data-ttu-id="6d12f-125">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d12f-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
