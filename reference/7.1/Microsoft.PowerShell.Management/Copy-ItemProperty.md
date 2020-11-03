---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-itemproperty?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-ItemProperty
ms.openlocfilehash: 22c55ab07b5524e9552808ebaf385b18e22106ef
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194811"
---
# <span data-ttu-id="26e2e-103">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="26e2e-103">Copy-ItemProperty</span></span>

## <span data-ttu-id="26e2e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="26e2e-104">SYNOPSIS</span></span>
<span data-ttu-id="26e2e-105">Copia uma propriedade e o valor de um local especificado para outro local.</span><span class="sxs-lookup"><span data-stu-id="26e2e-105">Copies a property and value from a specified location to another location.</span></span>

## <span data-ttu-id="26e2e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="26e2e-106">SYNTAX</span></span>

### <span data-ttu-id="26e2e-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="26e2e-107">Path (Default)</span></span>

```
Copy-ItemProperty [-Path] <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="26e2e-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="26e2e-108">LiteralPath</span></span>

```
Copy-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="26e2e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="26e2e-109">DESCRIPTION</span></span>

<span data-ttu-id="26e2e-110">O `Copy-ItemProperty` cmdlet copia uma propriedade e um valor de um local especificado para outro local.</span><span class="sxs-lookup"><span data-stu-id="26e2e-110">The `Copy-ItemProperty` cmdlet copies a property and value from a specified location to another location.</span></span>
<span data-ttu-id="26e2e-111">Por exemplo, você pode usar este cmdlet para copiar uma ou mais entradas de registro de uma chave do registro para outra chave do registro.</span><span class="sxs-lookup"><span data-stu-id="26e2e-111">For instance, you can use this cmdlet to copy one or more registry entries from one registry key to another registry key.</span></span>

## <span data-ttu-id="26e2e-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="26e2e-112">EXAMPLES</span></span>

### <span data-ttu-id="26e2e-113">Exemplo 1: copiar uma propriedade de uma chave do registro para outra chave do registro</span><span class="sxs-lookup"><span data-stu-id="26e2e-113">Example 1: Copy a property from a registry key to another registry key</span></span>

<span data-ttu-id="26e2e-114">Esse comando copia a propriedade denominada "MyProperty" da chave do registro "MyApplication" para a chave do registro "MyApplicationRev2".</span><span class="sxs-lookup"><span data-stu-id="26e2e-114">This command copies the property named "MyProperty" from the "MyApplication" registry key to the "MyApplicationRev2" registry key.</span></span>

```powershell
Copy-ItemProperty -Path "MyApplication" -Destination "HKLM:\Software\MyApplicationRev2" -Name "MyProperty"
```

## <span data-ttu-id="26e2e-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="26e2e-115">PARAMETERS</span></span>

### <span data-ttu-id="26e2e-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="26e2e-116">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="26e2e-117">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26e2e-117">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="26e2e-118">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="26e2e-118">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="26e2e-119">-Destino</span><span class="sxs-lookup"><span data-stu-id="26e2e-119">-Destination</span></span>

<span data-ttu-id="26e2e-120">Especifica o caminho para o local de destino.</span><span class="sxs-lookup"><span data-stu-id="26e2e-120">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="26e2e-121">-Excluir</span><span class="sxs-lookup"><span data-stu-id="26e2e-121">-Exclude</span></span>

<span data-ttu-id="26e2e-122">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="26e2e-122">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="26e2e-123">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="26e2e-123">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="26e2e-124">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="26e2e-124">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="26e2e-125">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="26e2e-125">Wildcard characters are permitted.</span></span> <span data-ttu-id="26e2e-126">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="26e2e-126">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="26e2e-127">-Filter</span><span class="sxs-lookup"><span data-stu-id="26e2e-127">-Filter</span></span>

<span data-ttu-id="26e2e-128">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="26e2e-128">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="26e2e-129">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="26e2e-129">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="26e2e-130">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="26e2e-130">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="26e2e-131">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="26e2e-131">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="26e2e-132">-Force</span><span class="sxs-lookup"><span data-stu-id="26e2e-132">-Force</span></span>

<span data-ttu-id="26e2e-133">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="26e2e-133">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="26e2e-134">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="26e2e-134">Implementation varies from provider to provider.</span></span>

<span data-ttu-id="26e2e-135">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="26e2e-135">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="26e2e-136">-Incluir</span><span class="sxs-lookup"><span data-stu-id="26e2e-136">-Include</span></span>

<span data-ttu-id="26e2e-137">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="26e2e-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="26e2e-138">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="26e2e-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="26e2e-139">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="26e2e-139">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="26e2e-140">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="26e2e-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="26e2e-141">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="26e2e-141">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="26e2e-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="26e2e-142">-LiteralPath</span></span>

<span data-ttu-id="26e2e-143">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="26e2e-143">Specifies a path to one or more locations.</span></span> <span data-ttu-id="26e2e-144">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="26e2e-144">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="26e2e-145">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="26e2e-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="26e2e-146">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="26e2e-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="26e2e-147">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="26e2e-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="26e2e-148">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="26e2e-148">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="26e2e-149">-Name</span><span class="sxs-lookup"><span data-stu-id="26e2e-149">-Name</span></span>

<span data-ttu-id="26e2e-150">Especifica o nome da propriedade a ser copiada.</span><span class="sxs-lookup"><span data-stu-id="26e2e-150">Specifies the name of the property to be copied.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="26e2e-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="26e2e-151">-PassThru</span></span>

<span data-ttu-id="26e2e-152">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="26e2e-152">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="26e2e-153">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="26e2e-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="26e2e-154">-Path</span><span class="sxs-lookup"><span data-stu-id="26e2e-154">-Path</span></span>

<span data-ttu-id="26e2e-155">Especifica, como uma matriz de cadeia de caracteres, o caminho para a propriedade a ser copiada.</span><span class="sxs-lookup"><span data-stu-id="26e2e-155">Specifies, as a string array, the path to the property to be copied.</span></span>
<span data-ttu-id="26e2e-156">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="26e2e-156">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="26e2e-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="26e2e-157">-Confirm</span></span>

<span data-ttu-id="26e2e-158">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="26e2e-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="26e2e-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="26e2e-159">-WhatIf</span></span>

<span data-ttu-id="26e2e-160">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="26e2e-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="26e2e-161">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="26e2e-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="26e2e-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="26e2e-162">CommonParameters</span></span>

<span data-ttu-id="26e2e-163">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="26e2e-163">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="26e2e-164">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="26e2e-164">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="26e2e-165">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="26e2e-165">INPUTS</span></span>

### <span data-ttu-id="26e2e-166">System.String</span><span class="sxs-lookup"><span data-stu-id="26e2e-166">System.String</span></span>

<span data-ttu-id="26e2e-167">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="26e2e-167">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="26e2e-168">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="26e2e-168">OUTPUTS</span></span>

### <span data-ttu-id="26e2e-169">Nenhum ou System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="26e2e-169">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="26e2e-170">Quando você usa o parâmetro **PassThru** , esse cmdlet gera um **PSCustomObject** que representa a propriedade de item copiada.</span><span class="sxs-lookup"><span data-stu-id="26e2e-170">When you use the **Passthru** parameter, this cmdlet generates a **PsCustomObject** representing the copied item property.</span></span> <span data-ttu-id="26e2e-171">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="26e2e-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="26e2e-172">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="26e2e-172">NOTES</span></span>

<span data-ttu-id="26e2e-173">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="26e2e-173">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="26e2e-174">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="26e2e-174">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="26e2e-175">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="26e2e-175">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="26e2e-176">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="26e2e-176">RELATED LINKS</span></span>

[<span data-ttu-id="26e2e-177">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="26e2e-177">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="26e2e-178">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="26e2e-178">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="26e2e-179">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="26e2e-179">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="26e2e-180">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="26e2e-180">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="26e2e-181">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="26e2e-181">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="26e2e-182">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="26e2e-182">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="26e2e-183">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="26e2e-183">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="26e2e-184">about_Providers</span><span class="sxs-lookup"><span data-stu-id="26e2e-184">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

