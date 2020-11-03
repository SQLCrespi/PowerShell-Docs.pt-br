---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-itemproperty?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ItemProperty
ms.openlocfilehash: c5be0006d5f51e3a06868c497ac53e1a507d5f3e
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192810"
---
# <span data-ttu-id="73387-103">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73387-103">Move-ItemProperty</span></span>

## <span data-ttu-id="73387-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="73387-104">Synopsis</span></span>
<span data-ttu-id="73387-105">Move uma propriedade de um local para outro.</span><span class="sxs-lookup"><span data-stu-id="73387-105">Moves a property from one location to another.</span></span>

## <span data-ttu-id="73387-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="73387-106">SYNTAX</span></span>

### <span data-ttu-id="73387-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="73387-107">Path (Default)</span></span>

```
Move-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="73387-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="73387-108">LiteralPath</span></span>

```
Move-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="73387-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="73387-109">Description</span></span>

<span data-ttu-id="73387-110">O `Move-ItemProperty` cmdlet Move uma propriedade de um item de um item para outro item.</span><span class="sxs-lookup"><span data-stu-id="73387-110">The `Move-ItemProperty` cmdlet moves a property of an item from one item to another item.</span></span>
<span data-ttu-id="73387-111">Por exemplo, ele pode mover uma entrada de registro de uma chave do registro para outra chave do registro.</span><span class="sxs-lookup"><span data-stu-id="73387-111">For instance, it can move a registry entry from one registry key to another registry key.</span></span>
<span data-ttu-id="73387-112">Quando você move uma propriedade de um item, ela é adicionada ao novo local e excluída de seu local original.</span><span class="sxs-lookup"><span data-stu-id="73387-112">When you move an item property, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="73387-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="73387-113">EXAMPLES</span></span>

### <span data-ttu-id="73387-114">Exemplo 1: mover um valor de registro e seus dados para outra chave</span><span class="sxs-lookup"><span data-stu-id="73387-114">Example 1: Move a registry value and its data to another key</span></span>

<span data-ttu-id="73387-115">Esse comando move o valor do registro de versão e seus dados da subchave "MyApp" para a subchave NewApp da `HKLM\Software\MyCompany` chave do registro.</span><span class="sxs-lookup"><span data-stu-id="73387-115">This command moves the Version registry value, and its data, from the "MyApp" subkey to the NewApp subkey of the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Move-ItemProperty "HKLM:\Software\MyCompany\MyApp" -Name "Version" -Destination "HKLM:\Software\MyCompany\NewApp"
```

## <span data-ttu-id="73387-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="73387-116">PARAMETERS</span></span>

### <span data-ttu-id="73387-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="73387-117">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="73387-118">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73387-118">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="73387-119">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="73387-119">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="73387-120">-Destino</span><span class="sxs-lookup"><span data-stu-id="73387-120">-Destination</span></span>

<span data-ttu-id="73387-121">Especifica o caminho para o local de destino.</span><span class="sxs-lookup"><span data-stu-id="73387-121">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="73387-122">-Excluir</span><span class="sxs-lookup"><span data-stu-id="73387-122">-Exclude</span></span>

<span data-ttu-id="73387-123">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="73387-123">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="73387-124">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="73387-124">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="73387-125">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="73387-125">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="73387-126">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="73387-126">Wildcard characters are permitted.</span></span> <span data-ttu-id="73387-127">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="73387-127">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="73387-128">-Filter</span><span class="sxs-lookup"><span data-stu-id="73387-128">-Filter</span></span>

<span data-ttu-id="73387-129">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="73387-129">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="73387-130">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="73387-130">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="73387-131">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="73387-131">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="73387-132">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="73387-132">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="73387-133">-Force</span><span class="sxs-lookup"><span data-stu-id="73387-133">-Force</span></span>

<span data-ttu-id="73387-134">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="73387-134">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="73387-135">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="73387-135">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="73387-136">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="73387-136">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="73387-137">-Incluir</span><span class="sxs-lookup"><span data-stu-id="73387-137">-Include</span></span>

<span data-ttu-id="73387-138">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="73387-138">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="73387-139">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="73387-139">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="73387-140">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="73387-140">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="73387-141">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="73387-141">Wildcard characters are permitted.</span></span> <span data-ttu-id="73387-142">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="73387-142">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="73387-143">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="73387-143">-LiteralPath</span></span>

<span data-ttu-id="73387-144">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="73387-144">Specifies a path to one or more locations.</span></span> <span data-ttu-id="73387-145">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="73387-145">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="73387-146">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="73387-146">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="73387-147">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="73387-147">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="73387-148">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="73387-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="73387-149">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="73387-149">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="73387-150">-Name</span><span class="sxs-lookup"><span data-stu-id="73387-150">-Name</span></span>

<span data-ttu-id="73387-151">Especifica o nome da propriedade a ser movida.</span><span class="sxs-lookup"><span data-stu-id="73387-151">Specifies the name of the property to be moved.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="73387-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="73387-152">-PassThru</span></span>

<span data-ttu-id="73387-153">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="73387-153">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="73387-154">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="73387-154">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="73387-155">-Path</span><span class="sxs-lookup"><span data-stu-id="73387-155">-Path</span></span>

<span data-ttu-id="73387-156">Especifica o caminho para o local atual da propriedade.</span><span class="sxs-lookup"><span data-stu-id="73387-156">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="73387-157">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="73387-157">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="73387-158">-Confirm</span><span class="sxs-lookup"><span data-stu-id="73387-158">-Confirm</span></span>

<span data-ttu-id="73387-159">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="73387-159">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="73387-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="73387-160">-WhatIf</span></span>

<span data-ttu-id="73387-161">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="73387-161">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="73387-162">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="73387-162">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="73387-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="73387-163">CommonParameters</span></span>

<span data-ttu-id="73387-164">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="73387-164">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="73387-165">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="73387-165">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="73387-166">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="73387-166">INPUTS</span></span>

### <span data-ttu-id="73387-167">System.String</span><span class="sxs-lookup"><span data-stu-id="73387-167">System.String</span></span>

<span data-ttu-id="73387-168">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="73387-168">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="73387-169">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="73387-169">OUTPUTS</span></span>

### <span data-ttu-id="73387-170">Nenhum ou System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="73387-170">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="73387-171">Quando você usa o parâmetro **PassThru** , esse cmdlet gera um **PSCustomObject** que representa a propriedade item movido.</span><span class="sxs-lookup"><span data-stu-id="73387-171">When you use the **PassThru** parameter, this cmdlet generates a **PSCustomObject** representing the moved item property.</span></span> <span data-ttu-id="73387-172">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="73387-172">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="73387-173">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="73387-173">NOTES</span></span>

<span data-ttu-id="73387-174">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="73387-174">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="73387-175">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="73387-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="73387-176">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="73387-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="73387-177">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="73387-177">RELATED LINKS</span></span>

[<span data-ttu-id="73387-178">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73387-178">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="73387-179">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73387-179">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="73387-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73387-180">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="73387-181">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73387-181">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="73387-182">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73387-182">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="73387-183">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73387-183">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="73387-184">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73387-184">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="73387-185">about_Providers</span><span class="sxs-lookup"><span data-stu-id="73387-185">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
