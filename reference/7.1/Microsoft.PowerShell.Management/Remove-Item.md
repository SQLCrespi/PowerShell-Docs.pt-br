---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Item
ms.openlocfilehash: c4a0243c528cbe1a28cad99cf6fa8d91018d9b3c
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692674"
---
# <span data-ttu-id="c55e3-102">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="c55e3-102">Remove-Item</span></span>

## <span data-ttu-id="c55e3-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c55e3-103">SYNOPSIS</span></span>
<span data-ttu-id="c55e3-104">Exclui os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="c55e3-104">Deletes the specified items.</span></span>

## <span data-ttu-id="c55e3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c55e3-105">SYNTAX</span></span>

### <span data-ttu-id="c55e3-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="c55e3-106">Path (Default)</span></span>

```
Remove-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="c55e3-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c55e3-107">LiteralPath</span></span>

```
Remove-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="c55e3-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c55e3-108">DESCRIPTION</span></span>

<span data-ttu-id="c55e3-109">O `Remove-Item` cmdlet exclui um ou mais itens.</span><span class="sxs-lookup"><span data-stu-id="c55e3-109">The `Remove-Item` cmdlet deletes one or more items.</span></span> <span data-ttu-id="c55e3-110">Como há suporte para vários provedores, ele pode excluir vários tipos diferentes de itens, incluindo arquivos, pastas, chaves do registro, variáveis, aliases e funções.</span><span class="sxs-lookup"><span data-stu-id="c55e3-110">Because it is supported by many providers, it can delete many different types of items, including files, folders, registry keys, variables, aliases, and functions.</span></span>

## <span data-ttu-id="c55e3-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c55e3-111">EXAMPLES</span></span>

### <span data-ttu-id="c55e3-112">Exemplo 1: excluir arquivos que têm qualquer extensão de nome de arquivo</span><span class="sxs-lookup"><span data-stu-id="c55e3-112">Example 1: Delete files that have any file name extension</span></span>

<span data-ttu-id="c55e3-113">Este exemplo exclui todos os arquivos que têm nomes que incluem um ponto ( `.` ) da `C:\Test` pasta.</span><span class="sxs-lookup"><span data-stu-id="c55e3-113">This example deletes all of the files that have names that include a dot (`.`) from the `C:\Test` folder.</span></span> <span data-ttu-id="c55e3-114">Como o comando especifica um ponto, o comando não exclui pastas ou arquivos que não têm nenhuma extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="c55e3-114">Because the command specifies a dot, the command does not delete folders or files that have no file name extension.</span></span>

```powershell
Remove-Item C:\Test\*.*
```

### <span data-ttu-id="c55e3-115">Exemplo 2: excluir alguns dos arquivos de documento em uma pasta</span><span class="sxs-lookup"><span data-stu-id="c55e3-115">Example 2: Delete some of the document files in a folder</span></span>

<span data-ttu-id="c55e3-116">Este exemplo exclui da pasta atual todos os arquivos que têm uma `.doc` extensão de nome de arquivo e um nome que não inclui `*1*` .</span><span class="sxs-lookup"><span data-stu-id="c55e3-116">This example deletes from the current folder all files that have a `.doc` file name extension and a name that does not include `*1*`.</span></span>

```powershell
Remove-Item * -Include *.doc -Exclude *1*
```

<span data-ttu-id="c55e3-117">Ele usa o caractere curinga ( `*` ) para especificar o conteúdo da pasta atual.</span><span class="sxs-lookup"><span data-stu-id="c55e3-117">It uses the wildcard character (`*`) to specify the contents of the current folder.</span></span> <span data-ttu-id="c55e3-118">Ele usa os parâmetros **include** e **Exclude** para especificar os arquivos a serem excluídos.</span><span class="sxs-lookup"><span data-stu-id="c55e3-118">It uses the **Include** and **Exclude** parameters to specify the files to delete.</span></span>

### <span data-ttu-id="c55e3-119">Exemplo 3: excluir arquivos ocultos e somente leitura</span><span class="sxs-lookup"><span data-stu-id="c55e3-119">Example 3: Delete hidden, read-only files</span></span>

<span data-ttu-id="c55e3-120">Esse comando exclui um arquivo que está *oculto* e *somente leitura*.</span><span class="sxs-lookup"><span data-stu-id="c55e3-120">This command deletes a file that is both *hidden* and *read-only*.</span></span>

```powershell
Remove-Item -Path C:\Test\hidden-RO-file.txt -Force
```

<span data-ttu-id="c55e3-121">Ele usa o parâmetro **path** para especificar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="c55e3-121">It uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="c55e3-122">Ele usa o parâmetro **Force** para excluí-lo.</span><span class="sxs-lookup"><span data-stu-id="c55e3-122">It uses the **Force** parameter to delete it.</span></span> <span data-ttu-id="c55e3-123">Sem **forçar**, você não pode excluir arquivos _somente leitura_ ou _ocultos_ .</span><span class="sxs-lookup"><span data-stu-id="c55e3-123">Without **Force**, you cannot delete _read-only_ or _hidden_ files.</span></span>

### <span data-ttu-id="c55e3-124">Exemplo 4: excluir arquivos em subpastas de forma recursiva</span><span class="sxs-lookup"><span data-stu-id="c55e3-124">Example 4: Delete files in subfolders recursively</span></span>

<span data-ttu-id="c55e3-125">Esse comando exclui todos os arquivos CSV na pasta atual e todas as subpastas de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="c55e3-125">This command deletes all of the CSV files in the current folder and all subfolders recursively.</span></span>

<span data-ttu-id="c55e3-126">Como o parâmetro **recurse** no `Remove-Item` tem um problema conhecido, o comando neste exemplo usa `Get-ChildItem` para obter os arquivos desejados e, em seguida, usa o operador de pipeline para passá-los para `Remove-Item` .</span><span class="sxs-lookup"><span data-stu-id="c55e3-126">Because the **Recurse** parameter in `Remove-Item` has a known issue, the command in this example uses `Get-ChildItem` to get the desired files, and then uses the pipeline operator to pass them to `Remove-Item`.</span></span>

```powershell
Get-ChildItem * -Include *.csv -Recurse | Remove-Item
```

<span data-ttu-id="c55e3-127">No `Get-ChildItem` comando, **Path** tem um valor de ( `*` ), que representa o conteúdo da pasta atual.</span><span class="sxs-lookup"><span data-stu-id="c55e3-127">In the `Get-ChildItem` command, **Path** has a value of (`*`), which represents the contents of the current folder.</span></span> <span data-ttu-id="c55e3-128">Ele usa **include** para especificar o tipo de arquivo CSV e usa **recurse** para tornar a recuperação recursiva.</span><span class="sxs-lookup"><span data-stu-id="c55e3-128">It uses **Include** to specify the CSV file type, and it uses **Recurse** to make the retrieval recursive.</span></span> <span data-ttu-id="c55e3-129">Se você tentar especificar o tipo de arquivo o caminho, como `-Path *.csv` , o cmdlet interpretará o assunto da pesquisa para ser um arquivo que não tem itens filhos e **recurse** falhará.</span><span class="sxs-lookup"><span data-stu-id="c55e3-129">If you try to specify the file type the path, such as `-Path *.csv`, the cmdlet interprets the subject of the search to be a file that has no child items, and **Recurse** fails.</span></span>

### <span data-ttu-id="c55e3-130">Exemplo 5: excluir subchaves recursivamente</span><span class="sxs-lookup"><span data-stu-id="c55e3-130">Example 5: Delete subkeys recursively</span></span>

<span data-ttu-id="c55e3-131">Esse comando exclui a chave do registro "OldApp" e todas as suas subchaves e valores.</span><span class="sxs-lookup"><span data-stu-id="c55e3-131">This command deletes the "OldApp" registry key and all its subkeys and values.</span></span> <span data-ttu-id="c55e3-132">Ele usa `Remove-Item` para remover a chave.</span><span class="sxs-lookup"><span data-stu-id="c55e3-132">It uses `Remove-Item` to remove the key.</span></span> <span data-ttu-id="c55e3-133">O caminho é especificado, mas o nome de parâmetro opcional (**caminho**) é omitido.</span><span class="sxs-lookup"><span data-stu-id="c55e3-133">The path is specified, but the optional parameter name (**Path**) is omitted.</span></span>

<span data-ttu-id="c55e3-134">O parâmetro **recurse** exclui todo o conteúdo da chave "OldApp" recursivamente.</span><span class="sxs-lookup"><span data-stu-id="c55e3-134">The **Recurse** parameter deletes all of the contents of the "OldApp" key recursively.</span></span> <span data-ttu-id="c55e3-135">Se a chave contiver subchaves e você omitir o parâmetro **recurse** , será solicitado que você confirme se deseja excluir o conteúdo da chave.</span><span class="sxs-lookup"><span data-stu-id="c55e3-135">If the key contains subkeys and you omit the **Recurse** parameter, you are prompted to confirm that you want to delete the contents of the key.</span></span>

```powershell
Remove-Item HKLM:\Software\MyCompany\OldApp -Recurse
```

### <span data-ttu-id="c55e3-136">Exemplo 6: excluindo arquivos com caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="c55e3-136">Example 6: Deleting files with special characters</span></span>

<span data-ttu-id="c55e3-137">O exemplo a seguir mostra como excluir arquivos que contêm caracteres especiais, como colchetes ou parênteses.</span><span class="sxs-lookup"><span data-stu-id="c55e3-137">The following example shows how to delete files that contain special characters like brackets or parentheses.</span></span>

```powershell
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*'
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*' | ForEach-Object { Remove-Item -LiteralPath $_.Name }
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
```

### <span data-ttu-id="c55e3-138">Exemplo 7: remover um fluxo de dados alternativo</span><span class="sxs-lookup"><span data-stu-id="c55e3-138">Example 7: Remove an alternate data stream</span></span>

<span data-ttu-id="c55e3-139">Este exemplo mostra como usar o parâmetro **Stream** dinâmico do `Remove-Item` cmdlet para excluir um fluxo de dados alternativo.</span><span class="sxs-lookup"><span data-stu-id="c55e3-139">This example shows how to use the **Stream** dynamic parameter of the `Remove-Item` cmdlet to delete an alternate data stream.</span></span> <span data-ttu-id="c55e3-140">O parâmetro Stream é introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c55e3-140">The stream parameter is introduced in Windows PowerShell 3.0.</span></span>

```powershell
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
   FileName: \\C:\Test\Copy-Script.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

```

```powershell
Remove-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
Get-Item : Could not open alternate data stream 'Zone.Identifier' of file 'C:\Test\Copy-Script.ps1'.
At line:1 char:1
+ Get-Item 'C:\Test\Copy-Script.ps1' -Stream Zone.Identifier
+ [!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()]~~
    + CategoryInfo          : ObjectNotFound: (C:\Test\Copy-Script.ps1:String) [Get-Item], FileNotFoundE
   xception
    + FullyQualifiedErrorId : AlternateDataStreamNotFound,Microsoft.PowerShell.Commands.GetItemCommand

```

<span data-ttu-id="c55e3-141">O  parâmetro Stream `Get-Item` Obtém o `Zone.Identifier` fluxo do `Copy-Script.ps1` arquivo.</span><span class="sxs-lookup"><span data-stu-id="c55e3-141">The **Stream** parameter `Get-Item` gets the `Zone.Identifier` stream of the `Copy-Script.ps1` file.</span></span> <span data-ttu-id="c55e3-142">`Remove-Item` usa o parâmetro **Stream** para remover o `Zone.Identifier` fluxo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="c55e3-142">`Remove-Item` uses the **Stream** parameter to remove the `Zone.Identifier` stream of the file.</span></span> <span data-ttu-id="c55e3-143">Por fim, o `Get-Item` cmdlet mostra que o `Zone.Identifier` fluxo foi excluído.</span><span class="sxs-lookup"><span data-stu-id="c55e3-143">Finally, the `Get-Item` cmdlet shows that the `Zone.Identifier` stream was deleted.</span></span>

## <span data-ttu-id="c55e3-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c55e3-144">PARAMETERS</span></span>

### <span data-ttu-id="c55e3-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="c55e3-145">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="c55e3-146">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c55e3-146">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="c55e3-147">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="c55e3-147">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c55e3-148">-Excluir</span><span class="sxs-lookup"><span data-stu-id="c55e3-148">-Exclude</span></span>

<span data-ttu-id="c55e3-149">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="c55e3-149">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="c55e3-150">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="c55e3-150">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c55e3-151">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="c55e3-151">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="c55e3-152">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c55e3-152">Wildcard characters are permitted.</span></span> <span data-ttu-id="c55e3-153">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="c55e3-153">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c55e3-154">-Filter</span><span class="sxs-lookup"><span data-stu-id="c55e3-154">-Filter</span></span>

<span data-ttu-id="c55e3-155">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="c55e3-155">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="c55e3-156">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="c55e3-156">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="c55e3-157">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="c55e3-157">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span> <span data-ttu-id="c55e3-158">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="c55e3-158">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c55e3-159">-Force</span><span class="sxs-lookup"><span data-stu-id="c55e3-159">-Force</span></span>

<span data-ttu-id="c55e3-160">Força o cmdlet a remover itens que não podem ser alterados de outra forma, como arquivos ocultos ou somente leitura ou aliases ou variáveis somente leitura.</span><span class="sxs-lookup"><span data-stu-id="c55e3-160">Forces the cmdlet to remove items that cannot otherwise be changed, such as hidden or read-only files or read-only aliases or variables.</span></span> <span data-ttu-id="c55e3-161">O cmdlet não pode remover variáveis nem aliases constantes.</span><span class="sxs-lookup"><span data-stu-id="c55e3-161">The cmdlet cannot remove constant aliases or variables.</span></span>
<span data-ttu-id="c55e3-162">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="c55e3-162">Implementation varies from provider to provider.</span></span> <span data-ttu-id="c55e3-163">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="c55e3-163">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="c55e3-164">Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="c55e3-164">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c55e3-165">-Incluir</span><span class="sxs-lookup"><span data-stu-id="c55e3-165">-Include</span></span>

<span data-ttu-id="c55e3-166">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="c55e3-166">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="c55e3-167">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="c55e3-167">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c55e3-168">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="c55e3-168">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="c55e3-169">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c55e3-169">Wildcard characters are permitted.</span></span> <span data-ttu-id="c55e3-170">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="c55e3-170">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c55e3-171">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c55e3-171">-LiteralPath</span></span>

<span data-ttu-id="c55e3-172">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="c55e3-172">Specifies a path to one or more locations.</span></span> <span data-ttu-id="c55e3-173">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="c55e3-173">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="c55e3-174">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="c55e3-174">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="c55e3-175">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="c55e3-175">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="c55e3-176">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="c55e3-176">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="c55e3-177">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="c55e3-177">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c55e3-178">-Path</span><span class="sxs-lookup"><span data-stu-id="c55e3-178">-Path</span></span>

<span data-ttu-id="c55e3-179">Especifica um caminho dos itens que estão sendo removidos.</span><span class="sxs-lookup"><span data-stu-id="c55e3-179">Specifies a path of the items being removed.</span></span>
<span data-ttu-id="c55e3-180">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c55e3-180">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="c55e3-181">-Recurse</span><span class="sxs-lookup"><span data-stu-id="c55e3-181">-Recurse</span></span>

<span data-ttu-id="c55e3-182">Indica que esse cmdlet exclui os itens nos locais especificados e em todos os itens filho dos locais.</span><span class="sxs-lookup"><span data-stu-id="c55e3-182">Indicates that this cmdlet deletes the items in the specified locations and in all child items of the locations.</span></span>

<span data-ttu-id="c55e3-183">Quando usado com o parâmetro **include** , o parâmetro **recurse** pode não excluir todas as subpastas ou todos os itens filho.</span><span class="sxs-lookup"><span data-stu-id="c55e3-183">When it is used with the **Include** parameter, the **Recurse** parameter might not delete all subfolders or all child items.</span></span> <span data-ttu-id="c55e3-184">Este é um problema conhecido.</span><span class="sxs-lookup"><span data-stu-id="c55e3-184">This is a known issue.</span></span> <span data-ttu-id="c55e3-185">Como alternativa, tente canalizar os resultados do `Get-ChildItem -Recurse` comando para `Remove-Item` , conforme descrito no "exemplo 4" neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c55e3-185">As a workaround, try piping results of the `Get-ChildItem -Recurse` command to `Remove-Item`, as described in "Example 4" in this topic.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c55e3-186">-Fluxo</span><span class="sxs-lookup"><span data-stu-id="c55e3-186">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="c55e3-187">Esse parâmetro só está disponível no Windows.</span><span class="sxs-lookup"><span data-stu-id="c55e3-187">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="c55e3-188">O parâmetro de **fluxo** é um parâmetro dinâmico que o provedor FileSystem adiciona `Remove-Item` .</span><span class="sxs-lookup"><span data-stu-id="c55e3-188">The **Stream** parameter is a dynamic parameter that the FileSystem provider adds to `Remove-Item`.</span></span>
<span data-ttu-id="c55e3-189">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c55e3-189">This parameter works only in file system drives.</span></span>

<span data-ttu-id="c55e3-190">Você pode usar `Remove-Item` para excluir um fluxo de dados alternativo, como `Zone.Identifier` .</span><span class="sxs-lookup"><span data-stu-id="c55e3-190">You can use `Remove-Item` to delete an alternative data stream, such as `Zone.Identifier`.</span></span>
<span data-ttu-id="c55e3-191">No entanto, não é a maneira recomendada para eliminar verificações de segurança que bloqueiam arquivos baixados da Internet.</span><span class="sxs-lookup"><span data-stu-id="c55e3-191">However, it is not the recommended way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="c55e3-192">Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c55e3-192">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="c55e3-193">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c55e3-193">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c55e3-194">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c55e3-194">-Confirm</span></span>

<span data-ttu-id="c55e3-195">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c55e3-195">Prompts you for confirmation before running the cmdlet.</span></span> <span data-ttu-id="c55e3-196">Para obter mais informações, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="c55e3-196">For more information, see the following articles:</span></span>

- [<span data-ttu-id="c55e3-197">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="c55e3-197">about_Preference_Variables</span></span>](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)
- [<span data-ttu-id="c55e3-198">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="c55e3-198">about_Functions_CmdletBindingAttribute</span></span>](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c55e3-199">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c55e3-199">-WhatIf</span></span>

<span data-ttu-id="c55e3-200">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="c55e3-200">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="c55e3-201">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="c55e3-201">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c55e3-202">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c55e3-202">CommonParameters</span></span>

<span data-ttu-id="c55e3-203">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c55e3-203">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c55e3-204">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c55e3-204">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>


## <span data-ttu-id="c55e3-205">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c55e3-205">INPUTS</span></span>

### <span data-ttu-id="c55e3-206">System.String</span><span class="sxs-lookup"><span data-stu-id="c55e3-206">System.String</span></span>

<span data-ttu-id="c55e3-207">É possível canalizar uma cadeia de caracteres que contém um caminho, mas não um caminho literal, para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c55e3-207">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="c55e3-208">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c55e3-208">OUTPUTS</span></span>

### <span data-ttu-id="c55e3-209">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c55e3-209">None</span></span>

<span data-ttu-id="c55e3-210">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="c55e3-210">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="c55e3-211">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c55e3-211">NOTES</span></span>

<span data-ttu-id="c55e3-212">O `Remove-Item` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="c55e3-212">The `Remove-Item` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="c55e3-213">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="c55e3-213">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="c55e3-214">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="c55e3-214">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="c55e3-215">Quando você tenta excluir uma pasta que contém itens sem usar o parâmetro **recurse** , o cmdlet solicita confirmação.</span><span class="sxs-lookup"><span data-stu-id="c55e3-215">When you try to delete a folder that contains items without using the **Recurse** parameter, the cmdlet prompts for confirmation.</span></span> <span data-ttu-id="c55e3-216">Usar não `-Confirm:$false` suprime o prompt.</span><span class="sxs-lookup"><span data-stu-id="c55e3-216">Using `-Confirm:$false` does not suppress the prompt.</span></span> <span data-ttu-id="c55e3-217">Isso ocorre por design.</span><span class="sxs-lookup"><span data-stu-id="c55e3-217">This is by design.</span></span>

## <span data-ttu-id="c55e3-218">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c55e3-218">RELATED LINKS</span></span>

[<span data-ttu-id="c55e3-219">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="c55e3-219">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="c55e3-220">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="c55e3-220">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="c55e3-221">Get-Item</span><span class="sxs-lookup"><span data-stu-id="c55e3-221">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="c55e3-222">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="c55e3-222">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="c55e3-223">Move-Item</span><span class="sxs-lookup"><span data-stu-id="c55e3-223">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="c55e3-224">New-Item</span><span class="sxs-lookup"><span data-stu-id="c55e3-224">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="c55e3-225">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="c55e3-225">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="c55e3-226">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="c55e3-226">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="c55e3-227">Set-Item</span><span class="sxs-lookup"><span data-stu-id="c55e3-227">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="c55e3-228">about_Providers</span><span class="sxs-lookup"><span data-stu-id="c55e3-228">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="c55e3-229">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="c55e3-229">about_Preference_Variables</span></span>](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)

[<span data-ttu-id="c55e3-230">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="c55e3-230">about_Functions_CmdletBindingAttribute</span></span>](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)
