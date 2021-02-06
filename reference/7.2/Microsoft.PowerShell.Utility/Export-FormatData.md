---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-formatdata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-FormatData
ms.openlocfilehash: d42b108d469ed8989628a6c0b4214af4afc0db00
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603328"
---
# <span data-ttu-id="906ea-102">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="906ea-102">Export-FormatData</span></span>

## <span data-ttu-id="906ea-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="906ea-103">SYNOPSIS</span></span>
<span data-ttu-id="906ea-104">Salva os dados de formatação da sessão atual em um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="906ea-104">Saves formatting data from the current session in a formatting file.</span></span>

## <span data-ttu-id="906ea-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="906ea-105">SYNTAX</span></span>

### <span data-ttu-id="906ea-106">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="906ea-106">ByPath (Default)</span></span>

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -Path <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

### <span data-ttu-id="906ea-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="906ea-107">ByLiteralPath</span></span>

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -LiteralPath <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

## <span data-ttu-id="906ea-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="906ea-108">DESCRIPTION</span></span>

<span data-ttu-id="906ea-109">O `Export-FormatData` cmdlet cria arquivos de formatação do PowerShell (format.ps1XML) dos objetos de formatação na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="906ea-109">The `Export-FormatData` cmdlet creates PowerShell formatting files (format.ps1xml) from the formatting objects in the current session.</span></span> <span data-ttu-id="906ea-110">Ele usa os objetos **ExtendedTypeDefinition** que `Get-FormatData` retorna e salva-os em um arquivo em formato XML.</span><span class="sxs-lookup"><span data-stu-id="906ea-110">It takes the **ExtendedTypeDefinition** objects that `Get-FormatData` returns and saves them in a file in XML format.</span></span>

<span data-ttu-id="906ea-111">O PowerShell usa os dados em arquivos de formatação (format.ps1XML) para gerar a exibição padrão de objetos do Microsoft .NET Framework na sessão.</span><span class="sxs-lookup"><span data-stu-id="906ea-111">PowerShell uses the data in formatting files (format.ps1xml) to generate the default display of Microsoft .NET Framework objects in the session.</span></span> <span data-ttu-id="906ea-112">Você pode exibir e editar os arquivos de formatação e usar o cmdlet Update-FormatData para adicionar os dados de formatação a uma sessão.</span><span class="sxs-lookup"><span data-stu-id="906ea-112">You can view and edit the formatting files and use the Update-FormatData cmdlet to add the formatting data to a session.</span></span>

<span data-ttu-id="906ea-113">Para obter mais informações sobre como formatar arquivos no PowerShell, consulte [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="906ea-113">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="906ea-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="906ea-114">EXAMPLES</span></span>

### <span data-ttu-id="906ea-115">Exemplo 1: exportar dados de formato de sessão</span><span class="sxs-lookup"><span data-stu-id="906ea-115">Example 1: Export session format data</span></span>

```powershell
Get-FormatData -TypeName "*" | Export-FormatData -Path "allformat.ps1xml" -IncludeScriptBlock
```

<span data-ttu-id="906ea-116">Este comando exporta todos os dados de formato presentes na sessão para o arquivo AllFormat.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="906ea-116">This command exports all of the format data in the session to the AllFormat.ps1xml file.</span></span>

<span data-ttu-id="906ea-117">O comando usa o `Get-FormatData` cmdlet para obter os dados de formato na sessão.</span><span class="sxs-lookup"><span data-stu-id="906ea-117">The command uses the `Get-FormatData` cmdlet to get the format data in the session.</span></span> <span data-ttu-id="906ea-118">Um valor de `*` (All) para o parâmetro **TypeName** direciona o cmdlet para obter todos os dados na sessão.</span><span class="sxs-lookup"><span data-stu-id="906ea-118">A value of `*` (all) for the **TypeName** parameter directs the cmdlet to get all of the data in the session.</span></span>

<span data-ttu-id="906ea-119">O comando usa um operador de pipeline ( `|` ) para enviar os dados de formato do `Get-FormatData` comando para o `Export-FormatData` cmdlet, que exporta os dados de formato para o arquivo de AllFormat.ps1.</span><span class="sxs-lookup"><span data-stu-id="906ea-119">The command uses a pipeline operator (`|`) to send the format data from the `Get-FormatData` command to the `Export-FormatData` cmdlet, which exports the format data to the AllFormat.ps1 file.</span></span>

<span data-ttu-id="906ea-120">O `Export-FormatData` comando usa o parâmetro **IncludeScriptBlock** para incluir blocos de script no formato de dados no arquivo.</span><span class="sxs-lookup"><span data-stu-id="906ea-120">The `Export-FormatData` command uses the **IncludeScriptBlock** parameter to include script blocks in the format data in the file.</span></span>

### <span data-ttu-id="906ea-121">Exemplo 2: exportar dados de formato para um tipo</span><span class="sxs-lookup"><span data-stu-id="906ea-121">Example 2: Export format data for a type</span></span>

```powershell
$F = Get-FormatData -TypeName "helpinfoshort"
Export-FormatData -InputObject $F -Path "c:\test\help.format.ps1xml" -IncludeScriptBlock
```

<span data-ttu-id="906ea-122">Esses comandos exportam os dados de formato para o tipo **HelpInfoShort** para o arquivo XML Help.format.ps1.</span><span class="sxs-lookup"><span data-stu-id="906ea-122">These commands export the format data for the **HelpInfoShort** type to the Help.format.ps1xml file.</span></span>

<span data-ttu-id="906ea-123">O primeiro comando usa o `Get-FormatData` cmdlet para obter os dados de formato para o tipo **HelpInfoShort** e o salva na `$F` variável.</span><span class="sxs-lookup"><span data-stu-id="906ea-123">The first command uses the `Get-FormatData` cmdlet to get the format data for the **HelpInfoShort** type, and it saves it in the `$F` variable.</span></span>

<span data-ttu-id="906ea-124">O segundo comando usa o parâmetro **InputObject** do `Export-FormatData` cmdlet para inserir os dados de formato salvos na `$F` variável.</span><span class="sxs-lookup"><span data-stu-id="906ea-124">The second command uses the **InputObject** parameter of the `Export-FormatData` cmdlet to enter the format data saved in the `$F` variable.</span></span> <span data-ttu-id="906ea-125">Ele também usa o parâmetro **IncludeScriptBlock** para incluir blocos de script na saída.</span><span class="sxs-lookup"><span data-stu-id="906ea-125">It also uses the **IncludeScriptBlock** parameter to include script blocks in the output.</span></span>

### <span data-ttu-id="906ea-126">Exemplo 3: exportar dados de formato sem um bloco de script</span><span class="sxs-lookup"><span data-stu-id="906ea-126">Example 3: Export format data without a script block</span></span>

```powershell
Get-FormatData -TypeName "System.Diagnostics.Process" | Export-FormatData -Path process.format.ps1xml
Update-FormatData -PrependPath ".\process.format.ps1xml"
Get-Process p*
```

```Output
Handles  NPM(K)  PM(K)  WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------  -----  ----- -----   ------    -- -----------
323                                       5600 powershell
336                                       3900 powershell_ise
138                                       4076 PresentationFontCache
```

<span data-ttu-id="906ea-127">Este exemplo mostra o efeito de omitir o parâmetro **IncludeScriptBlock** de um `Export-FormatData` comando.</span><span class="sxs-lookup"><span data-stu-id="906ea-127">This example shows the effect of omitting the **IncludeScriptBlock** parameter from an `Export-FormatData` command.</span></span>

<span data-ttu-id="906ea-128">O primeiro comando usa o `Get-FormatData` cmdlet para obter os dados de formato para o objeto **System. Diagnostics. Process** que o cmdlet Get-Process retorna.</span><span class="sxs-lookup"><span data-stu-id="906ea-128">The first command uses the `Get-FormatData` cmdlet to get the format data for the **System.Diagnostics.Process** object that the Get-Process cmdlet returns.</span></span> <span data-ttu-id="906ea-129">O comando usa um operador de pipeline ( `|` ) para enviar os dados de formatação para o `Export-FormatData` cmdlet, que exporta para o arquivo XML Process.format.ps1no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="906ea-129">The command uses a pipeline operator (`|`) to send the formatting data to the `Export-FormatData` cmdlet, which exports it to the Process.format.ps1xml file in the current directory.</span></span>

<span data-ttu-id="906ea-130">Nesse caso, o `Export-FormatData` comando não usa o parâmetro **IncludeScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="906ea-130">In this case, the `Export-FormatData` command does not use the **IncludeScriptBlock** parameter.</span></span>

<span data-ttu-id="906ea-131">O segundo comando usa o `Update-FormatData` cmdlet para adicionar o Process.format.ps1arquivo XML à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="906ea-131">The second command uses the `Update-FormatData` cmdlet to add the Process.format.ps1xml file to the current session.</span></span> <span data-ttu-id="906ea-132">O comando usa o parâmetro **PrependPath** para garantir que os dados de formatação para objetos de processo no arquivo xml de Process.format.ps1sejam encontrados antes dos dados de formatação padrão para objetos de processo.</span><span class="sxs-lookup"><span data-stu-id="906ea-132">The command uses the **PrependPath** parameter to ensure that the formatting data for process objects in the Process.format.ps1xml file is found before the standard formatting data for process objects.</span></span>

<span data-ttu-id="906ea-133">O terceiro comando mostra os efeitos dessa alteração.</span><span class="sxs-lookup"><span data-stu-id="906ea-133">The third command shows the effects of this change.</span></span> <span data-ttu-id="906ea-134">O comando usa o `Get-Process` cmdlet para obter processos com nomes que começam com P. A saída mostra que os valores de propriedade que são calculados usando blocos de script estão ausentes na exibição.</span><span class="sxs-lookup"><span data-stu-id="906ea-134">The command uses the `Get-Process` cmdlet to get processes that have names that begin with P. The output shows that property values that are calculated by using script blocks are missing from the display.</span></span>

## <span data-ttu-id="906ea-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="906ea-135">PARAMETERS</span></span>

### <span data-ttu-id="906ea-136">-Force</span><span class="sxs-lookup"><span data-stu-id="906ea-136">-Force</span></span>

<span data-ttu-id="906ea-137">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="906ea-137">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="906ea-138">-IncludeScriptBlock</span><span class="sxs-lookup"><span data-stu-id="906ea-138">-IncludeScriptBlock</span></span>

<span data-ttu-id="906ea-139">Indica se os blocos de script nos dados de formato são exportados.</span><span class="sxs-lookup"><span data-stu-id="906ea-139">Indicates whether script blocks in the format data are exported.</span></span>

<span data-ttu-id="906ea-140">Já que os blocos de script contêm código e podem ser usados de maneira mal intencionada, eles não são exportados por padrão.</span><span class="sxs-lookup"><span data-stu-id="906ea-140">Because script blocks contain code and can be used maliciously, they are not exported by default.</span></span>

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

### <span data-ttu-id="906ea-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="906ea-141">-InputObject</span></span>

<span data-ttu-id="906ea-142">Especifica os objetos de dados de formato a serem exportados.</span><span class="sxs-lookup"><span data-stu-id="906ea-142">Specifies the format data objects to be exported.</span></span> <span data-ttu-id="906ea-143">Insira uma variável que contém os objetos ou um comando que obtém os objetos, como um `Get-FormatData` comando.</span><span class="sxs-lookup"><span data-stu-id="906ea-143">Enter a variable that contains the objects or a command that gets the objects, such as a `Get-FormatData` command.</span></span> <span data-ttu-id="906ea-144">Você também pode canalizar os objetos de `Get-FormatData` para `Export-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="906ea-144">You can also pipe the objects from `Get-FormatData` to `Export-FormatData`.</span></span>

```yaml
Type: System.Management.Automation.ExtendedTypeDefinition[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="906ea-145">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="906ea-145">-LiteralPath</span></span>

<span data-ttu-id="906ea-146">Especifica um local para o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="906ea-146">Specifies a location for the output file.</span></span> <span data-ttu-id="906ea-147">Ao contrário do parâmetro **Path**, o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="906ea-147">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="906ea-148">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="906ea-148">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="906ea-149">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="906ea-149">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="906ea-150">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="906ea-150">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="906ea-151">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="906ea-151">-NoClobber</span></span>

<span data-ttu-id="906ea-152">Indica que o cmdlet não substitui os arquivos existentes.</span><span class="sxs-lookup"><span data-stu-id="906ea-152">Indicates that the cmdlet does not overwrite existing files.</span></span> <span data-ttu-id="906ea-153">Por padrão, `Export-FormatData` o substitui arquivos sem aviso, a menos que o arquivo tenha o atributo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="906ea-153">By default, `Export-FormatData` overwrites files without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="906ea-154">Para direcionar `Export-FormatData` para substituir arquivos somente leitura, use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="906ea-154">To direct `Export-FormatData` to overwrite read-only files, use the **Force** parameter.</span></span>

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

### <span data-ttu-id="906ea-155">-Path</span><span class="sxs-lookup"><span data-stu-id="906ea-155">-Path</span></span>

<span data-ttu-id="906ea-156">Especifica um local para o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="906ea-156">Specifies a location for the output file.</span></span>
<span data-ttu-id="906ea-157">Insira um caminho (opcional) e um nome de arquivo com uma extensão de nome de arquivo format.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="906ea-157">Enter a path (optional) and file name with a format.ps1xml file name extension.</span></span>
<span data-ttu-id="906ea-158">Se você omitir o caminho, o `Export-FormatData` criará o arquivo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="906ea-158">If you omit the path, `Export-FormatData` creates the file in the current directory.</span></span>

<span data-ttu-id="906ea-159">Se você usar uma extensão de nome de arquivo diferente de. ps1xml, o `Update-FormatData` cmdlet não reconhecerá o arquivo.</span><span class="sxs-lookup"><span data-stu-id="906ea-159">If you use a file name extension other than .ps1xml, the `Update-FormatData` cmdlet will not recognize the file.</span></span>

<span data-ttu-id="906ea-160">Se você especificar um arquivo existente, o `Export-FormatData` substituirá o arquivo sem aviso, a menos que o arquivo tenha o atributo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="906ea-160">If you specify an existing file, `Export-FormatData` overwrites the file without warning, unless the file has the read-only attribute.</span></span> <span data-ttu-id="906ea-161">Para substituir um arquivo somente leitura, use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="906ea-161">To overwrite a read-only file, use the **Force** parameter.</span></span> <span data-ttu-id="906ea-162">Para impedir que arquivos sejam substituídos, use o parâmetro **NoClobber** .</span><span class="sxs-lookup"><span data-stu-id="906ea-162">To prevent files from being overwritten, use the **NoClobber** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: FilePath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="906ea-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="906ea-163">CommonParameters</span></span>

<span data-ttu-id="906ea-164">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="906ea-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="906ea-165">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="906ea-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="906ea-166">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="906ea-166">INPUTS</span></span>

### <span data-ttu-id="906ea-167">System. Management. Automation. ExtendedTypeDefinition</span><span class="sxs-lookup"><span data-stu-id="906ea-167">System.Management.Automation.ExtendedTypeDefinition</span></span>

<span data-ttu-id="906ea-168">Você pode canalizar objetos **ExtendedTypeDefinition** de `Get-FormatData` para `Export-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="906ea-168">You can pipe **ExtendedTypeDefinition** objects from `Get-FormatData` to `Export-FormatData`.</span></span>

## <span data-ttu-id="906ea-169">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="906ea-169">OUTPUTS</span></span>

### <span data-ttu-id="906ea-170">Nenhum</span><span class="sxs-lookup"><span data-stu-id="906ea-170">None</span></span>

<span data-ttu-id="906ea-171">`Export-FormatData` Não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="906ea-171">`Export-FormatData` does not return any objects.</span></span>
<span data-ttu-id="906ea-172">Ele gera um arquivo e o salva-o no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="906ea-172">It generates a file and saves it in the specified path.</span></span>

## <span data-ttu-id="906ea-173">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="906ea-173">NOTES</span></span>

- <span data-ttu-id="906ea-174">Para usar qualquer arquivo de formatação, incluindo um arquivo de formatação exportado, a diretriz de execução para a sessão deve permitir a execução de scripts e de arquivos de configuração.</span><span class="sxs-lookup"><span data-stu-id="906ea-174">To use any formatting file, including an exported formatting file, the execution policy for the session must allow scripts and configuration files to run.</span></span> <span data-ttu-id="906ea-175">Para obter mais informações, consulte [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="906ea-175">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="906ea-176">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="906ea-176">RELATED LINKS</span></span>

[<span data-ttu-id="906ea-177">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="906ea-177">Get-FormatData</span></span>](Get-FormatData.md)

[<span data-ttu-id="906ea-178">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="906ea-178">Update-FormatData</span></span>](Update-FormatData.md)
