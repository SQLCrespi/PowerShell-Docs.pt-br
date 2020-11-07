---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 03/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-acl?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Acl
ms.openlocfilehash: 118c3e563743cee03dc7a75ca68e0979c1522f07
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347067"
---
# <span data-ttu-id="0ff15-103">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="0ff15-103">Get-Acl</span></span>

## <span data-ttu-id="0ff15-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0ff15-104">SYNOPSIS</span></span>
<span data-ttu-id="0ff15-105">Obtém o descritor de segurança para um recurso, como um arquivo ou chave do registro.</span><span class="sxs-lookup"><span data-stu-id="0ff15-105">Gets the security descriptor for a resource, such as a file or registry key.</span></span>

## <span data-ttu-id="0ff15-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0ff15-106">SYNTAX</span></span>

### <span data-ttu-id="0ff15-107">ByPath (padrão)</span><span class="sxs-lookup"><span data-stu-id="0ff15-107">ByPath (Default)</span></span>

```
Get-Acl [[-Path] <String[]>] [-Audit] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="0ff15-108">ByInputObject</span><span class="sxs-lookup"><span data-stu-id="0ff15-108">ByInputObject</span></span>

```
Get-Acl -InputObject <PSObject> [-Audit] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="0ff15-109">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="0ff15-109">ByLiteralPath</span></span>

```
Get-Acl [-LiteralPath <String[]>] [-Audit] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="0ff15-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0ff15-110">DESCRIPTION</span></span>

<span data-ttu-id="0ff15-111">O `Get-Acl` cmdlet obtém objetos que representam o descritor de segurança de um arquivo ou recurso.</span><span class="sxs-lookup"><span data-stu-id="0ff15-111">The `Get-Acl` cmdlet gets objects that represent the security descriptor of a file or resource.</span></span> <span data-ttu-id="0ff15-112">O descritor de segurança contém as listas de controle de acesso (ACLs) do recurso.</span><span class="sxs-lookup"><span data-stu-id="0ff15-112">The security descriptor contains the access control lists (ACLs) of the resource.</span></span> <span data-ttu-id="0ff15-113">A ACL especifica as permissões que os usuários e grupos de usuários têm para acessar o recurso.</span><span class="sxs-lookup"><span data-stu-id="0ff15-113">The ACL specifies the permissions that users and user groups have to access the resource.</span></span>

<span data-ttu-id="0ff15-114">A partir do Windows PowerShell 3,0, você pode usar o parâmetro **InputObject** de `Get-Acl` para obter o descritor de segurança de objetos que não têm um caminho.</span><span class="sxs-lookup"><span data-stu-id="0ff15-114">Beginning in Windows PowerShell 3.0, you can use the **InputObject** parameter of `Get-Acl` to get the security descriptor of objects that do not have a path.</span></span>

## <span data-ttu-id="0ff15-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0ff15-115">EXAMPLES</span></span>

### <span data-ttu-id="0ff15-116">Exemplo 1-obter uma ACL para uma pasta</span><span class="sxs-lookup"><span data-stu-id="0ff15-116">Example 1- Get an ACL for a folder</span></span>

<span data-ttu-id="0ff15-117">Este exemplo obtém o descritor de segurança do `C:\Windows` diretório.</span><span class="sxs-lookup"><span data-stu-id="0ff15-117">This example gets the security descriptor of the `C:\Windows` directory.</span></span>

```powershell
Get-Acl C:\Windows
```

### <span data-ttu-id="0ff15-118">Exemplo 2-obter uma ACL para uma pasta usando curingas</span><span class="sxs-lookup"><span data-stu-id="0ff15-118">Example 2 - Get an ACL for a folder using wildcards</span></span>

<span data-ttu-id="0ff15-119">Este exemplo obtém o caminho e o SDDL do PowerShell para todos os `.log` arquivos no `C:\Windows` diretório cujos nomes começam com `s` .</span><span class="sxs-lookup"><span data-stu-id="0ff15-119">This example gets the PowerShell path and SDDL for all of the `.log` files in the `C:\Windows` directory whose names begin with `s`.</span></span>

```powershell
Get-Acl C:\Windows\s*.log | Format-List -Property PSPath, Sddl
```

<span data-ttu-id="0ff15-120">O comando usa o `Get-Acl` cmdlet para obter objetos que representam os descritores de segurança de cada arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="0ff15-120">The command uses the `Get-Acl` cmdlet to get objects representing the security descriptors of each log file.</span></span> <span data-ttu-id="0ff15-121">Ele usa um operador de pipeline ( `|` ) para enviar os resultados para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0ff15-121">It uses a pipeline operator (`|`) to send the results to the `Format-List` cmdlet.</span></span> <span data-ttu-id="0ff15-122">O comando usa o parâmetro **Property** de `Format-List` para exibir somente as propriedades **PSPath** e **SDDL** de cada objeto de descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="0ff15-122">The command uses the **Property** parameter of `Format-List` to display only the **PsPath** and **SDDL** properties of each security descriptor object.</span></span>

<span data-ttu-id="0ff15-123">As listas geralmente são usadas no PowerShell, porque os valores longos aparecem truncados nas tabelas.</span><span class="sxs-lookup"><span data-stu-id="0ff15-123">Lists are often used in PowerShell, because long values appear truncated in tables.</span></span>

<span data-ttu-id="0ff15-124">Os valores **SDDL** são importantes para administradores de sistema, porque eles são cadeias de caracteres de texto simples que contêm todas as informações no descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="0ff15-124">The **SDDL** values are valuable to system administrators, because they are simple text strings that contain all of the information in the security descriptor.</span></span> <span data-ttu-id="0ff15-125">Assim, é fácil que ocorra com eles passar e armazenar, eles que podem ser analisados quando necessário.</span><span class="sxs-lookup"><span data-stu-id="0ff15-125">As such, they are easy to pass and store, and they can be parsed when needed.</span></span>

### <span data-ttu-id="0ff15-126">Exemplo 3-obter a contagem de entradas de auditoria para uma ACL</span><span class="sxs-lookup"><span data-stu-id="0ff15-126">Example 3 - Get count of Audit entries for an ACL</span></span>

<span data-ttu-id="0ff15-127">Este exemplo obtém os descritores de segurança dos `.log` arquivos no `C:\Windows` diretório cujos nomes começam com `s` .</span><span class="sxs-lookup"><span data-stu-id="0ff15-127">This example gets the security descriptors of the `.log` files in the `C:\Windows` directory whose names begin with `s`.</span></span>

```powershell
Get-Acl C:\Windows\s*.log -Audit | ForEach-Object { $_.Audit.Count }
```

<span data-ttu-id="0ff15-128">Ele usa o parâmetro **Audit** para obter os registros de auditoria da SACL no descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="0ff15-128">It uses the **Audit** parameter to get the audit records from the SACL in the security descriptor.</span></span>
<span data-ttu-id="0ff15-129">Em seguida, ele usa o `ForEach-Object` cmdlet para contar o número de registros de auditoria associados a cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="0ff15-129">Then it uses the `ForEach-Object` cmdlet to count the number of audit records associated with each file.</span></span> <span data-ttu-id="0ff15-130">O resultado é uma lista de números que representam o número de registros de auditoria para cada arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="0ff15-130">The result is a list of numbers representing the number of audit records for each log file.</span></span>

### <span data-ttu-id="0ff15-131">Exemplo 4-obter uma ACL para uma chave do registro</span><span class="sxs-lookup"><span data-stu-id="0ff15-131">Example 4 - Get an ACL for a registry key</span></span>

<span data-ttu-id="0ff15-132">Este exemplo usa o `Get-Acl` cmdlet para obter o descritor de segurança da subchave de controle ( `HKLM:\SYSTEM\CurrentControlSet\Control` ) do registro.</span><span class="sxs-lookup"><span data-stu-id="0ff15-132">This example uses the `Get-Acl` cmdlet to get the security descriptor of the Control subkey (`HKLM:\SYSTEM\CurrentControlSet\Control`) of the registry.</span></span>

```powershell
Get-Acl -Path HKLM:\System\CurrentControlSet\Control | Format-List
```

<span data-ttu-id="0ff15-133">O parâmetro **path** especifica a subchave Control.</span><span class="sxs-lookup"><span data-stu-id="0ff15-133">The **Path** parameter specifies the Control subkey.</span></span> <span data-ttu-id="0ff15-134">O operador de pipeline ( `|` ) passa o descritor de segurança que `Get-Acl` Obtém o `Format-List` comando, que formata as propriedades do descritor de segurança como uma lista para que sejam fáceis de ler.</span><span class="sxs-lookup"><span data-stu-id="0ff15-134">The pipeline operator (`|`) passes the security descriptor that `Get-Acl` gets to the `Format-List` command, which formats the properties of the security descriptor as a list so that they are easy to read.</span></span>

### <span data-ttu-id="0ff15-135">Exemplo 5-obter uma ACL usando **InputObject**</span><span class="sxs-lookup"><span data-stu-id="0ff15-135">Example 5 - Get an ACL using **InputObject**</span></span>

<span data-ttu-id="0ff15-136">Este exemplo usa o parâmetro **InputObject** de `Get-Acl` para obter o descritor de segurança de um objeto de subsistema de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="0ff15-136">This example uses the **InputObject** parameter of `Get-Acl` to get the security descriptor of a storage subsystem object.</span></span>

```powershell
Get-Acl -InputObject (Get-StorageSubSystem -Name S087)
```

## <span data-ttu-id="0ff15-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0ff15-137">PARAMETERS</span></span>

### <span data-ttu-id="0ff15-138">-Auditoria</span><span class="sxs-lookup"><span data-stu-id="0ff15-138">-Audit</span></span>

<span data-ttu-id="0ff15-139">Obtém os dados de auditoria para o descritor de segurança da lista de controle de acesso do sistema (SACL).</span><span class="sxs-lookup"><span data-stu-id="0ff15-139">Gets the audit data for the security descriptor from the system access control list (SACL).</span></span>

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

### <span data-ttu-id="0ff15-140">-Excluir</span><span class="sxs-lookup"><span data-stu-id="0ff15-140">-Exclude</span></span>

<span data-ttu-id="0ff15-141">Omite os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="0ff15-141">Omits the specified items.</span></span> <span data-ttu-id="0ff15-142">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="0ff15-142">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="0ff15-143">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="0ff15-143">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="0ff15-144">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0ff15-144">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="0ff15-145">-Filter</span><span class="sxs-lookup"><span data-stu-id="0ff15-145">-Filter</span></span>

<span data-ttu-id="0ff15-146">Especifica um filtro no formato ou linguagem do provedor.</span><span class="sxs-lookup"><span data-stu-id="0ff15-146">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="0ff15-147">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="0ff15-147">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="0ff15-148">A sintaxe do filtro, incluindo o uso de caracteres curingas, depende do provedor.</span><span class="sxs-lookup"><span data-stu-id="0ff15-148">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="0ff15-149">Os filtros são mais eficientes do que outros parâmetros, pois o provedor os aplica ao obter os objetos, em vez de fazer com que o PowerShell filtre os objetos depois que eles são recuperados.</span><span class="sxs-lookup"><span data-stu-id="0ff15-149">Filters are more efficient than other parameters, because the provider applies them when getting the objects, rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="0ff15-150">-Incluir</span><span class="sxs-lookup"><span data-stu-id="0ff15-150">-Include</span></span>

<span data-ttu-id="0ff15-151">Obtém somente os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="0ff15-151">Gets only the specified items.</span></span> <span data-ttu-id="0ff15-152">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="0ff15-152">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="0ff15-153">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="0ff15-153">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="0ff15-154">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0ff15-154">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="0ff15-155">-Path</span><span class="sxs-lookup"><span data-stu-id="0ff15-155">-Path</span></span>

<span data-ttu-id="0ff15-156">Especifica o caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="0ff15-156">Specifies the path to a resource.</span></span> <span data-ttu-id="0ff15-157">`Get-Acl` Obtém o descritor de segurança do recurso indicado pelo caminho.</span><span class="sxs-lookup"><span data-stu-id="0ff15-157">`Get-Acl` gets the security descriptor of the resource indicated by the path.</span></span> <span data-ttu-id="0ff15-158">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0ff15-158">Wildcards are permitted.</span></span> <span data-ttu-id="0ff15-159">Se você omitir o parâmetro **path** , `Get-Acl` obterá o descritor de segurança do diretório atual.</span><span class="sxs-lookup"><span data-stu-id="0ff15-159">If you omit the **Path** parameter, `Get-Acl` gets the security descriptor of the current directory.</span></span>

<span data-ttu-id="0ff15-160">O nome do parâmetro ("Path") é opcional.</span><span class="sxs-lookup"><span data-stu-id="0ff15-160">The parameter name ("Path") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="0ff15-161">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0ff15-161">-InputObject</span></span>

<span data-ttu-id="0ff15-162">Obtém o descritor de segurança para o objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="0ff15-162">Gets the security descriptor for the specified object.</span></span> <span data-ttu-id="0ff15-163">Insira uma variável que contenha o objeto ou um comando que obtenha o objeto.</span><span class="sxs-lookup"><span data-stu-id="0ff15-163">Enter a variable that contains the object or a command that gets the object.</span></span>

<span data-ttu-id="0ff15-164">Não é possível canalizar um objeto, que não seja um caminho, para `Get-Acl` .</span><span class="sxs-lookup"><span data-stu-id="0ff15-164">You cannot pipe an object, other than a path, to `Get-Acl`.</span></span> <span data-ttu-id="0ff15-165">Em vez disso, use o parâmetro **InputObject** explicitamente no comando.</span><span class="sxs-lookup"><span data-stu-id="0ff15-165">Instead, use the **InputObject** parameter explicitly in the command.</span></span>

<span data-ttu-id="0ff15-166">Este parâmetro é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0ff15-166">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ff15-167">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0ff15-167">-LiteralPath</span></span>

<span data-ttu-id="0ff15-168">Especifica o caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="0ff15-168">Specifies the path to a resource.</span></span> <span data-ttu-id="0ff15-169">Ao contrário de **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado.</span><span class="sxs-lookup"><span data-stu-id="0ff15-169">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="0ff15-170">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="0ff15-170">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="0ff15-171">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="0ff15-171">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="0ff15-172">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="0ff15-172">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="0ff15-173">Este parâmetro é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0ff15-173">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0ff15-174">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0ff15-174">CommonParameters</span></span>

<span data-ttu-id="0ff15-175">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0ff15-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0ff15-176">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0ff15-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0ff15-177">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0ff15-177">INPUTS</span></span>

### <span data-ttu-id="0ff15-178">System.String</span><span class="sxs-lookup"><span data-stu-id="0ff15-178">System.String</span></span>

<span data-ttu-id="0ff15-179">É possível canalizar uma cadeia de caracteres que contém um caminho para `Get-Acl` .</span><span class="sxs-lookup"><span data-stu-id="0ff15-179">You can pipe a string that contains a path to `Get-Acl`.</span></span>

## <span data-ttu-id="0ff15-180">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0ff15-180">OUTPUTS</span></span>

### <span data-ttu-id="0ff15-181">System. Security. AccessControl. FileSecurity, System. Security. AccessControl. DirectorySecurity, System. Security. AccessControl. RegistrySecurity</span><span class="sxs-lookup"><span data-stu-id="0ff15-181">System.Security.AccessControl.FileSecurity, System.Security.AccessControl.DirectorySecurity, System.Security.AccessControl.RegistrySecurity</span></span>

<span data-ttu-id="0ff15-182">`Get-Acl` Retorna um objeto que representa as ACLs que ele obtém.</span><span class="sxs-lookup"><span data-stu-id="0ff15-182">`Get-Acl` returns an object that represents the ACLs that it gets.</span></span> <span data-ttu-id="0ff15-183">O tipo de objeto depende do tipo da ACL.</span><span class="sxs-lookup"><span data-stu-id="0ff15-183">The object type depends upon the ACL type.</span></span>

## <span data-ttu-id="0ff15-184">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0ff15-184">NOTES</span></span>

<span data-ttu-id="0ff15-185">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="0ff15-185">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="0ff15-186">Por padrão, `Get-Acl` o exibe o caminho do PowerShell para o recurso ( `<provider>::<resource-path>` ), o proprietário do recurso e "acesso", uma lista (matriz) das entradas de controle de acesso na DACL (lista de controle de acesso discricionário) do recurso.</span><span class="sxs-lookup"><span data-stu-id="0ff15-186">By default, `Get-Acl` displays the PowerShell path to the resource (`<provider>::<resource-path>`), the owner of the resource, and "Access", a list (array) of the access control entries in the discretionary access control list (DACL) for the resource.</span></span> <span data-ttu-id="0ff15-187">A lista de DACL é controlada pelo proprietário do recurso.</span><span class="sxs-lookup"><span data-stu-id="0ff15-187">The DACL list is controlled by the resource owner.</span></span>

<span data-ttu-id="0ff15-188">Quando você formata o resultado como uma lista, ( `Get-Acl | Format-List` ), além do caminho, do proprietário e da lista de acesso, o PowerShell exibe as propriedades e os valores de propriedade a seguir:</span><span class="sxs-lookup"><span data-stu-id="0ff15-188">When you format the result as a list, (`Get-Acl | Format-List`), in addition to the path, owner, and access list, PowerShell displays the following properties and property values:</span></span>

- <span data-ttu-id="0ff15-189">**Grupo** : o grupo de segurança do proprietário.</span><span class="sxs-lookup"><span data-stu-id="0ff15-189">**Group** : The security group of the owner.</span></span>
- <span data-ttu-id="0ff15-190">**Auditoria** : uma lista (matriz) de entradas na SACL (lista de controle de acesso) do sistema.</span><span class="sxs-lookup"><span data-stu-id="0ff15-190">**Audit** :  A list (array) of entries in the system access control list (SACL).</span></span> <span data-ttu-id="0ff15-191">A SACL especifica os tipos de tentativas de acesso para as quais o Windows gera registros de auditoria.</span><span class="sxs-lookup"><span data-stu-id="0ff15-191">The SACL specifies the types of access attempts for which Windows generates audit records.</span></span>
- <span data-ttu-id="0ff15-192">**SDDL** : o descritor de segurança do recurso exibido em uma única cadeia de texto no formato de linguagem de definição do descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="0ff15-192">**Sddl** : The security descriptor of the resource displayed in a single text string in Security Descriptor Definition Language format.</span></span> <span data-ttu-id="0ff15-193">O PowerShell usa o método **GetSddlForm** de descritores de segurança para obter esses dados.</span><span class="sxs-lookup"><span data-stu-id="0ff15-193">PowerShell uses the **GetSddlForm** method of security descriptors to get this data.</span></span>

<span data-ttu-id="0ff15-194">Como `Get-Acl` o é compatível com o sistema de arquivos e os provedores de registro, você pode usar `Get-Acl` o para exibir a ACL de objetos do sistema de arquivos, como arquivos e diretórios e objetos do registro, como chaves e entradas do registro.</span><span class="sxs-lookup"><span data-stu-id="0ff15-194">Because `Get-Acl` is supported by the file system and registry providers, you can use `Get-Acl` to view the ACL of file system objects, such as files and directories, and registry objects, such as registry keys and entries.</span></span>

## <span data-ttu-id="0ff15-195">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0ff15-195">RELATED LINKS</span></span>

[<span data-ttu-id="0ff15-196">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="0ff15-196">Set-Acl</span></span>](Set-Acl.md)
