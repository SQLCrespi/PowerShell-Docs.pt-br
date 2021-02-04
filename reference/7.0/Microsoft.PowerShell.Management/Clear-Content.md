---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-content?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Content
ms.openlocfilehash: 9ffe7510745e92c6863cf08d143f89e214ae9133
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692982"
---
# <span data-ttu-id="a5800-102">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="a5800-102">Clear-Content</span></span>

## <span data-ttu-id="a5800-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a5800-103">SYNOPSIS</span></span>
<span data-ttu-id="a5800-104">Exclui o conteúdo de um item, mas não exclui o item.</span><span class="sxs-lookup"><span data-stu-id="a5800-104">Deletes the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="a5800-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a5800-105">SYNTAX</span></span>

### <span data-ttu-id="a5800-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="a5800-106">Path (Default)</span></span>

```
Clear-Content [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

### <span data-ttu-id="a5800-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a5800-107">LiteralPath</span></span>

```
Clear-Content -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String>] [<CommonParameters>]
```

## <span data-ttu-id="a5800-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a5800-108">DESCRIPTION</span></span>

<span data-ttu-id="a5800-109">O `Clear-Content` cmdlet exclui o conteúdo de um item, como excluir o texto de um arquivo, mas ele não exclui o item.</span><span class="sxs-lookup"><span data-stu-id="a5800-109">The `Clear-Content` cmdlet deletes the contents of an item, such as deleting the text from a file, but it does not delete the item.</span></span>
<span data-ttu-id="a5800-110">Como resultado, o item existe, mas fica vazio.</span><span class="sxs-lookup"><span data-stu-id="a5800-110">As a result, the item exists, but it is empty.</span></span>
<span data-ttu-id="a5800-111">O `Clear-Content` é semelhante a `Clear-Item` , mas funciona em itens com conteúdo, em vez de itens com valores.</span><span class="sxs-lookup"><span data-stu-id="a5800-111">The `Clear-Content` is similar to `Clear-Item`, but it works on items with contents, instead of items with values.</span></span>

## <span data-ttu-id="a5800-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a5800-112">EXAMPLES</span></span>

### <span data-ttu-id="a5800-113">Exemplo 1: excluir todo o conteúdo de um diretório</span><span class="sxs-lookup"><span data-stu-id="a5800-113">Example 1: Delete all content from a directory</span></span>

```powershell
Clear-Content "..\SmpUsers\*\init.txt"
```

<span data-ttu-id="a5800-114">Esse comando exclui todo o conteúdo dos arquivos "init.txt" em todos os subdiretórios do diretório SmpUsers.</span><span class="sxs-lookup"><span data-stu-id="a5800-114">This command deletes all of the content from the "init.txt" files in all subdirectories of the SmpUsers directory.</span></span>
<span data-ttu-id="a5800-115">Os arquivos não serão excluídos, mas ficam vazios.</span><span class="sxs-lookup"><span data-stu-id="a5800-115">The files are not deleted, but they are empty.</span></span>

### <span data-ttu-id="a5800-116">Exemplo 2: excluir o conteúdo de todos os arquivos com um curinga</span><span class="sxs-lookup"><span data-stu-id="a5800-116">Example 2: Delete content of all files with a wildcard</span></span>

```powershell
Clear-Content -Path "*" -Filter "*.log" -Force
```

<span data-ttu-id="a5800-117">Esse comando exclui o conteúdo de todos os arquivos no diretório atual com a extensão de nome de arquivo ".log", incluindo arquivos com o atributo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="a5800-117">This command deletes the contents of all files in the current directory with the ".log" file name extension, including files with the read-only attribute.</span></span> <span data-ttu-id="a5800-118">O asterisco ( \* ) no caminho representa todos os itens no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="a5800-118">The asterisk (\*) in the path represents all items in the current directory.</span></span> <span data-ttu-id="a5800-119">O parâmetro **Force** torna o comando efetivo em arquivos somente leitura.</span><span class="sxs-lookup"><span data-stu-id="a5800-119">The **Force** parameter makes the command effective on read-only files.</span></span> <span data-ttu-id="a5800-120">Usando um filtro para restringir o comando a arquivos com a extensão de nome de arquivo. log em vez de especificar \* . log no caminho torna a operação mais rápida.</span><span class="sxs-lookup"><span data-stu-id="a5800-120">Using a filter to restrict the command to files with the .log file name extension instead of specifying \*.log in the path makes the operation faster.</span></span>

### <span data-ttu-id="a5800-121">Exemplo 3: limpar todos os dados de um fluxo</span><span class="sxs-lookup"><span data-stu-id="a5800-121">Example 3: Clear all data from a stream</span></span>

<span data-ttu-id="a5800-122">Este exemplo mostra como o `Clear-Content` cmdlet limpa o conteúdo de um fluxo de dados alternativo, deixando o fluxo intacto.</span><span class="sxs-lookup"><span data-stu-id="a5800-122">This example shows how the `Clear-Content` cmdlet clears the content from an alternate data stream while leaving the stream intact.</span></span>

<span data-ttu-id="a5800-123">O primeiro comando usa o `Get-Content` cmdlet para obter o conteúdo do `Zone.Identifier` fluxo no arquivo de Copy-Script.ps1, que foi baixado da Internet.</span><span class="sxs-lookup"><span data-stu-id="a5800-123">The first command uses the `Get-Content` cmdlet to get the content of the `Zone.Identifier` stream in the Copy-Script.ps1 file, which was downloaded from the Internet.</span></span>

<span data-ttu-id="a5800-124">O segundo comando usa o `Clear-Content` cmdlet para limpar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a5800-124">The second command uses the `Clear-Content` cmdlet to clear the content.</span></span>

<span data-ttu-id="a5800-125">O terceiro comando repete o primeiro comando.</span><span class="sxs-lookup"><span data-stu-id="a5800-125">The third command repeats the first command.</span></span> <span data-ttu-id="a5800-126">Ele verifica se o conteúdo está limpo, mas o fluxo permanece.</span><span class="sxs-lookup"><span data-stu-id="a5800-126">It verifies that the content is cleared, but the stream remains.</span></span> <span data-ttu-id="a5800-127">Se o fluxo foi excluído, o comando geraria um erro.</span><span class="sxs-lookup"><span data-stu-id="a5800-127">If the stream were deleted, the command would generate an error.</span></span>

<span data-ttu-id="a5800-128">Você pode usar um método como este para limpar o conteúdo de um fluxo de dados alternativo.</span><span class="sxs-lookup"><span data-stu-id="a5800-128">You can use a method like this one to clear the content of an alternate data stream.</span></span> <span data-ttu-id="a5800-129">No entanto, não é a maneira recomendada para eliminar verificações de segurança que bloqueiam arquivos baixados da Internet.</span><span class="sxs-lookup"><span data-stu-id="a5800-129">However, it is not the recommended way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="a5800-130">Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a5800-130">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

```
PS C:\> Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

[ZoneTransfer]
ZoneId=3

PS C:\>Clear-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier

PS C:\>Get-Content C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
PS C:\>
```

## <span data-ttu-id="a5800-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a5800-131">PARAMETERS</span></span>

### <span data-ttu-id="a5800-132">-Fluxo</span><span class="sxs-lookup"><span data-stu-id="a5800-132">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="a5800-133">Esse parâmetro só está disponível no Windows.</span><span class="sxs-lookup"><span data-stu-id="a5800-133">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="a5800-134">Especifica um fluxo de dados alternativo para o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a5800-134">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="a5800-135">Se o fluxo não existir, esse cmdlet o criará.</span><span class="sxs-lookup"><span data-stu-id="a5800-135">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="a5800-136">Não há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="a5800-136">Wildcard characters are not supported.</span></span>

<span data-ttu-id="a5800-137">Stream é um parâmetro dinâmico que o provedor FileSystem adiciona `Clear-Content` .</span><span class="sxs-lookup"><span data-stu-id="a5800-137">Stream is a dynamic parameter that the FileSystem provider adds to `Clear-Content`.</span></span>
<span data-ttu-id="a5800-138">Esse parâmetro funciona somente em unidades de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="a5800-138">This parameter works only in file system drives.</span></span>

<span data-ttu-id="a5800-139">Você pode usar o `Clear-Content` cmdlet para alterar o conteúdo do fluxo de dados alternativo Amy, como `Zone.Identifier` .</span><span class="sxs-lookup"><span data-stu-id="a5800-139">You can use the `Clear-Content` cmdlet to change the content of amy alternate data stream, such as `Zone.Identifier`.</span></span> <span data-ttu-id="a5800-140">No entanto, não recomendamos isso como uma maneira de eliminar verificações de segurança que bloqueiam arquivos baixados da Internet.</span><span class="sxs-lookup"><span data-stu-id="a5800-140">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="a5800-141">Se você verificar se um arquivo baixado é seguro, use o `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a5800-141">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

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

### <span data-ttu-id="a5800-142">-Credential</span><span class="sxs-lookup"><span data-stu-id="a5800-142">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="a5800-143">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5800-143">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="a5800-144">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="a5800-144">To impersonate another user, or elevate your credentials when running this cmdlet, use Invoke-Command.</span></span>

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

### <span data-ttu-id="a5800-145">-Excluir</span><span class="sxs-lookup"><span data-stu-id="a5800-145">-Exclude</span></span>

<span data-ttu-id="a5800-146">Especifica, como uma matriz de cadeia de caracteres, que esse cmdlet omite do caminho para o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a5800-146">Specifies, as a string array, strings that this cmdlet omits from the path to the content.</span></span> <span data-ttu-id="a5800-147">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="a5800-147">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a5800-148">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="a5800-148">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="a5800-149">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a5800-149">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="a5800-150">-Filter</span><span class="sxs-lookup"><span data-stu-id="a5800-150">-Filter</span></span>

<span data-ttu-id="a5800-151">Especifica um filtro no formato ou linguagem do provedor.</span><span class="sxs-lookup"><span data-stu-id="a5800-151">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="a5800-152">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="a5800-152">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a5800-153">A sintaxe do filtro, incluindo o uso de caracteres curingas, depende do provedor.</span><span class="sxs-lookup"><span data-stu-id="a5800-153">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="a5800-154">Os filtros são mais eficientes do que outros parâmetros, pois o provedor os aplica ao recuperar os objetos, em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="a5800-154">Filters are more efficient than other parameters, because the provider applies them when retrieving the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="a5800-155">-Force</span><span class="sxs-lookup"><span data-stu-id="a5800-155">-Force</span></span>

<span data-ttu-id="a5800-156">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="a5800-156">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="a5800-157">-Incluir</span><span class="sxs-lookup"><span data-stu-id="a5800-157">-Include</span></span>

<span data-ttu-id="a5800-158">Especifica, como uma matriz de cadeia de caracteres, o conteúdo que esse cmdlet limpa.</span><span class="sxs-lookup"><span data-stu-id="a5800-158">Specifies, as a string array, content that this cmdlet clears.</span></span> <span data-ttu-id="a5800-159">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="a5800-159">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a5800-160">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="a5800-160">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="a5800-161">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a5800-161">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="a5800-162">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a5800-162">-LiteralPath</span></span>

<span data-ttu-id="a5800-163">Especifica os caminhos para os itens dos quais o conteúdo é excluído.</span><span class="sxs-lookup"><span data-stu-id="a5800-163">Specifies the paths to the items from which content is deleted.</span></span> <span data-ttu-id="a5800-164">Ao contrário do parâmetro **Path**, o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="a5800-164">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="a5800-165">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="a5800-165">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="a5800-166">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="a5800-166">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="a5800-167">Aspas simples dizem que o PowerShell não interpreta nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="a5800-167">Single quotation marks tell having PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="a5800-168">-Path</span><span class="sxs-lookup"><span data-stu-id="a5800-168">-Path</span></span>

<span data-ttu-id="a5800-169">Especifica os caminhos para os itens dos quais o conteúdo é excluído.</span><span class="sxs-lookup"><span data-stu-id="a5800-169">Specifies the paths to the items from which content is deleted.</span></span> <span data-ttu-id="a5800-170">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a5800-170">Wildcards are permitted.</span></span> <span data-ttu-id="a5800-171">Os caminhos devem ser caminhos para itens, não para contêineres.</span><span class="sxs-lookup"><span data-stu-id="a5800-171">The paths must be paths to items, not to containers.</span></span> <span data-ttu-id="a5800-172">Por exemplo, você deve especificar um caminho para um ou mais arquivos, não um caminho para um diretório.</span><span class="sxs-lookup"><span data-stu-id="a5800-172">For example, you must specify a path to one or more files, not a path to a directory.</span></span> <span data-ttu-id="a5800-173">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a5800-173">Wildcards are permitted.</span></span> <span data-ttu-id="a5800-174">Este parâmetro é obrigatório, mas o nome do parâmetro ("Path") é opcional.</span><span class="sxs-lookup"><span data-stu-id="a5800-174">This parameter is required, but the parameter name ("Path") is optional.</span></span>

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

### <span data-ttu-id="a5800-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a5800-175">-Confirm</span></span>

<span data-ttu-id="a5800-176">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a5800-176">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a5800-177">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a5800-177">-WhatIf</span></span>

<span data-ttu-id="a5800-178">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="a5800-178">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a5800-179">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="a5800-179">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a5800-180">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a5800-180">CommonParameters</span></span>

<span data-ttu-id="a5800-181">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a5800-181">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a5800-182">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a5800-182">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>


## <span data-ttu-id="a5800-183">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a5800-183">INPUTS</span></span>

### <span data-ttu-id="a5800-184">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a5800-184">None</span></span>

<span data-ttu-id="a5800-185">Não é possível canalizar objetos para `Clear-Content` .</span><span class="sxs-lookup"><span data-stu-id="a5800-185">You cannot pipe objects to `Clear-Content`.</span></span>

## <span data-ttu-id="a5800-186">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a5800-186">OUTPUTS</span></span>

### <span data-ttu-id="a5800-187">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a5800-187">None</span></span>

<span data-ttu-id="a5800-188">Este cmdlet não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="a5800-188">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="a5800-189">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a5800-189">NOTES</span></span>

<span data-ttu-id="a5800-190">Você pode usar `Clear-Content` o com o provedor de sistema de arquivos do PowerShell e outros provedores que manipulam conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a5800-190">You can use `Clear-Content` with the PowerShell FileSystem provider and with other providers that manipulate content.</span></span> <span data-ttu-id="a5800-191">Para limpar os itens que não são considerados conteúdo, como itens gerenciados pelo certificado do PowerShell ou pelos provedores de registro, use `Clear-Item` .</span><span class="sxs-lookup"><span data-stu-id="a5800-191">To clear items that are not considered to be content, such as items managed by the PowerShell Certificate or Registry providers, use `Clear-Item`.</span></span>

<span data-ttu-id="a5800-192">O `Clear-Content` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="a5800-192">The `Clear-Content` cmdlet is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="a5800-193">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="a5800-193">To list the providers available in your session, type `Get-PsProvider`.</span></span>
<span data-ttu-id="a5800-194">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="a5800-194">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="a5800-195">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a5800-195">RELATED LINKS</span></span>

[<span data-ttu-id="a5800-196">Add-Content</span><span class="sxs-lookup"><span data-stu-id="a5800-196">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="a5800-197">Get-Content</span><span class="sxs-lookup"><span data-stu-id="a5800-197">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="a5800-198">Get-Item</span><span class="sxs-lookup"><span data-stu-id="a5800-198">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="a5800-199">Set-Content</span><span class="sxs-lookup"><span data-stu-id="a5800-199">Set-Content</span></span>](Set-Content.md)

[<span data-ttu-id="a5800-200">about_Providers</span><span class="sxs-lookup"><span data-stu-id="a5800-200">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
