---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-itemproperty?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-ItemProperty
ms.openlocfilehash: 3768a24438b0cc33711ebe61dc63c57c27bac976
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193394"
---
# <span data-ttu-id="d889c-103">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d889c-103">Rename-ItemProperty</span></span>

## <span data-ttu-id="d889c-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d889c-104">SYNOPSIS</span></span>
<span data-ttu-id="d889c-105">Renomeia uma propriedade de um item.</span><span class="sxs-lookup"><span data-stu-id="d889c-105">Renames a property of an item.</span></span>

## <span data-ttu-id="d889c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d889c-106">SYNTAX</span></span>

### <span data-ttu-id="d889c-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="d889c-107">Path (Default)</span></span>

```
Rename-ItemProperty [-Path] <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d889c-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d889c-108">LiteralPath</span></span>

```
Rename-ItemProperty -LiteralPath <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d889c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d889c-109">DESCRIPTION</span></span>

<span data-ttu-id="d889c-110">O `Rename-ItemProperty` cmdlet altera o nome de uma propriedade de item especificada.</span><span class="sxs-lookup"><span data-stu-id="d889c-110">The `Rename-ItemProperty` cmdlet changes the name of a specified item property.</span></span>
<span data-ttu-id="d889c-111">O valor da propriedade não é alterado.</span><span class="sxs-lookup"><span data-stu-id="d889c-111">The value of the property is not changed.</span></span>
<span data-ttu-id="d889c-112">Por exemplo, você pode usar `Rename-ItemProperty` para alterar o nome de uma entrada de registro.</span><span class="sxs-lookup"><span data-stu-id="d889c-112">For example, you can use `Rename-ItemProperty` to change the name of a registry entry.</span></span>

## <span data-ttu-id="d889c-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d889c-113">EXAMPLES</span></span>

### <span data-ttu-id="d889c-114">Exemplo 1: renomear uma entrada de registro</span><span class="sxs-lookup"><span data-stu-id="d889c-114">Example 1: Rename a registry entry</span></span>

<span data-ttu-id="d889c-115">Esse comando renomeia a entrada do registro de configuração que está contida na `HKEY_LOCAL_MACHINE\Software\SmpApplication` chave para "oldconfig".</span><span class="sxs-lookup"><span data-stu-id="d889c-115">This command renames the config registry entry that is contained in the `HKEY_LOCAL_MACHINE\Software\SmpApplication` key to "oldconfig".</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\Software\SmpApplication -Name config -NewName oldconfig
```

## <span data-ttu-id="d889c-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d889c-116">PARAMETERS</span></span>

### <span data-ttu-id="d889c-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="d889c-117">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="d889c-118">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d889c-118">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="d889c-119">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="d889c-119">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="d889c-120">-Excluir</span><span class="sxs-lookup"><span data-stu-id="d889c-120">-Exclude</span></span>

<span data-ttu-id="d889c-121">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="d889c-121">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="d889c-122">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="d889c-122">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="d889c-123">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="d889c-123">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="d889c-124">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d889c-124">Wildcard characters are permitted.</span></span> <span data-ttu-id="d889c-125">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="d889c-125">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="d889c-126">-Filter</span><span class="sxs-lookup"><span data-stu-id="d889c-126">-Filter</span></span>

<span data-ttu-id="d889c-127">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="d889c-127">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="d889c-128">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="d889c-128">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="d889c-129">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="d889c-129">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="d889c-130">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="d889c-130">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="d889c-131">-Force</span><span class="sxs-lookup"><span data-stu-id="d889c-131">-Force</span></span>

<span data-ttu-id="d889c-132">Força o cmdlet a renomear uma propriedade de um objeto que, de outra forma, não pode ser acessado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="d889c-132">Forces the cmdlet to rename a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="d889c-133">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="d889c-133">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="d889c-134">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d889c-134">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="d889c-135">-Incluir</span><span class="sxs-lookup"><span data-stu-id="d889c-135">-Include</span></span>

<span data-ttu-id="d889c-136">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="d889c-136">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="d889c-137">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="d889c-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="d889c-138">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="d889c-138">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="d889c-139">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d889c-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="d889c-140">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="d889c-140">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="d889c-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d889c-141">-LiteralPath</span></span>

<span data-ttu-id="d889c-142">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="d889c-142">Specifies a path to one or more locations.</span></span> <span data-ttu-id="d889c-143">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="d889c-143">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="d889c-144">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="d889c-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="d889c-145">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="d889c-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="d889c-146">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="d889c-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="d889c-147">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="d889c-147">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d889c-148">-Name</span><span class="sxs-lookup"><span data-stu-id="d889c-148">-Name</span></span>

<span data-ttu-id="d889c-149">Especifica o nome atual da propriedade a ser renomeada.</span><span class="sxs-lookup"><span data-stu-id="d889c-149">Specifies the current name of the property to rename.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d889c-150">-NewName</span><span class="sxs-lookup"><span data-stu-id="d889c-150">-NewName</span></span>

<span data-ttu-id="d889c-151">Especifica o novo nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="d889c-151">Specifies the new name for the property.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d889c-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d889c-152">-PassThru</span></span>

<span data-ttu-id="d889c-153">Retorna um objeto que representa a propriedade do item.</span><span class="sxs-lookup"><span data-stu-id="d889c-153">Returns an object that represents the item property.</span></span>
<span data-ttu-id="d889c-154">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="d889c-154">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="d889c-155">-Path</span><span class="sxs-lookup"><span data-stu-id="d889c-155">-Path</span></span>

<span data-ttu-id="d889c-156">Especifica o caminho do item a ser renomeado.</span><span class="sxs-lookup"><span data-stu-id="d889c-156">Specifies the path of the item to rename.</span></span>
<span data-ttu-id="d889c-157">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d889c-157">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="d889c-158">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d889c-158">-Confirm</span></span>

<span data-ttu-id="d889c-159">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d889c-159">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d889c-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d889c-160">-WhatIf</span></span>

<span data-ttu-id="d889c-161">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="d889c-161">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d889c-162">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="d889c-162">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d889c-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d889c-163">CommonParameters</span></span>

<span data-ttu-id="d889c-164">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="d889c-164">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="d889c-165">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d889c-165">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d889c-166">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d889c-166">INPUTS</span></span>

### <span data-ttu-id="d889c-167">System.String</span><span class="sxs-lookup"><span data-stu-id="d889c-167">System.String</span></span>

<span data-ttu-id="d889c-168">É possível canalizar uma cadeia de caracteres que contém um caminho, mas não um caminho literal, para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d889c-168">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="d889c-169">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d889c-169">OUTPUTS</span></span>

### <span data-ttu-id="d889c-170">Nenhum, System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="d889c-170">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="d889c-171">Esse cmdlet gera um **PSCustomObject** que representa a propriedade de item renomeada, se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="d889c-171">This cmdlet generates a **PSCustomObject** that represents the renamed item property, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="d889c-172">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="d889c-172">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d889c-173">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d889c-173">NOTES</span></span>

<span data-ttu-id="d889c-174">`Remove-ItemProperty` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="d889c-174">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="d889c-175">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="d889c-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="d889c-176">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d889c-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="d889c-177">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d889c-177">RELATED LINKS</span></span>

[<span data-ttu-id="d889c-178">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d889c-178">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="d889c-179">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d889c-179">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="d889c-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d889c-180">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="d889c-181">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d889c-181">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="d889c-182">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d889c-182">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="d889c-183">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d889c-183">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="d889c-184">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="d889c-184">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="d889c-185">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d889c-185">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="d889c-186">about_Providers</span><span class="sxs-lookup"><span data-stu-id="d889c-186">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
