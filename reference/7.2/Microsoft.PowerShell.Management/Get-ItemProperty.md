---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: 20116c12f09d6a9a36f33b656a36e30c2096db70
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598846"
---
# <span data-ttu-id="1bf26-102">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1bf26-102">Get-ItemProperty</span></span>

## <span data-ttu-id="1bf26-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1bf26-103">SYNOPSIS</span></span>
<span data-ttu-id="1bf26-104">Obtém as propriedades de um item especificado.</span><span class="sxs-lookup"><span data-stu-id="1bf26-104">Gets the properties of a specified item.</span></span>

## <span data-ttu-id="1bf26-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1bf26-105">SYNTAX</span></span>

### <span data-ttu-id="1bf26-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="1bf26-106">Path (Default)</span></span>

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="1bf26-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1bf26-107">LiteralPath</span></span>

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="1bf26-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1bf26-108">DESCRIPTION</span></span>

<span data-ttu-id="1bf26-109">O `Get-ItemProperty` cmdlet obtém as propriedades dos itens especificados.</span><span class="sxs-lookup"><span data-stu-id="1bf26-109">The `Get-ItemProperty` cmdlet gets the properties of the specified items.</span></span>
<span data-ttu-id="1bf26-110">Por exemplo, você pode usar este cmdlet para obter o valor da propriedade LastAccessTime de um objeto de arquivo.</span><span class="sxs-lookup"><span data-stu-id="1bf26-110">For example, you can use this cmdlet to get the value of the LastAccessTime property of a file object.</span></span> <span data-ttu-id="1bf26-111">Você também pode usar este cmdlet para exibir entradas do registro e seus valores.</span><span class="sxs-lookup"><span data-stu-id="1bf26-111">You can also use this cmdlet to view registry entries and their values.</span></span>

## <span data-ttu-id="1bf26-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1bf26-112">EXAMPLES</span></span>

### <span data-ttu-id="1bf26-113">Exemplo 1: obter informações sobre um diretório específico</span><span class="sxs-lookup"><span data-stu-id="1bf26-113">Example 1: Get information about a specific directory</span></span>

<span data-ttu-id="1bf26-114">Esse comando obtém informações sobre o `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="1bf26-114">This command gets information about the `C:\Windows` directory.</span></span>

```powershell
Get-ItemProperty C:\Windows
```

### <span data-ttu-id="1bf26-115">Exemplo 2: obter as propriedades de um arquivo específico</span><span class="sxs-lookup"><span data-stu-id="1bf26-115">Example 2: Get the properties of a specific file</span></span>

<span data-ttu-id="1bf26-116">Esse comando obtém as propriedades do `C:\Test\Weather.xls` arquivo.</span><span class="sxs-lookup"><span data-stu-id="1bf26-116">This command gets the properties of the `C:\Test\Weather.xls` file.</span></span>
<span data-ttu-id="1bf26-117">O resultado é canalizado para o `Format-List` cmdlet a fim de exibir a saída como uma lista.</span><span class="sxs-lookup"><span data-stu-id="1bf26-117">The result is piped to the `Format-List` cmdlet to display the output as a list.</span></span>

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### <span data-ttu-id="1bf26-118">Exemplo 3: exibir o nome do valor e os dados das entradas do registro em uma subchave do registro</span><span class="sxs-lookup"><span data-stu-id="1bf26-118">Example 3: Display the value name and data of registry entries in a registry subkey</span></span>

<span data-ttu-id="1bf26-119">Esse comando exibe o nome do valor e os dados de cada uma das entradas do registro contidas na subchave do registro "CurrentVersion".</span><span class="sxs-lookup"><span data-stu-id="1bf26-119">This command displays the value name and data of each of the registry entries contained in the "CurrentVersion" registry subkey.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

> [!NOTE]
> <span data-ttu-id="1bf26-120">Esse comando requer que haja uma unidade do PowerShell denominada `HKLM:` que seja mapeada para o hive "HKEY_LOCAL_MACHINE" do registro.</span><span class="sxs-lookup"><span data-stu-id="1bf26-120">This command requires that there is a PowerShell drive named `HKLM:` that is mapped to the "HKEY_LOCAL_MACHINE" hive of the registry.</span></span>
>
> <span data-ttu-id="1bf26-121">Uma unidade com esse nome e mapeamento está disponível no PowerShell por padrão.</span><span class="sxs-lookup"><span data-stu-id="1bf26-121">A drive with that name and mapping is available in PowerShell by default.</span></span>
> <span data-ttu-id="1bf26-122">Como alternativa, o caminho para essa subchave de registro pode ser especificado usando o seguinte caminho alternativo que começa com o nome do provedor seguido por dois-pontos duplos:</span><span class="sxs-lookup"><span data-stu-id="1bf26-122">Alternatively, the path to this registry subkey can be specified by using the following alternative path that begins with the provider name followed by two colons:</span></span>
>
> <span data-ttu-id="1bf26-123">`Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span><span class="sxs-lookup"><span data-stu-id="1bf26-123">`Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span></span>

### <span data-ttu-id="1bf26-124">Exemplo 4: obter o nome do valor e os dados de uma entrada do registro em uma subchave do registro</span><span class="sxs-lookup"><span data-stu-id="1bf26-124">Example 4: Get the value name and data of a registry entry in a registry subkey</span></span>

<span data-ttu-id="1bf26-125">Esse comando obtém o nome do valor e os dados da entrada do registro "ProgramFilesDir" na subchave do registro "CurrentVersion".</span><span class="sxs-lookup"><span data-stu-id="1bf26-125">This command gets the value name and data of the "ProgramFilesDir" registry entry in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="1bf26-126">O **caminho** especifica a subchave e o parâmetro **Name** especifica o nome do valor da entrada.</span><span class="sxs-lookup"><span data-stu-id="1bf26-126">The **Path** specifies the subkey and the **Name** parameter specifies the value name of the entry.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### <span data-ttu-id="1bf26-127">Exemplo 5: obter os nomes de valor e os dados das entradas do registro em uma chave do registro</span><span class="sxs-lookup"><span data-stu-id="1bf26-127">Example 5: Get the value names and data of registry entries in a registry key</span></span>

<span data-ttu-id="1bf26-128">Esse comando obtém os nomes de valor e os dados das entradas do registro na chave do registro "PowerShellEngine".</span><span class="sxs-lookup"><span data-stu-id="1bf26-128">This command gets the value names and data of the registry entries in the "PowerShellEngine" registry key.</span></span> <span data-ttu-id="1bf26-129">Os resultados são mostrados na seguinte saída de exemplo.</span><span class="sxs-lookup"><span data-stu-id="1bf26-129">The results are shown in the following sample output.</span></span>

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

## <span data-ttu-id="1bf26-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1bf26-130">PARAMETERS</span></span>

### <span data-ttu-id="1bf26-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="1bf26-131">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="1bf26-132">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bf26-132">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="1bf26-133">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="1bf26-133">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="1bf26-134">-Excluir</span><span class="sxs-lookup"><span data-stu-id="1bf26-134">-Exclude</span></span>

<span data-ttu-id="1bf26-135">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="1bf26-135">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="1bf26-136">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="1bf26-136">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="1bf26-137">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="1bf26-137">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="1bf26-138">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="1bf26-138">Wildcard characters are permitted.</span></span> <span data-ttu-id="1bf26-139">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="1bf26-139">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="1bf26-140">-Filter</span><span class="sxs-lookup"><span data-stu-id="1bf26-140">-Filter</span></span>

<span data-ttu-id="1bf26-141">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="1bf26-141">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="1bf26-142">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="1bf26-142">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="1bf26-143">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="1bf26-143">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="1bf26-144">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="1bf26-144">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="1bf26-145">-Incluir</span><span class="sxs-lookup"><span data-stu-id="1bf26-145">-Include</span></span>

<span data-ttu-id="1bf26-146">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="1bf26-146">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="1bf26-147">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="1bf26-147">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="1bf26-148">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="1bf26-148">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="1bf26-149">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="1bf26-149">Wildcard characters are permitted.</span></span> <span data-ttu-id="1bf26-150">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="1bf26-150">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="1bf26-151">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1bf26-151">-LiteralPath</span></span>

<span data-ttu-id="1bf26-152">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="1bf26-152">Specifies a path to one or more locations.</span></span> <span data-ttu-id="1bf26-153">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="1bf26-153">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="1bf26-154">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="1bf26-154">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="1bf26-155">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="1bf26-155">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="1bf26-156">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="1bf26-156">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="1bf26-157">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="1bf26-157">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="1bf26-158">-Name</span><span class="sxs-lookup"><span data-stu-id="1bf26-158">-Name</span></span>

<span data-ttu-id="1bf26-159">Especifica o nome da propriedade ou propriedades para recuperar.</span><span class="sxs-lookup"><span data-stu-id="1bf26-159">Specifies the name of the property or properties to retrieve.</span></span>
<span data-ttu-id="1bf26-160">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="1bf26-160">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="1bf26-161">-Path</span><span class="sxs-lookup"><span data-stu-id="1bf26-161">-Path</span></span>

<span data-ttu-id="1bf26-162">Especifica o caminho para o(s) item(ns).</span><span class="sxs-lookup"><span data-stu-id="1bf26-162">Specifies the path to the item or items.</span></span>
<span data-ttu-id="1bf26-163">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="1bf26-163">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="1bf26-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1bf26-164">CommonParameters</span></span>

<span data-ttu-id="1bf26-165">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="1bf26-165">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="1bf26-166">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="1bf26-166">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="1bf26-167">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1bf26-167">INPUTS</span></span>

### <span data-ttu-id="1bf26-168">System.String</span><span class="sxs-lookup"><span data-stu-id="1bf26-168">System.String</span></span>

<span data-ttu-id="1bf26-169">É possível canalizar uma cadeia de caracteres que contém um caminho para `Get-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="1bf26-169">You can pipe a string that contains a path to `Get-ItemProperty`.</span></span>

## <span data-ttu-id="1bf26-170">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1bf26-170">OUTPUTS</span></span>

### <span data-ttu-id="1bf26-171">System. booliano, System. String, System. DateTime</span><span class="sxs-lookup"><span data-stu-id="1bf26-171">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="1bf26-172">`Get-ItemProperty` Retorna um objeto para cada propriedade de item obtida.</span><span class="sxs-lookup"><span data-stu-id="1bf26-172">`Get-ItemProperty` returns an object for each item property that it gets.</span></span> <span data-ttu-id="1bf26-173">O tipo de objeto depende do objeto que é recuperado.</span><span class="sxs-lookup"><span data-stu-id="1bf26-173">The object type depends on the object that is retrieved.</span></span> <span data-ttu-id="1bf26-174">Por exemplo, em uma unidade de sistema de arquivos, ele pode retornar um arquivo ou pasta.</span><span class="sxs-lookup"><span data-stu-id="1bf26-174">For example, in a file system drive, it might return a file or folder.</span></span>

## <span data-ttu-id="1bf26-175">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1bf26-175">NOTES</span></span>

<span data-ttu-id="1bf26-176">O `Get-ItemProperty` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="1bf26-176">The `Get-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="1bf26-177">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="1bf26-177">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="1bf26-178">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="1bf26-178">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="1bf26-179">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1bf26-179">RELATED LINKS</span></span>

[<span data-ttu-id="1bf26-180">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1bf26-180">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="1bf26-181">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1bf26-181">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="1bf26-182">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1bf26-182">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="1bf26-183">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1bf26-183">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="1bf26-184">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1bf26-184">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="1bf26-185">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1bf26-185">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="1bf26-186">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="1bf26-186">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="1bf26-187">about_Providers</span><span class="sxs-lookup"><span data-stu-id="1bf26-187">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

