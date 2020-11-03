---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-Item
ms.openlocfilehash: 1898d0b80e715c817612b54d795d0c2f57b6c6b7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193219"
---
# <span data-ttu-id="71eea-103">Move-Item</span><span class="sxs-lookup"><span data-stu-id="71eea-103">Move-Item</span></span>

## <span data-ttu-id="71eea-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="71eea-104">SYNOPSIS</span></span>
<span data-ttu-id="71eea-105">Move um item de um local para outro.</span><span class="sxs-lookup"><span data-stu-id="71eea-105">Moves an item from one location to another.</span></span>

## <span data-ttu-id="71eea-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="71eea-106">SYNTAX</span></span>

### <span data-ttu-id="71eea-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="71eea-107">Path (Default)</span></span>

```
Move-Item [-Path] <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="71eea-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="71eea-108">LiteralPath</span></span>

```
Move-Item -LiteralPath <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="71eea-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="71eea-109">DESCRIPTION</span></span>

<span data-ttu-id="71eea-110">O `Move-Item` cmdlet Move um item, incluindo suas propriedades, conteúdo e itens filho, de um local para outro local.</span><span class="sxs-lookup"><span data-stu-id="71eea-110">The `Move-Item` cmdlet moves an item, including its properties, contents, and child items, from one location to another location.</span></span> <span data-ttu-id="71eea-111">Os locais devem ter suporte no mesmo provedor.</span><span class="sxs-lookup"><span data-stu-id="71eea-111">The locations must be supported by the same provider.</span></span>
<span data-ttu-id="71eea-112">Por exemplo, ele pode mover um arquivo ou um subdiretório de um diretório para outro ou mover uma subchave do registro de uma chave para outra.</span><span class="sxs-lookup"><span data-stu-id="71eea-112">For example, it can move a file or subdirectory from one directory to another or move a registry subkey from one key to another.</span></span>
<span data-ttu-id="71eea-113">Quando você move um item, ele é adicionado ao novo local e excluído do seu local original.</span><span class="sxs-lookup"><span data-stu-id="71eea-113">When you move an item, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="71eea-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="71eea-114">EXAMPLES</span></span>

### <span data-ttu-id="71eea-115">Exemplo 1: mover um arquivo para outro diretório e renomeá-lo</span><span class="sxs-lookup"><span data-stu-id="71eea-115">Example 1: Move a file to another directory and rename it</span></span>

<span data-ttu-id="71eea-116">Esse comando move o `Test.txt` arquivo da `C:` unidade para o `E:\Temp` diretório e o renomeia de `test.txt` para `tst.txt` .</span><span class="sxs-lookup"><span data-stu-id="71eea-116">This command moves the `Test.txt` file from the `C:` drive to the `E:\Temp` directory and renames it from `test.txt` to `tst.txt`.</span></span>

```powershell
Move-Item -Path C:\test.txt -Destination E:\Temp\tst.txt
```

### <span data-ttu-id="71eea-117">Exemplo 2: mover um diretório e seu conteúdo para outro diretório</span><span class="sxs-lookup"><span data-stu-id="71eea-117">Example 2: Move a directory and its contents to another directory</span></span>

<span data-ttu-id="71eea-118">Esse comando move o `C:\Temp` diretório e seu conteúdo para o `C:\Logs` diretório.</span><span class="sxs-lookup"><span data-stu-id="71eea-118">This command moves the `C:\Temp` directory and its contents to the `C:\Logs` directory.</span></span>
<span data-ttu-id="71eea-119">O diretório "Temp" e todos os seus subdiretórios e arquivos, em seguida, aparecem no diretório "logs".</span><span class="sxs-lookup"><span data-stu-id="71eea-119">The "Temp" directory, and all of its subdirectories and files, then appear in the "Logs" directory.</span></span>

```powershell
Move-Item -Path C:\Temp -Destination C:\Logs
```

### <span data-ttu-id="71eea-120">Exemplo 3: mover todos os arquivos de uma extensão especificada do diretório atual para outro diretório</span><span class="sxs-lookup"><span data-stu-id="71eea-120">Example 3: Move all files of a specified extension from the current directory to another directory</span></span>

<span data-ttu-id="71eea-121">Esse comando move todos os arquivos de texto ( `*.txt` ) no diretório atual (representado por um ponto ( `.` )) para o `C:\Logs` diretório.</span><span class="sxs-lookup"><span data-stu-id="71eea-121">This command moves all of the text files (`*.txt`) in the current directory (represented by a dot (`.`)) to the `C:\Logs` directory.</span></span>

```powershell
Move-Item -Path .\*.txt -Destination C:\Logs
```

### <span data-ttu-id="71eea-122">Exemplo 4: mover recursivamente todos os arquivos de uma extensão especificada do diretório atual para outro diretório</span><span class="sxs-lookup"><span data-stu-id="71eea-122">Example 4: Recursively move all files of a specified extension from the current directory to another directory</span></span>

<span data-ttu-id="71eea-123">Esse comando move todos os arquivos de texto do diretório atual e de todos os subdiretórios, recursivamente, para o diretório "C:\TextFiles".</span><span class="sxs-lookup"><span data-stu-id="71eea-123">This command moves all of the text files from the current directory and all subdirectories, recursively, to the "C:\TextFiles" directory.</span></span>

```powershell
Get-ChildItem -Path ".\*.txt" -Recurse | Move-Item -Destination "C:\TextFiles"
```

<span data-ttu-id="71eea-124">O comando usa o `Get-ChildItem` cmdlet para obter todos os itens filho no diretório atual (representado pelo ponto \[ \] ) e seus subdiretórios que têm uma *extensão de nome de arquivo ". txt". Ele usa o parâmetro **recurse** para tornar a recuperação recursiva e o parâmetro include para limitar a recuperação a arquivos "* . txt".</span><span class="sxs-lookup"><span data-stu-id="71eea-124">The command uses the `Get-ChildItem` cmdlet to get all of the child items in the current directory (represented by the dot \[.\]) and its subdirectories that have a " *.txt" file name extension. It uses the **Recurse** parameter to make the retrieval recursive and the Include parameter to limit the retrieval to "* .txt" files.</span></span>

<span data-ttu-id="71eea-125">O operador de pipeline ( `|` ) envia os resultados desse comando para `Move-Item` , que move os arquivos de texto para o diretório "textfiles".</span><span class="sxs-lookup"><span data-stu-id="71eea-125">The pipeline operator (`|`) sends the results of this command to `Move-Item`, which moves the text files to the "TextFiles" directory.</span></span>

<span data-ttu-id="71eea-126">Se os arquivos que devem ser movidos para "C:\Textfiles" tiverem o mesmo nome, o `Move-Item` exibirá um erro e continuará, mas moverá apenas um arquivo com cada nome para "C:\Textfiles".</span><span class="sxs-lookup"><span data-stu-id="71eea-126">If files that are to be moved to "C:\Textfiles" have the same name, `Move-Item` displays an error and continues, but it moves only one file with each name to "C:\Textfiles".</span></span>
<span data-ttu-id="71eea-127">Os outros arquivos permanecerão em seus diretórios originais.</span><span class="sxs-lookup"><span data-stu-id="71eea-127">The other files remain in their original directories.</span></span>

<span data-ttu-id="71eea-128">Se o diretório "textfiles" (ou qualquer outro elemento do caminho de destino) não existir, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="71eea-128">If the "Textfiles" directory (or any other element of the destination path) does not exist, the command fails.</span></span>
<span data-ttu-id="71eea-129">O diretório ausente não é criado para você, mesmo se você usar o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="71eea-129">The missing directory is not created for you, even if you use the **Force** parameter.</span></span>
<span data-ttu-id="71eea-130">`Move-Item` move o primeiro item para um arquivo chamado "textfiles" e, em seguida, exibe um erro explicando que o arquivo já existe.</span><span class="sxs-lookup"><span data-stu-id="71eea-130">`Move-Item` moves the first item to a file called "Textfiles" and then displays an error explaining that the file already exists.</span></span>

<span data-ttu-id="71eea-131">Além disso, por padrão, `Get-ChildItem` o não move arquivos ocultos.</span><span class="sxs-lookup"><span data-stu-id="71eea-131">Also, by default, `Get-ChildItem` does not move hidden files.</span></span>
<span data-ttu-id="71eea-132">Para mover arquivos ocultos, use o parâmetro **Force** com `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="71eea-132">To move hidden files, use the **Force** parameter with `Get-ChildItem`.</span></span>

> [!NOTE]
> <span data-ttu-id="71eea-133">No Windows PowerShell 2,0, ao usar o parâmetro **recurse** do `Get-ChildItem` cmdlet, o valor do parâmetro **Path** deve ser um contêiner.</span><span class="sxs-lookup"><span data-stu-id="71eea-133">In Windows PowerShell 2.0, when using the **Recurse** parameter of the `Get-ChildItem` cmdlet, the value of the **Path** parameter must be a container.</span></span>
> <span data-ttu-id="71eea-134">Use o parâmetro **include** para especificar o filtro de extensão de nome de arquivo. txt ( `Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles` ).</span><span class="sxs-lookup"><span data-stu-id="71eea-134">Use the **Include** parameter to specify the .txt file name extension filter (`Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles`).</span></span>

### <span data-ttu-id="71eea-135">Exemplo 5: mover as chaves e valores do registro para outra chave</span><span class="sxs-lookup"><span data-stu-id="71eea-135">Example 5: Move registry keys and values to another key</span></span>

<span data-ttu-id="71eea-136">Esse comando move as chaves do registro e os valores dentro da chave do registro "MyCompany" `HKLM\Software` para a chave "MyNewCompany".</span><span class="sxs-lookup"><span data-stu-id="71eea-136">This command moves the registry keys and values within the "MyCompany" registry key in `HKLM\Software` to the "MyNewCompany" key.</span></span>
<span data-ttu-id="71eea-137">O caractere curinga ( `*` ) indica que o conteúdo da chave "myCompany" deve ser movido, não a chave em si.</span><span class="sxs-lookup"><span data-stu-id="71eea-137">The wildcard character (`*`) indicates that the contents of the "MyCompany" key should be moved, not the key itself.</span></span>
<span data-ttu-id="71eea-138">Nesse comando, os nomes de parâmetro de **destino** e **caminho** opcionais são omitidos.</span><span class="sxs-lookup"><span data-stu-id="71eea-138">In this command, the optional **Path** and **Destination** parameter names are omitted.</span></span>

```powershell
Move-Item "HKLM:\software\mycompany\*" "HKLM:\software\mynewcompany"
```

### <span data-ttu-id="71eea-139">Exemplo 6: mover um diretório e seu conteúdo para um subdiretório do diretório especificado</span><span class="sxs-lookup"><span data-stu-id="71eea-139">Example 6: Move a directory and its contents to a subdirectory of the specified directory</span></span>

<span data-ttu-id="71eea-140">Esse comando move o diretório " \[ logs \` \] de 29 de setembro" (e seu conteúdo) para o \[ diretório "logs 2006 \] ".</span><span class="sxs-lookup"><span data-stu-id="71eea-140">This command moves the "Logs\[Sept\`06\]" directory (and its contents) into the "Logs\[2006\]" directory.</span></span>

```powershell
Move-Item -LiteralPath 'Logs[Sept`06]' -Destination 'Logs[2006]'
```

<span data-ttu-id="71eea-141">O parâmetro **LiteralPath** é usado em vez de **Path** , porque o nome do diretório original inclui colchetes à esquerda e colchetes à direita (" \[ " e " \] ").</span><span class="sxs-lookup"><span data-stu-id="71eea-141">The **LiteralPath** parameter is used instead of **Path** , because the original directory name includes left bracket and right bracket characters ("\[" and "\]").</span></span>
<span data-ttu-id="71eea-142">O caminho também é colocado entre aspas simples (' '), para que o símbolo de acento grave ( \` ) não seja interpretado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="71eea-142">The path is also enclosed in single quotation marks (' '), so that the backtick symbol (\`) is not misinterpreted.</span></span>

<span data-ttu-id="71eea-143">O parâmetro de **destino** não requer um caminho literal, pois a variável de destino também deve ser colocada entre aspas simples, pois inclui colchetes que podem ser interpretados incorretamente.</span><span class="sxs-lookup"><span data-stu-id="71eea-143">The **Destination** parameter does not require a literal path, because the Destination variable also must be enclosed in single quotation marks, because it includes brackets that can be misinterpreted.</span></span>

## <span data-ttu-id="71eea-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="71eea-144">PARAMETERS</span></span>

### <span data-ttu-id="71eea-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="71eea-145">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="71eea-146">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71eea-146">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="71eea-147">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="71eea-147">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="71eea-148">-Destino</span><span class="sxs-lookup"><span data-stu-id="71eea-148">-Destination</span></span>

<span data-ttu-id="71eea-149">Especifica o caminho para o local onde os itens são movidos.</span><span class="sxs-lookup"><span data-stu-id="71eea-149">Specifies the path to the location where the items are being moved.</span></span>
<span data-ttu-id="71eea-150">O padrão é o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="71eea-150">The default is the current directory.</span></span>
<span data-ttu-id="71eea-151">Caracteres curinga são permitidos, mas o resultado deve especificar um único local.</span><span class="sxs-lookup"><span data-stu-id="71eea-151">Wildcards are permitted, but the result must specify a single location.</span></span>

<span data-ttu-id="71eea-152">Para renomear o item que está sendo movido, especifique um novo nome no valor do parâmetro de **destino** .</span><span class="sxs-lookup"><span data-stu-id="71eea-152">To rename the item being moved, specify a new name in the value of the **Destination** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="71eea-153">-Excluir</span><span class="sxs-lookup"><span data-stu-id="71eea-153">-Exclude</span></span>

<span data-ttu-id="71eea-154">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="71eea-154">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="71eea-155">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="71eea-155">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="71eea-156">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="71eea-156">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="71eea-157">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="71eea-157">Wildcard characters are permitted.</span></span> <span data-ttu-id="71eea-158">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="71eea-158">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="71eea-159">-Filter</span><span class="sxs-lookup"><span data-stu-id="71eea-159">-Filter</span></span>

<span data-ttu-id="71eea-160">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="71eea-160">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="71eea-161">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="71eea-161">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="71eea-162">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="71eea-162">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="71eea-163">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="71eea-163">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="71eea-164">-Force</span><span class="sxs-lookup"><span data-stu-id="71eea-164">-Force</span></span>

<span data-ttu-id="71eea-165">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="71eea-165">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="71eea-166">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="71eea-166">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="71eea-167">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="71eea-167">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="71eea-168">-Incluir</span><span class="sxs-lookup"><span data-stu-id="71eea-168">-Include</span></span>

<span data-ttu-id="71eea-169">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="71eea-169">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="71eea-170">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="71eea-170">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="71eea-171">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="71eea-171">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="71eea-172">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="71eea-172">Wildcard characters are permitted.</span></span> <span data-ttu-id="71eea-173">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="71eea-173">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="71eea-174">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="71eea-174">-LiteralPath</span></span>

<span data-ttu-id="71eea-175">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="71eea-175">Specifies a path to one or more locations.</span></span> <span data-ttu-id="71eea-176">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="71eea-176">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="71eea-177">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="71eea-177">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="71eea-178">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="71eea-178">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="71eea-179">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="71eea-179">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="71eea-180">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="71eea-180">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="71eea-181">-PassThru</span><span class="sxs-lookup"><span data-stu-id="71eea-181">-PassThru</span></span>

<span data-ttu-id="71eea-182">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="71eea-182">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="71eea-183">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="71eea-183">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="71eea-184">-Path</span><span class="sxs-lookup"><span data-stu-id="71eea-184">-Path</span></span>

<span data-ttu-id="71eea-185">Especifica o caminho para o local atual dos itens.</span><span class="sxs-lookup"><span data-stu-id="71eea-185">Specifies the path to the current location of the items.</span></span>
<span data-ttu-id="71eea-186">O padrão é o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="71eea-186">The default is the current directory.</span></span>
<span data-ttu-id="71eea-187">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="71eea-187">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="71eea-188">-Confirm</span><span class="sxs-lookup"><span data-stu-id="71eea-188">-Confirm</span></span>

<span data-ttu-id="71eea-189">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="71eea-189">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="71eea-190">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="71eea-190">-WhatIf</span></span>

<span data-ttu-id="71eea-191">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="71eea-191">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="71eea-192">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="71eea-192">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="71eea-193">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="71eea-193">CommonParameters</span></span>

<span data-ttu-id="71eea-194">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="71eea-194">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="71eea-195">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="71eea-195">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="71eea-196">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="71eea-196">INPUTS</span></span>

### <span data-ttu-id="71eea-197">System.String</span><span class="sxs-lookup"><span data-stu-id="71eea-197">System.String</span></span>

<span data-ttu-id="71eea-198">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="71eea-198">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="71eea-199">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="71eea-199">OUTPUTS</span></span>

### <span data-ttu-id="71eea-200">Nenhum ou um objeto que representa o item movido</span><span class="sxs-lookup"><span data-stu-id="71eea-200">None or an object representing the moved item</span></span>

<span data-ttu-id="71eea-201">Quando você usa o parâmetro *PassThru* , esse cmdlet gera um objeto que representa o item movido.</span><span class="sxs-lookup"><span data-stu-id="71eea-201">When you use the *PassThru* parameter, this cmdlet generates an object representing the moved item.</span></span>
<span data-ttu-id="71eea-202">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="71eea-202">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="71eea-203">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="71eea-203">NOTES</span></span>

- <span data-ttu-id="71eea-204">Esse cmdlet moverá arquivos entre unidades com suporte no mesmo provedor, mas moverá os diretórios somente dentro da mesma unidade.</span><span class="sxs-lookup"><span data-stu-id="71eea-204">This cmdlet will move files between drives that are supported by the same provider, but it will move directories only within the same drive.</span></span>
- <span data-ttu-id="71eea-205">Como um `Move-Item` comando move as propriedades, o conteúdo e os itens filho de um item, todas as movimentações são recursivas por padrão.</span><span class="sxs-lookup"><span data-stu-id="71eea-205">Because a `Move-Item` command moves the properties, contents, and child items of an item, all moves are recursive by default.</span></span>
- <span data-ttu-id="71eea-206">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="71eea-206">This cmdlet is designed to work with the data exposed by any provider.</span></span>
  <span data-ttu-id="71eea-207">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="71eea-207">To list the providers available in your session, type `Get-PSProvider`.</span></span>
  <span data-ttu-id="71eea-208">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="71eea-208">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="71eea-209">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="71eea-209">RELATED LINKS</span></span>

[<span data-ttu-id="71eea-210">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="71eea-210">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="71eea-211">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="71eea-211">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="71eea-212">Get-Item</span><span class="sxs-lookup"><span data-stu-id="71eea-212">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="71eea-213">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="71eea-213">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="71eea-214">New-Item</span><span class="sxs-lookup"><span data-stu-id="71eea-214">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="71eea-215">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="71eea-215">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="71eea-216">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="71eea-216">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="71eea-217">Set-Item</span><span class="sxs-lookup"><span data-stu-id="71eea-217">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="71eea-218">about_Providers</span><span class="sxs-lookup"><span data-stu-id="71eea-218">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

