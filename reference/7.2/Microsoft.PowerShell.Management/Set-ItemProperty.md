---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ItemProperty
ms.openlocfilehash: 18383dc2b1e018e56864e412dfe75eca2b578a08
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598440"
---
# <span data-ttu-id="12637-102">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="12637-102">Set-ItemProperty</span></span>

## <span data-ttu-id="12637-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="12637-103">SYNOPSIS</span></span>
<span data-ttu-id="12637-104">Cria ou altera o valor de uma propriedade de um item.</span><span class="sxs-lookup"><span data-stu-id="12637-104">Creates or changes the value of a property of an item.</span></span>

## <span data-ttu-id="12637-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="12637-105">SYNTAX</span></span>

### <span data-ttu-id="12637-106">propertyValuePathSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="12637-106">propertyValuePathSet (Default)</span></span>

```
Set-ItemProperty [-Path] <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### <span data-ttu-id="12637-107">propertyPSObjectPathSet</span><span class="sxs-lookup"><span data-stu-id="12637-107">propertyPSObjectPathSet</span></span>

```
Set-ItemProperty [-Path] <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### <span data-ttu-id="12637-108">propertyValueLiteralPathSet</span><span class="sxs-lookup"><span data-stu-id="12637-108">propertyValueLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### <span data-ttu-id="12637-109">propertyPSObjectLiteralPathSet</span><span class="sxs-lookup"><span data-stu-id="12637-109">propertyPSObjectLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

## <span data-ttu-id="12637-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="12637-110">DESCRIPTION</span></span>

<span data-ttu-id="12637-111">O `Set-ItemProperty` cmdlet altera o valor da Propriedade do item especificado.</span><span class="sxs-lookup"><span data-stu-id="12637-111">The `Set-ItemProperty` cmdlet changes the value of the property of the specified item.</span></span>
<span data-ttu-id="12637-112">Você pode usar o cmdlet para estabelecer ou alterar as propriedades de itens.</span><span class="sxs-lookup"><span data-stu-id="12637-112">You can use the cmdlet to establish or change the properties of items.</span></span>
<span data-ttu-id="12637-113">Por exemplo, você pode usar `Set-ItemProperty` para definir o valor da propriedade **IsReadOnly** de um objeto de arquivo como `$True` .</span><span class="sxs-lookup"><span data-stu-id="12637-113">For example, you can use `Set-ItemProperty` to set the value of the **IsReadOnly** property of a file object to `$True`.</span></span>

<span data-ttu-id="12637-114">Você também usa `Set-ItemProperty` para criar e alterar dados e valores de registro.</span><span class="sxs-lookup"><span data-stu-id="12637-114">You also use `Set-ItemProperty` to create and change registry values and data.</span></span>
<span data-ttu-id="12637-115">Por exemplo, você pode adicionar uma nova entrada de registro a uma chave e estabelecer ou alterar seu valor.</span><span class="sxs-lookup"><span data-stu-id="12637-115">For example, you can add a new registry entry to a key and establish or change its value.</span></span>

## <span data-ttu-id="12637-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="12637-116">EXAMPLES</span></span>

### <span data-ttu-id="12637-117">Exemplo 1: definir uma propriedade de um arquivo</span><span class="sxs-lookup"><span data-stu-id="12637-117">Example 1: Set a property of a file</span></span>

<span data-ttu-id="12637-118">Esse comando define o valor da propriedade **IsReadOnly** do arquivo "final.doc" como "true".</span><span class="sxs-lookup"><span data-stu-id="12637-118">This command sets the value of the **IsReadOnly** property of the "final.doc" file to "true".</span></span>
<span data-ttu-id="12637-119">Ele usa o **caminho** para especificar o arquivo, o **nome** para especificar o nome da propriedade e o parâmetro de **valor** para especificar o novo valor.</span><span class="sxs-lookup"><span data-stu-id="12637-119">It uses **Path** to specify the file, **Name** to specify the name of the property, and the **Value** parameter to specify the new value.</span></span>

<span data-ttu-id="12637-120">O arquivo é um objeto **System. IO. FileInfo** e **IsReadOnly** é apenas uma de suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="12637-120">The file is a **System.IO.FileInfo** object and **IsReadOnly** is just one of its properties.</span></span>
<span data-ttu-id="12637-121">Para ver todas as propriedades, digite `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType
Property` .</span><span class="sxs-lookup"><span data-stu-id="12637-121">To see all of the properties, type `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType
Property`.</span></span>

<span data-ttu-id="12637-122">A `$true` variável automática representa um valor de "true".</span><span class="sxs-lookup"><span data-stu-id="12637-122">The `$true` automatic variable represents a value of "TRUE".</span></span>
<span data-ttu-id="12637-123">Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="12637-123">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
Set-ItemProperty -Path C:\GroupFiles\final.doc -Name IsReadOnly -Value $true
```

### <span data-ttu-id="12637-124">Exemplo 2: criar uma entrada e um valor de registro</span><span class="sxs-lookup"><span data-stu-id="12637-124">Example 2: Create a registry entry and value</span></span>

<span data-ttu-id="12637-125">Este exemplo mostra como usar `Set-ItemProperty` o para criar uma nova entrada de registro e atribuir um valor à entrada.</span><span class="sxs-lookup"><span data-stu-id="12637-125">This example shows how to use `Set-ItemProperty` to create a new registry entry and to assign a value to the entry.</span></span> <span data-ttu-id="12637-126">Ele cria a entrada "NoOfEmployees" na chave "ContosoCompany" na `HKLM\Software` chave e define seu valor como 823.</span><span class="sxs-lookup"><span data-stu-id="12637-126">It creates the "NoOfEmployees" entry in the "ContosoCompany" key in `HKLM\Software` key and sets its value to 823.</span></span>

<span data-ttu-id="12637-127">Como as entradas do registro são consideradas propriedades das chaves do registro, que são itens, você usa `Set-ItemProperty` para criar entradas do registro e para estabelecer e alterar seus valores.</span><span class="sxs-lookup"><span data-stu-id="12637-127">Because registry entries are considered to be properties of the registry keys, which are items, you use `Set-ItemProperty` to create registry entries, and to establish and change their values.</span></span>

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 823
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 823
```

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 824
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 824
```

<span data-ttu-id="12637-128">O primeiro comando cria a entrada do registro.</span><span class="sxs-lookup"><span data-stu-id="12637-128">The first command creates the registry entry.</span></span>
<span data-ttu-id="12637-129">Ele usa o **caminho** para especificar o caminho da `HKLM:` unidade e a chave "software\mycompany".</span><span class="sxs-lookup"><span data-stu-id="12637-129">It uses **Path** to specify the path of the `HKLM:` drive and the "Software\MyCompany" key.</span></span>
<span data-ttu-id="12637-130">O comando usa **nome** para especificar o nome e o **valor** da entrada para especificar um valor.</span><span class="sxs-lookup"><span data-stu-id="12637-130">The command uses **Name** to specify the entry name and **Value** to specify a value.</span></span>

<span data-ttu-id="12637-131">O segundo comando usa o `Get-ItemProperty` cmdlet para ver a nova entrada do registro.</span><span class="sxs-lookup"><span data-stu-id="12637-131">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>
<span data-ttu-id="12637-132">Se você usar os `Get-Item` `Get-ChildItem` cmdlets ou, as entradas não aparecerão porque são propriedades de uma chave, não itens ou itens filho.</span><span class="sxs-lookup"><span data-stu-id="12637-132">If you use the `Get-Item` or `Get-ChildItem` cmdlets, the entries do not appear because they are properties of a key, not items or child items.</span></span>

<span data-ttu-id="12637-133">O terceiro comando altera o valor da entrada **NoOfEmployees** para 824.</span><span class="sxs-lookup"><span data-stu-id="12637-133">The third command changes the value of the **NoOfEmployees** entry to 824.</span></span>

<span data-ttu-id="12637-134">Você também pode usar o `New-ItemProperty` cmdlet para criar a entrada do registro e seu valor e, em seguida, usar `Set-ItemProperty` para alterar o valor.</span><span class="sxs-lookup"><span data-stu-id="12637-134">You can also use the `New-ItemProperty` cmdlet to create the registry entry and its value and then use `Set-ItemProperty` to change the value.</span></span>

<span data-ttu-id="12637-135">Para obter mais informações sobre a `HKLM:` unidade, digite `Get-Help Get-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="12637-135">For more information about the `HKLM:` drive, type `Get-Help Get-PSDrive`.</span></span>
<span data-ttu-id="12637-136">Para obter mais informações sobre como usar o PowerShell para gerenciar o registro, digite `Get-Help Registry` .</span><span class="sxs-lookup"><span data-stu-id="12637-136">For more information about how to use PowerShell to manage the registry, type `Get-Help Registry`.</span></span>

### <span data-ttu-id="12637-137">Exemplo 3: modificar um item usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="12637-137">Example 3: Modify an item by using the pipeline</span></span>

<span data-ttu-id="12637-138">Estes comandos mostram como usar um operador de pipeline ( `|` ) para enviar um item para o `Set-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="12637-138">These commands show how to use a pipeline operator (`|`) to send an item to `Set-ItemProperty`.</span></span>

<span data-ttu-id="12637-139">A primeira parte do comando usa `Get-ChildItem` para obter um objeto que representa o arquivo "Weekly.txt".</span><span class="sxs-lookup"><span data-stu-id="12637-139">The first part of the command uses `Get-ChildItem` to get an object that represents the "Weekly.txt" file.</span></span> <span data-ttu-id="12637-140">O comando usa um operador de pipeline para o qual enviar o objeto de arquivo `Set-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="12637-140">The command uses a pipeline operator to send the file object to `Set-ItemProperty`.</span></span>
<span data-ttu-id="12637-141">O `Set-ItemProperty` comando usa os parâmetros **Name** e **Value** para especificar a propriedade e seu novo valor.</span><span class="sxs-lookup"><span data-stu-id="12637-141">The `Set-ItemProperty` command uses the **Name** and **Value** parameters to specify the property and its new value.</span></span>

<span data-ttu-id="12637-142">Esse comando é equivalente a usar o parâmetro **InputObject** para especificar o objeto que `Get-ChildItem` obtém.</span><span class="sxs-lookup"><span data-stu-id="12637-142">This command is equivalent to using the **InputObject** parameter to specify the object that `Get-ChildItem` gets.</span></span>

```powershell
Get-ChildItem weekly.txt | Set-ItemProperty -Name IsReadOnly -Value $True
```

## <span data-ttu-id="12637-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="12637-143">PARAMETERS</span></span>

### <span data-ttu-id="12637-144">-Credential</span><span class="sxs-lookup"><span data-stu-id="12637-144">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="12637-145">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12637-145">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="12637-146">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="12637-146">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="12637-147">-Excluir</span><span class="sxs-lookup"><span data-stu-id="12637-147">-Exclude</span></span>

<span data-ttu-id="12637-148">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet exclui na operação.</span><span class="sxs-lookup"><span data-stu-id="12637-148">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="12637-149">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="12637-149">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="12637-150">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="12637-150">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="12637-151">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="12637-151">Wildcard characters are permitted.</span></span> <span data-ttu-id="12637-152">O parâmetro **Exclude** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="12637-152">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="12637-153">-Filter</span><span class="sxs-lookup"><span data-stu-id="12637-153">-Filter</span></span>

<span data-ttu-id="12637-154">Especifica um filtro para qualificar o parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="12637-154">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="12637-155">O provedor [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) é o único provedor do PowerShell instalado que dá suporte ao uso de filtros.</span><span class="sxs-lookup"><span data-stu-id="12637-155">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="12637-156">Você pode encontrar a sintaxe para o idioma do filtro do **sistema de arquivos** em [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="12637-156">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="12637-157">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="12637-157">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="12637-158">-Force</span><span class="sxs-lookup"><span data-stu-id="12637-158">-Force</span></span>

<span data-ttu-id="12637-159">Força o cmdlet a definir uma propriedade em itens que, de outra forma, não podem ser acessados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="12637-159">Forces the cmdlet to set a property on items that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="12637-160">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="12637-160">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="12637-161">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="12637-161">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="12637-162">-Incluir</span><span class="sxs-lookup"><span data-stu-id="12637-162">-Include</span></span>

<span data-ttu-id="12637-163">Especifica, como uma matriz de cadeia de caracteres, um item ou itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="12637-163">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="12637-164">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="12637-164">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="12637-165">Insira um elemento ou padrão de caminho, como `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="12637-165">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="12637-166">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="12637-166">Wildcard characters are permitted.</span></span> <span data-ttu-id="12637-167">O parâmetro **include** é efetivo somente quando o comando inclui o conteúdo de um item, como `C:\Windows\*` , onde o caractere curinga especifica o conteúdo do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="12637-167">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="12637-168">-InputObject</span><span class="sxs-lookup"><span data-stu-id="12637-168">-InputObject</span></span>

<span data-ttu-id="12637-169">Especifica o objeto que tem as propriedades que esse cmdlet altera.</span><span class="sxs-lookup"><span data-stu-id="12637-169">Specifies the object that has the properties that this cmdlet changes.</span></span>
<span data-ttu-id="12637-170">Insira uma variável que contenha o objeto ou um comando que obtenha o objeto.</span><span class="sxs-lookup"><span data-stu-id="12637-170">Enter a variable that contains the object or a command that gets the object.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: propertyPSObjectPathSet, propertyPSObjectLiteralPathSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="12637-171">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="12637-171">-LiteralPath</span></span>

<span data-ttu-id="12637-172">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="12637-172">Specifies a path to one or more locations.</span></span> <span data-ttu-id="12637-173">O valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="12637-173">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="12637-174">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="12637-174">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="12637-175">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="12637-175">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="12637-176">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="12637-176">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="12637-177">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="12637-177">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyValueLiteralPathSet, propertyPSObjectLiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="12637-178">-Name</span><span class="sxs-lookup"><span data-stu-id="12637-178">-Name</span></span>

<span data-ttu-id="12637-179">Especifica o nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="12637-179">Specifies the name of the property.</span></span>

```yaml
Type: System.String
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="12637-180">-PassThru</span><span class="sxs-lookup"><span data-stu-id="12637-180">-PassThru</span></span>

<span data-ttu-id="12637-181">Retorna um objeto que representa a propriedade do item.</span><span class="sxs-lookup"><span data-stu-id="12637-181">Returns an object that represents the item property.</span></span>
<span data-ttu-id="12637-182">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="12637-182">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="12637-183">-Path</span><span class="sxs-lookup"><span data-stu-id="12637-183">-Path</span></span>

<span data-ttu-id="12637-184">Especifica o caminho dos itens com a propriedade a ser modificada.</span><span class="sxs-lookup"><span data-stu-id="12637-184">Specifies the path of the items with the property to modify.</span></span>
<span data-ttu-id="12637-185">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="12637-185">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyValuePathSet, propertyPSObjectPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="12637-186">-Type</span><span class="sxs-lookup"><span data-stu-id="12637-186">-Type</span></span>

<span data-ttu-id="12637-187">**Type** é um parâmetro dinâmico que o provedor do registro adiciona ao `Set-ItemProperty` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="12637-187">**Type** is a dynamic parameter that the Registry provider adds to the `Set-ItemProperty` cmdlet.</span></span>
<span data-ttu-id="12637-188">Esse parâmetro só funciona nas unidades do registro.</span><span class="sxs-lookup"><span data-stu-id="12637-188">This parameter only works in the registry drives.</span></span>

<span data-ttu-id="12637-189">Especifica o tipo de propriedade que este cmdlet adiciona.</span><span class="sxs-lookup"><span data-stu-id="12637-189">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="12637-190">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="12637-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="12637-191">**Cadeia de caracteres**: especifica uma cadeia de caracteres terminada em nulo.</span><span class="sxs-lookup"><span data-stu-id="12637-191">**String**: Specifies a null-terminated string.</span></span> <span data-ttu-id="12637-192">Equivalente a **REG_SZ**.</span><span class="sxs-lookup"><span data-stu-id="12637-192">Equivalent to **REG_SZ**.</span></span>
- <span data-ttu-id="12637-193">**ExpandString**: especifica uma cadeia de caracteres terminada em nulo que contém referências não expandidas a variáveis de ambiente que são expandidas quando o valor é recuperado.</span><span class="sxs-lookup"><span data-stu-id="12637-193">**ExpandString**: Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="12637-194">Equivalente a **REG_EXPAND_SZ**.</span><span class="sxs-lookup"><span data-stu-id="12637-194">Equivalent to **REG_EXPAND_SZ**.</span></span>
- <span data-ttu-id="12637-195">**Binary**: especifica dados binários em qualquer formulário.</span><span class="sxs-lookup"><span data-stu-id="12637-195">**Binary**: Specifies binary data in any form.</span></span> <span data-ttu-id="12637-196">Equivalente a **REG_BINARY**.</span><span class="sxs-lookup"><span data-stu-id="12637-196">Equivalent to **REG_BINARY**.</span></span>
- <span data-ttu-id="12637-197">**DWORD**: especifica um número binário de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="12637-197">**DWord**: Specifies a 32-bit binary number.</span></span> <span data-ttu-id="12637-198">Equivalente a **REG_DWORD**.</span><span class="sxs-lookup"><span data-stu-id="12637-198">Equivalent to **REG_DWORD**.</span></span>
- <span data-ttu-id="12637-199">**Multistring**: especifica uma matriz de cadeias de caracteres terminadas em nulo terminadas por dois caracteres nulos.</span><span class="sxs-lookup"><span data-stu-id="12637-199">**MultiString**: Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="12637-200">Equivalente a **REG_MULTI_SZ**.</span><span class="sxs-lookup"><span data-stu-id="12637-200">Equivalent to **REG_MULTI_SZ**.</span></span>
- <span data-ttu-id="12637-201">**QWORD**: especifica um número binário de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="12637-201">**Qword**: Specifies a 64-bit binary number.</span></span> <span data-ttu-id="12637-202">Equivalente a **REG_QWORD**.</span><span class="sxs-lookup"><span data-stu-id="12637-202">Equivalent to **REG_QWORD**.</span></span>
- <span data-ttu-id="12637-203">**Desconhecido**: indica um tipo de dados de registro sem suporte, como **REG_RESOURCE_LIST**.</span><span class="sxs-lookup"><span data-stu-id="12637-203">**Unknown**: Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST**.</span></span>

```yaml
Type: Microsoft.Win32.RegistryValueKind
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="12637-204">-Value</span><span class="sxs-lookup"><span data-stu-id="12637-204">-Value</span></span>

<span data-ttu-id="12637-205">Especifica o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="12637-205">Specifies the value of the property.</span></span>

```yaml
Type: System.Object
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="12637-206">-Confirm</span><span class="sxs-lookup"><span data-stu-id="12637-206">-Confirm</span></span>

<span data-ttu-id="12637-207">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="12637-207">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="12637-208">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="12637-208">-WhatIf</span></span>

<span data-ttu-id="12637-209">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="12637-209">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="12637-210">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="12637-210">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="12637-211">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="12637-211">CommonParameters</span></span>

<span data-ttu-id="12637-212">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="12637-212">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="12637-213">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="12637-213">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="12637-214">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="12637-214">INPUTS</span></span>

### <span data-ttu-id="12637-215">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="12637-215">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="12637-216">Você pode canalizar objetos para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="12637-216">You can pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="12637-217">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="12637-217">OUTPUTS</span></span>

### <span data-ttu-id="12637-218">Nenhum, System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="12637-218">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="12637-219">Esse cmdlet gera um objeto **PSCustomObject** que representa o item que foi alterado e seu novo valor de propriedade, se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="12637-219">This cmdlet generates a **PSCustomObject** object that represents the item that was changed and its new property value, if you specify the **PassThru** parameter.</span></span>
<span data-ttu-id="12637-220">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="12637-220">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="12637-221">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="12637-221">NOTES</span></span>

<span data-ttu-id="12637-222">`Set-ItemProperty` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="12637-222">`Set-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="12637-223">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="12637-223">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="12637-224">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="12637-224">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="12637-225">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="12637-225">RELATED LINKS</span></span>

[<span data-ttu-id="12637-226">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="12637-226">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="12637-227">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="12637-227">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="12637-228">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="12637-228">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="12637-229">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="12637-229">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="12637-230">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="12637-230">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="12637-231">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="12637-231">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="12637-232">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="12637-232">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="12637-233">about_Providers</span><span class="sxs-lookup"><span data-stu-id="12637-233">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

