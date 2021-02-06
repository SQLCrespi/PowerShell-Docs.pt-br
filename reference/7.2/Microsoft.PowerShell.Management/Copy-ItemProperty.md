---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-ItemProperty
ms.openlocfilehash: d6dd6d21d7c0022e8ca1ea7dbd8e1cab8a680de6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597000"
---
# <span data-ttu-id="d46c0-102">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d46c0-102">Copy-ItemProperty</span></span>

## <span data-ttu-id="d46c0-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d46c0-103">SYNOPSIS</span></span>
<span data-ttu-id="d46c0-104">Copia uma propriedade e o valor de um local especificado para outro local.</span><span class="sxs-lookup"><span data-stu-id="d46c0-104">Copies a property and value from a specified location to another location.</span></span>

## <span data-ttu-id="d46c0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d46c0-105">SYNTAX</span></span>

### <span data-ttu-id="d46c0-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="d46c0-106">Path (Default)</span></span>

```
Copy-ItemProperty [-Path] <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d46c0-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d46c0-107">LiteralPath</span></span>

```
Copy-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d46c0-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d46c0-108">DESCRIPTION</span></span>

<span data-ttu-id="d46c0-109">O `Copy-ItemProperty` cmdlet copia uma propriedade e um valor de um local especificado para outro local.</span><span class="sxs-lookup"><span data-stu-id="d46c0-109">The `Copy-ItemProperty` cmdlet copies a property and value from a specified location to another location.</span></span>
<span data-ttu-id="d46c0-110">Por exemplo, você pode usar este cmdlet para copiar uma ou mais entradas de registro de uma chave do registro para outra chave do registro.</span><span class="sxs-lookup"><span data-stu-id="d46c0-110">For instance, you can use this cmdlet to copy one or more registry entries from one registry key to another registry key.</span></span>

## <span data-ttu-id="d46c0-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d46c0-111">EXAMPLES</span></span>

### <span data-ttu-id="d46c0-112">Exemplo 1: copiar uma propriedade de uma chave do registro para outra chave do registro</span><span class="sxs-lookup"><span data-stu-id="d46c0-112">Example 1: Copy a property from a registry key to another registry key</span></span>

<span data-ttu-id="d46c0-113">Esse comando copia a propriedade denominada "MyProperty" da chave do registro "MyApplication" para a chave do registro "MyApplicationRev2".</span><span class="sxs-lookup"><span data-stu-id="d46c0-113">This command copies the property named "MyProperty" from the "MyApplication" registry key to the "MyApplicationRev2" registry key.</span></span>

```powershell
Copy-ItemProperty -Path "MyApplication" -Destination "HKLM:\Software\MyApplicationRev2" -Name "MyProperty"
```

## <span data-ttu-id="d46c0-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d46c0-114">PARAMETERS</span></span>

### <span data-ttu-id="d46c0-115">-Credential</span><span class="sxs-lookup"><span data-stu-id="d46c0-115">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="d46c0-116">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d46c0-116">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="d46c0-117">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="d46c0-117">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="d46c0-118">-Destino</span><span class="sxs-lookup"><span data-stu-id="d46c0-118">-Destination</span></span>

<span data-ttu-id="d46c0-119">Especifica o caminho para o local de destino.</span><span class="sxs-lookup"><span data-stu-id="d46c0-119">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="d46c0-120">-Excluir</span><span class="sxs-lookup"><span data-stu-id="d46c0-120">-Exclude</span></span>

<span data-ttu-id="d46c0-121">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="d46c0-121">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="d46c0-122">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="d46c0-122">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="d46c0-123">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="d46c0-123">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="d46c0-124">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d46c0-124">Wildcard characters are permitted.</span></span> <span data-ttu-id="d46c0-125">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="d46c0-125">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="d46c0-126">-Filter</span><span class="sxs-lookup"><span data-stu-id="d46c0-126">-Filter</span></span>

<span data-ttu-id="d46c0-127">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="d46c0-127">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="d46c0-128">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="d46c0-128">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="d46c0-129">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="d46c0-129">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="d46c0-130">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="d46c0-130">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="d46c0-131">-Force</span><span class="sxs-lookup"><span data-stu-id="d46c0-131">-Force</span></span>

<span data-ttu-id="d46c0-132">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="d46c0-132">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="d46c0-133">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="d46c0-133">Implementation varies from provider to provider.</span></span>

<span data-ttu-id="d46c0-134">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d46c0-134">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="d46c0-135">-Incluir</span><span class="sxs-lookup"><span data-stu-id="d46c0-135">-Include</span></span>

<span data-ttu-id="d46c0-136">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="d46c0-136">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="d46c0-137">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="d46c0-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="d46c0-138">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="d46c0-138">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="d46c0-139">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d46c0-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="d46c0-140">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="d46c0-140">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="d46c0-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d46c0-141">-LiteralPath</span></span>

<span data-ttu-id="d46c0-142">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="d46c0-142">Specifies a path to one or more locations.</span></span> <span data-ttu-id="d46c0-143">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="d46c0-143">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="d46c0-144">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="d46c0-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="d46c0-145">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="d46c0-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="d46c0-146">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="d46c0-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="d46c0-147">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="d46c0-147">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="d46c0-148">-Name</span><span class="sxs-lookup"><span data-stu-id="d46c0-148">-Name</span></span>

<span data-ttu-id="d46c0-149">Especifica o nome da propriedade a ser copiada.</span><span class="sxs-lookup"><span data-stu-id="d46c0-149">Specifies the name of the property to be copied.</span></span>

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

### <span data-ttu-id="d46c0-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d46c0-150">-PassThru</span></span>

<span data-ttu-id="d46c0-151">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="d46c0-151">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="d46c0-152">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="d46c0-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="d46c0-153">-Path</span><span class="sxs-lookup"><span data-stu-id="d46c0-153">-Path</span></span>

<span data-ttu-id="d46c0-154">Especifica, como uma matriz de cadeia de caracteres, o caminho para a propriedade a ser copiada.</span><span class="sxs-lookup"><span data-stu-id="d46c0-154">Specifies, as a string array, the path to the property to be copied.</span></span>
<span data-ttu-id="d46c0-155">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="d46c0-155">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="d46c0-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d46c0-156">-Confirm</span></span>

<span data-ttu-id="d46c0-157">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d46c0-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d46c0-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d46c0-158">-WhatIf</span></span>

<span data-ttu-id="d46c0-159">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="d46c0-159">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d46c0-160">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="d46c0-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d46c0-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d46c0-161">CommonParameters</span></span>

<span data-ttu-id="d46c0-162">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="d46c0-162">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="d46c0-163">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d46c0-163">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d46c0-164">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d46c0-164">INPUTS</span></span>

### <span data-ttu-id="d46c0-165">System.String</span><span class="sxs-lookup"><span data-stu-id="d46c0-165">System.String</span></span>

<span data-ttu-id="d46c0-166">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d46c0-166">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="d46c0-167">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d46c0-167">OUTPUTS</span></span>

### <span data-ttu-id="d46c0-168">Nenhum ou System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="d46c0-168">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="d46c0-169">Quando você usa o parâmetro **PassThru** , esse cmdlet gera um **PSCustomObject** que representa a propriedade de item copiada.</span><span class="sxs-lookup"><span data-stu-id="d46c0-169">When you use the **Passthru** parameter, this cmdlet generates a **PsCustomObject** representing the copied item property.</span></span> <span data-ttu-id="d46c0-170">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="d46c0-170">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d46c0-171">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d46c0-171">NOTES</span></span>

<span data-ttu-id="d46c0-172">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="d46c0-172">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="d46c0-173">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="d46c0-173">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="d46c0-174">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d46c0-174">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="d46c0-175">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d46c0-175">RELATED LINKS</span></span>

[<span data-ttu-id="d46c0-176">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d46c0-176">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="d46c0-177">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d46c0-177">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="d46c0-178">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d46c0-178">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="d46c0-179">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d46c0-179">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="d46c0-180">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d46c0-180">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="d46c0-181">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d46c0-181">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="d46c0-182">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="d46c0-182">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="d46c0-183">about_Providers</span><span class="sxs-lookup"><span data-stu-id="d46c0-183">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

