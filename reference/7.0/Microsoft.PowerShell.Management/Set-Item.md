---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Item
ms.openlocfilehash: 4485b1a140b1496ee80d81d1526b3d76e446fd34
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193044"
---
# <span data-ttu-id="7d4b7-103">Set-Item</span><span class="sxs-lookup"><span data-stu-id="7d4b7-103">Set-Item</span></span>

## <span data-ttu-id="7d4b7-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="7d4b7-104">SYNOPSIS</span></span>
<span data-ttu-id="7d4b7-105">Altera o valor de um item para o valor especificado no comando.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-105">Changes the value of an item to the value specified in the command.</span></span>

## <span data-ttu-id="7d4b7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7d4b7-106">SYNTAX</span></span>

### <span data-ttu-id="7d4b7-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="7d4b7-107">Path (Default)</span></span>

```
Set-Item [-Path] <String[]> [[-Value] <Object>] [-Force] [-PassThru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7d4b7-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7d4b7-108">LiteralPath</span></span>

```
Set-Item -LiteralPath <String[]> [[-Value] <Object>] [-Force] [-PassThru] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7d4b7-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7d4b7-109">DESCRIPTION</span></span>

<span data-ttu-id="7d4b7-110">O `Set-Item` cmdlet altera o valor de um item, como uma variável ou chave do registro, para o valor especificado no comando.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-110">The `Set-Item` cmdlet changes the value of an item, such as a variable or registry key, to the value specified in the command.</span></span>

## <span data-ttu-id="7d4b7-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="7d4b7-111">EXAMPLES</span></span>

### <span data-ttu-id="7d4b7-112">Exemplo 1: criar um alias</span><span class="sxs-lookup"><span data-stu-id="7d4b7-112">Example 1: Create an alias</span></span>

<span data-ttu-id="7d4b7-113">Este comando cria um alias de NP para o bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-113">This command creates an alias of np for Notepad.</span></span>

```powershell
Set-Item -Path alias:np -Value "c:\windows\notepad.exe"
```

### <span data-ttu-id="7d4b7-114">Exemplo 2: alterar o valor de uma variável de ambiente</span><span class="sxs-lookup"><span data-stu-id="7d4b7-114">Example 2: Change the value of an environment variable</span></span>

<span data-ttu-id="7d4b7-115">Esse comando altera o valor da variável de ambiente USERROLE para administrador.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-115">This command changes the value of the UserRole environment variable to Administrator.</span></span>

```powershell
Set-Item -Path env:UserRole -Value "Administrator"
```

### <span data-ttu-id="7d4b7-116">Exemplo 3: modificar sua função de prompt</span><span class="sxs-lookup"><span data-stu-id="7d4b7-116">Example 3: Modify your prompt function</span></span>

<span data-ttu-id="7d4b7-117">Esse comando altera a função de prompt para que ela exiba a hora antes do caminho.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-117">This command changes the prompt function so that it displays the time before the path.</span></span>

```powershell
Set-Item -Path function:prompt -Value {'PS '+ (Get-Date -Format t) + " " + (Get-Location) + '> '}
```

### <span data-ttu-id="7d4b7-118">Exemplo 4: definir opções para a função de prompt</span><span class="sxs-lookup"><span data-stu-id="7d4b7-118">Example 4: Set options for your prompt function</span></span>

<span data-ttu-id="7d4b7-119">Este comando define as opções de **escopo** e **somente leitura** para a função de prompt.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-119">This command sets the **AllScope** and **ReadOnly** options for the prompt function.</span></span>
<span data-ttu-id="7d4b7-120">Esse comando usa o parâmetro dinâmico **Options** de `Set-Item` .</span><span class="sxs-lookup"><span data-stu-id="7d4b7-120">This command uses the **Options** dynamic parameter of `Set-Item`.</span></span>
<span data-ttu-id="7d4b7-121">O parâmetro **Options** está disponível `Set-Item` somente quando você o usa com o **alias** ou o provedor de **funções** .</span><span class="sxs-lookup"><span data-stu-id="7d4b7-121">The **Options** parameter is available in `Set-Item` only when you use it with the **Alias** or **Function** provider.</span></span>

```powershell
Set-Item -Path function:prompt -Options "AllScope,ReadOnly"
```

## <span data-ttu-id="7d4b7-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7d4b7-122">PARAMETERS</span></span>

### <span data-ttu-id="7d4b7-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="7d4b7-123">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="7d4b7-124">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-124">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="7d4b7-125">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="7d4b7-125">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="7d4b7-126">-Excluir</span><span class="sxs-lookup"><span data-stu-id="7d4b7-126">-Exclude</span></span>

<span data-ttu-id="7d4b7-127">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-127">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="7d4b7-128">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="7d4b7-128">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="7d4b7-129">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="7d4b7-129">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="7d4b7-130">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-130">Wildcard characters are permitted.</span></span> <span data-ttu-id="7d4b7-131">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-131">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="7d4b7-132">-Filter</span><span class="sxs-lookup"><span data-stu-id="7d4b7-132">-Filter</span></span>

<span data-ttu-id="7d4b7-133">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="7d4b7-133">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="7d4b7-134">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-134">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="7d4b7-135">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="7d4b7-135">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="7d4b7-136">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-136">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="7d4b7-137">-Force</span><span class="sxs-lookup"><span data-stu-id="7d4b7-137">-Force</span></span>

<span data-ttu-id="7d4b7-138">Força o cmdlet a definir itens que, de outra forma, não podem ser alterados, como alias ou variáveis somente leitura.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-138">Forces the cmdlet to set items that cannot otherwise be changed, such as read-only alias or variables.</span></span> <span data-ttu-id="7d4b7-139">O cmdlet não pode alterar variáveis nem aliases constantes.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-139">The cmdlet cannot change constant aliases or variables.</span></span>
<span data-ttu-id="7d4b7-140">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-140">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="7d4b7-141">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="7d4b7-141">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="7d4b7-142">Mesmo usando o parâmetro *Force* , o cmdlet não pode substituir as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-142">Even using the *Force* parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="7d4b7-143">-Incluir</span><span class="sxs-lookup"><span data-stu-id="7d4b7-143">-Include</span></span>

<span data-ttu-id="7d4b7-144">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-144">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="7d4b7-145">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="7d4b7-145">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="7d4b7-146">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="7d4b7-146">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="7d4b7-147">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-147">Wildcard characters are permitted.</span></span> <span data-ttu-id="7d4b7-148">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-148">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="7d4b7-149">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7d4b7-149">-LiteralPath</span></span>

<span data-ttu-id="7d4b7-150">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-150">Specifies a path to one or more locations.</span></span> <span data-ttu-id="7d4b7-151">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-151">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="7d4b7-152">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-152">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="7d4b7-153">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-153">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="7d4b7-154">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-154">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="7d4b7-155">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="7d4b7-155">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="7d4b7-156">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7d4b7-156">-PassThru</span></span>

<span data-ttu-id="7d4b7-157">Passa um objeto que representa o item para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-157">Passes an object that represents the item to the pipeline.</span></span>
<span data-ttu-id="7d4b7-158">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-158">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="7d4b7-159">-Path</span><span class="sxs-lookup"><span data-stu-id="7d4b7-159">-Path</span></span>

<span data-ttu-id="7d4b7-160">Especifica um caminho do local dos itens.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-160">Specifies a path of the location of the items.</span></span>
<span data-ttu-id="7d4b7-161">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-161">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="7d4b7-162">-Value</span><span class="sxs-lookup"><span data-stu-id="7d4b7-162">-Value</span></span>

<span data-ttu-id="7d4b7-163">Especifica um novo valor para o item.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-163">Specifies a new value for the item.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7d4b7-164">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7d4b7-164">-Confirm</span></span>

<span data-ttu-id="7d4b7-165">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-165">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7d4b7-166">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7d4b7-166">-WhatIf</span></span>

<span data-ttu-id="7d4b7-167">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-167">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7d4b7-168">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-168">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7d4b7-169">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7d4b7-169">CommonParameters</span></span>

<span data-ttu-id="7d4b7-170">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="7d4b7-170">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="7d4b7-171">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="7d4b7-171">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="7d4b7-172">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="7d4b7-172">INPUTS</span></span>

### <span data-ttu-id="7d4b7-173">System.Object</span><span class="sxs-lookup"><span data-stu-id="7d4b7-173">System.Object</span></span>

<span data-ttu-id="7d4b7-174">É possível canalizar um objeto que representa o novo valor do item para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-174">You can pipe an object that represents the new value of the item to this cmdlet.</span></span>

## <span data-ttu-id="7d4b7-175">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="7d4b7-175">OUTPUTS</span></span>

### <span data-ttu-id="7d4b7-176">Nenhum ou um objeto que representa o item novo ou alterado.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-176">None or an object representing the new or changed item.</span></span>

<span data-ttu-id="7d4b7-177">Esse cmdlet gera um objeto que representa o item, se você especificar o parâmetro *PassThru* .</span><span class="sxs-lookup"><span data-stu-id="7d4b7-177">This cmdlet generates an object that represent the item, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="7d4b7-178">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-178">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7d4b7-179">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="7d4b7-179">NOTES</span></span>

- <span data-ttu-id="7d4b7-180">`Set-Item` Não é suportado pelo provedor de sistema de arquivos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-180">`Set-Item` is not supported by the PowerShell FileSystem provider.</span></span> <span data-ttu-id="7d4b7-181">Para alterar os valores de itens no sistema de arquivos, use o `Set-Content` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-181">To change the values of items in the file system, use the `Set-Content` cmdlet.</span></span>
- <span data-ttu-id="7d4b7-182">Nas unidades de registro, `HKLM:` e `HKCU:` `Set-Item` altera os dados no valor (padrão) de uma chave do registro.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-182">In the Registry drives, `HKLM:` and `HKCU:`, `Set-Item` changes the data in the (Default) value of a registry key.</span></span>
  - <span data-ttu-id="7d4b7-183">Para criar e alterar os nomes das chaves do registro, use `New-Item` o `Rename-Item` cmdlet e.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-183">To create and change the names of registry keys, use the `New-Item` and `Rename-Item` cmdlet.</span></span>
  - <span data-ttu-id="7d4b7-184">Para alterar os nomes e os dados em valores de registro, use os `New-ItemProperty` `Set-ItemProperty` `Rename-ItemProperty` cmdlets, e.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-184">To change the names and data in registry values, use the `New-ItemProperty`, `Set-ItemProperty`, and `Rename-ItemProperty` cmdlets.</span></span>
- <span data-ttu-id="7d4b7-185">`Set-Item` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="7d4b7-185">`Set-Item` is designed to work with the data exposed by any provider.</span></span>
  <span data-ttu-id="7d4b7-186">Para listar os provedores disponíveis em sua sessão, digite `Get-PsProvider` .</span><span class="sxs-lookup"><span data-stu-id="7d4b7-186">To list the providers available in your session, type `Get-PsProvider`.</span></span>
  <span data-ttu-id="7d4b7-187">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="7d4b7-187">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="7d4b7-188">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="7d4b7-188">RELATED LINKS</span></span>

[<span data-ttu-id="7d4b7-189">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="7d4b7-189">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="7d4b7-190">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="7d4b7-190">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="7d4b7-191">Get-Item</span><span class="sxs-lookup"><span data-stu-id="7d4b7-191">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="7d4b7-192">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="7d4b7-192">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="7d4b7-193">Move-Item</span><span class="sxs-lookup"><span data-stu-id="7d4b7-193">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="7d4b7-194">New-Item</span><span class="sxs-lookup"><span data-stu-id="7d4b7-194">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="7d4b7-195">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="7d4b7-195">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="7d4b7-196">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="7d4b7-196">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="7d4b7-197">about_Providers</span><span class="sxs-lookup"><span data-stu-id="7d4b7-197">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
