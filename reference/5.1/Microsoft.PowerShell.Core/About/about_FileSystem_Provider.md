---
description: FileSystem
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_filesystem_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: FileSystem Provider
ms.openlocfilehash: 204a90dc346e6d4ff483777b9adf7a70017ef093
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94386885"
---
# <a name="filesystem-provider"></a><span data-ttu-id="d3226-104">FileSystem Provider</span><span class="sxs-lookup"><span data-stu-id="d3226-104">FileSystem provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="d3226-105">Nome do provedor</span><span class="sxs-lookup"><span data-stu-id="d3226-105">Provider name</span></span>

<span data-ttu-id="d3226-106">FileSystem</span><span class="sxs-lookup"><span data-stu-id="d3226-106">FileSystem</span></span>

## <a name="drives"></a><span data-ttu-id="d3226-107">Unidades</span><span class="sxs-lookup"><span data-stu-id="d3226-107">Drives</span></span>

<span data-ttu-id="d3226-108">`C:`, `D:` ...</span><span class="sxs-lookup"><span data-stu-id="d3226-108">`C:`, `D:` ...</span></span>

## <a name="capabilities"></a><span data-ttu-id="d3226-109">Capacidades</span><span class="sxs-lookup"><span data-stu-id="d3226-109">Capabilities</span></span>

<span data-ttu-id="d3226-110">**Filtrar** , **ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="d3226-110">**Filter** , **ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="d3226-111">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="d3226-111">Short description</span></span>

<span data-ttu-id="d3226-112">Fornece acesso a arquivos e diretórios.</span><span class="sxs-lookup"><span data-stu-id="d3226-112">Provides access to files and directories.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="d3226-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="d3226-113">Detailed description</span></span>

<span data-ttu-id="d3226-114">O provedor do **sistema de arquivos** do PowerShell permite que você obtenha, adicione, altere, apague e exclua arquivos e diretórios no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3226-114">The PowerShell **FileSystem** provider lets you get, add, change, clear, and delete files and directories in PowerShell.</span></span>

<span data-ttu-id="d3226-115">As unidades do **sistema de arquivos** são um namespace hierárquico que contém os diretórios e arquivos em seu computador.</span><span class="sxs-lookup"><span data-stu-id="d3226-115">The **FileSystem** drives are a hierarchical namespace containing the directories and files on your computer.</span></span> <span data-ttu-id="d3226-116">Uma unidade de **sistema de arquivos** pode ser uma unidade lógica ou físicos, um diretório ou um compartilhamento de rede mapeado.</span><span class="sxs-lookup"><span data-stu-id="d3226-116">A **FileSystem** drive can be a logical or phsyical drive, directory, or mapped network share.</span></span>

<span data-ttu-id="d3226-117">O provedor **FileSystem** oferece suporte aos seguintes cmdlets, que são abordados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="d3226-117">The **FileSystem** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="d3226-118">Get-Location</span><span class="sxs-lookup"><span data-stu-id="d3226-118">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="d3226-119">Set-Location</span><span class="sxs-lookup"><span data-stu-id="d3226-119">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="d3226-120">Get-Item</span><span class="sxs-lookup"><span data-stu-id="d3226-120">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="d3226-121">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d3226-121">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="d3226-122">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="d3226-122">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="d3226-123">Move-Item</span><span class="sxs-lookup"><span data-stu-id="d3226-123">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="d3226-124">New-Item</span><span class="sxs-lookup"><span data-stu-id="d3226-124">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="d3226-125">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="d3226-125">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="d3226-126">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d3226-126">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="d3226-127">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d3226-127">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="d3226-128">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="d3226-128">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="d3226-129">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d3226-129">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="d3226-130">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="d3226-130">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="d3226-131">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d3226-131">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="d3226-132">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="d3226-132">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="d3226-133">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="d3226-133">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)
- [<span data-ttu-id="d3226-134">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="d3226-134">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [<span data-ttu-id="d3226-135">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="d3226-135">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="d3226-136">Tipos expostos por este provedor</span><span class="sxs-lookup"><span data-stu-id="d3226-136">Types exposed by this provider</span></span>

<span data-ttu-id="d3226-137">Os arquivos são instâncias da classe [System. IO. FileInfo](/dotnet/api/system.io.fileinfo) .</span><span class="sxs-lookup"><span data-stu-id="d3226-137">Files are instances of the [System.IO.FileInfo](/dotnet/api/system.io.fileinfo) class.</span></span>  <span data-ttu-id="d3226-138">Os diretórios são instâncias da classe [System. IO. DirectoryInfo](/dotnet/api/system.io.directoryinfo) .</span><span class="sxs-lookup"><span data-stu-id="d3226-138">Directories are instances of the [System.IO.DirectoryInfo](/dotnet/api/system.io.directoryinfo) class.</span></span>

## <a name="navigating-the-filesystem-drives"></a><span data-ttu-id="d3226-139">Navegando pelas unidades do sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="d3226-139">Navigating the FileSystem drives</span></span>

<span data-ttu-id="d3226-140">O provedor **FileSystem** expõe seus armazenamentos de dados mapeando quaisquer unidades lógicas no computador como unidades do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3226-140">The **FileSystem** provider exposes its data stores by mapping any logical drives on the computer as PowerShell drives.</span></span> <span data-ttu-id="d3226-141">Para trabalhar com uma unidade de **sistema de arquivos** , você pode alterar seu local para uma unidade utoridades o nome da unidade seguido por dois-pontos ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="d3226-141">To work with a **FileSystem** drive you can change your location to a drive uing the drive name followed by a colon (`:`).</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="d3226-142">Você também pode trabalhar com o provedor **FileSystem** de qualquer outra unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3226-142">You can also work with the **FileSystem** provider from any other PowerShell drive.</span></span> <span data-ttu-id="d3226-143">Para fazer referência a um arquivo ou diretório de outro local, use o nome da unidade ( `C:` , `D:` ,...) no caminho.</span><span class="sxs-lookup"><span data-stu-id="d3226-143">To reference a file or directory from another location, use the drive name (`C:`, `D:`, ...) in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="d3226-144">O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor.</span><span class="sxs-lookup"><span data-stu-id="d3226-144">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="d3226-145">Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="d3226-145">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="d3226-146">e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="d3226-146">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-files-and-directories"></a><span data-ttu-id="d3226-147">Obtendo arquivos e diretórios</span><span class="sxs-lookup"><span data-stu-id="d3226-147">Getting files and directories</span></span>

<span data-ttu-id="d3226-148">O `Get-ChildItem` cmdlet retorna todos os arquivos e diretórios no local atual.</span><span class="sxs-lookup"><span data-stu-id="d3226-148">The `Get-ChildItem` cmdlet returns all files and directories in the current location.</span></span> <span data-ttu-id="d3226-149">Você pode especificar um caminho diferente para pesquisar e usar parâmetros internos para filtrar e controlar a profundidade da recursão.</span><span class="sxs-lookup"><span data-stu-id="d3226-149">You can specify a different path to search and use built in parameters to filter and control the recursion depth.</span></span>

```powershell
Get-ChildItem
```

<span data-ttu-id="d3226-150">Para ler mais sobre o uso de cmdlet, consulte [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem).</span><span class="sxs-lookup"><span data-stu-id="d3226-150">To read more about cmdlet usage, see [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem).</span></span>

## <a name="copying-files-and-directories"></a><span data-ttu-id="d3226-151">Copiando arquivos e diretórios</span><span class="sxs-lookup"><span data-stu-id="d3226-151">Copying files and directories</span></span>

<span data-ttu-id="d3226-152">O `Copy-Item` cmdlet copia arquivos e diretórios para um local que você especificar.</span><span class="sxs-lookup"><span data-stu-id="d3226-152">The `Copy-Item` cmdlet copies files and directories to a location you specify.</span></span>
<span data-ttu-id="d3226-153">Os parâmetros estão disponíveis para filtrar e recurse, semelhante a `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="d3226-153">Parameters are available to filter and recurse, similar to `Get-ChildItem`.</span></span>

<span data-ttu-id="d3226-154">O comando a seguir copia todos os arquivos e diretórios no caminho "C:\temp" \" para a pasta "C:\Windows\Temp".</span><span class="sxs-lookup"><span data-stu-id="d3226-154">The following command copies all of the files and directories under the path "C:\temp\" to the folder "C:\Windows\Temp".</span></span>

```powershell
Copy-Item -Path C:\temp\* -Destination C:\Windows\Temp -Recurse -File
```

<span data-ttu-id="d3226-155">`Copy-Item` substitui os arquivos no diretório de destino sem solicitar confirmação.</span><span class="sxs-lookup"><span data-stu-id="d3226-155">`Copy-Item` overwrites files in the destination directory without prompting for confirmation.</span></span>

<span data-ttu-id="d3226-156">Esse comando copia o `a.txt` arquivo do `C:\a` diretório para o `C:\a\bb` diretório.</span><span class="sxs-lookup"><span data-stu-id="d3226-156">This command copies the `a.txt` file from the `C:\a` directory to the `C:\a\bb` directory.</span></span>

```powershell
Copy-Item -Path C:\a\a.txt -Destination C:\a\bb\a.txt
```

<span data-ttu-id="d3226-157">Copia todos os diretórios e arquivos no `C:\a` diretório para o `C:\c` diretório.</span><span class="sxs-lookup"><span data-stu-id="d3226-157">Copies all the directories and files in the `C:\a` directory to the `C:\c` directory.</span></span> <span data-ttu-id="d3226-158">Se qualquer um dos diretórios para copiar já existir no diretório de destino, o comando falhará a menos que você especifique o parâmetro Force.</span><span class="sxs-lookup"><span data-stu-id="d3226-158">If any of the directories to copy already exist in the destination directory, the command will fail unless you specify the Force parameter.</span></span>

```powershell
Copy-Item -Path C:\a\* -Destination C:\c -Recurse
```

<span data-ttu-id="d3226-159">Para obter mais informações, consulte [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item).</span><span class="sxs-lookup"><span data-stu-id="d3226-159">For more information, see [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item).</span></span>

## <a name="moving-files-and-directories"></a><span data-ttu-id="d3226-160">Movendo arquivos e diretórios</span><span class="sxs-lookup"><span data-stu-id="d3226-160">Moving files and directories</span></span>

<span data-ttu-id="d3226-161">Esse comando move o `c.txt` arquivo no `C:\a` diretório para o `C:\a\aa` diretório:</span><span class="sxs-lookup"><span data-stu-id="d3226-161">This command moves the `c.txt` file in the `C:\a` directory to the `C:\a\aa` directory:</span></span>

```powershell
Move-Item -Path C:\a\c.txt -Destination C:\a\aa
```

<span data-ttu-id="d3226-162">O comando não substituirá automaticamente um arquivo existente que tenha o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="d3226-162">The command will not automatically overwrite an existing file that has the same name.</span></span> <span data-ttu-id="d3226-163">Para forçar o cmdlet a substituir um arquivo existente, especifique o parâmetro Force.</span><span class="sxs-lookup"><span data-stu-id="d3226-163">To force the cmdlet to overwrite an existing file, specify the Force parameter.</span></span>

<span data-ttu-id="d3226-164">Você não pode mover um diretório quando aquele diretório é o local atual.</span><span class="sxs-lookup"><span data-stu-id="d3226-164">You cannot move a directory when that directory is the current location.</span></span> <span data-ttu-id="d3226-165">Ao usar `Move-Item` o para mover o diretório no local atual, você verá esse erro.</span><span class="sxs-lookup"><span data-stu-id="d3226-165">When you use `Move-Item` to move the directory at the current location, you see this error.</span></span>

```
C:\temp> Move-Item -Path C:\temp\ -Destination C:\Windows\Temp

Move-Item : Cannot move item because the item at 'C:\temp\' is in use.
At line:1 char:1
+ Move-Item C:\temp\ C:\temp2\
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Move-Item], PSInvalidOperationException
    + FullyQualifiedErrorId : InvalidOperation,Microsoft.PowerShell.Commands.MoveItemCommand
```

## <a name="managing-file-content"></a><span data-ttu-id="d3226-166">Gerenciando conteúdo do arquivo</span><span class="sxs-lookup"><span data-stu-id="d3226-166">Managing file content</span></span>

### <a name="get-the-content-of-a-file"></a><span data-ttu-id="d3226-167">Obter o conteúdo de um arquivo</span><span class="sxs-lookup"><span data-stu-id="d3226-167">Get the content of a file</span></span>

<span data-ttu-id="d3226-168">Esse comando obtém o conteúdo do arquivo "Test.txt" e os exibe no console do.</span><span class="sxs-lookup"><span data-stu-id="d3226-168">This command gets the contents of the "Test.txt" file and displays them in the console.</span></span>

```powershell
Get-Content -Path Test.txt
```

<span data-ttu-id="d3226-169">Você pode canalizar o conteúdo do arquivo para outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d3226-169">You can pipe the contents of the file to another cmdlet.</span></span> <span data-ttu-id="d3226-170">Por exemplo, o comando a seguir lê o conteúdo do `Test.txt` arquivo e, em seguida, fornece-os como entrada para o cmdlet [ConvertTo-HTML](xref:Microsoft.PowerShell.Utility.ConvertTo-Html) :</span><span class="sxs-lookup"><span data-stu-id="d3226-170">For example, the following command reads the contents of the `Test.txt` file and then supplies them as input to the [ConvertTo-Html](xref:Microsoft.PowerShell.Utility.ConvertTo-Html) cmdlet:</span></span>

```powershell
Get-Content -Path Test.txt | ConvertTo-Html
```

<span data-ttu-id="d3226-171">Você também pode recuperar o conteúdo de um arquivo prefixando seu caminho de provedor com o cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="d3226-171">You can also retrieve the content of a file by prefixing its provider path with the dollar sign (`$`).</span></span> <span data-ttu-id="d3226-172">O caminho deve ser colocado entre chaves devido a restrições de nomenclatura de variáveis.</span><span class="sxs-lookup"><span data-stu-id="d3226-172">The path must be enclosed in curly braces due to variable naming restrictions.</span></span> <span data-ttu-id="d3226-173">Para obter mais informações, consulte [about_Variables](about_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d3226-173">For more information, see [about_Variables](about_Variables.md).</span></span>

```powershell
${C:\Windows\System32\Drivers\etc\hosts}
```

### <a name="add-content-to-a-file"></a><span data-ttu-id="d3226-174">Adicionar conteúdo a um arquivo</span><span class="sxs-lookup"><span data-stu-id="d3226-174">Add content to a file</span></span>

<span data-ttu-id="d3226-175">Esse comando acrescenta a cadeia de caracteres "conteúdo do teste" ao `Test.txt` arquivo:</span><span class="sxs-lookup"><span data-stu-id="d3226-175">This command appends the "test content" string to the `Test.txt` file:</span></span>

```powershell
Add-Content -Path test.txt -Value "test content"
```

<span data-ttu-id="d3226-176">O conteúdo existente no `Test.txt` arquivo não é excluído.</span><span class="sxs-lookup"><span data-stu-id="d3226-176">The existing content in the `Test.txt` file is not deleted.</span></span>

### <a name="replace-the-content-of-a-file"></a><span data-ttu-id="d3226-177">Substituir o conteúdo de um arquivo</span><span class="sxs-lookup"><span data-stu-id="d3226-177">Replace the content of a file</span></span>

<span data-ttu-id="d3226-178">Esse comando substitui o conteúdo do `Test.txt` arquivo pela cadeia de caracteres "conteúdo do teste":</span><span class="sxs-lookup"><span data-stu-id="d3226-178">This command replaces the contents of the `Test.txt` file with the "test content" string:</span></span>

```powershell
Set-Content -Path test.txt -Value "test content"
```

<span data-ttu-id="d3226-179">Ele substitui o conteúdo de `Test.txt` .</span><span class="sxs-lookup"><span data-stu-id="d3226-179">It overwrites the contents of `Test.txt`.</span></span> <span data-ttu-id="d3226-180">Você pode usar o parâmetro **Value** do cmdlet [New-Item](xref:Microsoft.PowerShell.Management.New-Item) para adicionar conteúdo a um arquivo ao criá-lo.</span><span class="sxs-lookup"><span data-stu-id="d3226-180">You can use the **Value** parameter of the [New-Item](xref:Microsoft.PowerShell.Management.New-Item) cmdlet to add content to a file when you create it.</span></span>

### <a name="loop-through-the-contents-of-a-file"></a><span data-ttu-id="d3226-181">Executar um loop no conteúdo de um arquivo</span><span class="sxs-lookup"><span data-stu-id="d3226-181">Loop through the contents of a file</span></span>

<span data-ttu-id="d3226-182">Por padrão, o `Get-Content` cmdlet usa o caractere de final de linha como seu delimitador, portanto, ele obtém um arquivo como uma coleção de cadeias de caracteres, com cada linha como uma cadeia de caracteres no arquivo.</span><span class="sxs-lookup"><span data-stu-id="d3226-182">By default, the `Get-Content` cmdlet uses the end-of-line character as its delimiter, so it gets a file as a collection of strings, with each line as one string in the file.</span></span>

<span data-ttu-id="d3226-183">Você pode usar o `-Delimiter` parâmetro para especificar um delimitador alternativo.</span><span class="sxs-lookup"><span data-stu-id="d3226-183">You can use the `-Delimiter` parameter to specify an alternate delimiter.</span></span> <span data-ttu-id="d3226-184">Se você defini-lo para os caracteres que indicam o final de uma seção ou o início da próxima seção, você pode dividir o arquivo em partes lógicas.</span><span class="sxs-lookup"><span data-stu-id="d3226-184">If you set it to the characters that denote the end of a section or the beginning of the next section, you can split the file into logical parts.</span></span>

<span data-ttu-id="d3226-185">O primeiro comando obtém o `Employees.txt` arquivo e o divide em seções, cada um dos quais termina com as palavras "fim do registro do funcionário" e salva-o na `$e` variável.</span><span class="sxs-lookup"><span data-stu-id="d3226-185">The first command gets the `Employees.txt` file and splits it into sections, each of which ends with the words "End of Employee Record" and it saves it in the `$e` variable.</span></span>

<span data-ttu-id="d3226-186">O segundo comando usa a notação de matriz para obter o primeiro item na coleção no `$e` .</span><span class="sxs-lookup"><span data-stu-id="d3226-186">The second command uses array notation to get the first item in the collection in `$e`.</span></span> <span data-ttu-id="d3226-187">Ele usa um índice de 0, porque as matrizes do PowerShell são baseadas em zero.</span><span class="sxs-lookup"><span data-stu-id="d3226-187">It uses an index of 0, because PowerShell arrays are zero-based.</span></span>

<span data-ttu-id="d3226-188">Para obter mais informações sobre o `Get-Content` cmdlet, consulte o tópico da ajuda para o [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content).</span><span class="sxs-lookup"><span data-stu-id="d3226-188">For more information about `Get-Content` cmdlet, see the help topic for the [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content).</span></span>

<span data-ttu-id="d3226-189">Para obter mais informações sobre matrizes, consulte [about_Arrays](../About/about_Arrays.md).</span><span class="sxs-lookup"><span data-stu-id="d3226-189">For more information about arrays, see [about_Arrays](../About/about_Arrays.md).</span></span>

```powershell
$e = Get-Content c:\test\employees.txt -Delimited "End Of Employee Record"
$e[0]
```

## <a name="managing-security-descriptors"></a><span data-ttu-id="d3226-190">Gerenciando descritores de segurança</span><span class="sxs-lookup"><span data-stu-id="d3226-190">Managing security descriptors</span></span>

### <a name="view-the-acl-for-a-file"></a><span data-ttu-id="d3226-191">Exibir a ACL para um arquivo</span><span class="sxs-lookup"><span data-stu-id="d3226-191">View the ACL for a file</span></span>

<span data-ttu-id="d3226-192">Esse comando retorna um objeto [System. Security. AccessControl. FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) :</span><span class="sxs-lookup"><span data-stu-id="d3226-192">This command returns a [System.Security.AccessControl.FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) object:</span></span>

```powershell
Get-Acl -Path test.txt | Format-List -Property *
```

<span data-ttu-id="d3226-193">Para obter mais informações sobre esse objeto, redirecione o comando para o cmdlet [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member) .</span><span class="sxs-lookup"><span data-stu-id="d3226-193">For more information about this object, pipe the command to the [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member) cmdlet.</span></span> <span data-ttu-id="d3226-194">Ou, consulte classe [FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) .</span><span class="sxs-lookup"><span data-stu-id="d3226-194">Or, see [FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) Class.</span></span>

### <a name="modify-the-acl-for-a-file"></a><span data-ttu-id="d3226-195">Modificar a ACL de um arquivo</span><span class="sxs-lookup"><span data-stu-id="d3226-195">Modify the ACL for a file</span></span>

### <a name="create-and-set-an-acl-for-a-file"></a><span data-ttu-id="d3226-196">Criar e definir uma ACL para um arquivo</span><span class="sxs-lookup"><span data-stu-id="d3226-196">Create and set an ACL for a file</span></span>

## <a name="creating-files-and-directories"></a><span data-ttu-id="d3226-197">Criando arquivos e diretórios</span><span class="sxs-lookup"><span data-stu-id="d3226-197">Creating files and directories</span></span>

### <a name="create-a-directory"></a><span data-ttu-id="d3226-198">Criar um diretório</span><span class="sxs-lookup"><span data-stu-id="d3226-198">Create a directory</span></span>

<span data-ttu-id="d3226-199">Este comando cria o `logfiles` diretório na `C` unidade:</span><span class="sxs-lookup"><span data-stu-id="d3226-199">This command creates the `logfiles` directory on the `C` drive:</span></span>

```powershell
New-Item -Path c:\ -Name logfiles -Type directory
```

<span data-ttu-id="d3226-200">O PowerShell também inclui uma `mkdir` função (alias `md` ) que usa o cmdlet [New-Item](xref:Microsoft.PowerShell.Management.New-Item) para criar um novo diretório.</span><span class="sxs-lookup"><span data-stu-id="d3226-200">PowerShell also includes a `mkdir` function (alias `md`) that uses the [New-Item](xref:Microsoft.PowerShell.Management.New-Item) cmdlet to create a new directory.</span></span>

### <a name="create-a-file"></a><span data-ttu-id="d3226-201">Criar um arquivo</span><span class="sxs-lookup"><span data-stu-id="d3226-201">Create a file</span></span>

<span data-ttu-id="d3226-202">Esse comando cria o `log2.txt` arquivo no `C:\logfiles` diretório e, em seguida, adiciona a cadeia de caracteres "log de teste" ao arquivo:</span><span class="sxs-lookup"><span data-stu-id="d3226-202">This command creates the `log2.txt` file in the `C:\logfiles` directory and then adds the "test log" string to the file:</span></span>

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file
```

### <a name="create-a-file-with-content"></a><span data-ttu-id="d3226-203">Crie um arquivo com conteúdo</span><span class="sxs-lookup"><span data-stu-id="d3226-203">Create a file with content</span></span>

<span data-ttu-id="d3226-204">Cria um arquivo chamado `log2.txt` no `C:\logfiles` diretório e adiciona a cadeia de caracteres "log de teste" ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="d3226-204">Creates a file called `log2.txt` in the `C:\logfiles` directory and adds the string "test log" to the file.</span></span>

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file -Value "test log"
```

## <a name="renaming-files-and-directories"></a><span data-ttu-id="d3226-205">Renomeando arquivos e diretórios</span><span class="sxs-lookup"><span data-stu-id="d3226-205">Renaming files and directories</span></span>

### <a name="rename-a-file"></a><span data-ttu-id="d3226-206">Renomear um arquivo</span><span class="sxs-lookup"><span data-stu-id="d3226-206">Rename a file</span></span>

<span data-ttu-id="d3226-207">Esse comando renomeia o `a.txt` arquivo no `C:\a` diretório para `b.txt` :</span><span class="sxs-lookup"><span data-stu-id="d3226-207">This command renames the `a.txt` file in the `C:\a` directory to `b.txt`:</span></span>

```powershell
Rename-Item -Path c:\a\a.txt -NewName b.txt
```

### <a name="rename-a-directory"></a><span data-ttu-id="d3226-208">Renomear um diretório</span><span class="sxs-lookup"><span data-stu-id="d3226-208">Rename a directory</span></span>

<span data-ttu-id="d3226-209">Esse comando renomeia o `C:\a\cc` diretório para `C:\a\dd` :</span><span class="sxs-lookup"><span data-stu-id="d3226-209">This command renames the `C:\a\cc` directory to `C:\a\dd`:</span></span>

```powershell
Rename-Item -Path c:\a\cc -NewName dd
```

## <a name="deleting-files-and-directories"></a><span data-ttu-id="d3226-210">Excluindo arquivos e diretórios</span><span class="sxs-lookup"><span data-stu-id="d3226-210">Deleting files and directories</span></span>

### <a name="delete-a-file"></a><span data-ttu-id="d3226-211">Excluir um arquivo</span><span class="sxs-lookup"><span data-stu-id="d3226-211">Delete a file</span></span>

<span data-ttu-id="d3226-212">Este comando exclui o `Test.txt` arquivo no diretório atual:</span><span class="sxs-lookup"><span data-stu-id="d3226-212">This command deletes the `Test.txt` file in the current directory:</span></span>

```powershell
Remove-Item -Path test.txt
```

### <a name="delete-files-using-wildcards"></a><span data-ttu-id="d3226-213">Excluir arquivos usando curingas</span><span class="sxs-lookup"><span data-stu-id="d3226-213">Delete files using wildcards</span></span>

<span data-ttu-id="d3226-214">Este comando exclui todos os arquivos no diretório atual que têm a `.xml` extensão de nome de arquivo:</span><span class="sxs-lookup"><span data-stu-id="d3226-214">This command deletes all the files in the current directory that have the `.xml` file name extension:</span></span>

```powershell
Remove-Item -Path *.xml
```

## <a name="starting-a-program-by-invoking-an-associated-file"></a><span data-ttu-id="d3226-215">Iniciando um programa invocando um arquivo associado</span><span class="sxs-lookup"><span data-stu-id="d3226-215">Starting a program by invoking an associated file</span></span>

### <a name="invoke-a-file"></a><span data-ttu-id="d3226-216">Invocar um arquivo</span><span class="sxs-lookup"><span data-stu-id="d3226-216">Invoke a file</span></span>

<span data-ttu-id="d3226-217">O primeiro comando usa o cmdlet [Get-Service](xref:Microsoft.PowerShell.Management.Get-Service) para obter informações sobre serviços locais.</span><span class="sxs-lookup"><span data-stu-id="d3226-217">The first command uses the [Get-Service](xref:Microsoft.PowerShell.Management.Get-Service) cmdlet to get information about local services.</span></span>

<span data-ttu-id="d3226-218">Ele canaliza as informações para o cmdlet [Export-CSV](xref:Microsoft.PowerShell.Utility.Export-Csv) e, em seguida, armazena essas informações no `Services.csv` arquivo.</span><span class="sxs-lookup"><span data-stu-id="d3226-218">It pipes the information to the [Export-Csv](xref:Microsoft.PowerShell.Utility.Export-Csv) cmdlet and then stores that information in the `Services.csv` file.</span></span>

<span data-ttu-id="d3226-219">O segundo comando usa [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item) para abrir o `services.csv` arquivo no programa associado à `.csv` extensão:</span><span class="sxs-lookup"><span data-stu-id="d3226-219">The second command uses [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item) to open the `services.csv` file in the program associated with the `.csv` extension:</span></span>

```powershell
Get-Service | Export-Csv -Path services.csv
Invoke-Item -Path services.csv
```

## <a name="getting-files-and-folders-with-specified-attributes"></a><span data-ttu-id="d3226-220">Obtendo arquivos e pastas com atributos especificados</span><span class="sxs-lookup"><span data-stu-id="d3226-220">Getting files and folders with specified attributes</span></span>

### <a name="get-system-files"></a><span data-ttu-id="d3226-221">Obter arquivos do sistema</span><span class="sxs-lookup"><span data-stu-id="d3226-221">Get System files</span></span>

<span data-ttu-id="d3226-222">Esse comando obtém arquivos do sistema no diretório atual e em seus subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="d3226-222">This command gets system files in the current directory and its subdirectories.</span></span>

<span data-ttu-id="d3226-223">Ele usa o `-File` parâmetro para obter apenas os arquivos (não os diretórios) e o `-System` parâmetro para obter apenas os itens com o atributo "System".</span><span class="sxs-lookup"><span data-stu-id="d3226-223">It uses the `-File` parameter to get only files (not directories) and the `-System` parameter to get only items with the "system" attribute.</span></span>

<span data-ttu-id="d3226-224">Ele usa o `-Recurse` parâmetro para obter os itens no diretório atual e em todos os subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="d3226-224">It uses the `-Recurse` parameter to get the items in the current directory and all subdirectories.</span></span>

```powershell
Get-ChildItem -File -System -Recurse
```

### <a name="get-hidden-files"></a><span data-ttu-id="d3226-225">Obter arquivos ocultos</span><span class="sxs-lookup"><span data-stu-id="d3226-225">Get Hidden files</span></span>

<span data-ttu-id="d3226-226">Esse comando obtém todos os arquivos, inclusive arquivos ocultos, no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="d3226-226">This command gets all files, including hidden files, in the current directory.</span></span>

<span data-ttu-id="d3226-227">Ele usa o parâmetro **Attributes** com dois valores, `!Directory+Hidden` , que obtém arquivos ocultos e `!Directory` , que obtém todos os outros arquivos.</span><span class="sxs-lookup"><span data-stu-id="d3226-227">It uses the **Attributes** parameter with two values, `!Directory+Hidden`, which gets hidden files, and `!Directory`, which gets all other files.</span></span>

```powershell
Get-ChildItem -Attributes !Directory,!Directory+Hidden
```

<span data-ttu-id="d3226-228">`dir -att !d,!d+h` é o equivalente deste comando.</span><span class="sxs-lookup"><span data-stu-id="d3226-228">`dir -att !d,!d+h` is the equivalent of this command.</span></span>

### <a name="get-compressed-and-encrypted-files"></a><span data-ttu-id="d3226-229">Obter arquivos compactados e criptografados</span><span class="sxs-lookup"><span data-stu-id="d3226-229">Get Compressed and Encrypted files</span></span>

<span data-ttu-id="d3226-230">Esse comando obtém os arquivos no diretório atual que são compactados ou criptografados.</span><span class="sxs-lookup"><span data-stu-id="d3226-230">This command gets files in the current directory that are either compressed or encrypted.</span></span>

<span data-ttu-id="d3226-231">Ele usa o `-Attributes` parâmetro com dois valores, `Compressed` e `Encrypted` .</span><span class="sxs-lookup"><span data-stu-id="d3226-231">It uses the `-Attributes` parameter with two values, `Compressed` and `Encrypted`.</span></span> <span data-ttu-id="d3226-232">Os valores são separados por uma vírgula `,` que representa o operador "or".</span><span class="sxs-lookup"><span data-stu-id="d3226-232">The values are separated by a comma `,` which represents the "OR" operator.</span></span>

```powershell
Get-ChildItem -Attributes Compressed,Encrypted
```

## <a name="dynamic-parameters"></a><span data-ttu-id="d3226-233">Parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="d3226-233">Dynamic parameters</span></span>

<span data-ttu-id="d3226-234">Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor.</span><span class="sxs-lookup"><span data-stu-id="d3226-234">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="encoding-microsoftpowershellcommandsfilesystemcmdletproviderencoding"></a><span data-ttu-id="d3226-235">Encoding \<Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding\></span><span class="sxs-lookup"><span data-stu-id="d3226-235">Encoding \<Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding\></span></span>

<span data-ttu-id="d3226-236">Especifica a codificação do arquivo.</span><span class="sxs-lookup"><span data-stu-id="d3226-236">Specifies the file encoding.</span></span> <span data-ttu-id="d3226-237">O padrão é ASCII.</span><span class="sxs-lookup"><span data-stu-id="d3226-237">The default is ASCII.</span></span>

- <span data-ttu-id="d3226-238">**ASCII** : usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="d3226-238">**ASCII** :  Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="d3226-239">**BigEndianUnicode** : codifica em formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="d3226-239">**BigEndianUnicode** :  Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="d3226-240">**String** : usa o tipo de codificação para uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="d3226-240">**String** :  Uses the encoding type for a string.</span></span>
- <span data-ttu-id="d3226-241">**Unicode** : codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="d3226-241">**Unicode** :  Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="d3226-242">**UTF7** : codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="d3226-242">**UTF7** :   Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="d3226-243">**UTF8** : codifica no formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="d3226-243">**UTF8** :  Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="d3226-244">**UTF8BOM** : codifica em formato UTF-8 com marca de ordem de byte (bom)</span><span class="sxs-lookup"><span data-stu-id="d3226-244">**UTF8BOM** : Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="d3226-245">**UF8NOBOM** : codifica em formato UTF-8 sem marca de ordem de byte (bom)</span><span class="sxs-lookup"><span data-stu-id="d3226-245">**UF8NOBOM** : Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="d3226-246">**UTF32** : codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="d3226-246">**UTF32** :  Encodes in UTF-32 format.</span></span>
- <span data-ttu-id="d3226-247">**Padrão** : codifica na página de código padrão instalada.</span><span class="sxs-lookup"><span data-stu-id="d3226-247">**Default** : Encodes in the default installed code page.</span></span>
- <span data-ttu-id="d3226-248">**OEM** : usa a codificação padrão para MS-dos e programas de console.</span><span class="sxs-lookup"><span data-stu-id="d3226-248">**OEM** : Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="d3226-249">**Desconhecido** : o tipo de codificação é desconhecido ou inválido.</span><span class="sxs-lookup"><span data-stu-id="d3226-249">**Unknown** :  The encoding type is unknown or invalid.</span></span> <span data-ttu-id="d3226-250">Os dados podem ser tratados como binários.</span><span class="sxs-lookup"><span data-stu-id="d3226-250">The data can be treated as binary.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d3226-251">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="d3226-251">Cmdlets supported</span></span>

- [<span data-ttu-id="d3226-252">Add-Content</span><span class="sxs-lookup"><span data-stu-id="d3226-252">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="d3226-253">Get-Content</span><span class="sxs-lookup"><span data-stu-id="d3226-253">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="d3226-254">Set-Content</span><span class="sxs-lookup"><span data-stu-id="d3226-254">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="delimiter-systemstring"></a><span data-ttu-id="d3226-255">Delimiter \<System.String\></span><span class="sxs-lookup"><span data-stu-id="d3226-255">Delimiter \<System.String\></span></span>

<span data-ttu-id="d3226-256">Especifica o delimitador que o [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) usa para dividir o arquivo em objetos enquanto ele lê.</span><span class="sxs-lookup"><span data-stu-id="d3226-256">Specifies the delimiter that [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) uses to divide the file into objects while it reads.</span></span>

<span data-ttu-id="d3226-257">O padrão é `\n` , o caractere de fim de linha.</span><span class="sxs-lookup"><span data-stu-id="d3226-257">The default is `\n`, the end-of-line character.</span></span>

<span data-ttu-id="d3226-258">Ao ler um arquivo de texto, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) retorna uma coleção de objetos String, cada um dos quais termina com o caractere delimitador.</span><span class="sxs-lookup"><span data-stu-id="d3226-258">When reading a text file, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) returns a collection of string objects, each of which ends with the delimiter character.</span></span>

<span data-ttu-id="d3226-259">A inserção de um delimitador que não existe no arquivo, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) retorna o arquivo inteiro como um objeto único e não delimitado.</span><span class="sxs-lookup"><span data-stu-id="d3226-259">Entering a delimiter that does not exist in the file, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) returns the entire file as a single, un-delimited object.</span></span>

<span data-ttu-id="d3226-260">Você pode usar esse parâmetro para dividir um arquivo grande em arquivos menores, especificando um separador de arquivo, como "Final de exemplo," como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="d3226-260">You can use this parameter to split a large file into smaller files by specifying a file separator, such as "End of Example", as the delimiter.</span></span> <span data-ttu-id="d3226-261">O delimitador é preservado (não descartado) e se torna o último item em cada seção do arquivo.</span><span class="sxs-lookup"><span data-stu-id="d3226-261">The delimiter is preserved (not discarded) and becomes the last item in each file section.</span></span>

> [!NOTE]
> <span data-ttu-id="d3226-262">Atualmente, quando o valor do `-Delimiter` parâmetro é uma cadeia de caracteres vazia, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) não retorna nada.</span><span class="sxs-lookup"><span data-stu-id="d3226-262">Currently, when the value of the `-Delimiter` parameter is an empty string, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) does not return anything.</span></span>
> <span data-ttu-id="d3226-263">Esse é um problema conhecido.</span><span class="sxs-lookup"><span data-stu-id="d3226-263">This is a known issue.</span></span> <span data-ttu-id="d3226-264">Para forçar o [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) a retornar o arquivo inteiro como uma única cadeia de caracteres não delimitada, insira um valor que não existe no arquivo.</span><span class="sxs-lookup"><span data-stu-id="d3226-264">To force [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) to return the entire file as a single, undelimited string, enter a value that does not exist in the file.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d3226-265">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="d3226-265">Cmdlets supported</span></span>

- [<span data-ttu-id="d3226-266">Get-Content</span><span class="sxs-lookup"><span data-stu-id="d3226-266">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="wait-systemmanagementautomationswitchparameter"></a><span data-ttu-id="d3226-267">Wait \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d3226-267">Wait \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="d3226-268">Aguarda o conteúdo a ser anexado ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="d3226-268">Waits for content to be appended to the file.</span></span> <span data-ttu-id="d3226-269">Se o conteúdo será anexado, ele retorna o conteúdo anexado.</span><span class="sxs-lookup"><span data-stu-id="d3226-269">If content is appended, it returns the appended content.</span></span> <span data-ttu-id="d3226-270">Se o conteúdo tiver sido alterado, ele retornará o arquivo inteiro.</span><span class="sxs-lookup"><span data-stu-id="d3226-270">If the content has changed, it returns the entire file.</span></span>

<span data-ttu-id="d3226-271">Ao aguardar, o [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) verifica o arquivo uma vez por segundo até você interrompê-lo, por exemplo, pressionando CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="d3226-271">When waiting, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) checks the file once each second until you interrupt it, such as by pressing CTRL+C.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d3226-272">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="d3226-272">Cmdlets supported</span></span>

- [<span data-ttu-id="d3226-273">Get-Content</span><span class="sxs-lookup"><span data-stu-id="d3226-273">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="attributes-flagsexpression"></a><span data-ttu-id="d3226-274">Attributes \<FlagsExpression\></span><span class="sxs-lookup"><span data-stu-id="d3226-274">Attributes \<FlagsExpression\></span></span>

<span data-ttu-id="d3226-275">Obtém os arquivos e pastas com os atributos especificados.</span><span class="sxs-lookup"><span data-stu-id="d3226-275">Gets files and folders with the specified attributes.</span></span> <span data-ttu-id="d3226-276">Esse parâmetro dá suporte a todos os atributos e permite que você especifique combinações complexas de atributos.</span><span class="sxs-lookup"><span data-stu-id="d3226-276">This parameter supports all attributes and lets you specify complex combinations of attributes.</span></span>

<span data-ttu-id="d3226-277">O `-Attributes` parâmetro foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d3226-277">The `-Attributes` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d3226-278">O `-Attributes` parâmetro oferece suporte aos seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="d3226-278">The `-Attributes` parameter supports the following attributes:</span></span>

- <span data-ttu-id="d3226-279">**Arquivar**</span><span class="sxs-lookup"><span data-stu-id="d3226-279">**Archive**</span></span>
- <span data-ttu-id="d3226-280">**Compactado**</span><span class="sxs-lookup"><span data-stu-id="d3226-280">**Compressed**</span></span>
- <span data-ttu-id="d3226-281">**Dispositivo**</span><span class="sxs-lookup"><span data-stu-id="d3226-281">**Device**</span></span>
- <span data-ttu-id="d3226-282">**Diretório**</span><span class="sxs-lookup"><span data-stu-id="d3226-282">**Directory**</span></span>
- <span data-ttu-id="d3226-283">**Criptografado**</span><span class="sxs-lookup"><span data-stu-id="d3226-283">**Encrypted**</span></span>
- <span data-ttu-id="d3226-284">**Oculto**</span><span class="sxs-lookup"><span data-stu-id="d3226-284">**Hidden**</span></span>
- <span data-ttu-id="d3226-285">**Normal**</span><span class="sxs-lookup"><span data-stu-id="d3226-285">**Normal**</span></span>
- <span data-ttu-id="d3226-286">**NotContentIndexed**</span><span class="sxs-lookup"><span data-stu-id="d3226-286">**NotContentIndexed**</span></span>
- <span data-ttu-id="d3226-287">**Está**</span><span class="sxs-lookup"><span data-stu-id="d3226-287">**Offline**</span></span>
- <span data-ttu-id="d3226-288">**ReadOnly (somente-leitura)**</span><span class="sxs-lookup"><span data-stu-id="d3226-288">**ReadOnly**</span></span>
- <span data-ttu-id="d3226-289">**ReparsePoint**</span><span class="sxs-lookup"><span data-stu-id="d3226-289">**ReparsePoint**</span></span>
- <span data-ttu-id="d3226-290">**Escassfile**</span><span class="sxs-lookup"><span data-stu-id="d3226-290">**SparseFile**</span></span>
- <span data-ttu-id="d3226-291">**Sistema**</span><span class="sxs-lookup"><span data-stu-id="d3226-291">**System**</span></span>
- <span data-ttu-id="d3226-292">**Temporário**</span><span class="sxs-lookup"><span data-stu-id="d3226-292">**Temporary**</span></span>

<span data-ttu-id="d3226-293">Para obter uma descrição desses atributos, consulte a enumeração [FileAttributes](/dotnet/api/system.io.fileattributes) .</span><span class="sxs-lookup"><span data-stu-id="d3226-293">For a description of these attributes, see the [FileAttributes](/dotnet/api/system.io.fileattributes) enumeration.</span></span>

<span data-ttu-id="d3226-294">Use os seguintes operadores para combinar atributos.</span><span class="sxs-lookup"><span data-stu-id="d3226-294">Use the following operators to combine attributes.</span></span>

- <span data-ttu-id="d3226-295">`!` -Não</span><span class="sxs-lookup"><span data-stu-id="d3226-295">`!` - NOT</span></span>
- <span data-ttu-id="d3226-296">`+` -E</span><span class="sxs-lookup"><span data-stu-id="d3226-296">`+` - AND</span></span>
- <span data-ttu-id="d3226-297">`,` -OU</span><span class="sxs-lookup"><span data-stu-id="d3226-297">`,` - OR</span></span>

<span data-ttu-id="d3226-298">Nenhum espaço é permitido entre o operador e seus atributos.</span><span class="sxs-lookup"><span data-stu-id="d3226-298">No spaces are permitted between an operator and its attribute.</span></span> <span data-ttu-id="d3226-299">No entanto, os espaços são permitidos antes de vírgulas.</span><span class="sxs-lookup"><span data-stu-id="d3226-299">However, spaces are permitted before commas.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d3226-300">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="d3226-300">Cmdlets supported</span></span>

- [<span data-ttu-id="d3226-301">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d3226-301">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="directory-systemmanagementautomationswitchparameter"></a><span data-ttu-id="d3226-302">Directory \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d3226-302">Directory \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="d3226-303">Obtém os diretórios (pastas).</span><span class="sxs-lookup"><span data-stu-id="d3226-303">Gets directories (folders).</span></span>

<span data-ttu-id="d3226-304">O `-Directory` parâmetro foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d3226-304">The `-Directory` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d3226-305">Para obter apenas os diretórios, use o `-Directory` parâmetro e omita o `-File` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d3226-305">To get only directories, use the `-Directory` parameter and omit the `-File` parameter.</span></span> <span data-ttu-id="d3226-306">Para excluir diretórios, use o `-File` parâmetro e omita o `-Directory` parâmetro ou use o `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d3226-306">To exclude directories, use the `-File` parameter and omit the `-Directory` parameter, or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d3226-307">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="d3226-307">Cmdlets supported</span></span>

- [<span data-ttu-id="d3226-308">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d3226-308">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="file-systemmanagementautomationswitchparameter"></a><span data-ttu-id="d3226-309">File \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d3226-309">File \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="d3226-310">Obtém arquivos.</span><span class="sxs-lookup"><span data-stu-id="d3226-310">Gets files.</span></span>

<span data-ttu-id="d3226-311">O `-File` parâmetro foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d3226-311">The `-File` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d3226-312">Para obter apenas arquivos, use o `-File` parâmetro e omita o `-Directory` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d3226-312">To get only files, use the `-File` parameter and omit the `-Directory` parameter.</span></span> <span data-ttu-id="d3226-313">Para excluir arquivos, use o `-Directory` parâmetro e omita o `-File` parâmetro ou use o `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d3226-313">To exclude files, use the `-Directory` parameter and omit the `-File` parameter, or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d3226-314">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="d3226-314">Cmdlets supported</span></span>

- [<span data-ttu-id="d3226-315">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d3226-315">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="hidden-systemmanagementautomationswitchparameter"></a><span data-ttu-id="d3226-316">Hidden \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d3226-316">Hidden \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="d3226-317">Obtém somente arquivos ocultos e diretórios (pastas).</span><span class="sxs-lookup"><span data-stu-id="d3226-317">Gets only hidden files and directories (folders).</span></span> <span data-ttu-id="d3226-318">Por padrão, [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) obtém somente itens não ocultos.</span><span class="sxs-lookup"><span data-stu-id="d3226-318">By default, [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) gets only non-hidden items.</span></span>

<span data-ttu-id="d3226-319">O `-Hidden` parâmetro foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d3226-319">The `-Hidden` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d3226-320">Para obter apenas itens ocultos, use o `-Hidden` parâmetro, `h` seus `ah` aliases ou o valor **oculto** do `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d3226-320">To get only hidden items, use the `-Hidden` parameter, its `h` or `ah` aliases, or the **Hidden** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="d3226-321">Para excluir itens ocultos, omita o `-Hidden` parâmetro ou use o `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d3226-321">To exclude hidden items, omit the `-Hidden` parameter or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d3226-322">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="d3226-322">Cmdlets supported</span></span>

- [<span data-ttu-id="d3226-323">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d3226-323">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="readonly-systemmanagementautomationswitchparameter"></a><span data-ttu-id="d3226-324">ReadOnly \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d3226-324">ReadOnly \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="d3226-325">Obtém somente arquivos somente leitura e diretórios (pastas).</span><span class="sxs-lookup"><span data-stu-id="d3226-325">Gets only read-only files and directories (folders).</span></span>

<span data-ttu-id="d3226-326">O `-ReadOnly` parâmetro foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d3226-326">The `-ReadOnly` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d3226-327">Para obter somente itens somente leitura, use o `-ReadOnly` parâmetro, seu `ar` alias ou o valor **ReadOnly** do `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d3226-327">To get only read-only items, use the `-ReadOnly` parameter, its `ar` alias, or the **ReadOnly** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="d3226-328">Para excluir itens somente leitura, use o `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d3226-328">To exclude read-only items, use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d3226-329">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="d3226-329">Cmdlets supported</span></span>

- [<span data-ttu-id="d3226-330">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d3226-330">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="system-systemmanagementautomationswitchparameter"></a><span data-ttu-id="d3226-331">System \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d3226-331">System \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="d3226-332">Obtém somente os arquivos do sistema e diretórios (pastas).</span><span class="sxs-lookup"><span data-stu-id="d3226-332">Gets only system files and directories (folders).</span></span>

<span data-ttu-id="d3226-333">O `-System` parâmetro foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d3226-333">The `-System` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d3226-334">Para obter apenas arquivos e pastas do sistema, use o `-System` parâmetro, seu `as` alias ou o valor do **sistema** do `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d3226-334">To get only system files and folders, use the `-System` parameter, its `as` alias, or the **System** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="d3226-335">Para excluir arquivos e pastas do sistema, use o `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d3226-335">To exclude system files and folders, use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d3226-336">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="d3226-336">Cmdlets supported</span></span>

- [<span data-ttu-id="d3226-337">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d3226-337">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="newerthan-systemdatetime"></a><span data-ttu-id="d3226-338">NewerThan \<System.DateTime\></span><span class="sxs-lookup"><span data-stu-id="d3226-338">NewerThan \<System.DateTime\></span></span>

<span data-ttu-id="d3226-339">Retorna `$True` quando o `LastWriteTime` valor de um arquivo é maior que a data especificada.</span><span class="sxs-lookup"><span data-stu-id="d3226-339">Returns `$True` when the `LastWriteTime` value of a file is greater than the specified date.</span></span> <span data-ttu-id="d3226-340">Caso contrário, retornará `$False`.</span><span class="sxs-lookup"><span data-stu-id="d3226-340">Otherwise, it returns `$False`.</span></span>

<span data-ttu-id="d3226-341">Insira um objeto [DateTime](/dotnet/api/system.datetime) , como um que o cmdlet [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) retorna ou uma cadeia de caracteres que pode ser convertida em um objeto [DateTime](/dotnet/api/system.datetime) , como `"August 10, 2011 2:00 PM"` .</span><span class="sxs-lookup"><span data-stu-id="d3226-341">Enter a [DateTime](/dotnet/api/system.datetime) object, such as one that the [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet returns, or a string that can be converted to a [DateTime](/dotnet/api/system.datetime) object, such as `"August 10, 2011 2:00 PM"`.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d3226-342">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="d3226-342">Cmdlets supported</span></span>

- [<span data-ttu-id="d3226-343">Test-Path</span><span class="sxs-lookup"><span data-stu-id="d3226-343">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="olderthan-systemdatetime"></a><span data-ttu-id="d3226-344">OlderThan \<System.DateTime\></span><span class="sxs-lookup"><span data-stu-id="d3226-344">OlderThan \<System.DateTime\></span></span>

<span data-ttu-id="d3226-345">Retorna `$True` quando o `LastWriteTime` valor de um arquivo é menor que a data especificada.</span><span class="sxs-lookup"><span data-stu-id="d3226-345">Returns `$True` when the `LastWriteTime` value of a file is less than the specified date.</span></span> <span data-ttu-id="d3226-346">Caso contrário, retornará `$False`.</span><span class="sxs-lookup"><span data-stu-id="d3226-346">Otherwise, it returns `$False`.</span></span>

<span data-ttu-id="d3226-347">Insira um objeto [DateTime](/dotnet/api/system.datetime) , como um que o cmdlet [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) retorna ou uma cadeia de caracteres que pode ser convertida em um objeto [DateTime](/dotnet/api/system.datetime) , como `"August 10, 2011 2:00 PM"` .</span><span class="sxs-lookup"><span data-stu-id="d3226-347">Enter a [DateTime](/dotnet/api/system.datetime) object, such as one that the [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet returns, or a string that can be converted to a [DateTime](/dotnet/api/system.datetime) object, such as `"August 10, 2011 2:00 PM"`.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d3226-348">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="d3226-348">Cmdlets supported</span></span>

- [<span data-ttu-id="d3226-349">Test-Path</span><span class="sxs-lookup"><span data-stu-id="d3226-349">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="stream-systemstring"></a><span data-ttu-id="d3226-350">Stream \<System.String\></span><span class="sxs-lookup"><span data-stu-id="d3226-350">Stream \<System.String\></span></span>

<span data-ttu-id="d3226-351">Gerencia o fluxo de dados alternados.</span><span class="sxs-lookup"><span data-stu-id="d3226-351">Manages alternate data streams.</span></span> <span data-ttu-id="d3226-352">Insira o nome do fluxo.</span><span class="sxs-lookup"><span data-stu-id="d3226-352">Enter the stream name.</span></span> <span data-ttu-id="d3226-353">Curingas são permitidos somente em [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) para e os comandos [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item) em uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d3226-353">Wildcards are permitted only in [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) for and [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item) commands in a file system drive.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d3226-354">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="d3226-354">Cmdlets supported</span></span>

- [<span data-ttu-id="d3226-355">Add-Content</span><span class="sxs-lookup"><span data-stu-id="d3226-355">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="d3226-356">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="d3226-356">Clear-Content</span></span>](xref:Microsoft.PowerShell.Management.Clear-Content)
- [<span data-ttu-id="d3226-357">Get-Item</span><span class="sxs-lookup"><span data-stu-id="d3226-357">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="d3226-358">Get-Content</span><span class="sxs-lookup"><span data-stu-id="d3226-358">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="d3226-359">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="d3226-359">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="d3226-360">Set-Content</span><span class="sxs-lookup"><span data-stu-id="d3226-360">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="raw-switchparameter"></a><span data-ttu-id="d3226-361">Raw \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="d3226-361">Raw \<SwitchParameter\></span></span>

<span data-ttu-id="d3226-362">Ignora os caracteres de nova linha.</span><span class="sxs-lookup"><span data-stu-id="d3226-362">Ignores newline characters.</span></span> <span data-ttu-id="d3226-363">Retorna o conteúdo como um único item.</span><span class="sxs-lookup"><span data-stu-id="d3226-363">Returns contents as a single item.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="d3226-364">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="d3226-364">Cmdlets supported</span></span>

- [<span data-ttu-id="d3226-365">Get-Content</span><span class="sxs-lookup"><span data-stu-id="d3226-365">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="itemtype-string"></a><span data-ttu-id="d3226-366">ItemType \<String\></span><span class="sxs-lookup"><span data-stu-id="d3226-366">ItemType \<String\></span></span>

<span data-ttu-id="d3226-367">Esse parâmetro permite especificar o Tye do item a ser criado com `New-Item`</span><span class="sxs-lookup"><span data-stu-id="d3226-367">This parameter allows you to specify the tye of item to create with `New-Item`</span></span>

<span data-ttu-id="d3226-368">Os valores disponíveis desse parâmetro dependem do provedor atual que você está usando.</span><span class="sxs-lookup"><span data-stu-id="d3226-368">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="d3226-369">Em uma `FileSystem` unidade, os seguintes valores são permitidos:</span><span class="sxs-lookup"><span data-stu-id="d3226-369">In a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="d3226-370">Arquivo</span><span class="sxs-lookup"><span data-stu-id="d3226-370">File</span></span>
- <span data-ttu-id="d3226-371">Diretório</span><span class="sxs-lookup"><span data-stu-id="d3226-371">Directory</span></span>
- <span data-ttu-id="d3226-372">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="d3226-372">SymbolicLink</span></span>
- <span data-ttu-id="d3226-373">Junção</span><span class="sxs-lookup"><span data-stu-id="d3226-373">Junction</span></span>
- <span data-ttu-id="d3226-374">Real</span><span class="sxs-lookup"><span data-stu-id="d3226-374">HardLink</span></span>

### <a name="cmdlets-supported"></a><span data-ttu-id="d3226-375">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="d3226-375">Cmdlets supported</span></span>

- [<span data-ttu-id="d3226-376">New-Item</span><span class="sxs-lookup"><span data-stu-id="d3226-376">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="d3226-377">Usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="d3226-377">Using the pipeline</span></span>

<span data-ttu-id="d3226-378">Os cmdlets do provedor aceitam a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="d3226-378">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="d3226-379">Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor.</span><span class="sxs-lookup"><span data-stu-id="d3226-379">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="d3226-380">Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="d3226-380">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="d3226-381">Obtendo ajuda</span><span class="sxs-lookup"><span data-stu-id="d3226-381">Getting help</span></span>

<span data-ttu-id="d3226-382">A partir do Windows PowerShell 3.0, você pode obter tópicos da Ajuda personalizados para cmdlets do provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d3226-382">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="d3226-383">Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um comando [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) em uma unidade do sistema de arquivos ou use o `-Path` parâmetro de [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) para especificar uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d3226-383">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path c:
```

## <a name="see-also"></a><span data-ttu-id="d3226-384">Confira também</span><span class="sxs-lookup"><span data-stu-id="d3226-384">See also</span></span>

[<span data-ttu-id="d3226-385">about_Providers</span><span class="sxs-lookup"><span data-stu-id="d3226-385">about_Providers</span></span>](../About/about_Providers.md)
