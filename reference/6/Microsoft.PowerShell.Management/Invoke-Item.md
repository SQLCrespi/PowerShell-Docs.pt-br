---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-item?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Item
ms.openlocfilehash: 5d4fafe4dbb92f40e31b0af963256fdce50b5a8b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194065"
---
# <span data-ttu-id="d3f1d-103">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="d3f1d-103">Invoke-Item</span></span>

## <span data-ttu-id="d3f1d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d3f1d-104">SYNOPSIS</span></span>
<span data-ttu-id="d3f1d-105">Executa a ação padrão no item especificado.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-105">Performs the default action on the specified item.</span></span>

## <span data-ttu-id="d3f1d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d3f1d-106">SYNTAX</span></span>

### <span data-ttu-id="d3f1d-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="d3f1d-107">Path (Default)</span></span>

```
Invoke-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d3f1d-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d3f1d-108">LiteralPath</span></span>

```
Invoke-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d3f1d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d3f1d-109">DESCRIPTION</span></span>

<span data-ttu-id="d3f1d-110">O `Invoke-Item` cmdlet executa a ação padrão no item especificado.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-110">The `Invoke-Item` cmdlet performs the default action on the specified item.</span></span>
<span data-ttu-id="d3f1d-111">Por exemplo, ele executa um arquivo executável ou abre um arquivo de documento no aplicativo associado ao tipo de arquivo do documento.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-111">For example, it runs an executable file or opens a document file in the application associated with the document file type.</span></span>
<span data-ttu-id="d3f1d-112">A ação padrão depende do tipo de item e é determinada pelo provedor do PowerShell que fornece acesso aos dados.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-112">The default action depends on the type of item and is determined by the PowerShell provider that provides access to the data.</span></span>

## <span data-ttu-id="d3f1d-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d3f1d-113">EXAMPLES</span></span>

### <span data-ttu-id="d3f1d-114">Exemplo 1: abrir um arquivo</span><span class="sxs-lookup"><span data-stu-id="d3f1d-114">Example 1: Open a file</span></span>

<span data-ttu-id="d3f1d-115">Esse comando abre o arquivo "aliasApr04.doc" no Microsoft Office Word.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-115">This command opens the file "aliasApr04.doc" in Microsoft Office Word.</span></span>
<span data-ttu-id="d3f1d-116">Nesse caso, abrir no Word é a ação padrão para arquivos ". doc".</span><span class="sxs-lookup"><span data-stu-id="d3f1d-116">In this case, opening in Word is the default action for ".doc" files.</span></span>

```powershell
Invoke-Item "C:\Test\aliasApr04.doc"
```

### <span data-ttu-id="d3f1d-117">Exemplo 2: abrir todos os arquivos de um tipo específico</span><span class="sxs-lookup"><span data-stu-id="d3f1d-117">Example 2: Open all files of a specific type</span></span>

<span data-ttu-id="d3f1d-118">Esse comando abre todas as planilhas Microsoft Office Excel na `C:\Documents and
Settings\Lister\My Documents` pasta.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-118">This command opens all of the Microsoft Office Excel spreadsheets in the `C:\Documents and
Settings\Lister\My Documents` folder.</span></span> <span data-ttu-id="d3f1d-119">Cada planilha é aberta em uma nova instância do Excel.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-119">Each spreadsheet is opened in a new instance of Excel.</span></span>
<span data-ttu-id="d3f1d-120">Nesse caso, abrir no Excel é a ação padrão para `.xls` arquivos.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-120">In this case, opening in Excel is the default action for `.xls` files.</span></span>

```powershell
Invoke-Item "C:\Documents and Settings\Lister\My Documents\*.xls"
```

## <span data-ttu-id="d3f1d-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d3f1d-121">PARAMETERS</span></span>

### <span data-ttu-id="d3f1d-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="d3f1d-122">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="d3f1d-123">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-123">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="d3f1d-124">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="d3f1d-124">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="d3f1d-125">-Excluir</span><span class="sxs-lookup"><span data-stu-id="d3f1d-125">-Exclude</span></span>

<span data-ttu-id="d3f1d-126">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-126">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="d3f1d-127">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="d3f1d-127">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="d3f1d-128">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="d3f1d-128">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="d3f1d-129">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-129">Wildcard characters are permitted.</span></span> <span data-ttu-id="d3f1d-130">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-130">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="d3f1d-131">-Filter</span><span class="sxs-lookup"><span data-stu-id="d3f1d-131">-Filter</span></span>

<span data-ttu-id="d3f1d-132">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="d3f1d-132">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="d3f1d-133">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-133">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="d3f1d-134">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="d3f1d-134">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="d3f1d-135">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-135">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="d3f1d-136">-Incluir</span><span class="sxs-lookup"><span data-stu-id="d3f1d-136">-Include</span></span>

<span data-ttu-id="d3f1d-137">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="d3f1d-138">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="d3f1d-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="d3f1d-139">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="d3f1d-139">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="d3f1d-140">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="d3f1d-141">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-141">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="d3f1d-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d3f1d-142">-LiteralPath</span></span>

<span data-ttu-id="d3f1d-143">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-143">Specifies a path to one or more locations.</span></span> <span data-ttu-id="d3f1d-144">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-144">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="d3f1d-145">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="d3f1d-146">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="d3f1d-147">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="d3f1d-148">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="d3f1d-148">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="d3f1d-149">-Path</span><span class="sxs-lookup"><span data-stu-id="d3f1d-149">-Path</span></span>

<span data-ttu-id="d3f1d-150">Especifica o caminho para o item selecionado.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-150">Specifies the path to the selected item.</span></span>
<span data-ttu-id="d3f1d-151">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-151">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="d3f1d-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d3f1d-152">-Confirm</span></span>

<span data-ttu-id="d3f1d-153">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d3f1d-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d3f1d-154">-WhatIf</span></span>

<span data-ttu-id="d3f1d-155">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-155">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d3f1d-156">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-156">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d3f1d-157">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d3f1d-157">CommonParameters</span></span>

<span data-ttu-id="d3f1d-158">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="d3f1d-158">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="d3f1d-159">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d3f1d-159">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d3f1d-160">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d3f1d-160">INPUTS</span></span>

### <span data-ttu-id="d3f1d-161">System.String</span><span class="sxs-lookup"><span data-stu-id="d3f1d-161">System.String</span></span>

<span data-ttu-id="d3f1d-162">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-162">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="d3f1d-163">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d3f1d-163">OUTPUTS</span></span>

### <span data-ttu-id="d3f1d-164">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d3f1d-164">None</span></span>

<span data-ttu-id="d3f1d-165">Esse comando não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-165">The command does not generate any output.</span></span>
<span data-ttu-id="d3f1d-166">No entanto, a saída pode ser gerada pelo item que ela chama.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-166">However, output might be generated by the item that it invokes.</span></span>

## <span data-ttu-id="d3f1d-167">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d3f1d-167">NOTES</span></span>

<span data-ttu-id="d3f1d-168">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="d3f1d-168">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="d3f1d-169">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="d3f1d-169">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="d3f1d-170">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d3f1d-170">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="d3f1d-171">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d3f1d-171">RELATED LINKS</span></span>

[<span data-ttu-id="d3f1d-172">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="d3f1d-172">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="d3f1d-173">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="d3f1d-173">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="d3f1d-174">Get-Item</span><span class="sxs-lookup"><span data-stu-id="d3f1d-174">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="d3f1d-175">Move-Item</span><span class="sxs-lookup"><span data-stu-id="d3f1d-175">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="d3f1d-176">New-Item</span><span class="sxs-lookup"><span data-stu-id="d3f1d-176">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="d3f1d-177">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="d3f1d-177">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="d3f1d-178">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="d3f1d-178">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="d3f1d-179">Set-Item</span><span class="sxs-lookup"><span data-stu-id="d3f1d-179">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="d3f1d-180">about_Providers</span><span class="sxs-lookup"><span data-stu-id="d3f1d-180">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
