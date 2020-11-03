---
external help file: Microsoft.PowerShell.ODataUtils-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.ODataUtils
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.odatautils/export-odataendpointproxy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-ODataEndpointProxy
ms.openlocfilehash: 7550e2df319e5f195e65609ae29ebb00830ec8d2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193889"
---
# <span data-ttu-id="65ff6-103">Export-ODataEndpointProxy</span><span class="sxs-lookup"><span data-stu-id="65ff6-103">Export-ODataEndpointProxy</span></span>

## <span data-ttu-id="65ff6-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="65ff6-104">SYNOPSIS</span></span>
<span data-ttu-id="65ff6-105">Gera um módulo que contém cmdlets para gerenciar um ponto de extremidade OData.</span><span class="sxs-lookup"><span data-stu-id="65ff6-105">Generates a module that contains cmdlets to manage an OData endpoint.</span></span>

## <span data-ttu-id="65ff6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="65ff6-106">SYNTAX</span></span>

```
Export-ODataEndpointProxy [-Uri] <String> [-OutputModule] <String> [[-MetadataUri] <String>]
 [[-Credential] <PSCredential>] [[-CreateRequestMethod] <String>] [[-UpdateRequestMethod] <String>]
 [[-CmdletAdapter] <String>] [[-ResourceNameMapping] <Hashtable>] [-Force] [[-CustomData] <Hashtable>]
 [-AllowClobber] [-AllowUnsecureConnection] [[-Headers] <Hashtable>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="65ff6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="65ff6-107">DESCRIPTION</span></span>

<span data-ttu-id="65ff6-108">O `Export-ODataEndpointProxy` cmdlet usa os metadados de um ponto de extremidade OData para gerar um módulo que contém cmdlets que você pode usar para gerenciar esse ponto de extremidade OData.</span><span class="sxs-lookup"><span data-stu-id="65ff6-108">The `Export-ODataEndpointProxy` cmdlet uses the metadata of an OData endpoint to generate a module that contains cmdlets you can use to manage that OData endpoint.</span></span> <span data-ttu-id="65ff6-109">O módulo baseia-se no CDXML.</span><span class="sxs-lookup"><span data-stu-id="65ff6-109">The module is based on CDXML.</span></span> <span data-ttu-id="65ff6-110">Depois que esse cmdlet gera o módulo, ele salva esse módulo no caminho e no nome do arquivo especificado pelo parâmetro **OutputModule** .</span><span class="sxs-lookup"><span data-stu-id="65ff6-110">After this cmdlet generates the module, it saves that module to the path and file name specified by the **OutputModule** parameter.</span></span>

<span data-ttu-id="65ff6-111">`Export-ODataEndpointProxy` gera cmdlets para operações CRUD (criar, ler, atualizar e excluir), ações não CRUD e manipulação de associação.</span><span class="sxs-lookup"><span data-stu-id="65ff6-111">`Export-ODataEndpointProxy` generates cmdlets for create, read, update, and delete (CRUD) operations, non-CRUD actions, and association manipulation.</span></span>

<span data-ttu-id="65ff6-112">`Export-ODataEndpointProxy` gera um arquivo CDXML por recurso de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="65ff6-112">`Export-ODataEndpointProxy` generates one CDXML file per endpoint resource.</span></span> <span data-ttu-id="65ff6-113">Você pode editar esses arquivos CDXML depois que o módulo é gerado.</span><span class="sxs-lookup"><span data-stu-id="65ff6-113">You can edit these CDXML files after the module is generated.</span></span> <span data-ttu-id="65ff6-114">Por exemplo, se você quiser alterar os nomes de substantivo ou de verbo dos cmdlets para alinhar com as diretrizes de nomenclatura de cmdlet do Windows PowerShell, poderá modificar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="65ff6-114">For example, if you want to change the noun or verb names of the cmdlets to align with Windows PowerShell cmdlet naming guidelines, you can modify the file.</span></span>

<span data-ttu-id="65ff6-115">Cada cmdlet em um módulo gerado deve incluir um parâmetro **conexãouri** para se conectar ao ponto de extremidade que o módulo gerencia.</span><span class="sxs-lookup"><span data-stu-id="65ff6-115">Every cmdlet in a generated module must include a **ConnectionURI** parameter in order to connect to the endpoint that the module manages.</span></span>

## <span data-ttu-id="65ff6-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="65ff6-116">EXAMPLES</span></span>

### <span data-ttu-id="65ff6-117">Exemplo 1: gerar um módulo para gerenciar um ponto de extremidade de serviço Web de varejo</span><span class="sxs-lookup"><span data-stu-id="65ff6-117">Example 1: Generate a module to manage a retail web service endpoint</span></span>

```powershell
PS C:\> Export-ODataEndpointProxy -Uri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc' -MetadataUri 'http://services.odata.org/v3/(S(snyobsk1hhutkb2yulwldgf1))/odata/odata.svc/$metadata' -AllowUnsecureConnection -OutputModule 'C:\Users\user\GeneratedScript.psm1' -ResourceNameMapping @{Products = 'Merchandise'}
```

<span data-ttu-id="65ff6-118">Esse comando gera um módulo para gerenciar um ponto de extremidade de serviço de varejo.</span><span class="sxs-lookup"><span data-stu-id="65ff6-118">This command generates a module to manage a retail service endpoint.</span></span> <span data-ttu-id="65ff6-119">O comando especifica o URI do ponto de extremidade e o URI dos metadados do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="65ff6-119">The command specifies the URI of the endpoint and the URI of the endpoint metadata.</span></span> <span data-ttu-id="65ff6-120">O comando também fornece um caminho de saída e um nome de módulo de script como o valor do parâmetro **OutputModule** .</span><span class="sxs-lookup"><span data-stu-id="65ff6-120">The command also provides an output path and script module name as the value of the **OutputModule** parameter.</span></span> <span data-ttu-id="65ff6-121">Para o valor do parâmetro **ResourceNameMapping** , o comando fornece uma tabela de hash que mapeia o nome da coleção de recursos para o substantivo desejado para o conjunto de cmdlets.</span><span class="sxs-lookup"><span data-stu-id="65ff6-121">For the value of the **ResourceNameMapping** parameter, the command provides a hashtable that maps the resource collection name to the desired noun for the cmdlet set.</span></span> <span data-ttu-id="65ff6-122">Neste exemplo, Products é o nome da coleção de recursos e **mercadoria** é o substantivo.</span><span class="sxs-lookup"><span data-stu-id="65ff6-122">In this example, Products is the resource collection name and **Merchandise** is the noun.</span></span> <span data-ttu-id="65ff6-123">Para permitir conexões com sites não SSL, HTTP, em vez de HTTPS, adicione o parâmetro **AllowUnsecureConnection** .</span><span class="sxs-lookup"><span data-stu-id="65ff6-123">To allow connections to non-SSL sites, HTTP, as opposed to HTTPS, add the **AllowUnsecureConnection** parameter.</span></span>

## <span data-ttu-id="65ff6-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="65ff6-124">PARAMETERS</span></span>

### <span data-ttu-id="65ff6-125">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="65ff6-125">-AllowClobber</span></span>

<span data-ttu-id="65ff6-126">Indica que esse cmdlet substitui um módulo existente.</span><span class="sxs-lookup"><span data-stu-id="65ff6-126">Indicates that this cmdlet replaces an existing module.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="65ff6-127">-AllowUnsecureConnection</span><span class="sxs-lookup"><span data-stu-id="65ff6-127">-AllowUnsecureConnection</span></span>

<span data-ttu-id="65ff6-128">Indica que este módulo pode se conectar a URIs que não são protegidas por SSL.</span><span class="sxs-lookup"><span data-stu-id="65ff6-128">Indicates that this module can connect to URIs that are not SSL-secured.</span></span> <span data-ttu-id="65ff6-129">O módulo pode gerenciar sites HTTP, além de sites HTTPS.</span><span class="sxs-lookup"><span data-stu-id="65ff6-129">The module can manage HTTP sites in addition to HTTPS sites.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 11
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="65ff6-130">-CmdletAdapter</span><span class="sxs-lookup"><span data-stu-id="65ff6-130">-CmdletAdapter</span></span>

<span data-ttu-id="65ff6-131">Especifica o adaptador do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="65ff6-131">Specifies the cmdlet adapter.</span></span> <span data-ttu-id="65ff6-132">Os valores aceitáveis para esse parâmetro são: ODataAdapter e NetworkControllerAdapter.</span><span class="sxs-lookup"><span data-stu-id="65ff6-132">The acceptable values for this parameter are: ODataAdapter and NetworkControllerAdapter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ODataAdapter, NetworkControllerAdapter, ODataV4Adapter

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="65ff6-133">-CreateRequestMethod</span><span class="sxs-lookup"><span data-stu-id="65ff6-133">-CreateRequestMethod</span></span>

<span data-ttu-id="65ff6-134">Especifica o método de solicitação.</span><span class="sxs-lookup"><span data-stu-id="65ff6-134">Specifies the request method.</span></span> <span data-ttu-id="65ff6-135">Os valores aceitáveis para esse parâmetro são: PUT, POST e PATCH.</span><span class="sxs-lookup"><span data-stu-id="65ff6-135">The acceptable values for this parameter are: PUT, POST, and PATCH.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Put, Post, Patch

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="65ff6-136">-Credential</span><span class="sxs-lookup"><span data-stu-id="65ff6-136">-Credential</span></span>

<span data-ttu-id="65ff6-137">Especifica uma conta de usuário que tem acesso ao ponto de extremidade OData.</span><span class="sxs-lookup"><span data-stu-id="65ff6-137">Specifies a user account that has access to the OData endpoint.</span></span> <span data-ttu-id="65ff6-138">O valor padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="65ff6-138">The default value is the current user.</span></span> <span data-ttu-id="65ff6-139">Se um computador remoto executar o Windows Vista ou uma versão posterior do sistema operacional Windows, o cmdlet solicitará as credenciais.</span><span class="sxs-lookup"><span data-stu-id="65ff6-139">If a remote computer runs Windows Vista or a later release of the Windows operating system, the cmdlet prompts you for credentials.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="65ff6-140">-CustomData</span><span class="sxs-lookup"><span data-stu-id="65ff6-140">-CustomData</span></span>

<span data-ttu-id="65ff6-141">Especifica uma tabela de hash de dados personalizados.</span><span class="sxs-lookup"><span data-stu-id="65ff6-141">Specifies a hash table of custom data.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="65ff6-142">-Force</span><span class="sxs-lookup"><span data-stu-id="65ff6-142">-Force</span></span>

<span data-ttu-id="65ff6-143">Indica que esse cmdlet substitui um módulo gerado existente de mesmo nome em uma `Modules` pasta existente.</span><span class="sxs-lookup"><span data-stu-id="65ff6-143">Indicates that this cmdlet overwrites an existing generated module of the same name in an existing `Modules` folder.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="65ff6-144">-Cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="65ff6-144">-Headers</span></span>

<span data-ttu-id="65ff6-145">Especifica os cabeçalhos da solicitação da Web.</span><span class="sxs-lookup"><span data-stu-id="65ff6-145">Specifies the headers of the web request.</span></span> <span data-ttu-id="65ff6-146">Insira uma tabela de hash ou dicionário.</span><span class="sxs-lookup"><span data-stu-id="65ff6-146">Enter a hash table or dictionary.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 12
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="65ff6-147">-MetadataUri</span><span class="sxs-lookup"><span data-stu-id="65ff6-147">-MetadataUri</span></span>

<span data-ttu-id="65ff6-148">Especifica o URI dos metadados do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="65ff6-148">Specifies the URI of the metadata of the endpoint.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="65ff6-149">-OutputModule</span><span class="sxs-lookup"><span data-stu-id="65ff6-149">-OutputModule</span></span>

<span data-ttu-id="65ff6-150">Especifica o caminho e o nome do módulo para o qual esse cmdlet salva o módulo gerado de comandos de proxy.</span><span class="sxs-lookup"><span data-stu-id="65ff6-150">Specifies the path and module name to which this cmdlet saves the generated module of proxy commands.</span></span>

<span data-ttu-id="65ff6-151">Esse cmdlet copia um módulo binário, um manifesto de módulo e um arquivo de formatação, se aplicável, para a pasta especificada.</span><span class="sxs-lookup"><span data-stu-id="65ff6-151">This cmdlet copies a binary module, module manifest, and formatting file, if applicable, to the specified folder.</span></span> <span data-ttu-id="65ff6-152">Se você especificar apenas o nome do módulo, `Export-ODataEndpointProxy` o salvará o módulo na `$home\Documents\WindowsPowerShell\Modules` pasta.</span><span class="sxs-lookup"><span data-stu-id="65ff6-152">If you specify only the name of the module, `Export-ODataEndpointProxy` saves the module in the `$home\Documents\WindowsPowerShell\Modules` folder.</span></span> <span data-ttu-id="65ff6-153">Se você especificar um caminho, o cmdlet criará a pasta do módulo nesse caminho.</span><span class="sxs-lookup"><span data-stu-id="65ff6-153">If you specify a path, the cmdlet creates the module folder in that path.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="65ff6-154">-ResourceNameMapping</span><span class="sxs-lookup"><span data-stu-id="65ff6-154">-ResourceNameMapping</span></span>

<span data-ttu-id="65ff6-155">Especifica uma tabela de hash que contém mapeamentos que permitem personalizar os cmdlets gerados.</span><span class="sxs-lookup"><span data-stu-id="65ff6-155">Specifies a hashtable that contains mappings that let you customize the generated cmdlets.</span></span> <span data-ttu-id="65ff6-156">Nessa tabela de hash, o nome da coleção de recursos é a chave.</span><span class="sxs-lookup"><span data-stu-id="65ff6-156">In this hashtable, the resource collection name is the key.</span></span> <span data-ttu-id="65ff6-157">O substantivo do cmdlet desejado é o valor.</span><span class="sxs-lookup"><span data-stu-id="65ff6-157">The desired cmdlet noun is the value.</span></span>

<span data-ttu-id="65ff6-158">Por exemplo, na tabela de hash `@{Products = 'Merchandise'}` , **Products** é o nome da coleção de recursos que serve como a chave.</span><span class="sxs-lookup"><span data-stu-id="65ff6-158">For example, in the hash table `@{Products = 'Merchandise'}`, **Products** is the resource collection name that serves as the key.</span></span> <span data-ttu-id="65ff6-159">**Mercadoria** é o substantivo do cmdlet resultante.</span><span class="sxs-lookup"><span data-stu-id="65ff6-159">**Merchandise** is the resulting cmdlet noun.</span></span> <span data-ttu-id="65ff6-160">Os nomes de cmdlets gerados podem não ser alinhados às diretrizes de nomenclatura de cmdlet do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65ff6-160">The generated cmdlet names might not align to Windows PowerShell cmdlet naming guidelines.</span></span> <span data-ttu-id="65ff6-161">Você pode modificar o arquivo de recurso CDXML para alterar os nomes de cmdlet depois que esse cmdlet criar o módulo.</span><span class="sxs-lookup"><span data-stu-id="65ff6-161">You can modify the resource CDXML file to change the cmdlet names after this cmdlet creates the module.</span></span> <span data-ttu-id="65ff6-162">Para obter mais informações, consulte [diretrizes de desenvolvimento altamente incentivadas](/powershell/scripting/developer/cmdlet/strongly-encouraged-development-guidelines).</span><span class="sxs-lookup"><span data-stu-id="65ff6-162">For more information, see [Strongly Encouraged Development Guidelines](/powershell/scripting/developer/cmdlet/strongly-encouraged-development-guidelines).</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="65ff6-163">-UpdateRequestMethod</span><span class="sxs-lookup"><span data-stu-id="65ff6-163">-UpdateRequestMethod</span></span>

<span data-ttu-id="65ff6-164">Especifica o método de solicitação de atualização.</span><span class="sxs-lookup"><span data-stu-id="65ff6-164">Specifies the update request method.</span></span> <span data-ttu-id="65ff6-165">Os valores aceitáveis para esse parâmetro são: PUT, POST e PATCH.</span><span class="sxs-lookup"><span data-stu-id="65ff6-165">The acceptable values for this parameter are: PUT, POST, and PATCH.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Put, Post, Patch

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="65ff6-166">-URI</span><span class="sxs-lookup"><span data-stu-id="65ff6-166">-Uri</span></span>

<span data-ttu-id="65ff6-167">Especifica o URI do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="65ff6-167">Specifies the URI of the endpoint.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="65ff6-168">-Confirm</span><span class="sxs-lookup"><span data-stu-id="65ff6-168">-Confirm</span></span>

<span data-ttu-id="65ff6-169">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="65ff6-169">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="65ff6-170">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="65ff6-170">-WhatIf</span></span>

<span data-ttu-id="65ff6-171">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="65ff6-171">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="65ff6-172">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="65ff6-172">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="65ff6-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="65ff6-173">CommonParameters</span></span>

<span data-ttu-id="65ff6-174">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="65ff6-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="65ff6-175">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="65ff6-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="65ff6-176">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="65ff6-176">INPUTS</span></span>

## <span data-ttu-id="65ff6-177">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="65ff6-177">OUTPUTS</span></span>

## <span data-ttu-id="65ff6-178">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="65ff6-178">NOTES</span></span>

## <span data-ttu-id="65ff6-179">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="65ff6-179">RELATED LINKS</span></span>

<span data-ttu-id="65ff6-180">[Biblioteca OData](https://technet.microsoft.com/windowsserver/hh525392(v=vs.85).aspx?f=255&MSPPError=-2147217396)</span><span class="sxs-lookup"><span data-stu-id="65ff6-180">[OData Library](https://technet.microsoft.com/windowsserver/hh525392(v=vs.85).aspx?f=255&MSPPError=-2147217396)</span></span>

[<span data-ttu-id="65ff6-181">O que é o protocolo OData?</span><span class="sxs-lookup"><span data-stu-id="65ff6-181">What is the OData Protocol?</span></span>](https://www.odata.org/)

[<span data-ttu-id="65ff6-182">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="65ff6-182">Invoke-RestMethod</span></span>](../Microsoft.PowerShell.Utility/Invoke-RestMethod.md)
