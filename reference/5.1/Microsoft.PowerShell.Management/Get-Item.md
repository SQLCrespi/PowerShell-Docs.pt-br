---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Item
ms.openlocfilehash: 1498c7eb254e0d21b108c4016d8b737d5b33298d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194172"
---
# <span data-ttu-id="d18e8-103">Get-Item</span><span class="sxs-lookup"><span data-stu-id="d18e8-103">Get-Item</span></span>

## <span data-ttu-id="d18e8-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d18e8-104">SYNOPSIS</span></span>
<span data-ttu-id="d18e8-105">Obtém o item no local especificado.</span><span class="sxs-lookup"><span data-stu-id="d18e8-105">Gets the item at the specified location.</span></span>

## <span data-ttu-id="d18e8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d18e8-106">SYNTAX</span></span>

### <span data-ttu-id="d18e8-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="d18e8-107">Path (Default)</span></span>

```
Get-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-UseTransaction] [-Stream <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="d18e8-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d18e8-108">LiteralPath</span></span>

```
Get-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-UseTransaction] [-Stream <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="d18e8-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d18e8-109">DESCRIPTION</span></span>

<span data-ttu-id="d18e8-110">O `Get-Item` cmdlet obtém o item no local especificado.</span><span class="sxs-lookup"><span data-stu-id="d18e8-110">The `Get-Item` cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="d18e8-111">Ele não obtém o conteúdo do item no local, a menos que você use um caractere curinga ( `*` ) para solicitar todo o conteúdo do item.</span><span class="sxs-lookup"><span data-stu-id="d18e8-111">It doesn't get the contents of the item at the location unless you use a wildcard character (`*`) to request all the contents of the item.</span></span>

<span data-ttu-id="d18e8-112">Esse cmdlet é usado pelos provedores do PowerShell para navegar por diferentes tipos de armazenamentos de dados.</span><span class="sxs-lookup"><span data-stu-id="d18e8-112">This cmdlet is used by PowerShell providers to navigate through different types of data stores.</span></span>

## <span data-ttu-id="d18e8-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d18e8-113">EXAMPLES</span></span>

### <span data-ttu-id="d18e8-114">Exemplo 1: obter o diretório atual</span><span class="sxs-lookup"><span data-stu-id="d18e8-114">Example 1: Get the current directory</span></span>

<span data-ttu-id="d18e8-115">Este exemplo obtém o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="d18e8-115">This example gets the current directory.</span></span> <span data-ttu-id="d18e8-116">O ponto ('. ') representa o item no local atual (não seu conteúdo).</span><span class="sxs-lookup"><span data-stu-id="d18e8-116">The dot ('.') represents the item at the current location (not its contents).</span></span>

```powershell
Get-Item .
```

```output
Directory: C:\

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006  10:01 AM            ps-test
```

### <span data-ttu-id="d18e8-117">Exemplo 2: obter todos os itens no diretório atual</span><span class="sxs-lookup"><span data-stu-id="d18e8-117">Example 2: Get all the items in the current directory</span></span>

<span data-ttu-id="d18e8-118">Este exemplo obtém todos os itens no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="d18e8-118">This example gets all the items in the current directory.</span></span> <span data-ttu-id="d18e8-119">O caractere curinga ( `*` ) representa todo o conteúdo do item atual.</span><span class="sxs-lookup"><span data-stu-id="d18e8-119">The wildcard character (`*`) represents all the contents of the current item.</span></span>

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

### <span data-ttu-id="d18e8-120">Exemplo 3: obter o diretório atual de uma unidade</span><span class="sxs-lookup"><span data-stu-id="d18e8-120">Example 3: Get the current directory of a drive</span></span>

<span data-ttu-id="d18e8-121">Este exemplo obtém o diretório atual da `C:` unidade.</span><span class="sxs-lookup"><span data-stu-id="d18e8-121">This example gets the current directory of the `C:` drive.</span></span> <span data-ttu-id="d18e8-122">O objeto recuperado representa somente o diretório, e não o seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="d18e8-122">The object that is retrieved represents only the directory, not its contents.</span></span>

```powershell
Get-Item C:\
```

### <span data-ttu-id="d18e8-123">Exemplo 4: obter itens na unidade especificada</span><span class="sxs-lookup"><span data-stu-id="d18e8-123">Example 4: Get items in the specified drive</span></span>

<span data-ttu-id="d18e8-124">Este exemplo obtém os itens na `C:` unidade.</span><span class="sxs-lookup"><span data-stu-id="d18e8-124">This example gets the items in the `C:` drive.</span></span> <span data-ttu-id="d18e8-125">O caractere curinga ( `*` ) representa todos os itens no contêiner, não apenas o contêiner.</span><span class="sxs-lookup"><span data-stu-id="d18e8-125">The wildcard character (`*`) represents all the items in the container, not just the container.</span></span>

```powershell
Get-Item C:\*
```

<span data-ttu-id="d18e8-126">No PowerShell, use um único asterisco ( `*` ) para obter o conteúdo, em vez do tradicional `*.*` .</span><span class="sxs-lookup"><span data-stu-id="d18e8-126">In PowerShell, use a single asterisk (`*`) to get contents, instead of the traditional `*.*`.</span></span> <span data-ttu-id="d18e8-127">O formato é interpretado literalmente, portanto, não `*.*` recuperaria diretórios ou nomes de FileName sem um ponto.</span><span class="sxs-lookup"><span data-stu-id="d18e8-127">The format is interpreted literally, so `*.*` wouldn't retrieve directories or filenames without a dot.</span></span>

### <span data-ttu-id="d18e8-128">Exemplo 5: obter uma propriedade no diretório especificado</span><span class="sxs-lookup"><span data-stu-id="d18e8-128">Example 5: Get a property in the specified directory</span></span>

<span data-ttu-id="d18e8-129">Este exemplo obtém a propriedade **LastAccessTime** do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="d18e8-129">This example gets the **LastAccessTime** property of the `C:\Windows` directory.</span></span> <span data-ttu-id="d18e8-130">**LastAccessTime** é apenas uma propriedade dos diretórios do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d18e8-130">**LastAccessTime** is just one property of file system directories.</span></span> <span data-ttu-id="d18e8-131">Para ver todas as propriedades de um diretório, digite `(Get-Item <directory-name>) | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="d18e8-131">To see all the properties of a directory, type `(Get-Item <directory-name>) | Get-Member`.</span></span>

```powershell
(Get-Item C:\Windows).LastAccessTime
```

### <span data-ttu-id="d18e8-132">Exemplo 6: mostrar o conteúdo de uma chave do registro</span><span class="sxs-lookup"><span data-stu-id="d18e8-132">Example 6: Show the contents of a registry key</span></span>

<span data-ttu-id="d18e8-133">Este exemplo mostra o conteúdo da chave do registro **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="d18e8-133">This example shows the contents of the **Microsoft.PowerShell** registry key.</span></span> <span data-ttu-id="d18e8-134">Você pode usar esse cmdlet com o provedor de registro do PowerShell para obter chaves e subchaves do registro, mas você deve usar o `Get-ItemProperty` cmdlet para obter os valores e os dados do registro.</span><span class="sxs-lookup"><span data-stu-id="d18e8-134">You can use this cmdlet with the PowerShell Registry provider to get registry keys and subkeys, but you must use the `Get-ItemProperty` cmdlet to get the registry values and data.</span></span>

```powershell
Get-Item HKLM:\Software\Microsoft\Powershell\1\Shellids\Microsoft.Powershell\
```

### <span data-ttu-id="d18e8-135">Exemplo 7: obter itens em um diretório que tem uma exclusão</span><span class="sxs-lookup"><span data-stu-id="d18e8-135">Example 7: Get items in a directory that have an exclusion</span></span>

<span data-ttu-id="d18e8-136">Este exemplo obtém os itens no diretório do Windows com nomes que incluem um ponto ( `.` ), mas não comece com `w*` . Este exemplo só funciona quando o caminho inclui um caractere curinga ( `*` ) para especificar o conteúdo do item.</span><span class="sxs-lookup"><span data-stu-id="d18e8-136">This example gets items in the Windows directory with names that include a dot (`.`), but don't begin with `w*`.This example works only when the path includes a wildcard character (`*`) to specify the contents of the item.</span></span>

```powershell
Get-Item C:\Windows\*.* -Exclude "w*"
```

## <span data-ttu-id="d18e8-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d18e8-137">PARAMETERS</span></span>

### <span data-ttu-id="d18e8-138">-Fluxo</span><span class="sxs-lookup"><span data-stu-id="d18e8-138">-Stream</span></span>

<span data-ttu-id="d18e8-139">Obtém o fluxo de arquivos NTFS alternativo especificado do arquivo.</span><span class="sxs-lookup"><span data-stu-id="d18e8-139">Gets the specified alternate NTFS file stream from the file.</span></span> <span data-ttu-id="d18e8-140">Insira o nome do fluxo.</span><span class="sxs-lookup"><span data-stu-id="d18e8-140">Enter the stream name.</span></span> <span data-ttu-id="d18e8-141">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="d18e8-141">Wildcards are supported.</span></span> <span data-ttu-id="d18e8-142">Para obter todos os fluxos, use um asterisco ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="d18e8-142">To get all streams, use an asterisk (`*`).</span></span> <span data-ttu-id="d18e8-143">Esse parâmetro não é válido em pastas.</span><span class="sxs-lookup"><span data-stu-id="d18e8-143">This parameter isn't valid on folders.</span></span>

<span data-ttu-id="d18e8-144">**Stream** é um parâmetro dinâmico que o provedor **FileSystem** adiciona ao `Get-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d18e8-144">**Stream** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Item` cmdlet.</span></span>
<span data-ttu-id="d18e8-145">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d18e8-145">This parameter works only in file system drives.</span></span>

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

### <span data-ttu-id="d18e8-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="d18e8-146">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="d18e8-147">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d18e8-147">This parameter isn't supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="d18e8-148">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="d18e8-148">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="d18e8-149">-Excluir</span><span class="sxs-lookup"><span data-stu-id="d18e8-149">-Exclude</span></span>

<span data-ttu-id="d18e8-150">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="d18e8-150">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="d18e8-151">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="d18e8-151">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="d18e8-152">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="d18e8-152">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="d18e8-153">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d18e8-153">Wildcard characters are permitted.</span></span> <span data-ttu-id="d18e8-154">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="d18e8-154">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="d18e8-155">-Filter</span><span class="sxs-lookup"><span data-stu-id="d18e8-155">-Filter</span></span>

<span data-ttu-id="d18e8-156">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="d18e8-156">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="d18e8-157">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte a filtros.</span><span class="sxs-lookup"><span data-stu-id="d18e8-157">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="d18e8-158">Os filtros são mais eficientes do que outros parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d18e8-158">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="d18e8-159">O provedor aplica-se ao filtro quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="d18e8-159">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="d18e8-160">A cadeia de caracteres de filtro é passada para a API do .NET para enumerar arquivos.</span><span class="sxs-lookup"><span data-stu-id="d18e8-160">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="d18e8-161">A API só dá suporte a `*` `?` caracteres curinga e.</span><span class="sxs-lookup"><span data-stu-id="d18e8-161">The API only supports `*` and `?` wildcards.</span></span>

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

### <span data-ttu-id="d18e8-162">-Force</span><span class="sxs-lookup"><span data-stu-id="d18e8-162">-Force</span></span>

<span data-ttu-id="d18e8-163">Indica que esse cmdlet obtém os itens que não podem ser acessados de outra forma, como itens ocultos.</span><span class="sxs-lookup"><span data-stu-id="d18e8-163">Indicates that this cmdlet gets items that can't otherwise be accessed, such as hidden items.</span></span>
<span data-ttu-id="d18e8-164">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="d18e8-164">Implementation varies from provider to provider.</span></span> <span data-ttu-id="d18e8-165">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d18e8-165">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="d18e8-166">Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="d18e8-166">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="d18e8-167">-Incluir</span><span class="sxs-lookup"><span data-stu-id="d18e8-167">-Include</span></span>

<span data-ttu-id="d18e8-168">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="d18e8-168">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="d18e8-169">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="d18e8-169">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="d18e8-170">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="d18e8-170">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="d18e8-171">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d18e8-171">Wildcard characters are permitted.</span></span> <span data-ttu-id="d18e8-172">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="d18e8-172">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="d18e8-173">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d18e8-173">-LiteralPath</span></span>

<span data-ttu-id="d18e8-174">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="d18e8-174">Specifies a path to one or more locations.</span></span> <span data-ttu-id="d18e8-175">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="d18e8-175">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="d18e8-176">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="d18e8-176">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="d18e8-177">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="d18e8-177">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="d18e8-178">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="d18e8-178">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="d18e8-179">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="d18e8-179">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d18e8-180">-Path</span><span class="sxs-lookup"><span data-stu-id="d18e8-180">-Path</span></span>

<span data-ttu-id="d18e8-181">Especifica o caminho para um item.</span><span class="sxs-lookup"><span data-stu-id="d18e8-181">Specifies the path to an item.</span></span> <span data-ttu-id="d18e8-182">Esse cmdlet obtém o item no local especificado.</span><span class="sxs-lookup"><span data-stu-id="d18e8-182">This cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="d18e8-183">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d18e8-183">Wildcard characters are permitted.</span></span> <span data-ttu-id="d18e8-184">Esse parâmetro é necessário, mas o **caminho** do nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="d18e8-184">This parameter is required, but the parameter name **Path** is optional.</span></span>

<span data-ttu-id="d18e8-185">Use um ponto ( `.` ) para especificar o local atual.</span><span class="sxs-lookup"><span data-stu-id="d18e8-185">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="d18e8-186">Use o caractere curinga ( `*` ) para especificar todos os itens no local atual.</span><span class="sxs-lookup"><span data-stu-id="d18e8-186">Use the wildcard character (`*`) to specify all the items in the current location.</span></span>

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

### <span data-ttu-id="d18e8-187">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="d18e8-187">-UseTransaction</span></span>

<span data-ttu-id="d18e8-188">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="d18e8-188">Includes the command in the active transaction.</span></span>
<span data-ttu-id="d18e8-189">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="d18e8-189">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="d18e8-190">Para obter mais informações, consulte [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="d18e8-190">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d18e8-191">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d18e8-191">CommonParameters</span></span>

<span data-ttu-id="d18e8-192">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="d18e8-192">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="d18e8-193">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d18e8-193">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d18e8-194">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d18e8-194">INPUTS</span></span>

### <span data-ttu-id="d18e8-195">System.String</span><span class="sxs-lookup"><span data-stu-id="d18e8-195">System.String</span></span>

<span data-ttu-id="d18e8-196">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d18e8-196">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="d18e8-197">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d18e8-197">OUTPUTS</span></span>

### <span data-ttu-id="d18e8-198">System.Object</span><span class="sxs-lookup"><span data-stu-id="d18e8-198">System.Object</span></span>

<span data-ttu-id="d18e8-199">Esse cmdlet retorna os objetos que ele obtém.</span><span class="sxs-lookup"><span data-stu-id="d18e8-199">This cmdlet returns the objects that it gets.</span></span> <span data-ttu-id="d18e8-200">O tipo é determinado pelo tipo de objetos no caminho.</span><span class="sxs-lookup"><span data-stu-id="d18e8-200">The type is determined by the type of objects in the path.</span></span>

## <span data-ttu-id="d18e8-201">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d18e8-201">NOTES</span></span>

<span data-ttu-id="d18e8-202">Esse cmdlet não tem um parâmetro **recurse** , pois ele obtém apenas um item, não seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="d18e8-202">This cmdlet does not have a **Recurse** parameter, because it gets only an item, not its contents.</span></span>
<span data-ttu-id="d18e8-203">Para obter o conteúdo de um item recursivamente, use `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="d18e8-203">To get the contents of an item recursively, use `Get-ChildItem`.</span></span>

<span data-ttu-id="d18e8-204">Para navegar pelo registro, use este cmdlet para obter chaves do registro e `Get-ItemProperty` para obter valores e dados do registro.</span><span class="sxs-lookup"><span data-stu-id="d18e8-204">To navigate through the registry, use this cmdlet to get registry keys and the `Get-ItemProperty` to get registry values and data.</span></span> <span data-ttu-id="d18e8-205">Os valores do registro são considerados propriedade da chave do registro.</span><span class="sxs-lookup"><span data-stu-id="d18e8-205">The registry values are considered to be properties of the registry key.</span></span>

<span data-ttu-id="d18e8-206">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="d18e8-206">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="d18e8-207">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="d18e8-207">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="d18e8-208">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d18e8-208">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="d18e8-209">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d18e8-209">RELATED LINKS</span></span>

[<span data-ttu-id="d18e8-210">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="d18e8-210">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="d18e8-211">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="d18e8-211">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="d18e8-212">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="d18e8-212">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="d18e8-213">Move-Item</span><span class="sxs-lookup"><span data-stu-id="d18e8-213">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="d18e8-214">New-Item</span><span class="sxs-lookup"><span data-stu-id="d18e8-214">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="d18e8-215">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="d18e8-215">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="d18e8-216">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="d18e8-216">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="d18e8-217">Set-Item</span><span class="sxs-lookup"><span data-stu-id="d18e8-217">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="d18e8-218">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d18e8-218">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="d18e8-219">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d18e8-219">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="d18e8-220">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="d18e8-220">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="d18e8-221">about_Providers</span><span class="sxs-lookup"><span data-stu-id="d18e8-221">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
