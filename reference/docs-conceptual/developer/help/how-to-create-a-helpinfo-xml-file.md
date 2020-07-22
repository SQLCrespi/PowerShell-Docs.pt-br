---
title: Como criar um arquivo XML HelpInfo
ms.date: 09/13/2016
ms.openlocfilehash: e395746e51309477bbcbff51b4591de3f73ce0db
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893298"
---
# <a name="how-to-create-a-helpinfo-xml-file"></a><span data-ttu-id="05a33-102">Como criar um arquivo XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="05a33-102">How to Create a HelpInfo XML File</span></span>

<span data-ttu-id="05a33-103">Estes tópicos nesta seção explicam como criar e popular um arquivo de informações de ajuda, normalmente conhecido como "arquivo XML HelpInfo", para o recurso de ajuda atualizável do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05a33-103">This topics in this section explains how to create and populate a help information file, commonly known as a "HelpInfo XML file," for the PowerShell Updatable Help feature.</span></span>

## <a name="helpinfo-xml-file-overview"></a><span data-ttu-id="05a33-104">Visão geral do arquivo XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="05a33-104">HelpInfo XML File Overview</span></span>

<span data-ttu-id="05a33-105">O arquivo XML HelpInfo é a principal fonte de informações sobre a ajuda atualizável para o módulo.</span><span class="sxs-lookup"><span data-stu-id="05a33-105">The HelpInfo XML file is the primary source of information about Updatable Help for the module.</span></span> <span data-ttu-id="05a33-106">Ele inclui o local dos arquivos de ajuda para os módulos, as culturas de interface do usuário com suporte e os números de versão que a ajuda atualizável usa para determinar se o usuário tem os arquivos de ajuda mais recentes.</span><span class="sxs-lookup"><span data-stu-id="05a33-106">It includes the location of the help files for the modules, the supported UI cultures, and the version numbers that Updatable Help uses to determine whether the user has the newest help files.</span></span>

<span data-ttu-id="05a33-107">Cada módulo tem apenas um arquivo XML HelpInfo, mesmo que o módulo inclua vários arquivos de ajuda para várias culturas de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="05a33-107">Each module has just one HelpInfo XML file, even if the module includes multiple help files for multiple UI cultures.</span></span> <span data-ttu-id="05a33-108">O autor do módulo cria o arquivo XML HelpInfo e o coloca no local da Internet que é especificado pela chave **HelpInfoUri** no manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="05a33-108">The module author creates the HelpInfo XML file and places it in the internet location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="05a33-109">Quando os arquivos de ajuda do módulo são atualizados e carregados, o autor do módulo atualiza o arquivo XML HelpInfo e substitui o arquivo XML HelpInfo original pela nova versão.</span><span class="sxs-lookup"><span data-stu-id="05a33-109">When the module help files are updated and uploaded, the module author updates the HelpInfo XML file and replaces the original HelpInfo XML file with the new version.</span></span>

<span data-ttu-id="05a33-110">É importante que o arquivo XML HelpInfo seja cuidadosamente mantido.</span><span class="sxs-lookup"><span data-stu-id="05a33-110">It is critical that the HelpInfo XML file is carefully maintained.</span></span> <span data-ttu-id="05a33-111">Se você carregar novos arquivos, mas esquecer de incrementar os números de versão, a ajuda atualizável não baixará os novos arquivos nos computadores dos usuários.</span><span class="sxs-lookup"><span data-stu-id="05a33-111">If you upload new files, but forget to increment the version numbers, Updatable Help will not download the new files to users' computers.</span></span> <span data-ttu-id="05a33-112">Se você adicionar arquivos de ajuda para uma nova cultura de interface do usuário, mas não atualizar o arquivo XML HelpInfo ou colocá-lo no local correto, a ajuda atualizável não baixará os novos arquivos.</span><span class="sxs-lookup"><span data-stu-id="05a33-112">if you add help files for a new UI culture, but don't update the HelpInfo XML file or place it in the correct location, Updatable Help will not download the new files.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="05a33-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="05a33-113">In this section</span></span>

<span data-ttu-id="05a33-114">Esta seção inclui os seguintes tópicos.</span><span class="sxs-lookup"><span data-stu-id="05a33-114">This section includes the following topics.</span></span>

- [<span data-ttu-id="05a33-115">Esquema XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="05a33-115">HelpInfo XML Schema</span></span>](./helpinfo-xml-schema.md)

- [<span data-ttu-id="05a33-116">Arquivo de exemplo XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="05a33-116">HelpInfo XML Sample File</span></span>](./helpinfo-xml-sample-file.md)

- [<span data-ttu-id="05a33-117">Como nomear um arquivo XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="05a33-117">How to Name a HelpInfo XML File</span></span>](./how-to-name-a-helpinfo-xml-file.md)

- [<span data-ttu-id="05a33-118">Como definir os números de versão do XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="05a33-118">How to Set HelpInfo XML Version Numbers</span></span>](./how-to-set-helpinfo-xml-version-numbers.md)

## <a name="see-also"></a><span data-ttu-id="05a33-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="05a33-119">See Also</span></span>

[<span data-ttu-id="05a33-120">Suporte à ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="05a33-120">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)
