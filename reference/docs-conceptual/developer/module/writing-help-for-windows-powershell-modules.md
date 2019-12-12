---
title: Gravando ajuda para módulos do Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2b58fa5-01bc-426c-a043-5c700d6578e9
caps.latest.revision: 16
ms.openlocfilehash: 443bf5f693d2ab161668de25a1097347826cb5c2
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72360555"
---
# <a name="writing-help-for-windows-powershell-modules"></a><span data-ttu-id="5cd3e-102">Escrever ajuda para módulos do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5cd3e-102">Writing Help for Windows PowerShell Modules</span></span>

<span data-ttu-id="5cd3e-103">Os módulos do Windows PowerShell podem incluir tópicos de ajuda sobre o módulo e sobre os membros do módulo, como cmdlets, provedores, funções e scripts.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-103">Windows PowerShell modules can include Help topics about the module and about the module members, such as cmdlets, providers, functions and scripts.</span></span> <span data-ttu-id="5cd3e-104">O cmdlet `Get-Help` exibe os tópicos de ajuda do módulo no mesmo formato que exibe a ajuda para outros itens do Windows PowerShell, e os usuários usam comandos de `Get-Help` padrão para obter os tópicos da ajuda.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-104">The `Get-Help` cmdlet displays the module Help topics in the same format as it displays Help for other Windows PowerShell items, and users use standard `Get-Help` commands to get the Help topics.</span></span>

<span data-ttu-id="5cd3e-105">Este documento explica o formato e o posicionamento correto dos tópicos de ajuda do módulo e sugere diretrizes para o conteúdo da ajuda do módulo.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-105">This document explains the format and correct placement of module Help topics, and it suggests guidelines for module Help content.</span></span>

## <a name="types-of-module-help"></a><span data-ttu-id="5cd3e-106">Tipos de ajuda do módulo</span><span class="sxs-lookup"><span data-stu-id="5cd3e-106">Types of Module Help</span></span>

<span data-ttu-id="5cd3e-107">Um módulo pode incluir os seguintes tipos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-107">A module can include the following types of Help.</span></span>

- <span data-ttu-id="5cd3e-108">**Ajuda do cmdlet**.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-108">**Cmdlet Help**.</span></span> <span data-ttu-id="5cd3e-109">Os tópicos de ajuda que descrevem os cmdlets em um módulo são arquivos XML que usam o esquema de ajuda de comando</span><span class="sxs-lookup"><span data-stu-id="5cd3e-109">The Help topics that describe cmdlets in a module are XML files that use the command help schema</span></span>

- <span data-ttu-id="5cd3e-110">**Ajuda do provedor**.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-110">**Provider Help**.</span></span> <span data-ttu-id="5cd3e-111">Os tópicos de ajuda que descrevem provedores em um módulo são arquivos XML que usam o esquema de ajuda do provedor.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-111">The Help topics that describe providers in a module are XML files that use the provider help schema.</span></span>

- <span data-ttu-id="5cd3e-112">**Ajuda da função**.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-112">**Function Help**.</span></span> <span data-ttu-id="5cd3e-113">Os tópicos de ajuda que descrevem as funções em um módulo podem ser arquivos XML que usam o esquema de ajuda de comando ou tópicos de ajuda baseados em comentários dentro da função, ou o script ou o módulo de script</span><span class="sxs-lookup"><span data-stu-id="5cd3e-113">The Help topics that describe functions in a module can be XML files that use the command help schema or comment-based Help topics within the function, or the script or script module</span></span>

- <span data-ttu-id="5cd3e-114">**Ajuda do script**.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-114">**Script Help**.</span></span> <span data-ttu-id="5cd3e-115">Os tópicos de ajuda que descrevem scripts em um módulo podem ser arquivos XML que usam o esquema de ajuda de comando ou tópicos de ajuda baseados em comentários no módulo script ou script.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-115">The Help topics that describe scripts in a module can be XML files that use the command help schema or comment-based Help topics in the script or script module.</span></span>

- <span data-ttu-id="5cd3e-116">**Ajuda conceitual ("sobre")** .</span><span class="sxs-lookup"><span data-stu-id="5cd3e-116">**Conceptual ("About") Help**.</span></span> <span data-ttu-id="5cd3e-117">Você pode usar um tópico de ajuda conceitual ("sobre") para descrever o módulo e seus membros e explicar como os membros podem ser usados juntos para executar tarefas.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-117">You can use a conceptual ("about") Help topic to describe the module and its members and to explain how the members can be used together to perform tasks.</span></span> <span data-ttu-id="5cd3e-118">Os tópicos de ajuda conceitual são arquivos de texto com codificação Unicode (UTF-8).</span><span class="sxs-lookup"><span data-stu-id="5cd3e-118">Conceptual Help topics are text files with Unicode (UTF-8) encoding.</span></span> <span data-ttu-id="5cd3e-119">O nome do arquivo deve usar o formato `about_<name>.help.txt`, como about_MyModule. help. txt.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-119">The file name must use the `about_<name>.help.txt` format, such as about_MyModule.help.txt.</span></span> <span data-ttu-id="5cd3e-120">Por padrão, o Windows PowerShell inclui mais de 100 desses conceitos conceituais sobre tópicos de ajuda e eles são formatados como o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-120">By default, Windows PowerShell includes over 100 of these conceptual About Help topics, and they are formatted like the following example.</span></span>

  ```
  TOPIC
      about_<subject or module name>

  SHORT DESCRIPTION
      A short, one-line description of the topic contents.

  LONG DESCRIPTION
      A detailed, full description of the subject or purpose of the module.

  EXAMPLES
      Examples of how to use the module or how the subject feature works in practice.

  KEYWORDS
      Terms or titles on which you might expect your users to search for the information in this topic.

  SEE ALSO
      Text-only references for further reading. Hyperlinks cannot work in the Windows PowerShell console.

  ```

## <a name="placement-of-module-help"></a><span data-ttu-id="5cd3e-121">Posicionamento da ajuda do módulo</span><span class="sxs-lookup"><span data-stu-id="5cd3e-121">Placement of Module Help</span></span>

<span data-ttu-id="5cd3e-122">O cmdlet `Get-Help` procura arquivos de tópico da ajuda do módulo em subdiretórios específicos do idioma do diretório do módulo.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-122">The `Get-Help` cmdlet looks for module Help topic files in language-specific subdirectories of the module directory.</span></span>

<span data-ttu-id="5cd3e-123">Por exemplo, o diagrama de estrutura de diretório a seguir mostra o local dos tópicos de ajuda para o módulo SampleModule.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-123">For example, the following directory structure diagram shows the location of the Help topics for the SampleModule module.</span></span>

```
<ModulePath>
         \SampleModule
               \<en-US>
                     \about_SampleModule.help.txt
                     \SampleModule.dll-help.xml
                     \SampleNestedModule.dll-help.xml
               \<fr-FR>
                     \about_SampleModule.help.txt
                     \SampleModule.dll-help.xml
                     \SampleNestedModule.dll-help.xml

```

> [!NOTE]
> <span data-ttu-id="5cd3e-124">No exemplo, o espaço reservado *\<ModulePath >* representa um dos caminhos na variável de ambiente `PSModulePath`, como $Home \documents\modules, $pshome \modules ou um caminho personalizado que o usuário especifica.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-124">In the example, the *\<ModulePath>* placeholder represents one of the paths in the `PSModulePath` environment variable, such as $home\Documents\Modules, $pshome\Modules, or a custom path that the user specifies.</span></span>

## <a name="getting-module-help"></a><span data-ttu-id="5cd3e-125">Obtendo ajuda do módulo</span><span class="sxs-lookup"><span data-stu-id="5cd3e-125">Getting Module Help</span></span>

<span data-ttu-id="5cd3e-126">Quando um usuário importa um módulo para uma sessão, os tópicos de ajuda para esse módulo são importados para a sessão junto com o módulo.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-126">When a user imports a module into a session, the Help topics for that module are imported into the session along with the module.</span></span> <span data-ttu-id="5cd3e-127">Você pode listar os arquivos de tópico da ajuda no valor da chave FileList no manifesto do módulo, mas os tópicos da ajuda não são afetados pelo cmdlet `Export-ModuleMember`.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-127">You can list the Help topic files in the value of the FileList key in the module manifest, but Help topics are not affected by the `Export-ModuleMember` cmdlet.</span></span>

<span data-ttu-id="5cd3e-128">Você pode fornecer tópicos de ajuda de módulo em diferentes idiomas.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-128">You can provide module Help topics in different languages.</span></span> <span data-ttu-id="5cd3e-129">O cmdlet `Get-Help` exibe automaticamente tópicos de ajuda do módulo no idioma especificado para o usuário atual no item opções regionais e de idioma no painel de controle.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-129">The `Get-Help` cmdlet automatically displays module Help topics in the language that is specified for the current user in the Regional and Language Options item in Control Panel.</span></span> <span data-ttu-id="5cd3e-130">No Windows Vista e versões posteriores do Windows, `Get-Help` pesquisa os tópicos da ajuda em subdiretórios específicos do idioma do diretório do módulo de acordo com os padrões de fallback de idioma estabelecidos para o Windows.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-130">In Windows Vista and later versions of Windows, `Get-Help` searches for the Help topics in language-specific subdirectories of the module directory in accordance with the language fallback standards established for Windows.</span></span>

<span data-ttu-id="5cd3e-131">A partir do Windows PowerShell 3,0, a execução de um comando `Get-Help` para um cmdlet ou função dispara a importação automática do módulo.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-131">Beginning in Windows PowerShell 3.0, running a `Get-Help` command for a cmdlet or function triggers automatic importing of the module.</span></span> <span data-ttu-id="5cd3e-132">O cmdlet `Get-Help` exibe imediatamente o conteúdo dos tópicos da ajuda no módulo.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-132">The `Get-Help` cmdlet immediately displays the contents of the help topics in the module.</span></span>

<span data-ttu-id="5cd3e-133">Se o módulo não contiver tópicos de ajuda e não houver tópicos de ajuda para os comandos no módulo no computador do usuário, `Get-Help` exibirá a ajuda gerada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-133">If the module does not contain help topics and there are no help topics for the commands in the module on the user's computer, `Get-Help` displays auto-generated help.</span></span> <span data-ttu-id="5cd3e-134">A ajuda gerada automaticamente inclui a sintaxe do comando, os parâmetros e os tipos de entrada e saída, mas não inclui nenhuma descrição.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-134">The auto-generated help includes the command syntax, parameters, and input and output types, but does not include any descriptions.</span></span> <span data-ttu-id="5cd3e-135">A ajuda gerada automaticamente inclui um texto que orienta o usuário a tentar usar o cmdlet `Update-Help` para baixar a ajuda do comando da Internet ou de um compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-135">The auto-generated help includes text that directs the user to try to use the `Update-Help` cmdlet to download help for the command from the Internet or a file share.</span></span> <span data-ttu-id="5cd3e-136">Ele também recomenda o uso do parâmetro **online** do cmdlet `Get-Help` para obter a versão online do tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-136">It also recommends using the **Online** parameter of the `Get-Help` cmdlet to get the online version of the help topic.</span></span>

## <a name="supporting-updatable-help"></a><span data-ttu-id="5cd3e-137">Suporte à ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="5cd3e-137">Supporting Updatable Help</span></span>

<span data-ttu-id="5cd3e-138">Os usuários do Windows PowerShell 3,0 e versões posteriores do Windows PowerShell podem baixar e instalar arquivos de ajuda atualizados para um módulo da Internet ou de um compartilhamento de arquivos local.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-138">Users of Windows PowerShell 3.0 and later versions of Windows PowerShell can download and install updated help files for a module from the Internet or from a local file share.</span></span> <span data-ttu-id="5cd3e-139">Os cmdlets `Update-Help` e `Save-Help` ocultam os detalhes de gerenciamento do usuário.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-139">The `Update-Help` and `Save-Help` cmdlets hide the management details from the user.</span></span> <span data-ttu-id="5cd3e-140">Os usuários executam o cmdlet `Update-Help` e, em seguida, usam o cmdlet `Get-Help` para ler os arquivos de ajuda mais recentes do módulo no prompt de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-140">Users run the `Update-Help` cmdlet and then use the `Get-Help` cmdlet to read the newest help files for the module at the Windows PowerShell command prompt.</span></span> <span data-ttu-id="5cd3e-141">Os usuários não precisam reiniciar o Windows ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-141">Users do not need to restart Windows or Windows PowerShell.</span></span>

<span data-ttu-id="5cd3e-142">Os usuários atrás de firewalls e aqueles sem acesso à Internet também podem usar a ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-142">Users behind firewalls and those without Internet access can use Updatable Help, as well.</span></span> <span data-ttu-id="5cd3e-143">Os administradores com acesso à Internet usam o cmdlet `Save-Help` para baixar e instalar os arquivos de ajuda mais recentes em um compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-143">Administrators with Internet access use the `Save-Help` cmdlet to download and install the newest help files to a file share.</span></span> <span data-ttu-id="5cd3e-144">Em seguida, os usuários usam o parâmetro **path** do cmdlet `Update-Help` para obter os arquivos de ajuda mais recentes do compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-144">Then, users use the **Path** parameter of the `Update-Help` cmdlet to get the newest help files from the file share.</span></span>

<span data-ttu-id="5cd3e-145">Os autores de módulo podem incluir arquivos de ajuda no módulo e usar a ajuda atualizável para atualizar os arquivos de ajuda ou omitir os arquivos de ajuda do módulo e usar a ajuda atualizável para instalar e atualizá-los.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-145">Module authors can include help files in the module and use Updatable Help to update the help files, or omit help files from the module and use Updatable Help both to install and to update them.</span></span>

<span data-ttu-id="5cd3e-146">Para obter mais informações sobre a ajuda atualizável, consulte [suporte à ajuda atualizável](./supporting-updatable-help.md).</span><span class="sxs-lookup"><span data-stu-id="5cd3e-146">For more information about Updatable Help, see [Supporting Updatable Help](./supporting-updatable-help.md).</span></span>

## <a name="supporting-online-help"></a><span data-ttu-id="5cd3e-147">Suporte à ajuda online</span><span class="sxs-lookup"><span data-stu-id="5cd3e-147">Supporting Online Help</span></span>

<span data-ttu-id="5cd3e-148">Os usuários que não podem ou não instalar arquivos de ajuda atualizados em seus computadores geralmente dependem da versão online dos tópicos de ajuda do módulo.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-148">Users who cannot or do not install updated help files on their computers often rely on the online version of module help topics.</span></span> <span data-ttu-id="5cd3e-149">O parâmetro **online** do cmdlet `Get-Help` abre a versão online de um cmdlet ou tópico de ajuda de função avançada para o usuário em seu navegador de Internet padrão.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-149">The **Online** parameter of the `Get-Help` cmdlet opens the online version of a cmdlet or advanced function help topic for the user in their default Internet browser.</span></span>

<span data-ttu-id="5cd3e-150">O cmdlet `Get-Help` usa o valor da propriedade **HelpUri** do cmdlet ou da função para localizar a versão online do tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-150">The `Get-Help` cmdlet uses the value of the **HelpUri** property of the cmdlet or function to find the online version of the help topic.</span></span>

<span data-ttu-id="5cd3e-151">A partir do Windows PowerShell 3,0, você pode ajudar os usuários a localizar a versão online dos tópicos de ajuda do cmdlet e da função definindo o atributo HelpUri na classe cmdlet ou a propriedade **HelpUri** do atributo **CmdletBinding** .</span><span class="sxs-lookup"><span data-stu-id="5cd3e-151">Beginning in Windows PowerShell 3.0, you can help users find the online version of cmdlet and function help topics by defining the HelpUri attribute on the cmdlet class or the **HelpUri** property of the **CmdletBinding** attribute.</span></span> <span data-ttu-id="5cd3e-152">O valor do atributo é o valor da propriedade **HelpUri** do cmdlet ou da função.</span><span class="sxs-lookup"><span data-stu-id="5cd3e-152">The value of the attribute is the value of the **HelpUri** property of the cmdlet or function.</span></span>

<span data-ttu-id="5cd3e-153">Para obter mais informações, consulte [suporte à ajuda online](./supporting-online-help.md).</span><span class="sxs-lookup"><span data-stu-id="5cd3e-153">For more information, see [Supporting Online Help](./supporting-online-help.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5cd3e-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5cd3e-154">See Also</span></span>

[<span data-ttu-id="5cd3e-155">Escrevendo um módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5cd3e-155">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

[<span data-ttu-id="5cd3e-156">Suporte à ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="5cd3e-156">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)

[<span data-ttu-id="5cd3e-157">Suporte à ajuda online</span><span class="sxs-lookup"><span data-stu-id="5cd3e-157">Supporting Online Help</span></span>](./supporting-online-help.md)