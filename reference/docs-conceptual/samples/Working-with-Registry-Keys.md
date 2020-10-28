---
ms.date: 12/23/2019
keywords: powershell, cmdlet
title: Trabalhando com chaves do Registro
description: Este artigo discute como lidar com chaves do Registro usando o PowerShell.
ms.openlocfilehash: 90e8417fc3454b959dc2a86fc63e722832bdab23
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501381"
---
# <a name="working-with-registry-keys"></a><span data-ttu-id="e2b83-104">Trabalhando com chaves do Registro</span><span class="sxs-lookup"><span data-stu-id="e2b83-104">Working with Registry Keys</span></span>

<span data-ttu-id="e2b83-105">Como as chaves do Registro são itens em unidades do PowerShell, trabalhar com elas é muito semelhante a trabalhar com arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="e2b83-105">Because registry keys are items on PowerShell drives, working with them is very similar to working with files and folders.</span></span> <span data-ttu-id="e2b83-106">Uma diferença fundamental é que cada item em uma unidade do PowerShell com base no Registro é um contêiner, assim como uma pasta em uma unidade de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e2b83-106">One critical difference is that every item on a registry-based PowerShell drive is a container, just like a folder on a file system drive.</span></span> <span data-ttu-id="e2b83-107">No entanto, as entradas do Registro e seus valores associados são propriedades de itens, não itens distintos.</span><span class="sxs-lookup"><span data-stu-id="e2b83-107">However, registry entries and their associated values are properties of the items, not distinct items.</span></span>

## <a name="listing-all-subkeys-of-a-registry-key"></a><span data-ttu-id="e2b83-108">Listar todas as subchaves de uma chave do Registro</span><span class="sxs-lookup"><span data-stu-id="e2b83-108">Listing All Subkeys of a Registry Key</span></span>

<span data-ttu-id="e2b83-109">Você pode mostrar todos os itens diretamente em uma chave do Registro usando `Get-ChildItem`.</span><span class="sxs-lookup"><span data-stu-id="e2b83-109">You can show all items directly within a registry key by using `Get-ChildItem`.</span></span> <span data-ttu-id="e2b83-110">Adicione o parâmetro opcional **Force** para exibir itens ocultos ou do sistema.</span><span class="sxs-lookup"><span data-stu-id="e2b83-110">Add the optional **Force** parameter to display hidden or system items.</span></span> <span data-ttu-id="e2b83-111">Por exemplo, este comando exibe os itens diretamente na unidade do PowerShell `HKCU:`, que corresponde ao hive do Registro `HKEY_CURRENT_USER`:</span><span class="sxs-lookup"><span data-stu-id="e2b83-111">For example, this command displays the items directly within PowerShell drive `HKCU:`, which corresponds to the `HKEY_CURRENT_USER` registry hive:</span></span>

```powershell
Get-ChildItem -Path HKCU:\ | Select-Object Name
```

```Output
   Hive: Microsoft.PowerShell.Core\Registry::HKEY_CURRENT_USER

Name
----
HKEY_CURRENT_USER\AppEvents
HKEY_CURRENT_USER\Console
HKEY_CURRENT_USER\Control Panel
HKEY_CURRENT_USER\DirectShow
HKEY_CURRENT_USER\dummy
HKEY_CURRENT_USER\Environment
HKEY_CURRENT_USER\EUDC
HKEY_CURRENT_USER\Keyboard Layout
HKEY_CURRENT_USER\MediaFoundation
HKEY_CURRENT_USER\Microsoft
HKEY_CURRENT_USER\Network
HKEY_CURRENT_USER\Printers
HKEY_CURRENT_USER\Software
HKEY_CURRENT_USER\System
HKEY_CURRENT_USER\Uninstall
HKEY_CURRENT_USER\WXP
HKEY_CURRENT_USER\Volatile Environment
```

<span data-ttu-id="e2b83-112">Essas são as chaves de nível superior em `HKEY_CURRENT_USER` no Editor do Registro (Regedit.exe).</span><span class="sxs-lookup"><span data-stu-id="e2b83-112">These are the top-level keys visible under `HKEY_CURRENT_USER` in the Registry Editor (Regedit.exe).</span></span>

<span data-ttu-id="e2b83-113">Você também pode especificar esse caminho de Registro definindo o nome do provedor do Registro, seguido por `::`.</span><span class="sxs-lookup"><span data-stu-id="e2b83-113">You can also specify this registry path by specifying the registry provider's name, followed by `::`.</span></span> <span data-ttu-id="e2b83-114">O nome completo do provedor do Registro é `Microsoft.PowerShell.Core\Registry`, mas isso pode ser reduzido para apenas `Registry`.</span><span class="sxs-lookup"><span data-stu-id="e2b83-114">The registry provider's full name is `Microsoft.PowerShell.Core\Registry`, but this can be shortened to just `Registry`.</span></span> <span data-ttu-id="e2b83-115">Qualquer um dos comandos a seguir lista o conteúdo diretamente em `HKCU:`.</span><span class="sxs-lookup"><span data-stu-id="e2b83-115">Any of the following commands will list the contents directly under `HKCU:`.</span></span>

```powershell
Get-ChildItem -Path Registry::HKEY_CURRENT_USER
Get-ChildItem -Path Microsoft.PowerShell.Core\Registry::HKEY_CURRENT_USER
Get-ChildItem -Path Registry::HKCU
Get-ChildItem -Path Microsoft.PowerShell.Core\Registry::HKCU
Get-ChildItem HKCU:
```

<span data-ttu-id="e2b83-116">Esses comandos listam apenas os itens contidos diretamente, similar ao uso do comando `DIR` do **Cmd.exe** ou `ls` em um shell do UNIX.</span><span class="sxs-lookup"><span data-stu-id="e2b83-116">These commands list only the directly contained items, much like using `DIR` in **Cmd.exe** or `ls` in a UNIX shell.</span></span> <span data-ttu-id="e2b83-117">Para mostrar os itens contidos, você precisa especificar o parâmetro **Recurse** .</span><span class="sxs-lookup"><span data-stu-id="e2b83-117">To show contained items, you need to specify the **Recurse** parameter.</span></span> <span data-ttu-id="e2b83-118">Use o comando a seguir para listar todas as chave do Registro em `HKCU:`.</span><span class="sxs-lookup"><span data-stu-id="e2b83-118">To list all registry keys in `HKCU:`, use the following command.</span></span>

```powershell
Get-ChildItem -Path HKCU:\ -Recurse
```

<span data-ttu-id="e2b83-119">`Get-ChildItem` pode executar as funcionalidades de filtragem complexas por meio de seus parâmetros **Path** , **Filter** , **Include** e **Exclude** , mas esses parâmetros normalmente são baseados apenas no nome.</span><span class="sxs-lookup"><span data-stu-id="e2b83-119">`Get-ChildItem` can perform complex filtering capabilities through its **Path** , **Filter** , **Include** , and **Exclude** parameters, but those parameters are typically based only on name.</span></span> <span data-ttu-id="e2b83-120">Você pode executar a filtragem complexa com base em outras propriedades de itens usando o cmdlet `Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="e2b83-120">You can perform complex filtering based on other properties of items by using the `Where-Object` cmdlet.</span></span> <span data-ttu-id="e2b83-121">O comando a seguir encontra todas as chaves no `HKCU:\Software` que têm, no máximo, uma subchave e que também têm exatamente quatro valores:</span><span class="sxs-lookup"><span data-stu-id="e2b83-121">The following command finds all keys within `HKCU:\Software` that have no more than one subkey and also have exactly four values:</span></span>

```powershell
Get-ChildItem -Path HKCU:\Software -Recurse |
  Where-Object {($_.SubKeyCount -le 1) -and ($_.ValueCount -eq 4) }
```

## <a name="copying-keys"></a><span data-ttu-id="e2b83-122">Copiar chaves</span><span class="sxs-lookup"><span data-stu-id="e2b83-122">Copying Keys</span></span>

<span data-ttu-id="e2b83-123">A cópia é feita com `Copy-Item`.</span><span class="sxs-lookup"><span data-stu-id="e2b83-123">Copying is done with `Copy-Item`.</span></span> <span data-ttu-id="e2b83-124">O exemplo a seguir copia a subchave `CurrentVersion` de `HKLM:\SOFTWARE\Microsoft\Windows\` e todas as suas propriedades para `HKCU:\`.</span><span class="sxs-lookup"><span data-stu-id="e2b83-124">The following example copies the `CurrentVersion` subkey of `HKLM:\SOFTWARE\Microsoft\Windows\` and all of its properties to `HKCU:\`.</span></span>

```powershell
Copy-Item -Path 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion' -Destination HKCU:
```

<span data-ttu-id="e2b83-125">Se você examinar essa nova chave no editor do Registro ou por meio de `Get-ChildItem`, observará que não há cópias das subchaves contidas no novo local.</span><span class="sxs-lookup"><span data-stu-id="e2b83-125">If you examine this new key in the registry editor or by using `Get-ChildItem`, you notice that you do not have copies of the contained subkeys in the new location.</span></span> <span data-ttu-id="e2b83-126">Para copiar todo o conteúdo de um contêiner, você precisa especificar o parâmetro **Recurse** .</span><span class="sxs-lookup"><span data-stu-id="e2b83-126">In order to copy all of the contents of a container, you need to specify the **Recurse** parameter.</span></span> <span data-ttu-id="e2b83-127">Para tornar o comando de cópia anterior recursivo, você usaria este comando:</span><span class="sxs-lookup"><span data-stu-id="e2b83-127">To make the preceding copy command recursive, you would use this command:</span></span>

```powershell
Copy-Item -Path 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion' -Destination HKCU: -Recurse
```

<span data-ttu-id="e2b83-128">Você ainda pode usar outras ferramentas que já estão disponíveis para executar cópias do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e2b83-128">You can still use other tools you already have available to perform filesystem copies.</span></span> <span data-ttu-id="e2b83-129">Quaisquer ferramentas de edição de Registro, incluindo **reg.exe** , **regini.exe** , **regedit.exe** e objetos COM que dão suporte à edição do Registro, como o **WScript.Shell** e a classe **StdRegProv** do WMI, podem ser usados de dentro do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2b83-129">Any registry editing tools—including **reg.exe** , **regini.exe** , **regedit.exe** , and COM objects that support registry editing, such as **WScript.Shell** and WMI's **StdRegProv** class can be used from within Windows PowerShell.</span></span>

## <a name="creating-keys"></a><span data-ttu-id="e2b83-130">Criar chaves</span><span class="sxs-lookup"><span data-stu-id="e2b83-130">Creating Keys</span></span>

<span data-ttu-id="e2b83-131">Criar novas chaves no Registro é mais simples do que criar um novo item em um sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e2b83-131">Creating new keys in the registry is simpler than creating a new item in a file system.</span></span> <span data-ttu-id="e2b83-132">Como todas as chaves do Registro são contêineres, você não precisa especificar o tipo de item; basta fornecer um caminho explícito, como:</span><span class="sxs-lookup"><span data-stu-id="e2b83-132">Because all registry keys are containers, you do not need to specify the item type; you simply supply an explicit path, such as:</span></span>

```powershell
New-Item -Path HKCU:\Software_DeleteMe
```

<span data-ttu-id="e2b83-133">Você também pode usar um caminho de provedor para especificar uma chave:</span><span class="sxs-lookup"><span data-stu-id="e2b83-133">You can also use a provider-based path to specify a key:</span></span>

```powershell
New-Item -Path Registry::HKCU\Software_DeleteMe
```

## <a name="deleting-keys"></a><span data-ttu-id="e2b83-134">Excluir chaves</span><span class="sxs-lookup"><span data-stu-id="e2b83-134">Deleting Keys</span></span>

<span data-ttu-id="e2b83-135">Excluir itens é essencialmente o mesmo para todos os provedores.</span><span class="sxs-lookup"><span data-stu-id="e2b83-135">Deleting items is essentially the same for all providers.</span></span> <span data-ttu-id="e2b83-136">Os comandos a seguir removerão itens silenciosamente:</span><span class="sxs-lookup"><span data-stu-id="e2b83-136">The following commands will silently remove items:</span></span>

```powershell
Remove-Item -Path HKCU:\Software_DeleteMe
Remove-Item -Path 'HKCU:\key with spaces in the name'
```

## <a name="removing-all-keys-under-a-specific-key"></a><span data-ttu-id="e2b83-137">Remover todas as chaves sob uma chave específica</span><span class="sxs-lookup"><span data-stu-id="e2b83-137">Removing All Keys Under a Specific Key</span></span>

<span data-ttu-id="e2b83-138">É possível remover os itens contidos usando `Remove-Item`, mas será solicitado que você confirme a remoção se o item contiver qualquer outra coisa.</span><span class="sxs-lookup"><span data-stu-id="e2b83-138">You can remove contained items by using `Remove-Item`, but you will be prompted to confirm the removal if the item contains anything else.</span></span> <span data-ttu-id="e2b83-139">Por exemplo, se tentarmos excluir a subchave `HKCU:\CurrentVersion` que criamos, veremos isto:</span><span class="sxs-lookup"><span data-stu-id="e2b83-139">For example, if we attempt to delete the `HKCU:\CurrentVersion` subkey we created, we see this:</span></span>

```powershell
Remove-Item -Path HKCU:\CurrentVersion
```

```Output
Confirm
The item at HKCU:\CurrentVersion\AdminDebug has children and the -recurse
parameter was not specified. If you continue, all children will be removed with
the item. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="e2b83-140">Para excluir os itens contidos sem nenhuma solicitação, especifique o parâmetro **Recurse** :</span><span class="sxs-lookup"><span data-stu-id="e2b83-140">To delete contained items without prompting, specify the **Recurse** parameter:</span></span>

```powershell
Remove-Item -Path HKCU:\CurrentVersion -Recurse
```

<span data-ttu-id="e2b83-141">Se desejar remover todos os itens dentro de `HKCU:\CurrentVersion`, mas não o `HKCU:\CurrentVersion` em si, você poderá usar:</span><span class="sxs-lookup"><span data-stu-id="e2b83-141">If you wanted to remove all items within `HKCU:\CurrentVersion` but not `HKCU:\CurrentVersion` itself, you could instead use:</span></span>

```powershell
Remove-Item -Path HKCU:\CurrentVersion\* -Recurse
```
