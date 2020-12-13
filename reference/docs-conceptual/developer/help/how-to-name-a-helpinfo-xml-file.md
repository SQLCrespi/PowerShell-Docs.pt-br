---
ms.date: 09/12/2016
ms.topic: reference
title: Como nomear um arquivo XML HelpInfo
description: Como nomear um arquivo XML HelpInfo
ms.openlocfilehash: 55bc2ef9530fc457e4d9ddf18e79e7226c991663
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659040"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="fce5f-103">Como nomear um arquivo XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="fce5f-103">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="fce5f-104">Este tópico explica o formato de nome necessário para os arquivos de informações de ajuda atualizáveis, normalmente conhecidos como arquivos XML HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="fce5f-104">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="fce5f-105">Como nomear um arquivo XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="fce5f-105">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="fce5f-106">Um arquivo XML HelpInfo deve ter um nome com o formato a seguir.</span><span class="sxs-lookup"><span data-stu-id="fce5f-106">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="fce5f-107">Os elementos do nome são os seguintes.</span><span class="sxs-lookup"><span data-stu-id="fce5f-107">The elements of the name are as follows.</span></span>

- <span data-ttu-id="fce5f-108">`<ModuleName>` -O valor da propriedade **Name** do objeto **ModuleInfo** que o cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) retorna.</span><span class="sxs-lookup"><span data-stu-id="fce5f-108">`<ModuleName>` - The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

- <span data-ttu-id="fce5f-109">`<ModuleGUID>` -O valor da chave de **GUID** no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="fce5f-109">`<ModuleGUID>` - The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="fce5f-110">Por exemplo, se o nome do módulo for "TestModule" e o GUID do módulo for 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, o nome do arquivo XML HelpInfo para o módulo seria:</span><span class="sxs-lookup"><span data-stu-id="fce5f-110">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
