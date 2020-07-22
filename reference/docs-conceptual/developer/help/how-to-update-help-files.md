---
title: Como atualizar os arquivos de ajuda
ms.date: 09/12/2016
ms.openlocfilehash: 80f7c8865729515de98648765fa36ce540e00162
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892941"
---
# <a name="how-to-update-help-files"></a><span data-ttu-id="502b3-102">Como atualizar os arquivos de ajuda</span><span class="sxs-lookup"><span data-stu-id="502b3-102">How to Update Help Files</span></span>

<span data-ttu-id="502b3-103">Este tópico explica como atualizar arquivos de ajuda para um módulo que dá suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="502b3-103">This topic explains how to update help files for a module that supports Updatable Help.</span></span>

## <a name="updating-help-files"></a><span data-ttu-id="502b3-104">Atualizando arquivos de ajuda</span><span class="sxs-lookup"><span data-stu-id="502b3-104">Updating Help Files</span></span>

<span data-ttu-id="502b3-105">Há muitas razões para atualizar os arquivos de ajuda, como corrigir erros, esclarecer um conceito, responder a uma pergunta frequente, adicionar novos arquivos ou adicionar novos e melhores exemplos.</span><span class="sxs-lookup"><span data-stu-id="502b3-105">There are many reasons to update help files, such as correcting errors, clarifying a concept, answering a frequently-asked question, adding new files, or adding new and better examples.</span></span>

<span data-ttu-id="502b3-106">Para atualizar um arquivo de ajuda:</span><span class="sxs-lookup"><span data-stu-id="502b3-106">To update a help file:</span></span>

1. <span data-ttu-id="502b3-107">Altere os arquivos.</span><span class="sxs-lookup"><span data-stu-id="502b3-107">Change the files.</span></span>
1. <span data-ttu-id="502b3-108">Traduza os arquivos em outras culturas de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="502b3-108">Translate the files into other UI cultures.</span></span>
1. <span data-ttu-id="502b3-109">Coletar todos os arquivos de ajuda (novos, alterados e inalterados) para o módulo em cada cultura de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="502b3-109">Collect all help files (new, changed, and unchanged) for the module in each UI culture.</span></span>
1. <span data-ttu-id="502b3-110">Valide os arquivos em relação ao esquema XML.</span><span class="sxs-lookup"><span data-stu-id="502b3-110">Validate the files against the XML schema.</span></span>
1. <span data-ttu-id="502b3-111">Recrie os arquivos CAB para cada cultura de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="502b3-111">Rebuild the CAB files for each UI culture.</span></span>
1. <span data-ttu-id="502b3-112">No arquivo XML HelpInfo, aumente os números de versão do arquivo CAB para cada cultura de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="502b3-112">In the HelpInfo XML file, increment the version numbers of the CAB file for each UI culture.</span></span>
1. <span data-ttu-id="502b3-113">Carregue os novos arquivos CAB no local especificado pelo valor do elemento **HelpContentUri** no arquivo XML HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="502b3-113">Upload the new CAB files to the location that is specified by the value of the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="502b3-114">Substitua os arquivos CAB mais antigos pelos novos arquivos CAB.</span><span class="sxs-lookup"><span data-stu-id="502b3-114">Replace the older CAB files with the new CAB files.</span></span>
1. <span data-ttu-id="502b3-115">Carregue o arquivo XML HelpInfo atualizado no local especificado pela chave **HelpInfoUri** no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="502b3-115">Upload the updated HelpInfo XML file to the location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="502b3-116">Substitua o arquivo XML HelpInfo mais antigo pelo novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="502b3-116">Replace the older HelpInfo XML file with the new file.</span></span>
