---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Item
ms.openlocfilehash: ebb79f16447aef2dd194505d805a34353f710e69
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597814"
---
# <span data-ttu-id="38493-102">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="38493-102">Invoke-Item</span></span>

## <span data-ttu-id="38493-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="38493-103">SYNOPSIS</span></span>
<span data-ttu-id="38493-104">Executa a ação padrão no item especificado.</span><span class="sxs-lookup"><span data-stu-id="38493-104">Performs the default action on the specified item.</span></span>

## <span data-ttu-id="38493-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="38493-105">SYNTAX</span></span>

### <span data-ttu-id="38493-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="38493-106">Path (Default)</span></span>

```
Invoke-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="38493-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="38493-107">LiteralPath</span></span>

```
Invoke-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="38493-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="38493-108">DESCRIPTION</span></span>

<span data-ttu-id="38493-109">O `Invoke-Item` cmdlet executa a ação padrão no item especificado.</span><span class="sxs-lookup"><span data-stu-id="38493-109">The `Invoke-Item` cmdlet performs the default action on the specified item.</span></span>
<span data-ttu-id="38493-110">Por exemplo, ele executa um arquivo executável ou abre um arquivo de documento no aplicativo associado ao tipo de arquivo do documento.</span><span class="sxs-lookup"><span data-stu-id="38493-110">For example, it runs an executable file or opens a document file in the application associated with the document file type.</span></span>
<span data-ttu-id="38493-111">A ação padrão depende do tipo de item e é determinada pelo provedor do PowerShell que fornece acesso aos dados.</span><span class="sxs-lookup"><span data-stu-id="38493-111">The default action depends on the type of item and is determined by the PowerShell provider that provides access to the data.</span></span>

## <span data-ttu-id="38493-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="38493-112">EXAMPLES</span></span>

### <span data-ttu-id="38493-113">Exemplo 1: abrir um arquivo</span><span class="sxs-lookup"><span data-stu-id="38493-113">Example 1: Open a file</span></span>

<span data-ttu-id="38493-114">Esse comando abre o arquivo "aliasApr04.doc" no Microsoft Office Word.</span><span class="sxs-lookup"><span data-stu-id="38493-114">This command opens the file "aliasApr04.doc" in Microsoft Office Word.</span></span>
<span data-ttu-id="38493-115">Nesse caso, abrir no Word é a ação padrão para arquivos ". doc".</span><span class="sxs-lookup"><span data-stu-id="38493-115">In this case, opening in Word is the default action for ".doc" files.</span></span>

```powershell
Invoke-Item "C:\Test\aliasApr04.doc"
```

### <span data-ttu-id="38493-116">Exemplo 2: abrir todos os arquivos de um tipo específico</span><span class="sxs-lookup"><span data-stu-id="38493-116">Example 2: Open all files of a specific type</span></span>

<span data-ttu-id="38493-117">Esse comando abre todas as planilhas Microsoft Office Excel na `C:\Documents and
Settings\Lister\My Documents` pasta.</span><span class="sxs-lookup"><span data-stu-id="38493-117">This command opens all of the Microsoft Office Excel spreadsheets in the `C:\Documents and
Settings\Lister\My Documents` folder.</span></span> <span data-ttu-id="38493-118">Cada planilha é aberta em uma nova instância do Excel.</span><span class="sxs-lookup"><span data-stu-id="38493-118">Each spreadsheet is opened in a new instance of Excel.</span></span>
<span data-ttu-id="38493-119">Nesse caso, abrir no Excel é a ação padrão para `.xls` arquivos.</span><span class="sxs-lookup"><span data-stu-id="38493-119">In this case, opening in Excel is the default action for `.xls` files.</span></span>

```powershell
Invoke-Item "C:\Documents and Settings\Lister\My Documents\*.xls"
```

## <span data-ttu-id="38493-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="38493-120">PARAMETERS</span></span>

### <span data-ttu-id="38493-121">-Credential</span><span class="sxs-lookup"><span data-stu-id="38493-121">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="38493-122">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38493-122">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="38493-123">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="38493-123">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="38493-124">-Excluir</span><span class="sxs-lookup"><span data-stu-id="38493-124">-Exclude</span></span>

<span data-ttu-id="38493-125">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="38493-125">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="38493-126">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="38493-126">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="38493-127">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="38493-127">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="38493-128">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="38493-128">Wildcard characters are permitted.</span></span> <span data-ttu-id="38493-129">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="38493-129">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="38493-130">-Filter</span><span class="sxs-lookup"><span data-stu-id="38493-130">-Filter</span></span>

<span data-ttu-id="38493-131">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="38493-131">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="38493-132">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="38493-132">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="38493-133">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="38493-133">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="38493-134">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="38493-134">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="38493-135">-Incluir</span><span class="sxs-lookup"><span data-stu-id="38493-135">-Include</span></span>

<span data-ttu-id="38493-136">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="38493-136">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="38493-137">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="38493-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="38493-138">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="38493-138">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="38493-139">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="38493-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="38493-140">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="38493-140">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="38493-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="38493-141">-LiteralPath</span></span>

<span data-ttu-id="38493-142">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="38493-142">Specifies a path to one or more locations.</span></span> <span data-ttu-id="38493-143">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="38493-143">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="38493-144">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="38493-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="38493-145">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="38493-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="38493-146">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="38493-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="38493-147">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="38493-147">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="38493-148">-Path</span><span class="sxs-lookup"><span data-stu-id="38493-148">-Path</span></span>

<span data-ttu-id="38493-149">Especifica o caminho para o item selecionado.</span><span class="sxs-lookup"><span data-stu-id="38493-149">Specifies the path to the selected item.</span></span>
<span data-ttu-id="38493-150">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="38493-150">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="38493-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="38493-151">-Confirm</span></span>

<span data-ttu-id="38493-152">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38493-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="38493-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="38493-153">-WhatIf</span></span>

<span data-ttu-id="38493-154">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="38493-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="38493-155">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="38493-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="38493-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="38493-156">CommonParameters</span></span>

<span data-ttu-id="38493-157">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="38493-157">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="38493-158">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="38493-158">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="38493-159">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="38493-159">INPUTS</span></span>

### <span data-ttu-id="38493-160">System.String</span><span class="sxs-lookup"><span data-stu-id="38493-160">System.String</span></span>

<span data-ttu-id="38493-161">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38493-161">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="38493-162">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="38493-162">OUTPUTS</span></span>

### <span data-ttu-id="38493-163">Nenhum</span><span class="sxs-lookup"><span data-stu-id="38493-163">None</span></span>

<span data-ttu-id="38493-164">Esse comando não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="38493-164">The command does not generate any output.</span></span>
<span data-ttu-id="38493-165">No entanto, a saída pode ser gerada pelo item que ela chama.</span><span class="sxs-lookup"><span data-stu-id="38493-165">However, output might be generated by the item that it invokes.</span></span>

## <span data-ttu-id="38493-166">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="38493-166">NOTES</span></span>

<span data-ttu-id="38493-167">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="38493-167">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="38493-168">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="38493-168">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="38493-169">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="38493-169">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="38493-170">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="38493-170">RELATED LINKS</span></span>

[<span data-ttu-id="38493-171">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="38493-171">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="38493-172">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="38493-172">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="38493-173">Get-Item</span><span class="sxs-lookup"><span data-stu-id="38493-173">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="38493-174">Move-Item</span><span class="sxs-lookup"><span data-stu-id="38493-174">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="38493-175">New-Item</span><span class="sxs-lookup"><span data-stu-id="38493-175">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="38493-176">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="38493-176">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="38493-177">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="38493-177">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="38493-178">Set-Item</span><span class="sxs-lookup"><span data-stu-id="38493-178">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="38493-179">about_Providers</span><span class="sxs-lookup"><span data-stu-id="38493-179">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

