---
ms.date: 09/12/2016
ms.topic: reference
title: Como nomear um arquivo CAB de ajuda atualizável
description: Como nomear um arquivo CAB de ajuda atualizável
ms.openlocfilehash: 57ea188d07a382d1a986a49c9ae22c5919dafa8e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658924"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="17137-103">Como nomear um arquivo CAB de ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="17137-103">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="17137-104">Este tópico explica o formato de nome necessário para os arquivos do gabinete de ajuda atualizável ( `.CAB` ).</span><span class="sxs-lookup"><span data-stu-id="17137-104">This topic explains the required name format for the Updatable Help cabinet (`.CAB`) files.</span></span>

## <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="17137-105">Como nomear um arquivo CAB de ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="17137-105">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="17137-106">Um arquivo de gabinete atualizável ( `.CAB` ) deve ter um nome com o formato a seguir.</span><span class="sxs-lookup"><span data-stu-id="17137-106">A Updatable cabinet (`.CAB`) file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

<span data-ttu-id="17137-107">Os elementos do nome são os seguintes.</span><span class="sxs-lookup"><span data-stu-id="17137-107">The elements of the name are as follows.</span></span>

- <span data-ttu-id="17137-108">`<ModuleName>` -O valor da propriedade **Name** do objeto **ModuleInfo** que o cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) retorna.</span><span class="sxs-lookup"><span data-stu-id="17137-108">`<ModuleName>` -The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>
- <span data-ttu-id="17137-109">`<ModuleGUID>` -O valor da chave de **GUID** no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="17137-109">`<ModuleGUID>` - The value of the **GUID** key in the module manifest.</span></span>
- <span data-ttu-id="17137-110">`<UICulture>` -A cultura da interface do usuário dos arquivos de ajuda no arquivo CAB.</span><span class="sxs-lookup"><span data-stu-id="17137-110">`<UICulture>` - The UI culture of the help files in the CAB file.</span></span> <span data-ttu-id="17137-111">Esse valor deve corresponder ao valor de um dos elementos **UICulture** no arquivo XML HelpInfo para o módulo.</span><span class="sxs-lookup"><span data-stu-id="17137-111">This value must match the value of one of the **UICulture** elements in the HelpInfo XML file for the module.</span></span>

<span data-ttu-id="17137-112">Por exemplo, se o nome do módulo for "TestModule", o GUID do módulo é 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 e a cultura da interface do usuário é "en-US", o nome do arquivo CAB seria:</span><span class="sxs-lookup"><span data-stu-id="17137-112">For example, if the module name is "TestModule," the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, and the UI culture is "en-US", the name of the CAB file would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
