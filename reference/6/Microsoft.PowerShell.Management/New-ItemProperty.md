---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-itemproperty?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ItemProperty
ms.openlocfilehash: 63f1df176bb2e3308a5fb66f19a6f94336a5d8d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193605"
---
# <span data-ttu-id="a6d75-103">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a6d75-103">New-ItemProperty</span></span>

## <span data-ttu-id="a6d75-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a6d75-104">SYNOPSIS</span></span>
<span data-ttu-id="a6d75-105">Cria uma nova propriedade para um item e define seu valor.</span><span class="sxs-lookup"><span data-stu-id="a6d75-105">Creates a new property for an item and sets its value.</span></span>

## <span data-ttu-id="a6d75-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a6d75-106">SYNTAX</span></span>

### <span data-ttu-id="a6d75-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="a6d75-107">Path (Default)</span></span>

```
New-ItemProperty [-Path] <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a6d75-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a6d75-108">LiteralPath</span></span>

```
New-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a6d75-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a6d75-109">DESCRIPTION</span></span>

<span data-ttu-id="a6d75-110">O `New-ItemProperty` cmdlet cria uma nova propriedade para um item especificado e define seu valor.</span><span class="sxs-lookup"><span data-stu-id="a6d75-110">The `New-ItemProperty` cmdlet creates a new property for a specified item and sets its value.</span></span>
<span data-ttu-id="a6d75-111">Normalmente, esse cmdlet é usado para criar novos valores de registro porque os valores do registro são propriedades de um item de chave do registro.</span><span class="sxs-lookup"><span data-stu-id="a6d75-111">Typically, this cmdlet is used to create new registry values, because registry values are properties of a registry key item.</span></span>

<span data-ttu-id="a6d75-112">Esse cmdlet não adiciona propriedades a um objeto.</span><span class="sxs-lookup"><span data-stu-id="a6d75-112">This cmdlet does not add properties to an object.</span></span>

- <span data-ttu-id="a6d75-113">Para adicionar uma propriedade a uma instância de um objeto, use o `Add-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a6d75-113">To add a property to an instance of an object, use the `Add-Member` cmdlet.</span></span>
- <span data-ttu-id="a6d75-114">Para adicionar uma propriedade a todos os objetos de um tipo específico, modifique o arquivo XML Types.ps1.</span><span class="sxs-lookup"><span data-stu-id="a6d75-114">To add a property to all objects of a particular type, modify the Types.ps1xml file.</span></span>

## <span data-ttu-id="a6d75-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a6d75-115">EXAMPLES</span></span>

### <span data-ttu-id="a6d75-116">Exemplo 1: adicionar uma entrada de registro</span><span class="sxs-lookup"><span data-stu-id="a6d75-116">Example 1: Add a registry entry</span></span>

<span data-ttu-id="a6d75-117">Esse comando adiciona uma nova entrada de registro, "NoOfEmployees", à chave "MyCompany" do "HKLM: \ Software Hive".</span><span class="sxs-lookup"><span data-stu-id="a6d75-117">This command adds a new registry entry, "NoOfEmployees", to the "MyCompany" key of the "HKLM:\Software hive".</span></span>

<span data-ttu-id="a6d75-118">O primeiro comando usa o parâmetro **path** para especificar o caminho da chave do registro "myCompany".</span><span class="sxs-lookup"><span data-stu-id="a6d75-118">The first command uses the **Path** parameter to specify the path of the "MyCompany" registry key.</span></span>
<span data-ttu-id="a6d75-119">Ele usa o parâmetro **Name** para especificar um nome para a entrada e o parâmetro **Value** para especificar seu valor.</span><span class="sxs-lookup"><span data-stu-id="a6d75-119">It uses the **Name** parameter to specify a name for the entry and the **Value** parameter to specify its value.</span></span>

<span data-ttu-id="a6d75-120">O segundo comando usa o `Get-ItemProperty` cmdlet para ver a nova entrada do registro.</span><span class="sxs-lookup"><span data-stu-id="a6d75-120">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>

```powershell
New-ItemProperty -Path "HKLM:\Software\MyCompany" -Name "NoOfEmployees" -Value 822
Get-ItemProperty "HKLM:\Software\MyCompany"
```

```output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\mycompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : mycompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 822
```

### <span data-ttu-id="a6d75-121">Exemplo 2: adicionar uma entrada de registro a uma chave</span><span class="sxs-lookup"><span data-stu-id="a6d75-121">Example 2: Add a registry entry to a key</span></span>

<span data-ttu-id="a6d75-122">Este comando adiciona uma nova entrada de registro a uma chave do registro.</span><span class="sxs-lookup"><span data-stu-id="a6d75-122">This command adds a new registry entry to a registry key.</span></span>
<span data-ttu-id="a6d75-123">Para especificar a chave, ele usa um operador de pipeline ( `|` ) para enviar um objeto que representa a chave para `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="a6d75-123">To specify the key, it uses a pipeline operator (`|`) to send an object that represents the key to `New-ItemProperty`.</span></span>

<span data-ttu-id="a6d75-124">A primeira parte do comando usa o `Get-Item` cmdlet para obter a chave do registro "myCompany".</span><span class="sxs-lookup"><span data-stu-id="a6d75-124">The first part of the command uses the `Get-Item` cmdlet to get the "MyCompany" registry key.</span></span>
<span data-ttu-id="a6d75-125">O operador de pipeline envia os resultados do comando para `New-ItemProperty` , que adiciona a nova entrada de registro ("NoOfLocations") e seu valor (3) à chave "myCompany".</span><span class="sxs-lookup"><span data-stu-id="a6d75-125">The pipeline operator sends the results of the command to `New-ItemProperty`, which adds the new registry entry ("NoOfLocations"), and its value (3), to the "MyCompany" key.</span></span>

```powershell
Get-Item -Path "HKLM:\Software\MyCompany" | New-ItemProperty -Name NoOfLocations -Value 3
```

<span data-ttu-id="a6d75-126">Esse comando funciona porque o recurso de vinculação de parâmetro do PowerShell associa o caminho do `RegistryKey` objeto que `Get-Item` retorna com o parâmetro **LiteralPath** de `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="a6d75-126">This command works because the parameter-binding feature of PowerShell associates the path of the `RegistryKey` object that `Get-Item` returns with the **LiteralPath** parameter of `New-ItemProperty`.</span></span> <span data-ttu-id="a6d75-127">Para obter mais informações, consulte [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span><span class="sxs-lookup"><span data-stu-id="a6d75-127">For more information, see [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span></span>

### <span data-ttu-id="a6d75-128">Exemplo 3: criar um valor de multistring no registro usando um Here-String</span><span class="sxs-lookup"><span data-stu-id="a6d75-128">Example 3: Create a MultiString value in the registry using a Here-String</span></span>

<span data-ttu-id="a6d75-129">Este exemplo cria um valor de multistring usando uma cadeia de caracteres here.</span><span class="sxs-lookup"><span data-stu-id="a6d75-129">This example creates a MultiString value using a Here-String.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'HereString' -PropertyType MultiString -Value @"
This is text which contains newlines
It can also contain "quoted" strings
"@
$newValue.multistring
```

```output
This is text which contains newlines
It can also contain "quoted" strings
```

### <span data-ttu-id="a6d75-130">Exemplo 4: criar um valor de cadeia de caracteres multistring no registro usando uma matriz</span><span class="sxs-lookup"><span data-stu-id="a6d75-130">Example 4: Create a MultiString value in the registry using an array</span></span>

<span data-ttu-id="a6d75-131">O exemplo mostra como usar uma matriz de valores para criar o `MultiString` valor.</span><span class="sxs-lookup"><span data-stu-id="a6d75-131">The example shows how to use an array of values to create the `MultiString` value.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'MultiString' -PropertyType MultiString -Value ('a','b','c')
$newValue.multistring[0]
```

```output
a
```

## <span data-ttu-id="a6d75-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a6d75-132">PARAMETERS</span></span>

### <span data-ttu-id="a6d75-133">-Credential</span><span class="sxs-lookup"><span data-stu-id="a6d75-133">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="a6d75-134">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6d75-134">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="a6d75-135">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="a6d75-135">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="a6d75-136">-Excluir</span><span class="sxs-lookup"><span data-stu-id="a6d75-136">-Exclude</span></span>

<span data-ttu-id="a6d75-137">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="a6d75-137">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="a6d75-138">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="a6d75-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a6d75-139">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="a6d75-139">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="a6d75-140">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a6d75-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="a6d75-141">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="a6d75-141">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="a6d75-142">-Filter</span><span class="sxs-lookup"><span data-stu-id="a6d75-142">-Filter</span></span>

<span data-ttu-id="a6d75-143">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="a6d75-143">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="a6d75-144">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="a6d75-144">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="a6d75-145">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="a6d75-145">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="a6d75-146">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="a6d75-146">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="a6d75-147">-Force</span><span class="sxs-lookup"><span data-stu-id="a6d75-147">-Force</span></span>

<span data-ttu-id="a6d75-148">Força o cmdlet a criar uma propriedade em um objeto que, de outra forma, não pode ser acessado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="a6d75-148">Forces the cmdlet to create a property on an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="a6d75-149">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="a6d75-149">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="a6d75-150">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="a6d75-150">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="a6d75-151">-Incluir</span><span class="sxs-lookup"><span data-stu-id="a6d75-151">-Include</span></span>

<span data-ttu-id="a6d75-152">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="a6d75-152">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="a6d75-153">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="a6d75-153">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="a6d75-154">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="a6d75-154">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="a6d75-155">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a6d75-155">Wildcard characters are permitted.</span></span> <span data-ttu-id="a6d75-156">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="a6d75-156">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="a6d75-157">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a6d75-157">-LiteralPath</span></span>

<span data-ttu-id="a6d75-158">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="a6d75-158">Specifies a path to one or more locations.</span></span> <span data-ttu-id="a6d75-159">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="a6d75-159">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="a6d75-160">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="a6d75-160">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="a6d75-161">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="a6d75-161">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="a6d75-162">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="a6d75-162">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="a6d75-163">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="a6d75-163">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="a6d75-164">-Name</span><span class="sxs-lookup"><span data-stu-id="a6d75-164">-Name</span></span>

<span data-ttu-id="a6d75-165">Especifica um nome para a nova propriedade.</span><span class="sxs-lookup"><span data-stu-id="a6d75-165">Specifies a name for the new property.</span></span>
<span data-ttu-id="a6d75-166">Se a propriedade for uma entrada de registro, esse parâmetro especifica o nome da entrada.</span><span class="sxs-lookup"><span data-stu-id="a6d75-166">If the property is a registry entry, this parameter specifies the name of the entry.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6d75-167">-Path</span><span class="sxs-lookup"><span data-stu-id="a6d75-167">-Path</span></span>

<span data-ttu-id="a6d75-168">Especifica o caminho do item.</span><span class="sxs-lookup"><span data-stu-id="a6d75-168">Specifies the path of the item.</span></span>
<span data-ttu-id="a6d75-169">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a6d75-169">Wildcard characters are permitted.</span></span>
<span data-ttu-id="a6d75-170">Esse parâmetro identifica o item ao qual esse cmdlet adiciona a nova propriedade.</span><span class="sxs-lookup"><span data-stu-id="a6d75-170">This parameter identifies the item to which this cmdlet adds the new property.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a6d75-171">-PropertyType</span><span class="sxs-lookup"><span data-stu-id="a6d75-171">-PropertyType</span></span>

<span data-ttu-id="a6d75-172">Especifica o tipo de propriedade que este cmdlet adiciona.</span><span class="sxs-lookup"><span data-stu-id="a6d75-172">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="a6d75-173">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="a6d75-173">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a6d75-174">**Cadeia de caracteres** : especifica uma cadeia de caracteres terminada em nulo.</span><span class="sxs-lookup"><span data-stu-id="a6d75-174">**String** : Specifies a null-terminated string.</span></span> <span data-ttu-id="a6d75-175">Equivalente a **REG_SZ** .</span><span class="sxs-lookup"><span data-stu-id="a6d75-175">Equivalent to **REG_SZ** .</span></span>
- <span data-ttu-id="a6d75-176">**ExpandString** : especifica uma cadeia de caracteres terminada em nulo que contém referências não expandidas a variáveis de ambiente que são expandidas quando o valor é recuperado.</span><span class="sxs-lookup"><span data-stu-id="a6d75-176">**ExpandString** : Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="a6d75-177">Equivalente a **REG_EXPAND_SZ** .</span><span class="sxs-lookup"><span data-stu-id="a6d75-177">Equivalent to **REG_EXPAND_SZ** .</span></span>
- <span data-ttu-id="a6d75-178">**Binary** : especifica dados binários em qualquer formulário.</span><span class="sxs-lookup"><span data-stu-id="a6d75-178">**Binary** : Specifies binary data in any form.</span></span> <span data-ttu-id="a6d75-179">Equivalente a **REG_BINARY** .</span><span class="sxs-lookup"><span data-stu-id="a6d75-179">Equivalent to **REG_BINARY** .</span></span>
- <span data-ttu-id="a6d75-180">**DWORD** : especifica um número binário de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="a6d75-180">**DWord** : Specifies a 32-bit binary number.</span></span> <span data-ttu-id="a6d75-181">Equivalente a **REG_DWORD** .</span><span class="sxs-lookup"><span data-stu-id="a6d75-181">Equivalent to **REG_DWORD** .</span></span>
- <span data-ttu-id="a6d75-182">**Multistring** : especifica uma matriz de cadeias de caracteres terminadas em nulo terminadas por dois caracteres nulos.</span><span class="sxs-lookup"><span data-stu-id="a6d75-182">**MultiString** : Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="a6d75-183">Equivalente a **REG_MULTI_SZ** .</span><span class="sxs-lookup"><span data-stu-id="a6d75-183">Equivalent to **REG_MULTI_SZ** .</span></span>
- <span data-ttu-id="a6d75-184">**QWORD** : especifica um número binário de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="a6d75-184">**Qword** : Specifies a 64-bit binary number.</span></span> <span data-ttu-id="a6d75-185">Equivalente a **REG_QWORD** .</span><span class="sxs-lookup"><span data-stu-id="a6d75-185">Equivalent to **REG_QWORD** .</span></span>
- <span data-ttu-id="a6d75-186">**Desconhecido** : indica um tipo de dados de registro sem suporte, como **REG_RESOURCE_LIST** .</span><span class="sxs-lookup"><span data-stu-id="a6d75-186">**Unknown** : Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6d75-187">-Value</span><span class="sxs-lookup"><span data-stu-id="a6d75-187">-Value</span></span>

<span data-ttu-id="a6d75-188">Especifica o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="a6d75-188">Specifies the property value.</span></span>
<span data-ttu-id="a6d75-189">Se a propriedade for uma entrada de registro, esse parâmetro especifica o nome da entrada.</span><span class="sxs-lookup"><span data-stu-id="a6d75-189">If the property is a registry entry, this parameter specifies the value of the entry.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6d75-190">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a6d75-190">-Confirm</span></span>

<span data-ttu-id="a6d75-191">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a6d75-191">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a6d75-192">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a6d75-192">-WhatIf</span></span>

<span data-ttu-id="a6d75-193">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="a6d75-193">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a6d75-194">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="a6d75-194">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a6d75-195">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a6d75-195">CommonParameters</span></span>

<span data-ttu-id="a6d75-196">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="a6d75-196">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="a6d75-197">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a6d75-197">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a6d75-198">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a6d75-198">INPUTS</span></span>

### <span data-ttu-id="a6d75-199">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a6d75-199">None</span></span>

<span data-ttu-id="a6d75-200">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a6d75-200">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a6d75-201">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a6d75-201">OUTPUTS</span></span>

### <span data-ttu-id="a6d75-202">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="a6d75-202">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="a6d75-203">`New-ItemProperty` Retorna um objeto personalizado que contém a nova propriedade.</span><span class="sxs-lookup"><span data-stu-id="a6d75-203">`New-ItemProperty` returns a custom object that contains the new property.</span></span>

## <span data-ttu-id="a6d75-204">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a6d75-204">NOTES</span></span>

<span data-ttu-id="a6d75-205">`New-ItemProperty` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="a6d75-205">`New-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="a6d75-206">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="a6d75-206">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="a6d75-207">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="a6d75-207">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="a6d75-208">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a6d75-208">RELATED LINKS</span></span>

[<span data-ttu-id="a6d75-209">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a6d75-209">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="a6d75-210">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a6d75-210">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="a6d75-211">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a6d75-211">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="a6d75-212">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a6d75-212">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="a6d75-213">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a6d75-213">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="a6d75-214">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a6d75-214">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="a6d75-215">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="a6d75-215">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="a6d75-216">about_Providers</span><span class="sxs-lookup"><span data-stu-id="a6d75-216">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
