---
description: Ambiente
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_environment_provider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor Environment
ms.openlocfilehash: f50558ba23d21b5ca145a06086c1c6d9b1fcd3bf
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603360"
---
# <a name="environment-provider"></a><span data-ttu-id="9327d-103">Provedor de ambiente</span><span class="sxs-lookup"><span data-stu-id="9327d-103">Environment provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="9327d-104">Nome do provedor</span><span class="sxs-lookup"><span data-stu-id="9327d-104">Provider name</span></span>
<span data-ttu-id="9327d-105">Ambiente</span><span class="sxs-lookup"><span data-stu-id="9327d-105">Environment</span></span>

## <a name="drives"></a><span data-ttu-id="9327d-106">Unidades</span><span class="sxs-lookup"><span data-stu-id="9327d-106">Drives</span></span>

`Env:`

## <a name="capabilities"></a><span data-ttu-id="9327d-107">Funcionalidades</span><span class="sxs-lookup"><span data-stu-id="9327d-107">Capabilities</span></span>

<span data-ttu-id="9327d-108">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="9327d-108">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="9327d-109">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="9327d-109">Short description</span></span>

<span data-ttu-id="9327d-110">Fornece acesso a variáveis de ambiente do Windows.</span><span class="sxs-lookup"><span data-stu-id="9327d-110">Provides access to the Windows environment variables.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="9327d-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="9327d-111">Detailed description</span></span>

<span data-ttu-id="9327d-112">O provedor de **ambiente** do PowerShell permite que você obtenha, adicione, altere, apague e exclua variáveis de ambiente e valores no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9327d-112">The PowerShell **Environment** provider lets you get, add, change, clear, and delete environment variables and values in PowerShell.</span></span>

<span data-ttu-id="9327d-113">Variáveis de **ambiente** são variáveis nomeadas dinamicamente que descrevem o ambiente no qual seus programas são executados.</span><span class="sxs-lookup"><span data-stu-id="9327d-113">**Environment** variables are dynamically named variables that describe the environment in which your programs run.</span></span> <span data-ttu-id="9327d-114">O Windows e o PowerShell usam variáveis de ambiente para armazenar informações persistentes que afetam a execução do sistema e do processo.</span><span class="sxs-lookup"><span data-stu-id="9327d-114">Windows and PowerShell use environment variables to store persistent information that affect system and process execution.</span></span> <span data-ttu-id="9327d-115">Ao contrário das variáveis do PowerShell, as variáveis de ambiente não estão sujeitas a restrições de escopo.</span><span class="sxs-lookup"><span data-stu-id="9327d-115">Unlike PowerShell variables, environment variables are not subject to scope constraints.</span></span>

<span data-ttu-id="9327d-116">A unidade de **ambiente** é um namespace simples que contém as variáveis de ambiente específicas para a sessão do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="9327d-116">The **Environment** drive is a flat namespace containing the environment variables specific to the current user's session.</span></span> <span data-ttu-id="9327d-117">As variáveis de ambiente não têm nenhum item filho.</span><span class="sxs-lookup"><span data-stu-id="9327d-117">The environment variables have no child items.</span></span>

<span data-ttu-id="9327d-118">O provedor de **ambiente** dá suporte aos seguintes cmdlets, que são abordados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="9327d-118">The **Environment** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="9327d-119">Get-Location</span><span class="sxs-lookup"><span data-stu-id="9327d-119">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="9327d-120">Set-Location</span><span class="sxs-lookup"><span data-stu-id="9327d-120">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="9327d-121">Get-Item</span><span class="sxs-lookup"><span data-stu-id="9327d-121">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="9327d-122">New-Item</span><span class="sxs-lookup"><span data-stu-id="9327d-122">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="9327d-123">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="9327d-123">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="9327d-124">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="9327d-124">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="9327d-125">Tipos expostos por este provedor</span><span class="sxs-lookup"><span data-stu-id="9327d-125">Types exposed by this provider</span></span>

<span data-ttu-id="9327d-126">Cada variável de ambiente é uma instância da classe [System. Collections. DictionaryEntry](/dotnet/api/system.collections.dictionaryentry) .</span><span class="sxs-lookup"><span data-stu-id="9327d-126">Each environment variable is an instance of the [System.Collections.DictionaryEntry](/dotnet/api/system.collections.dictionaryentry) class.</span></span> <span data-ttu-id="9327d-127">O nome da variável é a chave do dicionário.</span><span class="sxs-lookup"><span data-stu-id="9327d-127">The name of the variable is the dictionary key.</span></span> <span data-ttu-id="9327d-128">O valor da variável de ambiente é o valor do dicionário.</span><span class="sxs-lookup"><span data-stu-id="9327d-128">The value of the environment variable is the dictionary value.</span></span>

## <a name="navigating-the-environment-drive"></a><span data-ttu-id="9327d-129">Navegando pela unidade do ambiente</span><span class="sxs-lookup"><span data-stu-id="9327d-129">Navigating the Environment drive</span></span>

<span data-ttu-id="9327d-130">O provedor de **ambiente** expõe seu armazenamento de dados na `Env:` unidade.</span><span class="sxs-lookup"><span data-stu-id="9327d-130">The **Environment** provider exposes its data store in the `Env:` drive.</span></span> <span data-ttu-id="9327d-131">Para trabalhar com variáveis de ambiente, altere seu local para a `Env:` unidade ( `Set-Location Env:` ) ou trabalhe de outra unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9327d-131">To work with environment variables, change your location to the `Env:` drive (`Set-Location Env:`), or work from another PowerShell drive.</span></span> <span data-ttu-id="9327d-132">Para fazer referência a uma variável de ambiente de outro local, use o `Env:` nome da unidade no caminho.</span><span class="sxs-lookup"><span data-stu-id="9327d-132">To reference an environment variable from another location, use the `Env:` drive name in the path.</span></span>

```powershell
Set-Location Env:
```

<span data-ttu-id="9327d-133">Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="9327d-133">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="9327d-134">Por exemplo, digite:</span><span class="sxs-lookup"><span data-stu-id="9327d-134">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="9327d-135">Você também pode trabalhar com o provedor de **ambiente** de qualquer outra unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9327d-135">You can also work with the **Environment** provider from any other PowerShell drive.</span></span> <span data-ttu-id="9327d-136">Para fazer referência a uma variável de ambiente de outro local, use o nome da unidade `Env:` no caminho.</span><span class="sxs-lookup"><span data-stu-id="9327d-136">To reference an environment variable from another location, use the drive name `Env:` in the path.</span></span>

<span data-ttu-id="9327d-137">O provedor de **ambiente** também expõe variáveis de ambiente usando um prefixo variável de `$env:` .</span><span class="sxs-lookup"><span data-stu-id="9327d-137">The **Environment** provider also exposes environment variables using a variable prefix of `$env:`.</span></span>  <span data-ttu-id="9327d-138">O comando a seguir exibe o conteúdo da variável de ambiente **ProgramFiles** .</span><span class="sxs-lookup"><span data-stu-id="9327d-138">The following command views the contents of the **ProgramFiles** environment variable.</span></span> <span data-ttu-id="9327d-139">O `$env:` prefixo da variável pode ser usado em qualquer unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9327d-139">The `$env:` variable prefix can be used from any PowerShell drive.</span></span>

```
PS C:\> $env:ProgramFiles
C:\Program Files
```

<span data-ttu-id="9327d-140">Você também pode alterar o valor de uma variável de ambiente usando o `$env:` prefixo da variável.</span><span class="sxs-lookup"><span data-stu-id="9327d-140">You can also change the value of an environment variable using the `$env:` variable prefix.</span></span>  <span data-ttu-id="9327d-141">Todas as alterações feitas somente pertencem à sessão atual do PowerShell enquanto estiverem ativas.</span><span class="sxs-lookup"><span data-stu-id="9327d-141">Any changes made only pertain to the current PowerShell session for as long as it is active.</span></span>

> [!NOTE]
> <span data-ttu-id="9327d-142">O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor.</span><span class="sxs-lookup"><span data-stu-id="9327d-142">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="9327d-143">Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="9327d-143">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="9327d-144">e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="9327d-144">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-environment-variables"></a><span data-ttu-id="9327d-145">Obtendo variáveis de ambiente</span><span class="sxs-lookup"><span data-stu-id="9327d-145">Getting environment variables</span></span>

<span data-ttu-id="9327d-146">Esse comando lista todas as variáveis de ambiente na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="9327d-146">This command lists all the environment variables in the current session.</span></span>

```powershell
Get-Item -Path Env:
```

<span data-ttu-id="9327d-147">Você pode usar esse comando em qualquer unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9327d-147">You can use this command from any PowerShell drive.</span></span>

<span data-ttu-id="9327d-148">O provedor de ambiente não tem contêineres, portanto, o comando acima tem o mesmo efeito quando usado com `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="9327d-148">The Environment provider has no containers, so the above command has the same effect when used with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path Env:
```

### <a name="get-a-selected-environment-variable"></a><span data-ttu-id="9327d-149">Obter uma variável de ambiente selecionada</span><span class="sxs-lookup"><span data-stu-id="9327d-149">Get a selected environment variable</span></span>

<span data-ttu-id="9327d-150">Esse comando obtém a `WINDIR` variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="9327d-150">This command gets the `WINDIR` environment Variable.</span></span>

```powershell
Get-ChildItem -Path Env:windir
```

<span data-ttu-id="9327d-151">Você também pode usar o formato de prefixo de variável também.</span><span class="sxs-lookup"><span data-stu-id="9327d-151">You can also use the variable prefix format as well.</span></span>

```powershell
$env:windir
```

## <a name="create-an-environment-variable"></a><span data-ttu-id="9327d-152">Criar uma variável de ambiente</span><span class="sxs-lookup"><span data-stu-id="9327d-152">Create an environment variable</span></span>

<span data-ttu-id="9327d-153">Esse comando cria a `USERMODE` variável de ambiente com um valor de "não administrador".</span><span class="sxs-lookup"><span data-stu-id="9327d-153">This command creates the `USERMODE` environment variable with a value of "Non-Admin".</span></span> <span data-ttu-id="9327d-154">O `-Path` valor do parâmetro cria o novo item na `Env:` unidade.</span><span class="sxs-lookup"><span data-stu-id="9327d-154">The `-Path` parameter value creates the new item in the `Env:` drive.</span></span> <span data-ttu-id="9327d-155">A nova variável de ambiente só pode ser usada na sessão atual do PowerShell enquanto estiver ativa.</span><span class="sxs-lookup"><span data-stu-id="9327d-155">The new environment variable is only usable in the current PowerShell session for as long as it is active.</span></span>

```powershell
PS C:\> New-Item -Path Env: -Name USERMODE -Value Non-Admin
```

## <a name="changing-an-environment-variable"></a><span data-ttu-id="9327d-156">Alterando uma variável de ambiente</span><span class="sxs-lookup"><span data-stu-id="9327d-156">Changing an environment variable</span></span>

### <a name="rename-an-environment-variable"></a><span data-ttu-id="9327d-157">Renomear uma variável de ambiente</span><span class="sxs-lookup"><span data-stu-id="9327d-157">Rename an environment variable</span></span>

<span data-ttu-id="9327d-158">Esse comando usa o `Rename-Item` cmdlet para alterar o nome da `USERMODE` variável de ambiente que você criou para `USERROLE` .</span><span class="sxs-lookup"><span data-stu-id="9327d-158">This command uses the `Rename-Item` cmdlet to change the name of the `USERMODE` environment variable that you created to `USERROLE`.</span></span> <span data-ttu-id="9327d-159">Não altere o nome de uma variável de ambiente que usa o sistema.</span><span class="sxs-lookup"><span data-stu-id="9327d-159">Do not change the name of an environment variable that the system uses.</span></span> <span data-ttu-id="9327d-160">Embora essas alterações afetem apenas a sessão atual, elas podem fazer com que o sistema ou um programa seja operado de forma incorreta.</span><span class="sxs-lookup"><span data-stu-id="9327d-160">Although these changes affect only the current session, they might cause the system or a program to operate incorrectly.</span></span>

```powershell
Rename-Item -Path Env:USERMODE -NewName USERROLE
```

### <a name="change-an-environment-variable"></a><span data-ttu-id="9327d-161">Alterar uma variável de ambiente</span><span class="sxs-lookup"><span data-stu-id="9327d-161">Change an environment variable</span></span>

<span data-ttu-id="9327d-162">Esse comando usa o `Set-Item` cmdlet para alterar o valor da `USERROLE` variável de ambiente para "administrador".</span><span class="sxs-lookup"><span data-stu-id="9327d-162">This command uses the `Set-Item` cmdlet to change the value of the `USERROLE` environment variable to "Administrator".</span></span>

```powershell
Set-Item -Path Env:USERROLE -Value Administrator
```

## <a name="copy-an-environment-variable"></a><span data-ttu-id="9327d-163">Copiar uma variável de ambiente</span><span class="sxs-lookup"><span data-stu-id="9327d-163">Copy an environment variable</span></span>

<span data-ttu-id="9327d-164">Esse comando copia o valor da `USERROLE` variável de ambiente para a `USERROLE2` variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="9327d-164">This command copies the value of the `USERROLE` environment variable to the `USERROLE2` environment Variable.</span></span>

```powershell
Copy-Item -Path Env:USERROLE -Destination Env:USERROLE2
```

## <a name="remove-an-environment-variable"></a><span data-ttu-id="9327d-165">Remover uma variável de ambiente</span><span class="sxs-lookup"><span data-stu-id="9327d-165">Remove an environment variable</span></span>

<span data-ttu-id="9327d-166">Esse comando exclui a `USERROLE2` variável de ambiente da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="9327d-166">This command deletes the `USERROLE2` environment variable from the current session.</span></span>

```powershell
Remove-Item -Path Env:USERROLE2
```

## <a name="remove-an-environment-variable-with-clear-item"></a><span data-ttu-id="9327d-167">Remover uma variável de ambiente com Clear-Item</span><span class="sxs-lookup"><span data-stu-id="9327d-167">Remove an environment variable with Clear-Item</span></span>

<span data-ttu-id="9327d-168">Esse comando exclui a `USERROLE` variável de ambiente limpando seu valor.</span><span class="sxs-lookup"><span data-stu-id="9327d-168">This command deletes the `USERROLE` environment variable by clearing its value.</span></span>

```powershell
Clear-Item -Path Env:USERROLE
```

## <a name="using-the-pipeline"></a><span data-ttu-id="9327d-169">Usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="9327d-169">Using the pipeline</span></span>

<span data-ttu-id="9327d-170">Os cmdlets do provedor aceitam a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="9327d-170">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="9327d-171">Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor.</span><span class="sxs-lookup"><span data-stu-id="9327d-171">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="9327d-172">Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="9327d-172">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="9327d-173">Obtendo ajuda</span><span class="sxs-lookup"><span data-stu-id="9327d-173">Getting help</span></span>

<span data-ttu-id="9327d-174">A partir do Windows PowerShell 3.0, você pode obter tópicos da Ajuda personalizados para cmdlets do provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="9327d-174">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="9327d-175">Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um comando [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) em uma unidade do sistema de arquivos ou use o `-Path` parâmetro de [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) para especificar uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="9327d-175">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path env:
```

## <a name="see-also"></a><span data-ttu-id="9327d-176">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9327d-176">See also</span></span>

[<span data-ttu-id="9327d-177">about_Providers</span><span class="sxs-lookup"><span data-stu-id="9327d-177">about_Providers</span></span>](../About/about_Providers.md)

