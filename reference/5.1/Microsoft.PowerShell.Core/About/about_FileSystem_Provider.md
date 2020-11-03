---
description: FileSystem
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_filesystem_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: FileSystem Provider
ms.openlocfilehash: 3b37f6e4eb53ef7291c30cbc9820caf83641a9bb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196207"
---
# <a name="filesystem-provider"></a><span data-ttu-id="b9b53-104">FileSystem Provider</span><span class="sxs-lookup"><span data-stu-id="b9b53-104">FileSystem provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="b9b53-105">Nome do provedor</span><span class="sxs-lookup"><span data-stu-id="b9b53-105">Provider name</span></span>

<span data-ttu-id="b9b53-106">FileSystem</span><span class="sxs-lookup"><span data-stu-id="b9b53-106">FileSystem</span></span>

## <a name="drives"></a><span data-ttu-id="b9b53-107">Unidades</span><span class="sxs-lookup"><span data-stu-id="b9b53-107">Drives</span></span>

<span data-ttu-id="b9b53-108">`C:`, `D:` ...</span><span class="sxs-lookup"><span data-stu-id="b9b53-108">`C:`, `D:` ...</span></span>

## <a name="capabilities"></a><span data-ttu-id="b9b53-109">Funcionalidades</span><span class="sxs-lookup"><span data-stu-id="b9b53-109">Capabilities</span></span>

<span data-ttu-id="b9b53-110">**Filtrar** , **ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="b9b53-110">**Filter** , **ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="b9b53-111">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="b9b53-111">Short description</span></span>

<span data-ttu-id="b9b53-112">Fornece acesso a arquivos e diretórios.</span><span class="sxs-lookup"><span data-stu-id="b9b53-112">Provides access to files and directories.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="b9b53-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="b9b53-113">Detailed description</span></span>

<span data-ttu-id="b9b53-114">O provedor do **sistema de arquivos** do PowerShell permite que você obtenha, adicione, altere, apague e exclua arquivos e diretórios no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9b53-114">The PowerShell **FileSystem** provider lets you get, add, change, clear, and delete files and directories in PowerShell.</span></span>

<span data-ttu-id="b9b53-115">As unidades do **sistema de arquivos** são um namespace hierárquico que contém os diretórios e arquivos em seu computador.</span><span class="sxs-lookup"><span data-stu-id="b9b53-115">The **FileSystem** drives are a hierarchical namespace containing the directories and files on your computer.</span></span> <span data-ttu-id="b9b53-116">Uma unidade de **sistema de arquivos** pode ser uma unidade lógica ou físicos, um diretório ou um compartilhamento de rede mapeado.</span><span class="sxs-lookup"><span data-stu-id="b9b53-116">A **FileSystem** drive can be a logical or phsyical drive, directory, or mapped network share.</span></span>

<span data-ttu-id="b9b53-117">O provedor **FileSystem** oferece suporte aos seguintes cmdlets, que são abordados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b9b53-117">The **FileSystem** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="b9b53-118">Get-Location</span><span class="sxs-lookup"><span data-stu-id="b9b53-118">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="b9b53-119">Set-Location</span><span class="sxs-lookup"><span data-stu-id="b9b53-119">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="b9b53-120">Get-Item</span><span class="sxs-lookup"><span data-stu-id="b9b53-120">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="b9b53-121">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="b9b53-121">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="b9b53-122">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="b9b53-122">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="b9b53-123">Move-Item</span><span class="sxs-lookup"><span data-stu-id="b9b53-123">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="b9b53-124">New-Item</span><span class="sxs-lookup"><span data-stu-id="b9b53-124">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="b9b53-125">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="b9b53-125">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="b9b53-126">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b9b53-126">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="b9b53-127">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b9b53-127">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="b9b53-128">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="b9b53-128">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="b9b53-129">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b9b53-129">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="b9b53-130">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="b9b53-130">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="b9b53-131">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b9b53-131">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="b9b53-132">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="b9b53-132">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="b9b53-133">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="b9b53-133">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)
- [<span data-ttu-id="b9b53-134">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="b9b53-134">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [<span data-ttu-id="b9b53-135">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="b9b53-135">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="b9b53-136">Tipos expostos por este provedor</span><span class="sxs-lookup"><span data-stu-id="b9b53-136">Types exposed by this provider</span></span>

<span data-ttu-id="b9b53-137">Os arquivos são instâncias da classe [System. IO. FileInfo](/dotnet/api/system.io.fileinfo) .</span><span class="sxs-lookup"><span data-stu-id="b9b53-137">Files are instances of the [System.IO.FileInfo](/dotnet/api/system.io.fileinfo) class.</span></span>  <span data-ttu-id="b9b53-138">Os diretórios são instâncias da classe [System. IO. DirectoryInfo](/dotnet/api/system.io.directoryinfo) .</span><span class="sxs-lookup"><span data-stu-id="b9b53-138">Directories are instances of the [System.IO.DirectoryInfo](/dotnet/api/system.io.directoryinfo) class.</span></span>

## <a name="navigating-the-filesystem-drives"></a><span data-ttu-id="b9b53-139">Navegando pelas unidades do sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="b9b53-139">Navigating the FileSystem drives</span></span>

<span data-ttu-id="b9b53-140">O provedor **FileSystem** expõe seus armazenamentos de dados mapeando quaisquer unidades lógicas no computador como unidades do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9b53-140">The **FileSystem** provider exposes its data stores by mapping any logical drives on the computer as PowerShell drives.</span></span> <span data-ttu-id="b9b53-141">Para trabalhar com uma unidade de **sistema de arquivos** , você pode alterar seu local para uma unidade utoridades o nome da unidade seguido por dois-pontos ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="b9b53-141">To work with a **FileSystem** drive you can change your location to a drive uing the drive name followed by a colon (`:`).</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="b9b53-142">Você também pode trabalhar com o provedor **FileSystem** de qualquer outra unidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9b53-142">You can also work with the **FileSystem** provider from any other PowerShell drive.</span></span> <span data-ttu-id="b9b53-143">Para fazer referência a um arquivo ou diretório de outro local, use o nome da unidade ( `C:` , `D:` ,...) no caminho.</span><span class="sxs-lookup"><span data-stu-id="b9b53-143">To reference a file or directory from another location, use the drive name (`C:`, `D:`, ...) in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="b9b53-144">O PowerShell usa aliases para permitir a você uma maneira familiar de trabalhar com caminhos de provedor.</span><span class="sxs-lookup"><span data-stu-id="b9b53-144">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="b9b53-145">Comandos como `dir` e `ls` agora são aliases para [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` é um alias para [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="b9b53-145">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="b9b53-146">e `pwd` é um alias para [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="b9b53-146">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-files-and-directories"></a><span data-ttu-id="b9b53-147">Obtendo arquivos e diretórios</span><span class="sxs-lookup"><span data-stu-id="b9b53-147">Getting files and directories</span></span>

<span data-ttu-id="b9b53-148">O `Get-ChildItem` cmdlet retorna todos os arquivos e diretórios no local atual.</span><span class="sxs-lookup"><span data-stu-id="b9b53-148">The `Get-ChildItem` cmdlet returns all files and directories in the current location.</span></span> <span data-ttu-id="b9b53-149">Você pode especificar um caminho diferente para pesquisar e usar parâmetros internos para filtrar e controlar a profundidade da recursão.</span><span class="sxs-lookup"><span data-stu-id="b9b53-149">You can specify a different path to search and use built in parameters to filter and control the recursion depth.</span></span>

```powershell
Get-ChildItem
```

<span data-ttu-id="b9b53-150">Para ler mais sobre o uso de cmdlet, consulte [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem).</span><span class="sxs-lookup"><span data-stu-id="b9b53-150">To read more about cmdlet usage, see [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem).</span></span>

## <a name="copying-files-and-directories"></a><span data-ttu-id="b9b53-151">Copiando arquivos e diretórios</span><span class="sxs-lookup"><span data-stu-id="b9b53-151">Copying files and directories</span></span>

<span data-ttu-id="b9b53-152">O `Copy-Item` cmdlet copia arquivos e diretórios para um local que você especificar.</span><span class="sxs-lookup"><span data-stu-id="b9b53-152">The `Copy-Item` cmdlet copies files and directories to a location you specify.</span></span>
<span data-ttu-id="b9b53-153">Os parâmetros estão disponíveis para filtrar e recurse, semelhante a `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="b9b53-153">Parameters are available to filter and recurse, similar to `Get-ChildItem`.</span></span>

<span data-ttu-id="b9b53-154">O comando a seguir copia todos os arquivos e diretórios no caminho "C:\temp" \" para a pasta "C:\Windows\Temp".</span><span class="sxs-lookup"><span data-stu-id="b9b53-154">The following command copies all of the files and directories under the path "C:\temp\" to the folder "C:\Windows\Temp".</span></span>

```powershell
Copy-Item -Path C:\temp\* -Destination C:\Windows\Temp -Recurse -File
```

<span data-ttu-id="b9b53-155">`Copy-Item` substitui os arquivos no diretório de destino sem solicitar confirmação.</span><span class="sxs-lookup"><span data-stu-id="b9b53-155">`Copy-Item` overwrites files in the destination directory without prompting for confirmation.</span></span>

<span data-ttu-id="b9b53-156">Esse comando copia o `a.txt` arquivo do `C:\a` diretório para o `C:\a\bb` diretório.</span><span class="sxs-lookup"><span data-stu-id="b9b53-156">This command copies the `a.txt` file from the `C:\a` directory to the `C:\a\bb` directory.</span></span>

```powershell
Copy-Item -Path C:\a\a.txt -Destination C:\a\bb\a.txt
```

<span data-ttu-id="b9b53-157">Copia todos os diretórios e arquivos no `C:\a` diretório para o `C:\c` diretório.</span><span class="sxs-lookup"><span data-stu-id="b9b53-157">Copies all the directories and files in the `C:\a` directory to the `C:\c` directory.</span></span> <span data-ttu-id="b9b53-158">Se qualquer um dos diretórios para copiar já existir no diretório de destino, o comando falhará a menos que você especifique o parâmetro Force.</span><span class="sxs-lookup"><span data-stu-id="b9b53-158">If any of the directories to copy already exist in the destination directory, the command will fail unless you specify the Force parameter.</span></span>

```powershell
Copy-Item -Path C:\a\* -Destination C:\c -Recurse
```

<span data-ttu-id="b9b53-159">Para obter mais informações, consulte [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item).</span><span class="sxs-lookup"><span data-stu-id="b9b53-159">For more information, see [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item).</span></span>

## <a name="moving-files-and-directories"></a><span data-ttu-id="b9b53-160">Movendo arquivos e diretórios</span><span class="sxs-lookup"><span data-stu-id="b9b53-160">Moving files and directories</span></span>

<span data-ttu-id="b9b53-161">Esse comando move o `c.txt` arquivo no `C:\a` diretório para o `C:\a\aa` diretório:</span><span class="sxs-lookup"><span data-stu-id="b9b53-161">This command moves the `c.txt` file in the `C:\a` directory to the `C:\a\aa` directory:</span></span>

```powershell
Move-Item -Path C:\a\c.txt -Destination C:\a\aa
```

<span data-ttu-id="b9b53-162">O comando não substituirá automaticamente um arquivo existente que tenha o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="b9b53-162">The command will not automatically overwrite an existing file that has the same name.</span></span> <span data-ttu-id="b9b53-163">Para forçar o cmdlet a substituir um arquivo existente, especifique o parâmetro Force.</span><span class="sxs-lookup"><span data-stu-id="b9b53-163">To force the cmdlet to overwrite an existing file, specify the Force parameter.</span></span>

<span data-ttu-id="b9b53-164">Você não pode mover um diretório quando aquele diretório é o local atual.</span><span class="sxs-lookup"><span data-stu-id="b9b53-164">You cannot move a directory when that directory is the current location.</span></span> <span data-ttu-id="b9b53-165">Ao usar `Move-Item` o para mover o diretório no local atual, você verá esse erro.</span><span class="sxs-lookup"><span data-stu-id="b9b53-165">When you use `Move-Item` to move the directory at the current location, you see this error.</span></span>

```
C:\temp> Move-Item -Path C:\temp\ -Destination C:\Windows\Temp

Move-Item : Cannot move item because the item at 'C:\temp\' is in use.
At line:1 char:1
+ Move-Item C:\temp\ C:\temp2\
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Move-Item], PSInvalidOperationException
    + FullyQualifiedErrorId : InvalidOperation,Microsoft.PowerShell.Commands.MoveItemCommand
```

## <a name="managing-file-content"></a><span data-ttu-id="b9b53-166">Gerenciando conteúdo do arquivo</span><span class="sxs-lookup"><span data-stu-id="b9b53-166">Managing file content</span></span>

### <a name="get-the-content-of-a-file"></a><span data-ttu-id="b9b53-167">Obter o conteúdo de um arquivo</span><span class="sxs-lookup"><span data-stu-id="b9b53-167">Get the content of a file</span></span>

<span data-ttu-id="b9b53-168">Esse comando obtém o conteúdo do arquivo "Test.txt" e os exibe no console do.</span><span class="sxs-lookup"><span data-stu-id="b9b53-168">This command gets the contents of the "Test.txt" file and displays them in the console.</span></span>

```powershell
Get-Content -Path Test.txt
```

<span data-ttu-id="b9b53-169">Você pode canalizar o conteúdo do arquivo para outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b9b53-169">You can pipe the contents of the file to another cmdlet.</span></span> <span data-ttu-id="b9b53-170">Por exemplo, o comando a seguir lê o conteúdo do `Test.txt` arquivo e, em seguida, fornece-os como entrada para o cmdlet [ConvertTo-HTML](xref:Microsoft.PowerShell.Utility.ConvertTo-Html) :</span><span class="sxs-lookup"><span data-stu-id="b9b53-170">For example, the following command reads the contents of the `Test.txt` file and then supplies them as input to the [ConvertTo-Html](xref:Microsoft.PowerShell.Utility.ConvertTo-Html) cmdlet:</span></span>

```powershell
Get-Content -Path Test.txt | ConvertTo-Html
```

<span data-ttu-id="b9b53-171">Você também pode recuperar o conteúdo de um arquivo prefixando seu caminho de provedor com o cifrão ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="b9b53-171">You can also retrieve the content of a file by prefixing its provider path with the dollar sign (`$`).</span></span> <span data-ttu-id="b9b53-172">O caminho deve ser colocado entre chaves devido a restrições de nomenclatura de variáveis.</span><span class="sxs-lookup"><span data-stu-id="b9b53-172">The path must be enclosed in curly braces due to variable naming restrictions.</span></span> <span data-ttu-id="b9b53-173">Para obter mais informações, consulte [about_Variables](about_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b9b53-173">For more information, see [about_Variables](about_Variables.md).</span></span>

```powershell
${C:\Windows\System32\Drivers\etc\hosts}
```

### <a name="add-content-to-a-file"></a><span data-ttu-id="b9b53-174">Adicionar conteúdo a um arquivo</span><span class="sxs-lookup"><span data-stu-id="b9b53-174">Add content to a file</span></span>

<span data-ttu-id="b9b53-175">Esse comando acrescenta a cadeia de caracteres "conteúdo do teste" ao `Test.txt` arquivo:</span><span class="sxs-lookup"><span data-stu-id="b9b53-175">This command appends the "test content" string to the `Test.txt` file:</span></span>

```powershell
Add-Content -Path test.txt -Value "test content"
```

<span data-ttu-id="b9b53-176">O conteúdo existente no `Test.txt` arquivo não é excluído.</span><span class="sxs-lookup"><span data-stu-id="b9b53-176">The existing content in the `Test.txt` file is not deleted.</span></span>

### <a name="replace-the-content-of-a-file"></a><span data-ttu-id="b9b53-177">Substituir o conteúdo de um arquivo</span><span class="sxs-lookup"><span data-stu-id="b9b53-177">Replace the content of a file</span></span>

<span data-ttu-id="b9b53-178">Esse comando substitui o conteúdo do `Test.txt` arquivo pela cadeia de caracteres "conteúdo do teste":</span><span class="sxs-lookup"><span data-stu-id="b9b53-178">This command replaces the contents of the `Test.txt` file with the "test content" string:</span></span>

```powershell
Set-Content -Path test.txt -Value "test content"
```

<span data-ttu-id="b9b53-179">Ele substitui o conteúdo de `Test.txt` .</span><span class="sxs-lookup"><span data-stu-id="b9b53-179">It overwrites the contents of `Test.txt`.</span></span> <span data-ttu-id="b9b53-180">Você pode usar o parâmetro **Value** do cmdlet [New-Item](xref:Microsoft.PowerShell.Management.New-Item) para adicionar conteúdo a um arquivo ao criá-lo.</span><span class="sxs-lookup"><span data-stu-id="b9b53-180">You can use the **Value** parameter of the [New-Item](xref:Microsoft.PowerShell.Management.New-Item) cmdlet to add content to a file when you create it.</span></span>

### <a name="loop-through-the-contents-of-a-file"></a><span data-ttu-id="b9b53-181">Executar um loop no conteúdo de um arquivo</span><span class="sxs-lookup"><span data-stu-id="b9b53-181">Loop through the contents of a file</span></span>

<span data-ttu-id="b9b53-182">Por padrão, o `Get-Content` cmdlet usa o caractere de final de linha como seu delimitador, portanto, ele obtém um arquivo como uma coleção de cadeias de caracteres, com cada linha como uma cadeia de caracteres no arquivo.</span><span class="sxs-lookup"><span data-stu-id="b9b53-182">By default, the `Get-Content` cmdlet uses the end-of-line character as its delimiter, so it gets a file as a collection of strings, with each line as one string in the file.</span></span>

<span data-ttu-id="b9b53-183">Você pode usar o `-Delimiter` parâmetro para especificar um delimitador alternativo.</span><span class="sxs-lookup"><span data-stu-id="b9b53-183">You can use the `-Delimiter` parameter to specify an alternate delimiter.</span></span> <span data-ttu-id="b9b53-184">Se você defini-lo para os caracteres que indicam o final de uma seção ou o início da próxima seção, você pode dividir o arquivo em partes lógicas.</span><span class="sxs-lookup"><span data-stu-id="b9b53-184">If you set it to the characters that denote the end of a section or the beginning of the next section, you can split the file into logical parts.</span></span>

<span data-ttu-id="b9b53-185">O primeiro comando obtém o `Employees.txt` arquivo e o divide em seções, cada um dos quais termina com as palavras "fim do registro do funcionário" e salva-o na `$e` variável.</span><span class="sxs-lookup"><span data-stu-id="b9b53-185">The first command gets the `Employees.txt` file and splits it into sections, each of which ends with the words "End of Employee Record" and it saves it in the `$e` variable.</span></span>

<span data-ttu-id="b9b53-186">O segundo comando usa a notação de matriz para obter o primeiro item na coleção no `$e` .</span><span class="sxs-lookup"><span data-stu-id="b9b53-186">The second command uses array notation to get the first item in the collection in `$e`.</span></span> <span data-ttu-id="b9b53-187">Ele usa um índice de 0, porque as matrizes do PowerShell são baseadas em zero.</span><span class="sxs-lookup"><span data-stu-id="b9b53-187">It uses an index of 0, because PowerShell arrays are zero-based.</span></span>

<span data-ttu-id="b9b53-188">Para obter mais informações sobre o `Get-Content` cmdlet, consulte o tópico da ajuda para o [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content).</span><span class="sxs-lookup"><span data-stu-id="b9b53-188">For more information about `Get-Content` cmdlet, see the help topic for the [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content).</span></span>

<span data-ttu-id="b9b53-189">Para obter mais informações sobre matrizes, consulte [about_Arrays](../About/about_Arrays.md).</span><span class="sxs-lookup"><span data-stu-id="b9b53-189">For more information about arrays, see [about_Arrays](../About/about_Arrays.md).</span></span>

```powershell
$e = Get-Content c:\test\employees.txt -Delimited "End Of Employee Record"
$e[0]
```

## <a name="managing-security-descriptors"></a><span data-ttu-id="b9b53-190">Gerenciando descritores de segurança</span><span class="sxs-lookup"><span data-stu-id="b9b53-190">Managing security descriptors</span></span>

### <a name="view-the-acl-for-a-file"></a><span data-ttu-id="b9b53-191">Exibir a ACL para um arquivo</span><span class="sxs-lookup"><span data-stu-id="b9b53-191">View the ACL for a file</span></span>

<span data-ttu-id="b9b53-192">Esse comando retorna um objeto [System. Security. AccessControl. FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) :</span><span class="sxs-lookup"><span data-stu-id="b9b53-192">This command returns a [System.Security.AccessControl.FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) object:</span></span>

```powershell
Get-Acl -Path test.txt | Format-List -Property *
```

<span data-ttu-id="b9b53-193">Para obter mais informações sobre esse objeto, redirecione o comando para o cmdlet [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member) .</span><span class="sxs-lookup"><span data-stu-id="b9b53-193">For more information about this object, pipe the command to the [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member) cmdlet.</span></span> <span data-ttu-id="b9b53-194">Ou então, consulte "classe[FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) " na biblioteca do MSDN (Microsoft Developer Network).</span><span class="sxs-lookup"><span data-stu-id="b9b53-194">Or, see "[FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) Class" in the MSDN (Microsoft Developer Network) library.</span></span>

### <a name="modify-the-acl-for-a-file"></a><span data-ttu-id="b9b53-195">Modificar a ACL de um arquivo</span><span class="sxs-lookup"><span data-stu-id="b9b53-195">Modify the ACL for a file</span></span>

### <a name="create-and-set-an-acl-for-a-file"></a><span data-ttu-id="b9b53-196">Criar e definir uma ACL para um arquivo</span><span class="sxs-lookup"><span data-stu-id="b9b53-196">Create and set an ACL for a file</span></span>

## <a name="creating-files-and-directories"></a><span data-ttu-id="b9b53-197">Criando arquivos e diretórios</span><span class="sxs-lookup"><span data-stu-id="b9b53-197">Creating files and directories</span></span>

### <a name="create-a-directory"></a><span data-ttu-id="b9b53-198">Criar um diretório</span><span class="sxs-lookup"><span data-stu-id="b9b53-198">Create a directory</span></span>

<span data-ttu-id="b9b53-199">Este comando cria o `logfiles` diretório na `C` unidade:</span><span class="sxs-lookup"><span data-stu-id="b9b53-199">This command creates the `logfiles` directory on the `C` drive:</span></span>

```powershell
New-Item -Path c:\ -Name logfiles -Type directory
```

<span data-ttu-id="b9b53-200">O PowerShell também inclui uma `mkdir` função (alias `md` ) que usa o cmdlet [New-Item](xref:Microsoft.PowerShell.Management.New-Item) para criar um novo diretório.</span><span class="sxs-lookup"><span data-stu-id="b9b53-200">PowerShell also includes a `mkdir` function (alias `md`) that uses the [New-Item](xref:Microsoft.PowerShell.Management.New-Item) cmdlet to create a new directory.</span></span>

### <a name="create-a-file"></a><span data-ttu-id="b9b53-201">Criar um arquivo</span><span class="sxs-lookup"><span data-stu-id="b9b53-201">Create a file</span></span>

<span data-ttu-id="b9b53-202">Esse comando cria o `log2.txt` arquivo no `C:\logfiles` diretório e, em seguida, adiciona a cadeia de caracteres "log de teste" ao arquivo:</span><span class="sxs-lookup"><span data-stu-id="b9b53-202">This command creates the `log2.txt` file in the `C:\logfiles` directory and then adds the "test log" string to the file:</span></span>

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file
```

### <a name="create-a-file-with-content"></a><span data-ttu-id="b9b53-203">Crie um arquivo com conteúdo</span><span class="sxs-lookup"><span data-stu-id="b9b53-203">Create a file with content</span></span>

<span data-ttu-id="b9b53-204">Cria um arquivo chamado `log2.txt` no `C:\logfiles` diretório e adiciona a cadeia de caracteres "log de teste" ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="b9b53-204">Creates a file called `log2.txt` in the `C:\logfiles` directory and adds the string "test log" to the file.</span></span>

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file -Value "test log"
```

## <a name="renaming-files-and-directories"></a><span data-ttu-id="b9b53-205">Renomeando arquivos e diretórios</span><span class="sxs-lookup"><span data-stu-id="b9b53-205">Renaming files and directories</span></span>

### <a name="rename-a-file"></a><span data-ttu-id="b9b53-206">Renomear um arquivo</span><span class="sxs-lookup"><span data-stu-id="b9b53-206">Rename a file</span></span>

<span data-ttu-id="b9b53-207">Esse comando renomeia o `a.txt` arquivo no `C:\a` diretório para `b.txt` :</span><span class="sxs-lookup"><span data-stu-id="b9b53-207">This command renames the `a.txt` file in the `C:\a` directory to `b.txt`:</span></span>

```powershell
Rename-Item -Path c:\a\a.txt -NewName b.txt
```

### <a name="rename-a-directory"></a><span data-ttu-id="b9b53-208">Renomear um diretório</span><span class="sxs-lookup"><span data-stu-id="b9b53-208">Rename a directory</span></span>

<span data-ttu-id="b9b53-209">Esse comando renomeia o `C:\a\cc` diretório para `C:\a\dd` :</span><span class="sxs-lookup"><span data-stu-id="b9b53-209">This command renames the `C:\a\cc` directory to `C:\a\dd`:</span></span>

```powershell
Rename-Item -Path c:\a\cc -NewName dd
```

## <a name="deleting-files-and-directories"></a><span data-ttu-id="b9b53-210">Excluindo arquivos e diretórios</span><span class="sxs-lookup"><span data-stu-id="b9b53-210">Deleting files and directories</span></span>

### <a name="delete-a-file"></a><span data-ttu-id="b9b53-211">Excluir um arquivo</span><span class="sxs-lookup"><span data-stu-id="b9b53-211">Delete a file</span></span>

<span data-ttu-id="b9b53-212">Este comando exclui o `Test.txt` arquivo no diretório atual:</span><span class="sxs-lookup"><span data-stu-id="b9b53-212">This command deletes the `Test.txt` file in the current directory:</span></span>

```powershell
Remove-Item -Path test.txt
```

### <a name="delete-files-using-wildcards"></a><span data-ttu-id="b9b53-213">Excluir arquivos usando curingas</span><span class="sxs-lookup"><span data-stu-id="b9b53-213">Delete files using wildcards</span></span>

<span data-ttu-id="b9b53-214">Este comando exclui todos os arquivos no diretório atual que têm a `.xml` extensão de nome de arquivo:</span><span class="sxs-lookup"><span data-stu-id="b9b53-214">This command deletes all the files in the current directory that have the `.xml` file name extension:</span></span>

```powershell
Remove-Item -Path *.xml
```

## <a name="starting-a-program-by-invoking-an-associated-file"></a><span data-ttu-id="b9b53-215">Iniciando um programa invocando um arquivo associado</span><span class="sxs-lookup"><span data-stu-id="b9b53-215">Starting a program by invoking an associated file</span></span>

### <a name="invoke-a-file"></a><span data-ttu-id="b9b53-216">Invocar um arquivo</span><span class="sxs-lookup"><span data-stu-id="b9b53-216">Invoke a file</span></span>

<span data-ttu-id="b9b53-217">O primeiro comando usa o cmdlet [Get-Service](xref:Microsoft.PowerShell.Management.Get-Service) para obter informações sobre serviços locais.</span><span class="sxs-lookup"><span data-stu-id="b9b53-217">The first command uses the [Get-Service](xref:Microsoft.PowerShell.Management.Get-Service) cmdlet to get information about local services.</span></span>

<span data-ttu-id="b9b53-218">Ele canaliza as informações para o cmdlet [Export-CSV](xref:Microsoft.PowerShell.Utility.Export-Csv) e, em seguida, armazena essas informações no `Services.csv` arquivo.</span><span class="sxs-lookup"><span data-stu-id="b9b53-218">It pipes the information to the [Export-Csv](xref:Microsoft.PowerShell.Utility.Export-Csv) cmdlet and then stores that information in the `Services.csv` file.</span></span>

<span data-ttu-id="b9b53-219">O segundo comando usa [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item) para abrir o `services.csv` arquivo no programa associado à `.csv` extensão:</span><span class="sxs-lookup"><span data-stu-id="b9b53-219">The second command uses [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item) to open the `services.csv` file in the program associated with the `.csv` extension:</span></span>

```powershell
Get-Service | Export-Csv -Path services.csv
Invoke-Item -Path services.csv
```

## <a name="getting-files-and-folders-with-specified-attributes"></a><span data-ttu-id="b9b53-220">Obtendo arquivos e pastas com atributos especificados</span><span class="sxs-lookup"><span data-stu-id="b9b53-220">Getting files and folders with specified attributes</span></span>

### <a name="get-system-files"></a><span data-ttu-id="b9b53-221">Obter arquivos do sistema</span><span class="sxs-lookup"><span data-stu-id="b9b53-221">Get System files</span></span>

<span data-ttu-id="b9b53-222">Esse comando obtém arquivos do sistema no diretório atual e em seus subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="b9b53-222">This command gets system files in the current directory and its subdirectories.</span></span>

<span data-ttu-id="b9b53-223">Ele usa o `-File` parâmetro para obter apenas os arquivos (não os diretórios) e o `-System` parâmetro para obter apenas os itens com o atributo "System".</span><span class="sxs-lookup"><span data-stu-id="b9b53-223">It uses the `-File` parameter to get only files (not directories) and the `-System` parameter to get only items with the "system" attribute.</span></span>

<span data-ttu-id="b9b53-224">Ele usa o `-Recurse` parâmetro para obter os itens no diretório atual e em todos os subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="b9b53-224">It uses the `-Recurse` parameter to get the items in the current directory and all subdirectories.</span></span>

```powershell
Get-ChildItem -File -System -Recurse
```

### <a name="get-hidden-files"></a><span data-ttu-id="b9b53-225">Obter arquivos ocultos</span><span class="sxs-lookup"><span data-stu-id="b9b53-225">Get Hidden files</span></span>

<span data-ttu-id="b9b53-226">Esse comando obtém todos os arquivos, inclusive arquivos ocultos, no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="b9b53-226">This command gets all files, including hidden files, in the current directory.</span></span>

<span data-ttu-id="b9b53-227">Ele usa o parâmetro **Attributes** com dois valores, `!Directory+Hidden` , que obtém arquivos ocultos e `!Directory` , que obtém todos os outros arquivos.</span><span class="sxs-lookup"><span data-stu-id="b9b53-227">It uses the **Attributes** parameter with two values, `!Directory+Hidden`, which gets hidden files, and `!Directory`, which gets all other files.</span></span>

```powershell
Get-ChildItem -Attributes !Directory,!Directory+Hidden
```

<span data-ttu-id="b9b53-228">`dir -att !d,!d+h` é o equivalente deste comando.</span><span class="sxs-lookup"><span data-stu-id="b9b53-228">`dir -att !d,!d+h` is the equivalent of this command.</span></span>

### <a name="get-compressed-and-encrypted-files"></a><span data-ttu-id="b9b53-229">Obter arquivos compactados e criptografados</span><span class="sxs-lookup"><span data-stu-id="b9b53-229">Get Compressed and Encrypted files</span></span>

<span data-ttu-id="b9b53-230">Esse comando obtém os arquivos no diretório atual que são compactados ou criptografados.</span><span class="sxs-lookup"><span data-stu-id="b9b53-230">This command gets files in the current directory that are either compressed or encrypted.</span></span>

<span data-ttu-id="b9b53-231">Ele usa o `-Attributes` parâmetro com dois valores, `Compressed` e `Encrypted` .</span><span class="sxs-lookup"><span data-stu-id="b9b53-231">It uses the `-Attributes` parameter with two values, `Compressed` and `Encrypted`.</span></span> <span data-ttu-id="b9b53-232">Os valores são separados por uma vírgula `,` que representa o operador "or".</span><span class="sxs-lookup"><span data-stu-id="b9b53-232">The values are separated by a comma `,` which represents the "OR" operator.</span></span>

```powershell
Get-ChildItem -Attributes Compressed,Encrypted
```

## <a name="dynamic-parameters"></a><span data-ttu-id="b9b53-233">Parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="b9b53-233">Dynamic parameters</span></span>

<span data-ttu-id="b9b53-234">Parâmetros dinâmicos são parâmetros de cmdlet que são adicionados por um provedor do PowerShell e estão disponíveis somente quando o cmdlet está sendo usado na unidade habilitada para provedor.</span><span class="sxs-lookup"><span data-stu-id="b9b53-234">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="encoding-microsoftpowershellcommandsfilesystemcmdletproviderencoding"></a><span data-ttu-id="b9b53-235">Encoding \<Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding\></span><span class="sxs-lookup"><span data-stu-id="b9b53-235">Encoding \<Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding\></span></span>

<span data-ttu-id="b9b53-236">Especifica a codificação do arquivo.</span><span class="sxs-lookup"><span data-stu-id="b9b53-236">Specifies the file encoding.</span></span> <span data-ttu-id="b9b53-237">O padrão é ASCII.</span><span class="sxs-lookup"><span data-stu-id="b9b53-237">The default is ASCII.</span></span>

- <span data-ttu-id="b9b53-238">**ASCII** : usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="b9b53-238">**ASCII** :  Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="b9b53-239">**BigEndianUnicode** : codifica em formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="b9b53-239">**BigEndianUnicode** :  Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="b9b53-240">**String** : usa o tipo de codificação para uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b9b53-240">**String** :  Uses the encoding type for a string.</span></span>
- <span data-ttu-id="b9b53-241">**Unicode** : codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="b9b53-241">**Unicode** :  Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="b9b53-242">**UTF7** : codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="b9b53-242">**UTF7** :   Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="b9b53-243">**UTF8** : codifica no formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b9b53-243">**UTF8** :  Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="b9b53-244">**UTF8BOM** : codifica em formato UTF-8 com marca de ordem de byte (bom)</span><span class="sxs-lookup"><span data-stu-id="b9b53-244">**UTF8BOM** : Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="b9b53-245">**UF8NOBOM** : codifica em formato UTF-8 sem marca de ordem de byte (bom)</span><span class="sxs-lookup"><span data-stu-id="b9b53-245">**UF8NOBOM** : Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="b9b53-246">**UTF32** : codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="b9b53-246">**UTF32** :  Encodes in UTF-32 format.</span></span>
- <span data-ttu-id="b9b53-247">**Padrão** : codifica na página de código padrão instalada.</span><span class="sxs-lookup"><span data-stu-id="b9b53-247">**Default** : Encodes in the default installed code page.</span></span>
- <span data-ttu-id="b9b53-248">**OEM** : usa a codificação padrão para MS-dos e programas de console.</span><span class="sxs-lookup"><span data-stu-id="b9b53-248">**OEM** : Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="b9b53-249">**Desconhecido** : o tipo de codificação é desconhecido ou inválido.</span><span class="sxs-lookup"><span data-stu-id="b9b53-249">**Unknown** :  The encoding type is unknown or invalid.</span></span> <span data-ttu-id="b9b53-250">Os dados podem ser tratados como binários.</span><span class="sxs-lookup"><span data-stu-id="b9b53-250">The data can be treated as binary.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="b9b53-251">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="b9b53-251">Cmdlets supported</span></span>

- [<span data-ttu-id="b9b53-252">Add-Content</span><span class="sxs-lookup"><span data-stu-id="b9b53-252">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="b9b53-253">Get-Content</span><span class="sxs-lookup"><span data-stu-id="b9b53-253">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="b9b53-254">Set-Content</span><span class="sxs-lookup"><span data-stu-id="b9b53-254">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="delimiter-systemstring"></a><span data-ttu-id="b9b53-255">Delimiter \<System.String\></span><span class="sxs-lookup"><span data-stu-id="b9b53-255">Delimiter \<System.String\></span></span>

<span data-ttu-id="b9b53-256">Especifica o delimitador que o [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) usa para dividir o arquivo em objetos enquanto ele lê.</span><span class="sxs-lookup"><span data-stu-id="b9b53-256">Specifies the delimiter that [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) uses to divide the file into objects while it reads.</span></span>

<span data-ttu-id="b9b53-257">O padrão é `\n` , o caractere de fim de linha.</span><span class="sxs-lookup"><span data-stu-id="b9b53-257">The default is `\n`, the end-of-line character.</span></span>

<span data-ttu-id="b9b53-258">Ao ler um arquivo de texto, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) retorna uma coleção de objetos String, cada um dos quais termina com o caractere delimitador.</span><span class="sxs-lookup"><span data-stu-id="b9b53-258">When reading a text file, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) returns a collection of string objects, each of which ends with the delimiter character.</span></span>

<span data-ttu-id="b9b53-259">A inserção de um delimitador que não existe no arquivo, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) retorna o arquivo inteiro como um objeto único e não delimitado.</span><span class="sxs-lookup"><span data-stu-id="b9b53-259">Entering a delimiter that does not exist in the file, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) returns the entire file as a single, un-delimited object.</span></span>

<span data-ttu-id="b9b53-260">Você pode usar esse parâmetro para dividir um arquivo grande em arquivos menores, especificando um separador de arquivo, como "Final de exemplo," como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="b9b53-260">You can use this parameter to split a large file into smaller files by specifying a file separator, such as "End of Example", as the delimiter.</span></span> <span data-ttu-id="b9b53-261">O delimitador é preservado (não descartado) e se torna o último item em cada seção do arquivo.</span><span class="sxs-lookup"><span data-stu-id="b9b53-261">The delimiter is preserved (not discarded) and becomes the last item in each file section.</span></span>

> [!NOTE]
> <span data-ttu-id="b9b53-262">Atualmente, quando o valor do `-Delimiter` parâmetro é uma cadeia de caracteres vazia, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) não retorna nada.</span><span class="sxs-lookup"><span data-stu-id="b9b53-262">Currently, when the value of the `-Delimiter` parameter is an empty string, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) does not return anything.</span></span>
> <span data-ttu-id="b9b53-263">Este é um problema conhecido.</span><span class="sxs-lookup"><span data-stu-id="b9b53-263">This is a known issue.</span></span> <span data-ttu-id="b9b53-264">Para forçar o [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) a retornar o arquivo inteiro como uma única cadeia de caracteres não delimitada, insira um valor que não existe no arquivo.</span><span class="sxs-lookup"><span data-stu-id="b9b53-264">To force [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) to return the entire file as a single, undelimited string, enter a value that does not exist in the file.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="b9b53-265">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="b9b53-265">Cmdlets supported</span></span>

- [<span data-ttu-id="b9b53-266">Get-Content</span><span class="sxs-lookup"><span data-stu-id="b9b53-266">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="wait-systemmanagementautomationswitchparameter"></a><span data-ttu-id="b9b53-267">Wait \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="b9b53-267">Wait \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="b9b53-268">Aguarda o conteúdo a ser anexado ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="b9b53-268">Waits for content to be appended to the file.</span></span> <span data-ttu-id="b9b53-269">Se o conteúdo será anexado, ele retorna o conteúdo anexado.</span><span class="sxs-lookup"><span data-stu-id="b9b53-269">If content is appended, it returns the appended content.</span></span> <span data-ttu-id="b9b53-270">Se o conteúdo tiver sido alterado, ele retornará o arquivo inteiro.</span><span class="sxs-lookup"><span data-stu-id="b9b53-270">If the content has changed, it returns the entire file.</span></span>

<span data-ttu-id="b9b53-271">Ao aguardar, o [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) verifica o arquivo uma vez por segundo até você interrompê-lo, por exemplo, pressionando CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="b9b53-271">When waiting, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) checks the file once each second until you interrupt it, such as by pressing CTRL+C.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="b9b53-272">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="b9b53-272">Cmdlets supported</span></span>

- [<span data-ttu-id="b9b53-273">Get-Content</span><span class="sxs-lookup"><span data-stu-id="b9b53-273">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="attributes-flagsexpression"></a><span data-ttu-id="b9b53-274">Attributes \<FlagsExpression\></span><span class="sxs-lookup"><span data-stu-id="b9b53-274">Attributes \<FlagsExpression\></span></span>

<span data-ttu-id="b9b53-275">Obtém os arquivos e pastas com os atributos especificados.</span><span class="sxs-lookup"><span data-stu-id="b9b53-275">Gets files and folders with the specified attributes.</span></span> <span data-ttu-id="b9b53-276">Esse parâmetro dá suporte a todos os atributos e permite que você especifique combinações complexas de atributos.</span><span class="sxs-lookup"><span data-stu-id="b9b53-276">This parameter supports all attributes and lets you specify complex combinations of attributes.</span></span>

<span data-ttu-id="b9b53-277">O `-Attributes` parâmetro foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b9b53-277">The `-Attributes` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="b9b53-278">O `-Attributes` parâmetro oferece suporte aos seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="b9b53-278">The `-Attributes` parameter supports the following attributes:</span></span>

- <span data-ttu-id="b9b53-279">**Arquivar**</span><span class="sxs-lookup"><span data-stu-id="b9b53-279">**Archive**</span></span>
- <span data-ttu-id="b9b53-280">**Compactado**</span><span class="sxs-lookup"><span data-stu-id="b9b53-280">**Compressed**</span></span>
- <span data-ttu-id="b9b53-281">**Dispositivo**</span><span class="sxs-lookup"><span data-stu-id="b9b53-281">**Device**</span></span>
- <span data-ttu-id="b9b53-282">**Diretório**</span><span class="sxs-lookup"><span data-stu-id="b9b53-282">**Directory**</span></span>
- <span data-ttu-id="b9b53-283">**Criptografado**</span><span class="sxs-lookup"><span data-stu-id="b9b53-283">**Encrypted**</span></span>
- <span data-ttu-id="b9b53-284">**Oculto**</span><span class="sxs-lookup"><span data-stu-id="b9b53-284">**Hidden**</span></span>
- <span data-ttu-id="b9b53-285">**Normal**</span><span class="sxs-lookup"><span data-stu-id="b9b53-285">**Normal**</span></span>
- <span data-ttu-id="b9b53-286">**NotContentIndexed**</span><span class="sxs-lookup"><span data-stu-id="b9b53-286">**NotContentIndexed**</span></span>
- <span data-ttu-id="b9b53-287">**Está**</span><span class="sxs-lookup"><span data-stu-id="b9b53-287">**Offline**</span></span>
- <span data-ttu-id="b9b53-288">**ReadOnly (somente-leitura)**</span><span class="sxs-lookup"><span data-stu-id="b9b53-288">**ReadOnly**</span></span>
- <span data-ttu-id="b9b53-289">**ReparsePoint**</span><span class="sxs-lookup"><span data-stu-id="b9b53-289">**ReparsePoint**</span></span>
- <span data-ttu-id="b9b53-290">**Escassfile**</span><span class="sxs-lookup"><span data-stu-id="b9b53-290">**SparseFile**</span></span>
- <span data-ttu-id="b9b53-291">**Sistema**</span><span class="sxs-lookup"><span data-stu-id="b9b53-291">**System**</span></span>
- <span data-ttu-id="b9b53-292">**Temporário**</span><span class="sxs-lookup"><span data-stu-id="b9b53-292">**Temporary**</span></span>

<span data-ttu-id="b9b53-293">Para obter uma descrição desses atributos, consulte a enumeração [FileAttributes](/dotnet/api/system.io.fileattributes) .</span><span class="sxs-lookup"><span data-stu-id="b9b53-293">For a description of these attributes, see the [FileAttributes](/dotnet/api/system.io.fileattributes) enumeration.</span></span>

<span data-ttu-id="b9b53-294">Use os seguintes operadores para combinar atributos.</span><span class="sxs-lookup"><span data-stu-id="b9b53-294">Use the following operators to combine attributes.</span></span>

- <span data-ttu-id="b9b53-295">`!` -Não</span><span class="sxs-lookup"><span data-stu-id="b9b53-295">`!` - NOT</span></span>
- <span data-ttu-id="b9b53-296">`+` -E</span><span class="sxs-lookup"><span data-stu-id="b9b53-296">`+` - AND</span></span>
- <span data-ttu-id="b9b53-297">`,` -OU</span><span class="sxs-lookup"><span data-stu-id="b9b53-297">`,` - OR</span></span>

<span data-ttu-id="b9b53-298">Nenhum espaço é permitido entre o operador e seus atributos.</span><span class="sxs-lookup"><span data-stu-id="b9b53-298">No spaces are permitted between an operator and its attribute.</span></span> <span data-ttu-id="b9b53-299">No entanto, os espaços são permitidos antes de vírgulas.</span><span class="sxs-lookup"><span data-stu-id="b9b53-299">However, spaces are permitted before commas.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="b9b53-300">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="b9b53-300">Cmdlets supported</span></span>

- [<span data-ttu-id="b9b53-301">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="b9b53-301">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="directory-systemmanagementautomationswitchparameter"></a><span data-ttu-id="b9b53-302">Directory \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="b9b53-302">Directory \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="b9b53-303">Obtém os diretórios (pastas).</span><span class="sxs-lookup"><span data-stu-id="b9b53-303">Gets directories (folders).</span></span>

<span data-ttu-id="b9b53-304">O `-Directory` parâmetro foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b9b53-304">The `-Directory` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="b9b53-305">Para obter apenas os diretórios, use o `-Directory` parâmetro e omita o `-File` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b9b53-305">To get only directories, use the `-Directory` parameter and omit the `-File` parameter.</span></span> <span data-ttu-id="b9b53-306">Para excluir diretórios, use o `-File` parâmetro e omita o `-Directory` parâmetro ou use o `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b9b53-306">To exclude directories, use the `-File` parameter and omit the `-Directory` parameter, or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="b9b53-307">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="b9b53-307">Cmdlets supported</span></span>

- [<span data-ttu-id="b9b53-308">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="b9b53-308">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="file-systemmanagementautomationswitchparameter"></a><span data-ttu-id="b9b53-309">File \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="b9b53-309">File \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="b9b53-310">Obtém arquivos.</span><span class="sxs-lookup"><span data-stu-id="b9b53-310">Gets files.</span></span>

<span data-ttu-id="b9b53-311">O `-File` parâmetro foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b9b53-311">The `-File` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="b9b53-312">Para obter apenas arquivos, use o `-File` parâmetro e omita o `-Directory` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b9b53-312">To get only files, use the `-File` parameter and omit the `-Directory` parameter.</span></span> <span data-ttu-id="b9b53-313">Para excluir arquivos, use o `-Directory` parâmetro e omita o `-File` parâmetro ou use o `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b9b53-313">To exclude files, use the `-Directory` parameter and omit the `-File` parameter, or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="b9b53-314">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="b9b53-314">Cmdlets supported</span></span>

- [<span data-ttu-id="b9b53-315">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="b9b53-315">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="hidden-systemmanagementautomationswitchparameter"></a><span data-ttu-id="b9b53-316">Hidden \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="b9b53-316">Hidden \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="b9b53-317">Obtém somente arquivos ocultos e diretórios (pastas).</span><span class="sxs-lookup"><span data-stu-id="b9b53-317">Gets only hidden files and directories (folders).</span></span> <span data-ttu-id="b9b53-318">Por padrão, [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) obtém somente itens não ocultos.</span><span class="sxs-lookup"><span data-stu-id="b9b53-318">By default, [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) gets only non-hidden items.</span></span>

<span data-ttu-id="b9b53-319">O `-Hidden` parâmetro foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b9b53-319">The `-Hidden` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="b9b53-320">Para obter apenas itens ocultos, use o `-Hidden` parâmetro, `h` seus `ah` aliases ou o valor **oculto** do `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b9b53-320">To get only hidden items, use the `-Hidden` parameter, its `h` or `ah` aliases, or the **Hidden** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="b9b53-321">Para excluir itens ocultos, omita o `-Hidden` parâmetro ou use o `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b9b53-321">To exclude hidden items, omit the `-Hidden` parameter or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="b9b53-322">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="b9b53-322">Cmdlets supported</span></span>

- [<span data-ttu-id="b9b53-323">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="b9b53-323">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="readonly-systemmanagementautomationswitchparameter"></a><span data-ttu-id="b9b53-324">ReadOnly \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="b9b53-324">ReadOnly \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="b9b53-325">Obtém somente arquivos somente leitura e diretórios (pastas).</span><span class="sxs-lookup"><span data-stu-id="b9b53-325">Gets only read-only files and directories (folders).</span></span>

<span data-ttu-id="b9b53-326">O `-ReadOnly` parâmetro foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b9b53-326">The `-ReadOnly` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="b9b53-327">Para obter somente itens somente leitura, use o `-ReadOnly` parâmetro, seu `ar` alias ou o valor **ReadOnly** do `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b9b53-327">To get only read-only items, use the `-ReadOnly` parameter, its `ar` alias, or the **ReadOnly** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="b9b53-328">Para excluir itens somente leitura, use o `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b9b53-328">To exclude read-only items, use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="b9b53-329">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="b9b53-329">Cmdlets supported</span></span>

- [<span data-ttu-id="b9b53-330">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="b9b53-330">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="system-systemmanagementautomationswitchparameter"></a><span data-ttu-id="b9b53-331">System \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="b9b53-331">System \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="b9b53-332">Obtém somente os arquivos do sistema e diretórios (pastas).</span><span class="sxs-lookup"><span data-stu-id="b9b53-332">Gets only system files and directories (folders).</span></span>

<span data-ttu-id="b9b53-333">O `-System` parâmetro foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b9b53-333">The `-System` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="b9b53-334">Para obter apenas arquivos e pastas do sistema, use o `-System` parâmetro, seu `as` alias ou o valor do **sistema** do `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b9b53-334">To get only system files and folders, use the `-System` parameter, its `as` alias, or the **System** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="b9b53-335">Para excluir arquivos e pastas do sistema, use o `-Attributes` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b9b53-335">To exclude system files and folders, use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="b9b53-336">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="b9b53-336">Cmdlets supported</span></span>

- [<span data-ttu-id="b9b53-337">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="b9b53-337">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="newerthan-systemdatetime"></a><span data-ttu-id="b9b53-338">NewerThan \<System.DateTime\></span><span class="sxs-lookup"><span data-stu-id="b9b53-338">NewerThan \<System.DateTime\></span></span>

<span data-ttu-id="b9b53-339">Retorna `$True` quando o `LastWriteTime` valor de um arquivo é maior que a data especificada.</span><span class="sxs-lookup"><span data-stu-id="b9b53-339">Returns `$True` when the `LastWriteTime` value of a file is greater than the specified date.</span></span> <span data-ttu-id="b9b53-340">Caso contrário, retornará `$False`.</span><span class="sxs-lookup"><span data-stu-id="b9b53-340">Otherwise, it returns `$False`.</span></span>

<span data-ttu-id="b9b53-341">Insira um objeto [DateTime](/dotnet/api/system.datetime) , como um que o cmdlet [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) retorna ou uma cadeia de caracteres que pode ser convertida em um objeto [DateTime](/dotnet/api/system.datetime) , como `"August 10, 2011 2:00 PM"` .</span><span class="sxs-lookup"><span data-stu-id="b9b53-341">Enter a [DateTime](/dotnet/api/system.datetime) object, such as one that the [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet returns, or a string that can be converted to a [DateTime](/dotnet/api/system.datetime) object, such as `"August 10, 2011 2:00 PM"`.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="b9b53-342">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="b9b53-342">Cmdlets supported</span></span>

- [<span data-ttu-id="b9b53-343">Test-Path</span><span class="sxs-lookup"><span data-stu-id="b9b53-343">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="olderthan-systemdatetime"></a><span data-ttu-id="b9b53-344">OlderThan \<System.DateTime\></span><span class="sxs-lookup"><span data-stu-id="b9b53-344">OlderThan \<System.DateTime\></span></span>

<span data-ttu-id="b9b53-345">Retorna `$True` quando o `LastWriteTime` valor de um arquivo é menor que a data especificada.</span><span class="sxs-lookup"><span data-stu-id="b9b53-345">Returns `$True` when the `LastWriteTime` value of a file is less than the specified date.</span></span> <span data-ttu-id="b9b53-346">Caso contrário, retornará `$False`.</span><span class="sxs-lookup"><span data-stu-id="b9b53-346">Otherwise, it returns `$False`.</span></span>

<span data-ttu-id="b9b53-347">Insira um objeto [DateTime](/dotnet/api/system.datetime) , como um que o cmdlet [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) retorna ou uma cadeia de caracteres que pode ser convertida em um objeto [DateTime](/dotnet/api/system.datetime) , como `"August 10, 2011 2:00 PM"` .</span><span class="sxs-lookup"><span data-stu-id="b9b53-347">Enter a [DateTime](/dotnet/api/system.datetime) object, such as one that the [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet returns, or a string that can be converted to a [DateTime](/dotnet/api/system.datetime) object, such as `"August 10, 2011 2:00 PM"`.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="b9b53-348">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="b9b53-348">Cmdlets supported</span></span>

- [<span data-ttu-id="b9b53-349">Test-Path</span><span class="sxs-lookup"><span data-stu-id="b9b53-349">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="stream-systemstring"></a><span data-ttu-id="b9b53-350">Stream \<System.String\></span><span class="sxs-lookup"><span data-stu-id="b9b53-350">Stream \<System.String\></span></span>

<span data-ttu-id="b9b53-351">Gerencia o fluxo de dados alternados.</span><span class="sxs-lookup"><span data-stu-id="b9b53-351">Manages alternate data streams.</span></span> <span data-ttu-id="b9b53-352">Insira o nome do fluxo.</span><span class="sxs-lookup"><span data-stu-id="b9b53-352">Enter the stream name.</span></span> <span data-ttu-id="b9b53-353">Curingas são permitidos somente em [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) para e os comandos [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item) em uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b9b53-353">Wildcards are permitted only in [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) for and [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item) commands in a file system drive.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="b9b53-354">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="b9b53-354">Cmdlets supported</span></span>

- [<span data-ttu-id="b9b53-355">Add-Content</span><span class="sxs-lookup"><span data-stu-id="b9b53-355">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="b9b53-356">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="b9b53-356">Clear-Content</span></span>](xref:Microsoft.PowerShell.Management.Clear-Content)
- [<span data-ttu-id="b9b53-357">Get-Item</span><span class="sxs-lookup"><span data-stu-id="b9b53-357">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="b9b53-358">Get-Content</span><span class="sxs-lookup"><span data-stu-id="b9b53-358">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="b9b53-359">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="b9b53-359">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="b9b53-360">Set-Content</span><span class="sxs-lookup"><span data-stu-id="b9b53-360">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="raw-switchparameter"></a><span data-ttu-id="b9b53-361">Raw \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="b9b53-361">Raw \<SwitchParameter\></span></span>

<span data-ttu-id="b9b53-362">Ignora os caracteres de nova linha.</span><span class="sxs-lookup"><span data-stu-id="b9b53-362">Ignores newline characters.</span></span> <span data-ttu-id="b9b53-363">Retorna o conteúdo como um único item.</span><span class="sxs-lookup"><span data-stu-id="b9b53-363">Returns contents as a single item.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="b9b53-364">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="b9b53-364">Cmdlets supported</span></span>

- [<span data-ttu-id="b9b53-365">Get-Content</span><span class="sxs-lookup"><span data-stu-id="b9b53-365">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

#### <a name="cmdlets-supported"></a><span data-ttu-id="b9b53-366">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="b9b53-366">Cmdlets supported</span></span>

- [<span data-ttu-id="b9b53-367">Get-Content</span><span class="sxs-lookup"><span data-stu-id="b9b53-367">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="itemtype-string"></a><span data-ttu-id="b9b53-368">ItemType \<String\></span><span class="sxs-lookup"><span data-stu-id="b9b53-368">ItemType \<String\></span></span>

<span data-ttu-id="b9b53-369">Esse parâmetro permite especificar o Tye do item a ser criado com `New-Item`</span><span class="sxs-lookup"><span data-stu-id="b9b53-369">This parameter allows you to specify the tye of item to create with `New-Item`</span></span>

<span data-ttu-id="b9b53-370">Os valores disponíveis desse parâmetro dependem do provedor atual que você está usando.</span><span class="sxs-lookup"><span data-stu-id="b9b53-370">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="b9b53-371">Em uma `FileSystem` unidade, os seguintes valores são permitidos:</span><span class="sxs-lookup"><span data-stu-id="b9b53-371">In a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="b9b53-372">Arquivo</span><span class="sxs-lookup"><span data-stu-id="b9b53-372">File</span></span>
- <span data-ttu-id="b9b53-373">Diretório</span><span class="sxs-lookup"><span data-stu-id="b9b53-373">Directory</span></span>
- <span data-ttu-id="b9b53-374">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="b9b53-374">SymbolicLink</span></span>
- <span data-ttu-id="b9b53-375">Junção</span><span class="sxs-lookup"><span data-stu-id="b9b53-375">Junction</span></span>
- <span data-ttu-id="b9b53-376">Real</span><span class="sxs-lookup"><span data-stu-id="b9b53-376">HardLink</span></span>

### <a name="cmdlets-supported"></a><span data-ttu-id="b9b53-377">Cmdlets com suporte</span><span class="sxs-lookup"><span data-stu-id="b9b53-377">Cmdlets supported</span></span>

- [<span data-ttu-id="b9b53-378">New-Item</span><span class="sxs-lookup"><span data-stu-id="b9b53-378">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="b9b53-379">Usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="b9b53-379">Using the pipeline</span></span>

<span data-ttu-id="b9b53-380">Os cmdlets do provedor aceitam a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="b9b53-380">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="b9b53-381">Você pode usar o pipeline para simplificar a tarefa enviando dados do provedor de um cmdlet para outro cmdlet do provedor.</span><span class="sxs-lookup"><span data-stu-id="b9b53-381">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="b9b53-382">Para ler mais sobre como usar o pipeline com cmdlets de provedor, consulte as referências de cmdlet fornecidas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b9b53-382">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="b9b53-383">Obtendo ajuda</span><span class="sxs-lookup"><span data-stu-id="b9b53-383">Getting help</span></span>

<span data-ttu-id="b9b53-384">A partir do Windows PowerShell 3.0, você pode obter tópicos da Ajuda personalizados para cmdlets do provedor que explicam como esses cmdlets se comportam em uma unidade de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b9b53-384">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="b9b53-385">Para obter os tópicos de ajuda personalizados para a unidade do sistema de arquivos, execute um comando [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) em uma unidade do sistema de arquivos ou use o `-Path` parâmetro de [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) para especificar uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b9b53-385">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path c:
```

## <a name="see-also"></a><span data-ttu-id="b9b53-386">Confira também</span><span class="sxs-lookup"><span data-stu-id="b9b53-386">See also</span></span>

[<span data-ttu-id="b9b53-387">about_Providers</span><span class="sxs-lookup"><span data-stu-id="b9b53-387">about_Providers</span></span>](../About/about_Providers.md)
