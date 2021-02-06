---
description: Alias
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_alias_provider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor Alias
ms.openlocfilehash: d6bfbaf878a6d971b1e01d963faec8c8ece5d1fc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596201"
---
# <a name="alias-provider"></a><span data-ttu-id="eeaf4-103">Provedor de alias</span><span class="sxs-lookup"><span data-stu-id="eeaf4-103">Alias provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="eeaf4-104">Nome do provedor</span><span class="sxs-lookup"><span data-stu-id="eeaf4-104">Provider name</span></span>
<span data-ttu-id="eeaf4-105">Alias</span><span class="sxs-lookup"><span data-stu-id="eeaf4-105">Alias</span></span>

## <a name="drives"></a><span data-ttu-id="eeaf4-106">Unidades</span><span class="sxs-lookup"><span data-stu-id="eeaf4-106">Drives</span></span>

`Alias:`

## <a name="capabilities"></a><span data-ttu-id="eeaf4-107">Funcionalidades</span><span class="sxs-lookup"><span data-stu-id="eeaf4-107">Capabilities</span></span>

<span data-ttu-id="eeaf4-108">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="eeaf4-108">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="eeaf4-109">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="eeaf4-109">Short description</span></span>

<span data-ttu-id="eeaf4-110">Fornece acesso aos aliases do PowerShell e aos valores que eles representam.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-110">Provides access to the PowerShell aliases and the values that they represent.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="eeaf4-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="eeaf4-111">Detailed description</span></span>

<span data-ttu-id="eeaf4-112">O provedor de **alias** do PowerShell permite que você obtenha, adicione, altere, apague e exclua aliases no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-112">The PowerShell **Alias** provider lets you get, add, change, clear, and delete aliases in PowerShell.</span></span>

<span data-ttu-id="eeaf4-113">Um alias é um nome alternativo para um cmdlet, função, arquivo executável, incluindo scripts.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-113">An alias is an alternate name for a cmdlet, function, executable file, including scripts.</span></span> <span data-ttu-id="eeaf4-114">O PowerShell inclui um conjunto de aliases internos.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-114">PowerShell includes a set of built-in aliases.</span></span> <span data-ttu-id="eeaf4-115">Você pode adicionar seus próprios aliases à sessão atual e ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-115">You can add your own aliases to the current session and to your PowerShell profile.</span></span>

<span data-ttu-id="eeaf4-116">A unidade de **alias** é um namespace simples que contém apenas os objetos de alias.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-116">The **Alias** drive is a flat namespace that contains only the alias objects.</span></span>
<span data-ttu-id="eeaf4-117">Os aliases não possuem itens filho.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-117">The aliases have no child items.</span></span>

<span data-ttu-id="eeaf4-118">O provedor de **alias** dá suporte aos seguintes cmdlets, que são abordados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-118">The **Alias** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="eeaf4-119">Get-Location</span><span class="sxs-lookup"><span data-stu-id="eeaf4-119">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="eeaf4-120">Set-Location</span><span class="sxs-lookup"><span data-stu-id="eeaf4-120">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="eeaf4-121">Get-Item</span><span class="sxs-lookup"><span data-stu-id="eeaf4-121">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="eeaf4-122">New-Item</span><span class="sxs-lookup"><span data-stu-id="eeaf4-122">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="eeaf4-123">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="eeaf4-123">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="eeaf4-124">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="eeaf4-124">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

<span data-ttu-id="eeaf4-125">O PowerShell inclui um conjunto de cmdlets que são projetados para exibir e alterar aliases.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-125">PowerShell includes a set of cmdlets that are designed to view and to change aliases.</span></span> <span data-ttu-id="eeaf4-126">Quando você usa cmdlets de **alias** , não é necessário especificar a `Alias:` unidade no nome.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-126">When you use **Alias** cmdlets, you do not need to specify the `Alias:` drive in the name.</span></span> <span data-ttu-id="eeaf4-127">Este artigo não aborda o trabalho com cmdlets de **alias** .</span><span class="sxs-lookup"><span data-stu-id="eeaf4-127">This article does not cover working with **Alias** cmdlets.</span></span>

- [<span data-ttu-id="eeaf4-128">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="eeaf4-128">Export-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [<span data-ttu-id="eeaf4-129">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="eeaf4-129">Get-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [<span data-ttu-id="eeaf4-130">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="eeaf4-130">Import-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [<span data-ttu-id="eeaf4-131">New-Alias</span><span class="sxs-lookup"><span data-stu-id="eeaf4-131">New-Alias</span></span>](xref:Microsoft.PowerShell.Utility.New-Alias)
- [<span data-ttu-id="eeaf4-132">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="eeaf4-132">Set-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Set-Alias)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="eeaf4-133">Tipos expostos por este provedor</span><span class="sxs-lookup"><span data-stu-id="eeaf4-133">Types exposed by this provider</span></span>

<span data-ttu-id="eeaf4-134">Cada alias é uma instância da classe [System. Management. Automation. AliasInfo](/dotnet/api/system.management.automation.aliasinfo) .</span><span class="sxs-lookup"><span data-stu-id="eeaf4-134">Each alias is an instance of the [System.Management.Automation.AliasInfo](/dotnet/api/system.management.automation.aliasinfo) class.</span></span>

## <a name="navigating-the-alias-drive"></a><span data-ttu-id="eeaf4-135">Navegando pela unidade de alias</span><span class="sxs-lookup"><span data-stu-id="eeaf4-135">Navigating the Alias drive</span></span>

<span data-ttu-id="eeaf4-136">O provedor de **alias** expõe seu armazenamento de dados na `Alias:` unidade.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-136">The **Alias** provider exposes its data store in the `Alias:` drive.</span></span> <span data-ttu-id="eeaf4-137">Para trabalhar com aliases, você pode alterar seu local para a `Alias:` unidade usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="eeaf4-137">To work with aliases, you can change your location to the `Alias:` drive by using the following command:</span></span>

```powershell
Set-Location Alias:
```

<span data-ttu-id="eeaf4-138">Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-138">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="eeaf4-139">Por exemplo, digite:</span><span class="sxs-lookup"><span data-stu-id="eeaf4-139">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="eeaf4-140">Você também pode trabalhar com o provedor de alias de qualquer outra unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-140">You can also work with the Alias provider from any other PowerShell drive.</span></span> <span data-ttu-id="eeaf4-141">Para fazer referência a um alias de outro local, use o `Alias:` nome da unidade no caminho.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-141">To reference an alias from another location, use the `Alias:` drive name in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="eeaf4-142">O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-142">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="eeaf4-143">Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="eeaf4-143">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="eeaf4-144">e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="eeaf4-144">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

### <a name="displaying-the-contents-of-the-alias-drive"></a><span data-ttu-id="eeaf4-145">Exibindo o conteúdo da unidade Alias:</span><span class="sxs-lookup"><span data-stu-id="eeaf4-145">Displaying the Contents of the Alias: drive</span></span>

<span data-ttu-id="eeaf4-146">Esse comando obtém a lista de todos os aliases quando o local atual é a `Alias:` unidade.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-146">This command gets the list of all the aliases when the current location is the `Alias:` drive.</span></span> <span data-ttu-id="eeaf4-147">Ele usa um caractere curinga `*` para indicar todo o conteúdo do local atual.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-147">It uses a wildcard character `*` to indicate all the contents of the current location.</span></span>

```powershell
PS Alias:\> Get-Item -Path *
```

<span data-ttu-id="eeaf4-148">Na `Alias:` unidade, um ponto `.` , que representa o local atual e um caractere curinga `*` , que representa todos os itens no local atual, têm o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-148">In the `Alias:` drive, a dot `.`, which represents the current location, and a wildcard character `*`, which represents all items in the current location, have the same effect.</span></span> <span data-ttu-id="eeaf4-149">Por exemplo, `Get-Item -Path .` ou `Get-Item \*` produzir o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-149">For example, `Get-Item -Path .` or `Get-Item \*` produce the same result.</span></span>

<span data-ttu-id="eeaf4-150">O provedor de alias não tem contêineres, portanto, o comando acima tem o mesmo efeito quando usado com `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="eeaf4-150">The Alias provider has no containers, so the above command has the same effect when used with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path Alias:
```

### <a name="get-a-selected-alias"></a><span data-ttu-id="eeaf4-151">Obter um alias selecionado</span><span class="sxs-lookup"><span data-stu-id="eeaf4-151">Get a selected alias</span></span>

<span data-ttu-id="eeaf4-152">Esse comando obtém o `ls` alias.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-152">This command gets the `ls` alias.</span></span>
<span data-ttu-id="eeaf4-153">Como ele inclui o caminho, você pode usá-lo em qualquer unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-153">Because it includes the path, you can use it in any PowerShell drive.</span></span>

```powershell
Get-Item -Path Alias:ls
```

<span data-ttu-id="eeaf4-154">Se você estiver na `Alias:` unidade, poderá omitir o nome da unidade do caminho.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-154">If you are in the `Alias:` drive, you can omit the drive name from the path.</span></span>

<span data-ttu-id="eeaf4-155">Você também pode recuperar a definição de um alias prefixando o caminho do provedor com o cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="eeaf4-155">You can also retrieve the definition for an alias by prefixing the provider path with the dollar sign (`$`).</span></span>

```powershell
$Alias:ls
```

### <a name="get-all-aliases-for-a-specific-cmdlet"></a><span data-ttu-id="eeaf4-156">Obter todos os aliases para um cmdlet específico</span><span class="sxs-lookup"><span data-stu-id="eeaf4-156">Get all aliases for a specific cmdlet</span></span>

<span data-ttu-id="eeaf4-157">Esse comando obtém uma lista dos aliases associados ao `Get-ChildItem` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-157">This command gets a list of the aliases that are associated with the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="eeaf4-158">Ele usa a propriedade de **definição** , que armazena o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-158">It uses the **Definition** property, which stores the cmdlet name.</span></span>

```powershell
Get-Item -Path Alias:* | Where-Object {$_.Definition -eq "Get-ChildItem"}
```

## <a name="creating-aliases"></a><span data-ttu-id="eeaf4-159">Criando aliases</span><span class="sxs-lookup"><span data-stu-id="eeaf4-159">Creating aliases</span></span>

### <a name="create-an-alias-from-the-alias-drive"></a><span data-ttu-id="eeaf4-160">Criar um alias da unidade Alias:</span><span class="sxs-lookup"><span data-stu-id="eeaf4-160">Create an alias from the Alias: drive</span></span>

<span data-ttu-id="eeaf4-161">Este comando cria o `serv` alias para o `Get-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-161">This command creates the `serv` alias for the `Get-Service` cmdlet.</span></span> <span data-ttu-id="eeaf4-162">Como o local atual está na `Alias:` unidade, o `-Path` parâmetro não é necessário.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-162">Because the current location is in the `Alias:` drive, the `-Path` parameter is not needed.</span></span>

<span data-ttu-id="eeaf4-163">Esse comando também usa o `-Options` parâmetro dinâmico para definir a opção de **escopo** no alias.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-163">This command also uses the `-Options` dynamic parameter to set the **AllScope** option on the alias.</span></span> <span data-ttu-id="eeaf4-164">O `-Options` parâmetro estará disponível no `New-Item` cmdlet somente quando você estiver na `Alias:` unidade.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-164">The `-Options` parameter is available in the `New-Item` cmdlet only when you are in the `Alias:` drive.</span></span> <span data-ttu-id="eeaf4-165">O ponto ( `.` ) indica o diretório atual, que é a unidade de alias.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-165">The dot (`.`) indicates the current directory, which is the alias drive.</span></span>

```
PS Alias:\> New-Item -Path . -Name serv -Value Get-Service -Options "AllScope"
```

### <a name="create-an-alias-with-an-absolute-path"></a><span data-ttu-id="eeaf4-166">Criar um alias com um caminho absoluto</span><span class="sxs-lookup"><span data-stu-id="eeaf4-166">Create an alias with an absolute path</span></span>

<span data-ttu-id="eeaf4-167">Você pode criar um alias para qualquer item que chama um comando.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-167">You can create an alias for any item that invokes a command.</span></span>
<span data-ttu-id="eeaf4-168">Este comando cria o `np` alias para `Notepad.exe` .</span><span class="sxs-lookup"><span data-stu-id="eeaf4-168">This command creates the `np` alias for `Notepad.exe`.</span></span>

```powershell
New-Item -Path Alias:np -Value c:\windows\notepad.exe
```

### <a name="create-an-alias-to-a-new-function"></a><span data-ttu-id="eeaf4-169">Criar um alias para uma nova função</span><span class="sxs-lookup"><span data-stu-id="eeaf4-169">Create an alias to a new function</span></span>

<span data-ttu-id="eeaf4-170">Você pode criar um alias para qualquer função.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-170">You can create an alias for any function.</span></span> <span data-ttu-id="eeaf4-171">Você pode usar esse recurso para criar um alias que inclui um cmdlet e seus parâmetros.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-171">You can use this feature to create an alias that includes both a cmdlet and its parameters.</span></span>

<span data-ttu-id="eeaf4-172">O primeiro comando cria a `CD32` função, que altera o diretório atual para o `System32` diretório.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-172">The first command creates the `CD32` function, which changes the current directory to the `System32` directory.</span></span> <span data-ttu-id="eeaf4-173">O segundo comando cria o `go` alias para a `CD32` função.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-173">The second command creates the `go` alias for the `CD32` function.</span></span>

<span data-ttu-id="eeaf4-174">Quando o comando for concluído, você poderá usar o `CD32` ou o `go` para invocar a função.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-174">When the command is complete, you can use either `CD32` or `go` to invoke the function.</span></span>

```powershell
function CD32 {Set-Location -Path c:\windows\system32}
Set-Item -Path Alias:go -Value CD32
```

## <a name="changing-aliases"></a><span data-ttu-id="eeaf4-175">Alterando aliases</span><span class="sxs-lookup"><span data-stu-id="eeaf4-175">Changing aliases</span></span>

### <a name="change-the-options-of-an-alias"></a><span data-ttu-id="eeaf4-176">Alterar as opções de um alias</span><span class="sxs-lookup"><span data-stu-id="eeaf4-176">Change the options of an alias</span></span>

<span data-ttu-id="eeaf4-177">Você pode usar o `Set-Item` cmdlet com o `-Options` parâmetro dinâmico para alterar o valor da `-Options` propriedade de um alias.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-177">You can use the `Set-Item` cmdlet with the `-Options` dynamic parameter to change the value of the `-Options` property of an alias.</span></span>

<span data-ttu-id="eeaf4-178">Esse comando define as opções de **escopo** e **somente leitura** para o `dir` alias.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-178">This command sets the **AllScope** and **ReadOnly** options for the `dir` alias.</span></span> <span data-ttu-id="eeaf4-179">O comando usa o `-Options` parâmetro dinâmico do `Set-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-179">The command uses the `-Options` dynamic parameter of the `Set-Item` cmdlet.</span></span> <span data-ttu-id="eeaf4-180">O `-Options` parâmetro está disponível em `Set-Item` quando você o usa com o **alias** ou o provedor de **funções** .</span><span class="sxs-lookup"><span data-stu-id="eeaf4-180">The `-Options` parameter is available in `Set-Item` when you use it with the **Alias** or **Function** provider.</span></span>

```powershell
Set-Item -Path Alias:dir -Options "AllScope,ReadOnly"
```

### <a name="change-an-aliases-referenced-command"></a><span data-ttu-id="eeaf4-181">Alterar um comando de aliases referenciado</span><span class="sxs-lookup"><span data-stu-id="eeaf4-181">Change an aliases referenced command</span></span>

<span data-ttu-id="eeaf4-182">Esse comando usa o `Set-Item` cmdlet para alterar o `gp` alias para que ele represente o `Get-Process` cmdlet em vez do `Get-ItemProperty` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-182">This command uses the `Set-Item` cmdlet to change the `gp` alias so that it represents the `Get-Process` cmdlet instead of the `Get-ItemProperty` cmdlet.</span></span>
<span data-ttu-id="eeaf4-183">O `-Force` parâmetro é necessário porque o valor da propriedade **Options** do `gp` alias é definido como `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="eeaf4-183">The `-Force` parameter is required because the value of the **Options** property of the `gp` alias is set to `ReadOnly`.</span></span> <span data-ttu-id="eeaf4-184">Como o comando é enviado de dentro da `Alias:` unidade, a unidade não é especificada no caminho.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-184">Because the command is submitted from within the `Alias:` drive, the drive is not specified in the path.</span></span>

```powershell
Set-Item -Path gp -Value Get-Process -Force
```

<span data-ttu-id="eeaf4-185">A alteração afeta as quatro propriedades que definem a associação entre o alias e o comando.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-185">The change affects the four properties that define the association between the alias and the command.</span></span> <span data-ttu-id="eeaf4-186">Para exibir o efeito da alteração, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="eeaf4-186">To view the effect of the change, type the following command:</span></span>

```powershell
Get-Item -Path gp | Format-List -Property *
```

### <a name="rename-an-alias"></a><span data-ttu-id="eeaf4-187">Renomear um alias</span><span class="sxs-lookup"><span data-stu-id="eeaf4-187">Rename an alias</span></span>

<span data-ttu-id="eeaf4-188">Esse comando usa o `Rename-Item` cmdlet para alterar o `popd` alias para `pop` .</span><span class="sxs-lookup"><span data-stu-id="eeaf4-188">This command uses the `Rename-Item` cmdlet to change the `popd` alias to `pop`.</span></span>

```powershell
Rename-Item -Path Alias:popd -NewName pop
```

## <a name="copying-an-alias"></a><span data-ttu-id="eeaf4-189">Copiando um alias</span><span class="sxs-lookup"><span data-stu-id="eeaf4-189">Copying an alias</span></span>

<span data-ttu-id="eeaf4-190">Esse comando copia o `pushd` alias para que um novo `push` alias seja criado para o `Push-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-190">This command copies the `pushd` alias so that a new `push` alias is created for the `Push-Location` cmdlet.</span></span>

<span data-ttu-id="eeaf4-191">Quando o novo alias é criado, sua propriedade **Description** tem um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-191">When the new alias is created, its **Description** property has a null value.</span></span>
<span data-ttu-id="eeaf4-192">E, sua propriedade **Option** tem um valor de `None` .</span><span class="sxs-lookup"><span data-stu-id="eeaf4-192">And, its **Option** property has a value of `None`.</span></span> <span data-ttu-id="eeaf4-193">Se o comando for emitido de dentro da `Alias:` unidade, você poderá omitir o nome da unidade do valor do `-Path` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-193">If the command is issued from within the `Alias:` drive, you can omit the drive name from the value of the `-Path` parameter.</span></span>

```powershell
Copy-Item -Path Alias:pushd -Destination Alias:push
```

## <a name="deleting-an-alias"></a><span data-ttu-id="eeaf4-194">Excluindo um alias</span><span class="sxs-lookup"><span data-stu-id="eeaf4-194">Deleting an alias</span></span>

<span data-ttu-id="eeaf4-195">Este comando exclui o `serv` alias da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-195">This command deletes the `serv` alias from the current session.</span></span>
<span data-ttu-id="eeaf4-196">Você pode usar esse comando em qualquer unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-196">You can use this command in any PowerShell drive.</span></span>

```powershell
Remove-Item -Path Alias:serv
```

<span data-ttu-id="eeaf4-197">Esse comando exclui aliases que começam com "s".</span><span class="sxs-lookup"><span data-stu-id="eeaf4-197">This command deletes aliases that begin with "s".</span></span>
<span data-ttu-id="eeaf4-198">Isso não exclui os aliases de somente leitura.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-198">It does not delete read-only aliases.</span></span>

```powershell
Clear-Item -Path Alias:s*
```

### <a name="delete-read-only-aliases"></a><span data-ttu-id="eeaf4-199">Excluir aliases somente leitura</span><span class="sxs-lookup"><span data-stu-id="eeaf4-199">Delete read-only aliases</span></span>

<span data-ttu-id="eeaf4-200">Esse comando exclui todos os aliases da sessão atual, exceto aqueles com um valor de `Constant` para a propriedade **Options** .</span><span class="sxs-lookup"><span data-stu-id="eeaf4-200">This command deletes all aliases from the current session, except those with a value of `Constant` for their **Options** property.</span></span> <span data-ttu-id="eeaf4-201">O `-Force` parâmetro permite que o comando exclua aliases cuja propriedade **Options** tem um valor de `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="eeaf4-201">The `-Force` parameter allows the command to delete aliases whose **Options** property has a value of `ReadOnly`.</span></span>

```powershell
Remove-Item Alias:* -Force
```

## <a name="dynamic-parameters"></a><span data-ttu-id="eeaf4-202">Parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="eeaf4-202">Dynamic parameters</span></span>

<span data-ttu-id="eeaf4-203">Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-203">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="options-systemmanagementautomationscopeditemoptions"></a><span data-ttu-id="eeaf4-204">Opções [System. Management. Automation. ScopedItemOptions]</span><span class="sxs-lookup"><span data-stu-id="eeaf4-204">Options [System.Management.Automation.ScopedItemOptions]</span></span>

<span data-ttu-id="eeaf4-205">Determina o valor da propriedade **Options** de um alias.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-205">Determines the value of the **Options** property of an alias.</span></span>

- <span data-ttu-id="eeaf4-206">**Nenhum**: nenhuma opção.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-206">**None**: No options.</span></span> <span data-ttu-id="eeaf4-207">Esse valor é o padrão.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-207">This value is the default.</span></span>
- <span data-ttu-id="eeaf4-208">**Constante**: o alias não pode ser excluído e suas propriedades não podem ser alteradas.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-208">**Constant**:The alias cannot be deleted and its properties cannot be changed.</span></span>
  <span data-ttu-id="eeaf4-209">A **constante** está disponível somente quando você cria um alias.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-209">**Constant** is available only when you create an alias.</span></span> <span data-ttu-id="eeaf4-210">Você não pode alterar a opção de um alias existente para **constante**.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-210">You cannot change the option of an existing alias to **Constant**.</span></span>
- <span data-ttu-id="eeaf4-211">**Particular**: o alias é visível apenas no escopo atual, não nos escopos filho.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-211">**Private**:The alias is visible only in the current scope, not in the child  scopes.</span></span>
- <span data-ttu-id="eeaf4-212">**ReadOnly**: as propriedades do alias não podem ser alteradas, exceto usando o `-Force` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-212">**ReadOnly**:The properties of the alias cannot be changed except by using the `-Force` parameter.</span></span> <span data-ttu-id="eeaf4-213">Você pode usar `Remove-Item` para excluir o alias.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-213">You can use `Remove-Item` to delete the alias.</span></span>
- <span data-ttu-id="eeaf4-214">**Escopo**: o alias é copiado para todos os novos escopos criados.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-214">**AllScope**:The alias is copied to any new scopes that are created.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="eeaf4-215">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="eeaf4-215">Cmdlets supported</span></span>

- [<span data-ttu-id="eeaf4-216">New-Item</span><span class="sxs-lookup"><span data-stu-id="eeaf4-216">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="eeaf4-217">Set-Item</span><span class="sxs-lookup"><span data-stu-id="eeaf4-217">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="eeaf4-218">Usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="eeaf4-218">Using the pipeline</span></span>

<span data-ttu-id="eeaf4-219">Os cmdlets do provedor aceitam a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-219">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="eeaf4-220">Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-220">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="eeaf4-221">Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-221">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="eeaf4-222">Obtendo ajuda</span><span class="sxs-lookup"><span data-stu-id="eeaf4-222">Getting help</span></span>

<span data-ttu-id="eeaf4-223">A partir do Windows PowerShell 3.0, você pode obter tópicos da Ajuda personalizados para cmdlets do provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-223">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="eeaf4-224">Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um comando [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) em uma unidade do sistema de arquivos ou use o `-Path` parâmetro de [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) para especificar uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="eeaf4-224">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path alias:
```

## <a name="see-also"></a><span data-ttu-id="eeaf4-225">Consulte também</span><span class="sxs-lookup"><span data-stu-id="eeaf4-225">See also</span></span>

[<span data-ttu-id="eeaf4-226">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="eeaf4-226">about_Aliases</span></span>](../About/about_Aliases.md)

[<span data-ttu-id="eeaf4-227">about_Providers</span><span class="sxs-lookup"><span data-stu-id="eeaf4-227">about_Providers</span></span>](../About/about_Providers.md)

