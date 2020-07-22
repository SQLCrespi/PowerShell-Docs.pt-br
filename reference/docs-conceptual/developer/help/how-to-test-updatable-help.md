---
title: Como testar a ajuda atualizável
ms.date: 09/12/2016
ms.openlocfilehash: 0602349f853fddd0cadae545eaf0302c150e3a28
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892958"
---
# <a name="how-to-test-updatable-help"></a><span data-ttu-id="c64fe-102">Como testar a ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="c64fe-102">How to Test Updatable Help</span></span>

<span data-ttu-id="c64fe-103">Este tópico descreve as abordagens para testar a ajuda atualizável para um módulo.</span><span class="sxs-lookup"><span data-stu-id="c64fe-103">This topic describes approaches to testing Updatable Help for a module.</span></span>

## <a name="using-verbose-to-detect-errors"></a><span data-ttu-id="c64fe-104">Usando o modo detalhado para detectar erros</span><span class="sxs-lookup"><span data-stu-id="c64fe-104">Using Verbose to Detect Errors</span></span>

<span data-ttu-id="c64fe-105">Depois de carregar o arquivo XML HelpInfo e os arquivos CAB para seu módulo, teste os arquivos executando um comando [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) com o parâmetro **Verbose** .</span><span class="sxs-lookup"><span data-stu-id="c64fe-105">After uploading the HelpInfo XML file and CAB files for your module, test the files by running an [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) command with the **Verbose** parameter.</span></span> <span data-ttu-id="c64fe-106">O parâmetro **Verbose** direciona `Update-Help` para relatar as etapas críticas em suas ações, da leitura da chave **HelpInfoUri** no manifesto do módulo para validar os tipos de arquivo no arquivo CAB desempacotado e colocar os arquivos no diretório de módulo específico do idioma.</span><span class="sxs-lookup"><span data-stu-id="c64fe-106">The **Verbose** parameter directs `Update-Help` to report the critical steps in its actions, from reading the **HelpInfoUri** key in the module manifest to validating the file types in the unpacked CAB file and placing the files in the language-specific module directory.</span></span>

<span data-ttu-id="c64fe-107">Quando todas as mensagens detalhadas forem resolvidas, execute um `Update-Help` comando com o parâmetro **debug** .</span><span class="sxs-lookup"><span data-stu-id="c64fe-107">When all verbose messages are resolved, run an `Update-Help` command with the **Debug** parameter.</span></span>
<span data-ttu-id="c64fe-108">Esse parâmetro deve detectar quaisquer problemas restantes com os arquivos de ajuda atualizáveis.</span><span class="sxs-lookup"><span data-stu-id="c64fe-108">This parameter should detect any remaining problems with the Updatable Help files.</span></span>
