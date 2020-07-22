---
title: Como nomear um arquivo XML HelpInfo
ms.date: 09/12/2016
ms.openlocfilehash: 9505a7f66852a569d25ac0c1be86e68f870a7930
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892924"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="6d8a8-102">Como nomear um arquivo XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="6d8a8-102">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="6d8a8-103">Este tópico explica o formato de nome necessário para os arquivos de informações de ajuda atualizáveis, normalmente conhecidos como arquivos XML HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="6d8a8-103">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="6d8a8-104">Como nomear um arquivo XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="6d8a8-104">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="6d8a8-105">Um arquivo XML HelpInfo deve ter um nome com o formato a seguir.</span><span class="sxs-lookup"><span data-stu-id="6d8a8-105">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="6d8a8-106">Os elementos do nome são os seguintes.</span><span class="sxs-lookup"><span data-stu-id="6d8a8-106">The elements of the name are as follows.</span></span>

- <span data-ttu-id="6d8a8-107">`<ModuleName>`-O valor da propriedade **Name** do objeto **ModuleInfo** que o cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) retorna.</span><span class="sxs-lookup"><span data-stu-id="6d8a8-107">`<ModuleName>` - The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

- <span data-ttu-id="6d8a8-108">`<ModuleGUID>`-O valor da chave de **GUID** no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="6d8a8-108">`<ModuleGUID>` - The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="6d8a8-109">Por exemplo, se o nome do módulo for "TestModule" e o GUID do módulo for 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, o nome do arquivo XML HelpInfo para o módulo seria:</span><span class="sxs-lookup"><span data-stu-id="6d8a8-109">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
