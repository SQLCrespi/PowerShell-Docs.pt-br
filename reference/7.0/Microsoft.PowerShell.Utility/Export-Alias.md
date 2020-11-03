---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Alias
ms.openlocfilehash: 4ddc9af276f1d24cc687652d96ffba77897305f0
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192867"
---
# <span data-ttu-id="53862-103">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="53862-103">Export-Alias</span></span>

## <span data-ttu-id="53862-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="53862-104">SYNOPSIS</span></span>
<span data-ttu-id="53862-105">Exporta as informações sobre aliases definidos atualmente para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="53862-105">Exports information about currently defined aliases to a file.</span></span>

## <span data-ttu-id="53862-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="53862-106">SYNTAX</span></span>

### <span data-ttu-id="53862-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="53862-107">ByPath (Default)</span></span>

```
Export-Alias [-Path] <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append] [-Force]
 [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="53862-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="53862-108">ByLiteralPath</span></span>

```
Export-Alias -LiteralPath <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append]
 [-Force] [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="53862-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="53862-109">DESCRIPTION</span></span>

<span data-ttu-id="53862-110">O `Export-Alias` cmdlet exporta os aliases na sessão atual para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="53862-110">The `Export-Alias` cmdlet exports the aliases in the current session to a file.</span></span>
<span data-ttu-id="53862-111">Se o arquivo de saída não existe, o cmdlet o cria.</span><span class="sxs-lookup"><span data-stu-id="53862-111">If the output file does not exist, the cmdlet will create it.</span></span>

<span data-ttu-id="53862-112">`Export-Alias` pode exportar os aliases em um escopo específico ou em todos os escopos, ele pode gerar os dados no formato CSV ou como uma série de comandos Set-Alias que você pode adicionar a uma sessão ou a um perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53862-112">`Export-Alias` can export the aliases in a particular scope or all scopes, it can generate the data in CSV format or as a series of Set-Alias commands that you can add to a session or to a PowerShell profile.</span></span>

## <span data-ttu-id="53862-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="53862-113">EXAMPLES</span></span>

### <span data-ttu-id="53862-114">Exemplo 1: exportar um alias</span><span class="sxs-lookup"><span data-stu-id="53862-114">Example 1: Export an alias</span></span>

```powershell
Export-Alias -Path "alias.csv"
```

<span data-ttu-id="53862-115">Este comando exporta as informações atuais de alias em um arquivo chamado Alias.csv no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="53862-115">This command exports current alias information to a file named Alias.csv in the current directory.</span></span>

### <span data-ttu-id="53862-116">Exemplo 2: exportar um alias, a menos que o arquivo de exportação já exista</span><span class="sxs-lookup"><span data-stu-id="53862-116">Example 2: Export an alias unless the export file already exists</span></span>

```powershell
Export-Alias -Path "alias.csv" -NoClobber
```

<span data-ttu-id="53862-117">Esse comando exporta os aliases na sessão atual para um arquivo Alias.csv.</span><span class="sxs-lookup"><span data-stu-id="53862-117">This command exports the aliases in the current session to an Alias.csv file.</span></span>

<span data-ttu-id="53862-118">Como o parâmetro **NoClobber** é especificado, o comando falhará se um arquivo de Alias.csv já existir no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="53862-118">Because the **NoClobber** parameter is specified, the command will fail if an Alias.csv file already exists in the current directory.</span></span>

### <span data-ttu-id="53862-119">Exemplo 3: acrescentar aliases a um arquivo</span><span class="sxs-lookup"><span data-stu-id="53862-119">Example 3: Append aliases to a file</span></span>

```powershell
Export-Alias -Path "alias.csv" -Append -Description "Appended Aliases" -Force
```

<span data-ttu-id="53862-120">Este comando anexa os aliases na sessão atual ao arquivo Alias.csv.</span><span class="sxs-lookup"><span data-stu-id="53862-120">This command appends the aliases in the current session to the Alias.csv file.</span></span>

<span data-ttu-id="53862-121">O comando usa o parâmetro **Description** para adicionar uma descrição aos comentários na parte superior do arquivo.</span><span class="sxs-lookup"><span data-stu-id="53862-121">The command uses the **Description** parameter to add a description to the comments at the top of the file.</span></span>

<span data-ttu-id="53862-122">O comando também usa o parâmetro **Force** para substituir todos os arquivos de Alias.csv existentes, mesmo que eles tenham o atributo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="53862-122">The command also uses the **Force** parameter to overwrite any existing Alias.csv files, even if they have the read-only attribute.</span></span>

### <span data-ttu-id="53862-123">Exemplo 4: exportar aliases como um script</span><span class="sxs-lookup"><span data-stu-id="53862-123">Example 4: Export aliases as a script</span></span>

```powershell
Export-Alias -Path "alias.ps1" -As Script
Add-Content -Path $Profile -Value (Get-Content alias.ps1)
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -FilePath .\alias.ps1
```

<span data-ttu-id="53862-124">Este exemplo mostra como usar o formato de arquivo de script que `Export-Alias` gera.</span><span class="sxs-lookup"><span data-stu-id="53862-124">This example shows how to use the script file format that `Export-Alias` generates.</span></span>

<span data-ttu-id="53862-125">O primeiro comando exporta os aliases da sessão para o arquivo Alias.ps1.</span><span class="sxs-lookup"><span data-stu-id="53862-125">The first command exports the aliases in the session to the Alias.ps1 file.</span></span>
<span data-ttu-id="53862-126">Ele **usa o parâmetro as com** um valor de script para gerar um arquivo que contém um comando Set-Alias para cada alias.</span><span class="sxs-lookup"><span data-stu-id="53862-126">It uses the **As** parameter with a value of Script to generate a file that contains a Set-Alias command for each alias.</span></span>

<span data-ttu-id="53862-127">O segundo comando adiciona os alias no arquivo Alias.ps1 ao perfil CurrentUser-CurrentHost.</span><span class="sxs-lookup"><span data-stu-id="53862-127">The second command adds the aliases in the Alias.ps1 file to the CurrentUser-CurrentHost profile.</span></span>
<span data-ttu-id="53862-128">O caminho para o perfil é salvo na `$Profile` variável.</span><span class="sxs-lookup"><span data-stu-id="53862-128">The path to the profile is saved in the `$Profile` variable.</span></span>
<span data-ttu-id="53862-129">O comando usa o `Get-Content` cmdlet para obter os aliases do arquivo de Alias.ps1 e o `Add-Content` cmdlet para adicioná-los ao perfil.</span><span class="sxs-lookup"><span data-stu-id="53862-129">The command uses the `Get-Content` cmdlet to get the aliases from the Alias.ps1 file and the `Add-Content` cmdlet to add them to the profile.</span></span>
<span data-ttu-id="53862-130">Para obter mais informações, consulte about_Profiles.</span><span class="sxs-lookup"><span data-stu-id="53862-130">For more information, see about_Profiles.</span></span>

<span data-ttu-id="53862-131">O terceiro e o quarto comandos adicionam os aliases no arquivo de Alias.ps1 a uma sessão remota no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="53862-131">The third and fourth commands add the aliases in the Alias.ps1 file to a remote session on the Server01 computer.</span></span>
<span data-ttu-id="53862-132">O terceiro comando usa o `New-PSSession` cmdlet para criar a sessão.</span><span class="sxs-lookup"><span data-stu-id="53862-132">The third command uses the `New-PSSession` cmdlet to create the session.</span></span>
<span data-ttu-id="53862-133">O quarto comando usa o parâmetro **FilePath** do `Invoke-Command` cmdlet para executar o arquivo de Alias.ps1 na nova sessão.</span><span class="sxs-lookup"><span data-stu-id="53862-133">The fourth command uses the **FilePath** parameter of the `Invoke-Command` cmdlet to run the Alias.ps1 file in the new session.</span></span>

## <span data-ttu-id="53862-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="53862-134">PARAMETERS</span></span>

### <span data-ttu-id="53862-135">-Acrescentar</span><span class="sxs-lookup"><span data-stu-id="53862-135">-Append</span></span>

<span data-ttu-id="53862-136">Indica que esse cmdlet acrescenta a saída ao arquivo especificado, em vez de substituir o conteúdo existente desse arquivo.</span><span class="sxs-lookup"><span data-stu-id="53862-136">Indicates that this cmdlet appends the output to the specified file, rather than overwriting the existing contents of that file.</span></span>

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

### <span data-ttu-id="53862-137">-Como</span><span class="sxs-lookup"><span data-stu-id="53862-137">-As</span></span>

<span data-ttu-id="53862-138">Especifica o formato de saída.</span><span class="sxs-lookup"><span data-stu-id="53862-138">Specifies the output format.</span></span>
<span data-ttu-id="53862-139">CSV é o padrão.</span><span class="sxs-lookup"><span data-stu-id="53862-139">CSV is the default.</span></span>
<span data-ttu-id="53862-140">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="53862-140">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="53862-141">CSV.</span><span class="sxs-lookup"><span data-stu-id="53862-141">CSV.</span></span>
<span data-ttu-id="53862-142">Formato de valores separados por vírgulas (CSV).</span><span class="sxs-lookup"><span data-stu-id="53862-142">Comma-separated value (CSV) format.</span></span>
- <span data-ttu-id="53862-143">Script.</span><span class="sxs-lookup"><span data-stu-id="53862-143">Script.</span></span>
<span data-ttu-id="53862-144">Cria um `Set-Alias` comando para cada alias exportado.</span><span class="sxs-lookup"><span data-stu-id="53862-144">Creates a `Set-Alias` command for each exported alias.</span></span>
<span data-ttu-id="53862-145">Se você nomear o arquivo de saída com uma extensão de nome de arquivo .ps1, poderá executá-lo como um script para adicionar os aliases a qualquer sessão.</span><span class="sxs-lookup"><span data-stu-id="53862-145">If you name the output file with a .ps1 file name extension, you can run it as a script to add the aliases to any session.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ExportAliasFormat
Parameter Sets: (All)
Aliases:
Accepted values: Csv, Script

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53862-146">-Description</span><span class="sxs-lookup"><span data-stu-id="53862-146">-Description</span></span>

<span data-ttu-id="53862-147">Especifica a descrição do arquivo exportado.</span><span class="sxs-lookup"><span data-stu-id="53862-147">Specifies the description of the exported file.</span></span>
<span data-ttu-id="53862-148">A descrição aparecerá como um comentário na parte superior do arquivo, após as informações de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="53862-148">The description appears as a comment at the top of the file, following the header information.</span></span>

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

### <span data-ttu-id="53862-149">-Force</span><span class="sxs-lookup"><span data-stu-id="53862-149">-Force</span></span>

<span data-ttu-id="53862-150">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="53862-150">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="53862-151">Substitui o arquivo de saída, mesmo se o atributo somente leitura estiver definido no arquivo.</span><span class="sxs-lookup"><span data-stu-id="53862-151">Overwrites the output file, even if the read-only attribute is set on the file.</span></span>

<span data-ttu-id="53862-152">Por padrão, `Export-Alias` o substitui arquivos sem aviso, a menos que o atributo somente leitura ou oculto esteja definido ou o parâmetro **NoClobber** seja usado no comando.</span><span class="sxs-lookup"><span data-stu-id="53862-152">By default, `Export-Alias` overwrites files without warning, unless the read-only or hidden attribute is set or the **NoClobber** parameter is used in the command.</span></span>
<span data-ttu-id="53862-153">O parâmetro **NoClobber** tem precedência sobre o parâmetro **Force** quando ambos são usados em um comando.</span><span class="sxs-lookup"><span data-stu-id="53862-153">The **NoClobber** parameter takes precedence over the **Force** parameter when both are used in a command.</span></span>

<span data-ttu-id="53862-154">O parâmetro **Force** não pode forçar `Export-Alias` a substituição de arquivos pelo atributo Hidden.</span><span class="sxs-lookup"><span data-stu-id="53862-154">The **Force** parameter cannot force `Export-Alias` to overwrite files with the hidden attribute.</span></span>

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

### <span data-ttu-id="53862-155">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="53862-155">-LiteralPath</span></span>

<span data-ttu-id="53862-156">Especifica o caminho para o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="53862-156">Specifies the path to the output file.</span></span>
<span data-ttu-id="53862-157">Ao contrário de **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado.</span><span class="sxs-lookup"><span data-stu-id="53862-157">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="53862-158">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="53862-158">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="53862-159">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="53862-159">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="53862-160">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="53862-160">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="53862-161">-Name</span><span class="sxs-lookup"><span data-stu-id="53862-161">-Name</span></span>

<span data-ttu-id="53862-162">Especifica os nomes como uma matriz dos aliases a serem exportados.</span><span class="sxs-lookup"><span data-stu-id="53862-162">Specifies the names as an array of the aliases to export.</span></span>
<span data-ttu-id="53862-163">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="53862-163">Wildcards are permitted.</span></span>

<span data-ttu-id="53862-164">Por padrão, o `Export-Alias` exporta todos os aliases na sessão ou no escopo.</span><span class="sxs-lookup"><span data-stu-id="53862-164">By default, `Export-Alias` exports all aliases in the session or scope.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="53862-165">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="53862-165">-NoClobber</span></span>

<span data-ttu-id="53862-166">Indica que esse cmdlet impede `Export-Alias` a substituição de todos os arquivos, mesmo se o parâmetro **Force** for usado no comando.</span><span class="sxs-lookup"><span data-stu-id="53862-166">Indicates that this cmdlet prevents `Export-Alias` from overwriting any files, even if the **Force** parameter is used in the command.</span></span>

<span data-ttu-id="53862-167">Se o parâmetro **NoClobber** for omitido, o `Export-Alias` substituirá um arquivo existente sem aviso, a menos que o atributo somente leitura esteja definido no arquivo.</span><span class="sxs-lookup"><span data-stu-id="53862-167">If the **NoClobber** parameter is omitted, `Export-Alias` will overwrite an existing file without warning, unless the read-only attribute is set on the file.</span></span>
<span data-ttu-id="53862-168">*NoClobber* tem precedência sobre o parâmetro **Force** , que permite `Export-Alias` substituir um arquivo pelo atributo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="53862-168">*NoClobber* takes precedence over the **Force** parameter, which permits `Export-Alias` to overwrite a file with the read-only attribute.</span></span>

<span data-ttu-id="53862-169">*NoClobber* não impede que o parâmetro **Append** adicione conteúdo a um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="53862-169">*NoClobber* does not prevent the **Append** parameter from adding content to an existing file.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53862-170">-PassThru</span><span class="sxs-lookup"><span data-stu-id="53862-170">-PassThru</span></span>

<span data-ttu-id="53862-171">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="53862-171">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="53862-172">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="53862-172">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="53862-173">-Path</span><span class="sxs-lookup"><span data-stu-id="53862-173">-Path</span></span>

<span data-ttu-id="53862-174">Especifica o caminho para o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="53862-174">Specifies the path to the output file.</span></span>
<span data-ttu-id="53862-175">Caracteres curinga são permitidos, mas o valor do caminho resultante deve ser resolvido para um único nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="53862-175">Wildcards are permitted, but the resulting path value must resolve to a single file name.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="53862-176">-Escopo</span><span class="sxs-lookup"><span data-stu-id="53862-176">-Scope</span></span>

<span data-ttu-id="53862-177">Especifica o escopo do qual os aliases devem ser exportados.</span><span class="sxs-lookup"><span data-stu-id="53862-177">Specifies the scope from which the aliases should be exported.</span></span>
<span data-ttu-id="53862-178">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="53862-178">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="53862-179">Global</span><span class="sxs-lookup"><span data-stu-id="53862-179">Global</span></span>
- <span data-ttu-id="53862-180">Local</span><span class="sxs-lookup"><span data-stu-id="53862-180">Local</span></span>
- <span data-ttu-id="53862-181">script</span><span class="sxs-lookup"><span data-stu-id="53862-181">Script</span></span>
- <span data-ttu-id="53862-182">Um número relativo ao escopo atual (0 até o número de escopos em que 0 é o escopo atual e 1 é seu pai)</span><span class="sxs-lookup"><span data-stu-id="53862-182">A number relative to the current scope (0 through the number of scopes where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="53862-183">O valor padrão é Local.</span><span class="sxs-lookup"><span data-stu-id="53862-183">The default value is Local.</span></span>
<span data-ttu-id="53862-184">Para obter mais informações, consulte about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="53862-184">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="53862-185">-Confirm</span><span class="sxs-lookup"><span data-stu-id="53862-185">-Confirm</span></span>

<span data-ttu-id="53862-186">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="53862-186">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="53862-187">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="53862-187">-WhatIf</span></span>

<span data-ttu-id="53862-188">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="53862-188">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="53862-189">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="53862-189">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="53862-190">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="53862-190">CommonParameters</span></span>

<span data-ttu-id="53862-191">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="53862-191">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="53862-192">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="53862-192">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="53862-193">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="53862-193">INPUTS</span></span>

### <span data-ttu-id="53862-194">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="53862-194">None.</span></span>

<span data-ttu-id="53862-195">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="53862-195">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="53862-196">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="53862-196">OUTPUTS</span></span>

### <span data-ttu-id="53862-197">Nenhum ou System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="53862-197">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="53862-198">Quando você usa o parâmetro **PassThru** , `Export-Alias` retorna um objeto **System. Management. Automation. AliasInfo** que representa o alias.</span><span class="sxs-lookup"><span data-stu-id="53862-198">When you use the **Passthru** parameter, `Export-Alias` returns a **System.Management.Automation.AliasInfo** object that represents the alias.</span></span>
<span data-ttu-id="53862-199">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="53862-199">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="53862-200">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="53862-200">NOTES</span></span>

* <span data-ttu-id="53862-201">Somente é possível usar o Export-Alias para exportar aliases para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="53862-201">You can only Export-Aliases to a file.</span></span>

## <span data-ttu-id="53862-202">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="53862-202">RELATED LINKS</span></span>

[<span data-ttu-id="53862-203">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="53862-203">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="53862-204">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="53862-204">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="53862-205">New-Alias</span><span class="sxs-lookup"><span data-stu-id="53862-205">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="53862-206">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="53862-206">Set-Alias</span></span>](Set-Alias.md)
