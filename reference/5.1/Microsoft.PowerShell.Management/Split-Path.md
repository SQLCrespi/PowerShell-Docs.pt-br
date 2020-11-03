---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/split-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Split-Path
ms.openlocfilehash: 5d92acbe080b0d232047f1184c9a369b8837845c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193916"
---
# <span data-ttu-id="ada9f-103">Split-Path</span><span class="sxs-lookup"><span data-stu-id="ada9f-103">Split-Path</span></span>

## <span data-ttu-id="ada9f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ada9f-104">SYNOPSIS</span></span>
<span data-ttu-id="ada9f-105">Retorna a parte especificada de um caminho.</span><span class="sxs-lookup"><span data-stu-id="ada9f-105">Returns the specified part of a path.</span></span>

## <span data-ttu-id="ada9f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ada9f-106">SYNTAX</span></span>

### <span data-ttu-id="ada9f-107">Parentset (padrão)</span><span class="sxs-lookup"><span data-stu-id="ada9f-107">ParentSet (Default)</span></span>

```
Split-Path [-Path] <String[]> [-Parent] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="ada9f-108">Noqualifierset</span><span class="sxs-lookup"><span data-stu-id="ada9f-108">NoQualifierSet</span></span>

```
Split-Path [-Path] <String[]> [-NoQualifier] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="ada9f-109">Folha de um</span><span class="sxs-lookup"><span data-stu-id="ada9f-109">LeafSet</span></span>

```
Split-Path [-Path] <String[]> [-Leaf] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="ada9f-110">Qualificador</span><span class="sxs-lookup"><span data-stu-id="ada9f-110">QualifierSet</span></span>

```
Split-Path [-Path] <String[]> [-Qualifier] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="ada9f-111">Isabsolutaset</span><span class="sxs-lookup"><span data-stu-id="ada9f-111">IsAbsoluteSet</span></span>

```
Split-Path [-Path] <String[]> [-Resolve] [-IsAbsolute] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### <span data-ttu-id="ada9f-112">LiteralPathSet</span><span class="sxs-lookup"><span data-stu-id="ada9f-112">LiteralPathSet</span></span>

```
Split-Path -LiteralPath <String[]> [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

## <span data-ttu-id="ada9f-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ada9f-113">DESCRIPTION</span></span>

<span data-ttu-id="ada9f-114">O cmdlet **Split-Path** retorna apenas a parte especificada de um caminho, como a pasta pai, uma subpasta ou um nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="ada9f-114">The **Split-Path** cmdlet returns only the specified part of a path, such as the parent folder, a subfolder, or a file name.</span></span>
<span data-ttu-id="ada9f-115">Também pode obter itens que são referenciados pelo caminho de divisão e informar se o caminho é relativo ou absoluto.</span><span class="sxs-lookup"><span data-stu-id="ada9f-115">It can also get items that are referenced by the split path and tell whether the path is relative or absolute.</span></span>

<span data-ttu-id="ada9f-116">Você pode usar esse cmdlet para obter ou enviar apenas uma parte selecionada de um caminho.</span><span class="sxs-lookup"><span data-stu-id="ada9f-116">You can use this cmdlet to get or submit only a selected part of a path.</span></span>

## <span data-ttu-id="ada9f-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ada9f-117">EXAMPLES</span></span>

### <span data-ttu-id="ada9f-118">Exemplo 1: obter o qualificador de um caminho</span><span class="sxs-lookup"><span data-stu-id="ada9f-118">Example 1: Get the qualifier of a path</span></span>

```
PS C:\> Split-Path -Path "HKCU:\Software\Microsoft" -Qualifier
HKCU:
```

<span data-ttu-id="ada9f-119">Esse comando retorna somente o qualificador do caminho.</span><span class="sxs-lookup"><span data-stu-id="ada9f-119">This command returns only the qualifier of the path.</span></span>
<span data-ttu-id="ada9f-120">O qualificador é a unidade.</span><span class="sxs-lookup"><span data-stu-id="ada9f-120">The qualifier is the drive.</span></span>

### <span data-ttu-id="ada9f-121">Exemplo 2: exibir nomes de arquivo</span><span class="sxs-lookup"><span data-stu-id="ada9f-121">Example 2: Display file names</span></span>

```
PS C:\> Split-Path -Path "C:\Test\Logs\*.log" -Leaf -Resolve
Pass1.log
Pass2.log
...
```

<span data-ttu-id="ada9f-122">Esse comando exibe os arquivos que são referenciados pelo caminho de divisão.</span><span class="sxs-lookup"><span data-stu-id="ada9f-122">This command displays the files that are referenced by the split path.</span></span>
<span data-ttu-id="ada9f-123">Como esse caminho é dividido para o último item, também conhecido como folha, o comando exibe somente os nomes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="ada9f-123">Because this path is split to the last item, also known as the leaf, the command displays only the file names.</span></span>

<span data-ttu-id="ada9f-124">O parâmetro *resolve* informa ao **Split-Path** para exibir os itens que o caminho de divisão referencia, em vez de exibir o caminho de divisão.</span><span class="sxs-lookup"><span data-stu-id="ada9f-124">The *Resolve* parameter tells **Split-Path** to display the items that the split path references, instead of displaying the split path.</span></span>

<span data-ttu-id="ada9f-125">Assim como todos os comandos **de divisão-caminho** , esse comando retorna cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ada9f-125">Like all **Split-Path** commands, this command returns strings.</span></span>
<span data-ttu-id="ada9f-126">Ele não retorna objetos **FileInfo** que representam os arquivos.</span><span class="sxs-lookup"><span data-stu-id="ada9f-126">It does not return **FileInfo** objects that represent the files.</span></span>

### <span data-ttu-id="ada9f-127">Exemplo 3: obter o contêiner pai</span><span class="sxs-lookup"><span data-stu-id="ada9f-127">Example 3: Get the parent container</span></span>

```
PS C:\> Split-Path -Path "C:\WINDOWS\system32\WindowsPowerShell\V1.0\about_*.txt"
C:\WINDOWS\system32\WindowsPowerShell\V1.0
```

<span data-ttu-id="ada9f-128">Esse comando retorna apenas os contêineres pai do caminho.</span><span class="sxs-lookup"><span data-stu-id="ada9f-128">This command returns only the parent containers of the path.</span></span>
<span data-ttu-id="ada9f-129">Como não inclui nenhum parâmetro para especificar a divisão, **Split-Path** usa o padrão de localização de divisão, que é o *pai* .</span><span class="sxs-lookup"><span data-stu-id="ada9f-129">Because it does not include any parameters to specify the split, **Split-Path** uses the split location default, which is *Parent* .</span></span>

### <span data-ttu-id="ada9f-130">Exemplo 4: determina se um caminho é absoluto</span><span class="sxs-lookup"><span data-stu-id="ada9f-130">Example 4: Determines whether a path is absolute</span></span>

```
PS C:\> Split-Path -Path ".\My Pictures\*.jpg" -IsAbsolute
False
```

<span data-ttu-id="ada9f-131">Esse comando determina se o caminho é relativo ou absoluto.</span><span class="sxs-lookup"><span data-stu-id="ada9f-131">This command determines whether the path is relative or absolute.</span></span>
<span data-ttu-id="ada9f-132">Nesse caso, como o caminho é relativo à pasta atual, que é representada por um ponto (.), ela retorna $False.</span><span class="sxs-lookup"><span data-stu-id="ada9f-132">In this case, because the path is relative to the current folder, which is represented by a dot (.), it returns $False.</span></span>

### <span data-ttu-id="ada9f-133">Exemplo 5: alterar o local para um caminho especificado</span><span class="sxs-lookup"><span data-stu-id="ada9f-133">Example 5: Change location to a specified path</span></span>

```
PS C:\> Set-Location (Split-Path -Path $profile)
PS C:\Documents and Settings\User01\My Documents\WindowsPowerShell>
```

<span data-ttu-id="ada9f-134">Esse comando altera o local para a pasta que contém o perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ada9f-134">This command changes your location to the folder that contains the PowerShell profile.</span></span>

<span data-ttu-id="ada9f-135">O comando entre parênteses usa **Split-Path** para retornar apenas o pai do caminho armazenado na variável de $Profile interna.</span><span class="sxs-lookup"><span data-stu-id="ada9f-135">The command in parentheses uses **Split-Path** to return only the parent of the path stored in the built-in $Profile variable.</span></span>
<span data-ttu-id="ada9f-136">O parâmetro *pai* é o parâmetro de local de divisão padrão.</span><span class="sxs-lookup"><span data-stu-id="ada9f-136">The *Parent* parameter is the default split location parameter.</span></span>
<span data-ttu-id="ada9f-137">Portanto, você pode omiti-lo do comando.</span><span class="sxs-lookup"><span data-stu-id="ada9f-137">Therefore, you can omit it from the command.</span></span>
<span data-ttu-id="ada9f-138">Os parênteses direcionam o PowerShell para executar o comando primeiro.</span><span class="sxs-lookup"><span data-stu-id="ada9f-138">The parentheses direct PowerShell to run the command first.</span></span>
<span data-ttu-id="ada9f-139">Essa é uma maneira útil de mover para uma pasta que tem um nome de caminho longo.</span><span class="sxs-lookup"><span data-stu-id="ada9f-139">This is a useful way to move to a folder that has a long path name.</span></span>

### <span data-ttu-id="ada9f-140">Exemplo 6: dividir um caminho usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="ada9f-140">Example 6: Split a path by using the pipeline</span></span>

```
PS C:\> 'C:\Documents and Settings\User01\My Documents\My Pictures' | Split-Path
C:\Documents and Settings\User01\My Documents
```

<span data-ttu-id="ada9f-141">Este comando usa um operador de pipeline (|) para enviar um caminho para o **caminho de divisão** .</span><span class="sxs-lookup"><span data-stu-id="ada9f-141">This command uses a pipeline operator (|) to send a path to **Split-Path** .</span></span>
<span data-ttu-id="ada9f-142">O caminho é colocado entre aspas para indicar que se trata de um único token.</span><span class="sxs-lookup"><span data-stu-id="ada9f-142">The path is enclosed in quotation marks to indicate that it is a single token.</span></span>

## <span data-ttu-id="ada9f-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ada9f-143">PARAMETERS</span></span>

### <span data-ttu-id="ada9f-144">-Credential</span><span class="sxs-lookup"><span data-stu-id="ada9f-144">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="ada9f-145">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ada9f-145">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="ada9f-146">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="ada9f-146">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ada9f-147">-Isabsoluta</span><span class="sxs-lookup"><span data-stu-id="ada9f-147">-IsAbsolute</span></span>

<span data-ttu-id="ada9f-148">Indica que esse cmdlet retornará $True se o caminho for absoluto e $False se for relativo.</span><span class="sxs-lookup"><span data-stu-id="ada9f-148">Indicates that this cmdlet returns $True if the path is absolute and $False if it is relative.</span></span>
<span data-ttu-id="ada9f-149">Um caminho absoluto tem um comprimento maior que zero e não usa um ponto (.) para indicar o caminho atual.</span><span class="sxs-lookup"><span data-stu-id="ada9f-149">An absolute path has a length greater than zero and does not use a dot (.) to indicate the current path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsAbsoluteSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ada9f-150">-Folha</span><span class="sxs-lookup"><span data-stu-id="ada9f-150">-Leaf</span></span>

<span data-ttu-id="ada9f-151">Indica que esse cmdlet retorna apenas o último item ou contêiner no caminho.</span><span class="sxs-lookup"><span data-stu-id="ada9f-151">Indicates that this cmdlet returns only the last item or container in the path.</span></span>
<span data-ttu-id="ada9f-152">Por exemplo, no caminho `C:\Test\Logs\Pass1.log` , ele retorna somente Pass1. log.</span><span class="sxs-lookup"><span data-stu-id="ada9f-152">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only Pass1.log.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ada9f-153">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ada9f-153">-LiteralPath</span></span>

<span data-ttu-id="ada9f-154">Especifica os caminhos que serão divididos.</span><span class="sxs-lookup"><span data-stu-id="ada9f-154">Specifies the paths to be split.</span></span>
<span data-ttu-id="ada9f-155">Ao contrário de *Path* , o valor de *LiteralPath* é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="ada9f-155">Unlike *Path* , the value of *LiteralPath* is used exactly as it is typed.</span></span>
<span data-ttu-id="ada9f-156">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="ada9f-156">No characters are interpreted as wildcard characters.</span></span>
<span data-ttu-id="ada9f-157">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="ada9f-157">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="ada9f-158">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="ada9f-158">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPathSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ada9f-159">-NoQualifier</span><span class="sxs-lookup"><span data-stu-id="ada9f-159">-NoQualifier</span></span>

<span data-ttu-id="ada9f-160">Indica que esse cmdlet retorna o caminho sem o qualificador.</span><span class="sxs-lookup"><span data-stu-id="ada9f-160">Indicates that this cmdlet returns the path without the qualifier.</span></span>
<span data-ttu-id="ada9f-161">Para os provedores de sistema de arquivos ou registro, o qualificador é a unidade do caminho de provedor, como C: ou HKCU:.</span><span class="sxs-lookup"><span data-stu-id="ada9f-161">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as C: or HKCU:.</span></span>
<span data-ttu-id="ada9f-162">Por exemplo, no caminho `C:\Test\Logs\Pass1.log` , ele retorna apenas \Test\Logs\Pass1.log.</span><span class="sxs-lookup"><span data-stu-id="ada9f-162">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only \Test\Logs\Pass1.log.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoQualifierSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ada9f-163">-Pai</span><span class="sxs-lookup"><span data-stu-id="ada9f-163">-Parent</span></span>

<span data-ttu-id="ada9f-164">Indica que esse cmdlet retorna somente os contêineres pai do item ou do contêiner especificado pelo caminho.</span><span class="sxs-lookup"><span data-stu-id="ada9f-164">Indicates that this cmdlet returns only the parent containers of the item or of the container specified by the path.</span></span>
<span data-ttu-id="ada9f-165">Por exemplo, no caminho `C:\Test\Logs\Pass1.log` , ele retorna C:\Test\Logs.</span><span class="sxs-lookup"><span data-stu-id="ada9f-165">For example, in the path `C:\Test\Logs\Pass1.log`, it returns C:\Test\Logs.</span></span>
<span data-ttu-id="ada9f-166">O parâmetro *pai* é o parâmetro de local de divisão padrão.</span><span class="sxs-lookup"><span data-stu-id="ada9f-166">The *Parent* parameter is the default split location parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ParentSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ada9f-167">-Path</span><span class="sxs-lookup"><span data-stu-id="ada9f-167">-Path</span></span>

<span data-ttu-id="ada9f-168">Especifica os caminhos que serão divididos.</span><span class="sxs-lookup"><span data-stu-id="ada9f-168">Specifies the paths to be split.</span></span>
<span data-ttu-id="ada9f-169">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="ada9f-169">Wildcard characters are permitted.</span></span>
<span data-ttu-id="ada9f-170">Se o caminho incluir espaços, coloque-os entre aspas.</span><span class="sxs-lookup"><span data-stu-id="ada9f-170">If the path includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="ada9f-171">Você também pode canalizar um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ada9f-171">You can also pipe a path to this cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ParentSet, NoQualifierSet, LeafSet, QualifierSet, IsAbsoluteSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="ada9f-172">-Qualificador</span><span class="sxs-lookup"><span data-stu-id="ada9f-172">-Qualifier</span></span>

<span data-ttu-id="ada9f-173">Indica que esse cmdlet retorna apenas o qualificador do caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="ada9f-173">Indicates that this cmdlet returns only the qualifier of the specified path.</span></span>
<span data-ttu-id="ada9f-174">Para os provedores de sistema de arquivos ou registro, o qualificador é a unidade do caminho de provedor, como C: ou HKCU:.</span><span class="sxs-lookup"><span data-stu-id="ada9f-174">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as C: or HKCU:.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: QualifierSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ada9f-175">-Resolver</span><span class="sxs-lookup"><span data-stu-id="ada9f-175">-Resolve</span></span>

<span data-ttu-id="ada9f-176">Indica que esse cmdlet exibe os itens que são referenciados pelo caminho dividido resultante em vez de exibir os elementos de caminho.</span><span class="sxs-lookup"><span data-stu-id="ada9f-176">Indicates that this cmdlet displays the items that are referenced by the resulting split path instead of displaying the path elements.</span></span>

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

### <span data-ttu-id="ada9f-177">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="ada9f-177">-UseTransaction</span></span>

<span data-ttu-id="ada9f-178">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="ada9f-178">Includes the command in the active transaction.</span></span>
<span data-ttu-id="ada9f-179">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="ada9f-179">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="ada9f-180">Para obter mais informações, consulte about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="ada9f-180">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="ada9f-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ada9f-181">CommonParameters</span></span>

<span data-ttu-id="ada9f-182">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ada9f-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ada9f-183">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ada9f-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ada9f-184">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ada9f-184">INPUTS</span></span>

### <span data-ttu-id="ada9f-185">System.String</span><span class="sxs-lookup"><span data-stu-id="ada9f-185">System.String</span></span>

<span data-ttu-id="ada9f-186">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ada9f-186">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="ada9f-187">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ada9f-187">OUTPUTS</span></span>

### <span data-ttu-id="ada9f-188">System. String, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="ada9f-188">System.String, System.Boolean</span></span>

<span data-ttu-id="ada9f-189">**Split-Path** retorna cadeias de caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="ada9f-189">**Split-Path** returns text strings.</span></span>
<span data-ttu-id="ada9f-190">Quando você especifica o parâmetro *resolve* , o **Split-Path** retorna uma cadeia de caracteres que descreve o local dos itens; Ele não retorna objetos que representam os itens, como um objeto **FileInfo** ou **RegistryKey** .</span><span class="sxs-lookup"><span data-stu-id="ada9f-190">When you specify the *Resolve* parameter, **Split-Path** returns a string that describes the location of the items; it does not return objects that represent the items, such as a **FileInfo** or **RegistryKey** object.</span></span>

<span data-ttu-id="ada9f-191">Quando você especifica o parâmetro *IsAbsolute* , o **Split-Path** retorna um valor **booliano** .</span><span class="sxs-lookup"><span data-stu-id="ada9f-191">When you specify the *IsAbsolute* parameter, **Split-Path** returns a **Boolean** value.</span></span>

## <span data-ttu-id="ada9f-192">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ada9f-192">NOTES</span></span>

* <span data-ttu-id="ada9f-193">Os parâmetros de localização de divisão ( *qualificador* , *pai* , *folha* e *NoQualifier* ) são exclusivos.</span><span class="sxs-lookup"><span data-stu-id="ada9f-193">The split location parameters ( *Qualifier* , *Parent* , *Leaf* , and *NoQualifier* ) are exclusive.</span></span> <span data-ttu-id="ada9f-194">Você pode usar somente uma opção em cada comando.</span><span class="sxs-lookup"><span data-stu-id="ada9f-194">You can use only one in each command.</span></span>

  <span data-ttu-id="ada9f-195">Os cmdlets que contêm o substantivo de **caminho** (os cmdlets de **caminho** ) funcionam com nomes de caminho e retornam os nomes em um formato conciso que todos os provedores do PowerShell podem interpretar.</span><span class="sxs-lookup"><span data-stu-id="ada9f-195">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span>
<span data-ttu-id="ada9f-196">Eles foram projetados para uso em programas e scripts onde você deseja exibir uma parte ou todo um nome de caminho em um formato específico.</span><span class="sxs-lookup"><span data-stu-id="ada9f-196">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span>
<span data-ttu-id="ada9f-197">Use-os na forma como você usaria **dirname** , **Normpath** , **realpath** , **Join** ou outros manipuladores de caminho.</span><span class="sxs-lookup"><span data-stu-id="ada9f-197">Use them in the way that you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

  <span data-ttu-id="ada9f-198">Você pode usar os cmdlets de **caminho** junto com vários provedores.</span><span class="sxs-lookup"><span data-stu-id="ada9f-198">You can use the **Path** cmdlets together with several providers.</span></span>
<span data-ttu-id="ada9f-199">Isso inclui o sistema de arquivos, o registro e os provedores de certificado.</span><span class="sxs-lookup"><span data-stu-id="ada9f-199">These include the FileSystem, Registry, and Certificate providers.</span></span>

  <span data-ttu-id="ada9f-200">A **divisão de caminho** é projetada para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="ada9f-200">**Split-Path** is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="ada9f-201">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="ada9f-201">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="ada9f-202">Para obter mais informações, consulte about_Providers.</span><span class="sxs-lookup"><span data-stu-id="ada9f-202">For more information, see about_Providers.</span></span>

## <span data-ttu-id="ada9f-203">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ada9f-203">RELATED LINKS</span></span>

[<span data-ttu-id="ada9f-204">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="ada9f-204">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="ada9f-205">Join-Path</span><span class="sxs-lookup"><span data-stu-id="ada9f-205">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="ada9f-206">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="ada9f-206">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="ada9f-207">Test-Path</span><span class="sxs-lookup"><span data-stu-id="ada9f-207">Test-Path</span></span>](Test-Path.md)
