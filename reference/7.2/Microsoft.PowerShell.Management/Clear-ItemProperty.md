---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-ItemProperty
ms.openlocfilehash: fc454095f9610e8712af18bfe1558e275324cefe
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603552"
---
# <span data-ttu-id="0892e-102">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0892e-102">Clear-ItemProperty</span></span>

## <span data-ttu-id="0892e-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0892e-103">SYNOPSIS</span></span>
<span data-ttu-id="0892e-104">Limpa o valor de uma propriedade, mas não exclui a propriedade.</span><span class="sxs-lookup"><span data-stu-id="0892e-104">Clears the value of a property but does not delete the property.</span></span>

## <span data-ttu-id="0892e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0892e-105">SYNTAX</span></span>

### <span data-ttu-id="0892e-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="0892e-106">Path (Default)</span></span>

```
Clear-ItemProperty [-Path] <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0892e-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0892e-107">LiteralPath</span></span>

```
Clear-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0892e-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0892e-108">DESCRIPTION</span></span>

<span data-ttu-id="0892e-109">O `Clear-ItemProperty` cmdlet limpa o valor de uma propriedade, mas não exclui a propriedade.</span><span class="sxs-lookup"><span data-stu-id="0892e-109">The `Clear-ItemProperty` cmdlet clears the value of a property, but it does not delete the property.</span></span>
<span data-ttu-id="0892e-110">Você pode usar este cmdlet para excluir os dados de um valor do registro.</span><span class="sxs-lookup"><span data-stu-id="0892e-110">You can use this cmdlet to delete the data from a registry value.</span></span>

## <span data-ttu-id="0892e-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0892e-111">EXAMPLES</span></span>

### <span data-ttu-id="0892e-112">Exemplo 1: limpar o valor da chave do registro</span><span class="sxs-lookup"><span data-stu-id="0892e-112">Example 1: Clear the value of registry key</span></span>

<span data-ttu-id="0892e-113">Esse comando limpa os dados no valor do registro "Options" na subchave "MyApp" de `HKEY_LOCAL_MACHINE\Software\MyCompany` .</span><span class="sxs-lookup"><span data-stu-id="0892e-113">This command clears the data in the "Options" registry value in the "MyApp" subkey of `HKEY_LOCAL_MACHINE\Software\MyCompany`.</span></span>

```powershell
Clear-ItemProperty -Path "HKLM:\Software\MyCompany\MyApp" -Name "Options"
```

## <span data-ttu-id="0892e-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0892e-114">PARAMETERS</span></span>

### <span data-ttu-id="0892e-115">-Credential</span><span class="sxs-lookup"><span data-stu-id="0892e-115">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="0892e-116">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0892e-116">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="0892e-117">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="0892e-117">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="0892e-118">-Excluir</span><span class="sxs-lookup"><span data-stu-id="0892e-118">-Exclude</span></span>

<span data-ttu-id="0892e-119">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="0892e-119">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="0892e-120">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="0892e-120">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="0892e-121">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="0892e-121">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="0892e-122">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0892e-122">Wildcard characters are permitted.</span></span> <span data-ttu-id="0892e-123">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="0892e-123">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="0892e-124">-Filter</span><span class="sxs-lookup"><span data-stu-id="0892e-124">-Filter</span></span>

<span data-ttu-id="0892e-125">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="0892e-125">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="0892e-126">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="0892e-126">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="0892e-127">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="0892e-127">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="0892e-128">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="0892e-128">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="0892e-129">-Force</span><span class="sxs-lookup"><span data-stu-id="0892e-129">-Force</span></span>

<span data-ttu-id="0892e-130">Indica que esse cmdlet exclui Propriedades de itens que não podem ser acessados pelo usuário de outra forma.</span><span class="sxs-lookup"><span data-stu-id="0892e-130">Indicates that this cmdlet deletes properties from items that cannot otherwise be accessed by the user.</span></span> <span data-ttu-id="0892e-131">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="0892e-131">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="0892e-132">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="0892e-132">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="0892e-133">-Incluir</span><span class="sxs-lookup"><span data-stu-id="0892e-133">-Include</span></span>

<span data-ttu-id="0892e-134">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="0892e-134">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="0892e-135">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="0892e-135">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="0892e-136">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="0892e-136">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="0892e-137">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0892e-137">Wildcard characters are permitted.</span></span> <span data-ttu-id="0892e-138">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="0892e-138">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="0892e-139">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0892e-139">-LiteralPath</span></span>

<span data-ttu-id="0892e-140">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="0892e-140">Specifies a path to one or more locations.</span></span> <span data-ttu-id="0892e-141">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="0892e-141">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="0892e-142">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="0892e-142">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="0892e-143">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="0892e-143">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="0892e-144">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="0892e-144">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="0892e-145">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="0892e-145">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="0892e-146">-Name</span><span class="sxs-lookup"><span data-stu-id="0892e-146">-Name</span></span>

<span data-ttu-id="0892e-147">Especifica o nome da propriedade a ser apagada, como o nome de um valor do registro.</span><span class="sxs-lookup"><span data-stu-id="0892e-147">Specifies the name of the property to be cleared, such as the name of a registry value.</span></span>
<span data-ttu-id="0892e-148">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0892e-148">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="0892e-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="0892e-149">-PassThru</span></span>

<span data-ttu-id="0892e-150">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="0892e-150">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="0892e-151">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="0892e-151">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="0892e-152">-Path</span><span class="sxs-lookup"><span data-stu-id="0892e-152">-Path</span></span>

<span data-ttu-id="0892e-153">Especifica o caminho para as propriedades sendo apagadas.</span><span class="sxs-lookup"><span data-stu-id="0892e-153">Specifies the path to the property being cleared.</span></span>
<span data-ttu-id="0892e-154">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0892e-154">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0892e-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0892e-155">-Confirm</span></span>

<span data-ttu-id="0892e-156">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0892e-156">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0892e-157">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0892e-157">-WhatIf</span></span>

<span data-ttu-id="0892e-158">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="0892e-158">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0892e-159">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="0892e-159">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0892e-160">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0892e-160">CommonParameters</span></span>

<span data-ttu-id="0892e-161">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="0892e-161">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="0892e-162">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="0892e-162">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0892e-163">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0892e-163">INPUTS</span></span>

### <span data-ttu-id="0892e-164">System.String</span><span class="sxs-lookup"><span data-stu-id="0892e-164">System.String</span></span>

<span data-ttu-id="0892e-165">É possível canalizar uma cadeia de caracteres de caminho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0892e-165">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="0892e-166">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0892e-166">OUTPUTS</span></span>

### <span data-ttu-id="0892e-167">Nenhum ou System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="0892e-167">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="0892e-168">Quando você usa o parâmetro **PassThru** , o `Clear-ItemProperty` gera um objeto **PSCustomObject** que representa a propriedade item limpa.</span><span class="sxs-lookup"><span data-stu-id="0892e-168">When you use the **PassThru** parameter, `Clear-ItemProperty` generates a **PSCustomObject** object that represents the cleared item property.</span></span> <span data-ttu-id="0892e-169">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="0892e-169">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0892e-170">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0892e-170">NOTES</span></span>

- <span data-ttu-id="0892e-171">Você pode usar `Clear-ItemProperty` para excluir os dados em valores de registro sem excluir o valor.</span><span class="sxs-lookup"><span data-stu-id="0892e-171">You can use `Clear-ItemProperty` to delete the data in registry values without deleting the value.</span></span>
  <span data-ttu-id="0892e-172">Se o tipo de dados do valor for binários ou DWORD, limpar os dados definirá o valor como zero.</span><span class="sxs-lookup"><span data-stu-id="0892e-172">If the data type of the value is Binary or DWORD, clearing the data sets the value to zero.</span></span>
  <span data-ttu-id="0892e-173">Caso contrário, o valor ficará vazio.</span><span class="sxs-lookup"><span data-stu-id="0892e-173">Otherwise, the value is empty.</span></span>
- <span data-ttu-id="0892e-174">O `Clear-ItemProperty` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="0892e-174">The `Clear-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="0892e-175">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="0892e-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="0892e-176">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="0892e-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="0892e-177">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0892e-177">RELATED LINKS</span></span>

[<span data-ttu-id="0892e-178">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0892e-178">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="0892e-179">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0892e-179">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="0892e-180">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0892e-180">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="0892e-181">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0892e-181">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="0892e-182">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0892e-182">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="0892e-183">about_Providers</span><span class="sxs-lookup"><span data-stu-id="0892e-183">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

