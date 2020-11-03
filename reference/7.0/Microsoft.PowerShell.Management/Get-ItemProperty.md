---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: 5ef804e0274c0caaa6da1cf8714ab8aae1899068
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192739"
---
# <span data-ttu-id="67a83-103">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="67a83-103">Get-ItemProperty</span></span>

## <span data-ttu-id="67a83-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="67a83-104">SYNOPSIS</span></span>
<span data-ttu-id="67a83-105">Obtém as propriedades de um item especificado.</span><span class="sxs-lookup"><span data-stu-id="67a83-105">Gets the properties of a specified item.</span></span>

## <span data-ttu-id="67a83-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="67a83-106">SYNTAX</span></span>

### <span data-ttu-id="67a83-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="67a83-107">Path (Default)</span></span>

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="67a83-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="67a83-108">LiteralPath</span></span>

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="67a83-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="67a83-109">DESCRIPTION</span></span>

<span data-ttu-id="67a83-110">O `Get-ItemProperty` cmdlet obtém as propriedades dos itens especificados.</span><span class="sxs-lookup"><span data-stu-id="67a83-110">The `Get-ItemProperty` cmdlet gets the properties of the specified items.</span></span>
<span data-ttu-id="67a83-111">Por exemplo, você pode usar este cmdlet para obter o valor da propriedade LastAccessTime de um objeto de arquivo.</span><span class="sxs-lookup"><span data-stu-id="67a83-111">For example, you can use this cmdlet to get the value of the LastAccessTime property of a file object.</span></span> <span data-ttu-id="67a83-112">Você também pode usar este cmdlet para exibir entradas do registro e seus valores.</span><span class="sxs-lookup"><span data-stu-id="67a83-112">You can also use this cmdlet to view registry entries and their values.</span></span>

## <span data-ttu-id="67a83-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="67a83-113">EXAMPLES</span></span>

### <span data-ttu-id="67a83-114">Exemplo 1: obter informações sobre um diretório específico</span><span class="sxs-lookup"><span data-stu-id="67a83-114">Example 1: Get information about a specific directory</span></span>

<span data-ttu-id="67a83-115">Esse comando obtém informações sobre o `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="67a83-115">This command gets information about the `C:\Windows` directory.</span></span>

```powershell
Get-ItemProperty C:\Windows
```

### <span data-ttu-id="67a83-116">Exemplo 2: obter as propriedades de um arquivo específico</span><span class="sxs-lookup"><span data-stu-id="67a83-116">Example 2: Get the properties of a specific file</span></span>

<span data-ttu-id="67a83-117">Esse comando obtém as propriedades do `C:\Test\Weather.xls` arquivo.</span><span class="sxs-lookup"><span data-stu-id="67a83-117">This command gets the properties of the `C:\Test\Weather.xls` file.</span></span>
<span data-ttu-id="67a83-118">O resultado é canalizado para o `Format-List` cmdlet a fim de exibir a saída como uma lista.</span><span class="sxs-lookup"><span data-stu-id="67a83-118">The result is piped to the `Format-List` cmdlet to display the output as a list.</span></span>

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### <span data-ttu-id="67a83-119">Exemplo 3: exibir o nome do valor e os dados das entradas do registro em uma subchave do registro</span><span class="sxs-lookup"><span data-stu-id="67a83-119">Example 3: Display the value name and data of registry entries in a registry subkey</span></span>

<span data-ttu-id="67a83-120">Esse comando exibe o nome do valor e os dados de cada uma das entradas do registro contidas na subchave do registro "CurrentVersion".</span><span class="sxs-lookup"><span data-stu-id="67a83-120">This command displays the value name and data of each of the registry entries contained in the "CurrentVersion" registry subkey.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

> [!NOTE]
> <span data-ttu-id="67a83-121">Esse comando requer que haja uma unidade do PowerShell denominada `HKLM:` que seja mapeada para o hive "HKEY_LOCAL_MACHINE" do registro.</span><span class="sxs-lookup"><span data-stu-id="67a83-121">This command requires that there is a PowerShell drive named `HKLM:` that is mapped to the "HKEY_LOCAL_MACHINE" hive of the registry.</span></span>
>
> <span data-ttu-id="67a83-122">Uma unidade com esse nome e mapeamento está disponível no PowerShell por padrão.</span><span class="sxs-lookup"><span data-stu-id="67a83-122">A drive with that name and mapping is available in PowerShell by default.</span></span>
> <span data-ttu-id="67a83-123">Como alternativa, o caminho para essa subchave de registro pode ser especificado usando o seguinte caminho alternativo que começa com o nome do provedor seguido por dois-pontos duplos:</span><span class="sxs-lookup"><span data-stu-id="67a83-123">Alternatively, the path to this registry subkey can be specified by using the following alternative path that begins with the provider name followed by two colons:</span></span>
>
> <span data-ttu-id="67a83-124">`Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span><span class="sxs-lookup"><span data-stu-id="67a83-124">`Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span></span>

### <span data-ttu-id="67a83-125">Exemplo 4: obter o nome do valor e os dados de uma entrada do registro em uma subchave do registro</span><span class="sxs-lookup"><span data-stu-id="67a83-125">Example 4: Get the value name and data of a registry entry in a registry subkey</span></span>

<span data-ttu-id="67a83-126">Esse comando obtém o nome do valor e os dados da entrada do registro "ProgramFilesDir" na subchave do registro "CurrentVersion".</span><span class="sxs-lookup"><span data-stu-id="67a83-126">This command gets the value name and data of the "ProgramFilesDir" registry entry in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="67a83-127">O **caminho** especifica a subchave e o parâmetro **Name** especifica o nome do valor da entrada.</span><span class="sxs-lookup"><span data-stu-id="67a83-127">The **Path** specifies the subkey and the **Name** parameter specifies the value name of the entry.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### <span data-ttu-id="67a83-128">Exemplo 5: obter os nomes de valor e os dados das entradas do registro em uma chave do registro</span><span class="sxs-lookup"><span data-stu-id="67a83-128">Example 5: Get the value names and data of registry entries in a registry key</span></span>

<span data-ttu-id="67a83-129">Esse comando obtém os nomes de valor e os dados das entradas do registro na chave do registro "PowerShellEngine".</span><span class="sxs-lookup"><span data-stu-id="67a83-129">This command gets the value names and data of the registry entries in the "PowerShellEngine" registry key.</span></span> <span data-ttu-id="67a83-130">Os resultados são mostrados na seguinte saída de exemplo.</span><span class="sxs-lookup"><span data-stu-id="67a83-130">The results are shown in the following sample output.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine
```

```output
ApplicationBase         : C:\Windows\system32\WindowsPowerShell\v1.0\
ConsoleHostAssemblyName : Microsoft.PowerShell.ConsoleHost, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, ProcessorArchitecture=msil
PowerShellVersion       : 2.0
RuntimeVersion          : v2.0.50727
CTPVersion              : 5
PSCompatibleVersion     : 1.0,2.0
```

## <span data-ttu-id="67a83-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="67a83-131">PARAMETERS</span></span>

### <span data-ttu-id="67a83-132">-Credential</span><span class="sxs-lookup"><span data-stu-id="67a83-132">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="67a83-133">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67a83-133">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="67a83-134">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="67a83-134">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="67a83-135">-Excluir</span><span class="sxs-lookup"><span data-stu-id="67a83-135">-Exclude</span></span>

<span data-ttu-id="67a83-136">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="67a83-136">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="67a83-137">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="67a83-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="67a83-138">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="67a83-138">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="67a83-139">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="67a83-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="67a83-140">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="67a83-140">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="67a83-141">-Filter</span><span class="sxs-lookup"><span data-stu-id="67a83-141">-Filter</span></span>

<span data-ttu-id="67a83-142">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="67a83-142">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="67a83-143">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="67a83-143">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="67a83-144">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="67a83-144">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="67a83-145">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="67a83-145">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="67a83-146">-Incluir</span><span class="sxs-lookup"><span data-stu-id="67a83-146">-Include</span></span>

<span data-ttu-id="67a83-147">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="67a83-147">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="67a83-148">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="67a83-148">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="67a83-149">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="67a83-149">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="67a83-150">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="67a83-150">Wildcard characters are permitted.</span></span> <span data-ttu-id="67a83-151">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="67a83-151">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="67a83-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="67a83-152">-LiteralPath</span></span>

<span data-ttu-id="67a83-153">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="67a83-153">Specifies a path to one or more locations.</span></span> <span data-ttu-id="67a83-154">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="67a83-154">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="67a83-155">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="67a83-155">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="67a83-156">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="67a83-156">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="67a83-157">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="67a83-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="67a83-158">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="67a83-158">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="67a83-159">-Name</span><span class="sxs-lookup"><span data-stu-id="67a83-159">-Name</span></span>

<span data-ttu-id="67a83-160">Especifica o nome da propriedade ou propriedades para recuperar.</span><span class="sxs-lookup"><span data-stu-id="67a83-160">Specifies the name of the property or properties to retrieve.</span></span>
<span data-ttu-id="67a83-161">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="67a83-161">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="67a83-162">-Path</span><span class="sxs-lookup"><span data-stu-id="67a83-162">-Path</span></span>

<span data-ttu-id="67a83-163">Especifica o caminho para o(s) item(ns).</span><span class="sxs-lookup"><span data-stu-id="67a83-163">Specifies the path to the item or items.</span></span>
<span data-ttu-id="67a83-164">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="67a83-164">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="67a83-165">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="67a83-165">CommonParameters</span></span>

<span data-ttu-id="67a83-166">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="67a83-166">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="67a83-167">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="67a83-167">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="67a83-168">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="67a83-168">INPUTS</span></span>

### <span data-ttu-id="67a83-169">System.String</span><span class="sxs-lookup"><span data-stu-id="67a83-169">System.String</span></span>

<span data-ttu-id="67a83-170">É possível canalizar uma cadeia de caracteres que contém um caminho para `Get-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="67a83-170">You can pipe a string that contains a path to `Get-ItemProperty`.</span></span>

## <span data-ttu-id="67a83-171">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="67a83-171">OUTPUTS</span></span>

### <span data-ttu-id="67a83-172">System. booliano, System. String, System. DateTime</span><span class="sxs-lookup"><span data-stu-id="67a83-172">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="67a83-173">`Get-ItemProperty` Retorna um objeto para cada propriedade de item obtida.</span><span class="sxs-lookup"><span data-stu-id="67a83-173">`Get-ItemProperty` returns an object for each item property that it gets.</span></span> <span data-ttu-id="67a83-174">O tipo de objeto depende do objeto que é recuperado.</span><span class="sxs-lookup"><span data-stu-id="67a83-174">The object type depends on the object that is retrieved.</span></span> <span data-ttu-id="67a83-175">Por exemplo, em uma unidade de sistema de arquivos, ele pode retornar um arquivo ou pasta.</span><span class="sxs-lookup"><span data-stu-id="67a83-175">For example, in a file system drive, it might return a file or folder.</span></span>

## <span data-ttu-id="67a83-176">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="67a83-176">NOTES</span></span>

<span data-ttu-id="67a83-177">O `Get-ItemProperty` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="67a83-177">The `Get-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="67a83-178">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="67a83-178">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="67a83-179">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="67a83-179">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="67a83-180">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="67a83-180">RELATED LINKS</span></span>

[<span data-ttu-id="67a83-181">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="67a83-181">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="67a83-182">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="67a83-182">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="67a83-183">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="67a83-183">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="67a83-184">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="67a83-184">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="67a83-185">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="67a83-185">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="67a83-186">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="67a83-186">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="67a83-187">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="67a83-187">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="67a83-188">about_Providers</span><span class="sxs-lookup"><span data-stu-id="67a83-188">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
