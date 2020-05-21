---
title: Como atualizar os arquivos de ajuda | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495869a6-080e-4401-9ddc-16edd2f86857
caps.latest.revision: 6
ms.openlocfilehash: 35b3fd696419d0135fd6f662223e6c8586df443a
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561383"
---
# <a name="how-to-update-help-files"></a><span data-ttu-id="4c7fd-102">Como atualizar os arquivos de ajuda</span><span class="sxs-lookup"><span data-stu-id="4c7fd-102">How to Update Help Files</span></span>

<span data-ttu-id="4c7fd-103">Este tópico explica como atualizar arquivos de ajuda para um módulo que dá suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="4c7fd-103">This topic explains how to update help files for a module that supports Updatable Help.</span></span>

## <a name="updating-help-files"></a><span data-ttu-id="4c7fd-104">Atualizando arquivos de ajuda</span><span class="sxs-lookup"><span data-stu-id="4c7fd-104">Updating Help Files</span></span>

<span data-ttu-id="4c7fd-105">Há muitas razões para atualizar os arquivos de ajuda, como corrigir erros, esclarecer um conceito, responder a uma pergunta frequente, adicionar novos arquivos ou adicionar novos e melhores exemplos.</span><span class="sxs-lookup"><span data-stu-id="4c7fd-105">There are many reasons to update help files, such as correcting errors, clarifying a concept, answering a frequently-asked question, adding new files, or adding new and better examples.</span></span>

<span data-ttu-id="4c7fd-106">Para atualizar um arquivo de ajuda:</span><span class="sxs-lookup"><span data-stu-id="4c7fd-106">To update a help file:</span></span>

1. <span data-ttu-id="4c7fd-107">Altere os arquivos.</span><span class="sxs-lookup"><span data-stu-id="4c7fd-107">Change the files.</span></span>

2. <span data-ttu-id="4c7fd-108">Traduza os arquivos em outras culturas de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="4c7fd-108">Translate the files into other UI cultures.</span></span>

3. <span data-ttu-id="4c7fd-109">Coletar todos os arquivos de ajuda (novos, alterados e inalterados) para o módulo em cada cultura de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="4c7fd-109">Collect all help files (new, changed, and unchanged) for the module in each UI culture.</span></span>

4. <span data-ttu-id="4c7fd-110">Valide os arquivos em relação ao esquema XML.</span><span class="sxs-lookup"><span data-stu-id="4c7fd-110">Validate the files against the XML schema.</span></span>

5. <span data-ttu-id="4c7fd-111">Recrie os arquivos CAB para cada cultura de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="4c7fd-111">Rebuild the CAB files for each UI culture.</span></span>

6. <span data-ttu-id="4c7fd-112">No arquivo XML HelpInfo, aumente os números de versão do arquivo CAB para cada cultura de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="4c7fd-112">In the HelpInfo XML file, increment the version numbers of the CAB file for each UI culture.</span></span>

7. <span data-ttu-id="4c7fd-113">Carregue os novos arquivos CAB no local especificado pelo valor do elemento **HelpContentUri** no arquivo XML HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="4c7fd-113">Upload the new CAB files to the location that is specified by the value of the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="4c7fd-114">Substitua os arquivos CAB mais antigos pelos novos arquivos CAB.</span><span class="sxs-lookup"><span data-stu-id="4c7fd-114">Replace the older CAB files with the new CAB files.</span></span>

8. <span data-ttu-id="4c7fd-115">Carregue o arquivo XML HelpInfo atualizado no local especificado pela chave **HelpInfoUri** no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="4c7fd-115">Upload the updated HelpInfo XML file to the location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="4c7fd-116">Substitua o arquivo XML HelpInfo mais antigo pelo novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="4c7fd-116">Replace the older HelpInfo XML file with the new file.</span></span>
