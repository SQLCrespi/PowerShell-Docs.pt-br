---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Usando a expansão com Tab
description: Explica como usar o recurso de Expansão de Guia no PowerShell.
ms.openlocfilehash: d3408aac8cc9325666082577a7b00bc3362bfca3
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500038"
---
# <a name="using-tab-expansion"></a><span data-ttu-id="5e990-104">Usando a expansão com Tab</span><span class="sxs-lookup"><span data-stu-id="5e990-104">Using Tab Expansion</span></span>

<span data-ttu-id="5e990-105">Shells de linha de comando geralmente fornecem uma maneira de preencher nomes longos de arquivos ou comandos automaticamente, acelerando a entrada de comandos e fornecendo dicas.</span><span class="sxs-lookup"><span data-stu-id="5e990-105">Command-line shells often provide a way to complete the names of long files or commands automatically, speeding up command entry and providing hints.</span></span> <span data-ttu-id="5e990-106">O PowerShell permite preencher os nomes de arquivo e os nomes de cmdlet pressionando a tecla <kbd>Tab</kbd>.</span><span class="sxs-lookup"><span data-stu-id="5e990-106">PowerShell allows you to fill in file names and cmdlet names by pressing the <kbd>Tab</kbd> key.</span></span>

> [!NOTE]
> <span data-ttu-id="5e990-107">A expansão da guia é controlada pelas funções internas TabExpansion ou TabExpansion2.</span><span class="sxs-lookup"><span data-stu-id="5e990-107">Tab expansion is controlled by the internal function TabExpansion or TabExpansion2.</span></span> <span data-ttu-id="5e990-108">Como essa função pode ser modificada ou substituída, essa discussão é um guia para o comportamento da configuração padrão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e990-108">Since this function can be modified or overridden, this discussion is a guide to the behavior of the default PowerShell configuration.</span></span>

<span data-ttu-id="5e990-109">Para preencher automaticamente um nome de arquivo ou um caminho com as opções disponíveis automaticamente, digite parte do nome e pressione a tecla <kbd>Tab</kbd>.</span><span class="sxs-lookup"><span data-stu-id="5e990-109">To fill in a filename or path from the available choices automatically, type part of the name and press the <kbd>Tab</kbd> key.</span></span> <span data-ttu-id="5e990-110">O PowerShell expandirá automaticamente o nome para a primeira correspondência que encontrar.</span><span class="sxs-lookup"><span data-stu-id="5e990-110">PowerShell will automatically expand the name to the first match that it finds.</span></span> <span data-ttu-id="5e990-111">Pressionar a tecla <kbd>Tab</kbd> repetidamente percorrerá todas as opções disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5e990-111">Pressing the <kbd>Tab</kbd> key repeatedly will cycle through all of the available choices.</span></span>

<span data-ttu-id="5e990-112">A expansão com Tab de nomes de cmdlet é ligeiramente diferente.</span><span class="sxs-lookup"><span data-stu-id="5e990-112">The tab expansion of cmdlet names is slightly different.</span></span> <span data-ttu-id="5e990-113">Para usar a expansão com Tab em um nome de cmdlet, digite a primeira parte inteira do nome (o verbo) e o hífen que o segue.</span><span class="sxs-lookup"><span data-stu-id="5e990-113">To use tab expansion on a cmdlet name, type the entire first part of the name (the verb) and the hyphen that follows it.</span></span> <span data-ttu-id="5e990-114">Você pode preencher mais do mesmo nome de uma correspondência parcial.</span><span class="sxs-lookup"><span data-stu-id="5e990-114">You can fill in more of the name for a partial match.</span></span> <span data-ttu-id="5e990-115">Por exemplo, se você digitar `get-co` e pressionar a tecla <kbd>Tab</kbd>, o PowerShell o expandirá automaticamente para o cmdlet `Get-Command` (observe que ele também altera as letras maiúsculas e minúsculas para sua forma padrão).</span><span class="sxs-lookup"><span data-stu-id="5e990-115">For example, if you type `get-co` and then press the <kbd>Tab</kbd> key, PowerShell will automatically expand this to the `Get-Command` cmdlet (notice that it also changes the case of letters to their standard form).</span></span> <span data-ttu-id="5e990-116">Se você pressionar a tecla <kbd>Tab</kbd> novamente, o PowerShell substitui isso pelo outro único nome de cmdlet correspondente, `Get-Content`.</span><span class="sxs-lookup"><span data-stu-id="5e990-116">If you press <kbd>Tab</kbd> key again, PowerShell replaces this with the only other matching cmdlet name, `Get-Content`.</span></span>

<span data-ttu-id="5e990-117">Você pode usar a expansão com Tab várias vezes na mesma linha.</span><span class="sxs-lookup"><span data-stu-id="5e990-117">You can use tab expansion repeatedly on the same line.</span></span> <span data-ttu-id="5e990-118">Por exemplo, você pode usar a expansão de guias no nome do cmdlet `Get-Content` digitando:</span><span class="sxs-lookup"><span data-stu-id="5e990-118">For example, you can use tab expansion on the name of the `Get-Content` cmdlet by entering:</span></span>

```
PS> Get-Con<Tab>
```

<span data-ttu-id="5e990-119">Quando você pressiona a tecla <kbd>Tab</kbd>, o comando se expande para:</span><span class="sxs-lookup"><span data-stu-id="5e990-119">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content
```

<span data-ttu-id="5e990-120">Você pode especificar parcialmente o caminho para o arquivo de log Active Setup e usar a expansão com Tab novamente:</span><span class="sxs-lookup"><span data-stu-id="5e990-120">You can then partially specify the path to the Active Setup log file and use tab expansion again:</span></span>

```
PS> Get-Content c:\windows\acts<Tab>
```

<span data-ttu-id="5e990-121">Quando você pressiona a tecla <kbd>Tab</kbd>, o comando se expande para:</span><span class="sxs-lookup"><span data-stu-id="5e990-121">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content C:\windows\actsetup.log
```

> [!NOTE]
> <span data-ttu-id="5e990-122">Uma limitação do processo de expansão de guia é que as guias são sempre interpretadas como tentativas de preencher uma palavra.</span><span class="sxs-lookup"><span data-stu-id="5e990-122">One limitation of the tab expansion process is that tabs are always interpreted as attempts to complete a word.</span></span> <span data-ttu-id="5e990-123">Se você copiar e colar os exemplos de comando em um console do PowerShell, verifique se o exemplo não contém guias; se contiver, os resultados serão imprevisíveis e certamente não serão o que você pretendia.</span><span class="sxs-lookup"><span data-stu-id="5e990-123">If you copy and paste command examples into a PowerShell console, make sure that the sample does not contain tabs; if it does, the results will be unpredictable and will almost certainly not be what you intended.</span></span>
