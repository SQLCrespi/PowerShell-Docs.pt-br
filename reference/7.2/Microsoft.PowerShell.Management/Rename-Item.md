---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Item
ms.openlocfilehash: dec5c2c905486110e4885f29d236ab41d945fb96
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596385"
---
# <span data-ttu-id="9afe6-102">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="9afe6-102">Rename-Item</span></span>

## <span data-ttu-id="9afe6-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9afe6-103">SYNOPSIS</span></span>
<span data-ttu-id="9afe6-104">Renomeia um item em um namespace do provedor do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9afe6-104">Renames an item in a PowerShell provider namespace.</span></span>

## <span data-ttu-id="9afe6-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9afe6-105">SYNTAX</span></span>

### <span data-ttu-id="9afe6-106">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="9afe6-106">ByPath (Default)</span></span>

```
Rename-Item [-Path] <String> [-NewName] <String> [-Force] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### <span data-ttu-id="9afe6-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="9afe6-107">ByLiteralPath</span></span>

```
Rename-Item -LiteralPath <String> [-NewName] <String> [-Force] [-PassThru]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="9afe6-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9afe6-108">DESCRIPTION</span></span>

<span data-ttu-id="9afe6-109">O `Rename-Item` cmdlet altera o nome de um item especificado.</span><span class="sxs-lookup"><span data-stu-id="9afe6-109">The `Rename-Item` cmdlet changes the name of a specified item.</span></span> <span data-ttu-id="9afe6-110">Este cmdlet não afeta o conteúdo do item que é renomeado.</span><span class="sxs-lookup"><span data-stu-id="9afe6-110">This cmdlet does not affect the content of the item being renamed.</span></span>

<span data-ttu-id="9afe6-111">Você não pode usar `Rename-Item` o para mover um item, como especificando um caminho junto com o novo nome.</span><span class="sxs-lookup"><span data-stu-id="9afe6-111">You can't use `Rename-Item` to move an item, such as by specifying a path together with the new name.</span></span> <span data-ttu-id="9afe6-112">Para mover e renomear um item, use o `Move-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9afe6-112">To move and rename an item, use the `Move-Item` cmdlet.</span></span>

## <span data-ttu-id="9afe6-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9afe6-113">EXAMPLES</span></span>

### <span data-ttu-id="9afe6-114">Exemplo 1: renomear um arquivo</span><span class="sxs-lookup"><span data-stu-id="9afe6-114">Example 1: Rename a file</span></span>

<span data-ttu-id="9afe6-115">Esse comando renomeia o arquivo `daily_file.txt` para `monday_file.txt` .</span><span class="sxs-lookup"><span data-stu-id="9afe6-115">This command renames the file `daily_file.txt` to `monday_file.txt`.</span></span>

```powershell
Rename-Item -Path "c:\logfiles\daily_file.txt" -NewName "monday_file.txt"
```

### <span data-ttu-id="9afe6-116">Exemplo 2: renomear e mover um item</span><span class="sxs-lookup"><span data-stu-id="9afe6-116">Example 2: Rename and move an item</span></span>

<span data-ttu-id="9afe6-117">Não é possível usar `Rename-Item` o para renomear e mover um item.</span><span class="sxs-lookup"><span data-stu-id="9afe6-117">You can't use `Rename-Item` to both rename and move an item.</span></span> <span data-ttu-id="9afe6-118">Especificamente, você não pode fornecer um caminho para o valor do parâmetro **NewName** , a menos que o caminho seja idêntico ao caminho especificado no parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="9afe6-118">Specifically, you can't supply a path for the value of the **NewName** parameter, unless the path is identical to the path specified in the **Path** parameter.</span></span> <span data-ttu-id="9afe6-119">Caso contrário, é permitido somente um novo nome.</span><span class="sxs-lookup"><span data-stu-id="9afe6-119">Otherwise, only a new name is permitted.</span></span>

<span data-ttu-id="9afe6-120">Este exemplo tenta renomear o `project.txt` arquivo no diretório atual como `old-project.txt` no `D:\Archive` diretório.</span><span class="sxs-lookup"><span data-stu-id="9afe6-120">This example attempts to rename the `project.txt` file in the current directory to `old-project.txt` in the `D:\Archive` directory.</span></span> <span data-ttu-id="9afe6-121">O resultado é o erro mostrado na saída.</span><span class="sxs-lookup"><span data-stu-id="9afe6-121">The result is the error shown in the output.</span></span>

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

### <span data-ttu-id="9afe6-122">Exemplo 3: renomear uma chave do registro</span><span class="sxs-lookup"><span data-stu-id="9afe6-122">Example 3: Rename a registry key</span></span>

<span data-ttu-id="9afe6-123">Este exemplo renomeia uma chave do registro de **propaganda** para **marketing**.</span><span class="sxs-lookup"><span data-stu-id="9afe6-123">This example renames a registry key from **Advertising** to **Marketing**.</span></span> <span data-ttu-id="9afe6-124">Quando o comando é concluído, a chave é renomeada, mas as entradas de registro na chave permanecem inalteradas.</span><span class="sxs-lookup"><span data-stu-id="9afe6-124">When the command is complete, the key is renamed, but the registry entries in the key are unchanged.</span></span>

```powershell
Rename-Item -Path "HKLM:\Software\MyCompany\Advertising" -NewName "Marketing"
```

### <span data-ttu-id="9afe6-125">Exemplo 4: renomear vários arquivos</span><span class="sxs-lookup"><span data-stu-id="9afe6-125">Example 4: Rename multiple files</span></span>

<span data-ttu-id="9afe6-126">Este exemplo renomeia todos os `*.txt` arquivos no diretório atual para `*.log` .</span><span class="sxs-lookup"><span data-stu-id="9afe6-126">This example renames all the `*.txt` files in the current directory to `*.log`.</span></span>

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

<span data-ttu-id="9afe6-127">O `Get-ChildItem` cmdlet obtém todos os arquivos na pasta atual que têm uma `.txt` extensão de arquivo, em seguida, os canaliza para `Rename-Item` .</span><span class="sxs-lookup"><span data-stu-id="9afe6-127">The `Get-ChildItem` cmdlet gets all the files in the current folder that have a `.txt` file extension then pipes them to `Rename-Item`.</span></span> <span data-ttu-id="9afe6-128">O valor de **NewName** é um bloco de script que é executado antes que o valor seja enviado ao parâmetro **NewName** .</span><span class="sxs-lookup"><span data-stu-id="9afe6-128">The value of **NewName** is a script block that runs before the value is submitted to the **NewName** parameter.</span></span>

<span data-ttu-id="9afe6-129">No bloco de script, a `$_` variável automática representa cada objeto de arquivo como ele se refere ao comando por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="9afe6-129">In the script block, the `$_` automatic variable represents each file object as it comes to the command through the pipeline.</span></span> <span data-ttu-id="9afe6-130">O bloco de script usa o `-replace` operador para substituir a extensão de arquivo de cada arquivo por `.log` .</span><span class="sxs-lookup"><span data-stu-id="9afe6-130">The script block uses the `-replace` operator to replace the file extension of each file with `.log`.</span></span> <span data-ttu-id="9afe6-131">Observe que a correspondência usando o `-replace` operador não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9afe6-131">Notice that matching using the `-replace` operator is not case sensitive.</span></span>

## <span data-ttu-id="9afe6-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9afe6-132">PARAMETERS</span></span>

### <span data-ttu-id="9afe6-133">-Credential</span><span class="sxs-lookup"><span data-stu-id="9afe6-133">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="9afe6-134">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9afe6-134">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="9afe6-135">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="9afe6-135">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="9afe6-136">-Force</span><span class="sxs-lookup"><span data-stu-id="9afe6-136">-Force</span></span>

<span data-ttu-id="9afe6-137">Força o cmdlet a renomear itens que não podem ser alterados de outra forma, como arquivos ocultos ou somente leitura ou aliases ou variáveis somente leitura.</span><span class="sxs-lookup"><span data-stu-id="9afe6-137">Forces the cmdlet to rename items that can't otherwise be changed, such as hidden or read-only files or read-only aliases or variables.</span></span> <span data-ttu-id="9afe6-138">O cmdlet não pode alterar aliases ou variáveis constantes.</span><span class="sxs-lookup"><span data-stu-id="9afe6-138">The cmdlet can't change constant aliases or variables.</span></span>
<span data-ttu-id="9afe6-139">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="9afe6-139">Implementation varies from provider to provider.</span></span> <span data-ttu-id="9afe6-140">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="9afe6-140">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="9afe6-141">Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="9afe6-141">Even using the **Force** parameter, the cmdlet can't override security restrictions.</span></span>

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

### <span data-ttu-id="9afe6-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9afe6-142">-LiteralPath</span></span>

<span data-ttu-id="9afe6-143">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="9afe6-143">Specifies a path to one or more locations.</span></span> <span data-ttu-id="9afe6-144">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="9afe6-144">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="9afe6-145">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="9afe6-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="9afe6-146">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="9afe6-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="9afe6-147">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="9afe6-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="9afe6-148">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="9afe6-148">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="9afe6-149">-NewName</span><span class="sxs-lookup"><span data-stu-id="9afe6-149">-NewName</span></span>

<span data-ttu-id="9afe6-150">Especifica o novo nome do item.</span><span class="sxs-lookup"><span data-stu-id="9afe6-150">Specifies the new name of the item.</span></span> <span data-ttu-id="9afe6-151">Digite apenas um nome, não um caminho e nome.</span><span class="sxs-lookup"><span data-stu-id="9afe6-151">Enter only a name, not a path and name.</span></span> <span data-ttu-id="9afe6-152">Se você inserir um caminho diferente do caminho especificado no parâmetro **path** , o `Rename-Item` gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="9afe6-152">If you enter a path that differs from the path that is specified in the **Path** parameter, `Rename-Item` generates an error.</span></span>
<span data-ttu-id="9afe6-153">Para renomear e mover um item, use `Move-Item` .</span><span class="sxs-lookup"><span data-stu-id="9afe6-153">To rename and move an item, use `Move-Item`.</span></span>

<span data-ttu-id="9afe6-154">Você não pode usar caracteres curinga no valor do parâmetro **NewName** .</span><span class="sxs-lookup"><span data-stu-id="9afe6-154">You can't use wildcard characters in the value of the **NewName** parameter.</span></span> <span data-ttu-id="9afe6-155">Para especificar um nome para vários arquivos, use o operador **replace** em uma expressão regular.</span><span class="sxs-lookup"><span data-stu-id="9afe6-155">To specify a name for multiple files, use the **Replace** operator in a regular expression.</span></span> <span data-ttu-id="9afe6-156">Para obter mais informações sobre o operador Replace, consulte [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="9afe6-156">For more information about the Replace operator, see [about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md).</span></span>

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

### <span data-ttu-id="9afe6-157">-PassThru</span><span class="sxs-lookup"><span data-stu-id="9afe6-157">-PassThru</span></span>

<span data-ttu-id="9afe6-158">Retorna um objeto que representa o item para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="9afe6-158">Returns an object that represents the item to the pipeline.</span></span> <span data-ttu-id="9afe6-159">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="9afe6-159">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="9afe6-160">-Path</span><span class="sxs-lookup"><span data-stu-id="9afe6-160">-Path</span></span>

<span data-ttu-id="9afe6-161">Especifica o caminho do item a ser renomeado.</span><span class="sxs-lookup"><span data-stu-id="9afe6-161">Specifies the path of the item to rename.</span></span>

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

### <span data-ttu-id="9afe6-162">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9afe6-162">-Confirm</span></span>

<span data-ttu-id="9afe6-163">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9afe6-163">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9afe6-164">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9afe6-164">-WhatIf</span></span>

<span data-ttu-id="9afe6-165">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="9afe6-165">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9afe6-166">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="9afe6-166">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9afe6-167">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9afe6-167">CommonParameters</span></span>

<span data-ttu-id="9afe6-168">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9afe6-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9afe6-169">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9afe6-169">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9afe6-170">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9afe6-170">INPUTS</span></span>

### <span data-ttu-id="9afe6-171">System.String</span><span class="sxs-lookup"><span data-stu-id="9afe6-171">System.String</span></span>

<span data-ttu-id="9afe6-172">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9afe6-172">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="9afe6-173">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9afe6-173">OUTPUTS</span></span>

### <span data-ttu-id="9afe6-174">Nenhum ou um objeto que representa o item renomeado.</span><span class="sxs-lookup"><span data-stu-id="9afe6-174">None or an object that represents the renamed item.</span></span>

<span data-ttu-id="9afe6-175">Esse cmdlet gera um objeto que representa o item renomeado, se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="9afe6-175">This cmdlet generates an object that represents the renamed item, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="9afe6-176">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="9afe6-176">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9afe6-177">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9afe6-177">NOTES</span></span>

<span data-ttu-id="9afe6-178">`Rename-Item` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="9afe6-178">`Rename-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="9afe6-179">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="9afe6-179">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="9afe6-180">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="9afe6-180">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="9afe6-181">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9afe6-181">RELATED LINKS</span></span>

[<span data-ttu-id="9afe6-182">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="9afe6-182">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="9afe6-183">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="9afe6-183">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="9afe6-184">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="9afe6-184">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="9afe6-185">Get-Item</span><span class="sxs-lookup"><span data-stu-id="9afe6-185">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="9afe6-186">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="9afe6-186">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="9afe6-187">Move-Item</span><span class="sxs-lookup"><span data-stu-id="9afe6-187">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="9afe6-188">New-Item</span><span class="sxs-lookup"><span data-stu-id="9afe6-188">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="9afe6-189">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="9afe6-189">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="9afe6-190">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9afe6-190">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="9afe6-191">Set-Item</span><span class="sxs-lookup"><span data-stu-id="9afe6-191">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="9afe6-192">about_Providers</span><span class="sxs-lookup"><span data-stu-id="9afe6-192">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

