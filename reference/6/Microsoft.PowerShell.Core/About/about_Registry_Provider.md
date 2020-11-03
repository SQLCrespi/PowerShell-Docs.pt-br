---
description: Registro
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_registry_provider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Provedor Registry
ms.openlocfilehash: 13ffc6b07150dc7bb5f6bcc2310b44d3b570562c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195663"
---
# <a name="registry-provider"></a><span data-ttu-id="54697-104">Provedor de registro</span><span class="sxs-lookup"><span data-stu-id="54697-104">Registry provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="54697-105">Nome do provedor</span><span class="sxs-lookup"><span data-stu-id="54697-105">Provider name</span></span>

<span data-ttu-id="54697-106">Registro</span><span class="sxs-lookup"><span data-stu-id="54697-106">Registry</span></span>

## <a name="drives"></a><span data-ttu-id="54697-107">Unidades</span><span class="sxs-lookup"><span data-stu-id="54697-107">Drives</span></span>

<span data-ttu-id="54697-108">`HKLM:`, `HKCU:`</span><span class="sxs-lookup"><span data-stu-id="54697-108">`HKLM:`, `HKCU:`</span></span>

## <a name="capabilities"></a><span data-ttu-id="54697-109">Funcionalidades</span><span class="sxs-lookup"><span data-stu-id="54697-109">Capabilities</span></span>

<span data-ttu-id="54697-110">**ShouldProcess** , **UseTransactions**</span><span class="sxs-lookup"><span data-stu-id="54697-110">**ShouldProcess** , **UseTransactions**</span></span>

## <a name="short-description"></a><span data-ttu-id="54697-111">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="54697-111">Short description</span></span>

<span data-ttu-id="54697-112">Fornece acesso às chaves, entradas e valores do registro no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54697-112">Provides access to the registry keys, entries, and values in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="54697-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="54697-113">Detailed description</span></span>

<span data-ttu-id="54697-114">O provedor **do registro do** PowerShell permite que você obtenha, adicione, altere, apague e exclua chaves, entradas e valores do registro no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54697-114">The PowerShell **Registry** provider lets you get, add, change, clear, and delete registry keys, entries, and values in PowerShell.</span></span>

<span data-ttu-id="54697-115">As unidades **do registro** são um namespace hierárquico que contém as chaves do registro e as subchaves em seu computador.</span><span class="sxs-lookup"><span data-stu-id="54697-115">The **Registry** drives are a hierarchical namespace containing the registry keys and subkeys on your computer.</span></span> <span data-ttu-id="54697-116">Valores e entradas de Registro não são componentes dessa hierarquia.</span><span class="sxs-lookup"><span data-stu-id="54697-116">Registry entries and values are not components of that hierarchy.</span></span> <span data-ttu-id="54697-117">Em vez disso, eles são propriedades de cada uma das chaves.</span><span class="sxs-lookup"><span data-stu-id="54697-117">Instead, they are properties of each of the keys.</span></span>

<span data-ttu-id="54697-118">O provedor de **registro** dá suporte aos seguintes cmdlets, que são abordados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="54697-118">The **Registry** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="54697-119">Get-Location</span><span class="sxs-lookup"><span data-stu-id="54697-119">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="54697-120">Set-Location</span><span class="sxs-lookup"><span data-stu-id="54697-120">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="54697-121">Get-Item</span><span class="sxs-lookup"><span data-stu-id="54697-121">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="54697-122">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="54697-122">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="54697-123">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="54697-123">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="54697-124">Move-Item</span><span class="sxs-lookup"><span data-stu-id="54697-124">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="54697-125">New-Item</span><span class="sxs-lookup"><span data-stu-id="54697-125">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="54697-126">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="54697-126">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="54697-127">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="54697-127">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="54697-128">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="54697-128">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="54697-129">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="54697-129">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="54697-130">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="54697-130">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="54697-131">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="54697-131">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="54697-132">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="54697-132">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="54697-133">Tipos expostos por este provedor</span><span class="sxs-lookup"><span data-stu-id="54697-133">Types exposed by this provider</span></span>

<span data-ttu-id="54697-134">As chaves do registro são representadas como instâncias da classe [Microsoft. Win32. RegistryKey](/dotnet/api/microsoft.win32.registrykey) .</span><span class="sxs-lookup"><span data-stu-id="54697-134">Registry keys are represented as instances of the [Microsoft.Win32.RegistryKey](/dotnet/api/microsoft.win32.registrykey) class.</span></span> <span data-ttu-id="54697-135">As entradas do registro são representadas como instâncias da classe [PSCustomObject](/dotnet/api/system.management.automation.pscustomobject) .</span><span class="sxs-lookup"><span data-stu-id="54697-135">Registry entries are represented as instances of the [PSCustomObject](/dotnet/api/system.management.automation.pscustomobject) class.</span></span>

## <a name="navigating-the-registry-drives"></a><span data-ttu-id="54697-136">Navegando pelas unidades do registro</span><span class="sxs-lookup"><span data-stu-id="54697-136">Navigating the Registry drives</span></span>

<span data-ttu-id="54697-137">O provedor de **registro** expõe seu armazenamento de dados como duas unidades padrão.</span><span class="sxs-lookup"><span data-stu-id="54697-137">The **Registry** provider exposes its data store as two default drives.</span></span> <span data-ttu-id="54697-138">O local do registro HKEY_LOCAL_MACHINE é mapeado para a `HKLM:` unidade e HKEY_CURRENT_USER é mapeado para a `HKCU:` unidade.</span><span class="sxs-lookup"><span data-stu-id="54697-138">The registry location HKEY_LOCAL_MACHINE is mapped to the `HKLM:` drive and HKEY_CURRENT_USER is mapped to the `HKCU:` drive.</span></span> <span data-ttu-id="54697-139">Para trabalhar com o registro, você pode alterar seu local para a `HKLM:` unidade usando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="54697-139">To work with the registry, you can change your location to the `HKLM:` drive using the following command.</span></span>

```powershell
Set-Location HKLM:
```

<span data-ttu-id="54697-140">Para retornar a uma unidade de sistema de arquivos, digite o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="54697-140">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="54697-141">Por exemplo, digite:</span><span class="sxs-lookup"><span data-stu-id="54697-141">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="54697-142">Você também pode trabalhar com o provedor de **registro** de qualquer outra unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54697-142">You can also work with the **Registry** provider from any other PowerShell drive.</span></span> <span data-ttu-id="54697-143">Para fazer referência a uma chave do registro de outro local, use o nome da unidade ( `HKLM:` , `HKCU:` ) no caminho.</span><span class="sxs-lookup"><span data-stu-id="54697-143">To reference a registry key from another location, use the drive name (`HKLM:`, `HKCU:`) in the path.</span></span> <span data-ttu-id="54697-144">Use uma barra invertida ( \\ ) ou uma barra (/) para indicar um nível da unidade do **registro** .</span><span class="sxs-lookup"><span data-stu-id="54697-144">Use a backslash (\\) or a forward slash (/) to indicate a level of the **Registry** drive.</span></span>

```powershell
PS C:\> cd HKLM:\Software
```

> [!NOTE]
> <span data-ttu-id="54697-145">O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor.</span><span class="sxs-lookup"><span data-stu-id="54697-145">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="54697-146">Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="54697-146">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location), and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

<span data-ttu-id="54697-147">Este último exemplo mostra outra sintaxe de caminho que você pode usar para navegar pelo provedor de **registro** .</span><span class="sxs-lookup"><span data-stu-id="54697-147">This last example shows another path syntax you can use to navigate the **Registry** provider.</span></span> <span data-ttu-id="54697-148">Essa sintaxe usa o nome do provedor, seguida por dois dois-pontos `::` .</span><span class="sxs-lookup"><span data-stu-id="54697-148">This syntax uses the provider name, followed by two colons `::`.</span></span> <span data-ttu-id="54697-149">Essa sintaxe permite que você use o nome completo do HIVE, em vez do nome da unidade mapeada `HKLM` .</span><span class="sxs-lookup"><span data-stu-id="54697-149">This syntax allows you to use the full HIVE name, instead of the mapped drive name `HKLM`.</span></span>

```powershell
cd "Registry::HKEY_LOCAL_MACHINE\Software"
```

## <a name="displaying-the-contents-of-registry-keys"></a><span data-ttu-id="54697-150">Exibindo o conteúdo das chaves do registro</span><span class="sxs-lookup"><span data-stu-id="54697-150">Displaying the contents of registry keys</span></span>

<span data-ttu-id="54697-151">O registro é dividido em chaves, subchaves e entradas.</span><span class="sxs-lookup"><span data-stu-id="54697-151">The registry is divided into keys, subkeys, and entries.</span></span> <span data-ttu-id="54697-152">Para obter mais informações sobre a estrutura do registro, consulte [estrutura do registro](/windows/desktop/sysinfo/structure-of-the-registry).</span><span class="sxs-lookup"><span data-stu-id="54697-152">For more information about registry structure, see [Structure of the Registry](/windows/desktop/sysinfo/structure-of-the-registry).</span></span>

<span data-ttu-id="54697-153">Em uma unidade de **registro** , cada chave é um contêiner.</span><span class="sxs-lookup"><span data-stu-id="54697-153">In a **Registry** drive, each key is a container.</span></span> <span data-ttu-id="54697-154">Uma chave pode conter qualquer número de chaves.</span><span class="sxs-lookup"><span data-stu-id="54697-154">A key can contain any number of keys.</span></span> <span data-ttu-id="54697-155">Uma chave do registro que tem uma chave pai é chamada de subchave.</span><span class="sxs-lookup"><span data-stu-id="54697-155">A registry key that has a parent key is called a subkey.</span></span> <span data-ttu-id="54697-156">Você pode usar `Get-ChildItem` para exibir as chaves do registro e `Set-Location` navegar até um caminho de chave.</span><span class="sxs-lookup"><span data-stu-id="54697-156">You can use `Get-ChildItem` to view registry keys and `Set-Location` to navigate to a key path.</span></span>

<span data-ttu-id="54697-157">Os valores do registro são atributos de uma chave do registro.</span><span class="sxs-lookup"><span data-stu-id="54697-157">Registry values are attributes of a registry key.</span></span> <span data-ttu-id="54697-158">Na unidade **do registro** , eles são chamados de **Propriedades de item** .</span><span class="sxs-lookup"><span data-stu-id="54697-158">In the **Registry** drive, they are called **Item Properties** .</span></span> <span data-ttu-id="54697-159">Uma chave do registro pode ter as duas chaves filho e as propriedades do item.</span><span class="sxs-lookup"><span data-stu-id="54697-159">A registry key can have both children keys and item properties.</span></span>

<span data-ttu-id="54697-160">Neste exemplo, a diferença entre `Get-Item` e `Get-ChildItem` é mostrada.</span><span class="sxs-lookup"><span data-stu-id="54697-160">In this example, the difference between `Get-Item` and `Get-ChildItem` is shown.</span></span> <span data-ttu-id="54697-161">Ao usar `Get-Item` a chave do registro "spooler", você pode exibir suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="54697-161">When you use `Get-Item` on the "Spooler" registry key, you can view its properties.</span></span>

```
PS C:\ > Get-Item -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler


    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services


Name        Property
----        --------
Spooler     DependOnService    : {RPCSS, http}
            Description        : @%systemroot%\system32\spoolsv.exe,-2
            DisplayName        : @%systemroot%\system32\spoolsv.exe,-1
            ErrorControl       : 1
            FailureActions     : {16, 14, 0, 0...}
            Group              : SpoolerGroup
            ImagePath          : C:\WINDOWS\System32\spoolsv.exe
            ObjectName         : LocalSystem
            RequiredPrivileges : {SeTcbPrivilege, SeImpersonatePrivilege, ...
            ServiceSidType     : 1
            Start              : 2
            Type               : 27
```

<span data-ttu-id="54697-162">Cada chave do registro também pode ter subchaves.</span><span class="sxs-lookup"><span data-stu-id="54697-162">Each registry key can also have subkeys.</span></span> <span data-ttu-id="54697-163">Quando você usa `Get-Item` o em uma chave do registro, as subchaves não são exibidas.</span><span class="sxs-lookup"><span data-stu-id="54697-163">When you use `Get-Item` on a registry key, the subkeys are not displayed.</span></span> <span data-ttu-id="54697-164">O `Get-ChildItem` cmdlet mostrará os itens filhos da chave "spooler", incluindo as propriedades de cada subchave.</span><span class="sxs-lookup"><span data-stu-id="54697-164">The `Get-ChildItem` cmdlet will show you children items of the "Spooler" key, including each subkey's properties.</span></span> <span data-ttu-id="54697-165">As propriedades de chaves pai não são mostradas ao usar `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="54697-165">The parent keys properties are not shown when using `Get-ChildItem`.</span></span>

```
PS C:\> Get-ChildItem -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler


    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Spooler


Name             Property
----             --------
Performance      Close           : PerfClose
                 Collect         : PerfCollect
                 Collect Timeout : 2000
                 Library         : C:\Windows\System32\winspool.drv
                 Object List     : 1450
                 Open            : PerfOpen
                 Open Timeout    : 4000
Security         Security : {1, 0, 20, 128...}
```

<span data-ttu-id="54697-166">O `Get-Item` cmdlet também pode ser usado no local atual.</span><span class="sxs-lookup"><span data-stu-id="54697-166">The `Get-Item` cmdlet can also be used on the current location.</span></span> <span data-ttu-id="54697-167">O exemplo a seguir navega para a chave do registro "spooler" e obtém as propriedades do item.</span><span class="sxs-lookup"><span data-stu-id="54697-167">The following example navigates to the "Spooler" registry key and gets the item properties.</span></span>
<span data-ttu-id="54697-168">O ponto `.` é usado para indicar o local atual.</span><span class="sxs-lookup"><span data-stu-id="54697-168">The dot `.` is used to indicate the current location.</span></span>

```
PS C:\> cd HKLM:\System\CurrentControlSet\Services\Spooler
PS HKLM:\SYSTEM\CurrentControlSet\Services\Spooler> Get-Item .

    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services

Name             Property
----             --------
Spooler          DependOnService    : {RPCSS, http}
                 Description        : @%systemroot%\system32\spoolsv.exe,-2
...
```

<span data-ttu-id="54697-169">Para obter mais informações sobre os cmdlets abordados nesta seção, consulte os artigos a seguir.</span><span class="sxs-lookup"><span data-stu-id="54697-169">For more information on the cmdlets covered in this section, see the following articles.</span></span>

<span data-ttu-id="54697-170">-[Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) 
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)</span><span class="sxs-lookup"><span data-stu-id="54697-170">-[Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
-[Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)</span></span>

## <a name="viewing-registry-key-values"></a><span data-ttu-id="54697-171">Exibindo valores de chave do registro</span><span class="sxs-lookup"><span data-stu-id="54697-171">Viewing registry key values</span></span>

<span data-ttu-id="54697-172">Os valores de chave do registro são armazenados como propriedades de cada chave do registro.</span><span class="sxs-lookup"><span data-stu-id="54697-172">Registry key values are stored as properties of each registry key.</span></span> <span data-ttu-id="54697-173">O `Get-ItemProperty` cmdlet exibe as propriedades da chave do registro usando o nome que você especificar.</span><span class="sxs-lookup"><span data-stu-id="54697-173">The `Get-ItemProperty` cmdlet views registry key properties using the name you specify.</span></span> <span data-ttu-id="54697-174">O resultado é um **PSCustomObject** que contém as propriedades que você especificar.</span><span class="sxs-lookup"><span data-stu-id="54697-174">The result is a **PSCustomObject** containing the properties you specify.</span></span>

<span data-ttu-id="54697-175">O exemplo a seguir usa o `Get-ItemProperty` cmdlet para exibir todas as propriedades.</span><span class="sxs-lookup"><span data-stu-id="54697-175">The Following example uses the `Get-ItemProperty` cmdlet to view all properties.</span></span> <span data-ttu-id="54697-176">Armazenar o objeto resultante em uma variável permite que você acesse o valor da propriedade desejada.</span><span class="sxs-lookup"><span data-stu-id="54697-176">Storing the resulting object in a variable allows you to access the desired property value.</span></span>

```powershell
$p = Get-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler
$p.DependOnService
```

```output
RPCSS
http
```

<span data-ttu-id="54697-177">A especificação de um valor para o `-Name` parâmetro seleciona as propriedades que você especificar e retorna o **PSCustomObject** .</span><span class="sxs-lookup"><span data-stu-id="54697-177">Specifying a value for the `-Name` parameter selects the properties you specify and returns the **PSCustomObject** .</span></span>  <span data-ttu-id="54697-178">O exemplo a seguir mostra a diferença na saída quando você usa o `-Name` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="54697-178">The following example shows the difference in output when you use the `-Name` parameter.</span></span>

```
PS C:\> Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Wbem

BUILD                      : 17134.1
Installation Directory     : C:\WINDOWS\system32\WBEM
MOF Self-Install Directory : C:\WINDOWS\system32\WBEM\MOF
PSPath                     : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wbem
PSParentPath               : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft
PSChildName                : Wbem
PSDrive                    : HKLM
PSProvider                 : Microsoft.PowerShell.Core\Registry

PS C:\> Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD

BUILD        : 17134.1
PSPath       : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wbem
PSParentPath : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft
PSChildName  : Wbem
PSDrive      : HKLM
PSProvider   : Microsoft.PowerShell.Core\Registry
```

<span data-ttu-id="54697-179">A partir do PowerShell 5,0, o `Get-ItemPropertyValue` cmdlet retorna apenas o valor da propriedade que você especificar.</span><span class="sxs-lookup"><span data-stu-id="54697-179">Beginning in PowerShell 5.0, the `Get-ItemPropertyValue` cmdlet returns only the value of the property you specify.</span></span>

```powershell
Get-ItemPropertyValue -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD
```

```output
17134.1
```

<span data-ttu-id="54697-180">Para obter mais informações sobre os cmdlets usados nesta seção, consulte os artigos a seguir.</span><span class="sxs-lookup"><span data-stu-id="54697-180">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="54697-181">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="54697-181">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="54697-182">Get-ItemPropertyValue</span><span class="sxs-lookup"><span data-stu-id="54697-182">Get-ItemPropertyValue</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)

## <a name="changing-registry-key-values"></a><span data-ttu-id="54697-183">Alterando valores de chave do registro</span><span class="sxs-lookup"><span data-stu-id="54697-183">Changing registry key values</span></span>

<span data-ttu-id="54697-184">O `Set-ItemProperty` cmdlet definirá atributos para chaves do registro.</span><span class="sxs-lookup"><span data-stu-id="54697-184">The `Set-ItemProperty` cmdlet will set attributes for registry keys.</span></span> <span data-ttu-id="54697-185">O exemplo a seguir usa `Set-ItemProperty` para alterar o tipo de início do serviço de spooler para manual.</span><span class="sxs-lookup"><span data-stu-id="54697-185">The following example uses `Set-ItemProperty` to change the spooler service start type to manual.</span></span> <span data-ttu-id="54697-186">O exemplo altera o **StartType** de volta para *automático* usando o `Set-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="54697-186">The example changes the **StartType** back to *Automatic* using the `Set-Service` cmdlet.</span></span>

```
PS C:\> Get-Service spooler | Select-Object Name, StartMode

Name    StartType
----    ---------
spooler Automatic

PS C:\> $path = "HKLM:\SYSTEM\CurrentControlSet\Services\Spooler\"
PS C:\> Set-ItemProperty -Path $path -Name Start -Value 3
PS C:\> Get-Service spooler | Select-Object Name, StartMode

Name    StartType
----    ---------
spooler    Manual

PS C:\> Set-Service -Name Spooler -StartupType Automatic
```

<span data-ttu-id="54697-187">Cada chave do registro tem um valor *padrão* .</span><span class="sxs-lookup"><span data-stu-id="54697-187">Each registry key has a *default* value.</span></span> <span data-ttu-id="54697-188">Você pode alterar o valor *padrão* de uma chave do registro com um `Set-Item` ou `Set-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="54697-188">You can change the *default* value for a registry key with either `Set-Item` or `Set-ItemProperty`.</span></span>

```powershell
Set-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name "(default)" -Value "one"
Set-Item -Path HKLM:\SOFTWARE\Contoso -Value "two"
```

<span data-ttu-id="54697-189">Para obter mais informações sobre os cmdlets usados nesta seção, consulte os artigos a seguir.</span><span class="sxs-lookup"><span data-stu-id="54697-189">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="54697-190">Set-Item</span><span class="sxs-lookup"><span data-stu-id="54697-190">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)
- [<span data-ttu-id="54697-191">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="54697-191">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="creating-registry-keys-and-values"></a><span data-ttu-id="54697-192">Criando chaves e valores do registro</span><span class="sxs-lookup"><span data-stu-id="54697-192">Creating registry keys and values</span></span>

<span data-ttu-id="54697-193">O `New-Item` cmdlet criará chaves do registro com um nome que você fornecer.</span><span class="sxs-lookup"><span data-stu-id="54697-193">The `New-Item` cmdlet will create registry keys with a name that you provide.</span></span>
<span data-ttu-id="54697-194">Você também pode usar a `mkdir` função, que chama o `New-Item` cmdlet internamente.</span><span class="sxs-lookup"><span data-stu-id="54697-194">You can also use the `mkdir` function, which calls the `New-Item` cmdlet internally.</span></span>

```
PS HKLM:\SOFTWARE\> mkdir ContosoCompany

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
ContosoCompany
```

<span data-ttu-id="54697-195">Você pode usar o `New-ItemProperty` cmdlet para criar valores em uma chave do registro que você especificar.</span><span class="sxs-lookup"><span data-stu-id="54697-195">You can use the `New-ItemProperty` cmdlet to create values in a registry key that you specify.</span></span> <span data-ttu-id="54697-196">O exemplo a seguir cria um novo valor DWORD na chave do registro ContosoCompany.</span><span class="sxs-lookup"><span data-stu-id="54697-196">The following example creates a new DWORD value on the ContosoCompany registry key.</span></span>

```powershell
$path = "HKLM:\SOFTWARE\ContosoCompany"
New-ItemProperty -Path  -Name Test -Type DWORD -Value 1
```

> [!NOTE]
> <span data-ttu-id="54697-197">Examine a seção de parâmetros dinâmicos neste artigo para outros valores de tipo permitidos.</span><span class="sxs-lookup"><span data-stu-id="54697-197">Review the dynamic parameters section in this article for other allowed type values.</span></span>

<span data-ttu-id="54697-198">Para obter o uso detalhado do cmdlet, consulte [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty).</span><span class="sxs-lookup"><span data-stu-id="54697-198">For detailed cmdlet usage, see [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty).</span></span>

## <a name="copying-registry-keys-and-values"></a><span data-ttu-id="54697-199">Copiando chaves e valores do registro</span><span class="sxs-lookup"><span data-stu-id="54697-199">Copying registry keys and values</span></span>

<span data-ttu-id="54697-200">No provedor de **registro** , use o `Copy-Item` cmdlet para copiar valores e chaves do registro.</span><span class="sxs-lookup"><span data-stu-id="54697-200">In the **Registry** provider, use the `Copy-Item` cmdlet copies registry keys and values.</span></span> <span data-ttu-id="54697-201">Use o `Copy-ItemProperty` cmdlet para copiar somente valores de registro.</span><span class="sxs-lookup"><span data-stu-id="54697-201">Use the `Copy-ItemProperty` cmdlet to copy registry values only.</span></span>
<span data-ttu-id="54697-202">O comando a seguir copia a chave do registro "contoso" e suas propriedades para o local especificado "HKLM: \ Software\Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="54697-202">The following command copies the "Contoso" registry key, and its properties to the specified location "HKLM:\Software\Fabrikam".</span></span>

<span data-ttu-id="54697-203">`Copy-Item` cria a chave de destino se ela não existir.</span><span class="sxs-lookup"><span data-stu-id="54697-203">`Copy-Item` creates the destination key if it does not exist.</span></span> <span data-ttu-id="54697-204">Se a chave de destino existir, o `Copy-Item` criará uma duplicata da chave de origem como um item filho (subchave) da chave de destino.</span><span class="sxs-lookup"><span data-stu-id="54697-204">If the destination key exists, `Copy-Item` creates a duplicate of the source key as a child item (subkey) of the destination key.</span></span>

```powershell
Copy-Item -Path  HKLM:\Software\Contoso -Destination HKLM:\Software\Fabrikam
```

<span data-ttu-id="54697-205">O comando a seguir usa o `Copy-ItemProperty` cmdlet para copiar o valor "Server" da chave "contoso" para a chave "fabrikam".</span><span class="sxs-lookup"><span data-stu-id="54697-205">The following command uses the `Copy-ItemProperty` cmdlet to copy the "Server" value from the "Contoso" key to the "Fabrikam" key.</span></span>

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Copy-ItemProperty -Path $source -Destination $dest -Name Server
```

<span data-ttu-id="54697-206">Para obter mais informações sobre os cmdlets usados nesta seção, consulte os artigos a seguir.</span><span class="sxs-lookup"><span data-stu-id="54697-206">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="54697-207">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="54697-207">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)
- [<span data-ttu-id="54697-208">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="54697-208">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

## <a name="moving-registry-keys-and-values"></a><span data-ttu-id="54697-209">Movendo chaves e valores do registro</span><span class="sxs-lookup"><span data-stu-id="54697-209">Moving registry keys and values</span></span>

<span data-ttu-id="54697-210">Os `Move-Item` `Move-ItemProperty` cmdlets e se comportam como suas contrapartes de "cópia".</span><span class="sxs-lookup"><span data-stu-id="54697-210">The `Move-Item` and `Move-ItemProperty` cmdlets behave like their "Copy" counterparts.</span></span> <span data-ttu-id="54697-211">Se o destino existir, `Move-Item` o moverá a chave de origem para baixo da chave de destino.</span><span class="sxs-lookup"><span data-stu-id="54697-211">If the destination exists, `Move-Item` moves the source key underneath the destination key.</span></span> <span data-ttu-id="54697-212">Se a chave de destino não existir, a chave de origem será movida para o caminho de destino.</span><span class="sxs-lookup"><span data-stu-id="54697-212">If the destination key does not exist, the source key is moved to the destination path.</span></span>

<span data-ttu-id="54697-213">O comando a seguir move a chave "contoso" para o caminho "HKLM: \ SOFTWARE\Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="54697-213">The following command moves the "Contoso" key to the path "HKLM:\SOFTWARE\Fabrikam".</span></span>

```powershell
Move-Item -Path HKLM:\SOFTWARE\Contoso -Destination HKLM:\SOFTWARE\Fabrikam
```

<span data-ttu-id="54697-214">Esse comando move todas as propriedades de "HKLM: \ SOFTWARE\ContosoCompany" para "HKLM: \ SOFTWARE\Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="54697-214">This command moves all of the properties from "HKLM:\SOFTWARE\ContosoCompany" to "HKLM:\SOFTWARE\Fabrikam".</span></span>

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Move-ItemProperty -Path $source -Destination $dest -Name *
```

<span data-ttu-id="54697-215">Para obter mais informações sobre os cmdlets usados nesta seção, consulte os artigos a seguir.</span><span class="sxs-lookup"><span data-stu-id="54697-215">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="54697-216">Move-Item</span><span class="sxs-lookup"><span data-stu-id="54697-216">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="54697-217">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="54697-217">Move-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Move-ItemProperty)

## <a name="renaming-registry-keys-and-values"></a><span data-ttu-id="54697-218">Renomeando chaves e valores do registro</span><span class="sxs-lookup"><span data-stu-id="54697-218">Renaming registry keys and values</span></span>

<span data-ttu-id="54697-219">Você pode renomear chaves e valores do registro da mesma forma que faria com arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="54697-219">You can rename registry keys and values just like you would files and folders.</span></span>
<span data-ttu-id="54697-220">`Rename-Item` renomeia as chaves do registro, enquanto `Rename-ItemProperty` renomeia os valores do registro.</span><span class="sxs-lookup"><span data-stu-id="54697-220">`Rename-Item` renames registry keys, while `Rename-ItemProperty` renames registry values.</span></span>

```powershell
$path = "HKLM:\SOFTWARE\Contoso"
Rename-ItemProperty -Path $path -Name ContosoTest -NewName FabrikamTest
Rename-Item -Path $path -NewName Fabrikam
```

## <a name="changing-security-descriptors"></a><span data-ttu-id="54697-221">Alterando descritores de segurança</span><span class="sxs-lookup"><span data-stu-id="54697-221">Changing security descriptors</span></span>

<span data-ttu-id="54697-222">Você pode restringir o acesso a chaves do registro usando os `Get-Acl` `Set-Acl` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="54697-222">You can restrict access to registry keys using the `Get-Acl` and `Set-Acl` cmdlets.</span></span> <span data-ttu-id="54697-223">O exemplo a seguir adiciona um novo usuário com controle total à chave do registro "HKLM: \ SOFTWARE\Contoso".</span><span class="sxs-lookup"><span data-stu-id="54697-223">The following example adds a new user with full control to the "HKLM:\SOFTWARE\Contoso" registry key.</span></span>

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Contoso
$rule = New-Object System.Security.AccessControl.RegistryAccessRule `
("CONTOSO\jsmith", "FullControl", "Allow")
$acl.SetAccessRule($rule)
$acl | Set-Acl -Path HKLM:\SOFTWARE\Contoso
```

<span data-ttu-id="54697-224">Para obter mais exemplos e detalhes de uso do cmdlet, consulte os artigos a seguir.</span><span class="sxs-lookup"><span data-stu-id="54697-224">For more examples and cmdlet usage details see the following articles.</span></span>

- [<span data-ttu-id="54697-225">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="54697-225">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="54697-226">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="54697-226">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="removing-and-clearing-registry-keys-and-values"></a><span data-ttu-id="54697-227">Removendo e limpando chaves e valores do registro</span><span class="sxs-lookup"><span data-stu-id="54697-227">Removing and clearing registry keys and values</span></span>

<span data-ttu-id="54697-228">Você pode remover itens contidos usando **Remove-Item** , mas será solicitado que você confirme a remoção se o item contiver qualquer outra coisa.</span><span class="sxs-lookup"><span data-stu-id="54697-228">You can remove contained items by using **Remove-Item** , but you will be prompted to confirm the removal if the item contains anything else.</span></span> <span data-ttu-id="54697-229">O exemplo a seguir tenta excluir uma chave "HKLM: \ SOFTWARE\Contoso".</span><span class="sxs-lookup"><span data-stu-id="54697-229">The following example attempts to delete a key "HKLM:\SOFTWARE\Contoso".</span></span>

```
PS C:\> dir HKLM:\SOFTWARE\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Contoso

Name                           Property
----                           --------
ChildKey

PS C:\> Remove-Item -Path HKLM:\SOFTWARE\Contoso

Confirm
The item at HKLM:\SOFTWARE\Contoso has children and the -Recurse
parameter was not specified. If you continue, all children will be removed
with the item. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):
```

<span data-ttu-id="54697-230">Para excluir os itens contidos sem avisar, especifique o `-Recurse` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="54697-230">To delete contained items without prompting, specify the `-Recurse` parameter.</span></span>

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso -Recurse
```

<span data-ttu-id="54697-231">Se você quisesse remover todos os itens dentro de "HKLM: \ SOFTWARE\Contoso", mas não "HKLM: \ SOFTWARE\Contoso", use uma barra invertida à direita `\` seguida por um caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="54697-231">If you wanted to remove all items within "HKLM:\SOFTWARE\Contoso" but not "HKLM:\SOFTWARE\Contoso" itself, use a trailing backslash `\` followed by a wildcard.</span></span>

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso\* -Recurse
```

<span data-ttu-id="54697-232">Este comando exclui o valor do registro "ContosoTest" da chave do registro "HKLM: \ SOFTWARE\Contoso".</span><span class="sxs-lookup"><span data-stu-id="54697-232">This command deletes the "ContosoTest" registry value from the "HKLM:\SOFTWARE\Contoso" registry key.</span></span>

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name ContosoTest
```

<span data-ttu-id="54697-233">`Clear-Item` limpa todos os valores de registro de uma chave.</span><span class="sxs-lookup"><span data-stu-id="54697-233">`Clear-Item` clears all registry values for a key.</span></span> <span data-ttu-id="54697-234">O exemplo a seguir limpa todos os valores da chave do registro "HKLM: \ SOFTWARE\Contoso".</span><span class="sxs-lookup"><span data-stu-id="54697-234">The following example clears all values from the "HKLM:\SOFTWARE\Contoso" registry key.</span></span> <span data-ttu-id="54697-235">Para limpar apenas uma propriedade específica, use `Clear-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="54697-235">To clear only a specific property, use `Clear-ItemProperty`.</span></span>

```
PS HKLM:\SOFTWARE\> Get-Item .\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name           Property
----           --------
Contoso        Server     : {a, b, c}
               HereString : {This is text which contains
               newlines. It also contains "quoted" strings}
               (default)  : 1

PS HKLM:\SOFTWARE\> Clear-Item .\Contoso\
PS HKLM:\SOFTWARE\> Get-Item .\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
Contoso
```

<span data-ttu-id="54697-236">Para obter mais exemplos e detalhes de uso do cmdlet, consulte os artigos a seguir.</span><span class="sxs-lookup"><span data-stu-id="54697-236">For more examples and cmdlet usage details see the following articles.</span></span>

- [<span data-ttu-id="54697-237">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="54697-237">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="54697-238">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="54697-238">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="54697-239">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="54697-239">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="54697-240">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="54697-240">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)

## <a name="dynamic-parameters"></a><span data-ttu-id="54697-241">Parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="54697-241">Dynamic parameters</span></span>

<span data-ttu-id="54697-242">Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor.</span><span class="sxs-lookup"><span data-stu-id="54697-242">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="type-microsoftwin32registryvaluekind"></a><span data-ttu-id="54697-243">Digite <Microsoft. Win32. RegistryValueKind></span><span class="sxs-lookup"><span data-stu-id="54697-243">Type <Microsoft.Win32.RegistryValueKind></span></span>

<span data-ttu-id="54697-244">Estabelece ou altera o tipo de dados de um valor do Registro.</span><span class="sxs-lookup"><span data-stu-id="54697-244">Establishes or changes the data type of a registry value.</span></span> <span data-ttu-id="54697-245">O padrão é `String` (REG_SZ).</span><span class="sxs-lookup"><span data-stu-id="54697-245">The default is `String` (REG_SZ).</span></span>

<span data-ttu-id="54697-246">Esse parâmetro funciona corretamente no cmdlet [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty).</span><span class="sxs-lookup"><span data-stu-id="54697-246">This parameter works as designed on the [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty) cmdlet.</span></span> <span data-ttu-id="54697-247">Ele também está disponível no cmdlet [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item) em unidades de Registro, mas não tem nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="54697-247">It is also available on the [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item) cmdlet in the registry drives, but it has no effect.</span></span>

|<span data-ttu-id="54697-248">Valor</span><span class="sxs-lookup"><span data-stu-id="54697-248">Value</span></span> | <span data-ttu-id="54697-249">Descrição</span><span class="sxs-lookup"><span data-stu-id="54697-249">Description</span></span> |
| ---- | ----------- |
| `String` | <span data-ttu-id="54697-250">Especifica uma cadeia de caracteres terminada em nulo.</span><span class="sxs-lookup"><span data-stu-id="54697-250">Specifies a null-terminated string.</span></span> <span data-ttu-id="54697-251">Equivalente a REG_SZ.</span><span class="sxs-lookup"><span data-stu-id="54697-251">Equivalent to REG_SZ.</span></span> |
| `ExpandString` | <span data-ttu-id="54697-252">Especifica uma cadeia de caracteres terminada em nulo que contém não expandido</span><span class="sxs-lookup"><span data-stu-id="54697-252">Specifies a null-terminated string that contains unexpanded</span></span> |
|                | <span data-ttu-id="54697-253">referências a variáveis de ambiente que são expandidas quando</span><span class="sxs-lookup"><span data-stu-id="54697-253">references to environment variables that are expanded when</span></span> |
|                | <span data-ttu-id="54697-254">o valor é recuperado.</span><span class="sxs-lookup"><span data-stu-id="54697-254">the value is retrieved.</span></span> <span data-ttu-id="54697-255">Equivalente ao REG_EXPAND_SZ.</span><span class="sxs-lookup"><span data-stu-id="54697-255">Equivalent to REG_EXPAND_SZ.</span></span> |
| `Binary` | <span data-ttu-id="54697-256">Especifica os dados binários em qualquer formulário.</span><span class="sxs-lookup"><span data-stu-id="54697-256">Specifies binary data in any form.</span></span> <span data-ttu-id="54697-257">Equivalente ao REG_BINARY.</span><span class="sxs-lookup"><span data-stu-id="54697-257">Equivalent to REG_BINARY.</span></span> |
| `DWord` | <span data-ttu-id="54697-258">Especifica um número binário de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="54697-258">Specifies a 32-bit binary number.</span></span> <span data-ttu-id="54697-259">Equivalente ao REG_DWORD.</span><span class="sxs-lookup"><span data-stu-id="54697-259">Equivalent to REG_DWORD.</span></span> |
| `MultiString` | <span data-ttu-id="54697-260">Especifica uma matriz de cadeias de caracteres terminadas em nulo terminadas por</span><span class="sxs-lookup"><span data-stu-id="54697-260">Specifies an array of null-terminated strings terminated by</span></span> |
|               | <span data-ttu-id="54697-261">dois caracteres nulos.</span><span class="sxs-lookup"><span data-stu-id="54697-261">two null characters.</span></span> <span data-ttu-id="54697-262">Equivalente ao REG_MULTI_SZ.</span><span class="sxs-lookup"><span data-stu-id="54697-262">Equivalent to REG_MULTI_SZ.</span></span> |
| `QWord` | <span data-ttu-id="54697-263">Especifica um número binário de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="54697-263">Specifies a 64-bit binary number.</span></span> <span data-ttu-id="54697-264">Equivalente ao REG_QWORD.</span><span class="sxs-lookup"><span data-stu-id="54697-264">Equivalent to REG_QWORD.</span></span> |
| `Unknown` | <span data-ttu-id="54697-265">Indica um tipo de dados de registro sem suporte, como</span><span class="sxs-lookup"><span data-stu-id="54697-265">Indicates an unsupported registry data type, such as</span></span> |
|           | <span data-ttu-id="54697-266">REG_RESOURCE_LIST.</span><span class="sxs-lookup"><span data-stu-id="54697-266">REG_RESOURCE_LIST.</span></span> |

#### <a name="cmdlets-supported"></a><span data-ttu-id="54697-267">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="54697-267">Cmdlets supported</span></span>

- [<span data-ttu-id="54697-268">Set-Item</span><span class="sxs-lookup"><span data-stu-id="54697-268">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)
- [<span data-ttu-id="54697-269">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="54697-269">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="using-the-pipeline"></a><span data-ttu-id="54697-270">Usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="54697-270">Using the pipeline</span></span>

<span data-ttu-id="54697-271">Os cmdlets do provedor aceitam a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="54697-271">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="54697-272">Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor.</span><span class="sxs-lookup"><span data-stu-id="54697-272">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span> <span data-ttu-id="54697-273">Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="54697-273">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="54697-274">Obtendo ajuda</span><span class="sxs-lookup"><span data-stu-id="54697-274">Getting help</span></span>

<span data-ttu-id="54697-275">A partir do Windows PowerShell 3.0, você pode obter tópicos da Ajuda personalizados para cmdlets do provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="54697-275">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="54697-276">Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um `Get-Help` comando em uma unidade do sistema de arquivos ou use o parâmetro **Path** para especificar uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="54697-276">To get the help topics that are customized for the file system drive, run a `Get-Help` command in a file system drive or use the **Path** parameter to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path HKLM:
```

## <a name="see-also"></a><span data-ttu-id="54697-277">Confira também</span><span class="sxs-lookup"><span data-stu-id="54697-277">See also</span></span>

 [<span data-ttu-id="54697-278">about_Providers</span><span class="sxs-lookup"><span data-stu-id="54697-278">about_Providers</span></span>](../About/about_Providers.md)
