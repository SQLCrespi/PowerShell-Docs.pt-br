---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ItemProperty
ms.openlocfilehash: 9ae9c0e7c17a6a63da5487cce138ddce129b975b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193953"
---
# <span data-ttu-id="700b5-103">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="700b5-103">Remove-ItemProperty</span></span>

## <span data-ttu-id="700b5-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="700b5-104">SYNOPSIS</span></span>
<span data-ttu-id="700b5-105">Exclui a propriedade e seu valor de um item.</span><span class="sxs-lookup"><span data-stu-id="700b5-105">Deletes the property and its value from an item.</span></span>

## <span data-ttu-id="700b5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="700b5-106">SYNTAX</span></span>

### <span data-ttu-id="700b5-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="700b5-107">Path (Default)</span></span>

```
Remove-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="700b5-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="700b5-108">LiteralPath</span></span>

```
Remove-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="700b5-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="700b5-109">DESCRIPTION</span></span>

<span data-ttu-id="700b5-110">O `Remove-ItemProperty` cmdlet exclui uma propriedade e seu valor de um item.</span><span class="sxs-lookup"><span data-stu-id="700b5-110">The `Remove-ItemProperty` cmdlet deletes a property and its value from an item.</span></span>
<span data-ttu-id="700b5-111">Você pode usá-lo para excluir os valores do registro e os dados que eles armazenam.</span><span class="sxs-lookup"><span data-stu-id="700b5-111">You can use it to delete registry values and the data that they store.</span></span>

## <span data-ttu-id="700b5-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="700b5-112">EXAMPLES</span></span>

### <span data-ttu-id="700b5-113">Exemplo 1: excluir um valor de registro</span><span class="sxs-lookup"><span data-stu-id="700b5-113">Example 1: Delete a registry value</span></span>

<span data-ttu-id="700b5-114">Esse comando exclui o valor do registro "SmpProperty" e seus dados, da subchave "SmpApplication" da chave do registro "HKEY_LOCAL_MACHINE\Software".</span><span class="sxs-lookup"><span data-stu-id="700b5-114">This command deletes the "SmpProperty" registry value, and its data, from the "SmpApplication" subkey of the "HKEY_LOCAL_MACHINE\Software" registry key.</span></span>

<span data-ttu-id="700b5-115">Como o comando é emitido de uma unidade do sistema de arquivos ( `PS C:\>` ), ele inclui o caminho totalmente qualificado da subchave "SmpApplication", incluindo a unidade, `HKLM:` e a chave "software".</span><span class="sxs-lookup"><span data-stu-id="700b5-115">Because the command is issued from a file system drive (`PS C:\>`), it includes the fully qualified path of the "SmpApplication" subkey, including the drive, `HKLM:`, and the "Software" key.</span></span>

<span data-ttu-id="700b5-116">Ele usa o parâmetro **Name** para identificar o valor do registro que está sendo excluído.</span><span class="sxs-lookup"><span data-stu-id="700b5-116">It uses the **Name** parameter to identify the registry value that is being deleted.</span></span>

```powershell
Remove-ItemProperty -Path "HKLM:\Software\SmpApplication" -Name "SmpProperty"
```

### <span data-ttu-id="700b5-117">Exemplo 2: excluir um valor de registro do local HKCU</span><span class="sxs-lookup"><span data-stu-id="700b5-117">Example 2: Delete a registry value from the HKCU location</span></span>

<span data-ttu-id="700b5-118">Esses comandos excluem o valor do registro "Options" e seus dados, da subchave "MyApp" de "HKEY_CURRENT_USER\Software\MyCompany".</span><span class="sxs-lookup"><span data-stu-id="700b5-118">These commands delete the "Options" registry value, and its data, from the "MyApp" subkey of "HKEY_CURRENT_USER\Software\MyCompany".</span></span>

<span data-ttu-id="700b5-119">O primeiro comando usa o `Set-Location` cmdlet para alterar o local atual para a unidade de **HKEY_CURRENT_USER** ( `HKCU:` ) e a subchave "Software\MyCompany\MyApp.".</span><span class="sxs-lookup"><span data-stu-id="700b5-119">The first command uses the `Set-Location` cmdlet to change the current location to the **HKEY_CURRENT_USER** drive (`HKCU:`) and the "Software\MyCompany\MyApp" subkey.</span></span>

<span data-ttu-id="700b5-120">O segundo comando usa `Remove-ItemProperty` para remover o valor do registro "Options" e seus dados da subchave "MyApp".</span><span class="sxs-lookup"><span data-stu-id="700b5-120">The second command uses `Remove-ItemProperty` to remove the "Options" registry value, and its data, from the "MyApp" subkey.</span></span>
<span data-ttu-id="700b5-121">Como o **caminho** é necessário, o comando usa um ponto ('. ') para indicar o local atual.</span><span class="sxs-lookup"><span data-stu-id="700b5-121">Because **Path** is required, the command uses a dot ('.') to indicate the current location.</span></span>
<span data-ttu-id="700b5-122">Ele usa **nome** para especificar qual valor de registro deve ser excluído.</span><span class="sxs-lookup"><span data-stu-id="700b5-122">It uses **Name** to specify which registry value to delete.</span></span>
<span data-ttu-id="700b5-123">Ele usa o parâmetro **Confirm** para solicitar um prompt do usuário antes de excluir o valor.</span><span class="sxs-lookup"><span data-stu-id="700b5-123">It uses the **Confirm** parameter to request a user prompt before deleting the value.</span></span>

```
PS C:\> Set-Location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> Remove-ItemProperty -Path . -Name "Options" -Confirm
```

### <span data-ttu-id="700b5-124">Exemplo 3: remover um valor de registro usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="700b5-124">Example 3: Remove a registry value by using the pipeline</span></span>

<span data-ttu-id="700b5-125">Esse comando exclui o valor do registro "NoOfEmployees" e seus dados da chave do registro "Hklm\software\mycompany.".</span><span class="sxs-lookup"><span data-stu-id="700b5-125">This command deletes the "NoOfEmployees" registry value, and its data, from the "HKLM\Software\MyCompany" registry key.</span></span>

<span data-ttu-id="700b5-126">O comando usa o `Get-Item` cmdlet para obter um item que representa a chave do registro.</span><span class="sxs-lookup"><span data-stu-id="700b5-126">The command uses the `Get-Item` cmdlet to get an item that represents the registry key.</span></span>
<span data-ttu-id="700b5-127">Ele usa um operador de pipeline ( `|` ) para enviar o objeto para `Remove-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="700b5-127">It uses a pipeline operator (`|`) to send the object to `Remove-ItemProperty`.</span></span>
<span data-ttu-id="700b5-128">Em seguida, ele usa o parâmetro **Name** de `Remove-ItemProperty` para especificar o nome do valor do registro.</span><span class="sxs-lookup"><span data-stu-id="700b5-128">Then, it uses the **Name** parameter of `Remove-ItemProperty` to specify the name of the registry value.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany | Remove-ItemProperty -Name NoOfEmployees
```

## <span data-ttu-id="700b5-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="700b5-129">PARAMETERS</span></span>

### <span data-ttu-id="700b5-130">-Credential</span><span class="sxs-lookup"><span data-stu-id="700b5-130">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="700b5-131">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="700b5-131">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="700b5-132">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="700b5-132">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="700b5-133">-Excluir</span><span class="sxs-lookup"><span data-stu-id="700b5-133">-Exclude</span></span>

<span data-ttu-id="700b5-134">Especifica os itens que esse cmdlet omite.</span><span class="sxs-lookup"><span data-stu-id="700b5-134">Specifies items that this cmdlet omits.</span></span>
<span data-ttu-id="700b5-135">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="700b5-135">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="700b5-136">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="700b5-136">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="700b5-137">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="700b5-137">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="700b5-138">-Filter</span><span class="sxs-lookup"><span data-stu-id="700b5-138">-Filter</span></span>

<span data-ttu-id="700b5-139">Especifica um filtro no formato ou idioma do provedor.</span><span class="sxs-lookup"><span data-stu-id="700b5-139">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="700b5-140">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="700b5-140">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="700b5-141">A sintaxe do filtro, incluindo o uso de caracteres curinga, depende do provedor.</span><span class="sxs-lookup"><span data-stu-id="700b5-141">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="700b5-142">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="700b5-142">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="700b5-143">-Force</span><span class="sxs-lookup"><span data-stu-id="700b5-143">-Force</span></span>

<span data-ttu-id="700b5-144">Força o cmdlet a remover uma propriedade de um objeto que, de outra forma, não pode ser acessado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="700b5-144">Forces the cmdlet to remove a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="700b5-145">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="700b5-145">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="700b5-146">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="700b5-146">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="700b5-147">-Incluir</span><span class="sxs-lookup"><span data-stu-id="700b5-147">-Include</span></span>

<span data-ttu-id="700b5-148">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="700b5-148">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="700b5-149">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="700b5-149">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="700b5-150">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="700b5-150">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="700b5-151">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="700b5-151">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="700b5-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="700b5-152">-LiteralPath</span></span>

<span data-ttu-id="700b5-153">Especifica o caminho para o local atual da propriedade.</span><span class="sxs-lookup"><span data-stu-id="700b5-153">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="700b5-154">Ao contrário do parâmetro **Path** , o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="700b5-154">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="700b5-155">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="700b5-155">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="700b5-156">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="700b5-156">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="700b5-157">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="700b5-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="700b5-158">-Name</span><span class="sxs-lookup"><span data-stu-id="700b5-158">-Name</span></span>

<span data-ttu-id="700b5-159">Especifica os nomes das propriedades a serem removidas.</span><span class="sxs-lookup"><span data-stu-id="700b5-159">Specifies the names of the properties to remove.</span></span>
<span data-ttu-id="700b5-160">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="700b5-160">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="700b5-161">-Path</span><span class="sxs-lookup"><span data-stu-id="700b5-161">-Path</span></span>

<span data-ttu-id="700b5-162">Especifica o caminho do item cujas propriedades estão sendo removidas.</span><span class="sxs-lookup"><span data-stu-id="700b5-162">Specifies the path of the item whose properties are being removed.</span></span>
<span data-ttu-id="700b5-163">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="700b5-163">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="700b5-164">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="700b5-164">-UseTransaction</span></span>

<span data-ttu-id="700b5-165">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="700b5-165">Includes the command in the active transaction.</span></span>
<span data-ttu-id="700b5-166">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="700b5-166">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="700b5-167">Para obter mais informações, consulte about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="700b5-167">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="700b5-168">-Confirm</span><span class="sxs-lookup"><span data-stu-id="700b5-168">-Confirm</span></span>

<span data-ttu-id="700b5-169">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="700b5-169">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="700b5-170">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="700b5-170">-WhatIf</span></span>

<span data-ttu-id="700b5-171">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="700b5-171">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="700b5-172">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="700b5-172">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="700b5-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="700b5-173">CommonParameters</span></span>

<span data-ttu-id="700b5-174">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="700b5-174">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="700b5-175">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="700b5-175">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="700b5-176">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="700b5-176">INPUTS</span></span>

### <span data-ttu-id="700b5-177">System.String</span><span class="sxs-lookup"><span data-stu-id="700b5-177">System.String</span></span>

<span data-ttu-id="700b5-178">É possível canalizar uma cadeia de caracteres que contém um caminho, mas não um caminho literal, para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="700b5-178">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="700b5-179">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="700b5-179">OUTPUTS</span></span>

### <span data-ttu-id="700b5-180">Nenhum</span><span class="sxs-lookup"><span data-stu-id="700b5-180">None</span></span>

<span data-ttu-id="700b5-181">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="700b5-181">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="700b5-182">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="700b5-182">NOTES</span></span>

<span data-ttu-id="700b5-183">No provedor do registro do PowerShell, os valores do registro são considerados propriedades de uma chave ou subchave do registro.</span><span class="sxs-lookup"><span data-stu-id="700b5-183">In the PowerShell Registry provider, registry values are considered to be properties of a registry key or subkey.</span></span> <span data-ttu-id="700b5-184">Você pode usar os cmdlets **ItemProperty** para gerenciar esses valores.</span><span class="sxs-lookup"><span data-stu-id="700b5-184">You can use the **ItemProperty** cmdlets to manage these values.</span></span>

<span data-ttu-id="700b5-185">`Remove-ItemProperty` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="700b5-185">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="700b5-186">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="700b5-186">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="700b5-187">Para obter mais informações, consulte about_Providers.</span><span class="sxs-lookup"><span data-stu-id="700b5-187">For more information, see about_Providers.</span></span>

## <span data-ttu-id="700b5-188">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="700b5-188">RELATED LINKS</span></span>

[<span data-ttu-id="700b5-189">Get-Item</span><span class="sxs-lookup"><span data-stu-id="700b5-189">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="700b5-190">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="700b5-190">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="700b5-191">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="700b5-191">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="700b5-192">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="700b5-192">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="700b5-193">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="700b5-193">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="700b5-194">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="700b5-194">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="700b5-195">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="700b5-195">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="700b5-196">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="700b5-196">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="700b5-197">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="700b5-197">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="700b5-198">about_Providers</span><span class="sxs-lookup"><span data-stu-id="700b5-198">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
