---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 903c4eb784c1bb86b66766c7dfb563f586545dc1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194219"
---
# <span data-ttu-id="2ea73-103">Add-Content</span><span class="sxs-lookup"><span data-stu-id="2ea73-103">Add-Content</span></span>

## <span data-ttu-id="2ea73-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2ea73-104">SYNOPSIS</span></span>
<span data-ttu-id="2ea73-105">Adiciona conteúdo aos itens especificados, como a adição de palavras a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-105">Adds content to the specified items, such as adding words to a file.</span></span>

## <span data-ttu-id="2ea73-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2ea73-106">SYNTAX</span></span>

### <span data-ttu-id="2ea73-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="2ea73-107">Path (Default)</span></span>

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

### <span data-ttu-id="2ea73-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2ea73-108">LiteralPath</span></span>

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

## <span data-ttu-id="2ea73-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2ea73-109">DESCRIPTION</span></span>

<span data-ttu-id="2ea73-110">O `Add-Content` cmdlet acrescenta o conteúdo a um item ou arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="2ea73-110">The `Add-Content` cmdlet appends content to a specified item or file.</span></span> <span data-ttu-id="2ea73-111">Você pode especificar o conteúdo, digitando-o no comando ou especificando um objeto que contém o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-111">You can specify the content by typing the content in the command or by specifying an object that contains the content.</span></span>

<span data-ttu-id="2ea73-112">Se você precisar criar arquivos ou diretórios para os exemplos a seguir, consulte [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="2ea73-112">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="2ea73-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2ea73-113">EXAMPLES</span></span>

### <span data-ttu-id="2ea73-114">Exemplo 1: adicionar uma cadeia de caracteres a todos os arquivos de texto com uma exceção</span><span class="sxs-lookup"><span data-stu-id="2ea73-114">Example 1: Add a string to all text files with an exception</span></span>

<span data-ttu-id="2ea73-115">Este exemplo acrescenta um valor a arquivos de texto no diretório atual, mas exclui arquivos com base no nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-115">This example appends a value to text files in the current directory but excludes files based on their file name.</span></span>

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

<span data-ttu-id="2ea73-116">O `Add-Content` cmdlet usa o parâmetro **Path** para especificar todos os arquivos. txt no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ea73-116">The `Add-Content` cmdlet uses the **Path** parameter to specify all .txt files in the current directory.</span></span> <span data-ttu-id="2ea73-117">O parâmetro **Exclude** ignora nomes de arquivo que correspondem ao padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="2ea73-117">The **Exclude** parameter ignores file names that match the specified pattern.</span></span> <span data-ttu-id="2ea73-118">O parâmetro **Value** especifica a cadeia de caracteres de texto que é gravada nos arquivos.</span><span class="sxs-lookup"><span data-stu-id="2ea73-118">The **Value** parameter specifies the text string that is written to the files.</span></span>

<span data-ttu-id="2ea73-119">Use [Get-Content](Get-Content.md) para exibir o conteúdo desses arquivos.</span><span class="sxs-lookup"><span data-stu-id="2ea73-119">Use [Get-Content](Get-Content.md) to display the contents of these files.</span></span>

### <span data-ttu-id="2ea73-120">Exemplo 2: adicionar uma data ao final dos arquivos especificados</span><span class="sxs-lookup"><span data-stu-id="2ea73-120">Example 2: Add a date to the end of the specified files</span></span>

<span data-ttu-id="2ea73-121">Este exemplo acrescenta a data a arquivos no diretório atual e exibe a data no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ea73-121">This example appends the date to files in the current directory and displays the date in the PowerShell console.</span></span>

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

<span data-ttu-id="2ea73-122">O `Add-Content` cmdlet usa os parâmetros **Path** e **Value** para criar dois novos arquivos no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ea73-122">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create two new files in the current directory.</span></span> <span data-ttu-id="2ea73-123">O parâmetro **Value** especifica o `Get-Date` cmdlet para obter a data e passa a data para `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="2ea73-123">The **Value** parameter specifies the `Get-Date` cmdlet to get the date and passes the date to `Add-Content`.</span></span> <span data-ttu-id="2ea73-124">O `Add-Content` cmdlet grava a data em cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-124">The `Add-Content` cmdlet writes the date to each file.</span></span> <span data-ttu-id="2ea73-125">O parâmetro **PassThru** passa um objeto que representa o objeto Date.</span><span class="sxs-lookup"><span data-stu-id="2ea73-125">The **PassThru** parameter passes an object that represents the date object.</span></span> <span data-ttu-id="2ea73-126">Como não há nenhum outro cmdlet para receber o objeto passado, ele é exibido no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ea73-126">Because there is no other cmdlet to receive the passed object, it is displayed in the PowerShell console.</span></span> <span data-ttu-id="2ea73-127">O `Get-Content` cmdlet exibe o arquivo atualizado, DateTimeFile1. log.</span><span class="sxs-lookup"><span data-stu-id="2ea73-127">The `Get-Content` cmdlet displays the updated file, DateTimeFile1.log.</span></span>

### <span data-ttu-id="2ea73-128">Exemplo 3: Adicionar o conteúdo de um arquivo especificado a outro arquivo</span><span class="sxs-lookup"><span data-stu-id="2ea73-128">Example 3: Add the contents of a specified file to another file</span></span>

<span data-ttu-id="2ea73-129">Este exemplo obtém o conteúdo de um arquivo e acrescenta esse conteúdo a outro arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-129">This example gets the content from a file and appends that content into another file.</span></span>

```powershell
Add-Content -Path .\CopyToFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="2ea73-130">O `Add-Content` cmdlet usa o parâmetro **Path** para especificar o novo arquivo no diretório atual, CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="2ea73-130">The `Add-Content` cmdlet uses the **Path** parameter to specify the new file in the current directory, CopyToFile.txt.</span></span> <span data-ttu-id="2ea73-131">O parâmetro **Value** usa o `Get-Content` cmdlet para obter o conteúdo do arquivo, CopyFromFile.txt.</span><span class="sxs-lookup"><span data-stu-id="2ea73-131">The **Value** parameter uses the `Get-Content` cmdlet to get the contents of the file, CopyFromFile.txt.</span></span> <span data-ttu-id="2ea73-132">Os parênteses em volta do `Get-Content` cmdlet garantem que o comando seja concluído antes do `Add-Content` início do comando.</span><span class="sxs-lookup"><span data-stu-id="2ea73-132">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span> <span data-ttu-id="2ea73-133">O parâmetro de **valor** é passado para `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="2ea73-133">The **Value** parameter is passed to `Add-Content`.</span></span> <span data-ttu-id="2ea73-134">O `Add-Content` cmdlet acrescenta os dados ao arquivo de CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="2ea73-134">The `Add-Content` cmdlet appends the data to the CopyToFile.txt file.</span></span> <span data-ttu-id="2ea73-135">O `Get-Content` cmdlet exibe o arquivo atualizado, CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="2ea73-135">The `Get-Content` cmdlet displays the updated file, CopyToFile.txt.</span></span>

### <span data-ttu-id="2ea73-136">Exemplo 4: usar uma variável para adicionar o conteúdo de um arquivo especificado a outro arquivo</span><span class="sxs-lookup"><span data-stu-id="2ea73-136">Example 4: Use a variable to add the contents of a specified file to another file</span></span>

<span data-ttu-id="2ea73-137">Este exemplo obtém o conteúdo de um arquivo e armazena o conteúdo em uma variável.</span><span class="sxs-lookup"><span data-stu-id="2ea73-137">This example gets the content from a file and stores the content in a variable.</span></span> <span data-ttu-id="2ea73-138">A variável é usada para acrescentar o conteúdo a outro arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-138">The variable is used to append the content into another file.</span></span>

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="2ea73-139">O `Get-Content` cmdlet obtém o conteúdo de CopyFromFile.txt e armazena o conteúdo na `$From` variável.</span><span class="sxs-lookup"><span data-stu-id="2ea73-139">The `Get-Content` cmdlet gets the contents of CopyFromFile.txt and stores the contents in the `$From` variable.</span></span> <span data-ttu-id="2ea73-140">O `Add-Content` cmdlet usa o parâmetro **Path** para especificar o arquivo de CopyToFile.txt no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ea73-140">The `Add-Content` cmdlet uses the **Path** parameter to specify the CopyToFile.txt file in the current directory.</span></span> <span data-ttu-id="2ea73-141">O parâmetro **Value** usa a `$From` variável e passa o conteúdo para `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="2ea73-141">The **Value** parameter uses the `$From` variable and passes the content to `Add-Content`.</span></span> <span data-ttu-id="2ea73-142">O `Add-Content` cmdlet atualiza o arquivo de CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="2ea73-142">The `Add-Content` cmdlet updates the CopyToFile.txt file.</span></span> <span data-ttu-id="2ea73-143">O `Get-Content` cmdlet exibe CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="2ea73-143">The `Get-Content` cmdlet displays CopyToFile.txt.</span></span>

### <span data-ttu-id="2ea73-144">Exemplo 5: criar um novo arquivo e copiar o conteúdo</span><span class="sxs-lookup"><span data-stu-id="2ea73-144">Example 5: Create a new file and copy content</span></span>

<span data-ttu-id="2ea73-145">Este exemplo cria um novo arquivo e copia o conteúdo de um arquivo existente no novo arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-145">This example creates a new file and copies an existing file's content into the new file.</span></span>

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

<span data-ttu-id="2ea73-146">O `Add-Content` cmdlet usa os parâmetros **Path** e **Value** para criar um novo arquivo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ea73-146">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create a new file in the current directory.</span></span> <span data-ttu-id="2ea73-147">O parâmetro **Value** usa o `Get-Content` cmdlet para obter o conteúdo de um arquivo existente, CopyFromFile.txt.</span><span class="sxs-lookup"><span data-stu-id="2ea73-147">The **Value** parameter uses the `Get-Content` cmdlet to get the contents of an existing file, CopyFromFile.txt.</span></span> <span data-ttu-id="2ea73-148">Os parênteses em volta do `Get-Content` cmdlet garantem que o comando seja concluído antes do `Add-Content` início do comando.</span><span class="sxs-lookup"><span data-stu-id="2ea73-148">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span> <span data-ttu-id="2ea73-149">O parâmetro **Value** passa o conteúdo para o `Add-Content` qual atualiza o arquivo de NewFile.txt.</span><span class="sxs-lookup"><span data-stu-id="2ea73-149">The **Value** parameter passes the content to `Add-Content` which updates the NewFile.txt file.</span></span> <span data-ttu-id="2ea73-150">O `Get-Content` cmdlet exibe o conteúdo do novo arquivo, NewFile.txt.</span><span class="sxs-lookup"><span data-stu-id="2ea73-150">The `Get-Content` cmdlet displays the contents of the new file, NewFile.txt.</span></span>

### <span data-ttu-id="2ea73-151">Exemplo 6: adicionar conteúdo a um arquivo somente leitura</span><span class="sxs-lookup"><span data-stu-id="2ea73-151">Example 6: Add content to a read-only file</span></span>

<span data-ttu-id="2ea73-152">Esse comando adiciona o valor ao arquivo, mesmo que o atributo de arquivo **IsReadOnly** esteja definido como true.</span><span class="sxs-lookup"><span data-stu-id="2ea73-152">This command adds the value to the file even if the **IsReadOnly** file attribute is set to True.</span></span>
<span data-ttu-id="2ea73-153">As etapas para criar um arquivo somente leitura são incluídas no exemplo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-153">The steps to create a read-only file are included in the example.</span></span>

```powershell
New-Item -Path .\IsReadOnlyTextFile.txt -ItemType File
Set-ItemProperty -Path .\IsReadOnlyTextFile.txt -Name IsReadOnly -Value $True
Get-ChildItem -Path .\IsReadOnlyTextFile.txt
Add-Content -Path .\IsReadOnlyTextFile.txt -Value 'Add value to read-only text file' -Force
Get-Content -Path .\IsReadOnlyTextFile.txt
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-ar---        1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

<span data-ttu-id="2ea73-154">O `New-Item` cmdlet usa os parâmetros **Path** e **ItemType** para criar o arquivo IsReadOnlyTextFile.txt no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ea73-154">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the file IsReadOnlyTextFile.txt in the current directory.</span></span> <span data-ttu-id="2ea73-155">O `Set-ItemProperty` cmdlet usa os parâmetros **Name** e **Value** para alterar a propriedade **IsReadOnly** do arquivo para true.</span><span class="sxs-lookup"><span data-stu-id="2ea73-155">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to True.</span></span> <span data-ttu-id="2ea73-156">O `Get-ChildItem` cmdlet mostra que o arquivo está vazio (0) e tem o atributo somente leitura ( `r` ).</span><span class="sxs-lookup"><span data-stu-id="2ea73-156">The `Get-ChildItem` cmdlet shows the file is empty (0) and has the read-only attribute (`r`).</span></span> <span data-ttu-id="2ea73-157">O `Add-Content` cmdlet usa o parâmetro **Path** para especificar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-157">The `Add-Content` cmdlet uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="2ea73-158">O parâmetro **Value** inclui a cadeia de caracteres de texto a ser acrescentada ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-158">The **Value** parameter includes the text string to append to the file.</span></span> <span data-ttu-id="2ea73-159">O parâmetro **Force** grava o texto no arquivo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="2ea73-159">The **Force** parameter writes the text to the read-only file.</span></span> <span data-ttu-id="2ea73-160">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-160">The `Get-Content` cmdlet uses the **Path** parameter to display the file's contents.</span></span>

<span data-ttu-id="2ea73-161">Para remover o atributo somente leitura, use o `Set-ItemProperty` comando com o parâmetro de **valor** definido como `False` .</span><span class="sxs-lookup"><span data-stu-id="2ea73-161">To remove the read-only attribute, use the `Set-ItemProperty` command with the **Value** parameter set to `False`.</span></span>

## <span data-ttu-id="2ea73-162">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2ea73-162">PARAMETERS</span></span>

### <span data-ttu-id="2ea73-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2ea73-163">-Confirm</span></span>

<span data-ttu-id="2ea73-164">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ea73-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2ea73-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="2ea73-165">-Credential</span></span>

<span data-ttu-id="2ea73-166">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="2ea73-166">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="2ea73-167">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="2ea73-167">The default is the current user.</span></span>

<span data-ttu-id="2ea73-168">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ea73-168">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="2ea73-169">Se você digitar um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="2ea73-169">If you type a user name, you will be prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="2ea73-170">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ea73-170">This parameter is not supported by any providers installed with PowerShell.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2ea73-171">-Codificação</span><span class="sxs-lookup"><span data-stu-id="2ea73-171">-Encoding</span></span>

<span data-ttu-id="2ea73-172">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="2ea73-172">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="2ea73-173">O valor padrão é `Default`.</span><span class="sxs-lookup"><span data-stu-id="2ea73-173">The default value is `Default`.</span></span>

<span data-ttu-id="2ea73-174">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="2ea73-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="2ea73-175">`Ascii` Usa conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="2ea73-175">`Ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="2ea73-176">`BigEndianUnicode` Usa UTF-16 com a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="2ea73-176">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="2ea73-177">`BigEndianUTF32` Usa UTF-32 com a ordem de byte big-endian.</span><span class="sxs-lookup"><span data-stu-id="2ea73-177">`BigEndianUTF32` Uses UTF-32 with the big-endian byte order.</span></span>
- <span data-ttu-id="2ea73-178">`Byte` Codifica um conjunto de caracteres em uma sequência de bytes.</span><span class="sxs-lookup"><span data-stu-id="2ea73-178">`Byte` Encodes a set of characters into a sequence of bytes.</span></span>
- <span data-ttu-id="2ea73-179">`Default` Usa a codificação que corresponde à página de código ativa do sistema (geralmente ANSI).</span><span class="sxs-lookup"><span data-stu-id="2ea73-179">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="2ea73-180">`Oem` Usa a codificação que corresponde à página de código OEM atual do sistema.</span><span class="sxs-lookup"><span data-stu-id="2ea73-180">`Oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="2ea73-181">`String` Mesmo que **Unicode** .</span><span class="sxs-lookup"><span data-stu-id="2ea73-181">`String` Same as **Unicode** .</span></span>
- <span data-ttu-id="2ea73-182">`Unicode` Usa UTF-16 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="2ea73-182">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="2ea73-183">`Unknown` Mesmo que **Unicode** .</span><span class="sxs-lookup"><span data-stu-id="2ea73-183">`Unknown` Same as **Unicode** .</span></span>
- <span data-ttu-id="2ea73-184">`UTF7` Usa UTF-7.</span><span class="sxs-lookup"><span data-stu-id="2ea73-184">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="2ea73-185">`UTF8` Usa UTF-8.</span><span class="sxs-lookup"><span data-stu-id="2ea73-185">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="2ea73-186">`UTF32` Usa UTF-32 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="2ea73-186">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

<span data-ttu-id="2ea73-187">A codificação é um parâmetro dinâmico que o provedor FileSystem adiciona ao `Add-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ea73-187">Encoding is a dynamic parameter that the FileSystem provider adds to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="2ea73-188">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2ea73-188">This parameter works only in file system drives.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, Byte, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ea73-189">-Excluir</span><span class="sxs-lookup"><span data-stu-id="2ea73-189">-Exclude</span></span>

<span data-ttu-id="2ea73-190">Omite os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="2ea73-190">Omits the specified items.</span></span> <span data-ttu-id="2ea73-191">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="2ea73-191">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="2ea73-192">Insira um elemento ou padrão de caminho, como **\* . txt** .</span><span class="sxs-lookup"><span data-stu-id="2ea73-192">Enter a path element or pattern, such as **\*.txt** .</span></span> <span data-ttu-id="2ea73-193">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="2ea73-193">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="2ea73-194">-Filter</span><span class="sxs-lookup"><span data-stu-id="2ea73-194">-Filter</span></span>

<span data-ttu-id="2ea73-195">Especifica um filtro no formato ou linguagem do provedor.</span><span class="sxs-lookup"><span data-stu-id="2ea73-195">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="2ea73-196">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="2ea73-196">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="2ea73-197">A sintaxe do filtro, incluindo o uso de caracteres curingas, depende do provedor.</span><span class="sxs-lookup"><span data-stu-id="2ea73-197">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="2ea73-198">Os **filtros** são mais eficientes do que outros parâmetros porque o provedor aplica filtros quando objetos são recuperados.</span><span class="sxs-lookup"><span data-stu-id="2ea73-198">**Filters** are more efficient than other parameters because the provider applies filters when objects are retrieved.</span></span> <span data-ttu-id="2ea73-199">Caso contrário, o PowerShell processará filtros depois que os objetos forem recuperados.</span><span class="sxs-lookup"><span data-stu-id="2ea73-199">Otherwise, PowerShell processes filters after the objects are retrieved.</span></span>

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

### <span data-ttu-id="2ea73-200">-Force</span><span class="sxs-lookup"><span data-stu-id="2ea73-200">-Force</span></span>

<span data-ttu-id="2ea73-201">Substitui o atributo somente leitura, permitindo adicionar conteúdo a um arquivo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="2ea73-201">Overrides the read-only attribute, allowing you to add content to a read-only file.</span></span> <span data-ttu-id="2ea73-202">Por exemplo, o **Force** substituirá o atributo somente leitura ou criar diretórios para concluir um caminho de arquivo, mas não tentará alterar permissões de arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-202">For example, **Force** will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.</span></span>

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

### <span data-ttu-id="2ea73-203">-Incluir</span><span class="sxs-lookup"><span data-stu-id="2ea73-203">-Include</span></span>

<span data-ttu-id="2ea73-204">Adiciona apenas os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="2ea73-204">Adds only the specified items.</span></span> <span data-ttu-id="2ea73-205">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="2ea73-205">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="2ea73-206">Insira um elemento ou padrão de caminho, como **\* . txt** .</span><span class="sxs-lookup"><span data-stu-id="2ea73-206">Enter a path element or pattern, such as **\*.txt** .</span></span> <span data-ttu-id="2ea73-207">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="2ea73-207">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="2ea73-208">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2ea73-208">-LiteralPath</span></span>

<span data-ttu-id="2ea73-209">Especifica o caminho para os itens que recebem conteúdo adicional.</span><span class="sxs-lookup"><span data-stu-id="2ea73-209">Specifies the path to the items that receive the additional content.</span></span> <span data-ttu-id="2ea73-210">Ao contrário de **Path** , o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="2ea73-210">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="2ea73-211">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="2ea73-211">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="2ea73-212">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="2ea73-212">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="2ea73-213">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="2ea73-213">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="2ea73-214">-Nonovat</span><span class="sxs-lookup"><span data-stu-id="2ea73-214">-NoNewline</span></span>

<span data-ttu-id="2ea73-215">Indica que esse cmdlet não adiciona uma nova linha ou retorno de carro ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-215">Indicates that this cmdlet does not add a new line or carriage return to the content.</span></span>

<span data-ttu-id="2ea73-216">As representações de cadeia de caracteres dos objetos de entrada são concatenadas para formar a saída.</span><span class="sxs-lookup"><span data-stu-id="2ea73-216">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="2ea73-217">Nenhum espaço ou novas linhas são inseridas entre as cadeias de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="2ea73-217">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="2ea73-218">Nenhuma nova linha é adicionada após a última cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="2ea73-218">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="2ea73-219">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2ea73-219">-PassThru</span></span>

<span data-ttu-id="2ea73-220">Retorna um objeto que representa o conteúdo adicionado.</span><span class="sxs-lookup"><span data-stu-id="2ea73-220">Returns an object representing the added content.</span></span> <span data-ttu-id="2ea73-221">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="2ea73-221">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="2ea73-222">-Path</span><span class="sxs-lookup"><span data-stu-id="2ea73-222">-Path</span></span>

<span data-ttu-id="2ea73-223">Especifica o caminho para os itens que recebem conteúdo adicional.</span><span class="sxs-lookup"><span data-stu-id="2ea73-223">Specifies the path to the items that receive the additional content.</span></span> <span data-ttu-id="2ea73-224">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="2ea73-224">Wildcards are permitted.</span></span> <span data-ttu-id="2ea73-225">Se você especificar vários caminhos, use vírgulas para separá-los.</span><span class="sxs-lookup"><span data-stu-id="2ea73-225">If you specify multiple paths, use commas to separate the paths.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="2ea73-226">-Fluxo</span><span class="sxs-lookup"><span data-stu-id="2ea73-226">-Stream</span></span>

<span data-ttu-id="2ea73-227">Especifica um fluxo de dados alternativo para o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-227">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="2ea73-228">Se o fluxo não existir, esse cmdlet o criará.</span><span class="sxs-lookup"><span data-stu-id="2ea73-228">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="2ea73-229">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="2ea73-229">Wildcard characters are not supported.</span></span>

<span data-ttu-id="2ea73-230">**Stream** é um parâmetro dinâmico que o provedor FileSystem adiciona `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="2ea73-230">**Stream** is a dynamic parameter that the FileSystem provider adds to `Add-Content`.</span></span> <span data-ttu-id="2ea73-231">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2ea73-231">This parameter works only in file system drives.</span></span>

<span data-ttu-id="2ea73-232">Você pode usar o `Add-Content` cmdlet para alterar o conteúdo do fluxo de dados de **zona. identificador** alternativo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-232">You can use the `Add-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="2ea73-233">No entanto, não recomendamos isso como uma maneira de eliminar verificações de segurança que bloqueiam arquivos baixados da Internet.</span><span class="sxs-lookup"><span data-stu-id="2ea73-233">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="2ea73-234">Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ea73-234">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="2ea73-235">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2ea73-235">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ea73-236">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="2ea73-236">-UseTransaction</span></span>

<span data-ttu-id="2ea73-237">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="2ea73-237">Includes the command in the active transaction.</span></span> <span data-ttu-id="2ea73-238">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="2ea73-238">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="2ea73-239">Para obter mais informações, consulte [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="2ea73-239">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="2ea73-240">-Value</span><span class="sxs-lookup"><span data-stu-id="2ea73-240">-Value</span></span>

<span data-ttu-id="2ea73-241">Especifica o conteúdo a ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="2ea73-241">Specifies the content to be added.</span></span> <span data-ttu-id="2ea73-242">Digite uma cadeia de caracteres entre aspas, como **esses dados são somente para uso interno** ou especifique um objeto que contenha conteúdo, como o objeto **DateTime** que `Get-Date` gera.</span><span class="sxs-lookup"><span data-stu-id="2ea73-242">Type a quoted string, such as **This data is for internal use only** , or specify an object that contains content, such as the **DateTime** object that `Get-Date` generates.</span></span>

<span data-ttu-id="2ea73-243">Você não pode especificar o conteúdo de um arquivo digitando seu caminho, pois o caminho é apenas uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2ea73-243">You cannot specify the contents of a file by typing its path, because the path is just a string.</span></span>
<span data-ttu-id="2ea73-244">Você pode usar um `Get-Content` comando para obter o conteúdo e passá-lo para o parâmetro **Value** .</span><span class="sxs-lookup"><span data-stu-id="2ea73-244">You can use a `Get-Content` command to get the content and pass it to the **Value** parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2ea73-245">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2ea73-245">-WhatIf</span></span>

<span data-ttu-id="2ea73-246">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="2ea73-246">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2ea73-247">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="2ea73-247">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2ea73-248">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2ea73-248">CommonParameters</span></span>

<span data-ttu-id="2ea73-249">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="2ea73-249">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="2ea73-250">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2ea73-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2ea73-251">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2ea73-251">INPUTS</span></span>

### <span data-ttu-id="2ea73-252">System. Object, System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="2ea73-252">System.Object, System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="2ea73-253">Você pode canalizar valores, caminhos ou credenciais para `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="2ea73-253">You can pipe values, paths, or credentials to `Set-Content`.</span></span>

## <span data-ttu-id="2ea73-254">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2ea73-254">OUTPUTS</span></span>

### <span data-ttu-id="2ea73-255">Nenhum ou System.String</span><span class="sxs-lookup"><span data-stu-id="2ea73-255">None or System.String</span></span>

<span data-ttu-id="2ea73-256">Quando você usa o parâmetro **PassThru** , o `Add-Content` gera um objeto **System. String** que representa o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="2ea73-256">When you use the **PassThru** parameter, `Add-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="2ea73-257">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="2ea73-257">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2ea73-258">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2ea73-258">NOTES</span></span>

<span data-ttu-id="2ea73-259">Quando você canaliza um objeto para `Add-Content` , o objeto é convertido em uma cadeia de caracteres antes de ser adicionado ao item.</span><span class="sxs-lookup"><span data-stu-id="2ea73-259">When you pipe an object to `Add-Content`, the object is converted to a string before it is added to the item.</span></span> <span data-ttu-id="2ea73-260">O tipo de objeto determina o formato de cadeia de caracteres, mas o formato pode ser diferente da exibição padrão do objeto.</span><span class="sxs-lookup"><span data-stu-id="2ea73-260">The object type determines the string format, but the format might be different than the default display of the object.</span></span> <span data-ttu-id="2ea73-261">Para controlar o formato da cadeia de caracteres, use os parâmetros de formatação do cmdlet de envio.</span><span class="sxs-lookup"><span data-stu-id="2ea73-261">To control the string format, use the formatting parameters of the sending cmdlet.</span></span>

<span data-ttu-id="2ea73-262">Você também pode consultar `Add-Content` por seu alias interno, `ac` .</span><span class="sxs-lookup"><span data-stu-id="2ea73-262">You can also refer to `Add-Content` by its built-in alias, `ac`.</span></span> <span data-ttu-id="2ea73-263">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="2ea73-263">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="2ea73-264">O `Add-Content` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="2ea73-264">The `Add-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="2ea73-265">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="2ea73-265">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="2ea73-266">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="2ea73-266">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="2ea73-267">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2ea73-267">RELATED LINKS</span></span>

[<span data-ttu-id="2ea73-268">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="2ea73-268">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="2ea73-269">about_Providers</span><span class="sxs-lookup"><span data-stu-id="2ea73-269">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="2ea73-270">about_Transactions</span><span class="sxs-lookup"><span data-stu-id="2ea73-270">about_Transactions</span></span>](../Microsoft.PowerShell.Core/About/about_Transactions.md)

[<span data-ttu-id="2ea73-271">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="2ea73-271">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="2ea73-272">Get-Content</span><span class="sxs-lookup"><span data-stu-id="2ea73-272">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="2ea73-273">Get-Item</span><span class="sxs-lookup"><span data-stu-id="2ea73-273">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="2ea73-274">New-Item</span><span class="sxs-lookup"><span data-stu-id="2ea73-274">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="2ea73-275">Set-Content</span><span class="sxs-lookup"><span data-stu-id="2ea73-275">Set-Content</span></span>](Set-Content.md)
