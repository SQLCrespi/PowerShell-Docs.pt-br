---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Outros objetos de script úteis
ms.assetid: 4d781196-720b-4ccc-90d2-c570e5e719f5
ms.openlocfilehash: ff494f375c0d43d83b2a067dbe4f2ab35a90d564
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086197"
---
# <a name="other-useful-scripting-objects"></a><span data-ttu-id="f0c6b-103">Outros objetos de script úteis</span><span class="sxs-lookup"><span data-stu-id="f0c6b-103">Other Useful Scripting Objects</span></span>

<span data-ttu-id="f0c6b-104">Os seguintes objetos fornecem funcionalidade adicional de script no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-104">The following objects provide additional scripting functionality in Windows PowerShell ISE.</span></span> <span data-ttu-id="f0c6b-105">Eles não fazem parte da hierarquia **$psISE**.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-105">They are not part of the **$psISE** hierarchy.</span></span>

## <a name="useful-scripting-objects"></a><span data-ttu-id="f0c6b-106">Objetos de scripts úteis</span><span class="sxs-lookup"><span data-stu-id="f0c6b-106">Useful Scripting objects</span></span>

### <a name="psunsupportedconsoleapplications"></a><span data-ttu-id="f0c6b-107">$psUnsupportedConsoleApplications</span><span class="sxs-lookup"><span data-stu-id="f0c6b-107">$psUnsupportedConsoleApplications</span></span>

<span data-ttu-id="f0c6b-108">Existem algumas limitações sobre como o ISE do Windows PowerShell interage com os aplicativos do console.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-108">There are some limitations on how Windows PowerShell ISE interacts with console applications.</span></span> <span data-ttu-id="f0c6b-109">Um comando ou um script de automação que requer a intervenção do usuário pode não funcionar da maneira que funciona no console do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-109">A command or an automation script that requires user intervention might not work the way it works from the Windows PowerShell console.</span></span> <span data-ttu-id="f0c6b-110">Você pode impedir que esses comandos ou scripts sejam executados no painel de comando ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-110">You might want to block these commands or scripts from running in the Windows PowerShell ISE Command pane.</span></span> <span data-ttu-id="f0c6b-111">O objeto **$psUnsupportedConsoleApplications** mantém uma lista de tais comandos.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-111">The **$psUnsupportedConsoleApplications** object keeps a list of such commands.</span></span> <span data-ttu-id="f0c6b-112">Se você tentar executar os comandos nesta lista, receberá uma mensagem de que eles não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-112">If you try to run the commands in this list, you get a message that they are not supported.</span></span> <span data-ttu-id="f0c6b-113">O script a seguir adiciona uma entrada à lista.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-113">The following script adds an entry to the list.</span></span>

```powershell
# List the unsupported commands
$psUnsupportedConsoleApplications

# Add a command to this list
$psUnsupportedConsoleApplications.Add('Mycommand')

# Show the augmented list of commands
$psUnsupportedConsoleApplications
```

### <a name="pslocalhelp"></a><span data-ttu-id="f0c6b-114">$psLocalHelp</span><span class="sxs-lookup"><span data-stu-id="f0c6b-114">$psLocalHelp</span></span>

<span data-ttu-id="f0c6b-115">Esse é um objeto de dicionário que mantém um mapeamento contextual entre os tópicos da Ajuda e seus links associados no arquivo de ajuda local HTML compilado.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-115">This is a dictionary object that maintains a context-sensitive mapping between Help topics and their associated links in the local compiled HTML Help file.</span></span> <span data-ttu-id="f0c6b-116">Ele é usado para localizar a Ajuda local para determinado tópico.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-116">It is used to locate the local Help for a particular topic.</span></span> <span data-ttu-id="f0c6b-117">Você pode adicionar ou excluir tópicos desta lista.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-117">You can add or delete topics from this list.</span></span> <span data-ttu-id="f0c6b-118">O exemplo de código a seguir mostra alguns exemplos de pares de chave-valor contidos em `$psLocalHelp`.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-118">The following code example shows some example key-value pairs that are contained in `$psLocalHelp`.</span></span>

```powershell
# See the local help map
$psLocalHelp | Format-List
```

```output
Key   : Add-Computer
Value : WindowsPowerShellHelp.chm::/html/093f660c-b8d5-43cf-aa0c-54e5e54e76f9.htm

Key   : Add-Content
Value : WindowsPowerShellHelp.chm::/html/0c836a1b-f389-4e9a-9325-0f415686d194.htm
```

<span data-ttu-id="f0c6b-119">O script a seguir adiciona uma entrada à lista.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-119">The following script adds an entry to the list.</span></span>

```powershell
$psLocalHelp.Add("get-myNoun", "c:\MyFolder\MyHelpChm.chm::/html/0198854a-1298-57ae-aa0c-87b5e5a84712.htm")
```

### <a name="psonlinehelp"></a><span data-ttu-id="f0c6b-120">$psOnlineHelp</span><span class="sxs-lookup"><span data-stu-id="f0c6b-120">$psOnlineHelp</span></span>

<span data-ttu-id="f0c6b-121">Este é um objeto de dicionário que mantém um mapeamento contextual entre títulos de tópicos dos tópicos de ajuda e suas URLs externas associadas.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-121">This is a dictionary object that maintains a context-sensitive mapping between topic titles of Help topics and their associated external URLs.</span></span> <span data-ttu-id="f0c6b-122">Ele é usado para localizar a ajuda para um tópico específico na Web.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-122">It is used to locate the Help for a particular topic on the web.</span></span> <span data-ttu-id="f0c6b-123">Você pode adicionar ou excluir tópicos desta lista.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-123">You can add or delete topics from this list.</span></span>

```powershell
$psOnlineHelp | Format-List
```

```output
Key   : Add-Computer
Value : http://go.microsoft.com/fwlink/p/?LinkID=135194

Key   : Add-Content
Value : http://go.microsoft.com/fwlink/p/?LinkID=113278
```

<span data-ttu-id="f0c6b-124">O script a seguir adiciona uma entrada à lista.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-124">The following script adds an entry to the list.</span></span>

```powershell
$psOnlineHelp.Add("get-myNoun", "http://www.mydomain.com/MyNoun.html")
```

## <a name="see-also"></a><span data-ttu-id="f0c6b-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f0c6b-125">See Also</span></span>

[<span data-ttu-id="f0c6b-126">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0c6b-126">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](../components/ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)