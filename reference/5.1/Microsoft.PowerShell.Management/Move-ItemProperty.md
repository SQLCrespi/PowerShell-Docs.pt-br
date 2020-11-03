---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ItemProperty
ms.openlocfilehash: 4cf883964e1ff86487bf5abca8789af62b274c8a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193972"
---
# <span data-ttu-id="90cc3-103">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="90cc3-103">Move-ItemProperty</span></span>

## <span data-ttu-id="90cc3-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="90cc3-104">Synopsis</span></span>
<span data-ttu-id="90cc3-105">Move uma propriedade de um local para outro.</span><span class="sxs-lookup"><span data-stu-id="90cc3-105">Moves a property from one location to another.</span></span>

## <span data-ttu-id="90cc3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="90cc3-106">SYNTAX</span></span>

### <span data-ttu-id="90cc3-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="90cc3-107">Path (Default)</span></span>

```
Move-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="90cc3-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="90cc3-108">LiteralPath</span></span>

```
Move-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="90cc3-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="90cc3-109">Description</span></span>

<span data-ttu-id="90cc3-110">O `Move-ItemProperty` cmdlet Move uma propriedade de um item de um item para outro item.</span><span class="sxs-lookup"><span data-stu-id="90cc3-110">The `Move-ItemProperty` cmdlet moves a property of an item from one item to another item.</span></span>
<span data-ttu-id="90cc3-111">Por exemplo, ele pode mover uma entrada de registro de uma chave do registro para outra chave do registro.</span><span class="sxs-lookup"><span data-stu-id="90cc3-111">For instance, it can move a registry entry from one registry key to another registry key.</span></span>
<span data-ttu-id="90cc3-112">Quando você move uma propriedade de um item, ela é adicionada ao novo local e excluída de seu local original.</span><span class="sxs-lookup"><span data-stu-id="90cc3-112">When you move an item property, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="90cc3-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="90cc3-113">EXAMPLES</span></span>

### <span data-ttu-id="90cc3-114">Exemplo 1: mover um valor de registro e seus dados para outra chave</span><span class="sxs-lookup"><span data-stu-id="90cc3-114">Example 1: Move a registry value and its data to another key</span></span>

<span data-ttu-id="90cc3-115">Esse comando move o valor do registro de versão e seus dados da subchave "MyApp" para a subchave NewApp da `HKLM\Software\MyCompany` chave do registro.</span><span class="sxs-lookup"><span data-stu-id="90cc3-115">This command moves the Version registry value, and its data, from the "MyApp" subkey to the NewApp subkey of the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Move-ItemProperty "HKLM:\Software\MyCompany\MyApp" -Name "Version" -Destination "HKLM:\Software\MyCompany\NewApp"
```

## <span data-ttu-id="90cc3-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="90cc3-116">PARAMETERS</span></span>

### <span data-ttu-id="90cc3-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="90cc3-117">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="90cc3-118">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90cc3-118">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="90cc3-119">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="90cc3-119">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="90cc3-120">-Destino</span><span class="sxs-lookup"><span data-stu-id="90cc3-120">-Destination</span></span>

<span data-ttu-id="90cc3-121">Especifica o caminho para o local de destino.</span><span class="sxs-lookup"><span data-stu-id="90cc3-121">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="90cc3-122">-Excluir</span><span class="sxs-lookup"><span data-stu-id="90cc3-122">-Exclude</span></span>

<span data-ttu-id="90cc3-123">Especifica, como uma matriz de cadeia de caracteres, uma propriedade ou propriedade que esse cmdlet exclui da operação.</span><span class="sxs-lookup"><span data-stu-id="90cc3-123">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="90cc3-124">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="90cc3-124">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="90cc3-125">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="90cc3-125">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="90cc3-126">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="90cc3-126">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="90cc3-127">-Filter</span><span class="sxs-lookup"><span data-stu-id="90cc3-127">-Filter</span></span>

<span data-ttu-id="90cc3-128">Especifica um filtro no formato ou idioma do provedor.</span><span class="sxs-lookup"><span data-stu-id="90cc3-128">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="90cc3-129">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="90cc3-129">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="90cc3-130">A sintaxe do filtro, incluindo o uso de caracteres curinga, depende do provedor.</span><span class="sxs-lookup"><span data-stu-id="90cc3-130">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="90cc3-131">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="90cc3-131">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="90cc3-132">-Force</span><span class="sxs-lookup"><span data-stu-id="90cc3-132">-Force</span></span>

<span data-ttu-id="90cc3-133">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="90cc3-133">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="90cc3-134">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="90cc3-134">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="90cc3-135">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="90cc3-135">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="90cc3-136">-Incluir</span><span class="sxs-lookup"><span data-stu-id="90cc3-136">-Include</span></span>

<span data-ttu-id="90cc3-137">Especifica, como uma matriz de cadeia de caracteres, uma propriedade ou propriedade que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="90cc3-137">Specifies, as a string array, a property or property that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="90cc3-138">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="90cc3-138">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="90cc3-139">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="90cc3-139">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="90cc3-140">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="90cc3-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="90cc3-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="90cc3-141">-LiteralPath</span></span>

<span data-ttu-id="90cc3-142">Especifica o caminho para o local atual da propriedade.</span><span class="sxs-lookup"><span data-stu-id="90cc3-142">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="90cc3-143">Ao contrário do parâmetro **Path** , o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="90cc3-143">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="90cc3-144">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="90cc3-144">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="90cc3-145">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="90cc3-145">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="90cc3-146">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="90cc3-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="90cc3-147">-Name</span><span class="sxs-lookup"><span data-stu-id="90cc3-147">-Name</span></span>

<span data-ttu-id="90cc3-148">Especifica o nome da propriedade a ser movida.</span><span class="sxs-lookup"><span data-stu-id="90cc3-148">Specifies the name of the property to be moved.</span></span>

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

### <span data-ttu-id="90cc3-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="90cc3-149">-PassThru</span></span>

<span data-ttu-id="90cc3-150">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="90cc3-150">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="90cc3-151">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="90cc3-151">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="90cc3-152">-Path</span><span class="sxs-lookup"><span data-stu-id="90cc3-152">-Path</span></span>

<span data-ttu-id="90cc3-153">Especifica o caminho para o local atual da propriedade.</span><span class="sxs-lookup"><span data-stu-id="90cc3-153">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="90cc3-154">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="90cc3-154">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="90cc3-155">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="90cc3-155">-UseTransaction</span></span>

<span data-ttu-id="90cc3-156">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="90cc3-156">Includes the command in the active transaction.</span></span>
<span data-ttu-id="90cc3-157">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="90cc3-157">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="90cc3-158">Para obter mais informações, consulte about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="90cc3-158">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="90cc3-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="90cc3-159">-Confirm</span></span>

<span data-ttu-id="90cc3-160">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="90cc3-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="90cc3-161">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="90cc3-161">-WhatIf</span></span>

<span data-ttu-id="90cc3-162">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="90cc3-162">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="90cc3-163">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="90cc3-163">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="90cc3-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="90cc3-164">CommonParameters</span></span>

<span data-ttu-id="90cc3-165">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="90cc3-165">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="90cc3-166">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="90cc3-166">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="90cc3-167">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="90cc3-167">INPUTS</span></span>

### <span data-ttu-id="90cc3-168">System.String</span><span class="sxs-lookup"><span data-stu-id="90cc3-168">System.String</span></span>

<span data-ttu-id="90cc3-169">É possível canalizar uma cadeia de caracteres que contém um caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="90cc3-169">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="90cc3-170">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="90cc3-170">OUTPUTS</span></span>

### <span data-ttu-id="90cc3-171">Nenhum ou System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="90cc3-171">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="90cc3-172">Quando você usa o parâmetro **PassThru** , esse cmdlet gera um **PSCustomObject** que representa a propriedade item movido.</span><span class="sxs-lookup"><span data-stu-id="90cc3-172">When you use the **PassThru** parameter, this cmdlet generates a **PSCustomObject** representing the moved item property.</span></span>
<span data-ttu-id="90cc3-173">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="90cc3-173">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="90cc3-174">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="90cc3-174">NOTES</span></span>

<span data-ttu-id="90cc3-175">Esse cmdlet foi projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="90cc3-175">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="90cc3-176">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="90cc3-176">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="90cc3-177">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="90cc3-177">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="90cc3-178">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="90cc3-178">RELATED LINKS</span></span>

[<span data-ttu-id="90cc3-179">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="90cc3-179">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="90cc3-180">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="90cc3-180">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="90cc3-181">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="90cc3-181">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="90cc3-182">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="90cc3-182">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="90cc3-183">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="90cc3-183">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="90cc3-184">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="90cc3-184">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="90cc3-185">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="90cc3-185">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="90cc3-186">about_Providers</span><span class="sxs-lookup"><span data-stu-id="90cc3-186">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
