---
title: Gravando ajuda para módulos do PowerShell
ms.date: 04/10/2020
ms.openlocfilehash: 115ea3f3c5941e74ed6ddbc8480d4a21576bc5c6
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893060"
---
# <a name="writing-help-for-powershell-modules"></a><span data-ttu-id="d5194-102">Gravando ajuda para módulos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5194-102">Writing Help for PowerShell Modules</span></span>

<span data-ttu-id="d5194-103">Os módulos do PowerShell podem incluir tópicos de ajuda sobre o módulo e sobre os membros do módulo, como cmdlets, provedores, funções e scripts.</span><span class="sxs-lookup"><span data-stu-id="d5194-103">PowerShell modules can include Help topics about the module and about the module members, such as cmdlets, providers, functions and scripts.</span></span> <span data-ttu-id="d5194-104">O `Get-Help` cmdlet exibe os tópicos de ajuda do módulo no mesmo formato que exibe a ajuda para outros itens do PowerShell, e os usuários usam `Get-Help` comandos padrão para obter os tópicos da ajuda.</span><span class="sxs-lookup"><span data-stu-id="d5194-104">The `Get-Help` cmdlet displays the module Help topics in the same format as it displays Help for other PowerShell items, and users use standard `Get-Help` commands to get the Help topics.</span></span>

<span data-ttu-id="d5194-105">Este documento explica o formato e o posicionamento correto dos tópicos de ajuda do módulo e sugere diretrizes para o conteúdo da ajuda do módulo.</span><span class="sxs-lookup"><span data-stu-id="d5194-105">This document explains the format and correct placement of module Help topics, and it suggests guidelines for module Help content.</span></span>

## <a name="types-of-module-help"></a><span data-ttu-id="d5194-106">Tipos de ajuda do módulo</span><span class="sxs-lookup"><span data-stu-id="d5194-106">Types of Module Help</span></span>

<span data-ttu-id="d5194-107">Um módulo pode incluir os seguintes tipos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="d5194-107">A module can include the following types of Help.</span></span>

- <span data-ttu-id="d5194-108">**Ajuda do cmdlet**.</span><span class="sxs-lookup"><span data-stu-id="d5194-108">**Cmdlet Help**.</span></span> <span data-ttu-id="d5194-109">Os tópicos de ajuda que descrevem os cmdlets em um módulo são arquivos XML que usam o esquema de ajuda de comando</span><span class="sxs-lookup"><span data-stu-id="d5194-109">The Help topics that describe cmdlets in a module are XML files that use the command help schema</span></span>

- <span data-ttu-id="d5194-110">**Ajuda do provedor**.</span><span class="sxs-lookup"><span data-stu-id="d5194-110">**Provider Help**.</span></span> <span data-ttu-id="d5194-111">Os tópicos de ajuda que descrevem provedores em um módulo são arquivos XML que usam o esquema de ajuda do provedor.</span><span class="sxs-lookup"><span data-stu-id="d5194-111">The Help topics that describe providers in a module are XML files that use the provider help schema.</span></span>

- <span data-ttu-id="d5194-112">**Ajuda da função**.</span><span class="sxs-lookup"><span data-stu-id="d5194-112">**Function Help**.</span></span> <span data-ttu-id="d5194-113">Os tópicos de ajuda que descrevem as funções em um módulo podem ser arquivos XML que usam o esquema de ajuda de comando ou tópicos de ajuda baseados em comentários dentro da função, ou o script ou o módulo de script</span><span class="sxs-lookup"><span data-stu-id="d5194-113">The Help topics that describe functions in a module can be XML files that use the command help schema or comment-based Help topics within the function, or the script or script module</span></span>

- <span data-ttu-id="d5194-114">**Ajuda do script**.</span><span class="sxs-lookup"><span data-stu-id="d5194-114">**Script Help**.</span></span> <span data-ttu-id="d5194-115">Os tópicos de ajuda que descrevem scripts em um módulo podem ser arquivos XML que usam o esquema de ajuda de comando ou tópicos de ajuda baseados em comentários no módulo script ou script.</span><span class="sxs-lookup"><span data-stu-id="d5194-115">The Help topics that describe scripts in a module can be XML files that use the command help schema or comment-based Help topics in the script or script module.</span></span>

- <span data-ttu-id="d5194-116">**Ajuda conceitual ("sobre")**.</span><span class="sxs-lookup"><span data-stu-id="d5194-116">**Conceptual ("About") Help**.</span></span> <span data-ttu-id="d5194-117">Você pode usar um tópico de ajuda conceitual ("sobre") para descrever o módulo e seus membros e explicar como os membros podem ser usados juntos para executar tarefas.</span><span class="sxs-lookup"><span data-stu-id="d5194-117">You can use a conceptual ("about") Help topic to describe the module and its members and to explain how the members can be used together to perform tasks.</span></span>
  <span data-ttu-id="d5194-118">Os tópicos de ajuda conceitual são arquivos de texto com codificação Unicode (UTF-8).</span><span class="sxs-lookup"><span data-stu-id="d5194-118">Conceptual Help topics are text files with Unicode (UTF-8) encoding.</span></span> <span data-ttu-id="d5194-119">O nome do arquivo deve usar o `about_<name>.help.txt` formato, como `about_MyModule.help.txt` .</span><span class="sxs-lookup"><span data-stu-id="d5194-119">The filename must use the `about_<name>.help.txt` format, such as `about_MyModule.help.txt`.</span></span> <span data-ttu-id="d5194-120">Por padrão, o PowerShell inclui mais de 100 desses conceitos conceituais sobre tópicos de ajuda e eles são formatados como o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="d5194-120">By default, PowerShell includes over 100 of these conceptual About Help topics, and they are formatted like the following example.</span></span>

  ```Output
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
      Text-only references for further reading. Hyperlinks cannot work in the PowerShell console.

  ```

<span data-ttu-id="d5194-121">Todos os arquivos de esquema podem ser encontrados na `$PSHOME\Schemas\PSMaml` pasta.</span><span class="sxs-lookup"><span data-stu-id="d5194-121">All of the schema files can be found in the `$PSHOME\Schemas\PSMaml` folder.</span></span>

## <a name="placement-of-module-help"></a><span data-ttu-id="d5194-122">Posicionamento da ajuda do módulo</span><span class="sxs-lookup"><span data-stu-id="d5194-122">Placement of Module Help</span></span>

<span data-ttu-id="d5194-123">O `Get-Help` cmdlet procura arquivos de tópico da ajuda do módulo em subdiretórios específicos do idioma do diretório do módulo.</span><span class="sxs-lookup"><span data-stu-id="d5194-123">The `Get-Help` cmdlet looks for module Help topic files in language-specific subdirectories of the module directory.</span></span>

<span data-ttu-id="d5194-124">Por exemplo, o diagrama de estrutura de diretório a seguir mostra o local dos tópicos de ajuda para o módulo SampleModule.</span><span class="sxs-lookup"><span data-stu-id="d5194-124">For example, the following directory structure diagram shows the location of the Help topics for the SampleModule module.</span></span>

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
> <span data-ttu-id="d5194-125">No exemplo, o `<ModulePath>` espaço reservado representa um dos caminhos na variável de `PSModulePath` ambiente, como `$HOME\Documents\Modules` , `$PSHOME\Modules` ou um caminho personalizado que o usuário especifica.</span><span class="sxs-lookup"><span data-stu-id="d5194-125">In the example, the `<ModulePath>` placeholder represents one of the paths in the `PSModulePath` environment variable, such as `$HOME\Documents\Modules`, `$PSHOME\Modules`, or a custom path that the user specifies.</span></span>

## <a name="getting-module-help"></a><span data-ttu-id="d5194-126">Obtendo ajuda do módulo</span><span class="sxs-lookup"><span data-stu-id="d5194-126">Getting Module Help</span></span>

<span data-ttu-id="d5194-127">Quando um usuário importa um módulo para uma sessão, os tópicos de ajuda para esse módulo são importados para a sessão junto com o módulo.</span><span class="sxs-lookup"><span data-stu-id="d5194-127">When a user imports a module into a session, the Help topics for that module are imported into the session along with the module.</span></span> <span data-ttu-id="d5194-128">Você pode listar os arquivos de tópico da ajuda no valor da chave FileList no manifesto do módulo, mas os tópicos da ajuda não são afetados pelo `Export-ModuleMember` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5194-128">You can list the Help topic files in the value of the FileList key in the module manifest, but Help topics are not affected by the `Export-ModuleMember` cmdlet.</span></span>

<span data-ttu-id="d5194-129">Você pode fornecer tópicos de ajuda de módulo em diferentes idiomas.</span><span class="sxs-lookup"><span data-stu-id="d5194-129">You can provide module Help topics in different languages.</span></span> <span data-ttu-id="d5194-130">O `Get-Help` cmdlet exibe automaticamente tópicos de ajuda do módulo no idioma especificado para o usuário atual no item opções regionais e de idioma no painel de controle.</span><span class="sxs-lookup"><span data-stu-id="d5194-130">The `Get-Help` cmdlet automatically displays module Help topics in the language that is specified for the current user in the Regional and Language Options item in Control Panel.</span></span> <span data-ttu-id="d5194-131">No Windows Vista e versões posteriores do Windows, `Get-Help` o procura os tópicos da ajuda em subdiretórios específicos do idioma do diretório do módulo de acordo com os padrões de fallback de linguagem estabelecidos para o Windows.</span><span class="sxs-lookup"><span data-stu-id="d5194-131">In Windows Vista and later versions of Windows, `Get-Help` searches for the Help topics in language-specific subdirectories of the module directory in accordance with the language fallback standards established for Windows.</span></span>

<span data-ttu-id="d5194-132">A partir do PowerShell 3,0, a execução de um `Get-Help` comando para um cmdlet ou função dispara a importação automática do módulo.</span><span class="sxs-lookup"><span data-stu-id="d5194-132">Beginning in PowerShell 3.0, running a `Get-Help` command for a cmdlet or function triggers automatic importing of the module.</span></span> <span data-ttu-id="d5194-133">O `Get-Help` cmdlet exibe imediatamente o conteúdo dos tópicos da ajuda no módulo.</span><span class="sxs-lookup"><span data-stu-id="d5194-133">The `Get-Help` cmdlet immediately displays the contents of the help topics in the module.</span></span>

<span data-ttu-id="d5194-134">Se o módulo não contiver tópicos de ajuda e não houver tópicos de ajuda para os comandos no módulo no computador do usuário, o `Get-Help` exibirá a ajuda gerada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d5194-134">If the module does not contain help topics and there are no help topics for the commands in the module on the user's computer, `Get-Help` displays auto-generated help.</span></span> <span data-ttu-id="d5194-135">A ajuda gerada automaticamente inclui a sintaxe do comando, os parâmetros e os tipos de entrada e saída, mas não inclui nenhuma descrição.</span><span class="sxs-lookup"><span data-stu-id="d5194-135">The auto-generated help includes the command syntax, parameters, and input and output types, but does not include any descriptions.</span></span> <span data-ttu-id="d5194-136">A ajuda gerada automaticamente inclui texto que orienta o usuário a tentar usar o `Update-Help` cmdlet para baixar a ajuda do comando da Internet ou de um compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d5194-136">The auto-generated help includes text that directs the user to try to use the `Update-Help` cmdlet to download help for the command from the internet or a file share.</span></span> <span data-ttu-id="d5194-137">Ele também recomenda o uso do parâmetro **online** do `Get-Help` cmdlet para obter a versão online do tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="d5194-137">It also recommends using the **Online** parameter of the `Get-Help` cmdlet to get the online version of the help topic.</span></span>

## <a name="supporting-updatable-help"></a><span data-ttu-id="d5194-138">Suporte à ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="d5194-138">Supporting Updatable Help</span></span>

<span data-ttu-id="d5194-139">Os usuários do PowerShell 3,0 e versões posteriores do PowerShell podem baixar e instalar arquivos de ajuda atualizados para um módulo da Internet ou de um compartilhamento de arquivos local.</span><span class="sxs-lookup"><span data-stu-id="d5194-139">Users of PowerShell 3.0 and later versions of PowerShell can download and install updated help files for a module from the internet or from a local file share.</span></span> <span data-ttu-id="d5194-140">Os `Update-Help` `Save-Help` cmdlets e ocultam os detalhes de gerenciamento do usuário.</span><span class="sxs-lookup"><span data-stu-id="d5194-140">The `Update-Help` and `Save-Help` cmdlets hide the management details from the user.</span></span> <span data-ttu-id="d5194-141">Os usuários executam o `Update-Help` cmdlet e, em seguida, usam o `Get-Help` cmdlet para ler os arquivos de ajuda mais recentes do módulo no prompt de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5194-141">Users run the `Update-Help` cmdlet and then use the `Get-Help` cmdlet to read the newest help files for the module at the PowerShell command prompt.</span></span>
<span data-ttu-id="d5194-142">Os usuários não precisam reiniciar o Windows ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5194-142">Users do not need to restart Windows or PowerShell.</span></span>

<span data-ttu-id="d5194-143">Os usuários atrás de firewalls e aqueles sem acesso à Internet também podem usar a ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="d5194-143">Users behind firewalls and those without internet access can use Updatable Help, as well.</span></span>
<span data-ttu-id="d5194-144">Os administradores com acesso à Internet usam o `Save-Help` cmdlet para baixar e instalar os arquivos de ajuda mais recentes em um compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d5194-144">Administrators with internet access use the `Save-Help` cmdlet to download and install the newest help files to a file share.</span></span> <span data-ttu-id="d5194-145">Em seguida, os usuários usam o parâmetro **path** do `Update-Help` cmdlet para obter os arquivos de ajuda mais recentes do compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d5194-145">Then, users use the **Path** parameter of the `Update-Help` cmdlet to get the newest help files from the file share.</span></span>

<span data-ttu-id="d5194-146">Os autores de módulo podem incluir arquivos de ajuda no módulo e usar a ajuda atualizável para atualizar os arquivos de ajuda ou omitir os arquivos de ajuda do módulo e usar a ajuda atualizável para instalar e atualizá-los.</span><span class="sxs-lookup"><span data-stu-id="d5194-146">Module authors can include help files in the module and use Updatable Help to update the help files, or omit help files from the module and use Updatable Help both to install and to update them.</span></span>

<span data-ttu-id="d5194-147">Para obter mais informações sobre a ajuda atualizável, consulte [suporte à ajuda atualizável](./supporting-updatable-help.md).</span><span class="sxs-lookup"><span data-stu-id="d5194-147">For more information about Updatable Help, see [Supporting Updatable Help](./supporting-updatable-help.md).</span></span>

## <a name="supporting-online-help"></a><span data-ttu-id="d5194-148">Suporte à ajuda online</span><span class="sxs-lookup"><span data-stu-id="d5194-148">Supporting Online Help</span></span>

<span data-ttu-id="d5194-149">Os usuários que não podem ou não instalar arquivos de ajuda atualizados em seus computadores geralmente dependem da versão online dos tópicos de ajuda do módulo.</span><span class="sxs-lookup"><span data-stu-id="d5194-149">Users who cannot or do not install updated help files on their computers often rely on the online version of module help topics.</span></span> <span data-ttu-id="d5194-150">O parâmetro **online** do `Get-Help` cmdlet abre a versão online de um cmdlet ou tópico de ajuda de função avançada para o usuário em seu navegador de Internet padrão.</span><span class="sxs-lookup"><span data-stu-id="d5194-150">The **Online** parameter of the `Get-Help` cmdlet opens the online version of a cmdlet or advanced function help topic for the user in their default internet browser.</span></span>

<span data-ttu-id="d5194-151">O `Get-Help` cmdlet usa o valor da propriedade **HelpUri** do cmdlet ou da função para localizar a versão online do tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="d5194-151">The `Get-Help` cmdlet uses the value of the **HelpUri** property of the cmdlet or function to find the online version of the help topic.</span></span>

<span data-ttu-id="d5194-152">A partir do PowerShell 3,0, você pode ajudar os usuários a localizar a versão online dos tópicos de ajuda do cmdlet e da função definindo o atributo HelpUri na classe cmdlet ou a propriedade **HelpUri** do atributo **CmdletBinding** .</span><span class="sxs-lookup"><span data-stu-id="d5194-152">Beginning in PowerShell 3.0, you can help users find the online version of cmdlet and function help topics by defining the HelpUri attribute on the cmdlet class or the **HelpUri** property of the **CmdletBinding** attribute.</span></span> <span data-ttu-id="d5194-153">O valor do atributo é o valor da propriedade **HelpUri** do cmdlet ou da função.</span><span class="sxs-lookup"><span data-stu-id="d5194-153">The value of the attribute is the value of the **HelpUri** property of the cmdlet or function.</span></span>

<span data-ttu-id="d5194-154">Para obter mais informações, consulte [suporte à ajuda online](./supporting-online-help.md).</span><span class="sxs-lookup"><span data-stu-id="d5194-154">For more information, see [Supporting Online Help](./supporting-online-help.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d5194-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d5194-155">See Also</span></span>

[<span data-ttu-id="d5194-156">Escrevendo um módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5194-156">Writing a PowerShell Module</span></span>](../module/writing-a-windows-powershell-module.md)

[<span data-ttu-id="d5194-157">Suporte à ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="d5194-157">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)

[<span data-ttu-id="d5194-158">Suporte à ajuda online</span><span class="sxs-lookup"><span data-stu-id="d5194-158">Supporting Online Help</span></span>](./supporting-online-help.md)
