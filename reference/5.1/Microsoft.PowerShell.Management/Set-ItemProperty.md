---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ItemProperty
ms.openlocfilehash: cbd1229721650823d9780517934c40a2287f4227
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692663"
---
# <span data-ttu-id="38f42-103">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="38f42-103">Set-ItemProperty</span></span>

## <span data-ttu-id="38f42-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="38f42-104">SYNOPSIS</span></span>
<span data-ttu-id="38f42-105">Cria ou altera o valor de uma propriedade de um item.</span><span class="sxs-lookup"><span data-stu-id="38f42-105">Creates or changes the value of a property of an item.</span></span>

## <span data-ttu-id="38f42-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="38f42-106">SYNTAX</span></span>

### <span data-ttu-id="38f42-107">propertyValuePathSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="38f42-107">propertyValuePathSet (Default)</span></span>

```
Set-ItemProperty [-Path] <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="38f42-108">propertyPSObjectPathSet</span><span class="sxs-lookup"><span data-stu-id="38f42-108">propertyPSObjectPathSet</span></span>

```
Set-ItemProperty [-Path] <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="38f42-109">propertyValueLiteralPathSet</span><span class="sxs-lookup"><span data-stu-id="38f42-109">propertyValueLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="38f42-110">propertyPSObjectLiteralPathSet</span><span class="sxs-lookup"><span data-stu-id="38f42-110">propertyPSObjectLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="38f42-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="38f42-111">DESCRIPTION</span></span>

<span data-ttu-id="38f42-112">O `Set-ItemProperty` cmdlet altera o valor da Propriedade do item especificado.</span><span class="sxs-lookup"><span data-stu-id="38f42-112">The `Set-ItemProperty` cmdlet changes the value of the property of the specified item.</span></span> <span data-ttu-id="38f42-113">Você pode usar o cmdlet para estabelecer ou alterar as propriedades de itens.</span><span class="sxs-lookup"><span data-stu-id="38f42-113">You can use the cmdlet to establish or change the properties of items.</span></span> <span data-ttu-id="38f42-114">Por exemplo, você pode usar `Set-ItemProperty` para definir o valor da propriedade **IsReadOnly** de um objeto de arquivo como `$True` .</span><span class="sxs-lookup"><span data-stu-id="38f42-114">For example, you can use `Set-ItemProperty` to set the value of the **IsReadOnly** property of a file object to `$True`.</span></span>

<span data-ttu-id="38f42-115">Você também usa `Set-ItemProperty` para criar e alterar dados e valores de registro.</span><span class="sxs-lookup"><span data-stu-id="38f42-115">You also use `Set-ItemProperty` to create and change registry values and data.</span></span>
<span data-ttu-id="38f42-116">Por exemplo, você pode adicionar uma nova entrada de registro a uma chave e estabelecer ou alterar seu valor.</span><span class="sxs-lookup"><span data-stu-id="38f42-116">For example, you can add a new registry entry to a key and establish or change its value.</span></span>

## <span data-ttu-id="38f42-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="38f42-117">EXAMPLES</span></span>

### <span data-ttu-id="38f42-118">Exemplo 1: definir uma propriedade de um arquivo</span><span class="sxs-lookup"><span data-stu-id="38f42-118">Example 1: Set a property of a file</span></span>

<span data-ttu-id="38f42-119">Esse comando define o valor da propriedade **IsReadOnly** do arquivo "final.doc" como "true".</span><span class="sxs-lookup"><span data-stu-id="38f42-119">This command sets the value of the **IsReadOnly** property of the "final.doc" file to "true".</span></span> <span data-ttu-id="38f42-120">Ele usa o **caminho** para especificar o arquivo, o **nome** para especificar o nome da propriedade e o parâmetro de **valor** para especificar o novo valor.</span><span class="sxs-lookup"><span data-stu-id="38f42-120">It uses **Path** to specify the file, **Name** to specify the name of the property, and the **Value** parameter to specify the new value.</span></span>

<span data-ttu-id="38f42-121">O arquivo é um objeto **System. IO. FileInfo** e **IsReadOnly** é apenas uma de suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="38f42-121">The file is a **System.IO.FileInfo** object and **IsReadOnly** is just one of its properties.</span></span>
<span data-ttu-id="38f42-122">Para ver todas as propriedades, digite `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType Property` .</span><span class="sxs-lookup"><span data-stu-id="38f42-122">To see all of the properties, type `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType Property`.</span></span>

<span data-ttu-id="38f42-123">A `$true` variável automática representa um valor de "true".</span><span class="sxs-lookup"><span data-stu-id="38f42-123">The `$true` automatic variable represents a value of "TRUE".</span></span>
<span data-ttu-id="38f42-124">Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="38f42-124">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
Set-ItemProperty -Path C:\GroupFiles\final.doc -Name IsReadOnly -Value $true
```

### <span data-ttu-id="38f42-125">Exemplo 2: criar uma entrada e um valor de registro</span><span class="sxs-lookup"><span data-stu-id="38f42-125">Example 2: Create a registry entry and value</span></span>

<span data-ttu-id="38f42-126">Este exemplo mostra como usar `Set-ItemProperty` o para criar uma nova entrada de registro e atribuir um valor à entrada.</span><span class="sxs-lookup"><span data-stu-id="38f42-126">This example shows how to use `Set-ItemProperty` to create a new registry entry and to assign a value to the entry.</span></span> <span data-ttu-id="38f42-127">Ele cria a entrada "NoOfEmployees" na chave "ContosoCompany" na chave "HKLM\Software" e define seu valor como 823.</span><span class="sxs-lookup"><span data-stu-id="38f42-127">It creates the "NoOfEmployees" entry in the "ContosoCompany" key in "HKLM\Software" key and sets its value to 823.</span></span>

<span data-ttu-id="38f42-128">Como as entradas do registro são consideradas propriedades das chaves do registro, que são itens, você usa `Set-ItemProperty` para criar entradas do registro e para estabelecer e alterar seus valores.</span><span class="sxs-lookup"><span data-stu-id="38f42-128">Because registry entries are considered to be properties of the registry keys, which are items, you use `Set-ItemProperty` to create registry entries, and to establish and change their values.</span></span>

<span data-ttu-id="38f42-129">O primeiro comando cria a entrada do registro.</span><span class="sxs-lookup"><span data-stu-id="38f42-129">The first command creates the registry entry.</span></span>
<span data-ttu-id="38f42-130">Ele usa o **caminho** para especificar o caminho da `HKLM:` unidade e a chave "software\mycompany".</span><span class="sxs-lookup"><span data-stu-id="38f42-130">It uses **Path** to specify the path of the `HKLM:` drive and the "Software\MyCompany" key.</span></span>
<span data-ttu-id="38f42-131">O comando usa **nome** para especificar o nome e o **valor** da entrada para especificar um valor.</span><span class="sxs-lookup"><span data-stu-id="38f42-131">The command uses **Name** to specify the entry name and **Value** to specify a value.</span></span>

<span data-ttu-id="38f42-132">O segundo comando usa o `Get-ItemProperty` cmdlet para ver a nova entrada do registro.</span><span class="sxs-lookup"><span data-stu-id="38f42-132">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span> <span data-ttu-id="38f42-133">Se você usar os `Get-Item` `Get-ChildItem` cmdlets ou, as entradas não aparecerão porque são propriedades de uma chave, não itens ou itens filho.</span><span class="sxs-lookup"><span data-stu-id="38f42-133">If you use the `Get-Item` or `Get-ChildItem` cmdlets, the entries do not appear because they are properties of a key, not items or child items.</span></span>

<span data-ttu-id="38f42-134">O terceiro comando altera o valor da entrada **NoOfEmployees** para 824.</span><span class="sxs-lookup"><span data-stu-id="38f42-134">The third command changes the value of the **NoOfEmployees** entry to 824.</span></span>

<span data-ttu-id="38f42-135">Você também pode usar o `New-ItemProperty` cmdlet para criar a entrada do registro e seu valor e, em seguida, usar `Set-ItemProperty` para alterar o valor.</span><span class="sxs-lookup"><span data-stu-id="38f42-135">You can also use the `New-ItemProperty` cmdlet to create the registry entry and its value and then use `Set-ItemProperty` to change the value.</span></span>

<span data-ttu-id="38f42-136">Para obter mais informações sobre a `HKLM:` unidade, digite `Get-Help Get-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="38f42-136">For more information about the `HKLM:` drive, type `Get-Help Get-PSDrive`.</span></span>
<span data-ttu-id="38f42-137">Para obter mais informações sobre como usar o PowerShell para gerenciar o registro, digite `Get-Help Registry` .</span><span class="sxs-lookup"><span data-stu-id="38f42-137">For more information about how to use PowerShell to manage the registry, type `Get-Help Registry`.</span></span>

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 823
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```output
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

```output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 824
```

### <span data-ttu-id="38f42-138">Exemplo 3: modificar um item usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="38f42-138">Example 3: Modify an item by using the pipeline</span></span>

<span data-ttu-id="38f42-139">Estes comandos mostram como usar um operador de pipeline ( `|` ) para enviar um item para o `Set-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="38f42-139">These commands show how to use a pipeline operator (`|`) to send an item to `Set-ItemProperty`.</span></span>

<span data-ttu-id="38f42-140">A primeira parte do comando usa `Get-ChildItem` para obter um objeto que representa o arquivo "Weekly.txt".</span><span class="sxs-lookup"><span data-stu-id="38f42-140">The first part of the command uses `Get-ChildItem` to get an object that represents the "Weekly.txt" file.</span></span>
<span data-ttu-id="38f42-141">O comando usa um operador de pipeline para o qual enviar o objeto de arquivo `Set-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="38f42-141">The command uses a pipeline operator to send the file object to `Set-ItemProperty`.</span></span>
<span data-ttu-id="38f42-142">O `Set-ItemProperty` comando usa os parâmetros **Name** e **Value** para especificar a propriedade e seu novo valor.</span><span class="sxs-lookup"><span data-stu-id="38f42-142">The `Set-ItemProperty` command uses the **Name** and **Value** parameters to specify the property and its new value.</span></span>

<span data-ttu-id="38f42-143">Esse comando é equivalente a usar o parâmetro **InputObject** para especificar o objeto que `Get-ChildItem` obtém.</span><span class="sxs-lookup"><span data-stu-id="38f42-143">This command is equivalent to using the **InputObject** parameter to specify the object that `Get-ChildItem` gets.</span></span>

```powershell
Get-ChildItem weekly.txt | Set-ItemProperty -Name IsReadOnly -Value $True
```

## <span data-ttu-id="38f42-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="38f42-144">PARAMETERS</span></span>

### <span data-ttu-id="38f42-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="38f42-145">-Credential</span></span>

<span data-ttu-id="38f42-146">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="38f42-146">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="38f42-147">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="38f42-147">The default is the current user.</span></span>

<span data-ttu-id="38f42-148">Digite um nome de usuário, como "User01" ou "Domínio01 \ Usuário01", ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38f42-148">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="38f42-149">Se você digitar um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="38f42-149">If you type a user name, you are prompted for a password.</span></span>

> [!NOTE]
> <span data-ttu-id="38f42-150">Não há suporte para esse parâmetro em nenhum provedor instalado com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38f42-150">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="38f42-151">Para representar outro usuário ou elevar suas credenciais ao executar esse cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="38f42-151">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="38f42-152">-Excluir</span><span class="sxs-lookup"><span data-stu-id="38f42-152">-Exclude</span></span>

<span data-ttu-id="38f42-153">Especifica os itens sobre os quais o cmdlet não funciona e inclui todos os outros.</span><span class="sxs-lookup"><span data-stu-id="38f42-153">Specifies those items upon which the cmdlet does not act, and includes all others.</span></span>
<span data-ttu-id="38f42-154">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="38f42-154">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="38f42-155">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="38f42-155">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="38f42-156">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="38f42-156">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="38f42-157">-Filter</span><span class="sxs-lookup"><span data-stu-id="38f42-157">-Filter</span></span>

<span data-ttu-id="38f42-158">Especifica um filtro no formato ou idioma do provedor.</span><span class="sxs-lookup"><span data-stu-id="38f42-158">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="38f42-159">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="38f42-159">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="38f42-160">A sintaxe do filtro, incluindo o uso de caracteres curinga, depende do provedor.</span><span class="sxs-lookup"><span data-stu-id="38f42-160">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="38f42-161">Os filtros são mais eficientes do que outros parâmetros, porque o provedor os aplica quando o cmdlet obtém os objetos em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="38f42-161">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="38f42-162">-Force</span><span class="sxs-lookup"><span data-stu-id="38f42-162">-Force</span></span>

<span data-ttu-id="38f42-163">Força o cmdlet a definir uma propriedade em itens que, de outra forma, não podem ser acessados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="38f42-163">Forces the cmdlet to set a property on items that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="38f42-164">A implementação varia de provedor para provedor.</span><span class="sxs-lookup"><span data-stu-id="38f42-164">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="38f42-165">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="38f42-165">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="38f42-166">-Incluir</span><span class="sxs-lookup"><span data-stu-id="38f42-166">-Include</span></span>

<span data-ttu-id="38f42-167">Especifica somente os itens sobre os quais o cmdlet atua, o que exclui todos os outros.</span><span class="sxs-lookup"><span data-stu-id="38f42-167">Specifies only those items upon which the cmdlet acts, which excludes all others.</span></span>
<span data-ttu-id="38f42-168">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="38f42-168">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="38f42-169">Insira um padrão ou elemento de caminho, como "\*.txt".</span><span class="sxs-lookup"><span data-stu-id="38f42-169">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="38f42-170">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="38f42-170">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="38f42-171">-InputObject</span><span class="sxs-lookup"><span data-stu-id="38f42-171">-InputObject</span></span>

<span data-ttu-id="38f42-172">Especifica o objeto que tem as propriedades que esse cmdlet altera.</span><span class="sxs-lookup"><span data-stu-id="38f42-172">Specifies the object that has the properties that this cmdlet changes.</span></span>
<span data-ttu-id="38f42-173">Insira uma variável que contenha o objeto ou um comando que obtenha o objeto.</span><span class="sxs-lookup"><span data-stu-id="38f42-173">Enter a variable that contains the object or a command that gets the object.</span></span>

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

### <span data-ttu-id="38f42-174">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="38f42-174">-LiteralPath</span></span>

<span data-ttu-id="38f42-175">Especifica um caminho da propriedade item.</span><span class="sxs-lookup"><span data-stu-id="38f42-175">Specifies a path of the item property.</span></span>
<span data-ttu-id="38f42-176">Ao contrário do parâmetro **Path**, o valor de **LiteralPath** é usado exatamente como digitado.</span><span class="sxs-lookup"><span data-stu-id="38f42-176">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="38f42-177">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="38f42-177">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="38f42-178">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="38f42-178">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="38f42-179">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="38f42-179">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyValueLiteralPathSet, propertyPSObjectLiteralPathSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="38f42-180">-Name</span><span class="sxs-lookup"><span data-stu-id="38f42-180">-Name</span></span>

<span data-ttu-id="38f42-181">Especifica o nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="38f42-181">Specifies the name of the property.</span></span>

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

### <span data-ttu-id="38f42-182">-PassThru</span><span class="sxs-lookup"><span data-stu-id="38f42-182">-PassThru</span></span>

<span data-ttu-id="38f42-183">Retorna um objeto que representa a propriedade do item.</span><span class="sxs-lookup"><span data-stu-id="38f42-183">Returns an object that represents the item property.</span></span>
<span data-ttu-id="38f42-184">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="38f42-184">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="38f42-185">-Path</span><span class="sxs-lookup"><span data-stu-id="38f42-185">-Path</span></span>

<span data-ttu-id="38f42-186">Especifica o caminho dos itens com a propriedade a ser modificada.</span><span class="sxs-lookup"><span data-stu-id="38f42-186">Specifies the path of the items with the property to modify.</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyValuePathSet, propertyPSObjectPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="38f42-187">-Type</span><span class="sxs-lookup"><span data-stu-id="38f42-187">-Type</span></span>

<span data-ttu-id="38f42-188">**Type** é um parâmetro dinâmico que o provedor do registro adiciona ao `Set-ItemProperty` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38f42-188">**Type** is a dynamic parameter that the Registry provider adds to the `Set-ItemProperty` cmdlet.</span></span>
<span data-ttu-id="38f42-189">Esse parâmetro só funciona nas unidades do registro.</span><span class="sxs-lookup"><span data-stu-id="38f42-189">This parameter only works in the registry drives.</span></span>

<span data-ttu-id="38f42-190">Especifica o tipo de propriedade que este cmdlet adiciona.</span><span class="sxs-lookup"><span data-stu-id="38f42-190">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="38f42-191">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="38f42-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="38f42-192">**Cadeia de caracteres**: especifica uma cadeia de caracteres terminada em nulo.</span><span class="sxs-lookup"><span data-stu-id="38f42-192">**String**: Specifies a null-terminated string.</span></span> <span data-ttu-id="38f42-193">Equivalente a **REG_SZ**.</span><span class="sxs-lookup"><span data-stu-id="38f42-193">Equivalent to **REG_SZ**.</span></span>
- <span data-ttu-id="38f42-194">**ExpandString**: especifica uma cadeia de caracteres terminada em nulo que contém referências não expandidas a variáveis de ambiente que são expandidas quando o valor é recuperado.</span><span class="sxs-lookup"><span data-stu-id="38f42-194">**ExpandString**: Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="38f42-195">Equivalente a **REG_EXPAND_SZ**.</span><span class="sxs-lookup"><span data-stu-id="38f42-195">Equivalent to **REG_EXPAND_SZ**.</span></span>
- <span data-ttu-id="38f42-196">**Binary**: especifica dados binários em qualquer formulário.</span><span class="sxs-lookup"><span data-stu-id="38f42-196">**Binary**: Specifies binary data in any form.</span></span> <span data-ttu-id="38f42-197">Equivalente a **REG_BINARY**.</span><span class="sxs-lookup"><span data-stu-id="38f42-197">Equivalent to **REG_BINARY**.</span></span>
- <span data-ttu-id="38f42-198">**DWORD**: especifica um número binário de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="38f42-198">**DWord**: Specifies a 32-bit binary number.</span></span> <span data-ttu-id="38f42-199">Equivalente a **REG_DWORD**.</span><span class="sxs-lookup"><span data-stu-id="38f42-199">Equivalent to **REG_DWORD**.</span></span>
- <span data-ttu-id="38f42-200">**Multistring**: especifica uma matriz de cadeias de caracteres terminadas em nulo terminadas por dois caracteres nulos.</span><span class="sxs-lookup"><span data-stu-id="38f42-200">**MultiString**: Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="38f42-201">Equivalente a **REG_MULTI_SZ**.</span><span class="sxs-lookup"><span data-stu-id="38f42-201">Equivalent to **REG_MULTI_SZ**.</span></span>
- <span data-ttu-id="38f42-202">**QWORD**: especifica um número binário de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="38f42-202">**Qword**: Specifies a 64-bit binary number.</span></span> <span data-ttu-id="38f42-203">Equivalente a **REG_QWORD**.</span><span class="sxs-lookup"><span data-stu-id="38f42-203">Equivalent to **REG_QWORD**.</span></span>
- <span data-ttu-id="38f42-204">**Desconhecido**: indica um tipo de dados de registro sem suporte, como **REG_RESOURCE_LIST**.</span><span class="sxs-lookup"><span data-stu-id="38f42-204">**Unknown**: Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST**.</span></span>

```yaml
Type: RegistryValueKind
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="38f42-205">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="38f42-205">-UseTransaction</span></span>

<span data-ttu-id="38f42-206">Inclui o comando na transação ativa.</span><span class="sxs-lookup"><span data-stu-id="38f42-206">Includes the command in the active transaction.</span></span>
<span data-ttu-id="38f42-207">Este parâmetro é válido somente quando uma transação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="38f42-207">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="38f42-208">Para obter mais informações, consulte [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="38f42-208">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="38f42-209">-Value</span><span class="sxs-lookup"><span data-stu-id="38f42-209">-Value</span></span>

<span data-ttu-id="38f42-210">Especifica o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="38f42-210">Specifies the value of the property.</span></span>

```yaml
Type: Object
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="38f42-211">-Confirm</span><span class="sxs-lookup"><span data-stu-id="38f42-211">-Confirm</span></span>

<span data-ttu-id="38f42-212">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38f42-212">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="38f42-213">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="38f42-213">-WhatIf</span></span>

<span data-ttu-id="38f42-214">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="38f42-214">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="38f42-215">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="38f42-215">The cmdlet is not run.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="38f42-216">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="38f42-216">CommonParameters</span></span>

<span data-ttu-id="38f42-217">Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="38f42-217">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="38f42-218">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="38f42-218">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="38f42-219">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="38f42-219">INPUTS</span></span>

### <span data-ttu-id="38f42-220">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="38f42-220">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="38f42-221">Você pode canalizar objetos para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="38f42-221">You can pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="38f42-222">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="38f42-222">OUTPUTS</span></span>

### <span data-ttu-id="38f42-223">Nenhum, System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="38f42-223">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="38f42-224">Esse cmdlet gera um objeto **PSCustomObject** que representa o item que foi alterado e seu novo valor de propriedade, se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="38f42-224">This cmdlet generates a **PSCustomObject** object that represents the item that was changed and its new property value, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="38f42-225">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="38f42-225">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="38f42-226">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="38f42-226">NOTES</span></span>

<span data-ttu-id="38f42-227">`Set-ItemProperty` o é projetado para trabalhar com os dados expostos por qualquer provedor.</span><span class="sxs-lookup"><span data-stu-id="38f42-227">`Set-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="38f42-228">Para listar os provedores disponíveis em sua sessão, digite `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="38f42-228">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="38f42-229">Para obter mais informações, consulte [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="38f42-229">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="38f42-230">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="38f42-230">RELATED LINKS</span></span>

[<span data-ttu-id="38f42-231">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="38f42-231">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="38f42-232">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="38f42-232">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="38f42-233">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="38f42-233">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="38f42-234">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="38f42-234">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="38f42-235">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="38f42-235">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="38f42-236">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="38f42-236">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="38f42-237">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="38f42-237">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)
