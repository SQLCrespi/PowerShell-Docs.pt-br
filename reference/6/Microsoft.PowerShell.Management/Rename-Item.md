---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-item?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Item
ms.openlocfilehash: 66a7b82b56028a4801a3aa8c93cd46460a5353ce
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194064"
---
# <span data-ttu-id="bc269-103">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="bc269-103">Rename-Item</span></span>

## <span data-ttu-id="bc269-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="bc269-104">SYNOPSIS</span></span>
<span data-ttu-id="bc269-105">Renomeia um item em um namespace do provedor do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc269-105">Renames an item in a PowerShell provider namespace.</span></span>

## <span data-ttu-id="bc269-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bc269-106">SYNTAX</span></span>

### <span data-ttu-id="bc269-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="bc269-107">ByPath (Default)</span></span>

```
Rename-Item [-Path] <String> [-NewName] <String> [-Force] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="bc269-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="bc269-108">ByLiteralPath</span></span>

```
Rename-Item -LiteralPath <String> [-NewName] <String> [-Force] [-PassThru]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="bc269-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bc269-109">DESCRIPTION</span></span>

<span data-ttu-id="bc269-110">O `Rename-Item` cmdlet altera o nome de um item especificado.</span><span class="sxs-lookup"><span data-stu-id="bc269-110">The `Rename-Item` cmdlet changes the name of a specified item.</span></span> <span data-ttu-id="bc269-111">Este cmdlet não afeta o conteúdo do item que é renomeado.</span><span class="sxs-lookup"><span data-stu-id="bc269-111">This cmdlet does not affect the content of the item being renamed.</span></span>

<span data-ttu-id="bc269-112">Você não pode usar `Rename-Item` o para mover um item, como especificando um caminho junto com o novo nome.</span><span class="sxs-lookup"><span data-stu-id="bc269-112">You can't use `Rename-Item` to move an item, such as by specifying a path together with the new name.</span></span> <span data-ttu-id="bc269-113">Para mover e renomear um item, use o `Move-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bc269-113">To move and rename an item, use the `Move-Item` cmdlet.</span></span>

## <span data-ttu-id="bc269-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="bc269-114">EXAMPLES</span></span>

### <span data-ttu-id="bc269-115">Exemplo 1: renomear um arquivo</span><span class="sxs-lookup"><span data-stu-id="bc269-115">Example 1: Rename a file</span></span>

<span data-ttu-id="bc269-116">Esse comando renomeia o arquivo `daily_file.txt` para `monday_file.txt` .</span><span class="sxs-lookup"><span data-stu-id="bc269-116">This command renames the file `daily_file.txt` to `monday_file.txt`.</span></span>

```powershell
Rename-Item -Path "c:\logfiles\daily_file.txt" -NewName "monday_file.txt"
```

### <span data-ttu-id="bc269-117">Exemplo 2: renomear e mover um item</span><span class="sxs-lookup"><span data-stu-id="bc269-117">Example 2: Rename and move an item</span></span>

<span data-ttu-id="bc269-118">Não é possível usar `Rename-Item` o para renomear e mover um item.</span><span class="sxs-lookup"><span data-stu-id="bc269-118">You can't use `Rename-Item` to both rename and move an item.</span></span> <span data-ttu-id="bc269-119">Especificamente, você não pode fornecer um caminho para o valor do parâmetro **NewName** , a menos que o caminho seja idêntico ao caminho especificado no parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="bc269-119">Specifically, you can't supply a path for the value of the **NewName** parameter, unless the path is identical to the path specified in the **Path** parameter.</span></span> <span data-ttu-id="bc269-120">Caso contrário, é permitido somente um novo nome.</span><span class="sxs-lookup"><span data-stu-id="bc269-120">Otherwise, only a new name is permitted.</span></span>

<span data-ttu-id="bc269-121">Este exemplo tenta renomear o `project.txt` arquivo no diretório atual como `old-project.txt` no `D:\Archive` diretório.</span><span class="sxs-lookup"><span data-stu-id="bc269-121">This example attempts to rename the `project.txt` file in the current directory to `old-project.txt` in the `D:\Archive` directory.</span></span> <span data-ttu-id="bc269-122">O resultado é o erro mostrado na saída.</span><span class="sxs-lookup"><span data-stu-id="bc269-122">The result is the error shown in the output.</span></span>

```powershell
Rename-Item -Path "project.txt" -NewName "d:\archive\old-project.txt"
```

```Output
Rename-Item : can't rename because the target specified represents a path or device name.
At line:1 char:12
+ Rename-Item <<<<  -path project.txt -NewName d:\archive\old-project.txt
+ CategoryInfo          : InvalidArgument: (:) [Rename-Item], PS>  Move-Item -Path "project.txt" -De
stination "d:\archive\old-project.txt"
```

### <span data-ttu-id="bc269-123">Exemplo 3: renomear uma chave do registro</span><span class="sxs-lookup"><span data-stu-id="bc269-123">Example 3: Rename a registry key</span></span>

<span data-ttu-id="bc269-124">Este exemplo renomeia uma chave do registro de **propaganda** para **marketing** .</span><span class="sxs-lookup"><span data-stu-id="bc269-124">This example renames a registry key from **Advertising** to **Marketing** .</span></span> <span data-ttu-id="bc269-125">Quando o comando é concluído, a chave é renomeada, mas as entradas de registro na chave permanecem inalteradas.</span><span class="sxs-lookup"><span data-stu-id="bc269-125">When the command is complete, the key is renamed, but the registry entries in the key are unchanged.</span></span>

```powershell
Rename-Item -Path "HKLM:\Software\MyCompany\Advertising" -NewName "Marketing"
```

### <span data-ttu-id="bc269-126">Exemplo 4: renomear vários arquivos</span><span class="sxs-lookup"><span data-stu-id="bc269-126">Example 4: Rename multiple files</span></span>

<span data-ttu-id="bc269-127">Este exemplo renomeia todos os `*.txt` arquivos no diretório atual para `*.log` .</span><span class="sxs-lookup"><span data-stu-id="bc269-127">This example renames all the `*.txt` files in the current directory to `*.log`.</span></span>

```powershell
Get-ChildItem *.txt
```

```Output
    Directory: C:\temp\files

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        10/3/2019   7:47 AM           2918 Friday.TXT
-a----        10/3/2019   7:46 AM           2918 Monday.Txt
-a----        10/3/2019   7:47 AM           2918 Wednesday.txt
```

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.Name -replace '.txt','.log' }
Get-ChildItem *.log
```

```Output
    Directory: C:\temp\files

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        10/3/2019   7:47 AM           2918 Friday.log
-a----        10/3/2019   7:46 AM           2918 Monday.log
-a----        10/3/2019   7:47 AM           2918 Wednesday.log
```

<span data-ttu-id="bc269-128">O `Get-ChildItem` cmdlet obtém todos os arquivos na pasta atual que têm uma `.txt` extensão de arquivo, em seguida, os canaliza para `Rename-Item` .</span><span class="sxs-lookup"><span data-stu-id="bc269-128">The `Get-ChildItem` cmdlet gets all the files in the current folder that have a `.txt` file extension then pipes them to `Rename-Item`.</span></span> <span data-ttu-id="bc269-129">O valor de **NewName** é um bloco de script que é executado antes que o valor seja enviado ao parâmetro **NewName** .</span><span class="sxs-lookup"><span data-stu-id="bc269-129">The value of **NewName** is a script block that runs before the value is submitted to the **NewName** parameter.</span></span>

<span data-ttu-id="bc269-130">No bloco de script, a `$_` variável automática representa cada objeto de arquivo como ele se refere ao comando por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="bc269-130">In the script block, the `$_` automatic variable represents each file object as it comes to the command through the pipeline.</span></span> <span data-ttu-id="bc269-131">O bloco de script usa o `-replace` operador para substituir a extensão de arquivo de cada arquivo por `.log` .</span><span class="sxs-lookup"><span data-stu-id="bc269-131">The script block uses the `-replace` operator to replace the file extension of each file with `.log`.</span></span> <span data-ttu-id="bc269-132">Observe que a correspondência usando o `-replace` operador não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="bc269-132">Notice that matching using the `-replace` operator is not case sensitive.</span></span>

## <span data-ttu-id="bc269-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bc269-133">PARAMETERS</span></span>

### <span data-ttu-id="bc269-134">-Credential</span><span class="sxs-lookup"><span data-stu-id="bc269-134">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="bc269-135">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc269-135">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="bc269-136">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="bc269-136">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="bc269-137">-Force</span><span class="sxs-lookup"><span data-stu-id="bc269-137">-Force</span></span>

<span data-ttu-id="bc269-138">Força o cmdlet a renomear itens que não podem ser alterados de outra forma, como arquivos ocultos ou somente leitura ou aliases ou variáveis somente leitura.</span><span class="sxs-lookup"><span data-stu-id="bc269-138">Forces the cmdlet to rename items that can't otherwise be changed, such as hidden or read-only files or read-only aliases or variables.</span></span> <span data-ttu-id="bc269-139">O cmdlet não pode alterar aliases ou variáveis constantes.</span><span class="sxs-lookup"><span data-stu-id="bc269-139">The cmdlet can't change constant aliases or variables.</span></span>
<span data-ttu-id="bc269-140">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="bc269-140">Implementation varies from provider to provider.</span></span> <span data-ttu-id="bc269-141">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="bc269-141">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="bc269-142">Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="bc269-142">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="bc269-143">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="bc269-143">-LiteralPath</span></span>

<span data-ttu-id="bc269-144">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="bc269-144">Specifies a path to one or more locations.</span></span> <span data-ttu-id="bc269-145">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="bc269-145">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="bc269-146">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="bc269-146">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="bc269-147">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="bc269-147">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="bc269-148">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="bc269-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="bc269-149">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="bc269-149">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="bc269-150">-NewName</span><span class="sxs-lookup"><span data-stu-id="bc269-150">-NewName</span></span>

<span data-ttu-id="bc269-151">Especifica o novo nome do item.</span><span class="sxs-lookup"><span data-stu-id="bc269-151">Specifies the new name of the item.</span></span> <span data-ttu-id="bc269-152">Digite apenas um nome, não um caminho e nome.</span><span class="sxs-lookup"><span data-stu-id="bc269-152">Enter only a name, not a path and name.</span></span> <span data-ttu-id="bc269-153">Se você inserir um caminho diferente do caminho especificado no parâmetro **path** , o `Rename-Item` gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="bc269-153">If you enter a path that differs from the path that is specified in the **Path** parameter, `Rename-Item` generates an error.</span></span>
<span data-ttu-id="bc269-154">Para renomear e mover um item, use `Move-Item` .</span><span class="sxs-lookup"><span data-stu-id="bc269-154">To rename and move an item, use `Move-Item`.</span></span>

<span data-ttu-id="bc269-155">Você não pode usar caracteres curinga no valor do parâmetro **NewName** .</span><span class="sxs-lookup"><span data-stu-id="bc269-155">You can't use wildcard characters in the value of the **NewName** parameter.</span></span> <span data-ttu-id="bc269-156">Para especificar um nome para vários arquivos, use o operador **replace** em uma expressão regular.</span><span class="sxs-lookup"><span data-stu-id="bc269-156">To specify a name for multiple files, use the **Replace** operator in a regular expression.</span></span> <span data-ttu-id="bc269-157">Para obter mais informações sobre o operador Replace, consulte [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="bc269-157">For more information about the Replace operator, see [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="bc269-158">-PassThru</span><span class="sxs-lookup"><span data-stu-id="bc269-158">-PassThru</span></span>

<span data-ttu-id="bc269-159">Retorna um objeto que representa o item para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="bc269-159">Returns an object that represents the item to the pipeline.</span></span> <span data-ttu-id="bc269-160">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="bc269-160">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="bc269-161">-Path</span><span class="sxs-lookup"><span data-stu-id="bc269-161">-Path</span></span>

<span data-ttu-id="bc269-162">Especifica o caminho do item a ser renomeado.</span><span class="sxs-lookup"><span data-stu-id="bc269-162">Specifies the path of the item to rename.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bc269-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bc269-163">-Confirm</span></span>

<span data-ttu-id="bc269-164">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bc269-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bc269-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bc269-165">-WhatIf</span></span>

<span data-ttu-id="bc269-166">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="bc269-166">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="bc269-167">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="bc269-167">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bc269-168">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bc269-168">CommonParameters</span></span>

<span data-ttu-id="bc269-169">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bc269-169">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bc269-170">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="bc269-170">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="bc269-171">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="bc269-171">INPUTS</span></span>

### <span data-ttu-id="bc269-172">System.String</span><span class="sxs-lookup"><span data-stu-id="bc269-172">System.String</span></span>

<span data-ttu-id="bc269-173">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bc269-173">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="bc269-174">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="bc269-174">OUTPUTS</span></span>

### <span data-ttu-id="bc269-175">Nenhum ou um objeto que representa o item renomeado.</span><span class="sxs-lookup"><span data-stu-id="bc269-175">None or an object that represents the renamed item.</span></span>

<span data-ttu-id="bc269-176">Esse cmdlet gera um objeto que representa o item renomeado, se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="bc269-176">This cmdlet generates an object that represents the renamed item, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="bc269-177">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="bc269-177">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="bc269-178">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="bc269-178">NOTES</span></span>

<span data-ttu-id="bc269-179">`Rename-Item` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="bc269-179">`Rename-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="bc269-180">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="bc269-180">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="bc269-181">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="bc269-181">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="bc269-182">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="bc269-182">RELATED LINKS</span></span>

[<span data-ttu-id="bc269-183">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="bc269-183">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="bc269-184">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="bc269-184">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="bc269-185">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="bc269-185">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="bc269-186">Get-Item</span><span class="sxs-lookup"><span data-stu-id="bc269-186">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="bc269-187">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="bc269-187">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="bc269-188">Move-Item</span><span class="sxs-lookup"><span data-stu-id="bc269-188">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="bc269-189">New-Item</span><span class="sxs-lookup"><span data-stu-id="bc269-189">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="bc269-190">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="bc269-190">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="bc269-191">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bc269-191">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="bc269-192">Set-Item</span><span class="sxs-lookup"><span data-stu-id="bc269-192">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="bc269-193">about_Providers</span><span class="sxs-lookup"><span data-stu-id="bc269-193">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
