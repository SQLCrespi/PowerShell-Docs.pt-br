---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Item
ms.openlocfilehash: 67d9f351b8ef4936dcb4e9cff6583da0f464bc12
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "99603756"
---
# <span data-ttu-id="669c2-102">Get-Item</span><span class="sxs-lookup"><span data-stu-id="669c2-102">Get-Item</span></span>

## <span data-ttu-id="669c2-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="669c2-103">SYNOPSIS</span></span>
<span data-ttu-id="669c2-104">Obtém o item no local especificado.</span><span class="sxs-lookup"><span data-stu-id="669c2-104">Gets the item at the specified location.</span></span>

## <span data-ttu-id="669c2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="669c2-105">SYNTAX</span></span>

### <span data-ttu-id="669c2-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="669c2-106">Path (Default)</span></span>

```
Get-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="669c2-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="669c2-107">LiteralPath</span></span>

```
Get-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Force] [-Credential <PSCredential>] [-Stream <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="669c2-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="669c2-108">DESCRIPTION</span></span>

<span data-ttu-id="669c2-109">O `Get-Item` cmdlet obtém o item no local especificado.</span><span class="sxs-lookup"><span data-stu-id="669c2-109">The `Get-Item` cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="669c2-110">Ele não obtém o conteúdo do item no local, a menos que você use um caractere curinga ( `*` ) para solicitar todo o conteúdo do item.</span><span class="sxs-lookup"><span data-stu-id="669c2-110">It doesn't get the contents of the item at the location unless you use a wildcard character (`*`) to request all the contents of the item.</span></span>

<span data-ttu-id="669c2-111">Esse cmdlet é usado pelos provedores do PowerShell para navegar por diferentes tipos de armazenamentos de dados.</span><span class="sxs-lookup"><span data-stu-id="669c2-111">This cmdlet is used by PowerShell providers to navigate through different types of data stores.</span></span>

## <span data-ttu-id="669c2-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="669c2-112">EXAMPLES</span></span>

### <span data-ttu-id="669c2-113">Exemplo 1: obter o diretório atual</span><span class="sxs-lookup"><span data-stu-id="669c2-113">Example 1: Get the current directory</span></span>

<span data-ttu-id="669c2-114">Este exemplo obtém o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="669c2-114">This example gets the current directory.</span></span> <span data-ttu-id="669c2-115">O ponto ('. ') representa o item no local atual (não seu conteúdo).</span><span class="sxs-lookup"><span data-stu-id="669c2-115">The dot ('.') represents the item at the current location (not its contents).</span></span>

```powershell
Get-Item .
```

```output
Directory: C:\

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         7/26/2006  10:01 AM            ps-test
```

### <span data-ttu-id="669c2-116">Exemplo 2: obter todos os itens no diretório atual</span><span class="sxs-lookup"><span data-stu-id="669c2-116">Example 2: Get all the items in the current directory</span></span>

<span data-ttu-id="669c2-117">Este exemplo obtém todos os itens no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="669c2-117">This example gets all the items in the current directory.</span></span> <span data-ttu-id="669c2-118">O caractere curinga ( `*` ) representa todo o conteúdo do item atual.</span><span class="sxs-lookup"><span data-stu-id="669c2-118">The wildcard character (`*`) represents all the contents of the current item.</span></span>

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

### <span data-ttu-id="669c2-119">Exemplo 3: obter o diretório atual de uma unidade</span><span class="sxs-lookup"><span data-stu-id="669c2-119">Example 3: Get the current directory of a drive</span></span>

<span data-ttu-id="669c2-120">Este exemplo obtém o diretório atual da `C:` unidade.</span><span class="sxs-lookup"><span data-stu-id="669c2-120">This example gets the current directory of the `C:` drive.</span></span> <span data-ttu-id="669c2-121">O objeto recuperado representa somente o diretório, e não o seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="669c2-121">The object that is retrieved represents only the directory, not its contents.</span></span>

```powershell
Get-Item C:\
```

### <span data-ttu-id="669c2-122">Exemplo 4: obter itens na unidade especificada</span><span class="sxs-lookup"><span data-stu-id="669c2-122">Example 4: Get items in the specified drive</span></span>

<span data-ttu-id="669c2-123">Este exemplo obtém os itens na `C:` unidade.</span><span class="sxs-lookup"><span data-stu-id="669c2-123">This example gets the items in the `C:` drive.</span></span> <span data-ttu-id="669c2-124">O caractere curinga ( `*` ) representa todos os itens no contêiner, não apenas o contêiner.</span><span class="sxs-lookup"><span data-stu-id="669c2-124">The wildcard character (`*`) represents all the items in the container, not just the container.</span></span>

```powershell
Get-Item C:\*
```

<span data-ttu-id="669c2-125">No PowerShell, use um único asterisco ( `*` ) para obter o conteúdo, em vez do tradicional `*.*` .</span><span class="sxs-lookup"><span data-stu-id="669c2-125">In PowerShell, use a single asterisk (`*`) to get contents, instead of the traditional `*.*`.</span></span> <span data-ttu-id="669c2-126">O formato é interpretado literalmente, portanto, não `*.*` recuperaria diretórios ou nomes de FileName sem um ponto.</span><span class="sxs-lookup"><span data-stu-id="669c2-126">The format is interpreted literally, so `*.*` wouldn't retrieve directories or filenames without a dot.</span></span>

### <span data-ttu-id="669c2-127">Exemplo 5: obter uma propriedade no diretório especificado</span><span class="sxs-lookup"><span data-stu-id="669c2-127">Example 5: Get a property in the specified directory</span></span>

<span data-ttu-id="669c2-128">Este exemplo obtém a propriedade **LastAccessTime** do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="669c2-128">This example gets the **LastAccessTime** property of the `C:\Windows` directory.</span></span> <span data-ttu-id="669c2-129">**LastAccessTime** é apenas uma propriedade dos diretórios do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="669c2-129">**LastAccessTime** is just one property of file system directories.</span></span> <span data-ttu-id="669c2-130">Para ver todas as propriedades de um diretório, digite `(Get-Item <directory-name>) | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="669c2-130">To see all the properties of a directory, type `(Get-Item <directory-name>) | Get-Member`.</span></span>

```powershell
(Get-Item C:\Windows).LastAccessTime
```

### <span data-ttu-id="669c2-131">Exemplo 6: mostrar o conteúdo de uma chave do registro</span><span class="sxs-lookup"><span data-stu-id="669c2-131">Example 6: Show the contents of a registry key</span></span>

<span data-ttu-id="669c2-132">Este exemplo mostra o conteúdo da chave do registro **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="669c2-132">This example shows the contents of the **Microsoft.PowerShell** registry key.</span></span> <span data-ttu-id="669c2-133">Você pode usar esse cmdlet com o provedor de registro do PowerShell para obter chaves e subchaves do registro, mas você deve usar o `Get-ItemProperty` cmdlet para obter os valores e os dados do registro.</span><span class="sxs-lookup"><span data-stu-id="669c2-133">You can use this cmdlet with the PowerShell Registry provider to get registry keys and subkeys, but you must use the `Get-ItemProperty` cmdlet to get the registry values and data.</span></span>

```powershell
Get-Item HKLM:\Software\Microsoft\Powershell\1\Shellids\Microsoft.Powershell\
```

### <span data-ttu-id="669c2-134">Exemplo 7: obter itens em um diretório que tem uma exclusão</span><span class="sxs-lookup"><span data-stu-id="669c2-134">Example 7: Get items in a directory that have an exclusion</span></span>

<span data-ttu-id="669c2-135">Este exemplo obtém os itens no diretório do Windows com nomes que incluem um ponto ( `.` ), mas não comece com `w*` . Este exemplo só funciona quando o caminho inclui um caractere curinga ( `*` ) para especificar o conteúdo do item.</span><span class="sxs-lookup"><span data-stu-id="669c2-135">This example gets items in the Windows directory with names that include a dot (`.`), but don't begin with `w*`.This example works only when the path includes a wildcard character (`*`) to specify the contents of the item.</span></span>

```powershell
Get-Item C:\Windows\*.* -Exclude "w*"
```

### <span data-ttu-id="669c2-136">Exemplo 8: obtendo informações de hardlink</span><span class="sxs-lookup"><span data-stu-id="669c2-136">Example 8: Getting hardlink information</span></span>

<span data-ttu-id="669c2-137">No PowerShell 6,2, uma exibição alternativa foi adicionada para obter informações de hardlink.</span><span class="sxs-lookup"><span data-stu-id="669c2-137">In PowerShell 6.2, an alternate view was added to get hardlink information.</span></span> <span data-ttu-id="669c2-138">Para obter as informações de hardlink, redirecione a saída para `Format-Table -View childrenWithHardlink`</span><span class="sxs-lookup"><span data-stu-id="669c2-138">To get the hardlink information, pipe the output to `Format-Table -View childrenWithHardlink`</span></span>

```powershell
Get-Item -Path C:\PathWhichIsAHardLink | Format-Table -View childrenWithHardlink
```

### <span data-ttu-id="669c2-139">Exemplo 9: saída para sistemas operacionais que não são do Windows</span><span class="sxs-lookup"><span data-stu-id="669c2-139">Example 9: Output for Non-Windows Operating Systems</span></span>

<span data-ttu-id="669c2-140">No PowerShell 7,1 em sistemas UNIX, o `Get-Item` cmdlet fornece saída semelhante ao Unix:</span><span class="sxs-lookup"><span data-stu-id="669c2-140">In PowerShell 7.1 on Unix systems, the `Get-Item` cmdlet provides Unix-like output:</span></span>

```powershell
PS> Get-Item /Users
```

```Output
    Directory: /

UnixMode    User  Group   LastWriteTime      Size  Name
--------    ----  -----   -------------      ----  ----
drwxr-xr-x  root  admin   12/20/2019 11:46   192   Users
```

<span data-ttu-id="669c2-141">As novas propriedades que agora fazem parte da saída são:</span><span class="sxs-lookup"><span data-stu-id="669c2-141">The new properties that are now part of the output are:</span></span>

- <span data-ttu-id="669c2-142">**Unixmode** são as permissões de arquivo, conforme representado em um sistema UNIX</span><span class="sxs-lookup"><span data-stu-id="669c2-142">**UnixMode** is the file permissions as represented on a Unix system</span></span>
- <span data-ttu-id="669c2-143">O **usuário** é o proprietário do arquivo</span><span class="sxs-lookup"><span data-stu-id="669c2-143">**User** is the file owner</span></span>
- <span data-ttu-id="669c2-144">O **grupo** é o proprietário do grupo</span><span class="sxs-lookup"><span data-stu-id="669c2-144">**Group** is the group owner</span></span>
- <span data-ttu-id="669c2-145">**Tamanho** é o tamanho do arquivo ou diretório, conforme representado em um sistema UNIX</span><span class="sxs-lookup"><span data-stu-id="669c2-145">**Size** is the size of the file or directory as represented on a Unix system</span></span>

> [!NOTE]
> <span data-ttu-id="669c2-146">Esse recurso foi movido do experimental para o básico no PowerShell 7,1.</span><span class="sxs-lookup"><span data-stu-id="669c2-146">This feature was moved from experimental to mainstream in PowerShell 7.1.</span></span>

## <span data-ttu-id="669c2-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="669c2-147">PARAMETERS</span></span>

### <span data-ttu-id="669c2-148">-Fluxo</span><span class="sxs-lookup"><span data-stu-id="669c2-148">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="669c2-149">Esse parâmetro só está disponível no Windows.</span><span class="sxs-lookup"><span data-stu-id="669c2-149">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="669c2-150">Obtém o fluxo de dados alternativo especificado do arquivo.</span><span class="sxs-lookup"><span data-stu-id="669c2-150">Gets the specified alternative data stream from the file.</span></span> <span data-ttu-id="669c2-151">Insira o nome do fluxo.</span><span class="sxs-lookup"><span data-stu-id="669c2-151">Enter the stream name.</span></span> <span data-ttu-id="669c2-152">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="669c2-152">Wildcards are supported.</span></span> <span data-ttu-id="669c2-153">Para obter todos os fluxos, use um asterisco ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="669c2-153">To get all streams, use an asterisk (`*`).</span></span> <span data-ttu-id="669c2-154">Esse parâmetro é válido em diretórios, mas observe que os diretórios não têm fluxos de dados por padrão.</span><span class="sxs-lookup"><span data-stu-id="669c2-154">This parameter is valid on directories, but note that directories do not have data streams by default.</span></span>

<span data-ttu-id="669c2-155">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="669c2-155">This parameter was introduced in PowerShell 3.0.</span></span>  <span data-ttu-id="669c2-156">A partir do PowerShell 7,2, o `Get-Item` pode obter fluxos de dados alternativos de diretórios, bem como arquivos.</span><span class="sxs-lookup"><span data-stu-id="669c2-156">As of PowerShell 7.2, `Get-Item` can get alternative data streams from directories as well as files.</span></span>

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

### <span data-ttu-id="669c2-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="669c2-157">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="669c2-158">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="669c2-158">This parameter isn't supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="669c2-159">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="669c2-159">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="669c2-160">-Excluir</span><span class="sxs-lookup"><span data-stu-id="669c2-160">-Exclude</span></span>

<span data-ttu-id="669c2-161">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="669c2-161">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="669c2-162">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="669c2-162">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="669c2-163">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="669c2-163">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="669c2-164">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="669c2-164">Wildcard characters are permitted.</span></span> <span data-ttu-id="669c2-165">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="669c2-165">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="669c2-166">-Filter</span><span class="sxs-lookup"><span data-stu-id="669c2-166">-Filter</span></span>

<span data-ttu-id="669c2-167">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="669c2-167">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="669c2-168">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte a filtros.</span><span class="sxs-lookup"><span data-stu-id="669c2-168">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="669c2-169">Os filtros são mais eficientes do que outros parâmetros.</span><span class="sxs-lookup"><span data-stu-id="669c2-169">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="669c2-170">O provedor aplica-se ao filtro quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="669c2-170">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="669c2-171">A cadeia de caracteres de filtro é passada para a API do .NET para enumerar arquivos.</span><span class="sxs-lookup"><span data-stu-id="669c2-171">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="669c2-172">A API só dá suporte a `*` `?` caracteres curinga e.</span><span class="sxs-lookup"><span data-stu-id="669c2-172">The API only supports `*` and `?` wildcards.</span></span>

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

### <span data-ttu-id="669c2-173">-Force</span><span class="sxs-lookup"><span data-stu-id="669c2-173">-Force</span></span>

<span data-ttu-id="669c2-174">Indica que esse cmdlet obtém os itens que não podem ser acessados de outra forma, como itens ocultos.</span><span class="sxs-lookup"><span data-stu-id="669c2-174">Indicates that this cmdlet gets items that can't otherwise be accessed, such as hidden items.</span></span>
<span data-ttu-id="669c2-175">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="669c2-175">Implementation varies from provider to provider.</span></span> <span data-ttu-id="669c2-176">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="669c2-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="669c2-177">Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="669c2-177">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="669c2-178">-Incluir</span><span class="sxs-lookup"><span data-stu-id="669c2-178">-Include</span></span>

<span data-ttu-id="669c2-179">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="669c2-179">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="669c2-180">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="669c2-180">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="669c2-181">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="669c2-181">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="669c2-182">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="669c2-182">Wildcard characters are permitted.</span></span> <span data-ttu-id="669c2-183">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="669c2-183">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="669c2-184">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="669c2-184">-LiteralPath</span></span>

<span data-ttu-id="669c2-185">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="669c2-185">Specifies a path to one or more locations.</span></span> <span data-ttu-id="669c2-186">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="669c2-186">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="669c2-187">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="669c2-187">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="669c2-188">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="669c2-188">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="669c2-189">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="669c2-189">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="669c2-190">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="669c2-190">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="669c2-191">-Path</span><span class="sxs-lookup"><span data-stu-id="669c2-191">-Path</span></span>

<span data-ttu-id="669c2-192">Especifica o caminho para um item.</span><span class="sxs-lookup"><span data-stu-id="669c2-192">Specifies the path to an item.</span></span> <span data-ttu-id="669c2-193">Esse cmdlet obtém o item no local especificado.</span><span class="sxs-lookup"><span data-stu-id="669c2-193">This cmdlet gets the item at the specified location.</span></span> <span data-ttu-id="669c2-194">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="669c2-194">Wildcard characters are permitted.</span></span> <span data-ttu-id="669c2-195">Esse parâmetro é necessário, mas o **caminho** do nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="669c2-195">This parameter is required, but the parameter name **Path** is optional.</span></span>

<span data-ttu-id="669c2-196">Use um ponto ( `.` ) para especificar o local atual.</span><span class="sxs-lookup"><span data-stu-id="669c2-196">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="669c2-197">Use o caractere curinga ( `*` ) para especificar todos os itens no local atual.</span><span class="sxs-lookup"><span data-stu-id="669c2-197">Use the wildcard character (`*`) to specify all the items in the current location.</span></span>

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

### <span data-ttu-id="669c2-198">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="669c2-198">CommonParameters</span></span>

<span data-ttu-id="669c2-199">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="669c2-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="669c2-200">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="669c2-200">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="669c2-201">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="669c2-201">INPUTS</span></span>

### <span data-ttu-id="669c2-202">System.String</span><span class="sxs-lookup"><span data-stu-id="669c2-202">System.String</span></span>

<span data-ttu-id="669c2-203">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="669c2-203">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="669c2-204">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="669c2-204">OUTPUTS</span></span>

### <span data-ttu-id="669c2-205">System.Object</span><span class="sxs-lookup"><span data-stu-id="669c2-205">System.Object</span></span>

<span data-ttu-id="669c2-206">Esse cmdlet retorna os objetos que ele obtém.</span><span class="sxs-lookup"><span data-stu-id="669c2-206">This cmdlet returns the objects that it gets.</span></span> <span data-ttu-id="669c2-207">O tipo é determinado pelo tipo de objetos no caminho.</span><span class="sxs-lookup"><span data-stu-id="669c2-207">The type is determined by the type of objects in the path.</span></span>

## <span data-ttu-id="669c2-208">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="669c2-208">NOTES</span></span>

<span data-ttu-id="669c2-209">Esse cmdlet não tem um parâmetro **recurse** , pois ele obtém apenas um item, não seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="669c2-209">This cmdlet does not have a **Recurse** parameter, because it gets only an item, not its contents.</span></span>
<span data-ttu-id="669c2-210">Para obter o conteúdo de um item recursivamente, use `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="669c2-210">To get the contents of an item recursively, use `Get-ChildItem`.</span></span>

<span data-ttu-id="669c2-211">Para navegar pelo registro, use este cmdlet para obter chaves do registro e `Get-ItemProperty` para obter valores e dados do registro.</span><span class="sxs-lookup"><span data-stu-id="669c2-211">To navigate through the registry, use this cmdlet to get registry keys and the `Get-ItemProperty` to get registry values and data.</span></span> <span data-ttu-id="669c2-212">Os valores do registro são considerados propriedade da chave do registro.</span><span class="sxs-lookup"><span data-stu-id="669c2-212">The registry values are considered to be properties of the registry key.</span></span>

<span data-ttu-id="669c2-213">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="669c2-213">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="669c2-214">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="669c2-214">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="669c2-215">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="669c2-215">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="669c2-216">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="669c2-216">RELATED LINKS</span></span>

[<span data-ttu-id="669c2-217">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="669c2-217">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="669c2-218">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="669c2-218">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="669c2-219">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="669c2-219">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="669c2-220">Move-Item</span><span class="sxs-lookup"><span data-stu-id="669c2-220">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="669c2-221">New-Item</span><span class="sxs-lookup"><span data-stu-id="669c2-221">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="669c2-222">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="669c2-222">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="669c2-223">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="669c2-223">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="669c2-224">Set-Item</span><span class="sxs-lookup"><span data-stu-id="669c2-224">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="669c2-225">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="669c2-225">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="669c2-226">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="669c2-226">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="669c2-227">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="669c2-227">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="669c2-228">about_Providers</span><span class="sxs-lookup"><span data-stu-id="669c2-228">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

