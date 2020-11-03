---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-item?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Item
ms.openlocfilehash: 8483fd374ee973256633e3711322561fc14b8ae2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194400"
---
# <span data-ttu-id="63602-103">Get-Item</span><span class="sxs-lookup"><span data-stu-id="63602-103">Get-Item</span></span>

## <span data-ttu-id="63602-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="63602-104">SYNOPSIS</span></span>
<span data-ttu-id="63602-105">Obtém o item no local especificado.</span><span class="sxs-lookup"><span data-stu-id="63602-105">Gets the item at the specified location.</span></span>

## <span data-ttu-id="63602-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="63602-106">SYNTAX</span></span>

### <span data-ttu-id="63602-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="63602-107">Path (Default)</span></span>

```
Get-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="63602-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="63602-108">LiteralPath</span></span>

```
Get-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Force] [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="63602-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="63602-109">DESCRIPTION</span></span>

<span data-ttu-id="63602-110">O `Get-Item` cmdlet obtém o item no local especificado.</span><span class="sxs-lookup"><span data-stu-id="63602-110">The `Get-Item` cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="63602-111">Ele não obtém o conteúdo do item no local, a menos que você use um caractere curinga ( `*` ) para solicitar todo o conteúdo do item.</span><span class="sxs-lookup"><span data-stu-id="63602-111">It doesn't get the contents of the item at the location unless you use a wildcard character (`*`) to request all the contents of the item.</span></span>

<span data-ttu-id="63602-112">Esse cmdlet é usado pelos provedores do PowerShell para navegar por diferentes tipos de armazenamentos de dados.</span><span class="sxs-lookup"><span data-stu-id="63602-112">This cmdlet is used by PowerShell providers to navigate through different types of data stores.</span></span>

## <span data-ttu-id="63602-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="63602-113">EXAMPLES</span></span>

### <span data-ttu-id="63602-114">Exemplo 1: obter o diretório atual</span><span class="sxs-lookup"><span data-stu-id="63602-114">Example 1: Get the current directory</span></span>

<span data-ttu-id="63602-115">Este exemplo obtém o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="63602-115">This example gets the current directory.</span></span> <span data-ttu-id="63602-116">O ponto ('. ') representa o item no local atual (não seu conteúdo).</span><span class="sxs-lookup"><span data-stu-id="63602-116">The dot ('.') represents the item at the current location (not its contents).</span></span>

```powershell
Get-Item .
```

```output
Directory: C:\

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006  10:01 AM            ps-test
```

### <span data-ttu-id="63602-117">Exemplo 2: obter todos os itens no diretório atual</span><span class="sxs-lookup"><span data-stu-id="63602-117">Example 2: Get all the items in the current directory</span></span>

<span data-ttu-id="63602-118">Este exemplo obtém todos os itens no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="63602-118">This example gets all the items in the current directory.</span></span> <span data-ttu-id="63602-119">O caractere curinga ( `*` ) representa todo o conteúdo do item atual.</span><span class="sxs-lookup"><span data-stu-id="63602-119">The wildcard character (`*`) represents all the contents of the current item.</span></span>

```powershell
Get-Item *
```

```output
Directory: C:\ps-test

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006   9:29 AM            Logs
d----         7/26/2006   9:26 AM            Recs
-a---         7/26/2006   9:28 AM         80 date.csv
-a---         7/26/2006  10:01 AM         30 filenoext
-a---         7/26/2006   9:30 AM      11472 process.doc
-a---         7/14/2006  10:47 AM         30 test.txt
```

### <span data-ttu-id="63602-120">Exemplo 3: obter o diretório atual de uma unidade</span><span class="sxs-lookup"><span data-stu-id="63602-120">Example 3: Get the current directory of a drive</span></span>

<span data-ttu-id="63602-121">Este exemplo obtém o diretório atual da `C:` unidade.</span><span class="sxs-lookup"><span data-stu-id="63602-121">This example gets the current directory of the `C:` drive.</span></span> <span data-ttu-id="63602-122">O objeto recuperado representa somente o diretório, e não o seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="63602-122">The object that is retrieved represents only the directory, not its contents.</span></span>

```powershell
Get-Item C:\
```

### <span data-ttu-id="63602-123">Exemplo 4: obter itens na unidade especificada</span><span class="sxs-lookup"><span data-stu-id="63602-123">Example 4: Get items in the specified drive</span></span>

<span data-ttu-id="63602-124">Este exemplo obtém os itens na `C:` unidade.</span><span class="sxs-lookup"><span data-stu-id="63602-124">This example gets the items in the `C:` drive.</span></span> <span data-ttu-id="63602-125">O caractere curinga ( `*` ) representa todos os itens no contêiner, não apenas o contêiner.</span><span class="sxs-lookup"><span data-stu-id="63602-125">The wildcard character (`*`) represents all the items in the container, not just the container.</span></span>

```powershell
Get-Item C:\*
```

<span data-ttu-id="63602-126">No PowerShell, use um único asterisco ( `*` ) para obter o conteúdo, em vez do tradicional `*.*` .</span><span class="sxs-lookup"><span data-stu-id="63602-126">In PowerShell, use a single asterisk (`*`) to get contents, instead of the traditional `*.*`.</span></span> <span data-ttu-id="63602-127">O formato é interpretado literalmente, portanto, não `*.*` recuperaria diretórios ou nomes de FileName sem um ponto.</span><span class="sxs-lookup"><span data-stu-id="63602-127">The format is interpreted literally, so `*.*` wouldn't retrieve directories or filenames without a dot.</span></span>

### <span data-ttu-id="63602-128">Exemplo 5: obter uma propriedade no diretório especificado</span><span class="sxs-lookup"><span data-stu-id="63602-128">Example 5: Get a property in the specified directory</span></span>

<span data-ttu-id="63602-129">Este exemplo obtém a propriedade **LastAccessTime** do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="63602-129">This example gets the **LastAccessTime** property of the `C:\Windows` directory.</span></span> <span data-ttu-id="63602-130">**LastAccessTime** é apenas uma propriedade dos diretórios do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="63602-130">**LastAccessTime** is just one property of file system directories.</span></span> <span data-ttu-id="63602-131">Para ver todas as propriedades de um diretório, digite `(Get-Item <directory-name>) | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="63602-131">To see all the properties of a directory, type `(Get-Item <directory-name>) | Get-Member`.</span></span>

```powershell
(Get-Item C:\Windows).LastAccessTime
```

### <span data-ttu-id="63602-132">Exemplo 6: mostrar o conteúdo de uma chave do registro</span><span class="sxs-lookup"><span data-stu-id="63602-132">Example 6: Show the contents of a registry key</span></span>

<span data-ttu-id="63602-133">Este exemplo mostra o conteúdo da chave do registro **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="63602-133">This example shows the contents of the **Microsoft.PowerShell** registry key.</span></span> <span data-ttu-id="63602-134">Você pode usar esse cmdlet com o provedor de registro do PowerShell para obter chaves e subchaves do registro, mas você deve usar o `Get-ItemProperty` cmdlet para obter os valores e os dados do registro.</span><span class="sxs-lookup"><span data-stu-id="63602-134">You can use this cmdlet with the PowerShell Registry provider to get registry keys and subkeys, but you must use the `Get-ItemProperty` cmdlet to get the registry values and data.</span></span>

```powershell
Get-Item HKLM:\Software\Microsoft\Powershell\1\Shellids\Microsoft.Powershell\
```

### <span data-ttu-id="63602-135">Exemplo 7: obter itens em um diretório que tem uma exclusão</span><span class="sxs-lookup"><span data-stu-id="63602-135">Example 7: Get items in a directory that have an exclusion</span></span>

<span data-ttu-id="63602-136">Este exemplo obtém os itens no diretório do Windows com nomes que incluem um ponto ( `.` ), mas não comece com `w*` . Este exemplo só funciona quando o caminho inclui um caractere curinga ( `*` ) para especificar o conteúdo do item.</span><span class="sxs-lookup"><span data-stu-id="63602-136">This example gets items in the Windows directory with names that include a dot (`.`), but don't begin with `w*`.This example works only when the path includes a wildcard character (`*`) to specify the contents of the item.</span></span>

```powershell
Get-Item C:\Windows\*.* -Exclude "w*"
```

### <span data-ttu-id="63602-137">Exemplo 8: obtendo informações de hardlink</span><span class="sxs-lookup"><span data-stu-id="63602-137">Example 8: Getting hardlink information</span></span>

<span data-ttu-id="63602-138">No PowerShell 6,2, uma exibição alternativa foi adicionada para obter informações de hardlink.</span><span class="sxs-lookup"><span data-stu-id="63602-138">In PowerShell 6.2, an alternate view was added to get hardlink information.</span></span> <span data-ttu-id="63602-139">Para obter as informações de hardlink, redirecione a saída para `Format-Table -View childrenWithHardlink`</span><span class="sxs-lookup"><span data-stu-id="63602-139">To get the hardlink information, pipe the output to `Format-Table -View childrenWithHardlink`</span></span>

```powershell
Get-Item -Path C:\PathWhichIsAHardLink | Format-Table -View childrenWithHardlink
```

## <span data-ttu-id="63602-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="63602-140">PARAMETERS</span></span>

### <span data-ttu-id="63602-141">-Fluxo</span><span class="sxs-lookup"><span data-stu-id="63602-141">-Stream</span></span>

<span data-ttu-id="63602-142">Obtém o fluxo de arquivos NTFS alternativo especificado do arquivo.</span><span class="sxs-lookup"><span data-stu-id="63602-142">Gets the specified alternate NTFS file stream from the file.</span></span> <span data-ttu-id="63602-143">Insira o nome do fluxo.</span><span class="sxs-lookup"><span data-stu-id="63602-143">Enter the stream name.</span></span> <span data-ttu-id="63602-144">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="63602-144">Wildcards are supported.</span></span> <span data-ttu-id="63602-145">Para obter todos os fluxos, use um asterisco ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="63602-145">To get all streams, use an asterisk (`*`).</span></span> <span data-ttu-id="63602-146">Esse parâmetro não é válido em pastas.</span><span class="sxs-lookup"><span data-stu-id="63602-146">This parameter isn't valid on folders.</span></span>

<span data-ttu-id="63602-147">**Stream** é um parâmetro dinâmico que o provedor **FileSystem** adiciona ao `Get-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="63602-147">**Stream** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Item` cmdlet.</span></span>
<span data-ttu-id="63602-148">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="63602-148">This parameter works only in file system drives.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: No alternate file streams
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="63602-149">-Credential</span><span class="sxs-lookup"><span data-stu-id="63602-149">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="63602-150">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63602-150">This parameter isn't supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="63602-151">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="63602-151">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="63602-152">-Excluir</span><span class="sxs-lookup"><span data-stu-id="63602-152">-Exclude</span></span>

<span data-ttu-id="63602-153">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="63602-153">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="63602-154">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="63602-154">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="63602-155">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="63602-155">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="63602-156">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="63602-156">Wildcard characters are permitted.</span></span> <span data-ttu-id="63602-157">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="63602-157">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="63602-158">-Filter</span><span class="sxs-lookup"><span data-stu-id="63602-158">-Filter</span></span>

<span data-ttu-id="63602-159">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="63602-159">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="63602-160">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte a filtros.</span><span class="sxs-lookup"><span data-stu-id="63602-160">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="63602-161">Os filtros são mais eficientes do que outros parâmetros.</span><span class="sxs-lookup"><span data-stu-id="63602-161">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="63602-162">O provedor aplica-se ao filtro quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="63602-162">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="63602-163">A cadeia de caracteres de filtro é passada para a API do .NET para enumerar arquivos.</span><span class="sxs-lookup"><span data-stu-id="63602-163">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="63602-164">A API só dá suporte a `*` `?` caracteres curinga e.</span><span class="sxs-lookup"><span data-stu-id="63602-164">The API only supports `*` and `?` wildcards.</span></span>

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

### <span data-ttu-id="63602-165">-Force</span><span class="sxs-lookup"><span data-stu-id="63602-165">-Force</span></span>

<span data-ttu-id="63602-166">Indica que esse cmdlet obtém os itens que não podem ser acessados de outra forma, como itens ocultos.</span><span class="sxs-lookup"><span data-stu-id="63602-166">Indicates that this cmdlet gets items that can't otherwise be accessed, such as hidden items.</span></span>
<span data-ttu-id="63602-167">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="63602-167">Implementation varies from provider to provider.</span></span> <span data-ttu-id="63602-168">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="63602-168">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="63602-169">Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="63602-169">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="63602-170">-Incluir</span><span class="sxs-lookup"><span data-stu-id="63602-170">-Include</span></span>

<span data-ttu-id="63602-171">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="63602-171">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="63602-172">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="63602-172">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="63602-173">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="63602-173">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="63602-174">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="63602-174">Wildcard characters are permitted.</span></span> <span data-ttu-id="63602-175">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="63602-175">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="63602-176">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="63602-176">-LiteralPath</span></span>

<span data-ttu-id="63602-177">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="63602-177">Specifies a path to one or more locations.</span></span> <span data-ttu-id="63602-178">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="63602-178">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="63602-179">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="63602-179">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="63602-180">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="63602-180">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="63602-181">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="63602-181">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="63602-182">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="63602-182">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="63602-183">-Path</span><span class="sxs-lookup"><span data-stu-id="63602-183">-Path</span></span>

<span data-ttu-id="63602-184">Especifica o caminho para um item.</span><span class="sxs-lookup"><span data-stu-id="63602-184">Specifies the path to an item.</span></span> <span data-ttu-id="63602-185">Esse cmdlet obtém o item no local especificado.</span><span class="sxs-lookup"><span data-stu-id="63602-185">This cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="63602-186">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="63602-186">Wildcard characters are permitted.</span></span> <span data-ttu-id="63602-187">Esse parâmetro é necessário, mas o **caminho** do nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="63602-187">This parameter is required, but the parameter name **Path** is optional.</span></span>

<span data-ttu-id="63602-188">Use um ponto ( `.` ) para especificar o local atual.</span><span class="sxs-lookup"><span data-stu-id="63602-188">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="63602-189">Use o caractere curinga ( `*` ) para especificar todos os itens no local atual.</span><span class="sxs-lookup"><span data-stu-id="63602-189">Use the wildcard character (`*`) to specify all the items in the current location.</span></span>

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

### <span data-ttu-id="63602-190">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="63602-190">CommonParameters</span></span>

<span data-ttu-id="63602-191">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="63602-191">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="63602-192">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="63602-192">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="63602-193">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="63602-193">INPUTS</span></span>

### <span data-ttu-id="63602-194">System.String</span><span class="sxs-lookup"><span data-stu-id="63602-194">System.String</span></span>

<span data-ttu-id="63602-195">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="63602-195">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="63602-196">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="63602-196">OUTPUTS</span></span>

### <span data-ttu-id="63602-197">System.Object</span><span class="sxs-lookup"><span data-stu-id="63602-197">System.Object</span></span>

<span data-ttu-id="63602-198">Esse cmdlet retorna os objetos que ele obtém.</span><span class="sxs-lookup"><span data-stu-id="63602-198">This cmdlet returns the objects that it gets.</span></span> <span data-ttu-id="63602-199">O tipo é determinado pelo tipo de objetos no caminho.</span><span class="sxs-lookup"><span data-stu-id="63602-199">The type is determined by the type of objects in the path.</span></span>

## <span data-ttu-id="63602-200">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="63602-200">NOTES</span></span>

<span data-ttu-id="63602-201">Esse cmdlet não tem um parâmetro **recurse** , pois ele obtém apenas um item, não seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="63602-201">This cmdlet does not have a **Recurse** parameter, because it gets only an item, not its contents.</span></span>
<span data-ttu-id="63602-202">Para obter o conteúdo de um item recursivamente, use `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="63602-202">To get the contents of an item recursively, use `Get-ChildItem`.</span></span>

<span data-ttu-id="63602-203">Para navegar pelo registro, use este cmdlet para obter chaves do registro e `Get-ItemProperty` para obter valores e dados do registro.</span><span class="sxs-lookup"><span data-stu-id="63602-203">To navigate through the registry, use this cmdlet to get registry keys and the `Get-ItemProperty` to get registry values and data.</span></span> <span data-ttu-id="63602-204">Os valores do registro são considerados propriedade da chave do registro.</span><span class="sxs-lookup"><span data-stu-id="63602-204">The registry values are considered to be properties of the registry key.</span></span>
  
<span data-ttu-id="63602-205">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="63602-205">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="63602-206">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="63602-206">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="63602-207">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="63602-207">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="63602-208">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="63602-208">RELATED LINKS</span></span>

[<span data-ttu-id="63602-209">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="63602-209">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="63602-210">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="63602-210">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="63602-211">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="63602-211">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="63602-212">Move-Item</span><span class="sxs-lookup"><span data-stu-id="63602-212">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="63602-213">New-Item</span><span class="sxs-lookup"><span data-stu-id="63602-213">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="63602-214">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="63602-214">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="63602-215">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="63602-215">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="63602-216">Set-Item</span><span class="sxs-lookup"><span data-stu-id="63602-216">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="63602-217">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="63602-217">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="63602-218">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="63602-218">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="63602-219">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="63602-219">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="63602-220">about_Providers</span><span class="sxs-lookup"><span data-stu-id="63602-220">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
