---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Trabalhando com arquivos e pastas
description: Este artigo discute como lidar com tarefas de manipulação de arquivos e pastas específicas usando o PowerShell.
ms.openlocfilehash: c0c3abb082b05296daa480ac06bcbfa3a784e0c9
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500021"
---
# <a name="working-with-files-and-folders"></a><span data-ttu-id="ca77f-104">Trabalhando com arquivos e pastas</span><span class="sxs-lookup"><span data-stu-id="ca77f-104">Working with Files and Folders</span></span>

<span data-ttu-id="ca77f-105">Navegar pelas unidades do Windows PowerShell e manipular os itens nelas é semelhante a manipular arquivos e pastas em unidades de disco físico do Windows.</span><span class="sxs-lookup"><span data-stu-id="ca77f-105">Navigating through Windows PowerShell drives and manipulating the items on them is similar to manipulating files and folders on Windows physical disk drives.</span></span> <span data-ttu-id="ca77f-106">Este artigo discute como lidar com tarefas de manipulação de arquivos e pastas específicas usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca77f-106">This article discusses how to deal with specific file and folder manipulation tasks using PowerShell.</span></span>

## <a name="listing-all-the-files-and-folders-within-a-folder"></a><span data-ttu-id="ca77f-107">Listar todos os arquivos e pastas dentro de uma pasta</span><span class="sxs-lookup"><span data-stu-id="ca77f-107">Listing All the Files and Folders Within a Folder</span></span>

<span data-ttu-id="ca77f-108">Você pode obter todos os itens diretamente em uma pasta usando `Get-ChildItem`.</span><span class="sxs-lookup"><span data-stu-id="ca77f-108">You can get all items directly within a folder by using `Get-ChildItem`.</span></span> <span data-ttu-id="ca77f-109">Adicione o parâmetro opcional **Force** para exibir itens ocultos ou do sistema.</span><span class="sxs-lookup"><span data-stu-id="ca77f-109">Add the optional **Force** parameter to display hidden or system items.</span></span> <span data-ttu-id="ca77f-110">Por exemplo, este comando exibe o conteúdo direto da unidade do Windows PowerShell C (que é a mesma que a unidade física C do Windows):</span><span class="sxs-lookup"><span data-stu-id="ca77f-110">For example, this command displays the direct contents of Windows PowerShell Drive C (which is the same as the Windows physical drive C):</span></span>

```powershell
Get-ChildItem -Path C:\ -Force
```

<span data-ttu-id="ca77f-111">O comando lista apenas os itens contidos diretamente, similar ao uso do comando `DIR` ou `ls` de `Cmd.exe` em um shell do UNIX.</span><span class="sxs-lookup"><span data-stu-id="ca77f-111">The command lists only the directly contained items, much like using `Cmd.exe`'s `DIR` command or `ls` in a UNIX shell.</span></span> <span data-ttu-id="ca77f-112">Para mostrar os itens contidos, também é necessário especificar o parâmetro `-Recurse`.</span><span class="sxs-lookup"><span data-stu-id="ca77f-112">In order to show contained items, you need to specify the `-Recurse` parameter as well.</span></span> <span data-ttu-id="ca77f-113">(Isso pode levar muitíssimo tempo para ser concluído.) Para listar todos os itens na unidade C:</span><span class="sxs-lookup"><span data-stu-id="ca77f-113">(This can take an extremely long time to complete.) To list everything on the C drive:</span></span>

```powershell
Get-ChildItem -Path C:\ -Force -Recurse
```

<span data-ttu-id="ca77f-114">`Get-ChildItem` pode filtrar itens com seus parâmetros **Path** , **Filter** , **Include** e **Exclude** , mas eles normalmente se baseiam apenas no nome.</span><span class="sxs-lookup"><span data-stu-id="ca77f-114">`Get-ChildItem` can filter items with its **Path** , **Filter** , **Include** , and **Exclude** parameters, but those are typically based only on name.</span></span> <span data-ttu-id="ca77f-115">Você pode executar a filtragem complexa com base em outras propriedades de itens usando `Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="ca77f-115">You can perform complex filtering based on other properties of items by using `Where-Object`.</span></span>

<span data-ttu-id="ca77f-116">O comando a seguir localiza todos os executáveis na pasta Arquivos de Programa que foi modificado após 1º de outubro de 2005 e que não são menores que 1 megabyte nem maiores que 10 megabytes:</span><span class="sxs-lookup"><span data-stu-id="ca77f-116">The following command finds all executables within the Program Files folder that were last modified after October 1, 2005 and which are neither smaller than 1 megabyte nor larger than 10 megabytes:</span></span>

```powershell
Get-ChildItem -Path $env:ProgramFiles -Recurse -Include *.exe | Where-Object -FilterScript {($_.LastWriteTime -gt '2005-10-01') -and ($_.Length -ge 1mb) -and ($_.Length -le 10mb)}
```

## <a name="copying-files-and-folders"></a><span data-ttu-id="ca77f-117">Copiar arquivos e pastas</span><span class="sxs-lookup"><span data-stu-id="ca77f-117">Copying Files and Folders</span></span>

<span data-ttu-id="ca77f-118">A cópia é feita com `Copy-Item`.</span><span class="sxs-lookup"><span data-stu-id="ca77f-118">Copying is done with `Copy-Item`.</span></span> <span data-ttu-id="ca77f-119">O comando a seguir faz backup de C:\\boot.ini em C:\\boot.bak:</span><span class="sxs-lookup"><span data-stu-id="ca77f-119">The following command backs up C:\\boot.ini to C:\\boot.bak:</span></span>

```powershell
Copy-Item -Path C:\boot.ini -Destination C:\boot.bak
```

<span data-ttu-id="ca77f-120">Se o arquivo de destino já existir, a tentativa de cópia falhará.</span><span class="sxs-lookup"><span data-stu-id="ca77f-120">If the destination file already exists, the copy attempt fails.</span></span> <span data-ttu-id="ca77f-121">Para substituir um destino pré-existente, use o parâmetro **Force** :</span><span class="sxs-lookup"><span data-stu-id="ca77f-121">To overwrite a pre-existing destination, use the **Force** parameter:</span></span>

```powershell
Copy-Item -Path C:\boot.ini -Destination C:\boot.bak -Force
```

<span data-ttu-id="ca77f-122">Esse comando funciona mesmo quando o destino é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="ca77f-122">This command works even when the destination is read-only.</span></span>

<span data-ttu-id="ca77f-123">Copiar a pasta funciona da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="ca77f-123">Folder copying works the same way.</span></span> <span data-ttu-id="ca77f-124">Esse comando copia a pasta `C:\temp\test1` para a nova pasta `C:\temp\DeleteMe` recursivamente:</span><span class="sxs-lookup"><span data-stu-id="ca77f-124">This command copies the folder `C:\temp\test1` to the new folder `C:\temp\DeleteMe` recursively:</span></span>

```powershell
Copy-Item C:\temp\test1 -Recurse C:\temp\DeleteMe
```

<span data-ttu-id="ca77f-125">Você também pode copiar uma seleção de itens.</span><span class="sxs-lookup"><span data-stu-id="ca77f-125">You can also copy a selection of items.</span></span> <span data-ttu-id="ca77f-126">O comando a seguir copia todos os arquivos .txt contidos em qualquer lugar em `C:\data` para `C:\temp\text`:</span><span class="sxs-lookup"><span data-stu-id="ca77f-126">The following command copies all .txt files contained anywhere in `C:\data` to `C:\temp\text`:</span></span>

```powershell
Copy-Item -Filter *.txt -Path c:\data -Recurse -Destination C:\temp\text
```

<span data-ttu-id="ca77f-127">Você ainda pode usar outras ferramentas para realizar cópias do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="ca77f-127">You can still use other tools to perform file system copies.</span></span> <span data-ttu-id="ca77f-128">XCOPY, ROBOCOPY e objetos COM, como o **Scripting.FileSystemObject,** todos eles funcionam no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca77f-128">XCOPY, ROBOCOPY, and COM objects, such as the **Scripting.FileSystemObject,** all work in Windows PowerShell.</span></span> <span data-ttu-id="ca77f-129">Por exemplo, você pode usar a classe **Scripting.FileSystem COM** do Windows Script Host para fazer backup de `C:\boot.ini` para `C:\boot.bak`:</span><span class="sxs-lookup"><span data-stu-id="ca77f-129">For example, you can use the Windows Script Host **Scripting.FileSystem COM** class to back up `C:\boot.ini` to `C:\boot.bak`:</span></span>

```powershell
(New-Object -ComObject Scripting.FileSystemObject).CopyFile('C:\boot.ini', 'C:\boot.bak')
```

## <a name="creating-files-and-folders"></a><span data-ttu-id="ca77f-130">Criar arquivos e pastas</span><span class="sxs-lookup"><span data-stu-id="ca77f-130">Creating Files and Folders</span></span>

<span data-ttu-id="ca77f-131">Criar novos itens funciona da mesma forma em todos os provedores do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca77f-131">Creating new items works the same on all Windows PowerShell providers.</span></span> <span data-ttu-id="ca77f-132">Se um provedor do Windows PowerShell tiver mais de um tipo de item, por exemplo, se o provedor do Sistema de Arquivos do Windows PowerShell fizer distinção entre arquivos e diretórios, você precisará especificar o tipo de item.</span><span class="sxs-lookup"><span data-stu-id="ca77f-132">If a Windows PowerShell provider has more than one type of item—for example, the FileSystem Windows PowerShell provider distinguishes between directories and files—you need to specify the item type.</span></span>

<span data-ttu-id="ca77f-133">Esse comando cria uma pasta `C:\temp\New Folder`:</span><span class="sxs-lookup"><span data-stu-id="ca77f-133">This command creates a new folder `C:\temp\New Folder`:</span></span>

```powershell
New-Item -Path 'C:\temp\New Folder' -ItemType Directory
```

<span data-ttu-id="ca77f-134">Esse comando cria um arquivo vazio `C:\temp\New Folder\file.txt`</span><span class="sxs-lookup"><span data-stu-id="ca77f-134">This command creates a new empty file `C:\temp\New Folder\file.txt`</span></span>

```powershell
New-Item -Path 'C:\temp\New Folder\file.txt' -ItemType File
```

> [!IMPORTANT]
> <span data-ttu-id="ca77f-135">Ao usar a opção **Force** com o comando `New-Item` para criar uma pasta, e a pasta já existir, ele _não_ substituirá a pasta.</span><span class="sxs-lookup"><span data-stu-id="ca77f-135">When using the **Force** switch with the `New-Item` command to create a folder, and the folder already exists, it _won't_ overwrite or replace the folder.</span></span> <span data-ttu-id="ca77f-136">Simplesmente retornará o objeto da pasta existente.</span><span class="sxs-lookup"><span data-stu-id="ca77f-136">It will simply return the existing folder object.</span></span> <span data-ttu-id="ca77f-137">No entanto, se você usar `New-Item -Force` em um arquivo que já existe, o arquivo _será_ completamente substituído.</span><span class="sxs-lookup"><span data-stu-id="ca77f-137">However, if you use `New-Item -Force` on a file that already exists, the file _will_ be completely overwritten.</span></span>

## <a name="removing-all-files-and-folders-within-a-folder"></a><span data-ttu-id="ca77f-138">Remover todos os arquivos e pastas dentro de uma pasta</span><span class="sxs-lookup"><span data-stu-id="ca77f-138">Removing All Files and Folders Within a Folder</span></span>

<span data-ttu-id="ca77f-139">É possível remover os itens contidos usando `Remove-Item`, mas será solicitado que você confirme a remoção se o item contiver qualquer outra coisa.</span><span class="sxs-lookup"><span data-stu-id="ca77f-139">You can remove contained items using `Remove-Item`, but you will be prompted to confirm the removal if the item contains anything else.</span></span> <span data-ttu-id="ca77f-140">Por exemplo, se você tentar excluir a pasta `C:\temp\DeleteMe` que contém outros itens, o Windows PowerShell solicitará sua confirmação antes de excluí-la:</span><span class="sxs-lookup"><span data-stu-id="ca77f-140">For example, if you attempt to delete the folder `C:\temp\DeleteMe` that contains other items, Windows PowerShell prompts you for confirmation before deleting the folder:</span></span>

```
Remove-Item -Path C:\temp\DeleteMe

Confirm
The item at C:\temp\DeleteMe has children and the Recurse parameter was not
specified. If you continue, all children will be removed with the item. Are you
sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):
```

<span data-ttu-id="ca77f-141">Se você não quiser ser solicitado para cada item contido, especifique o parâmetro **Recurse** :</span><span class="sxs-lookup"><span data-stu-id="ca77f-141">If you do not want to be prompted for each contained item, specify the **Recurse** parameter:</span></span>

```powershell
Remove-Item -Path C:\temp\DeleteMe -Recurse
```

## <a name="mapping-a-local-folder-as-a-drive"></a><span data-ttu-id="ca77f-142">Mapear uma pasta local como uma unidade</span><span class="sxs-lookup"><span data-stu-id="ca77f-142">Mapping a Local Folder as a drive</span></span>

<span data-ttu-id="ca77f-143">Você também pode mapear uma pasta local usando o comando `New-PSDrive`.</span><span class="sxs-lookup"><span data-stu-id="ca77f-143">You can also map a local folder, using the `New-PSDrive` command.</span></span> <span data-ttu-id="ca77f-144">O comando a seguir cria uma unidade local `P:` com raiz no diretório Arquivos de Programa locais, visível somente na sessão do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ca77f-144">The following command creates a local drive `P:` rooted in the local Program Files directory, visible only from the PowerShell session:</span></span>

```powershell
New-PSDrive -Name P -Root $env:ProgramFiles -PSProvider FileSystem
```

<span data-ttu-id="ca77f-145">Assim como ocorre com unidades de rede, unidades mapeadas no Windows PowerShell ficam visíveis imediatamente para o shell do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca77f-145">Just as with network drives, drives mapped within Windows PowerShell are immediately visible to the Windows PowerShell shell.</span></span> <span data-ttu-id="ca77f-146">Para criar uma unidade mapeada visível no Explorador de Arquivos, é necessário o parâmetro `-Persist`.</span><span class="sxs-lookup"><span data-stu-id="ca77f-146">In order to create a mapped drive visible from File Explorer, the parameter `-Persist` is needed.</span></span> <span data-ttu-id="ca77f-147">No entanto, somente caminhos remotos podem ser usados com Persist.</span><span class="sxs-lookup"><span data-stu-id="ca77f-147">However, only remote paths can be used with Persist.</span></span>

## <a name="reading-a-text-file-into-an-array"></a><span data-ttu-id="ca77f-148">Ler um arquivo de texto em uma matriz</span><span class="sxs-lookup"><span data-stu-id="ca77f-148">Reading a Text File into an Array</span></span>

<span data-ttu-id="ca77f-149">Um dos formatos mais comuns de armazenamento para dados de texto é em um arquivo com linhas separadas, tratadas como elementos de dados distintos.</span><span class="sxs-lookup"><span data-stu-id="ca77f-149">One of the more common storage formats for text data is in a file with separate lines treated as distinct data elements.</span></span> <span data-ttu-id="ca77f-150">O cmdlet `Get-Content` pode ser usado para ler um arquivo inteiro em uma única etapa, como mostrado aqui:</span><span class="sxs-lookup"><span data-stu-id="ca77f-150">The `Get-Content` cmdlet can be used to read an entire file in one step, as shown here:</span></span>

```
PS> Get-Content -Path C:\boot.ini
[boot loader]
timeout=5
default=multi(0)disk(0)rdisk(0)partition(1)\WINDOWS
[operating systems]
multi(0)disk(0)rdisk(0)partition(1)\WINDOWS="Microsoft Windows XP Professional"
 /noexecute=AlwaysOff /fastdetect
multi(0)disk(0)rdisk(0)partition(1)\WINDOWS=" Microsoft Windows XP Professional
with Data Execution Prevention" /noexecute=optin /fastdetect
```

<span data-ttu-id="ca77f-151">`Get-Content` já trata os dados lidos do arquivo como uma matriz, com um elemento por linha do conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="ca77f-151">`Get-Content` already treats the data read from the file as an array, with one element per line of file content.</span></span> <span data-ttu-id="ca77f-152">Você pode confirmar isso verificando o **Length** do conteúdo retornado:</span><span class="sxs-lookup"><span data-stu-id="ca77f-152">You can confirm this by checking the **Length** of the returned content:</span></span>

```
PS> (Get-Content -Path C:\boot.ini).Length
6
```

<span data-ttu-id="ca77f-153">Esse comando é mais útil para obter listas de informações no Windows PowerShell diretamente.</span><span class="sxs-lookup"><span data-stu-id="ca77f-153">This command is most useful for getting lists of information into Windows PowerShell directly.</span></span> <span data-ttu-id="ca77f-154">Por exemplo, você pode armazenar uma lista de nomes de computador ou de endereços IP em um arquivo `C:\temp\domainMembers.txt`, com um nome em cada linha do arquivo.</span><span class="sxs-lookup"><span data-stu-id="ca77f-154">For example, you might store a list of computer names or IP addresses in a file `C:\temp\domainMembers.txt`, with one name on each line of the file.</span></span> <span data-ttu-id="ca77f-155">Você pode usar `Get-Content` para recuperar o conteúdo do arquivo e colocá-lo na variável `$Computers`:</span><span class="sxs-lookup"><span data-stu-id="ca77f-155">You can use `Get-Content` to retrieve the file contents and put them in the variable `$Computers`:</span></span>

```powershell
$Computers = Get-Content -Path C:\temp\DomainMembers.txt
```

<span data-ttu-id="ca77f-156">`$Computers` agora é uma matriz que contém um nome do computador em cada elemento.</span><span class="sxs-lookup"><span data-stu-id="ca77f-156">`$Computers` is now an array containing a computer name in each element.</span></span>
