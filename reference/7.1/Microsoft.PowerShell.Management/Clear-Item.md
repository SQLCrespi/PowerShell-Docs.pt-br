---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Item
ms.openlocfilehash: b03e6a68da933dc0da6bfce92201825f70b77b19
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194736"
---
# <span data-ttu-id="19243-103">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="19243-103">Clear-Item</span></span>

## <span data-ttu-id="19243-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="19243-104">SYNOPSIS</span></span>
<span data-ttu-id="19243-105">Limpa o conteúdo de um item, mas não exclui o item.</span><span class="sxs-lookup"><span data-stu-id="19243-105">Clears the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="19243-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="19243-106">SYNTAX</span></span>

### <span data-ttu-id="19243-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="19243-107">Path (Default)</span></span>

```
Clear-Item [-Path] <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="19243-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="19243-108">LiteralPath</span></span>

```
Clear-Item -LiteralPath <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="19243-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="19243-109">DESCRIPTION</span></span>

<span data-ttu-id="19243-110">O `Clear-Item` cmdlet limpa o conteúdo de um item, mas não exclui o item.</span><span class="sxs-lookup"><span data-stu-id="19243-110">The `Clear-Item` cmdlet clears the content of an item, but it does not delete the item.</span></span>
<span data-ttu-id="19243-111">Por exemplo, o `Clear-Item` cmdlet pode excluir o valor de uma variável, mas não exclui a variável.</span><span class="sxs-lookup"><span data-stu-id="19243-111">For example, the `Clear-Item` cmdlet can delete the value of a variable, but it does not delete the variable.</span></span> <span data-ttu-id="19243-112">O valor usado para representar um item limpo é definido por cada provedor do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19243-112">The value that used to represent a cleared item is defined by each PowerShell provider.</span></span>
<span data-ttu-id="19243-113">Esse cmdlet é semelhante a `Clear-Content` , mas funciona em aliases e variáveis, em vez de arquivos.</span><span class="sxs-lookup"><span data-stu-id="19243-113">This cmdlet is similar to `Clear-Content`, but it works on aliases and variables, instead of files.</span></span>

## <span data-ttu-id="19243-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="19243-114">EXAMPLES</span></span>

### <span data-ttu-id="19243-115">Exemplo 1: limpar o valor de uma variável</span><span class="sxs-lookup"><span data-stu-id="19243-115">Example 1: Clear the value of a variable</span></span>

<span data-ttu-id="19243-116">Esse comando limpa o valor da variável chamada `TestVar1` .</span><span class="sxs-lookup"><span data-stu-id="19243-116">This command clears the value of the variable named `TestVar1`.</span></span>
<span data-ttu-id="19243-117">A variável permanece e é válida, mas seu valor é definido como `$null` .</span><span class="sxs-lookup"><span data-stu-id="19243-117">The variable remains and is valid, but its value is set to `$null`.</span></span>
<span data-ttu-id="19243-118">O nome da variável é prefixado com `Variable:` para indicar o provedor de variáveis do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19243-118">The variable name is prefixed with `Variable:` to indicate the PowerShell Variable provider.</span></span>

<span data-ttu-id="19243-119">Os comandos alternativos mostram que, para obter o mesmo resultado, você pode alternar para a unidade do PowerShell `Variable:` e, em seguida, executar o `Clear-Item` comando.</span><span class="sxs-lookup"><span data-stu-id="19243-119">The alternate commands show that, to get the same result, you can switch to the PowerShell `Variable:` drive and then run the `Clear-Item` command.</span></span>

```powershell
Clear-Item Variable:TestVar1
```

```
Set-Location Variable:
PS Variable:\> Clear-Item TestVar1
```

### <span data-ttu-id="19243-120">Exemplo 2: limpar todas as entradas do registro</span><span class="sxs-lookup"><span data-stu-id="19243-120">Example 2: Clear all registry entries</span></span>

<span data-ttu-id="19243-121">Esse comando limpa todas as entradas de registro na subchave "MyKey", mas somente depois de solicitar que você confirme sua intenção.</span><span class="sxs-lookup"><span data-stu-id="19243-121">This command clears all registry entries in the "MyKey" subkey, but only after prompting you to confirm your intent.</span></span>
<span data-ttu-id="19243-122">Ele não exclui a subchave "MyKey" nem afeta quaisquer outras chaves ou entradas do registro.</span><span class="sxs-lookup"><span data-stu-id="19243-122">It does not delete the "MyKey" subkey or affect any other registry keys or entries.</span></span>
<span data-ttu-id="19243-123">Você pode usar os parâmetros **Include** e **Exclude** para identificar chaves do registro específicas, mas não pode usá-los para identificar entradas do registro.</span><span class="sxs-lookup"><span data-stu-id="19243-123">You can use the **Include** and **Exclude** parameters to identify particular registry keys, but you cannot use them to identify registry entries.</span></span>

- <span data-ttu-id="19243-124">Para excluir entradas de registro específicas, use o `Remove-ItemProperty` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="19243-124">To delete particular registry entries, use the `Remove-ItemProperty` cmdlet.</span></span>
- <span data-ttu-id="19243-125">Para excluir o valor de uma entrada de registro, use o `Clear-ItemProperty cmdlet` .</span><span class="sxs-lookup"><span data-stu-id="19243-125">To delete the value of a registry entry, use the `Clear-ItemProperty cmdlet`.</span></span>

```powershell
Clear-Item HKLM:\Software\MyCompany\MyKey -Confirm
```

## <span data-ttu-id="19243-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="19243-126">PARAMETERS</span></span>

### <span data-ttu-id="19243-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="19243-127">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="19243-128">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19243-128">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="19243-129">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="19243-129">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="19243-130">-Excluir</span><span class="sxs-lookup"><span data-stu-id="19243-130">-Exclude</span></span>

<span data-ttu-id="19243-131">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="19243-131">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="19243-132">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="19243-132">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="19243-133">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="19243-133">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="19243-134">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="19243-134">Wildcard characters are permitted.</span></span> <span data-ttu-id="19243-135">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="19243-135">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="19243-136">-Filter</span><span class="sxs-lookup"><span data-stu-id="19243-136">-Filter</span></span>

<span data-ttu-id="19243-137">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="19243-137">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="19243-138">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="19243-138">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="19243-139">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="19243-139">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="19243-140">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="19243-140">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="19243-141">-Force</span><span class="sxs-lookup"><span data-stu-id="19243-141">-Force</span></span>

<span data-ttu-id="19243-142">Indica que o cmdlet limpa os itens que não podem ser alterados de outra forma, como aliases somente leitura.</span><span class="sxs-lookup"><span data-stu-id="19243-142">Indicates that the cmdlet clears items that cannot otherwise be changed, such as read- only aliases.</span></span>
<span data-ttu-id="19243-143">O cmdlet não apaga constantes.</span><span class="sxs-lookup"><span data-stu-id="19243-143">The cmdlet cannot clear constants.</span></span>
<span data-ttu-id="19243-144">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="19243-144">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="19243-145">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="19243-145">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="19243-146">O cmdlet não pode substituir restrições de segurança, mesmo quando o parâmetro **Force** é usado.</span><span class="sxs-lookup"><span data-stu-id="19243-146">The cmdlet cannot override security restrictions, even when the **Force** parameter is used.</span></span>

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

### <span data-ttu-id="19243-147">-Incluir</span><span class="sxs-lookup"><span data-stu-id="19243-147">-Include</span></span>

<span data-ttu-id="19243-148">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="19243-148">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="19243-149">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="19243-149">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="19243-150">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="19243-150">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="19243-151">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="19243-151">Wildcard characters are permitted.</span></span> <span data-ttu-id="19243-152">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="19243-152">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="19243-153">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="19243-153">-LiteralPath</span></span>

<span data-ttu-id="19243-154">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="19243-154">Specifies a path to one or more locations.</span></span> <span data-ttu-id="19243-155">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="19243-155">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="19243-156">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="19243-156">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="19243-157">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="19243-157">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="19243-158">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="19243-158">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="19243-159">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="19243-159">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="19243-160">-Path</span><span class="sxs-lookup"><span data-stu-id="19243-160">-Path</span></span>

<span data-ttu-id="19243-161">Especifica o caminho para os itens sendo apagados.</span><span class="sxs-lookup"><span data-stu-id="19243-161">Specifies the path to the items being cleared.</span></span>
<span data-ttu-id="19243-162">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="19243-162">Wildcard characters are permitted.</span></span>
<span data-ttu-id="19243-163">Esse parâmetro é necessário, mas o **caminho** do nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="19243-163">This parameter is required, but the parameter name **Path** is optional.</span></span>

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

### <span data-ttu-id="19243-164">-Confirm</span><span class="sxs-lookup"><span data-stu-id="19243-164">-Confirm</span></span>

<span data-ttu-id="19243-165">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="19243-165">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="19243-166">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="19243-166">-WhatIf</span></span>

<span data-ttu-id="19243-167">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="19243-167">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="19243-168">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="19243-168">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="19243-169">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="19243-169">CommonParameters</span></span>

<span data-ttu-id="19243-170">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="19243-170">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="19243-171">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="19243-171">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="19243-172">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="19243-172">INPUTS</span></span>

### <span data-ttu-id="19243-173">System.String</span><span class="sxs-lookup"><span data-stu-id="19243-173">System.String</span></span>

<span data-ttu-id="19243-174">É possível canalizar uma cadeia de caracteres de caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="19243-174">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="19243-175">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="19243-175">OUTPUTS</span></span>

### <span data-ttu-id="19243-176">Nenhum</span><span class="sxs-lookup"><span data-stu-id="19243-176">None</span></span>

<span data-ttu-id="19243-177">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="19243-177">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="19243-178">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="19243-178">NOTES</span></span>

- <span data-ttu-id="19243-179">`Clear-Item`Há suporte para o cmdlet apenas por vários provedores do PowerShell, incluindo o **alias** , o **ambiente** , a **função** , o **registro** e os provedores de **variáveis** .</span><span class="sxs-lookup"><span data-stu-id="19243-179">The `Clear-Item` cmdlet is supported only by several PowerShell providers, including the **Alias** , **Environment** , **Function** , **Registry** , and **Variable** providers.</span></span> <span data-ttu-id="19243-180">Como tal, você pode usar `Clear-Item` para excluir o conteúdo de itens nos namespaces do provedor.</span><span class="sxs-lookup"><span data-stu-id="19243-180">As such, you can use `Clear-Item` to delete the content of items in the provider namespaces.</span></span> <span data-ttu-id="19243-181">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="19243-181">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="19243-182">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="19243-182">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
- <span data-ttu-id="19243-183">Não é possível usar `Clear-Item` o para excluir o conteúdo de um arquivo, pois o provedor do sistema de arquivos do PowerShell não oferece suporte a esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="19243-183">You cannot use `Clear-Item` to delete the contents of a file, because the PowerShell FileSystem provider does not support this cmdlet.</span></span> <span data-ttu-id="19243-184">Para limpar arquivos, use o `Clear-Content` .</span><span class="sxs-lookup"><span data-stu-id="19243-184">To clear files, use the `Clear-Content`.</span></span>

## <span data-ttu-id="19243-185">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="19243-185">RELATED LINKS</span></span>

[<span data-ttu-id="19243-186">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="19243-186">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="19243-187">Get-Item</span><span class="sxs-lookup"><span data-stu-id="19243-187">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="19243-188">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="19243-188">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="19243-189">Move-Item</span><span class="sxs-lookup"><span data-stu-id="19243-189">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="19243-190">New-Item</span><span class="sxs-lookup"><span data-stu-id="19243-190">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="19243-191">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="19243-191">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="19243-192">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="19243-192">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="19243-193">Set-Item</span><span class="sxs-lookup"><span data-stu-id="19243-193">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="19243-194">about_Providers</span><span class="sxs-lookup"><span data-stu-id="19243-194">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

