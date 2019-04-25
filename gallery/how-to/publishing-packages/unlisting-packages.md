---
ms.date: 06/12/2017
contributor: JKeithB
keywords: galeria,powershell,cmdlet,psgallery
title: Remover pacotes da lista
ms.openlocfilehash: fb66fd23dae1d4640056a764c31426f61f56d910
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62084106"
---
# <a name="unlisting-packages"></a><span data-ttu-id="78b52-103">Remover pacotes da lista</span><span class="sxs-lookup"><span data-stu-id="78b52-103">Unlisting Packages</span></span>

<span data-ttu-id="78b52-104">**Por que a remoção de um pacote da Galeria do PowerShell não é exposta como uma opção?**</span><span class="sxs-lookup"><span data-stu-id="78b52-104">**Why is removing a package from PowerShell Gallery not exposed as an option?**</span></span>

<span data-ttu-id="78b52-105">A Galeria do PowerShell não dá suporte à exclusão permanente dos pacotes pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="78b52-105">The PowerShell Gallery does not support users permanently deleting their packages.</span></span>
<span data-ttu-id="78b52-106">Isso permite que outros usuários possam usar as dependências de seus pacotes sem se preocupar com possíveis interrupções no futuro.</span><span class="sxs-lookup"><span data-stu-id="78b52-106">This enables others to take dependencies on your packages without worrying about possible breaks in the future.</span></span>
<span data-ttu-id="78b52-107">Por exemplo, se o módulo do Pester depender do módulo do Azure e o módulo do Azure for removido da galeria, o usuário não poderá mais usar o módulo do Pester.</span><span class="sxs-lookup"><span data-stu-id="78b52-107">For example, if the Pester module depends on the Azure module and the Azure module is removed from the gallery, then user can no longer uses the Pester module.</span></span>

<span data-ttu-id="78b52-108">No entanto, em vez de remover um pacote, você poderá removê-lo da lista.</span><span class="sxs-lookup"><span data-stu-id="78b52-108">Instead of removing an package, however, you can unlist it instead.</span></span>

<span data-ttu-id="78b52-109">**Qual o resultado da remoção de um pacote da lista na Galeria do PowerShell?**</span><span class="sxs-lookup"><span data-stu-id="78b52-109">**What does unlisting a package on PowerShell Gallery do?**</span></span>

<span data-ttu-id="78b52-110">A remoção de um pacote da lista como um módulo ou script na Galeria do PowerShell o removerá da guia Pacotes. Além disso, os pacotes removidos da lista não serão detectáveis usando a barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="78b52-110">Unlisting a package such as module or script on PowerShell Gallery will remove it from the Packages tab. In addition, unlisted packages will not be discoverable using the search bar.</span></span>
<span data-ttu-id="78b52-111">A única maneira de baixar um pacote removido da lista é especificar o nome exato e a versão do pacote.</span><span class="sxs-lookup"><span data-stu-id="78b52-111">The only way to download an unlisted package is to specify the exact name and version of the package.</span></span>
<span data-ttu-id="78b52-112">Por isso, a remoção de um pacote não interromperá outros módulos ou scripts que dependem dele.</span><span class="sxs-lookup"><span data-stu-id="78b52-112">Because of this, the unlisting of an package will not break other modules or scripts that depend on it.</span></span>

<span data-ttu-id="78b52-113">Para remover o pacote da lista, visite a página de detalhes do pacote e selecione "Excluir Pacote".</span><span class="sxs-lookup"><span data-stu-id="78b52-113">To unlist your package, visit the package details page and select 'Delete Module'.</span></span> <span data-ttu-id="78b52-114">Desmarque a caixa de seleção “Listado” e clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="78b52-114">Uncheck the 'Listed' checkbox, and click Save.</span></span>

<span data-ttu-id="78b52-115">**Como faço para remover um pacote?**</span><span class="sxs-lookup"><span data-stu-id="78b52-115">**How can I remove an package?**</span></span>

<span data-ttu-id="78b52-116">Se você tiver um cenário em que a exclusão do pacote é necessária, entre em contato com os Administradores da Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78b52-116">If you experience a scenario where package deletion is necessary, contact the PowerShell Gallery Administrators.</span></span>
<span data-ttu-id="78b52-117">Os cenários de exclusão válidos são:</span><span class="sxs-lookup"><span data-stu-id="78b52-117">Valid deletion scenarios are:</span></span>
- <span data-ttu-id="78b52-118">Problemas de violação de direitos autorais.</span><span class="sxs-lookup"><span data-stu-id="78b52-118">Issues of copyright infringement.</span></span>
- <span data-ttu-id="78b52-119">O pacote possui conteúdo potencialmente perigoso.</span><span class="sxs-lookup"><span data-stu-id="78b52-119">Package contains potentially harmful content.</span></span>
- <span data-ttu-id="78b52-120">O pacote contém dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="78b52-120">Package contains sensitive data.</span></span>

<span data-ttu-id="78b52-121">Para enviar uma Solicitação de Exclusão de Pacote aos Administradores da Galeria do PowerShell, visite a página de detalhes do pacote e selecione Entrar em Contato com o Suporte.</span><span class="sxs-lookup"><span data-stu-id="78b52-121">To submit a Delete Package Request to the PowerShell Gallery Administrators, visit your package's detail page and select Contact Support.</span></span>
