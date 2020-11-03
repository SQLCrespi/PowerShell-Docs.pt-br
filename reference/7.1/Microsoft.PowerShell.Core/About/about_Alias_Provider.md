---
description: Alias
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_alias_provider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor Alias
ms.openlocfilehash: 8edd1a406862e6bf1dcbc5e8215b60c93ac7b13f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196073"
---
# <a name="alias-provider"></a><span data-ttu-id="3dc3e-104">Provedor de alias</span><span class="sxs-lookup"><span data-stu-id="3dc3e-104">Alias provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="3dc3e-105">Nome do provedor</span><span class="sxs-lookup"><span data-stu-id="3dc3e-105">Provider name</span></span>
<span data-ttu-id="3dc3e-106">Alias</span><span class="sxs-lookup"><span data-stu-id="3dc3e-106">Alias</span></span>

## <a name="drives"></a><span data-ttu-id="3dc3e-107">Unidades</span><span class="sxs-lookup"><span data-stu-id="3dc3e-107">Drives</span></span>

`Alias:`

## <a name="capabilities"></a><span data-ttu-id="3dc3e-108">Funcionalidades</span><span class="sxs-lookup"><span data-stu-id="3dc3e-108">Capabilities</span></span>

<span data-ttu-id="3dc3e-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="3dc3e-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="3dc3e-110">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="3dc3e-110">Short description</span></span>

<span data-ttu-id="3dc3e-111">Fornece acesso aos aliases do PowerShell e aos valores que eles representam.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-111">Provides access to the PowerShell aliases and the values that they represent.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="3dc3e-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="3dc3e-112">Detailed description</span></span>

<span data-ttu-id="3dc3e-113">O provedor de **alias** do PowerShell permite que você obtenha, adicione, altere, apague e exclua aliases no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-113">The PowerShell **Alias** provider lets you get, add, change, clear, and delete aliases in PowerShell.</span></span>

<span data-ttu-id="3dc3e-114">Um alias é um nome alternativo para um cmdlet, função, arquivo executável, incluindo scripts.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-114">An alias is an alternate name for a cmdlet, function, executable file, including scripts.</span></span> <span data-ttu-id="3dc3e-115">O PowerShell inclui um conjunto de aliases internos.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-115">PowerShell includes a set of built-in aliases.</span></span> <span data-ttu-id="3dc3e-116">Você pode adicionar seus próprios aliases à sessão atual e ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-116">You can add your own aliases to the current session and to your PowerShell profile.</span></span>

<span data-ttu-id="3dc3e-117">A unidade de **alias** é um namespace simples que contém apenas os objetos de alias.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-117">The **Alias** drive is a flat namespace that contains only the alias objects.</span></span>
<span data-ttu-id="3dc3e-118">Os aliases não possuem itens filho.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-118">The aliases have no child items.</span></span>

<span data-ttu-id="3dc3e-119">O provedor de **alias** dá suporte aos seguintes cmdlets, que são abordados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-119">The **Alias** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="3dc3e-120">Get-Location</span><span class="sxs-lookup"><span data-stu-id="3dc3e-120">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="3dc3e-121">Set-Location</span><span class="sxs-lookup"><span data-stu-id="3dc3e-121">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="3dc3e-122">Get-Item</span><span class="sxs-lookup"><span data-stu-id="3dc3e-122">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="3dc3e-123">New-Item</span><span class="sxs-lookup"><span data-stu-id="3dc3e-123">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="3dc3e-124">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="3dc3e-124">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="3dc3e-125">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="3dc3e-125">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

<span data-ttu-id="3dc3e-126">O PowerShell inclui um conjunto de cmdlets que são projetados para exibir e alterar aliases.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-126">PowerShell includes a set of cmdlets that are designed to view and to change aliases.</span></span> <span data-ttu-id="3dc3e-127">Quando você usa cmdlets de **alias** , não é necessário especificar a `Alias:` unidade no nome.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-127">When you use **Alias** cmdlets, you do not need to specify the `Alias:` drive in the name.</span></span> <span data-ttu-id="3dc3e-128">Este artigo não aborda o trabalho com cmdlets de **alias** .</span><span class="sxs-lookup"><span data-stu-id="3dc3e-128">This article does not cover working with **Alias** cmdlets.</span></span>

- [<span data-ttu-id="3dc3e-129">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="3dc3e-129">Export-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [<span data-ttu-id="3dc3e-130">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="3dc3e-130">Get-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [<span data-ttu-id="3dc3e-131">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="3dc3e-131">Import-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [<span data-ttu-id="3dc3e-132">New-Alias</span><span class="sxs-lookup"><span data-stu-id="3dc3e-132">New-Alias</span></span>](xref:Microsoft.PowerShell.Utility.New-Alias)
- [<span data-ttu-id="3dc3e-133">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="3dc3e-133">Set-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Set-Alias)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="3dc3e-134">Tipos expostos por este provedor</span><span class="sxs-lookup"><span data-stu-id="3dc3e-134">Types exposed by this provider</span></span>

<span data-ttu-id="3dc3e-135">Cada alias é uma instância da classe [System. Management. Automation. AliasInfo](/dotnet/api/system.management.automation.aliasinfo) .</span><span class="sxs-lookup"><span data-stu-id="3dc3e-135">Each alias is an instance of the [System.Management.Automation.AliasInfo](/dotnet/api/system.management.automation.aliasinfo) class.</span></span>

## <a name="navigating-the-alias-drive"></a><span data-ttu-id="3dc3e-136">Navegando pela unidade de alias</span><span class="sxs-lookup"><span data-stu-id="3dc3e-136">Navigating the Alias drive</span></span>

<span data-ttu-id="3dc3e-137">O provedor de **alias** expõe seu armazenamento de dados na `Alias:` unidade.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-137">The **Alias** provider exposes its data store in the `Alias:` drive.</span></span> <span data-ttu-id="3dc3e-138">Para trabalhar com aliases, você pode alterar seu local para a `Alias:` unidade usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3dc3e-138">To work with aliases, you can change your location to the `Alias:` drive by using the following command:</span></span>

```powershell
Set-Location Alias:
```

<span data-ttu-id="3dc3e-139">Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-139">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="3dc3e-140">Por exemplo, digite:</span><span class="sxs-lookup"><span data-stu-id="3dc3e-140">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="3dc3e-141">Você também pode trabalhar com o provedor de alias de qualquer outra unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-141">You can also work with the Alias provider from any other PowerShell drive.</span></span> <span data-ttu-id="3dc3e-142">Para fazer referência a um alias de outro local, use o `Alias:` nome da unidade no caminho.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-142">To reference an alias from another location, use the `Alias:` drive name in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="3dc3e-143">O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-143">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="3dc3e-144">Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="3dc3e-144">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="3dc3e-145">e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="3dc3e-145">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

### <a name="displaying-the-contents-of-the-alias-drive"></a><span data-ttu-id="3dc3e-146">Exibindo o conteúdo da unidade Alias:</span><span class="sxs-lookup"><span data-stu-id="3dc3e-146">Displaying the Contents of the Alias: drive</span></span>

<span data-ttu-id="3dc3e-147">Esse comando obtém a lista de todos os aliases quando o local atual é a `Alias:` unidade.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-147">This command gets the list of all the aliases when the current location is the `Alias:` drive.</span></span> <span data-ttu-id="3dc3e-148">Ele usa um caractere curinga `*` para indicar todo o conteúdo do local atual.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-148">It uses a wildcard character `*` to indicate all the contents of the current location.</span></span>

```powershell
PS Alias:\> Get-Item -Path *
```

<span data-ttu-id="3dc3e-149">Na `Alias:` unidade, um ponto `.` , que representa o local atual e um caractere curinga `*` , que representa todos os itens no local atual, têm o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-149">In the `Alias:` drive, a dot `.`, which represents the current location, and a wildcard character `*`, which represents all items in the current location, have the same effect.</span></span> <span data-ttu-id="3dc3e-150">Por exemplo, `Get-Item -Path .` ou `Get-Item \*` produzir o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-150">For example, `Get-Item -Path .` or `Get-Item \*` produce the same result.</span></span>

<span data-ttu-id="3dc3e-151">O provedor de alias não tem contêineres, portanto, o comando acima tem o mesmo efeito quando usado com `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="3dc3e-151">The Alias provider has no containers, so the above command has the same effect when used with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path Alias:
```

### <a name="get-a-selected-alias"></a><span data-ttu-id="3dc3e-152">Obter um alias selecionado</span><span class="sxs-lookup"><span data-stu-id="3dc3e-152">Get a selected alias</span></span>

<span data-ttu-id="3dc3e-153">Esse comando obtém o `ls` alias.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-153">This command gets the `ls` alias.</span></span>
<span data-ttu-id="3dc3e-154">Como ele inclui o caminho, você pode usá-lo em qualquer unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-154">Because it includes the path, you can use it in any PowerShell drive.</span></span>

```powershell
Get-Item -Path Alias:ls
```

<span data-ttu-id="3dc3e-155">Se você estiver na `Alias:` unidade, poderá omitir o nome da unidade do caminho.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-155">If you are in the `Alias:` drive, you can omit the drive name from the path.</span></span>

<span data-ttu-id="3dc3e-156">Você também pode recuperar a definição de um alias prefixando o caminho do provedor com o cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="3dc3e-156">You can also retrieve the definition for an alias by prefixing the provider path with the dollar sign (`$`).</span></span>

```powershell
$Alias:ls
```

### <a name="get-all-aliases-for-a-specific-cmdlet"></a><span data-ttu-id="3dc3e-157">Obter todos os aliases para um cmdlet específico</span><span class="sxs-lookup"><span data-stu-id="3dc3e-157">Get all aliases for a specific cmdlet</span></span>

<span data-ttu-id="3dc3e-158">Esse comando obtém uma lista dos aliases associados ao `Get-ChildItem` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-158">This command gets a list of the aliases that are associated with the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="3dc3e-159">Ele usa a propriedade de **definição** , que armazena o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-159">It uses the **Definition** property, which stores the cmdlet name.</span></span>

```powershell
Get-Item -Path Alias:* | Where-Object {$_.Definition -eq "Get-ChildItem"}
```

## <a name="creating-aliases"></a><span data-ttu-id="3dc3e-160">Criando aliases</span><span class="sxs-lookup"><span data-stu-id="3dc3e-160">Creating aliases</span></span>

### <a name="create-an-alias-from-the-alias-drive"></a><span data-ttu-id="3dc3e-161">Criar um alias da unidade Alias:</span><span class="sxs-lookup"><span data-stu-id="3dc3e-161">Create an alias from the Alias: drive</span></span>

<span data-ttu-id="3dc3e-162">Este comando cria o `serv` alias para o `Get-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-162">This command creates the `serv` alias for the `Get-Service` cmdlet.</span></span> <span data-ttu-id="3dc3e-163">Como o local atual está na `Alias:` unidade, o `-Path` parâmetro não é necessário.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-163">Because the current location is in the `Alias:` drive, the `-Path` parameter is not needed.</span></span>

<span data-ttu-id="3dc3e-164">Esse comando também usa o `-Options` parâmetro dinâmico para definir a opção de **escopo** no alias.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-164">This command also uses the `-Options` dynamic parameter to set the **AllScope** option on the alias.</span></span> <span data-ttu-id="3dc3e-165">O `-Options` parâmetro estará disponível no `New-Item` cmdlet somente quando você estiver na `Alias:` unidade.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-165">The `-Options` parameter is available in the `New-Item` cmdlet only when you are in the `Alias:` drive.</span></span> <span data-ttu-id="3dc3e-166">O ponto ( `.` ) indica o diretório atual, que é a unidade de alias.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-166">The dot (`.`) indicates the current directory, which is the alias drive.</span></span>

```
PS Alias:\> New-Item -Path . -Name serv -Value Get-Service -Options "AllScope"
```

### <a name="create-an-alias-with-an-absolute-path"></a><span data-ttu-id="3dc3e-167">Criar um alias com um caminho absoluto</span><span class="sxs-lookup"><span data-stu-id="3dc3e-167">Create an alias with an absolute path</span></span>

<span data-ttu-id="3dc3e-168">Você pode criar um alias para qualquer item que chama um comando.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-168">You can create an alias for any item that invokes a command.</span></span>
<span data-ttu-id="3dc3e-169">Este comando cria o `np` alias para `Notepad.exe` .</span><span class="sxs-lookup"><span data-stu-id="3dc3e-169">This command creates the `np` alias for `Notepad.exe`.</span></span>

```powershell
New-Item -Path Alias:np -Value c:\windows\notepad.exe
```

### <a name="create-an-alias-to-a-new-function"></a><span data-ttu-id="3dc3e-170">Criar um alias para uma nova função</span><span class="sxs-lookup"><span data-stu-id="3dc3e-170">Create an alias to a new function</span></span>

<span data-ttu-id="3dc3e-171">Você pode criar um alias para qualquer função.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-171">You can create an alias for any function.</span></span> <span data-ttu-id="3dc3e-172">Você pode usar esse recurso para criar um alias que inclui um cmdlet e seus parâmetros.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-172">You can use this feature to create an alias that includes both a cmdlet and its parameters.</span></span>

<span data-ttu-id="3dc3e-173">O primeiro comando cria a `CD32` função, que altera o diretório atual para o `System32` diretório.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-173">The first command creates the `CD32` function, which changes the current directory to the `System32` directory.</span></span> <span data-ttu-id="3dc3e-174">O segundo comando cria o `go` alias para a `CD32` função.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-174">The second command creates the `go` alias for the `CD32` function.</span></span>

<span data-ttu-id="3dc3e-175">Quando o comando for concluído, você poderá usar o `CD32` ou o `go` para invocar a função.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-175">When the command is complete, you can use either `CD32` or `go` to invoke the function.</span></span>

```powershell
function CD32 {Set-Location -Path c:\windows\system32}
Set-Item -Path Alias:go -Value CD32
```

## <a name="changing-aliases"></a><span data-ttu-id="3dc3e-176">Alterando aliases</span><span class="sxs-lookup"><span data-stu-id="3dc3e-176">Changing aliases</span></span>

### <a name="change-the-options-of-an-alias"></a><span data-ttu-id="3dc3e-177">Alterar as opções de um alias</span><span class="sxs-lookup"><span data-stu-id="3dc3e-177">Change the options of an alias</span></span>

<span data-ttu-id="3dc3e-178">Você pode usar o `Set-Item` cmdlet com o `-Options` parâmetro dinâmico para alterar o valor da `-Options` propriedade de um alias.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-178">You can use the `Set-Item` cmdlet with the `-Options` dynamic parameter to change the value of the `-Options` property of an alias.</span></span>

<span data-ttu-id="3dc3e-179">Esse comando define as opções de **escopo** e **somente leitura** para o `dir` alias.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-179">This command sets the **AllScope** and **ReadOnly** options for the `dir` alias.</span></span> <span data-ttu-id="3dc3e-180">O comando usa o `-Options` parâmetro dinâmico do `Set-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-180">The command uses the `-Options` dynamic parameter of the `Set-Item` cmdlet.</span></span> <span data-ttu-id="3dc3e-181">O `-Options` parâmetro está disponível em `Set-Item` quando você o usa com o **alias** ou o provedor de **funções** .</span><span class="sxs-lookup"><span data-stu-id="3dc3e-181">The `-Options` parameter is available in `Set-Item` when you use it with the **Alias** or **Function** provider.</span></span>

```powershell
Set-Item -Path Alias:dir -Options "AllScope,ReadOnly"
```

### <a name="change-an-aliases-referenced-command"></a><span data-ttu-id="3dc3e-182">Alterar um comando de aliases referenciado</span><span class="sxs-lookup"><span data-stu-id="3dc3e-182">Change an aliases referenced command</span></span>

<span data-ttu-id="3dc3e-183">Esse comando usa o `Set-Item` cmdlet para alterar o `gp` alias para que ele represente o `Get-Process` cmdlet em vez do `Get-ItemProperty` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-183">This command uses the `Set-Item` cmdlet to change the `gp` alias so that it represents the `Get-Process` cmdlet instead of the `Get-ItemProperty` cmdlet.</span></span>
<span data-ttu-id="3dc3e-184">O `-Force` parâmetro é necessário porque o valor da propriedade **Options** do `gp` alias é definido como `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="3dc3e-184">The `-Force` parameter is required because the value of the **Options** property of the `gp` alias is set to `ReadOnly`.</span></span> <span data-ttu-id="3dc3e-185">Como o comando é enviado de dentro da `Alias:` unidade, a unidade não é especificada no caminho.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-185">Because the command is submitted from within the `Alias:` drive, the drive is not specified in the path.</span></span>

```powershell
Set-Item -Path gp -Value Get-Process -Force
```

<span data-ttu-id="3dc3e-186">A alteração afeta as quatro propriedades que definem a associação entre o alias e o comando.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-186">The change affects the four properties that define the association between the alias and the command.</span></span> <span data-ttu-id="3dc3e-187">Para exibir o efeito da alteração, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3dc3e-187">To view the effect of the change, type the following command:</span></span>

```powershell
Get-Item -Path gp | Format-List -Property *
```

### <a name="rename-an-alias"></a><span data-ttu-id="3dc3e-188">Renomear um alias</span><span class="sxs-lookup"><span data-stu-id="3dc3e-188">Rename an alias</span></span>

<span data-ttu-id="3dc3e-189">Esse comando usa o `Rename-Item` cmdlet para alterar o `popd` alias para `pop` .</span><span class="sxs-lookup"><span data-stu-id="3dc3e-189">This command uses the `Rename-Item` cmdlet to change the `popd` alias to `pop`.</span></span>

```powershell
Rename-Item -Path Alias:popd -NewName pop
```

## <a name="copying-an-alias"></a><span data-ttu-id="3dc3e-190">Copiando um alias</span><span class="sxs-lookup"><span data-stu-id="3dc3e-190">Copying an alias</span></span>

<span data-ttu-id="3dc3e-191">Esse comando copia o `pushd` alias para que um novo `push` alias seja criado para o `Push-Location` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-191">This command copies the `pushd` alias so that a new `push` alias is created for the `Push-Location` cmdlet.</span></span>

<span data-ttu-id="3dc3e-192">Quando o novo alias é criado, sua propriedade **Description** tem um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-192">When the new alias is created, its **Description** property has a null value.</span></span>
<span data-ttu-id="3dc3e-193">E, sua propriedade **Option** tem um valor de `None` .</span><span class="sxs-lookup"><span data-stu-id="3dc3e-193">And, its **Option** property has a value of `None`.</span></span> <span data-ttu-id="3dc3e-194">Se o comando for emitido de dentro da `Alias:` unidade, você poderá omitir o nome da unidade do valor do `-Path` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-194">If the command is issued from within the `Alias:` drive, you can omit the drive name from the value of the `-Path` parameter.</span></span>

```powershell
Copy-Item -Path Alias:pushd -Destination Alias:push
```

## <a name="deleting-an-alias"></a><span data-ttu-id="3dc3e-195">Excluindo um alias</span><span class="sxs-lookup"><span data-stu-id="3dc3e-195">Deleting an alias</span></span>

<span data-ttu-id="3dc3e-196">Este comando exclui o `serv` alias da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-196">This command deletes the `serv` alias from the current session.</span></span>
<span data-ttu-id="3dc3e-197">Você pode usar esse comando em qualquer unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-197">You can use this command in any PowerShell drive.</span></span>

```powershell
Remove-Item -Path Alias:serv
```

<span data-ttu-id="3dc3e-198">Esse comando exclui aliases que começam com "s".</span><span class="sxs-lookup"><span data-stu-id="3dc3e-198">This command deletes aliases that begin with "s".</span></span>
<span data-ttu-id="3dc3e-199">Isso não exclui os aliases de somente leitura.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-199">It does not delete read-only aliases.</span></span>

```powershell
Clear-Item -Path Alias:s*
```

### <a name="delete-read-only-aliases"></a><span data-ttu-id="3dc3e-200">Excluir aliases somente leitura</span><span class="sxs-lookup"><span data-stu-id="3dc3e-200">Delete read-only aliases</span></span>

<span data-ttu-id="3dc3e-201">Esse comando exclui todos os aliases da sessão atual, exceto aqueles com um valor de `Constant` para a propriedade **Options** .</span><span class="sxs-lookup"><span data-stu-id="3dc3e-201">This command deletes all aliases from the current session, except those with a value of `Constant` for their **Options** property.</span></span> <span data-ttu-id="3dc3e-202">O `-Force` parâmetro permite que o comando exclua aliases cuja propriedade **Options** tem um valor de `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="3dc3e-202">The `-Force` parameter allows the command to delete aliases whose **Options** property has a value of `ReadOnly`.</span></span>

```powershell
Remove-Item Alias:* -Force
```

## <a name="dynamic-parameters"></a><span data-ttu-id="3dc3e-203">Parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="3dc3e-203">Dynamic parameters</span></span>

<span data-ttu-id="3dc3e-204">Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-204">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="options-systemmanagementautomationscopeditemoptions"></a><span data-ttu-id="3dc3e-205">Opções [System. Management. Automation. ScopedItemOptions]</span><span class="sxs-lookup"><span data-stu-id="3dc3e-205">Options [System.Management.Automation.ScopedItemOptions]</span></span>

<span data-ttu-id="3dc3e-206">Determina o valor da propriedade **Options** de um alias.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-206">Determines the value of the **Options** property of an alias.</span></span>

- <span data-ttu-id="3dc3e-207">**Nenhum** : nenhuma opção.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-207">**None** : No options.</span></span> <span data-ttu-id="3dc3e-208">Esse valor é o padrão.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-208">This value is the default.</span></span>
- <span data-ttu-id="3dc3e-209">**Constante** : o alias não pode ser excluído e suas propriedades não podem ser alteradas.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-209">**Constant** :The alias cannot be deleted and its properties cannot be changed.</span></span>
  <span data-ttu-id="3dc3e-210">A **constante** está disponível somente quando você cria um alias.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-210">**Constant** is available only when you create an alias.</span></span> <span data-ttu-id="3dc3e-211">Você não pode alterar a opção de um alias existente para **constante** .</span><span class="sxs-lookup"><span data-stu-id="3dc3e-211">You cannot change the option of an existing alias to **Constant** .</span></span>
- <span data-ttu-id="3dc3e-212">**Particular** : o alias é visível apenas no escopo atual, não nos escopos filho.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-212">**Private** :The alias is visible only in the current scope, not in the child  scopes.</span></span>
- <span data-ttu-id="3dc3e-213">**ReadOnly** : as propriedades do alias não podem ser alteradas, exceto usando o `-Force` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-213">**ReadOnly** :The properties of the alias cannot be changed except by using the `-Force` parameter.</span></span> <span data-ttu-id="3dc3e-214">Você pode usar `Remove-Item` para excluir o alias.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-214">You can use `Remove-Item` to delete the alias.</span></span>
- <span data-ttu-id="3dc3e-215">**Escopo** : o alias é copiado para todos os novos escopos criados.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-215">**AllScope** :The alias is copied to any new scopes that are created.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="3dc3e-216">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="3dc3e-216">Cmdlets supported</span></span>

- [<span data-ttu-id="3dc3e-217">New-Item</span><span class="sxs-lookup"><span data-stu-id="3dc3e-217">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="3dc3e-218">Set-Item</span><span class="sxs-lookup"><span data-stu-id="3dc3e-218">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="3dc3e-219">Usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="3dc3e-219">Using the pipeline</span></span>

<span data-ttu-id="3dc3e-220">Os cmdlets do provedor aceitam a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-220">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="3dc3e-221">Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-221">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="3dc3e-222">Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-222">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="3dc3e-223">Obtendo ajuda</span><span class="sxs-lookup"><span data-stu-id="3dc3e-223">Getting help</span></span>

<span data-ttu-id="3dc3e-224">A partir do Windows PowerShell 3.0, você pode obter tópicos da Ajuda personalizados para cmdlets do provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-224">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="3dc3e-225">Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um comando [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) em uma unidade do sistema de arquivos ou use o `-Path` parâmetro de [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) para especificar uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="3dc3e-225">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path alias:
```

## <a name="see-also"></a><span data-ttu-id="3dc3e-226">Confira também</span><span class="sxs-lookup"><span data-stu-id="3dc3e-226">See also</span></span>

[<span data-ttu-id="3dc3e-227">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="3dc3e-227">about_Aliases</span></span>](../About/about_Aliases.md)

[<span data-ttu-id="3dc3e-228">about_Providers</span><span class="sxs-lookup"><span data-stu-id="3dc3e-228">about_Providers</span></span>](../About/about_Providers.md)

