---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ItemProperty
ms.openlocfilehash: 2569f4778f54f6cdad22e10cf92e727b73c323e3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193969"
---
# <span data-ttu-id="ea2d5-103">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ea2d5-103">New-ItemProperty</span></span>

## <span data-ttu-id="ea2d5-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ea2d5-104">SYNOPSIS</span></span>
<span data-ttu-id="ea2d5-105">Cria uma nova propriedade para um item e define seu valor.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-105">Creates a new property for an item and sets its value.</span></span>

## <span data-ttu-id="ea2d5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ea2d5-106">SYNTAX</span></span>

### <span data-ttu-id="ea2d5-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="ea2d5-107">Path (Default)</span></span>

```
New-ItemProperty [-Path] <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="ea2d5-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ea2d5-108">LiteralPath</span></span>

```
New-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="ea2d5-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ea2d5-109">DESCRIPTION</span></span>

<span data-ttu-id="ea2d5-110">O `New-ItemProperty` cmdlet cria uma nova propriedade para um item especificado e define seu valor.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-110">The `New-ItemProperty` cmdlet creates a new property for a specified item and sets its value.</span></span>
<span data-ttu-id="ea2d5-111">Normalmente, esse cmdlet é usado para criar novos valores de registro porque os valores do registro são propriedades de um item de chave do registro.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-111">Typically, this cmdlet is used to create new registry values, because registry values are properties of a registry key item.</span></span>

<span data-ttu-id="ea2d5-112">Esse cmdlet não adiciona propriedades a um objeto.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-112">This cmdlet does not add properties to an object.</span></span>

- <span data-ttu-id="ea2d5-113">Para adicionar uma propriedade a uma instância de um objeto, use o `Add-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-113">To add a property to an instance of an object, use the `Add-Member` cmdlet.</span></span>
- <span data-ttu-id="ea2d5-114">Para adicionar uma propriedade a todos os objetos de um tipo específico, modifique o arquivo XML Types.ps1.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-114">To add a property to all objects of a particular type, modify the Types.ps1xml file.</span></span>

## <span data-ttu-id="ea2d5-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ea2d5-115">EXAMPLES</span></span>

### <span data-ttu-id="ea2d5-116">Exemplo 1: adicionar uma entrada de registro</span><span class="sxs-lookup"><span data-stu-id="ea2d5-116">Example 1: Add a registry entry</span></span>

<span data-ttu-id="ea2d5-117">Esse comando adiciona uma nova entrada de registro, "NoOfEmployees", à chave "MyCompany" do "HKLM: \ Software Hive".</span><span class="sxs-lookup"><span data-stu-id="ea2d5-117">This command adds a new registry entry, "NoOfEmployees", to the "MyCompany" key of the "HKLM:\Software hive".</span></span>

<span data-ttu-id="ea2d5-118">O primeiro comando usa o parâmetro **path** para especificar o caminho da chave do registro "myCompany".</span><span class="sxs-lookup"><span data-stu-id="ea2d5-118">The first command uses the **Path** parameter to specify the path of the "MyCompany" registry key.</span></span>
<span data-ttu-id="ea2d5-119">Ele usa o parâmetro **Name** para especificar um nome para a entrada e o parâmetro **Value** para especificar seu valor.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-119">It uses the **Name** parameter to specify a name for the entry and the **Value** parameter to specify its value.</span></span>

<span data-ttu-id="ea2d5-120">O segundo comando usa o `Get-ItemProperty` cmdlet para ver a nova entrada do registro.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-120">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>

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

### <span data-ttu-id="ea2d5-121">Exemplo 2: adicionar uma entrada de registro a uma chave</span><span class="sxs-lookup"><span data-stu-id="ea2d5-121">Example 2: Add a registry entry to a key</span></span>

<span data-ttu-id="ea2d5-122">Este comando adiciona uma nova entrada de registro a uma chave do registro.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-122">This command adds a new registry entry to a registry key.</span></span> <span data-ttu-id="ea2d5-123">Para especificar a chave, ele usa um operador de pipeline (|) para enviar um objeto que representa a chave para `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="ea2d5-123">To specify the key, it uses a pipeline operator (|) to send an object that represents the key to `New-ItemProperty`.</span></span>

<span data-ttu-id="ea2d5-124">A primeira parte do comando usa o `Get-Item` cmdlet para obter a chave do registro "myCompany".</span><span class="sxs-lookup"><span data-stu-id="ea2d5-124">The first part of the command uses the `Get-Item` cmdlet to get the "MyCompany" registry key.</span></span> <span data-ttu-id="ea2d5-125">O operador de pipeline envia os resultados do comando para `New-ItemProperty` , que adiciona a nova entrada de registro ("NoOfLocations") e seu valor (3) à chave "myCompany".</span><span class="sxs-lookup"><span data-stu-id="ea2d5-125">The pipeline operator sends the results of the command to `New-ItemProperty`, which adds the new registry entry ("NoOfLocations"), and its value (3), to the "MyCompany" key.</span></span>

```powershell
Get-Item -Path "HKLM:\Software\MyCompany" | New-ItemProperty -Name NoOfLocations -Value 3
```

<span data-ttu-id="ea2d5-126">Esse comando funciona porque o recurso de vinculação de parâmetro do Windows PowerShell associa o caminho do `RegistryKey` objeto que `Get-Item` retorna com o parâmetro **LiteralPath** de `New-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="ea2d5-126">This command works because the parameter-binding feature of Windows PowerShell associates the path of the `RegistryKey` object that `Get-Item` returns with the **LiteralPath** parameter of `New-ItemProperty`.</span></span> <span data-ttu-id="ea2d5-127">Para obter mais informações, consulte [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span><span class="sxs-lookup"><span data-stu-id="ea2d5-127">For more information, see [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span></span>

### <span data-ttu-id="ea2d5-128">Exemplo 3: criar um valor de multistring no registro usando um Here-String</span><span class="sxs-lookup"><span data-stu-id="ea2d5-128">Example 3: Create a MultiString value in the registry using a Here-String</span></span>

<span data-ttu-id="ea2d5-129">Este exemplo cria um valor de multistring usando uma cadeia de caracteres here.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-129">This example creates a MultiString value using a Here-String.</span></span>

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

### <span data-ttu-id="ea2d5-130">Exemplo 4: criar um valor de cadeia de caracteres multistring no registro usando uma matriz</span><span class="sxs-lookup"><span data-stu-id="ea2d5-130">Example 4: Create a MultiString value in the registry using an array</span></span>

<span data-ttu-id="ea2d5-131">O exemplo mostra como usar uma matriz de valores para criar o `MultiString` valor.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-131">The example shows how to use an array of values to create the `MultiString` value.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'MultiString' -PropertyType MultiString -Value ('a','b','c')
$newValue.multistring[0]
```

```output
a
```

## <span data-ttu-id="ea2d5-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ea2d5-132">PARAMETERS</span></span>

### <span data-ttu-id="ea2d5-133">-Credential</span><span class="sxs-lookup"><span data-stu-id="ea2d5-133">-Credential</span></span>

<span data-ttu-id="ea2d5-134">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-134">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="ea2d5-135">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-135">The default is the current user.</span></span>

<span data-ttu-id="ea2d5-136">Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-136">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="ea2d5-137">Se você digitar um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-137">If you type a user name, you are prompted for a password.</span></span>

> [!NOTE]
> <span data-ttu-id="ea2d5-138">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-138">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="ea2d5-139">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="ea2d5-139">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="ea2d5-140">-Excluir</span><span class="sxs-lookup"><span data-stu-id="ea2d5-140">-Exclude</span></span>

<span data-ttu-id="ea2d5-141">Especifica, como uma matriz de cadeia de caracteres, uma propriedade ou propriedade que esse cmdlet exclui da operação.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-141">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="ea2d5-142">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="ea2d5-142">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="ea2d5-143">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="ea2d5-143">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="ea2d5-144">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-144">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="ea2d5-145">-Filter</span><span class="sxs-lookup"><span data-stu-id="ea2d5-145">-Filter</span></span>

<span data-ttu-id="ea2d5-146">Especifica um filtro no formato ou idioma do provedor.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-146">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="ea2d5-147">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="ea2d5-147">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="ea2d5-148">A sintaxe do filtro, incluindo o uso de caracteres curinga, depende do provedor.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-148">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span> <span data-ttu-id="ea2d5-149">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-149">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea2d5-150">-Force</span><span class="sxs-lookup"><span data-stu-id="ea2d5-150">-Force</span></span>

<span data-ttu-id="ea2d5-151">Força o cmdlet a criar uma propriedade em um objeto que, de outra forma, não pode ser acessado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-151">Forces the cmdlet to create a property on an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="ea2d5-152">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-152">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="ea2d5-153">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="ea2d5-153">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="ea2d5-154">-Incluir</span><span class="sxs-lookup"><span data-stu-id="ea2d5-154">-Include</span></span>

<span data-ttu-id="ea2d5-155">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-155">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="ea2d5-156">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="ea2d5-156">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="ea2d5-157">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="ea2d5-157">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="ea2d5-158">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-158">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="ea2d5-159">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ea2d5-159">-LiteralPath</span></span>

<span data-ttu-id="ea2d5-160">Especifica o caminho para o local atual da propriedade.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-160">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="ea2d5-161">Ao contrário do parâmetro **Path** , o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-161">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="ea2d5-162">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-162">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="ea2d5-163">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-163">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="ea2d5-164">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-164">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="ea2d5-165">-Name</span><span class="sxs-lookup"><span data-stu-id="ea2d5-165">-Name</span></span>

<span data-ttu-id="ea2d5-166">Especifica um nome para a nova propriedade.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-166">Specifies a name for the new property.</span></span>
<span data-ttu-id="ea2d5-167">Se a propriedade for uma entrada de registro, esse parâmetro especifica o nome da entrada.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-167">If the property is a registry entry, this parameter specifies the name of the entry.</span></span>

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

### <span data-ttu-id="ea2d5-168">-Path</span><span class="sxs-lookup"><span data-stu-id="ea2d5-168">-Path</span></span>

<span data-ttu-id="ea2d5-169">Especifica o caminho do item.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-169">Specifies the path of the item.</span></span>
<span data-ttu-id="ea2d5-170">Esse parâmetro identifica o item ao qual esse cmdlet adiciona a nova propriedade.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-170">This parameter identifies the item to which this cmdlet adds the new property.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea2d5-171">-PropertyType</span><span class="sxs-lookup"><span data-stu-id="ea2d5-171">-PropertyType</span></span>

<span data-ttu-id="ea2d5-172">Especifica o tipo de propriedade que este cmdlet adiciona.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-172">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="ea2d5-173">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="ea2d5-173">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ea2d5-174">**Cadeia de caracteres** : especifica uma cadeia de caracteres terminada em nulo.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-174">**String** : Specifies a null-terminated string.</span></span> <span data-ttu-id="ea2d5-175">Equivalente a **REG_SZ** .</span><span class="sxs-lookup"><span data-stu-id="ea2d5-175">Equivalent to **REG_SZ** .</span></span>
- <span data-ttu-id="ea2d5-176">**ExpandString** : especifica uma cadeia de caracteres terminada em nulo que contém referências não expandidas a variáveis de ambiente que são expandidas quando o valor é recuperado.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-176">**ExpandString** : Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="ea2d5-177">Equivalente a **REG_EXPAND_SZ** .</span><span class="sxs-lookup"><span data-stu-id="ea2d5-177">Equivalent to **REG_EXPAND_SZ** .</span></span>
- <span data-ttu-id="ea2d5-178">**Binary** : especifica dados binários em qualquer formulário.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-178">**Binary** : Specifies binary data in any form.</span></span> <span data-ttu-id="ea2d5-179">Equivalente a **REG_BINARY** .</span><span class="sxs-lookup"><span data-stu-id="ea2d5-179">Equivalent to **REG_BINARY** .</span></span>
- <span data-ttu-id="ea2d5-180">**DWORD** : especifica um número binário de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-180">**DWord** : Specifies a 32-bit binary number.</span></span> <span data-ttu-id="ea2d5-181">Equivalente a **REG_DWORD** .</span><span class="sxs-lookup"><span data-stu-id="ea2d5-181">Equivalent to **REG_DWORD** .</span></span>
- <span data-ttu-id="ea2d5-182">**Multistring** : especifica uma matriz de cadeias de caracteres terminadas em nulo terminadas por dois caracteres nulos.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-182">**MultiString** : Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="ea2d5-183">Equivalente a **REG_MULTI_SZ** .</span><span class="sxs-lookup"><span data-stu-id="ea2d5-183">Equivalent to **REG_MULTI_SZ** .</span></span>
- <span data-ttu-id="ea2d5-184">**QWORD** : especifica um número binário de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-184">**Qword** : Specifies a 64-bit binary number.</span></span> <span data-ttu-id="ea2d5-185">Equivalente a **REG_QWORD** .</span><span class="sxs-lookup"><span data-stu-id="ea2d5-185">Equivalent to **REG_QWORD** .</span></span>
- <span data-ttu-id="ea2d5-186">**Desconhecido** : indica um tipo de dados de registro sem suporte, como **REG_RESOURCE_LIST** .</span><span class="sxs-lookup"><span data-stu-id="ea2d5-186">**Unknown** : Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST** .</span></span>

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

### <span data-ttu-id="ea2d5-187">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="ea2d5-187">-UseTransaction</span></span>

<span data-ttu-id="ea2d5-188">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-188">Includes the command in the active transaction.</span></span>
<span data-ttu-id="ea2d5-189">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-189">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="ea2d5-190">Para obter mais informações, consulte about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-190">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="ea2d5-191">-Value</span><span class="sxs-lookup"><span data-stu-id="ea2d5-191">-Value</span></span>

<span data-ttu-id="ea2d5-192">Especifica o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-192">Specifies the property value.</span></span>
<span data-ttu-id="ea2d5-193">Se a propriedade for uma entrada de registro, esse parâmetro especifica o nome da entrada.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-193">If the property is a registry entry, this parameter specifies the value of the entry.</span></span>

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

### <span data-ttu-id="ea2d5-194">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ea2d5-194">-Confirm</span></span>

<span data-ttu-id="ea2d5-195">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-195">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ea2d5-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ea2d5-196">-WhatIf</span></span>

<span data-ttu-id="ea2d5-197">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-197">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ea2d5-198">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-198">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ea2d5-199">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ea2d5-199">CommonParameters</span></span>

<span data-ttu-id="ea2d5-200">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="ea2d5-200">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="ea2d5-201">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="ea2d5-201">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="ea2d5-202">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ea2d5-202">INPUTS</span></span>

### <span data-ttu-id="ea2d5-203">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ea2d5-203">None</span></span>

<span data-ttu-id="ea2d5-204">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-204">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="ea2d5-205">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ea2d5-205">OUTPUTS</span></span>

### <span data-ttu-id="ea2d5-206">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="ea2d5-206">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="ea2d5-207">`New-ItemProperty` Retorna um objeto personalizado que contém a nova propriedade.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-207">`New-ItemProperty` returns a custom object that contains the new property.</span></span>

## <span data-ttu-id="ea2d5-208">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ea2d5-208">NOTES</span></span>

<span data-ttu-id="ea2d5-209">`New-ItemProperty` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="ea2d5-209">`New-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="ea2d5-210">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="ea2d5-210">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="ea2d5-211">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="ea2d5-211">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="ea2d5-212">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ea2d5-212">RELATED LINKS</span></span>

[<span data-ttu-id="ea2d5-213">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ea2d5-213">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="ea2d5-214">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ea2d5-214">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="ea2d5-215">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ea2d5-215">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="ea2d5-216">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ea2d5-216">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="ea2d5-217">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ea2d5-217">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="ea2d5-218">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ea2d5-218">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="ea2d5-219">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ea2d5-219">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="ea2d5-220">about_Providers</span><span class="sxs-lookup"><span data-stu-id="ea2d5-220">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
