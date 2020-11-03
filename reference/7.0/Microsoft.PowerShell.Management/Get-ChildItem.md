---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ChildItem
ms.openlocfilehash: f8a2276b6121958aedc4eb297d0565b369ee401f
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192769"
---
# <span data-ttu-id="c7673-103">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="c7673-103">Get-ChildItem</span></span>

## <span data-ttu-id="c7673-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c7673-104">SYNOPSIS</span></span>

<span data-ttu-id="c7673-105">Obtém os itens e os itens filhos de um ou mais locais especificados.</span><span class="sxs-lookup"><span data-stu-id="c7673-105">Gets the items and child items in one or more specified locations.</span></span>

## <span data-ttu-id="c7673-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c7673-106">SYNTAX</span></span>

### <span data-ttu-id="c7673-107">Itens (padrão)</span><span class="sxs-lookup"><span data-stu-id="c7673-107">Items (Default)</span></span>

```
Get-ChildItem [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>]
 [-Recurse] [-Depth <uint32>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>]
 [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]
```

### <span data-ttu-id="c7673-108">LiteralItems</span><span class="sxs-lookup"><span data-stu-id="c7673-108">LiteralItems</span></span>

```
Get-ChildItem [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>]
 [-Exclude <string[]>] [-Recurse] [-Depth <uint32>] [-Force] [-Name]
 [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden]
 [-ReadOnly] [-System] [<CommonParameters>]
```

## <span data-ttu-id="c7673-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c7673-109">DESCRIPTION</span></span>

<span data-ttu-id="c7673-110">O `Get-ChildItem` cmdlet obtém os itens em um ou mais locais especificados.</span><span class="sxs-lookup"><span data-stu-id="c7673-110">The `Get-ChildItem` cmdlet gets the items in one or more specified locations.</span></span> <span data-ttu-id="c7673-111">Se o item for um contêiner, ele obtém os itens dentro do contêiner, conhecidos como itens filho.</span><span class="sxs-lookup"><span data-stu-id="c7673-111">If the item is a container, it gets the items inside the container, known as child items.</span></span> <span data-ttu-id="c7673-112">Você pode usar o parâmetro **recurse** para obter itens em todos os contêineres filho e usar o parâmetro **Depth** para limitar o número de níveis para recurse.</span><span class="sxs-lookup"><span data-stu-id="c7673-112">You can use the **Recurse** parameter to get items in all child containers and use the **Depth** parameter to limit the number of levels to recurse.</span></span>

<span data-ttu-id="c7673-113">`Get-ChildItem` não exibe diretórios vazios.</span><span class="sxs-lookup"><span data-stu-id="c7673-113">`Get-ChildItem` doesn't display empty directories.</span></span> <span data-ttu-id="c7673-114">Quando um `Get-ChildItem` comando inclui os parâmetros **Depth** ou **recurse** , os diretórios vazios não são incluídos na saída.</span><span class="sxs-lookup"><span data-stu-id="c7673-114">When a `Get-ChildItem` command includes the **Depth** or **Recurse** parameters, empty directories aren't included in the output.</span></span>

<span data-ttu-id="c7673-115">Os locais são expostos aos `Get-ChildItem` provedores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7673-115">Locations are exposed to `Get-ChildItem` by PowerShell providers.</span></span> <span data-ttu-id="c7673-116">Um local pode ser um diretório do sistema de arquivos, hive do registro ou um repositório de certificados.</span><span class="sxs-lookup"><span data-stu-id="c7673-116">A location can be a file system directory, registry hive, or a certificate store.</span></span> <span data-ttu-id="c7673-117">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="c7673-117">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="c7673-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c7673-118">EXAMPLES</span></span>

### <span data-ttu-id="c7673-119">Exemplo 1: obter itens filho de um diretório do sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="c7673-119">Example 1: Get child items from a file system directory</span></span>

<span data-ttu-id="c7673-120">Este exemplo obtém os itens filho de um diretório do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c7673-120">This example gets the child items from a file system directory.</span></span> <span data-ttu-id="c7673-121">Os nomes de filename e de subdiretório são exibidos.</span><span class="sxs-lookup"><span data-stu-id="c7673-121">The filenames and subdirectory names are displayed.</span></span> <span data-ttu-id="c7673-122">Para locais vazios, o comando não retorna nenhuma saída e retorna ao prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7673-122">For empty locations, the command doesn't return any output and returns to the PowerShell prompt.</span></span>

<span data-ttu-id="c7673-123">O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar o diretório `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="c7673-123">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span>
<span data-ttu-id="c7673-124">`Get-ChildItem` exibe os arquivos e diretórios no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7673-124">`Get-ChildItem` displays the files and directories in the PowerShell console.</span></span>

```powershell
Get-ChildItem -Path C:\Test
```

```Output
   Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     08:29                Logs
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

<span data-ttu-id="c7673-125">Por padrão `Get-ChildItem` , lista o modo **(atributos** ), **LastWriteTime** , tamanho do arquivo ( **comprimento** ) e o **nome** do item.</span><span class="sxs-lookup"><span data-stu-id="c7673-125">By default `Get-ChildItem` lists the mode ( **Attributes** ), **LastWriteTime** , file size ( **Length** ), and the **Name** of the item.</span></span> <span data-ttu-id="c7673-126">As letras na propriedade **modo** podem ser interpretadas da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c7673-126">The letters in the **Mode** property can be interpreted as follows:</span></span>

- <span data-ttu-id="c7673-127">`l` criar</span><span class="sxs-lookup"><span data-stu-id="c7673-127">`l` (link)</span></span>
- <span data-ttu-id="c7673-128">`d` active</span><span class="sxs-lookup"><span data-stu-id="c7673-128">`d` (directory)</span></span>
- <span data-ttu-id="c7673-129">`a` operação</span><span class="sxs-lookup"><span data-stu-id="c7673-129">`a` (archive)</span></span>
- <span data-ttu-id="c7673-130">`r` (somente leitura)</span><span class="sxs-lookup"><span data-stu-id="c7673-130">`r` (read-only)</span></span>
- <span data-ttu-id="c7673-131">`h` oculto</span><span class="sxs-lookup"><span data-stu-id="c7673-131">`h` (hidden)</span></span>
- <span data-ttu-id="c7673-132">`s` (sistema).</span><span class="sxs-lookup"><span data-stu-id="c7673-132">`s` (system).</span></span>

<span data-ttu-id="c7673-133">Para obter mais informações sobre os sinalizadores de modo, consulte [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).</span><span class="sxs-lookup"><span data-stu-id="c7673-133">For more information about the mode flags, see [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).</span></span>

### <span data-ttu-id="c7673-134">Exemplo 2: obter nomes de item filho em um diretório</span><span class="sxs-lookup"><span data-stu-id="c7673-134">Example 2: Get child item names in a directory</span></span>

<span data-ttu-id="c7673-135">Este exemplo lista somente os nomes de itens em um diretório.</span><span class="sxs-lookup"><span data-stu-id="c7673-135">This example lists only the names of items in a directory.</span></span>

<span data-ttu-id="c7673-136">O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar o diretório `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="c7673-136">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span> <span data-ttu-id="c7673-137">O parâmetro **Name** retorna somente os nomes de arquivo ou diretório do caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="c7673-137">The **Name** parameter returns only the file or directory names from the specified path.</span></span>

```powershell
Get-ChildItem -Path C:\Test -Name
```

```Output
Logs
anotherfile.txt
Command.txt
CreateTestFile.ps1
ReadOnlyFile.txt
```

### <span data-ttu-id="c7673-138">Exemplo 3: obter itens filho no diretório e nos subdiretórios atuais</span><span class="sxs-lookup"><span data-stu-id="c7673-138">Example 3: Get child items in the current directory and subdirectories</span></span>

<span data-ttu-id="c7673-139">Este exemplo exibe os arquivos **. txt** que estão localizados no diretório atual e seus subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="c7673-139">This example displays **.txt** files that are located in the current directory and its subdirectories.</span></span>

```powershell
Get-ChildItem -Path C:\Test\*.txt -Recurse -Force
```

```Output
    Directory: C:\Test\Logs\Adirectory

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile4.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile4.txt

    Directory: C:\Test\Logs\Backup

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 ATextFile.txt
-a----        2/12/2019     15:50             20 LogFile3.txt

    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

<span data-ttu-id="c7673-140">O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar `C:\Test\*.txt` .</span><span class="sxs-lookup"><span data-stu-id="c7673-140">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify `C:\Test\*.txt`.</span></span> <span data-ttu-id="c7673-141">O **caminho** usa o curinga asterisco ( `*` ) para especificar todos os arquivos com a extensão de nome de arquivo `.txt` .</span><span class="sxs-lookup"><span data-stu-id="c7673-141">**Path** uses the asterisk (`*`) wildcard to specify all files with the filename extension `.txt`.</span></span> <span data-ttu-id="c7673-142">O parâmetro **recurse** pesquisa o diretório **Path** em seus subdiretórios, conforme mostrado no **diretório:** cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="c7673-142">The **Recurse** parameter searches the **Path** directory its subdirectories, as shown in the **Directory:** headings.</span></span> <span data-ttu-id="c7673-143">O parâmetro **Force** exibe arquivos ocultos, como `hiddenfile.txt` que têm um modo de **h** .</span><span class="sxs-lookup"><span data-stu-id="c7673-143">The **Force** parameter displays hidden files such as `hiddenfile.txt` that have a mode of **h** .</span></span>

### <span data-ttu-id="c7673-144">Exemplo 4: obter itens filho usando o parâmetro include</span><span class="sxs-lookup"><span data-stu-id="c7673-144">Example 4: Get child items using the Include parameter</span></span>

<span data-ttu-id="c7673-145">Neste exemplo `Get-ChildItem` , usa o parâmetro **include** para localizar itens específicos do diretório especificado pelo parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="c7673-145">In this example `Get-ChildItem` uses the **Include** parameter to find specific items from the directory specified by the **Path** parameter.</span></span>

```powershell
# When using the -Include parameter, if you don't include an asterisk in the path
# the command returns no output.
Get-ChildItem -Path C:\Test\ -Include *.txt
```

```Output

```

```powershell
Get-ChildItem -Path C:\Test\* -Include *.txt
```

```Output
    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

<span data-ttu-id="c7673-146">O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar o diretório **C:\test** .</span><span class="sxs-lookup"><span data-stu-id="c7673-146">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory **C:\Test** .</span></span> <span data-ttu-id="c7673-147">O parâmetro **path** inclui um curinga asterisco ( `*` ) à direita para especificar o conteúdo do diretório.</span><span class="sxs-lookup"><span data-stu-id="c7673-147">The **Path** parameter includes a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span>
<span data-ttu-id="c7673-148">O parâmetro **include** usa um curinga asterisco ( `*` ) para especificar todos os arquivos com a extensão de nome de arquivo **. txt** .</span><span class="sxs-lookup"><span data-stu-id="c7673-148">The **Include** parameter uses an asterisk (`*`) wildcard to specify all files with the file name extension **.txt** .</span></span>

<span data-ttu-id="c7673-149">Quando o parâmetro **include** é usado, o parâmetro **Path** precisa de um curinga asterisco ( `*` ) à direita para especificar o conteúdo do diretório.</span><span class="sxs-lookup"><span data-stu-id="c7673-149">When the **Include** parameter is used, the **Path** parameter needs a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span> <span data-ttu-id="c7673-150">Por exemplo, `-Path C:\Test\*`.</span><span class="sxs-lookup"><span data-stu-id="c7673-150">For example, `-Path C:\Test\*`.</span></span>

- <span data-ttu-id="c7673-151">Se o parâmetro **recurse** for adicionado ao comando, o asterisco à direita ( `*` ) no parâmetro **Path** será opcional.</span><span class="sxs-lookup"><span data-stu-id="c7673-151">If the **Recurse** parameter is added to the command, the trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="c7673-152">O parâmetro **recurse** Obtém os itens do diretório **Path** e seus subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="c7673-152">The **Recurse** parameter gets items from the **Path** directory and its subdirectories.</span></span> <span data-ttu-id="c7673-153">Por exemplo, `-Path C:\Test\ -Recurse -Include *.txt`</span><span class="sxs-lookup"><span data-stu-id="c7673-153">For example, `-Path C:\Test\ -Recurse -Include *.txt`</span></span>
- <span data-ttu-id="c7673-154">Se um asterisco à direita ( `*` ) não estiver incluído no parâmetro **Path** , o comando não retornará nenhuma saída e retornará ao prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7673-154">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the command doesn't return any output and returns to the PowerShell prompt.</span></span> <span data-ttu-id="c7673-155">Por exemplo, `-Path C:\Test\`.</span><span class="sxs-lookup"><span data-stu-id="c7673-155">For example, `-Path C:\Test\`.</span></span>

### <span data-ttu-id="c7673-156">Exemplo 5: obter itens filhos usando o parâmetro Exclude</span><span class="sxs-lookup"><span data-stu-id="c7673-156">Example 5: Get child items using the Exclude parameter</span></span>

<span data-ttu-id="c7673-157">A saída do exemplo mostra o conteúdo do diretório **C:\Test\Logs** .</span><span class="sxs-lookup"><span data-stu-id="c7673-157">The example's output shows the contents of the directory **C:\Test\Logs** .</span></span> <span data-ttu-id="c7673-158">A saída é uma referência para os outros comandos que usam os parâmetros **Exclude** e **recurse** .</span><span class="sxs-lookup"><span data-stu-id="c7673-158">The output is a reference for the other commands that use the **Exclude** and **Recurse** parameters.</span></span>

```powershell
Get-ChildItem -Path C:\Test\Logs
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Adirectory
d-----        2/15/2019     08:28                AnEmptyDirectory
d-----        2/15/2019     13:21                Backup
-a----        2/12/2019     16:16             20 Afile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

```powershell
Get-ChildItem -Path C:\Test\Logs\* -Exclude A*
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Backup
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

<span data-ttu-id="c7673-159">O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar o diretório `C:\Test\Logs` .</span><span class="sxs-lookup"><span data-stu-id="c7673-159">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test\Logs`.</span></span>
<span data-ttu-id="c7673-160">O parâmetro **Exclude** usa o curinga asterisco ( `*` ) para especificar os arquivos ou diretórios que começam com **um** ou **um** são excluídos da saída.</span><span class="sxs-lookup"><span data-stu-id="c7673-160">The **Exclude** parameter uses the asterisk (`*`) wildcard to specify any files or directories that begin with **A** or **a** are excluded from the output.</span></span>

<span data-ttu-id="c7673-161">Quando o parâmetro **Exclude** é usado, um asterisco à direita ( `*` ) no parâmetro **Path** é opcional.</span><span class="sxs-lookup"><span data-stu-id="c7673-161">When the **Exclude** parameter is used, a trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="c7673-162">Por exemplo, `-Path C:\Test\Logs` ou `-Path C:\Test\Logs\*`.</span><span class="sxs-lookup"><span data-stu-id="c7673-162">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span>

- <span data-ttu-id="c7673-163">Se um asterisco à direita ( `*` ) não estiver incluído no parâmetro **Path** , o conteúdo do parâmetro **Path** será exibido.</span><span class="sxs-lookup"><span data-stu-id="c7673-163">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="c7673-164">As exceções são nomes de filename ou subdiretórios que correspondem ao valor do parâmetro **Exclude** .</span><span class="sxs-lookup"><span data-stu-id="c7673-164">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="c7673-165">Se um asterisco à direita ( `*` ) estiver incluído no parâmetro **Path** , o comando recursivamente nos subdiretórios do parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="c7673-165">If a trailing asterisk (`*`) is included in the **Path** parameter, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="c7673-166">As exceções são nomes de filename ou subdiretórios que correspondem ao valor do parâmetro **Exclude** .</span><span class="sxs-lookup"><span data-stu-id="c7673-166">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="c7673-167">Se o parâmetro **recurse** for adicionado ao comando, a saída de recursão será a mesma se o parâmetro **Path** incluir um asterisco à direita ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="c7673-167">If the **Recurse** parameter is added to the command, the recursion output is the same whether or not the **Path** parameter includes a trailing asterisk (`*`).</span></span>

### <span data-ttu-id="c7673-168">Exemplo 6: obter as chaves do registro de um hive do registro</span><span class="sxs-lookup"><span data-stu-id="c7673-168">Example 6: Get the registry keys from a registry hive</span></span>

<span data-ttu-id="c7673-169">Este exemplo obtém todas as chaves do registro de `HKEY_LOCAL_MACHINE\HARDWARE` .</span><span class="sxs-lookup"><span data-stu-id="c7673-169">This example gets all the registry keys from `HKEY_LOCAL_MACHINE\HARDWARE`.</span></span>

<span data-ttu-id="c7673-170">`Get-ChildItem` usa o parâmetro **path** para especificar a chave do registro `HKLM:\HARDWARE` .</span><span class="sxs-lookup"><span data-stu-id="c7673-170">`Get-ChildItem` uses the **Path** parameter to specify the registry key `HKLM:\HARDWARE`.</span></span> <span data-ttu-id="c7673-171">O caminho do hive e o nível superior das chaves do registro são exibidos no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7673-171">The hive's path and top level of registry keys are displayed in the PowerShell console.</span></span>

<span data-ttu-id="c7673-172">Para obter mais informações, consulte [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="c7673-172">For more information, see [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).</span></span>

```powershell
Get-ChildItem -Path HKLM:\HARDWARE
```

```Output
    Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name             Property
----             --------
ACPI
DESCRIPTION
DEVICEMAP
RESOURCEMAP
UEFI
```

```powershell
Get-ChildItem -Path HKLM:\HARDWARE -Exclude D*
```

```Output
   Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name                           Property
----                           --------
ACPI
RESOURCEMAP
```

<span data-ttu-id="c7673-173">O primeiro comando mostra o conteúdo da `HKLM:\HARDWARE` chave do registro.</span><span class="sxs-lookup"><span data-stu-id="c7673-173">The first command shows the contents of the `HKLM:\HARDWARE` registry key.</span></span> <span data-ttu-id="c7673-174">O parâmetro **Exclude** informa `Get-ChildItem` para não retornar nenhuma subchave que comece com `D*` .</span><span class="sxs-lookup"><span data-stu-id="c7673-174">The **Exclude** parameter tells `Get-ChildItem` not to return any subkeys that start with `D*`.</span></span> <span data-ttu-id="c7673-175">Atualmente, o parâmetro **Exclude** só funciona em subchaves, não em Propriedades de item.</span><span class="sxs-lookup"><span data-stu-id="c7673-175">Currently, the **Exclude** parameter only works on subkeys, not item properties.</span></span>

### <span data-ttu-id="c7673-176">Exemplo 7: obter todos os certificados com autoridade de assinatura de código</span><span class="sxs-lookup"><span data-stu-id="c7673-176">Example 7: Get all certificates with code-signing authority</span></span>

<span data-ttu-id="c7673-177">Este exemplo obtém cada certificado na unidade de **certificado** do PowerShell: que tem autoridade de assinatura de código.</span><span class="sxs-lookup"><span data-stu-id="c7673-177">This example gets each certificate in the PowerShell **Cert:** drive that has code-signing authority.</span></span>

<span data-ttu-id="c7673-178">O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar o **CERT:** Provider.</span><span class="sxs-lookup"><span data-stu-id="c7673-178">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the **Cert:** provider.</span></span> <span data-ttu-id="c7673-179">O parâmetro **recurse** pesquisa o diretório especificado por **Path** e seus subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="c7673-179">The **Recurse** parameter searches the directory specified by **Path** and its subdirectories.</span></span> <span data-ttu-id="c7673-180">O parâmetro **CodeSigningCert** obtém somente os certificados que têm autoridade de assinatura de código.</span><span class="sxs-lookup"><span data-stu-id="c7673-180">The **CodeSigningCert** parameter gets only certificates that have code-signing authority.</span></span>

```powershell
Get-ChildItem -Path Cert:\* -Recurse -CodeSigningCert
```

<span data-ttu-id="c7673-181">Para obter mais informações sobre o provedor de certificado e a unidade CERT:, consulte [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="c7673-181">For more information about the Certificate provider and the Cert: drive, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="c7673-182">Exemplo 8: obter itens usando o parâmetro Depth</span><span class="sxs-lookup"><span data-stu-id="c7673-182">Example 8: Get items using the Depth parameter</span></span>

<span data-ttu-id="c7673-183">Este exemplo exibe os itens em um diretório e seus subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="c7673-183">This example displays the items in a directory and its subdirectories.</span></span> <span data-ttu-id="c7673-184">O parâmetro **Depth** determina o número de níveis de subdiretório a serem incluídos na recursão.</span><span class="sxs-lookup"><span data-stu-id="c7673-184">The **Depth** parameter determines the number of subdirectory levels to include in the recursion.</span></span> <span data-ttu-id="c7673-185">Diretórios vazios são excluídos da saída.</span><span class="sxs-lookup"><span data-stu-id="c7673-185">Empty directories are excluded from the output.</span></span>

```powershell
Get-ChildItem -Path C:\Parent -Depth 2
```

```Output
    Directory: C:\Parent

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level1
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level2
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1\SubDir_Level2

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:22                SubDir_Level3
-a----        2/13/2019     08:55             26 file.txt
```

<span data-ttu-id="c7673-186">O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar **C:\Parent** .</span><span class="sxs-lookup"><span data-stu-id="c7673-186">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify **C:\Parent** .</span></span> <span data-ttu-id="c7673-187">O parâmetro **Depth** especifica dois níveis de recursão.</span><span class="sxs-lookup"><span data-stu-id="c7673-187">The **Depth** parameter specifies two levels of recursion.</span></span> <span data-ttu-id="c7673-188">`Get-ChildItem` exibe o conteúdo do diretório especificado pelo parâmetro **path** e os dois níveis de subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="c7673-188">`Get-ChildItem` displays the contents of the directory specified by the **Path** parameter and the two levels of subdirectories.</span></span>

### <span data-ttu-id="c7673-189">Exemplo 9: obtendo informações de vínculo físico</span><span class="sxs-lookup"><span data-stu-id="c7673-189">Example 9: Getting hard link information</span></span>

<span data-ttu-id="c7673-190">No PowerShell 6,2, uma exibição alternativa foi adicionada para obter informações de link físico.</span><span class="sxs-lookup"><span data-stu-id="c7673-190">In PowerShell 6.2, an alternate view was added to get hard link information.</span></span>

```powershell
Get-ChildItem -Path C:\PathContainingHardLink | Format-Table -View childrenWithHardLink
```

### <span data-ttu-id="c7673-191">Exemplo 9: saída para o recurso experimental PSUnixFileStat</span><span class="sxs-lookup"><span data-stu-id="c7673-191">Example 9: Output for experimental feature PSUnixFileStat</span></span>

<span data-ttu-id="c7673-192">No PowerShell 7 em sistemas UNIX, o recurso experimental **PSUnixFileStat** fornece saída do tipo UNIX:</span><span class="sxs-lookup"><span data-stu-id="c7673-192">In PowerShell 7 on Unix systems, the experimental feature **PSUnixFileStat** provides Unix-like output:</span></span>

```powershell
PS> Get-ChildItem /etc/r*
```

```Output
    Directory: /etc

UnixMode   User Group    LastWriteTime Size Name
--------   ---- -----    ------------- ---- ----
drwxr-xr-x root wheel  9/30/2019 19:19  128 racoon
-rw-r--r-- root wheel  9/26/2019 18:20 1560 rc.common
-rw-r--r-- root wheel  7/31/2017 17:30 1560 rc.common~previous
-rw-r--r-- root wheel  9/27/2019 20:34 5264 rc.netboot
lrwxr-xr-x root wheel  11/8/2019 15:35   22 resolv.conf -> /private/var/run/resolv.conf
-rw-r--r-- root wheel 10/23/2019 17:41    0 rmtab
-rw-r--r-- root wheel 10/23/2019 17:41 1735 rpc
-rw-r--r-- root wheel  7/25/2017 18:37 1735 rpc~previous
-rw-r--r-- root wheel 10/23/2019 18:42  891 rtadvd.conf
-rw-r--r-- root wheel  8/24/2017 21:54  891 rtadvd.conf~previous
```

<span data-ttu-id="c7673-193">As novas propriedades que agora fazem parte da saída são:</span><span class="sxs-lookup"><span data-stu-id="c7673-193">The new properties that are now part of the output are:</span></span>

- <span data-ttu-id="c7673-194">**Unixmode** são as permissões de arquivo, conforme representado em um sistema UNIX</span><span class="sxs-lookup"><span data-stu-id="c7673-194">**UnixMode** is the file permissions as represented on a Unix system</span></span>
- <span data-ttu-id="c7673-195">O **usuário** é o proprietário do arquivo</span><span class="sxs-lookup"><span data-stu-id="c7673-195">**User** is the file owner</span></span>
- <span data-ttu-id="c7673-196">O **grupo** é o proprietário do grupo</span><span class="sxs-lookup"><span data-stu-id="c7673-196">**Group** is the group owner</span></span>
- <span data-ttu-id="c7673-197">**Tamanho** é o tamanho do arquivo ou diretório, conforme representado em um sistema UNIX</span><span class="sxs-lookup"><span data-stu-id="c7673-197">**Size** is the size of the file or directory as represented on a Unix system</span></span>

## <span data-ttu-id="c7673-198">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c7673-198">Parameters</span></span>

### <span data-ttu-id="c7673-199">-Atributos</span><span class="sxs-lookup"><span data-stu-id="c7673-199">-Attributes</span></span>

<span data-ttu-id="c7673-200">Obtém os arquivos e pastas com os atributos especificados.</span><span class="sxs-lookup"><span data-stu-id="c7673-200">Gets files and folders with the specified attributes.</span></span> <span data-ttu-id="c7673-201">Esse parâmetro dá suporte a todos os atributos e permite que você especifique combinações complexas de atributos.</span><span class="sxs-lookup"><span data-stu-id="c7673-201">This parameter supports all attributes and lets you specify complex combinations of attributes.</span></span>

<span data-ttu-id="c7673-202">Por exemplo, para obter arquivos de fora do sistema (não diretórios) que sejam criptografados ou compactados, digite:</span><span class="sxs-lookup"><span data-stu-id="c7673-202">For example, to get non-system files (not directories) that are encrypted or compressed, type:</span></span>

`Get-ChildItem -Attributes !Directory+!System+Encrypted, !Directory+!System+Compressed`

<span data-ttu-id="c7673-203">Para localizar arquivos e pastas com atributos comumente usados, use o parâmetro **Attributes** .</span><span class="sxs-lookup"><span data-stu-id="c7673-203">To find files and folders with commonly used attributes, use the **Attributes** parameter.</span></span> <span data-ttu-id="c7673-204">Ou, o **diretório** de parâmetros, **arquivo** , **oculto** , **ReadOnly** e **System** .</span><span class="sxs-lookup"><span data-stu-id="c7673-204">Or, the parameters **Directory** , **File** , **Hidden** , **ReadOnly** , and **System** .</span></span>

<span data-ttu-id="c7673-205">O parâmetro **Attributes** dá suporte às seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="c7673-205">The **Attributes** parameter supports the following properties:</span></span>

- <span data-ttu-id="c7673-206">**Arquivar**</span><span class="sxs-lookup"><span data-stu-id="c7673-206">**Archive**</span></span>
- <span data-ttu-id="c7673-207">**Compactado**</span><span class="sxs-lookup"><span data-stu-id="c7673-207">**Compressed**</span></span>
- <span data-ttu-id="c7673-208">**Dispositivo**</span><span class="sxs-lookup"><span data-stu-id="c7673-208">**Device**</span></span>
- <span data-ttu-id="c7673-209">**Diretório**</span><span class="sxs-lookup"><span data-stu-id="c7673-209">**Directory**</span></span>
- <span data-ttu-id="c7673-210">**Criptografado**</span><span class="sxs-lookup"><span data-stu-id="c7673-210">**Encrypted**</span></span>
- <span data-ttu-id="c7673-211">**Oculto**</span><span class="sxs-lookup"><span data-stu-id="c7673-211">**Hidden**</span></span>
- <span data-ttu-id="c7673-212">**IntegrityStream**</span><span class="sxs-lookup"><span data-stu-id="c7673-212">**IntegrityStream**</span></span>
- <span data-ttu-id="c7673-213">**Normal**</span><span class="sxs-lookup"><span data-stu-id="c7673-213">**Normal**</span></span>
- <span data-ttu-id="c7673-214">**NoScrubData**</span><span class="sxs-lookup"><span data-stu-id="c7673-214">**NoScrubData**</span></span>
- <span data-ttu-id="c7673-215">**NotContentIndexed**</span><span class="sxs-lookup"><span data-stu-id="c7673-215">**NotContentIndexed**</span></span>
- <span data-ttu-id="c7673-216">**Está**</span><span class="sxs-lookup"><span data-stu-id="c7673-216">**Offline**</span></span>
- <span data-ttu-id="c7673-217">**ReadOnly (somente-leitura)**</span><span class="sxs-lookup"><span data-stu-id="c7673-217">**ReadOnly**</span></span>
- <span data-ttu-id="c7673-218">**ReparsePoint**</span><span class="sxs-lookup"><span data-stu-id="c7673-218">**ReparsePoint**</span></span>
- <span data-ttu-id="c7673-219">**Escassfile**</span><span class="sxs-lookup"><span data-stu-id="c7673-219">**SparseFile**</span></span>
- <span data-ttu-id="c7673-220">**Sistema**</span><span class="sxs-lookup"><span data-stu-id="c7673-220">**System**</span></span>
- <span data-ttu-id="c7673-221">**Temporário**</span><span class="sxs-lookup"><span data-stu-id="c7673-221">**Temporary**</span></span>

<span data-ttu-id="c7673-222">Para obter uma descrição desses atributos, consulte a [enumeração FileAttributes](/dotnet/api/system.io.fileattributes).</span><span class="sxs-lookup"><span data-stu-id="c7673-222">For a description of these attributes, see the [FileAttributes Enumeration](/dotnet/api/system.io.fileattributes).</span></span>

<span data-ttu-id="c7673-223">Para combinar atributos, use os seguintes operadores:</span><span class="sxs-lookup"><span data-stu-id="c7673-223">To combine attributes, use the following operators:</span></span>

- <span data-ttu-id="c7673-224">`!` VÁLIDO</span><span class="sxs-lookup"><span data-stu-id="c7673-224">`!` (NOT)</span></span>
- <span data-ttu-id="c7673-225">`+` E</span><span class="sxs-lookup"><span data-stu-id="c7673-225">`+` (AND)</span></span>
- <span data-ttu-id="c7673-226">`,` OR</span><span class="sxs-lookup"><span data-stu-id="c7673-226">`,` (OR)</span></span>

<span data-ttu-id="c7673-227">Não use espaços entre um operador e seu atributo.</span><span class="sxs-lookup"><span data-stu-id="c7673-227">Don't use spaces between an operator and its attribute.</span></span> <span data-ttu-id="c7673-228">Os espaços são aceitos após vírgulas.</span><span class="sxs-lookup"><span data-stu-id="c7673-228">Spaces are accepted after commas.</span></span>

<span data-ttu-id="c7673-229">Para atributos comuns, use as seguintes abreviações:</span><span class="sxs-lookup"><span data-stu-id="c7673-229">For common attributes, use the following abbreviations:</span></span>

- <span data-ttu-id="c7673-230">`D` Active</span><span class="sxs-lookup"><span data-stu-id="c7673-230">`D` (Directory)</span></span>
- <span data-ttu-id="c7673-231">`H` Oculto</span><span class="sxs-lookup"><span data-stu-id="c7673-231">`H` (Hidden)</span></span>
- <span data-ttu-id="c7673-232">`R` (Somente leitura)</span><span class="sxs-lookup"><span data-stu-id="c7673-232">`R` (Read-only)</span></span>
- <span data-ttu-id="c7673-233">`S` Sistema</span><span class="sxs-lookup"><span data-stu-id="c7673-233">`S` (System)</span></span>

```yaml
Type: System.Management.Automation.FlagsExpression`1[System.IO.FileAttributes]
Parameter Sets: (All)
Aliases:
Accepted values: Archive, Compressed, Device, Directory, Encrypted, Hidden, IntegrityStream, Normal, NoScrubData, NotContentIndexed, Offline, ReadOnly, ReparsePoint, SparseFile, System, Temporary

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7673-234">-Profundidade</span><span class="sxs-lookup"><span data-stu-id="c7673-234">-Depth</span></span>

<span data-ttu-id="c7673-235">Esse parâmetro foi adicionado no PowerShell 5,0 e permite que você controle a profundidade da recursão.</span><span class="sxs-lookup"><span data-stu-id="c7673-235">This parameter was added in PowerShell 5.0 and enables you to control the depth of recursion.</span></span> <span data-ttu-id="c7673-236">Por padrão, `Get-ChildItem` o exibe o conteúdo do diretório pai.</span><span class="sxs-lookup"><span data-stu-id="c7673-236">By default, `Get-ChildItem` displays the contents of the parent directory.</span></span> <span data-ttu-id="c7673-237">O parâmetro **Depth** determina o número de níveis de subdiretório que são incluídos na recursão e exibe o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c7673-237">The **Depth** parameter determines the number of subdirectory levels that are included in the recursion and displays the contents.</span></span>

<span data-ttu-id="c7673-238">Por exemplo, `Depth 2` inclui o diretório do parâmetro de **caminho** , o primeiro nível de subdiretórios e o segundo nível de subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="c7673-238">For example, `Depth 2` includes the **Path** parameter's directory, first level of subdirectories, and second level of subdirectories.</span></span> <span data-ttu-id="c7673-239">Por padrão, os nomes do diretório e os nomes de FileName são incluídos na saída.</span><span class="sxs-lookup"><span data-stu-id="c7673-239">By default directory names and filenames are included in the output.</span></span>

> [!NOTE]
> <span data-ttu-id="c7673-240">Em um computador Windows do PowerShell ou **cmd.exe** , você pode exibir uma exibição gráfica de uma estrutura de diretório com o comando **Tree.com** .</span><span class="sxs-lookup"><span data-stu-id="c7673-240">On a Windows computer from PowerShell or **cmd.exe** , you can display a graphical view of a directory structure with the **tree.com** command.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7673-241">-Directory</span><span class="sxs-lookup"><span data-stu-id="c7673-241">-Directory</span></span>

<span data-ttu-id="c7673-242">Para obter uma lista de diretórios, use o parâmetro **Directory** ou o parâmetro **Attributes** com a propriedade **Directory** .</span><span class="sxs-lookup"><span data-stu-id="c7673-242">To get a list of directories, use the **Directory** parameter or the **Attributes** parameter with the **Directory** property.</span></span> <span data-ttu-id="c7673-243">Você pode usar o parâmetro **recurse** com o **diretório** .</span><span class="sxs-lookup"><span data-stu-id="c7673-243">You can use the **Recurse** parameter with **Directory** .</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ad, d

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7673-244">-Excluir</span><span class="sxs-lookup"><span data-stu-id="c7673-244">-Exclude</span></span>

<span data-ttu-id="c7673-245">Especifica, como uma matriz de cadeia de caracteres, uma propriedade ou propriedade que esse cmdlet exclui da operação.</span><span class="sxs-lookup"><span data-stu-id="c7673-245">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="c7673-246">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="c7673-246">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c7673-247">Insira um elemento ou padrão de caminho, como `*.txt` ou `A*` .</span><span class="sxs-lookup"><span data-stu-id="c7673-247">Enter a path element or pattern, such as `*.txt` or `A*`.</span></span> <span data-ttu-id="c7673-248">Caracteres curinga são aceitos.</span><span class="sxs-lookup"><span data-stu-id="c7673-248">Wildcard characters are accepted.</span></span>

<span data-ttu-id="c7673-249">Um asterisco à direita ( `*` ) no parâmetro **Path** é opcional.</span><span class="sxs-lookup"><span data-stu-id="c7673-249">A trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="c7673-250">Por exemplo, `-Path C:\Test\Logs` ou `-Path C:\Test\Logs\*`.</span><span class="sxs-lookup"><span data-stu-id="c7673-250">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span> <span data-ttu-id="c7673-251">Se um asterisco à direita ( `*` ) for incluído, o comando recursivamente nos subdiretórios do parâmetro de **caminho** .</span><span class="sxs-lookup"><span data-stu-id="c7673-251">If a trailing asterisk (`*`) is included, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="c7673-252">Sem o asterisco ( `*` ), o conteúdo do parâmetro **Path** é exibido.</span><span class="sxs-lookup"><span data-stu-id="c7673-252">Without the asterisk (`*`), the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="c7673-253">Mais detalhes são incluídos no exemplo 5 e na seção observações.</span><span class="sxs-lookup"><span data-stu-id="c7673-253">More details are included in Example 5 and the Notes section.</span></span>

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

### <span data-ttu-id="c7673-254">-File</span><span class="sxs-lookup"><span data-stu-id="c7673-254">-File</span></span>

<span data-ttu-id="c7673-255">Para obter uma lista de arquivos, use o parâmetro **File** .</span><span class="sxs-lookup"><span data-stu-id="c7673-255">To get a list of files, use the **File** parameter.</span></span> <span data-ttu-id="c7673-256">Você pode usar o parâmetro **recurse** com o **arquivo** .</span><span class="sxs-lookup"><span data-stu-id="c7673-256">You can use the **Recurse** parameter with **File** .</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: af

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7673-257">-Filter</span><span class="sxs-lookup"><span data-stu-id="c7673-257">-Filter</span></span>

<span data-ttu-id="c7673-258">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="c7673-258">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="c7673-259">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte a filtros.</span><span class="sxs-lookup"><span data-stu-id="c7673-259">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="c7673-260">Os filtros são mais eficientes do que outros parâmetros.</span><span class="sxs-lookup"><span data-stu-id="c7673-260">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="c7673-261">O provedor aplica-se ao filtro quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="c7673-261">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="c7673-262">A cadeia de caracteres de filtro é passada para a API do .NET para enumerar arquivos.</span><span class="sxs-lookup"><span data-stu-id="c7673-262">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="c7673-263">A API só dá suporte a `*` `?` caracteres curinga e.</span><span class="sxs-lookup"><span data-stu-id="c7673-263">The API only supports `*` and `?` wildcards.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c7673-264">-FollowSymlink</span><span class="sxs-lookup"><span data-stu-id="c7673-264">-FollowSymlink</span></span>

<span data-ttu-id="c7673-265">Por padrão, o `Get-ChildItem` cmdlet exibe links simbólicos para diretórios encontrados durante a recursão, mas não os recursiva.</span><span class="sxs-lookup"><span data-stu-id="c7673-265">By default, the `Get-ChildItem` cmdlet displays symbolic links to directories found during recursion, but doesn't recurse into them.</span></span> <span data-ttu-id="c7673-266">Use o parâmetro **FollowSymlink** para pesquisar os diretórios direcionados a esses links simbólicos.</span><span class="sxs-lookup"><span data-stu-id="c7673-266">Use the **FollowSymlink** parameter to search the directories that target those symbolic links.</span></span> <span data-ttu-id="c7673-267">O **FollowSymlink** é um parâmetro dinâmico e só tem suporte no provedor **FileSystem** .</span><span class="sxs-lookup"><span data-stu-id="c7673-267">The **FollowSymlink** is a dynamic parameter and is supported only in the **FileSystem** provider.</span></span>

<span data-ttu-id="c7673-268">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="c7673-268">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="c7673-269">-Force</span><span class="sxs-lookup"><span data-stu-id="c7673-269">-Force</span></span>

<span data-ttu-id="c7673-270">Permite que o cmdlet obtenha itens que, de outra forma, não podem ser acessados pelo usuário, como arquivos ocultos ou do sistema.</span><span class="sxs-lookup"><span data-stu-id="c7673-270">Allows the cmdlet to get items that otherwise can't be accessed by the user, such as hidden or system files.</span></span> <span data-ttu-id="c7673-271">O parâmetro **Force** não substitui as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="c7673-271">The **Force** parameter doesn't override security restrictions.</span></span> <span data-ttu-id="c7673-272">A implementação varia entre os provedores.</span><span class="sxs-lookup"><span data-stu-id="c7673-272">Implementation varies among providers.</span></span> <span data-ttu-id="c7673-273">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="c7673-273">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="c7673-274">-Hidden</span><span class="sxs-lookup"><span data-stu-id="c7673-274">-Hidden</span></span>

<span data-ttu-id="c7673-275">Para obter apenas itens ocultos, use o parâmetro **Hidden** ou o parâmetro **Attributes** com a propriedade **Hidden** .</span><span class="sxs-lookup"><span data-stu-id="c7673-275">To get only hidden items, use the **Hidden** parameter or the **Attributes** parameter with the **Hidden** property.</span></span> <span data-ttu-id="c7673-276">Por padrão, o `Get-ChildItem` não exibe itens ocultos.</span><span class="sxs-lookup"><span data-stu-id="c7673-276">By default, `Get-ChildItem` doesn't display hidden items.</span></span> <span data-ttu-id="c7673-277">Use o parâmetro **Force** para obter itens ocultos.</span><span class="sxs-lookup"><span data-stu-id="c7673-277">Use the **Force** parameter to get hidden items.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ah, h

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7673-278">-Incluir</span><span class="sxs-lookup"><span data-stu-id="c7673-278">-Include</span></span>

<span data-ttu-id="c7673-279">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="c7673-279">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="c7673-280">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="c7673-280">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c7673-281">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="c7673-281">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="c7673-282">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c7673-282">Wildcard characters are permitted.</span></span> <span data-ttu-id="c7673-283">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="c7673-283">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="c7673-284">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c7673-284">-LiteralPath</span></span>

<span data-ttu-id="c7673-285">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="c7673-285">Specifies a path to one or more locations.</span></span> <span data-ttu-id="c7673-286">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="c7673-286">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="c7673-287">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="c7673-287">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="c7673-288">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="c7673-288">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="c7673-289">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="c7673-289">Single quotation marks tell PowerShell to not interpret any characters as escape sequences.</span></span>

<span data-ttu-id="c7673-290">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="c7673-290">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralItems
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c7673-291">-Name</span><span class="sxs-lookup"><span data-stu-id="c7673-291">-Name</span></span>

<span data-ttu-id="c7673-292">Obtém somente os nomes dos itens no local.</span><span class="sxs-lookup"><span data-stu-id="c7673-292">Gets only the names of the items in the location.</span></span> <span data-ttu-id="c7673-293">A saída é um objeto de cadeia de caracteres que pode ser enviado ao pipeline para outros comandos.</span><span class="sxs-lookup"><span data-stu-id="c7673-293">The output is a string object that can be sent down the pipeline to other commands.</span></span> <span data-ttu-id="c7673-294">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c7673-294">Wildcards are permitted.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c7673-295">-Path</span><span class="sxs-lookup"><span data-stu-id="c7673-295">-Path</span></span>

<span data-ttu-id="c7673-296">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="c7673-296">Specifies a path to one or more locations.</span></span> <span data-ttu-id="c7673-297">Caracteres curinga são aceitos.</span><span class="sxs-lookup"><span data-stu-id="c7673-297">Wildcards are accepted.</span></span> <span data-ttu-id="c7673-298">O local padrão é o diretório atual ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="c7673-298">The default location is the current directory (`.`).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Items
Aliases:

Required: False
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="c7673-299">-ReadOnly</span><span class="sxs-lookup"><span data-stu-id="c7673-299">-ReadOnly</span></span>

<span data-ttu-id="c7673-300">Para obter somente itens somente leitura, use o parâmetro **ReadOnly** ou a propriedade **ReadOnly** do parâmetro **Attributes** .</span><span class="sxs-lookup"><span data-stu-id="c7673-300">To get only read-only items, use the **ReadOnly** parameter or the **Attributes** parameter **ReadOnly** property.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ar

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7673-301">-Recurse</span><span class="sxs-lookup"><span data-stu-id="c7673-301">-Recurse</span></span>

<span data-ttu-id="c7673-302">Obtém os itens nos locais especificados e em todos os itens filhos dos locais.</span><span class="sxs-lookup"><span data-stu-id="c7673-302">Gets the items in the specified locations and in all child items of the locations.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: s

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7673-303">-System</span><span class="sxs-lookup"><span data-stu-id="c7673-303">-System</span></span>

<span data-ttu-id="c7673-304">Obtém somente os arquivos e diretórios do sistema.</span><span class="sxs-lookup"><span data-stu-id="c7673-304">Gets only system files and directories.</span></span> <span data-ttu-id="c7673-305">Para obter apenas arquivos e pastas do sistema, use o parâmetro do **sistema** ou a propriedade do **sistema** de parâmetros de **atributos** .</span><span class="sxs-lookup"><span data-stu-id="c7673-305">To get only system files and folders, use the **System** parameter or **Attributes** parameter **System** property.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: as

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7673-306">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c7673-306">CommonParameters</span></span>

<span data-ttu-id="c7673-307">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c7673-307">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c7673-308">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c7673-308">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c7673-309">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c7673-309">INPUTS</span></span>

### <span data-ttu-id="c7673-310">System.String</span><span class="sxs-lookup"><span data-stu-id="c7673-310">System.String</span></span>

<span data-ttu-id="c7673-311">É possível canalizar uma cadeia de caracteres que contém um caminho para `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="c7673-311">You can pipe a string that contains a path to `Get-ChildItem`.</span></span>

## <span data-ttu-id="c7673-312">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c7673-312">OUTPUTS</span></span>

### <span data-ttu-id="c7673-313">System.Object</span><span class="sxs-lookup"><span data-stu-id="c7673-313">System.Object</span></span>

<span data-ttu-id="c7673-314">O tipo de objeto que `Get-ChildItem` retorna é determinado pelos objetos no caminho da unidade do provedor.</span><span class="sxs-lookup"><span data-stu-id="c7673-314">The type of object that `Get-ChildItem` returns is determined by the objects in the provider drive path.</span></span>

### <span data-ttu-id="c7673-315">System.String</span><span class="sxs-lookup"><span data-stu-id="c7673-315">System.String</span></span>

<span data-ttu-id="c7673-316">Se você usar o parâmetro **Name** , `Get-ChildItem` o retornará os nomes de objeto como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c7673-316">If you use the **Name** parameter, `Get-ChildItem` returns the object names as strings.</span></span>

## <span data-ttu-id="c7673-317">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c7673-317">NOTES</span></span>

- <span data-ttu-id="c7673-318">`Get-ChildItem` pode ser executado usando qualquer um dos aliases internos, `ls` , `dir` , e `gci` .</span><span class="sxs-lookup"><span data-stu-id="c7673-318">`Get-ChildItem` can be run using any of the built-in aliases, `ls`, `dir`, and `gci`.</span></span> <span data-ttu-id="c7673-319">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="c7673-319">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="c7673-320">`Get-ChildItem` não obtém itens ocultos por padrão.</span><span class="sxs-lookup"><span data-stu-id="c7673-320">`Get-ChildItem` doesn't get hidden items by default.</span></span> <span data-ttu-id="c7673-321">Para obter itens ocultos, use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="c7673-321">To get hidden items, use the **Force** parameter.</span></span>
- <span data-ttu-id="c7673-322">O `Get-ChildItem` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="c7673-322">The `Get-ChildItem` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="c7673-323">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="c7673-323">To list the providers available in your session, type `Get-PSProvider`.</span></span>
  <span data-ttu-id="c7673-324">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="c7673-324">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="c7673-325">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c7673-325">RELATED LINKS</span></span>

[<span data-ttu-id="c7673-326">about_Certificate_Provider</span><span class="sxs-lookup"><span data-stu-id="c7673-326">about_Certificate_Provider</span></span>](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)

[<span data-ttu-id="c7673-327">about_Providers</span><span class="sxs-lookup"><span data-stu-id="c7673-327">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="c7673-328">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="c7673-328">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="c7673-329">about_Registry_Provider</span><span class="sxs-lookup"><span data-stu-id="c7673-329">about_Registry_Provider</span></span>](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md)

[<span data-ttu-id="c7673-330">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="c7673-330">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="c7673-331">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="c7673-331">Get-Alias</span></span>](../Microsoft.PowerShell.Utility/Get-Alias.md)

[<span data-ttu-id="c7673-332">Get-Item</span><span class="sxs-lookup"><span data-stu-id="c7673-332">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="c7673-333">Get-Location</span><span class="sxs-lookup"><span data-stu-id="c7673-333">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="c7673-334">Get-Process</span><span class="sxs-lookup"><span data-stu-id="c7673-334">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="c7673-335">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="c7673-335">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="c7673-336">Split-Path</span><span class="sxs-lookup"><span data-stu-id="c7673-336">Split-Path</span></span>](Split-Path.md)
