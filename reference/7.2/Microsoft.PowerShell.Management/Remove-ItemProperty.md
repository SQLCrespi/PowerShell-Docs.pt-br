---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ItemProperty
ms.openlocfilehash: 870d8e9797ff2cfce14034706f704c0e1c954fc2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603562"
---
# <span data-ttu-id="b1bb5-102">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1bb5-102">Remove-ItemProperty</span></span>

## <span data-ttu-id="b1bb5-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b1bb5-103">SYNOPSIS</span></span>
<span data-ttu-id="b1bb5-104">Exclui a propriedade e seu valor de um item.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-104">Deletes the property and its value from an item.</span></span>

## <span data-ttu-id="b1bb5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b1bb5-105">SYNTAX</span></span>

### <span data-ttu-id="b1bb5-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="b1bb5-106">Path (Default)</span></span>

```
Remove-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b1bb5-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b1bb5-107">LiteralPath</span></span>

```
Remove-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b1bb5-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b1bb5-108">DESCRIPTION</span></span>

<span data-ttu-id="b1bb5-109">O `Remove-ItemProperty` cmdlet exclui uma propriedade e seu valor de um item.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-109">The `Remove-ItemProperty` cmdlet deletes a property and its value from an item.</span></span>
<span data-ttu-id="b1bb5-110">Você pode usá-lo para excluir os valores do registro e os dados que eles armazenam.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-110">You can use it to delete registry values and the data that they store.</span></span>

## <span data-ttu-id="b1bb5-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b1bb5-111">EXAMPLES</span></span>

### <span data-ttu-id="b1bb5-112">Exemplo 1: excluir um valor de registro</span><span class="sxs-lookup"><span data-stu-id="b1bb5-112">Example 1: Delete a registry value</span></span>

<span data-ttu-id="b1bb5-113">Esse comando exclui o valor do registro "SmpProperty" e seus dados, da subchave "SmpApplication" da `HKEY_LOCAL_MACHINE\Software` chave do registro.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-113">This command deletes the "SmpProperty" registry value, and its data, from the "SmpApplication" subkey of the `HKEY_LOCAL_MACHINE\Software` registry key.</span></span>

```powershell
Remove-ItemProperty -Path "HKLM:\Software\SmpApplication" -Name "SmpProperty"
```

<span data-ttu-id="b1bb5-114">Como o comando é emitido de uma unidade do sistema de arquivos ( `PS C:\>` ), ele inclui o caminho totalmente qualificado da subchave "SmpApplication", incluindo a unidade, `HKLM:` e a chave "software".</span><span class="sxs-lookup"><span data-stu-id="b1bb5-114">Because the command is issued from a file system drive (`PS C:\>`), it includes the fully qualified path of the "SmpApplication" subkey, including the drive, `HKLM:`, and the "Software" key.</span></span>

### <span data-ttu-id="b1bb5-115">Exemplo 2: excluir um valor de registro do local HKCU</span><span class="sxs-lookup"><span data-stu-id="b1bb5-115">Example 2: Delete a registry value from the HKCU location</span></span>

<span data-ttu-id="b1bb5-116">Esses comandos excluem o valor do registro "Options" e seus dados, da subchave "MyApp" de "HKEY_CURRENT_USER\Software\MyCompany".</span><span class="sxs-lookup"><span data-stu-id="b1bb5-116">These commands delete the "Options" registry value, and its data, from the "MyApp" subkey of "HKEY_CURRENT_USER\Software\MyCompany".</span></span>

```
PS C:\> Set-Location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> Remove-ItemProperty -Path . -Name "Options" -Confirm
```

<span data-ttu-id="b1bb5-117">O primeiro comando usa o `Set-Location` cmdlet para alterar o local atual para a unidade de **HKEY_CURRENT_USER** ( `HKCU:` ) e a `Software\MyCompany\MyApp` subchave.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-117">The first command uses the `Set-Location` cmdlet to change the current location to the **HKEY_CURRENT_USER** drive (`HKCU:`) and the `Software\MyCompany\MyApp` subkey.</span></span>

<span data-ttu-id="b1bb5-118">O segundo comando usa `Remove-ItemProperty` para remover o valor do registro "Options" e seus dados da subchave "MyApp".</span><span class="sxs-lookup"><span data-stu-id="b1bb5-118">The second command uses `Remove-ItemProperty` to remove the "Options" registry value, and its data, from the "MyApp" subkey.</span></span> <span data-ttu-id="b1bb5-119">Como o **caminho** é necessário, o comando usa um ponto ( `.` ) para indicar o local atual.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-119">Because **Path** is required, the command uses a dot (`.`) to indicate the current location.</span></span> <span data-ttu-id="b1bb5-120">O parâmetro **Confirm** solicita um prompt do usuário antes de excluir o valor.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-120">The **Confirm** parameter requests a user prompt before deleting the value.</span></span>

### <span data-ttu-id="b1bb5-121">Exemplo 3: remover um valor de registro usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="b1bb5-121">Example 3: Remove a registry value by using the pipeline</span></span>

<span data-ttu-id="b1bb5-122">Esse comando exclui o valor do registro "NoOfEmployees" e seus dados da `HKLM\Software\MyCompany` chave do registro.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-122">This command deletes the "NoOfEmployees" registry value, and its data, from the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany | Remove-ItemProperty -Name NoOfEmployees
```

<span data-ttu-id="b1bb5-123">O comando usa o `Get-Item` cmdlet para obter um item que representa a chave do registro.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-123">The command uses the `Get-Item` cmdlet to get an item that represents the registry key.</span></span>
<span data-ttu-id="b1bb5-124">Ele usa um operador de pipeline ( `|` ) para enviar o objeto para `Remove-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="b1bb5-124">It uses a pipeline operator (`|`) to send the object to `Remove-ItemProperty`.</span></span>
<span data-ttu-id="b1bb5-125">Em seguida, ele usa o parâmetro **Name** de `Remove-ItemProperty` para especificar o nome do valor do registro.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-125">Then, it uses the **Name** parameter of `Remove-ItemProperty` to specify the name of the registry value.</span></span>

## <span data-ttu-id="b1bb5-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b1bb5-126">PARAMETERS</span></span>

### <span data-ttu-id="b1bb5-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="b1bb5-127">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="b1bb5-128">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-128">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="b1bb5-129">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="b1bb5-129">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="b1bb5-130">-Excluir</span><span class="sxs-lookup"><span data-stu-id="b1bb5-130">-Exclude</span></span>

<span data-ttu-id="b1bb5-131">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-131">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="b1bb5-132">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-132">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="b1bb5-133">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="b1bb5-133">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="b1bb5-134">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-134">Wildcard characters are permitted.</span></span> <span data-ttu-id="b1bb5-135">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-135">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="b1bb5-136">-Filter</span><span class="sxs-lookup"><span data-stu-id="b1bb5-136">-Filter</span></span>

<span data-ttu-id="b1bb5-137">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="b1bb5-137">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="b1bb5-138">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-138">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="b1bb5-139">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="b1bb5-139">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="b1bb5-140">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-140">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="b1bb5-141">-Force</span><span class="sxs-lookup"><span data-stu-id="b1bb5-141">-Force</span></span>

<span data-ttu-id="b1bb5-142">Força o cmdlet a remover uma propriedade de um objeto que, de outra forma, não pode ser acessado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-142">Forces the cmdlet to remove a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="b1bb5-143">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-143">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="b1bb5-144">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b1bb5-144">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="b1bb5-145">-Incluir</span><span class="sxs-lookup"><span data-stu-id="b1bb5-145">-Include</span></span>

<span data-ttu-id="b1bb5-146">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-146">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="b1bb5-147">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-147">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="b1bb5-148">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="b1bb5-148">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="b1bb5-149">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-149">Wildcard characters are permitted.</span></span> <span data-ttu-id="b1bb5-150">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-150">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="b1bb5-151">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b1bb5-151">-LiteralPath</span></span>

<span data-ttu-id="b1bb5-152">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-152">Specifies a path to one or more locations.</span></span> <span data-ttu-id="b1bb5-153">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-153">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="b1bb5-154">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-154">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="b1bb5-155">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-155">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="b1bb5-156">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-156">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="b1bb5-157">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="b1bb5-157">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="b1bb5-158">-Name</span><span class="sxs-lookup"><span data-stu-id="b1bb5-158">-Name</span></span>

<span data-ttu-id="b1bb5-159">Especifica os nomes das propriedades a serem removidas.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-159">Specifies the names of the properties to remove.</span></span>
<span data-ttu-id="b1bb5-160">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-160">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="b1bb5-161">-Path</span><span class="sxs-lookup"><span data-stu-id="b1bb5-161">-Path</span></span>

<span data-ttu-id="b1bb5-162">Especifica o caminho do item cujas propriedades estão sendo removidas.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-162">Specifies the path of the item whose properties are being removed.</span></span>
<span data-ttu-id="b1bb5-163">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-163">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="b1bb5-164">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b1bb5-164">-Confirm</span></span>

<span data-ttu-id="b1bb5-165">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-165">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b1bb5-166">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b1bb5-166">-WhatIf</span></span>

<span data-ttu-id="b1bb5-167">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-167">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b1bb5-168">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-168">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b1bb5-169">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b1bb5-169">CommonParameters</span></span>

<span data-ttu-id="b1bb5-170">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="b1bb5-170">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="b1bb5-171">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b1bb5-171">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b1bb5-172">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b1bb5-172">INPUTS</span></span>

### <span data-ttu-id="b1bb5-173">System.String</span><span class="sxs-lookup"><span data-stu-id="b1bb5-173">System.String</span></span>

<span data-ttu-id="b1bb5-174">É possível canalizar uma cadeia de caracteres que contém um caminho, mas não um caminho literal, para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-174">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="b1bb5-175">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b1bb5-175">OUTPUTS</span></span>

### <span data-ttu-id="b1bb5-176">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b1bb5-176">None</span></span>

<span data-ttu-id="b1bb5-177">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-177">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="b1bb5-178">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b1bb5-178">NOTES</span></span>

- <span data-ttu-id="b1bb5-179">No provedor do registro do PowerShell, os valores do registro são considerados propriedades de uma chave ou subchave do registro.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-179">In the PowerShell Registry provider, registry values are considered to be properties of a registry key or subkey.</span></span> <span data-ttu-id="b1bb5-180">Você pode usar os cmdlets **ItemProperty** para gerenciar esses valores.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-180">You can use the **ItemProperty** cmdlets to manage these values.</span></span>
- <span data-ttu-id="b1bb5-181">`Remove-ItemProperty` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="b1bb5-181">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="b1bb5-182">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="b1bb5-182">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="b1bb5-183">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b1bb5-183">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="b1bb5-184">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b1bb5-184">RELATED LINKS</span></span>

[<span data-ttu-id="b1bb5-185">Get-Item</span><span class="sxs-lookup"><span data-stu-id="b1bb5-185">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="b1bb5-186">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1bb5-186">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="b1bb5-187">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1bb5-187">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="b1bb5-188">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1bb5-188">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="b1bb5-189">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1bb5-189">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="b1bb5-190">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1bb5-190">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="b1bb5-191">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="b1bb5-191">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="b1bb5-192">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1bb5-192">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="b1bb5-193">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b1bb5-193">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="b1bb5-194">Set-Location</span><span class="sxs-lookup"><span data-stu-id="b1bb5-194">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="b1bb5-195">about_Providers</span><span class="sxs-lookup"><span data-stu-id="b1bb5-195">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

