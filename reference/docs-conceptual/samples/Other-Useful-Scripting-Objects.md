---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Outros objetos de script úteis
description: Este artigo descreve os objetos que fornecem funcionalidade de script adicional no ISE do Windows PowerShell.
ms.openlocfilehash: c20daa0045bc07b1f21aafa42a80ce7c47ee7331
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500259"
---
# <a name="other-useful-scripting-objects"></a><span data-ttu-id="1440a-104">Outros objetos de script úteis</span><span class="sxs-lookup"><span data-stu-id="1440a-104">Other Useful Scripting Objects</span></span>

<span data-ttu-id="1440a-105">Os seguintes objetos fornecem funcionalidade adicional de script no ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1440a-105">The following objects provide additional scripting functionality in Windows PowerShell ISE.</span></span> <span data-ttu-id="1440a-106">Eles não fazem parte da hierarquia **$psISE** .</span><span class="sxs-lookup"><span data-stu-id="1440a-106">They are not part of the **$psISE** hierarchy.</span></span>

## <a name="useful-scripting-objects"></a><span data-ttu-id="1440a-107">Objetos de scripts úteis</span><span class="sxs-lookup"><span data-stu-id="1440a-107">Useful Scripting objects</span></span>

### <a name="psunsupportedconsoleapplications"></a><span data-ttu-id="1440a-108">$psUnsupportedConsoleApplications</span><span class="sxs-lookup"><span data-stu-id="1440a-108">$psUnsupportedConsoleApplications</span></span>

<span data-ttu-id="1440a-109">Existem algumas limitações sobre como o ISE do Windows PowerShell interage com os aplicativos do console.</span><span class="sxs-lookup"><span data-stu-id="1440a-109">There are some limitations on how Windows PowerShell ISE interacts with console applications.</span></span> <span data-ttu-id="1440a-110">Um comando ou um script de automação que requer a intervenção do usuário pode não funcionar da maneira que funciona no console do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1440a-110">A command or an automation script that requires user intervention might not work the way it works from the Windows PowerShell console.</span></span> <span data-ttu-id="1440a-111">Você pode impedir que esses comandos ou scripts sejam executados no painel de comando ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1440a-111">You might want to block these commands or scripts from running in the Windows PowerShell ISE Command pane.</span></span> <span data-ttu-id="1440a-112">O objeto **$psUnsupportedConsoleApplications** mantém uma lista de tais comandos.</span><span class="sxs-lookup"><span data-stu-id="1440a-112">The **$psUnsupportedConsoleApplications** object keeps a list of such commands.</span></span> <span data-ttu-id="1440a-113">Se você tentar executar os comandos nesta lista, receberá uma mensagem de que eles não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="1440a-113">If you try to run the commands in this list, you get a message that they are not supported.</span></span> <span data-ttu-id="1440a-114">O script a seguir adiciona uma entrada à lista.</span><span class="sxs-lookup"><span data-stu-id="1440a-114">The following script adds an entry to the list.</span></span>

```powershell
# List the unsupported commands
$psUnsupportedConsoleApplications

# Add a command to this list
$psUnsupportedConsoleApplications.Add('Mycommand')

# Show the augmented list of commands
$psUnsupportedConsoleApplications
```

### <a name="pslocalhelp"></a><span data-ttu-id="1440a-115">$psLocalHelp</span><span class="sxs-lookup"><span data-stu-id="1440a-115">$psLocalHelp</span></span>

<span data-ttu-id="1440a-116">Esse é um objeto de dicionário que mantém um mapeamento contextual entre os tópicos da Ajuda e seus links associados no arquivo de ajuda local HTML compilado.</span><span class="sxs-lookup"><span data-stu-id="1440a-116">This is a dictionary object that maintains a context-sensitive mapping between Help topics and their associated links in the local compiled HTML Help file.</span></span> <span data-ttu-id="1440a-117">Ele é usado para localizar a Ajuda local para determinado tópico.</span><span class="sxs-lookup"><span data-stu-id="1440a-117">It is used to locate the local Help for a particular topic.</span></span> <span data-ttu-id="1440a-118">Você pode adicionar ou excluir tópicos desta lista.</span><span class="sxs-lookup"><span data-stu-id="1440a-118">You can add or delete topics from this list.</span></span> <span data-ttu-id="1440a-119">O exemplo de código a seguir mostra alguns exemplos de pares de chave-valor contidos em `$psLocalHelp`.</span><span class="sxs-lookup"><span data-stu-id="1440a-119">The following code example shows some example key-value pairs that are contained in `$psLocalHelp`.</span></span>

```powershell
# See the local help map
$psLocalHelp | Format-List
```

```Output
Key   : Add-Computer
Value : WindowsPowerShellHelp.chm::/html/093f660c-b8d5-43cf-aa0c-54e5e54e76f9.htm

Key   : Add-Content
Value : WindowsPowerShellHelp.chm::/html/0c836a1b-f389-4e9a-9325-0f415686d194.htm
```

<span data-ttu-id="1440a-120">O script a seguir adiciona uma entrada à lista.</span><span class="sxs-lookup"><span data-stu-id="1440a-120">The following script adds an entry to the list.</span></span>

```powershell
$psLocalHelp.Add("get-myNoun", "c:\MyFolder\MyHelpChm.chm::/html/0198854a-1298-57ae-aa0c-87b5e5a84712.htm")
```

### <a name="psonlinehelp"></a><span data-ttu-id="1440a-121">$psOnlineHelp</span><span class="sxs-lookup"><span data-stu-id="1440a-121">$psOnlineHelp</span></span>

<span data-ttu-id="1440a-122">Este é um objeto de dicionário que mantém um mapeamento contextual entre títulos de tópicos dos tópicos de ajuda e suas URLs externas associadas.</span><span class="sxs-lookup"><span data-stu-id="1440a-122">This is a dictionary object that maintains a context-sensitive mapping between topic titles of Help topics and their associated external URLs.</span></span> <span data-ttu-id="1440a-123">Ele é usado para localizar a ajuda para um tópico específico na Web.</span><span class="sxs-lookup"><span data-stu-id="1440a-123">It is used to locate the Help for a particular topic on the web.</span></span> <span data-ttu-id="1440a-124">Você pode adicionar ou excluir tópicos desta lista.</span><span class="sxs-lookup"><span data-stu-id="1440a-124">You can add or delete topics from this list.</span></span>

```powershell
$psOnlineHelp | Format-List
```

```Output
Key   : Add-Computer
Value : https://go.microsoft.com/fwlink/p/?LinkID=135194

Key   : Add-Content
Value : https://go.microsoft.com/fwlink/p/?LinkID=113278
```

<span data-ttu-id="1440a-125">O script a seguir adiciona uma entrada à lista.</span><span class="sxs-lookup"><span data-stu-id="1440a-125">The following script adds an entry to the list.</span></span>

```powershell
$psOnlineHelp.Add("get-myNoun", "https://www.mydomain.com/MyNoun.html")
```

## <a name="see-also"></a><span data-ttu-id="1440a-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1440a-126">See Also</span></span>

[<span data-ttu-id="1440a-127">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1440a-127">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](../components/ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
