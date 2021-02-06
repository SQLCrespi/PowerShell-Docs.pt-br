---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Item
ms.openlocfilehash: fb3f95f51578f9dc02d9f68b3c0be5a6531aca17
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596572"
---
# <span data-ttu-id="e0174-102">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="e0174-102">Clear-Item</span></span>

## <span data-ttu-id="e0174-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e0174-103">SYNOPSIS</span></span>
<span data-ttu-id="e0174-104">Limpa o conteúdo de um item, mas não exclui o item.</span><span class="sxs-lookup"><span data-stu-id="e0174-104">Clears the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="e0174-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e0174-105">SYNTAX</span></span>

### <span data-ttu-id="e0174-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="e0174-106">Path (Default)</span></span>

```
Clear-Item [-Path] <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e0174-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e0174-107">LiteralPath</span></span>

```
Clear-Item -LiteralPath <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e0174-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e0174-108">DESCRIPTION</span></span>

<span data-ttu-id="e0174-109">O `Clear-Item` cmdlet limpa o conteúdo de um item, mas não exclui o item.</span><span class="sxs-lookup"><span data-stu-id="e0174-109">The `Clear-Item` cmdlet clears the content of an item, but it does not delete the item.</span></span>
<span data-ttu-id="e0174-110">Por exemplo, o `Clear-Item` cmdlet pode excluir o valor de uma variável, mas não exclui a variável.</span><span class="sxs-lookup"><span data-stu-id="e0174-110">For example, the `Clear-Item` cmdlet can delete the value of a variable, but it does not delete the variable.</span></span> <span data-ttu-id="e0174-111">O valor usado para representar um item limpo é definido por cada provedor do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0174-111">The value that used to represent a cleared item is defined by each PowerShell provider.</span></span>
<span data-ttu-id="e0174-112">Esse cmdlet é semelhante a `Clear-Content` , mas funciona em aliases e variáveis, em vez de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e0174-112">This cmdlet is similar to `Clear-Content`, but it works on aliases and variables, instead of files.</span></span>

## <span data-ttu-id="e0174-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e0174-113">EXAMPLES</span></span>

### <span data-ttu-id="e0174-114">Exemplo 1: limpar o valor de uma variável</span><span class="sxs-lookup"><span data-stu-id="e0174-114">Example 1: Clear the value of a variable</span></span>

<span data-ttu-id="e0174-115">Esse comando limpa o valor da variável chamada `TestVar1` .</span><span class="sxs-lookup"><span data-stu-id="e0174-115">This command clears the value of the variable named `TestVar1`.</span></span>
<span data-ttu-id="e0174-116">A variável permanece e é válida, mas seu valor é definido como `$null` .</span><span class="sxs-lookup"><span data-stu-id="e0174-116">The variable remains and is valid, but its value is set to `$null`.</span></span>
<span data-ttu-id="e0174-117">O nome da variável é prefixado com `Variable:` para indicar o provedor de variáveis do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0174-117">The variable name is prefixed with `Variable:` to indicate the PowerShell Variable provider.</span></span>

<span data-ttu-id="e0174-118">Os comandos alternativos mostram que, para obter o mesmo resultado, você pode alternar para a unidade do PowerShell `Variable:` e, em seguida, executar o `Clear-Item` comando.</span><span class="sxs-lookup"><span data-stu-id="e0174-118">The alternate commands show that, to get the same result, you can switch to the PowerShell `Variable:` drive and then run the `Clear-Item` command.</span></span>

```powershell
Clear-Item Variable:TestVar1
```

```
Set-Location Variable:
PS Variable:\> Clear-Item TestVar1
```

### <span data-ttu-id="e0174-119">Exemplo 2: limpar todas as entradas do registro</span><span class="sxs-lookup"><span data-stu-id="e0174-119">Example 2: Clear all registry entries</span></span>

<span data-ttu-id="e0174-120">Esse comando limpa todas as entradas de registro na subchave "MyKey", mas somente depois de solicitar que você confirme sua intenção.</span><span class="sxs-lookup"><span data-stu-id="e0174-120">This command clears all registry entries in the "MyKey" subkey, but only after prompting you to confirm your intent.</span></span>
<span data-ttu-id="e0174-121">Ele não exclui a subchave "MyKey" nem afeta quaisquer outras chaves ou entradas do registro.</span><span class="sxs-lookup"><span data-stu-id="e0174-121">It does not delete the "MyKey" subkey or affect any other registry keys or entries.</span></span>
<span data-ttu-id="e0174-122">Você pode usar os parâmetros **Include** e **Exclude** para identificar chaves do registro específicas, mas não pode usá-los para identificar entradas do registro.</span><span class="sxs-lookup"><span data-stu-id="e0174-122">You can use the **Include** and **Exclude** parameters to identify particular registry keys, but you cannot use them to identify registry entries.</span></span>

- <span data-ttu-id="e0174-123">Para excluir entradas de registro específicas, use o `Remove-ItemProperty` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e0174-123">To delete particular registry entries, use the `Remove-ItemProperty` cmdlet.</span></span>
- <span data-ttu-id="e0174-124">Para excluir o valor de uma entrada de registro, use o `Clear-ItemProperty cmdlet` .</span><span class="sxs-lookup"><span data-stu-id="e0174-124">To delete the value of a registry entry, use the `Clear-ItemProperty cmdlet`.</span></span>

```powershell
Clear-Item HKLM:\Software\MyCompany\MyKey -Confirm
```

## <span data-ttu-id="e0174-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e0174-125">PARAMETERS</span></span>

### <span data-ttu-id="e0174-126">-Credential</span><span class="sxs-lookup"><span data-stu-id="e0174-126">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="e0174-127">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0174-127">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="e0174-128">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="e0174-128">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="e0174-129">-Excluir</span><span class="sxs-lookup"><span data-stu-id="e0174-129">-Exclude</span></span>

<span data-ttu-id="e0174-130">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="e0174-130">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="e0174-131">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="e0174-131">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="e0174-132">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="e0174-132">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="e0174-133">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="e0174-133">Wildcard characters are permitted.</span></span> <span data-ttu-id="e0174-134">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="e0174-134">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="e0174-135">-Filter</span><span class="sxs-lookup"><span data-stu-id="e0174-135">-Filter</span></span>

<span data-ttu-id="e0174-136">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="e0174-136">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="e0174-137">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="e0174-137">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="e0174-138">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="e0174-138">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="e0174-139">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="e0174-139">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="e0174-140">-Force</span><span class="sxs-lookup"><span data-stu-id="e0174-140">-Force</span></span>

<span data-ttu-id="e0174-141">Indica que o cmdlet limpa os itens que não podem ser alterados de outra forma, como aliases somente leitura.</span><span class="sxs-lookup"><span data-stu-id="e0174-141">Indicates that the cmdlet clears items that cannot otherwise be changed, such as read- only aliases.</span></span>
<span data-ttu-id="e0174-142">O cmdlet não apaga constantes.</span><span class="sxs-lookup"><span data-stu-id="e0174-142">The cmdlet cannot clear constants.</span></span>
<span data-ttu-id="e0174-143">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="e0174-143">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="e0174-144">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="e0174-144">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="e0174-145">O cmdlet não pode substituir restrições de segurança, mesmo quando o parâmetro **Force** é usado.</span><span class="sxs-lookup"><span data-stu-id="e0174-145">The cmdlet cannot override security restrictions, even when the **Force** parameter is used.</span></span>

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

### <span data-ttu-id="e0174-146">-Incluir</span><span class="sxs-lookup"><span data-stu-id="e0174-146">-Include</span></span>

<span data-ttu-id="e0174-147">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="e0174-147">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="e0174-148">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="e0174-148">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="e0174-149">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="e0174-149">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="e0174-150">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="e0174-150">Wildcard characters are permitted.</span></span> <span data-ttu-id="e0174-151">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="e0174-151">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="e0174-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e0174-152">-LiteralPath</span></span>

<span data-ttu-id="e0174-153">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="e0174-153">Specifies a path to one or more locations.</span></span> <span data-ttu-id="e0174-154">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="e0174-154">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="e0174-155">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="e0174-155">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="e0174-156">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="e0174-156">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="e0174-157">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="e0174-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="e0174-158">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="e0174-158">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="e0174-159">-Path</span><span class="sxs-lookup"><span data-stu-id="e0174-159">-Path</span></span>

<span data-ttu-id="e0174-160">Especifica o caminho para os itens sendo apagados.</span><span class="sxs-lookup"><span data-stu-id="e0174-160">Specifies the path to the items being cleared.</span></span>
<span data-ttu-id="e0174-161">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="e0174-161">Wildcard characters are permitted.</span></span>
<span data-ttu-id="e0174-162">Esse parâmetro é necessário, mas o **caminho** do nome do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="e0174-162">This parameter is required, but the parameter name **Path** is optional.</span></span>

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

### <span data-ttu-id="e0174-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e0174-163">-Confirm</span></span>

<span data-ttu-id="e0174-164">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e0174-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e0174-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e0174-165">-WhatIf</span></span>

<span data-ttu-id="e0174-166">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="e0174-166">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e0174-167">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="e0174-167">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e0174-168">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e0174-168">CommonParameters</span></span>

<span data-ttu-id="e0174-169">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="e0174-169">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="e0174-170">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="e0174-170">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e0174-171">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e0174-171">INPUTS</span></span>

### <span data-ttu-id="e0174-172">System.String</span><span class="sxs-lookup"><span data-stu-id="e0174-172">System.String</span></span>

<span data-ttu-id="e0174-173">É possível canalizar uma cadeia de caracteres de caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e0174-173">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="e0174-174">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e0174-174">OUTPUTS</span></span>

### <span data-ttu-id="e0174-175">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e0174-175">None</span></span>

<span data-ttu-id="e0174-176">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="e0174-176">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e0174-177">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e0174-177">NOTES</span></span>

- <span data-ttu-id="e0174-178">`Clear-Item`Há suporte para o cmdlet apenas por vários provedores do PowerShell, incluindo o **alias**, o **ambiente**, a **função**, o **registro** e os provedores de **variáveis** .</span><span class="sxs-lookup"><span data-stu-id="e0174-178">The `Clear-Item` cmdlet is supported only by several PowerShell providers, including the **Alias**, **Environment**, **Function**, **Registry**, and **Variable** providers.</span></span> <span data-ttu-id="e0174-179">Como tal, você pode usar `Clear-Item` para excluir o conteúdo de itens nos namespaces do provedor.</span><span class="sxs-lookup"><span data-stu-id="e0174-179">As such, you can use `Clear-Item` to delete the content of items in the provider namespaces.</span></span> <span data-ttu-id="e0174-180">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="e0174-180">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="e0174-181">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="e0174-181">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
- <span data-ttu-id="e0174-182">Não é possível usar `Clear-Item` o para excluir o conteúdo de um arquivo, pois o provedor do sistema de arquivos do PowerShell não oferece suporte a esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e0174-182">You cannot use `Clear-Item` to delete the contents of a file, because the PowerShell FileSystem provider does not support this cmdlet.</span></span> <span data-ttu-id="e0174-183">Para limpar arquivos, use o `Clear-Content` .</span><span class="sxs-lookup"><span data-stu-id="e0174-183">To clear files, use the `Clear-Content`.</span></span>

## <span data-ttu-id="e0174-184">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e0174-184">RELATED LINKS</span></span>

[<span data-ttu-id="e0174-185">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="e0174-185">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="e0174-186">Get-Item</span><span class="sxs-lookup"><span data-stu-id="e0174-186">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="e0174-187">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="e0174-187">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="e0174-188">Move-Item</span><span class="sxs-lookup"><span data-stu-id="e0174-188">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="e0174-189">New-Item</span><span class="sxs-lookup"><span data-stu-id="e0174-189">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="e0174-190">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="e0174-190">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="e0174-191">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="e0174-191">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="e0174-192">Set-Item</span><span class="sxs-lookup"><span data-stu-id="e0174-192">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="e0174-193">about_Providers</span><span class="sxs-lookup"><span data-stu-id="e0174-193">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

