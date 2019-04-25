---
title: Como adicionar o nome do Cmdlet e a Sinopse a um tópico de ajuda | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d0e1eb1-a962-4406-9625-175cfa3364ad
caps.latest.revision: 10
ms.openlocfilehash: f142548be473da15e702f4fa01835609d75b9d51
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083324"
---
# <a name="how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic"></a><span data-ttu-id="7c2a3-102">Como adicionar a sinopse e o nome do cmdlet a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="7c2a3-102">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>

<span data-ttu-id="7c2a3-103">Esta seção descreve como adicionar conteúdo que é exibido nas seções de nome e a Sinopse da Ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-103">This section describes how to add content that is displayed in the NAME and SYNOPSIS sections of the cmdlet help.</span></span> <span data-ttu-id="7c2a3-104">No arquivo de Ajuda, esse conteúdo é adicionado para o nó de comando para cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-104">In the Help file, this content is added to the Command node for each cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="7c2a3-105">Para obter uma visão completa de um arquivo de Ajuda, abra um dos arquivos dll Help.xml localizado no diretório de instalação do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-105">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="7c2a3-106">Por exemplo, o arquivo de Microsoft.PowerShell.Commands.Management.dll Help.xml contém conteúdo para vários dos cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-106">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="to-add-the-cmdlet-name-and-a-synopsis"></a><span data-ttu-id="7c2a3-107">Para adicionar o nome do Cmdlet e uma sinopse</span><span class="sxs-lookup"><span data-stu-id="7c2a3-107">To Add the Cmdlet Name and a Synopsis</span></span>

- <span data-ttu-id="7c2a3-108">O cmdlet Help pode exibir duas descrições para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-108">The cmdlet Help can display two descriptions for the cmdlet.</span></span> <span data-ttu-id="7c2a3-109">A descrição a primeira é uma breve descrição que é conhecida como a Sinopse.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-109">The first description is a short description that is referred to as the synopsis.</span></span> <span data-ttu-id="7c2a3-110">A segunda descrição é uma descrição mais detalhada que é abordada [adicionando a descrição detalhada para um tópico de Ajuda do Cmdlet](./how-to-add-a-cmdlet-description.md).</span><span class="sxs-lookup"><span data-stu-id="7c2a3-110">The second description is a more detailed description that is discussed in [Adding the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span> <span data-ttu-id="7c2a3-111">Ambas as essas descrições devem ser gravadas como um único parágrafo.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-111">Both these descriptions should be written as a single paragraph.</span></span>

- <span data-ttu-id="7c2a3-112">Na Sinopse não se repetem o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-112">In the synopsis do not repeat the cmdlet name.</span></span> <span data-ttu-id="7c2a3-113">Informando ao usuário que o cmdlet Get-Server obtém um servidor é breve, mas não informativos.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-113">Informing the user that the Get-Server cmdlet gets a server is brief, but not informative.</span></span> <span data-ttu-id="7c2a3-114">Em vez disso, usar sinônimos e adicionar detalhes à descrição.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-114">Instead, use synonyms and add details to the description.</span></span>

  <span data-ttu-id="7c2a3-115">Exemplo: "Obtém um objeto que representa um computador local ou remoto."</span><span class="sxs-lookup"><span data-stu-id="7c2a3-115">Example: "Gets an object that represents a local or remote computer."</span></span>

- <span data-ttu-id="7c2a3-116">Use verbos simples como "get", "criar" e "alterar" a Sinopse.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-116">Use simple verbs like "get", "create", and "change" in the synopsis.</span></span> <span data-ttu-id="7c2a3-117">Evite usar "set" porque é vaga e palavras bonitas como "modificam."</span><span class="sxs-lookup"><span data-stu-id="7c2a3-117">Avoid using "set" because it is vague, and fancy words such as "modify."</span></span>

  <span data-ttu-id="7c2a3-118">Exemplo: "Obtém informações sobre a assinatura Authenticode em um arquivo".</span><span class="sxs-lookup"><span data-stu-id="7c2a3-118">Example: "Gets information about the Authenticode signature in a file."</span></span>

- <span data-ttu-id="7c2a3-119">Gravar em voz ativa.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-119">Write in active voice.</span></span> <span data-ttu-id="7c2a3-120">Por exemplo, "usar o objeto TimeSpan..." é bem mais claro de "objeto TimeSpan pode ser usado para..."</span><span class="sxs-lookup"><span data-stu-id="7c2a3-120">For example, "Use the TimeSpan object..." is much clearer than "the TimeSpan object can be used to..."</span></span>

- <span data-ttu-id="7c2a3-121">Evite o verbo "display" ao descrever os cmdlets que obter objetos.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-121">Avoid the verb "display" when describing cmdlets that get objects.</span></span> <span data-ttu-id="7c2a3-122">Embora o Windows PowerShell exibe dados de cmdlet, é importante apresentar a usuários o conceito de que o cmdlet retorna objetos do .NET Framework cujos dados podem não ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-122">Although Windows PowerShell displays cmdlet data, it is important to introduce users to the concept that the cmdlet returns .NET Framework objects whose data may not be displayed.</span></span> <span data-ttu-id="7c2a3-123">Se você enfatizar a exibição, o usuário talvez não tenha percebido que o cmdlet pode ter retornado muitas outras propriedades e métodos úteis que não são exibidos.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-123">If you emphasize the display, the user might not realize that the cmdlet may have returned many other useful properties and methods that are not displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c2a3-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7c2a3-124">See Also</span></span>

 [<span data-ttu-id="7c2a3-125">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c2a3-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)