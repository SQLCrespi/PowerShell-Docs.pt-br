---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: b2c5b8596da085fab3af7a1545569dd65931a5f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194171"
---
# <span data-ttu-id="dcc80-103">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dcc80-103">Get-ItemProperty</span></span>

## <span data-ttu-id="dcc80-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="dcc80-104">SYNOPSIS</span></span>
<span data-ttu-id="dcc80-105">Obtém as propriedades de um item especificado.</span><span class="sxs-lookup"><span data-stu-id="dcc80-105">Gets the properties of a specified item.</span></span>

## <span data-ttu-id="dcc80-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dcc80-106">SYNTAX</span></span>

### <span data-ttu-id="dcc80-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="dcc80-107">Path (Default)</span></span>

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="dcc80-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="dcc80-108">LiteralPath</span></span>

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="dcc80-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dcc80-109">DESCRIPTION</span></span>

<span data-ttu-id="dcc80-110">O `Get-ItemProperty` cmdlet obtém as propriedades dos itens especificados.</span><span class="sxs-lookup"><span data-stu-id="dcc80-110">The `Get-ItemProperty` cmdlet gets the properties of the specified items.</span></span>
<span data-ttu-id="dcc80-111">Por exemplo, você pode usar este cmdlet para obter o valor da propriedade LastAccessTime de um objeto de arquivo.</span><span class="sxs-lookup"><span data-stu-id="dcc80-111">For example, you can use this cmdlet to get the value of the LastAccessTime property of a file object.</span></span>
<span data-ttu-id="dcc80-112">Você também pode usar este cmdlet para exibir entradas do registro e seus valores.</span><span class="sxs-lookup"><span data-stu-id="dcc80-112">You can also use this cmdlet to view registry entries and their values.</span></span>

## <span data-ttu-id="dcc80-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="dcc80-113">EXAMPLES</span></span>

### <span data-ttu-id="dcc80-114">Exemplo 1: obter informações sobre um diretório específico</span><span class="sxs-lookup"><span data-stu-id="dcc80-114">Example 1: Get information about a specific directory</span></span>

<span data-ttu-id="dcc80-115">Esse comando obtém informações sobre o diretório "C:\Windows".</span><span class="sxs-lookup"><span data-stu-id="dcc80-115">This command gets information about the "C:\Windows" directory.</span></span>

```powershell
Get-ItemProperty C:\Windows
```

### <span data-ttu-id="dcc80-116">Exemplo 2: obter as propriedades de um arquivo específico</span><span class="sxs-lookup"><span data-stu-id="dcc80-116">Example 2: Get the properties of a specific file</span></span>

<span data-ttu-id="dcc80-117">Esse comando obtém as propriedades do arquivo "C:\Test\Weather.xls".</span><span class="sxs-lookup"><span data-stu-id="dcc80-117">This command gets the properties of the "C:\Test\Weather.xls" file.</span></span>
<span data-ttu-id="dcc80-118">O resultado é canalizado para o `Format-List` cmdlet a fim de exibir a saída como uma lista.</span><span class="sxs-lookup"><span data-stu-id="dcc80-118">The result is piped to the `Format-List` cmdlet to display the output as a list.</span></span>

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### <span data-ttu-id="dcc80-119">Exemplo 3: exibir o nome do valor e os dados das entradas do registro em uma subchave do registro</span><span class="sxs-lookup"><span data-stu-id="dcc80-119">Example 3: Display the value name and data of registry entries in a registry subkey</span></span>

<span data-ttu-id="dcc80-120">Esse comando exibe o nome do valor e os dados de cada uma das entradas do registro contidas na subchave do registro "CurrentVersion".</span><span class="sxs-lookup"><span data-stu-id="dcc80-120">This command displays the value name and data of each of the registry entries contained in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="dcc80-121">Observe que o comando requer que haja uma unidade do PowerShell denominada `HKLM:` que seja mapeada para o hive "HKEY_LOCAL_MACHINE" do registro.</span><span class="sxs-lookup"><span data-stu-id="dcc80-121">Note that the command requires that there is a PowerShell drive named `HKLM:` that is mapped to the "HKEY_LOCAL_MACHINE" hive of the registry.</span></span>
<span data-ttu-id="dcc80-122">Uma unidade com esse nome e mapeamento está disponível no PowerShell por padrão.</span><span class="sxs-lookup"><span data-stu-id="dcc80-122">A drive with that name and mapping is available in PowerShell by default.</span></span>
<span data-ttu-id="dcc80-123">Como alternativa, o caminho para essa subchave de registro pode ser especificado usando o seguinte caminho alternativo que começa com o nome do provedor seguido por dois-pontos duplos:</span><span class="sxs-lookup"><span data-stu-id="dcc80-123">Alternatively, the path to this registry subkey can be specified by using the following alternative path that begins with the provider name followed by two colons:</span></span>

<span data-ttu-id="dcc80-124">"Registry:: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion".</span><span class="sxs-lookup"><span data-stu-id="dcc80-124">"Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion".</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

### <span data-ttu-id="dcc80-125">Exemplo 4: obter o nome do valor e os dados de uma entrada do registro em uma subchave do registro</span><span class="sxs-lookup"><span data-stu-id="dcc80-125">Example 4: Get the value name and data of a registry entry in a registry subkey</span></span>

<span data-ttu-id="dcc80-126">Esse comando obtém o nome do valor e os dados da entrada do registro "ProgramFilesDir" na subchave do registro "CurrentVersion".</span><span class="sxs-lookup"><span data-stu-id="dcc80-126">This command gets the value name and data of the "ProgramFilesDir" registry entry in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="dcc80-127">O comando usa o parâmetro **path** para especificar a subchave e o parâmetro Name para especificar o nome do valor da entrada.</span><span class="sxs-lookup"><span data-stu-id="dcc80-127">The command uses the **Path** parameter to specify the subkey and the Name parameter to specify the value name of the entry.</span></span>

<span data-ttu-id="dcc80-128">O comando usa uma marca de fundo ou acento grave ( \` ), o caractere de continuação do PowerShell, para continuar o comando na segunda linha.</span><span class="sxs-lookup"><span data-stu-id="dcc80-128">The command uses a back tick or grave accent (\`), the PowerShell continuation character, to continue the command on the second line.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### <span data-ttu-id="dcc80-129">Exemplo 5: obter os nomes de valor e os dados das entradas do registro em uma chave do registro</span><span class="sxs-lookup"><span data-stu-id="dcc80-129">Example 5: Get the value names and data of registry entries in a registry key</span></span>

<span data-ttu-id="dcc80-130">Esse comando obtém os nomes de valor e os dados das entradas do registro na chave do registro "PowerShellEngine".</span><span class="sxs-lookup"><span data-stu-id="dcc80-130">This command gets the value names and data of the registry entries in the "PowerShellEngine" registry key.</span></span>
<span data-ttu-id="dcc80-131">Os resultados são mostrados na seguinte saída de exemplo.</span><span class="sxs-lookup"><span data-stu-id="dcc80-131">The results are shown in the following sample output.</span></span>

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

### <span data-ttu-id="dcc80-132">Exemplo 6: obter, Formatar e exibir os resultados de valores e dados do registro</span><span class="sxs-lookup"><span data-stu-id="dcc80-132">Example 6: Get, format, and display the results of registry values and data</span></span>

<span data-ttu-id="dcc80-133">Este exemplo mostra como formatar a saída de um `Get-ItemProperty` comando em uma lista para facilitar a visualização dos valores e dados do registro e facilitar a interpretação dos resultados.</span><span class="sxs-lookup"><span data-stu-id="dcc80-133">This example shows how to format the output of a `Get-ItemProperty` command in a list to make it easy to see the registry values and data and to make it easy to interpret the results.</span></span>

<span data-ttu-id="dcc80-134">O primeiro comando usa o `Get-ItemProperty` cmdlet para obter as entradas do registro na subchave **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="dcc80-134">The first command uses the `Get-ItemProperty` cmdlet to get the registry entries in the **Microsoft.PowerShell** subkey.</span></span>
<span data-ttu-id="dcc80-135">Essa subchave armazena opções para o shell padrão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dcc80-135">This subkey stores options for the default shell for PowerShell.</span></span>
<span data-ttu-id="dcc80-136">Os resultados são mostrados na seguinte saída de exemplo.</span><span class="sxs-lookup"><span data-stu-id="dcc80-136">The results are shown in the following sample output.</span></span>

<span data-ttu-id="dcc80-137">A saída mostra que há duas entradas de registro, "Path" e "ExecutionPolicy".</span><span class="sxs-lookup"><span data-stu-id="dcc80-137">The output shows that there are two registry entries, "Path" and "ExecutionPolicy".</span></span>
<span data-ttu-id="dcc80-138">Quando uma chave do registro contém menos de cinco entradas, por padrão, ela é exibida em uma tabela, mas é mais fácil exibir em uma lista.</span><span class="sxs-lookup"><span data-stu-id="dcc80-138">When a registry key contains fewer than five entries, by default it is displayed in a table, but it is often easier to view in a list.</span></span>

<span data-ttu-id="dcc80-139">O segundo comando usa o mesmo `Get-ItemProperty` comando.</span><span class="sxs-lookup"><span data-stu-id="dcc80-139">The second command uses the same `Get-ItemProperty` command.</span></span>
<span data-ttu-id="dcc80-140">No entanto, desta vez, o comando usa um operador de pipeline ( `|` ) para enviar os resultados do comando para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dcc80-140">However, this time, the command uses a pipeline operator (`|`) to send the results of the command to the `Format-List` cmdlet.</span></span>
<span data-ttu-id="dcc80-141">O `Format-List` comando usa o parâmetro Property com um valor de ' \* ' (All) para exibir todas as propriedades dos objetos em uma lista.</span><span class="sxs-lookup"><span data-stu-id="dcc80-141">The `Format-List` command uses the Property parameter with a value of '\*' (all) to display all of the properties of the objects in a list.</span></span>
<span data-ttu-id="dcc80-142">Os resultados são mostrados na seguinte saída de exemplo.</span><span class="sxs-lookup"><span data-stu-id="dcc80-142">The results are shown in the following sample output.</span></span>

<span data-ttu-id="dcc80-143">A exibição resultante mostra as entradas do registro "Path" e "ExecutionPolicy", juntamente com várias propriedades menos familiares do objeto de chave do registro.</span><span class="sxs-lookup"><span data-stu-id="dcc80-143">The resulting display shows the "Path" and "ExecutionPolicy" registry entries, along with several less familiar properties of the registry key object.</span></span>
<span data-ttu-id="dcc80-144">As outras propriedades, prefixadas com o PS, são propriedades de objetos personalizados do PowerShell, como os objetos que representam as chaves do registro.</span><span class="sxs-lookup"><span data-stu-id="dcc80-144">The other properties, prefixed with PS, are properties of PowerShell custom objects, such as the objects that represent the registry keys.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell
```

```output
Path                                                        ExecutionPolicy
----                                                        ---------------
C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe   RemoteSigned
```

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell | Format-List -Property *
```

```output
PSPath          : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds\Micro
soft.PowerShell
PSParentPath    : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds
PSChildName     : Microsoft.PowerShell
PSDrive         : HKLM
PSProvider      : Microsoft.PowerShell.Core\Registry
Path            : C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe
ExecutionPolicy : RemoteSigned
```

## <span data-ttu-id="dcc80-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dcc80-145">PARAMETERS</span></span>

### <span data-ttu-id="dcc80-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="dcc80-146">-Credential</span></span>

<span data-ttu-id="dcc80-147">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="dcc80-147">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="dcc80-148">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="dcc80-148">The default is the current user.</span></span>

<span data-ttu-id="dcc80-149">Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dcc80-149">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="dcc80-150">Se você digitar um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="dcc80-150">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="dcc80-151">Nenhum provedor instalado com o Windows PowerShell dá suporte a esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="dcc80-151">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

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

### <span data-ttu-id="dcc80-152">-Excluir</span><span class="sxs-lookup"><span data-stu-id="dcc80-152">-Exclude</span></span>

<span data-ttu-id="dcc80-153">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui da operação.</span><span class="sxs-lookup"><span data-stu-id="dcc80-153">Specifies, as a string array, an item or items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="dcc80-154">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="dcc80-154">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="dcc80-155">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="dcc80-155">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="dcc80-156">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="dcc80-156">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dcc80-157">-Filter</span><span class="sxs-lookup"><span data-stu-id="dcc80-157">-Filter</span></span>

<span data-ttu-id="dcc80-158">Especifica um filtro no formato ou idioma do provedor.</span><span class="sxs-lookup"><span data-stu-id="dcc80-158">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="dcc80-159">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="dcc80-159">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="dcc80-160">A sintaxe do filtro, incluindo o uso de caracteres curinga, depende do provedor.</span><span class="sxs-lookup"><span data-stu-id="dcc80-160">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="dcc80-161">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="dcc80-161">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="dcc80-162">-Incluir</span><span class="sxs-lookup"><span data-stu-id="dcc80-162">-Include</span></span>

<span data-ttu-id="dcc80-163">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="dcc80-163">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="dcc80-164">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="dcc80-164">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="dcc80-165">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="dcc80-165">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="dcc80-166">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="dcc80-166">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dcc80-167">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="dcc80-167">-LiteralPath</span></span>

<span data-ttu-id="dcc80-168">Especifica o caminho para o local atual da propriedade.</span><span class="sxs-lookup"><span data-stu-id="dcc80-168">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="dcc80-169">Ao contrário do parâmetro **Path** , o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="dcc80-169">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="dcc80-170">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="dcc80-170">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="dcc80-171">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="dcc80-171">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="dcc80-172">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="dcc80-172">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="dcc80-173">-Name</span><span class="sxs-lookup"><span data-stu-id="dcc80-173">-Name</span></span>

<span data-ttu-id="dcc80-174">Especifica o nome da propriedade ou propriedades para recuperar.</span><span class="sxs-lookup"><span data-stu-id="dcc80-174">Specifies the name of the property or properties to retrieve.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dcc80-175">-Path</span><span class="sxs-lookup"><span data-stu-id="dcc80-175">-Path</span></span>

<span data-ttu-id="dcc80-176">Especifica o caminho para o(s) item(ns).</span><span class="sxs-lookup"><span data-stu-id="dcc80-176">Specifies the path to the item or items.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="dcc80-177">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="dcc80-177">-UseTransaction</span></span>

<span data-ttu-id="dcc80-178">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="dcc80-178">Includes the command in the active transaction.</span></span>
<span data-ttu-id="dcc80-179">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="dcc80-179">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="dcc80-180">Para obter mais informações, consulte inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="dcc80-180">For more information, see Includes the command in the active transaction.</span></span>
<span data-ttu-id="dcc80-181">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="dcc80-181">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="dcc80-182">Para obter mais informações, consulte [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="dcc80-182">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="dcc80-183">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dcc80-183">CommonParameters</span></span>

<span data-ttu-id="dcc80-184">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="dcc80-184">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="dcc80-185">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="dcc80-185">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="dcc80-186">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="dcc80-186">INPUTS</span></span>

### <span data-ttu-id="dcc80-187">System.String</span><span class="sxs-lookup"><span data-stu-id="dcc80-187">System.String</span></span>

<span data-ttu-id="dcc80-188">É possível canalizar uma cadeia de caracteres que contém um caminho para `Get-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="dcc80-188">You can pipe a string that contains a path to `Get-ItemProperty`.</span></span>

## <span data-ttu-id="dcc80-189">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="dcc80-189">OUTPUTS</span></span>

### <span data-ttu-id="dcc80-190">System. booliano, System. String, System. DateTime</span><span class="sxs-lookup"><span data-stu-id="dcc80-190">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="dcc80-191">`Get-ItemProperty` Retorna um objeto para cada propriedade de item obtida.</span><span class="sxs-lookup"><span data-stu-id="dcc80-191">`Get-ItemProperty` returns an object for each item property that it gets.</span></span>
<span data-ttu-id="dcc80-192">O tipo de objeto depende do objeto que é recuperado.</span><span class="sxs-lookup"><span data-stu-id="dcc80-192">The object type depends on the object that is retrieved.</span></span>
<span data-ttu-id="dcc80-193">Por exemplo, em uma unidade de sistema de arquivos, ele pode retornar um arquivo ou pasta.</span><span class="sxs-lookup"><span data-stu-id="dcc80-193">For example, in a file system drive, it might return a file or folder.</span></span>

## <span data-ttu-id="dcc80-194">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="dcc80-194">NOTES</span></span>

<span data-ttu-id="dcc80-195">O `Get-ItemProperty` cmdlet é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="dcc80-195">The `Get-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="dcc80-196">Para listar os provedores disponíveis em sua sessão, digite " `Get-PSProvider` ".</span><span class="sxs-lookup"><span data-stu-id="dcc80-196">To list the providers available in your session, type "`Get-PSProvider`".</span></span> <span data-ttu-id="dcc80-197">Para obter mais informações, consulte about_Providers.</span><span class="sxs-lookup"><span data-stu-id="dcc80-197">For more information, see about_Providers.</span></span>

## <span data-ttu-id="dcc80-198">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="dcc80-198">RELATED LINKS</span></span>

[<span data-ttu-id="dcc80-199">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dcc80-199">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="dcc80-200">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dcc80-200">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="dcc80-201">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dcc80-201">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="dcc80-202">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dcc80-202">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="dcc80-203">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dcc80-203">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="dcc80-204">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dcc80-204">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="dcc80-205">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dcc80-205">Set-ItemProperty</span></span>](Set-ItemProperty.md)
