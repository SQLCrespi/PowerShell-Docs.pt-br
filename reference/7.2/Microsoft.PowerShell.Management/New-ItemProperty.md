---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ItemProperty
ms.openlocfilehash: 59b7ea7f675d72dd90d970306c60107bd3f1de87
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596984"
---
# <span data-ttu-id="feebf-102">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="feebf-102">New-ItemProperty</span></span>

## <span data-ttu-id="feebf-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="feebf-103">SYNOPSIS</span></span>
<span data-ttu-id="feebf-104">Cria uma nova propriedade para um item e define seu valor.</span><span class="sxs-lookup"><span data-stu-id="feebf-104">Creates a new property for an item and sets its value.</span></span>

## <span data-ttu-id="feebf-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="feebf-105">SYNTAX</span></span>

### <span data-ttu-id="feebf-106">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="feebf-106">Path (Default)</span></span>

```
New-ItemProperty [-Path] <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="feebf-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="feebf-107">LiteralPath</span></span>

```
New-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="feebf-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="feebf-108">DESCRIPTION</span></span>

<span data-ttu-id="feebf-109">O `New-ItemProperty` cmdlet cria uma nova propriedade para um item especificado e define seu valor.</span><span class="sxs-lookup"><span data-stu-id="feebf-109">The `New-ItemProperty` cmdlet creates a new property for a specified item and sets its value.</span></span>
<span data-ttu-id="feebf-110">Normalmente, esse cmdlet é usado para criar novos valores de registro porque os valores do registro são propriedades de um item de chave do registro.</span><span class="sxs-lookup"><span data-stu-id="feebf-110">Typically, this cmdlet is used to create new registry values, because registry values are properties of a registry key item.</span></span>

<span data-ttu-id="feebf-111">Esse cmdlet não adiciona propriedades a um objeto.</span><span class="sxs-lookup"><span data-stu-id="feebf-111">This cmdlet does not add properties to an object.</span></span>

- <span data-ttu-id="feebf-112">Para adicionar uma propriedade a uma instância de um objeto, use o `Add-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="feebf-112">To add a property to an instance of an object, use the `Add-Member` cmdlet.</span></span>
- <span data-ttu-id="feebf-113">Para adicionar uma propriedade a todos os objetos de um tipo específico, modifique o arquivo XML Types.ps1.</span><span class="sxs-lookup"><span data-stu-id="feebf-113">To add a property to all objects of a particular type, modify the Types.ps1xml file.</span></span>

## <span data-ttu-id="feebf-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="feebf-114">EXAMPLES</span></span>

### <span data-ttu-id="feebf-115">Exemplo 1: adicionar uma entrada de registro</span><span class="sxs-lookup"><span data-stu-id="feebf-115">Example 1: Add a registry entry</span></span>

<span data-ttu-id="feebf-116">Esse comando adiciona uma nova entrada de registro, "NoOfEmployees", à chave "MyCompany" do "HKLM: \ Software Hive".</span><span class="sxs-lookup"><span data-stu-id="feebf-116">This command adds a new registry entry, "NoOfEmployees", to the "MyCompany" key of the "HKLM:\Software hive".</span></span>

<span data-ttu-id="feebf-117">O primeiro comando usa o parâmetro **path** para especificar o caminho da chave do registro "myCompany".</span><span class="sxs-lookup"><span data-stu-id="feebf-117">The first command uses the **Path** parameter to specify the path of the "MyCompany" registry key.</span></span>
<span data-ttu-id="feebf-118">Ele usa o parâmetro **Name** para especificar um nome para a entrada e o parâmetro **Value** para especificar seu valor.</span><span class="sxs-lookup"><span data-stu-id="feebf-118">It uses the **Name** parameter to specify a name for the entry and the **Value** parameter to specify its value.</span></span>

<span data-ttu-id="feebf-119">O segundo comando usa o `Get-ItemProperty` cmdlet para ver a nova entrada do registro.</span><span class="sxs-lookup"><span data-stu-id="feebf-119">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>

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

### <span data-ttu-id="feebf-120">Exemplo 2: adicionar uma entrada de registro a uma chave</span><span class="sxs-lookup"><span data-stu-id="feebf-120">Example 2: Add a registry entry to a key</span></span>

<span data-ttu-id="feebf-121">Este comando adiciona uma nova entrada de registro a uma chave do registro.</span><span class="sxs-lookup"><span data-stu-id="feebf-121">This command adds a new registry entry to a registry key.</span></span>
<span data-ttu-id="feebf-122">Para especificar a chave, ele usa um operador de pipeline ( `|` ) para enviar um objeto que representa a chave para `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="feebf-122">To specify the key, it uses a pipeline operator (`|`) to send an object that represents the key to `New-ItemProperty`.</span></span>

<span data-ttu-id="feebf-123">A primeira parte do comando usa o `Get-Item` cmdlet para obter a chave do registro "myCompany".</span><span class="sxs-lookup"><span data-stu-id="feebf-123">The first part of the command uses the `Get-Item` cmdlet to get the "MyCompany" registry key.</span></span>
<span data-ttu-id="feebf-124">O operador de pipeline envia os resultados do comando para `New-ItemProperty` , que adiciona a nova entrada de registro ("NoOfLocations") e seu valor (3) à chave "myCompany".</span><span class="sxs-lookup"><span data-stu-id="feebf-124">The pipeline operator sends the results of the command to `New-ItemProperty`, which adds the new registry entry ("NoOfLocations"), and its value (3), to the "MyCompany" key.</span></span>

```powershell
Get-Item -Path "HKLM:\Software\MyCompany" | New-ItemProperty -Name NoOfLocations -Value 3
```

<span data-ttu-id="feebf-125">Esse comando funciona porque o recurso de vinculação de parâmetro do PowerShell associa o caminho do `RegistryKey` objeto que `Get-Item` retorna com o parâmetro **LiteralPath** de `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="feebf-125">This command works because the parameter-binding feature of PowerShell associates the path of the `RegistryKey` object that `Get-Item` returns with the **LiteralPath** parameter of `New-ItemProperty`.</span></span> <span data-ttu-id="feebf-126">Para obter mais informações, consulte [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span><span class="sxs-lookup"><span data-stu-id="feebf-126">For more information, see [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span></span>

### <span data-ttu-id="feebf-127">Exemplo 3: criar um valor de multistring no registro usando um Here-String</span><span class="sxs-lookup"><span data-stu-id="feebf-127">Example 3: Create a MultiString value in the registry using a Here-String</span></span>

<span data-ttu-id="feebf-128">Este exemplo cria um valor de multistring usando uma cadeia de caracteres here.</span><span class="sxs-lookup"><span data-stu-id="feebf-128">This example creates a MultiString value using a Here-String.</span></span>

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

### <span data-ttu-id="feebf-129">Exemplo 4: criar um valor de cadeia de caracteres multistring no registro usando uma matriz</span><span class="sxs-lookup"><span data-stu-id="feebf-129">Example 4: Create a MultiString value in the registry using an array</span></span>

<span data-ttu-id="feebf-130">O exemplo mostra como usar uma matriz de valores para criar o `MultiString` valor.</span><span class="sxs-lookup"><span data-stu-id="feebf-130">The example shows how to use an array of values to create the `MultiString` value.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'MultiString' -PropertyType MultiString -Value ('a','b','c')
$newValue.multistring[0]
```

```output
a
```

## <span data-ttu-id="feebf-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="feebf-131">PARAMETERS</span></span>

### <span data-ttu-id="feebf-132">-Credential</span><span class="sxs-lookup"><span data-stu-id="feebf-132">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="feebf-133">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="feebf-133">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="feebf-134">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="feebf-134">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="feebf-135">-Excluir</span><span class="sxs-lookup"><span data-stu-id="feebf-135">-Exclude</span></span>

<span data-ttu-id="feebf-136">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="feebf-136">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="feebf-137">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="feebf-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="feebf-138">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="feebf-138">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="feebf-139">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="feebf-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="feebf-140">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="feebf-140">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="feebf-141">-Filter</span><span class="sxs-lookup"><span data-stu-id="feebf-141">-Filter</span></span>

<span data-ttu-id="feebf-142">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="feebf-142">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="feebf-143">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="feebf-143">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="feebf-144">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="feebf-144">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="feebf-145">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="feebf-145">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="feebf-146">-Force</span><span class="sxs-lookup"><span data-stu-id="feebf-146">-Force</span></span>

<span data-ttu-id="feebf-147">Força o cmdlet a criar uma propriedade em um objeto que, de outra forma, não pode ser acessado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="feebf-147">Forces the cmdlet to create a property on an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="feebf-148">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="feebf-148">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="feebf-149">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="feebf-149">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="feebf-150">-Incluir</span><span class="sxs-lookup"><span data-stu-id="feebf-150">-Include</span></span>

<span data-ttu-id="feebf-151">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="feebf-151">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="feebf-152">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="feebf-152">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="feebf-153">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="feebf-153">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="feebf-154">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="feebf-154">Wildcard characters are permitted.</span></span> <span data-ttu-id="feebf-155">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="feebf-155">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="feebf-156">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="feebf-156">-LiteralPath</span></span>

<span data-ttu-id="feebf-157">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="feebf-157">Specifies a path to one or more locations.</span></span> <span data-ttu-id="feebf-158">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="feebf-158">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="feebf-159">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="feebf-159">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="feebf-160">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="feebf-160">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="feebf-161">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="feebf-161">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="feebf-162">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="feebf-162">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="feebf-163">-Name</span><span class="sxs-lookup"><span data-stu-id="feebf-163">-Name</span></span>

<span data-ttu-id="feebf-164">Especifica um nome para a nova propriedade.</span><span class="sxs-lookup"><span data-stu-id="feebf-164">Specifies a name for the new property.</span></span>
<span data-ttu-id="feebf-165">Se a propriedade for uma entrada de registro, esse parâmetro especifica o nome da entrada.</span><span class="sxs-lookup"><span data-stu-id="feebf-165">If the property is a registry entry, this parameter specifies the name of the entry.</span></span>

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

### <span data-ttu-id="feebf-166">-Path</span><span class="sxs-lookup"><span data-stu-id="feebf-166">-Path</span></span>

<span data-ttu-id="feebf-167">Especifica o caminho do item.</span><span class="sxs-lookup"><span data-stu-id="feebf-167">Specifies the path of the item.</span></span>
<span data-ttu-id="feebf-168">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="feebf-168">Wildcard characters are permitted.</span></span>
<span data-ttu-id="feebf-169">Esse parâmetro identifica o item ao qual esse cmdlet adiciona a nova propriedade.</span><span class="sxs-lookup"><span data-stu-id="feebf-169">This parameter identifies the item to which this cmdlet adds the new property.</span></span>

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

### <span data-ttu-id="feebf-170">-PropertyType</span><span class="sxs-lookup"><span data-stu-id="feebf-170">-PropertyType</span></span>

<span data-ttu-id="feebf-171">Especifica o tipo de propriedade que este cmdlet adiciona.</span><span class="sxs-lookup"><span data-stu-id="feebf-171">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="feebf-172">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="feebf-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="feebf-173">**Cadeia de caracteres**: especifica uma cadeia de caracteres terminada em nulo.</span><span class="sxs-lookup"><span data-stu-id="feebf-173">**String**: Specifies a null-terminated string.</span></span> <span data-ttu-id="feebf-174">Equivalente a **REG_SZ**.</span><span class="sxs-lookup"><span data-stu-id="feebf-174">Equivalent to **REG_SZ**.</span></span>
- <span data-ttu-id="feebf-175">**ExpandString**: especifica uma cadeia de caracteres terminada em nulo que contém referências não expandidas a variáveis de ambiente que são expandidas quando o valor é recuperado.</span><span class="sxs-lookup"><span data-stu-id="feebf-175">**ExpandString**: Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="feebf-176">Equivalente a **REG_EXPAND_SZ**.</span><span class="sxs-lookup"><span data-stu-id="feebf-176">Equivalent to **REG_EXPAND_SZ**.</span></span>
- <span data-ttu-id="feebf-177">**Binary**: especifica dados binários em qualquer formulário.</span><span class="sxs-lookup"><span data-stu-id="feebf-177">**Binary**: Specifies binary data in any form.</span></span> <span data-ttu-id="feebf-178">Equivalente a **REG_BINARY**.</span><span class="sxs-lookup"><span data-stu-id="feebf-178">Equivalent to **REG_BINARY**.</span></span>
- <span data-ttu-id="feebf-179">**DWORD**: especifica um número binário de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="feebf-179">**DWord**: Specifies a 32-bit binary number.</span></span> <span data-ttu-id="feebf-180">Equivalente a **REG_DWORD**.</span><span class="sxs-lookup"><span data-stu-id="feebf-180">Equivalent to **REG_DWORD**.</span></span>
- <span data-ttu-id="feebf-181">**Multistring**: especifica uma matriz de cadeias de caracteres terminadas em nulo terminadas por dois caracteres nulos.</span><span class="sxs-lookup"><span data-stu-id="feebf-181">**MultiString**: Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="feebf-182">Equivalente a **REG_MULTI_SZ**.</span><span class="sxs-lookup"><span data-stu-id="feebf-182">Equivalent to **REG_MULTI_SZ**.</span></span>
- <span data-ttu-id="feebf-183">**QWORD**: especifica um número binário de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="feebf-183">**Qword**: Specifies a 64-bit binary number.</span></span> <span data-ttu-id="feebf-184">Equivalente a **REG_QWORD**.</span><span class="sxs-lookup"><span data-stu-id="feebf-184">Equivalent to **REG_QWORD**.</span></span>
- <span data-ttu-id="feebf-185">**Desconhecido**: indica um tipo de dados de registro sem suporte, como **REG_RESOURCE_LIST**.</span><span class="sxs-lookup"><span data-stu-id="feebf-185">**Unknown**: Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST**.</span></span>

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

### <span data-ttu-id="feebf-186">-Value</span><span class="sxs-lookup"><span data-stu-id="feebf-186">-Value</span></span>

<span data-ttu-id="feebf-187">Especifica o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="feebf-187">Specifies the property value.</span></span>
<span data-ttu-id="feebf-188">Se a propriedade for uma entrada de registro, esse parâmetro especifica o nome da entrada.</span><span class="sxs-lookup"><span data-stu-id="feebf-188">If the property is a registry entry, this parameter specifies the value of the entry.</span></span>

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

### <span data-ttu-id="feebf-189">-Confirm</span><span class="sxs-lookup"><span data-stu-id="feebf-189">-Confirm</span></span>

<span data-ttu-id="feebf-190">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="feebf-190">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="feebf-191">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="feebf-191">-WhatIf</span></span>

<span data-ttu-id="feebf-192">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="feebf-192">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="feebf-193">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="feebf-193">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="feebf-194">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="feebf-194">CommonParameters</span></span>

<span data-ttu-id="feebf-195">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="feebf-195">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="feebf-196">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="feebf-196">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="feebf-197">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="feebf-197">INPUTS</span></span>

### <span data-ttu-id="feebf-198">Nenhum</span><span class="sxs-lookup"><span data-stu-id="feebf-198">None</span></span>

<span data-ttu-id="feebf-199">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="feebf-199">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="feebf-200">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="feebf-200">OUTPUTS</span></span>

### <span data-ttu-id="feebf-201">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="feebf-201">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="feebf-202">`New-ItemProperty` Retorna um objeto personalizado que contém a nova propriedade.</span><span class="sxs-lookup"><span data-stu-id="feebf-202">`New-ItemProperty` returns a custom object that contains the new property.</span></span>

## <span data-ttu-id="feebf-203">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="feebf-203">NOTES</span></span>

<span data-ttu-id="feebf-204">`New-ItemProperty` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="feebf-204">`New-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="feebf-205">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="feebf-205">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="feebf-206">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="feebf-206">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="feebf-207">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="feebf-207">RELATED LINKS</span></span>

[<span data-ttu-id="feebf-208">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="feebf-208">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="feebf-209">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="feebf-209">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="feebf-210">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="feebf-210">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="feebf-211">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="feebf-211">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="feebf-212">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="feebf-212">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="feebf-213">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="feebf-213">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="feebf-214">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="feebf-214">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="feebf-215">about_Providers</span><span class="sxs-lookup"><span data-stu-id="feebf-215">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

