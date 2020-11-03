---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Item
ms.openlocfilehash: 6aac74b9b084996377b97997ab78972cb28b0959
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194162"
---
# <span data-ttu-id="0b8f0-103">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="0b8f0-103">Invoke-Item</span></span>

## <span data-ttu-id="0b8f0-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0b8f0-104">SYNOPSIS</span></span>
<span data-ttu-id="0b8f0-105">Executa a ação padrão no item especificado.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-105">Performs the default action on the specified item.</span></span>

## <span data-ttu-id="0b8f0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0b8f0-106">SYNTAX</span></span>

### <span data-ttu-id="0b8f0-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="0b8f0-107">Path (Default)</span></span>

```
Invoke-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="0b8f0-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0b8f0-108">LiteralPath</span></span>

```
Invoke-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="0b8f0-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b8f0-109">DESCRIPTION</span></span>

<span data-ttu-id="0b8f0-110">O `Invoke-Item` cmdlet executa a ação padrão no item especificado.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-110">The `Invoke-Item` cmdlet performs the default action on the specified item.</span></span>
<span data-ttu-id="0b8f0-111">Por exemplo, ele executa um arquivo executável ou abre um arquivo de documento no aplicativo associado ao tipo de arquivo do documento.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-111">For example, it runs an executable file or opens a document file in the application associated with the document file type.</span></span>
<span data-ttu-id="0b8f0-112">A ação padrão depende do tipo de item e é determinada pelo provedor do PowerShell que fornece acesso aos dados.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-112">The default action depends on the type of item and is determined by the PowerShell provider that provides access to the data.</span></span>

## <span data-ttu-id="0b8f0-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0b8f0-113">EXAMPLES</span></span>

### <span data-ttu-id="0b8f0-114">Exemplo 1: abrir um arquivo</span><span class="sxs-lookup"><span data-stu-id="0b8f0-114">Example 1: Open a file</span></span>

<span data-ttu-id="0b8f0-115">Esse comando abre o arquivo "aliasApr04.doc" no Microsoft Office Word.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-115">This command opens the file "aliasApr04.doc" in Microsoft Office Word.</span></span>
<span data-ttu-id="0b8f0-116">Nesse caso, abrir no Word é a ação padrão para arquivos ". doc".</span><span class="sxs-lookup"><span data-stu-id="0b8f0-116">In this case, opening in Word is the default action for ".doc" files.</span></span>

```powershell
Invoke-Item "C:\Test\aliasApr04.doc"
```

### <span data-ttu-id="0b8f0-117">Exemplo 2: abrir todos os arquivos de um tipo específico</span><span class="sxs-lookup"><span data-stu-id="0b8f0-117">Example 2: Open all files of a specific type</span></span>

<span data-ttu-id="0b8f0-118">Esse comando abre todas as planilhas Microsoft Office Excel na pasta "C:\Documents and Settings\Lister\My Documents".</span><span class="sxs-lookup"><span data-stu-id="0b8f0-118">This command opens all of the Microsoft Office Excel spreadsheets in the "C:\Documents and Settings\Lister\My Documents" folder.</span></span>
<span data-ttu-id="0b8f0-119">Cada planilha é aberta em uma nova instância do Excel.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-119">Each spreadsheet is opened in a new instance of Excel.</span></span>
<span data-ttu-id="0b8f0-120">Nesse caso, abrir no Excel é a ação padrão para arquivos ". xls".</span><span class="sxs-lookup"><span data-stu-id="0b8f0-120">In this case, opening in Excel is the default action for ".xls" files.</span></span>

```powershell
Invoke-Item "C:\Documents and Settings\Lister\My Documents\*.xls"
```

## <span data-ttu-id="0b8f0-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0b8f0-121">PARAMETERS</span></span>

### <span data-ttu-id="0b8f0-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="0b8f0-122">-Credential</span></span>

<span data-ttu-id="0b8f0-123">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-123">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="0b8f0-124">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-124">The default is the current user.</span></span>

<span data-ttu-id="0b8f0-125">Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-125">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="0b8f0-126">Se você digitar um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-126">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="0b8f0-127">Nenhum provedor instalado com o Windows PowerShell dá suporte a esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-127">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

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

### <span data-ttu-id="0b8f0-128">-Excluir</span><span class="sxs-lookup"><span data-stu-id="0b8f0-128">-Exclude</span></span>

<span data-ttu-id="0b8f0-129">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui da operação.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-129">Specifies, as a string array, an item or items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="0b8f0-130">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="0b8f0-130">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="0b8f0-131">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="0b8f0-131">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="0b8f0-132">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0b8f0-133">-Filter</span><span class="sxs-lookup"><span data-stu-id="0b8f0-133">-Filter</span></span>

<span data-ttu-id="0b8f0-134">Especifica um filtro no formato ou idioma do provedor.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-134">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="0b8f0-135">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="0b8f0-135">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="0b8f0-136">A sintaxe do filtro, incluindo o uso de caracteres curinga, depende do provedor.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-136">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="0b8f0-137">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-137">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="0b8f0-138">-Incluir</span><span class="sxs-lookup"><span data-stu-id="0b8f0-138">-Include</span></span>

<span data-ttu-id="0b8f0-139">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-139">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="0b8f0-140">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="0b8f0-140">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="0b8f0-141">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="0b8f0-141">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="0b8f0-142">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-142">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0b8f0-143">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0b8f0-143">-LiteralPath</span></span>

<span data-ttu-id="0b8f0-144">Especifica um caminho para o item.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-144">Specifies a path to the item.</span></span>
<span data-ttu-id="0b8f0-145">Ao contrário do parâmetro **Path** , o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-145">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="0b8f0-146">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-146">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="0b8f0-147">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-147">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="0b8f0-148">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="0b8f0-149">-Path</span><span class="sxs-lookup"><span data-stu-id="0b8f0-149">-Path</span></span>

<span data-ttu-id="0b8f0-150">Especifica o caminho para o item selecionado.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-150">Specifies the path to the selected item.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0b8f0-151">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="0b8f0-151">-UseTransaction</span></span>

<span data-ttu-id="0b8f0-152">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-152">Includes the command in the active transaction.</span></span>
<span data-ttu-id="0b8f0-153">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-153">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="0b8f0-154">Para obter mais informações, consulte about_transactions.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-154">For more information, see about_transactions.</span></span>

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

### <span data-ttu-id="0b8f0-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0b8f0-155">-Confirm</span></span>
<span data-ttu-id="0b8f0-156">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-156">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0b8f0-157">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0b8f0-157">-WhatIf</span></span>

<span data-ttu-id="0b8f0-158">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-158">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0b8f0-159">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-159">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0b8f0-160">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0b8f0-160">CommonParameters</span></span>

<span data-ttu-id="0b8f0-161">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="0b8f0-161">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="0b8f0-162">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="0b8f0-162">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0b8f0-163">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0b8f0-163">INPUTS</span></span>

### <span data-ttu-id="0b8f0-164">System.String</span><span class="sxs-lookup"><span data-stu-id="0b8f0-164">System.String</span></span>

<span data-ttu-id="0b8f0-165">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-165">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="0b8f0-166">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0b8f0-166">OUTPUTS</span></span>

### <span data-ttu-id="0b8f0-167">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0b8f0-167">None</span></span>

<span data-ttu-id="0b8f0-168">Esse comando não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-168">The command does not generate any output.</span></span>
<span data-ttu-id="0b8f0-169">No entanto, a saída pode ser gerada pelo item que ela chama.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-169">However, output might be generated by the item that it invokes.</span></span>

## <span data-ttu-id="0b8f0-170">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0b8f0-170">NOTES</span></span>

<span data-ttu-id="0b8f0-171">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-171">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="0b8f0-172">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="0b8f0-172">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="0b8f0-173">Para obter mais informações, consulte about_Providers.</span><span class="sxs-lookup"><span data-stu-id="0b8f0-173">For more information, see about_Providers.</span></span>

## <span data-ttu-id="0b8f0-174">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0b8f0-174">RELATED LINKS</span></span>

[<span data-ttu-id="0b8f0-175">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="0b8f0-175">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="0b8f0-176">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="0b8f0-176">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="0b8f0-177">Get-Item</span><span class="sxs-lookup"><span data-stu-id="0b8f0-177">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="0b8f0-178">Move-Item</span><span class="sxs-lookup"><span data-stu-id="0b8f0-178">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="0b8f0-179">New-Item</span><span class="sxs-lookup"><span data-stu-id="0b8f0-179">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="0b8f0-180">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="0b8f0-180">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="0b8f0-181">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="0b8f0-181">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="0b8f0-182">Set-Item</span><span class="sxs-lookup"><span data-stu-id="0b8f0-182">Set-Item</span></span>](Set-Item.md)
