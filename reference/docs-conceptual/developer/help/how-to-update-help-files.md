---
ms.date: 09/12/2016
ms.topic: reference
title: Como atualizar os arquivos de ajuda
description: Como atualizar os arquivos de ajuda
ms.openlocfilehash: 19bf501cf91b1eb5dabb334c2179953590b40232
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649593"
---
# <a name="how-to-update-help-files"></a><span data-ttu-id="55d0a-103">Como atualizar os arquivos de ajuda</span><span class="sxs-lookup"><span data-stu-id="55d0a-103">How to Update Help Files</span></span>

<span data-ttu-id="55d0a-104">Este tópico explica como atualizar arquivos de ajuda para um módulo que dá suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="55d0a-104">This topic explains how to update help files for a module that supports Updatable Help.</span></span>

## <a name="updating-help-files"></a><span data-ttu-id="55d0a-105">Atualizando arquivos de ajuda</span><span class="sxs-lookup"><span data-stu-id="55d0a-105">Updating Help Files</span></span>

<span data-ttu-id="55d0a-106">Há muitas razões para atualizar os arquivos de ajuda, como corrigir erros, esclarecer um conceito, responder a uma pergunta frequente, adicionar novos arquivos ou adicionar novos e melhores exemplos.</span><span class="sxs-lookup"><span data-stu-id="55d0a-106">There are many reasons to update help files, such as correcting errors, clarifying a concept, answering a frequently-asked question, adding new files, or adding new and better examples.</span></span>

<span data-ttu-id="55d0a-107">Para atualizar um arquivo de ajuda:</span><span class="sxs-lookup"><span data-stu-id="55d0a-107">To update a help file:</span></span>

1. <span data-ttu-id="55d0a-108">Altere os arquivos.</span><span class="sxs-lookup"><span data-stu-id="55d0a-108">Change the files.</span></span>
1. <span data-ttu-id="55d0a-109">Traduza os arquivos em outras culturas de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="55d0a-109">Translate the files into other UI cultures.</span></span>
1. <span data-ttu-id="55d0a-110">Coletar todos os arquivos de ajuda (novos, alterados e inalterados) para o módulo em cada cultura de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="55d0a-110">Collect all help files (new, changed, and unchanged) for the module in each UI culture.</span></span>
1. <span data-ttu-id="55d0a-111">Valide os arquivos em relação ao esquema XML.</span><span class="sxs-lookup"><span data-stu-id="55d0a-111">Validate the files against the XML schema.</span></span>
1. <span data-ttu-id="55d0a-112">Recrie os arquivos CAB para cada cultura de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="55d0a-112">Rebuild the CAB files for each UI culture.</span></span>
1. <span data-ttu-id="55d0a-113">No arquivo XML HelpInfo, aumente os números de versão do arquivo CAB para cada cultura de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="55d0a-113">In the HelpInfo XML file, increment the version numbers of the CAB file for each UI culture.</span></span>
1. <span data-ttu-id="55d0a-114">Carregue os novos arquivos CAB no local especificado pelo valor do elemento **HelpContentUri** no arquivo XML HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="55d0a-114">Upload the new CAB files to the location that is specified by the value of the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="55d0a-115">Substitua os arquivos CAB mais antigos pelos novos arquivos CAB.</span><span class="sxs-lookup"><span data-stu-id="55d0a-115">Replace the older CAB files with the new CAB files.</span></span>
1. <span data-ttu-id="55d0a-116">Carregue o arquivo XML HelpInfo atualizado no local especificado pela chave **HelpInfoUri** no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="55d0a-116">Upload the updated HelpInfo XML file to the location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="55d0a-117">Substitua o arquivo XML HelpInfo mais antigo pelo novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="55d0a-117">Replace the older HelpInfo XML file with the new file.</span></span>
