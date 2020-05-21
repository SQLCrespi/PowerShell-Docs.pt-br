---
title: Como nomear um arquivo CAB de ajuda atualizável | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de302da0-c17a-4d31-a8ef-14a626738993
caps.latest.revision: 7
ms.openlocfilehash: a253f98d213f797a659affb1560907bb99a045d3
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560552"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="e2823-102">Como nomear um arquivo CAB de ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="e2823-102">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="e2823-103">Este tópico explica o formato de nome necessário para o gabinete de ajuda atualizável (. Arquivos CAB).</span><span class="sxs-lookup"><span data-stu-id="e2823-103">This topic explains the required name format for the Updatable Help cabinet (.CAB) files.</span></span>

## <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="e2823-104">Como nomear um arquivo CAB de ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="e2823-104">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="e2823-105">Um gabinete atualizável (. CAB) deve ter um nome com o formato a seguir.</span><span class="sxs-lookup"><span data-stu-id="e2823-105">A Updatable cabinet (.CAB) file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

<span data-ttu-id="e2823-106">Os elementos do nome são os seguintes.</span><span class="sxs-lookup"><span data-stu-id="e2823-106">The elements of the name are as follows.</span></span>

<span data-ttu-id="e2823-107">ModuleName o valor da propriedade **Name** do objeto **ModuleInfo** que o cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) retorna.</span><span class="sxs-lookup"><span data-stu-id="e2823-107">ModuleName The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

<span data-ttu-id="e2823-108">ModuleGUID o valor da chave **GUID** no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="e2823-108">ModuleGUID The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="e2823-109">UICulture a cultura da interface do usuário dos arquivos de ajuda no arquivo CAB.</span><span class="sxs-lookup"><span data-stu-id="e2823-109">UICulture The UI culture of the help files in the CAB file.</span></span> <span data-ttu-id="e2823-110">Esse valor deve corresponder ao valor de um dos elementos **UICulture** no arquivo XML HelpInfo para o módulo.</span><span class="sxs-lookup"><span data-stu-id="e2823-110">This value must match the value of one of the **UICulture** elements in the HelpInfo XML file for the module.</span></span>

<span data-ttu-id="e2823-111">Por exemplo, se o nome do módulo for "TestModule", o GUID do módulo é 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 e a cultura da interface do usuário é "en-US", o nome do arquivo CAB seria:</span><span class="sxs-lookup"><span data-stu-id="e2823-111">For example, if the module name is "TestModule," the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, and the UI culture is "en-US", the name of the CAB file would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
