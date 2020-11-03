---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-psrolecapabilityfile?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSRoleCapabilityFile
ms.openlocfilehash: 61a144ca5bc74d63738e9ccfc65188ddf1e27c02
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192988"
---
# <span data-ttu-id="15ed0-103">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="15ed0-103">New-PSRoleCapabilityFile</span></span>

## <span data-ttu-id="15ed0-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="15ed0-104">SYNOPSIS</span></span>
<span data-ttu-id="15ed0-105">Cria um arquivo que define um conjunto de recursos a serem expostos por meio de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-105">Creates a file that defines a set of capabilities to be exposed through a session configuration.</span></span>

## <span data-ttu-id="15ed0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="15ed0-106">SYNTAX</span></span>

```
New-PSRoleCapabilityFile [-Path] <String> [-Guid <Guid>] [-Author <String>] [-Description <String>]
 [-CompanyName <String>] [-Copyright <String>] [-ModulesToImport <Object[]>] [-VisibleAliases <String[]>]
 [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>] [-VisibleExternalCommands <String[]>]
 [-VisibleProviders <String[]>] [-ScriptsToProcess <String[]>] [-AliasDefinitions <IDictionary[]>]
 [-FunctionDefinitions <IDictionary[]>] [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>]
 [-TypesToProcess <String[]>] [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="15ed0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="15ed0-107">DESCRIPTION</span></span>

<span data-ttu-id="15ed0-108">O `New-PSRoleCapabilityFile` cmdlet cria um arquivo que define um conjunto de recursos de usuário que pode ser exposto por meio de arquivos de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-108">The `New-PSRoleCapabilityFile` cmdlet creates a file that defines a set of user capabilities that can be exposed through session configuration files.</span></span> <span data-ttu-id="15ed0-109">Isso inclui determinar quais cmdlets, funções e scripts estão disponíveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="15ed0-109">This includes determining which cmdlets, functions, and scripts are available to users.</span></span> <span data-ttu-id="15ed0-110">O arquivo de capacidade é um arquivo de texto legível que contém uma tabela de hash de valores e propriedades de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-110">The capability file is a human-readable text file that contains a hash table of session configuration properties and values.</span></span> <span data-ttu-id="15ed0-111">O arquivo tem uma extensão de nome de arquivo. pSrc e pode ser usado por mais de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-111">The file has a .psrc file name extension, and can be used by more than one session configuration.</span></span>

<span data-ttu-id="15ed0-112">Todos os parâmetros de `New-PSRoleCapabilityFile` são opcionais, exceto o parâmetro **Path** , que especifica o caminho do arquivo para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="15ed0-112">All the parameters of `New-PSRoleCapabilityFile` are optional except for the **Path** parameter, which specifies the file path for the file.</span></span> <span data-ttu-id="15ed0-113">Se você não incluir um parâmetro ao executar o cmdlet, a chave correspondente no arquivo de configuração de sessão será comentada, exceto quando indicado na descrição do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="15ed0-113">If you do not include a parameter when you run the cmdlet, the corresponding key in the session configuration file is commented-out, except where noted in the parameter description.</span></span> <span data-ttu-id="15ed0-114">Por exemplo, se você não incluir o parâmetro **AssembliesToLoad** , essa seção do arquivo de configuração de sessão será comentada.</span><span class="sxs-lookup"><span data-stu-id="15ed0-114">For example, if you do not include the **AssembliesToLoad** parameter then that section of the session configuration file is commented out.</span></span>

<span data-ttu-id="15ed0-115">Para usar o arquivo de capacidade de função em uma configuração de sessão, primeiro coloque o arquivo em uma subpasta **RoleCapabilities** de uma pasta de módulo do PowerShell válida.</span><span class="sxs-lookup"><span data-stu-id="15ed0-115">To use the role capability file in a session configuration, first place the file in a **RoleCapabilities** subfolder of a valid PowerShell module folder.</span></span> <span data-ttu-id="15ed0-116">Em seguida, referencie o arquivo pelo nome no campo **RoleDefinitions** em um arquivo de configuração de sessão do PowerShell (. PSSC).</span><span class="sxs-lookup"><span data-stu-id="15ed0-116">Then reference the file by name in the **RoleDefinitions** field in a PowerShell Session Configuration (.pssc) file.</span></span>

<span data-ttu-id="15ed0-117">Esse cmdlet foi introduzido no Windows PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="15ed0-117">This cmdlet was introduced in Windows PowerShell 5.0.</span></span>

## <span data-ttu-id="15ed0-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="15ed0-118">EXAMPLES</span></span>

### <span data-ttu-id="15ed0-119">Exemplo 1: criar um arquivo de capacidade de função em branco</span><span class="sxs-lookup"><span data-stu-id="15ed0-119">Example 1: Create a blank role capability file</span></span>

<span data-ttu-id="15ed0-120">Este exemplo cria um novo arquivo de capacidade de função que usa os valores padrão (em branco).</span><span class="sxs-lookup"><span data-stu-id="15ed0-120">This example creates a new role capability file that uses the default (blank) values.</span></span> <span data-ttu-id="15ed0-121">O arquivo pode ser editado posteriormente em um editor de texto para alterar essas definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="15ed0-121">The file can later be edited in a text editor to change these configuration settings.</span></span>

```powershell
New-PSRoleCapabilityFile -Path ".\ExampleFile.psrc"
```

### <span data-ttu-id="15ed0-122">Exemplo 2: criar um arquivo de capacidade de função permitindo que os usuários reiniciem serviços e qualquer computador VDI</span><span class="sxs-lookup"><span data-stu-id="15ed0-122">Example 2: Create a role capability file allowing users to restart services and any VDI computer</span></span>

<span data-ttu-id="15ed0-123">Este exemplo cria um arquivo de capacidade de função de exemplo que permite que os usuários reiniciem serviços e computadores que correspondam a um padrão de nome específico.</span><span class="sxs-lookup"><span data-stu-id="15ed0-123">This example creates a sample role capability file that enables users to restart services and computers that match a specific name pattern.</span></span> <span data-ttu-id="15ed0-124">A filtragem de nomes é definida pela definição do parâmetro **ValidatePattern** para a expressão regular `VDI\d+` .</span><span class="sxs-lookup"><span data-stu-id="15ed0-124">Name filtering is defined by setting the **ValidatePattern** parameter to the regular expression `VDI\d+`.</span></span>

```powershell
$roleParameters = @{
    Path = ".\Maintenance.psrc"
    Author = "User01"
    CompanyName = "Fabrikam Corporation"
    Description = "This role enables users to restart any service and restart any VDI computer."
    ModulesToImport = "Microsoft.PowerShell.Core"
    VisibleCmdlets = "Restart-Service", @{
                      Name = "Restart-Computer"
                      Parameters = @{ Name = "ComputerName"; ValidatePattern = "VDI\d+" }
    }
}
New-PSRoleCapabilityFile @roleParameters
```

## <span data-ttu-id="15ed0-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="15ed0-125">PARAMETERS</span></span>

### <span data-ttu-id="15ed0-126">-AliasDefinitions</span><span class="sxs-lookup"><span data-stu-id="15ed0-126">-AliasDefinitions</span></span>

<span data-ttu-id="15ed0-127">Adiciona os aliases especificados a sessões que usam o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-127">Adds the specified aliases to sessions that use the role capability file.</span></span> <span data-ttu-id="15ed0-128">Insira uma tabela de hash com as seguintes chaves:</span><span class="sxs-lookup"><span data-stu-id="15ed0-128">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="15ed0-129">Nome.</span><span class="sxs-lookup"><span data-stu-id="15ed0-129">Name.</span></span> <span data-ttu-id="15ed0-130">Nome do alias.</span><span class="sxs-lookup"><span data-stu-id="15ed0-130">Name of the alias.</span></span> <span data-ttu-id="15ed0-131">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="15ed0-131">This key is required.</span></span>
- <span data-ttu-id="15ed0-132">Value.</span><span class="sxs-lookup"><span data-stu-id="15ed0-132">Value.</span></span> <span data-ttu-id="15ed0-133">O comando que o alias representa.</span><span class="sxs-lookup"><span data-stu-id="15ed0-133">The command that the alias represents.</span></span> <span data-ttu-id="15ed0-134">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="15ed0-134">This key is required.</span></span>
- <span data-ttu-id="15ed0-135">Descrição.</span><span class="sxs-lookup"><span data-stu-id="15ed0-135">Description.</span></span> <span data-ttu-id="15ed0-136">Uma cadeia de caracteres de texto que descreve o alias.</span><span class="sxs-lookup"><span data-stu-id="15ed0-136">A text string that describes the alias.</span></span> <span data-ttu-id="15ed0-137">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="15ed0-137">This key is optional.</span></span>
- <span data-ttu-id="15ed0-138">Opções.</span><span class="sxs-lookup"><span data-stu-id="15ed0-138">Options.</span></span> <span data-ttu-id="15ed0-139">Opções de alias.</span><span class="sxs-lookup"><span data-stu-id="15ed0-139">Alias options.</span></span> <span data-ttu-id="15ed0-140">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="15ed0-140">This key is optional.</span></span> <span data-ttu-id="15ed0-141">O valor padrão é Nenhum.</span><span class="sxs-lookup"><span data-stu-id="15ed0-141">The default value is None.</span></span> <span data-ttu-id="15ed0-142">Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.</span><span class="sxs-lookup"><span data-stu-id="15ed0-142">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="15ed0-143">Por exemplo: `@{Name="hlp";Value="Get-Help";Description="Gets help";Options="ReadOnly"}`</span><span class="sxs-lookup"><span data-stu-id="15ed0-143">For example: `@{Name="hlp";Value="Get-Help";Description="Gets help";Options="ReadOnly"}`</span></span>

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15ed0-144">-AssembliesToLoad</span><span class="sxs-lookup"><span data-stu-id="15ed0-144">-AssembliesToLoad</span></span>

<span data-ttu-id="15ed0-145">Especifica os assemblies a serem carregados nas sessões que usam o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-145">Specifies the assemblies to load into the sessions that use the role capability file.</span></span>

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

### <span data-ttu-id="15ed0-146">-Autor</span><span class="sxs-lookup"><span data-stu-id="15ed0-146">-Author</span></span>

<span data-ttu-id="15ed0-147">Especifica o usuário que criou o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-147">Specifies the user that created the role capability file.</span></span>

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

### <span data-ttu-id="15ed0-148">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="15ed0-148">-CompanyName</span></span>

<span data-ttu-id="15ed0-149">Identifica a empresa que criou o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-149">Identifies the company that created the role capability file.</span></span>
<span data-ttu-id="15ed0-150">O valor padrão é Desconhecido.</span><span class="sxs-lookup"><span data-stu-id="15ed0-150">The default value is Unknown.</span></span>

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

### <span data-ttu-id="15ed0-151">-Direitos autorais</span><span class="sxs-lookup"><span data-stu-id="15ed0-151">-Copyright</span></span>

<span data-ttu-id="15ed0-152">Especifica um direito autoral para o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-152">Specifies a copyright for the role capability file.</span></span> <span data-ttu-id="15ed0-153">Se você omitir esse parâmetro, o `New-PSRoleCapabilityFile` gerará uma declaração de direitos autorais usando o valor do parâmetro **Author** .</span><span class="sxs-lookup"><span data-stu-id="15ed0-153">If you omit this parameter, `New-PSRoleCapabilityFile` generates a copyright statement by using the value of the **Author** parameter.</span></span>

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

### <span data-ttu-id="15ed0-154">-Description</span><span class="sxs-lookup"><span data-stu-id="15ed0-154">-Description</span></span>

<span data-ttu-id="15ed0-155">Especifica uma descrição para o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-155">Specifies a description for the role capability file.</span></span>

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

### <span data-ttu-id="15ed0-156">-EnvironmentVariables</span><span class="sxs-lookup"><span data-stu-id="15ed0-156">-EnvironmentVariables</span></span>

<span data-ttu-id="15ed0-157">Especifica as variáveis de ambiente para sessões que expõem esse arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-157">Specifies the environment variables for sessions that expose this role capability file.</span></span> <span data-ttu-id="15ed0-158">Insira uma tabela de hash na qual as chaves são nomes de variáveis de ambiente e os valores são valores de variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="15ed0-158">Enter a hash table in which the keys are the environment variable names and the values are the environment variable values.</span></span>

<span data-ttu-id="15ed0-159">Por exemplo: `EnvironmentVariables=@{TestShare="\\\\Server01\TestShare"}`</span><span class="sxs-lookup"><span data-stu-id="15ed0-159">For example: `EnvironmentVariables=@{TestShare="\\\\Server01\TestShare"}`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15ed0-160">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="15ed0-160">-FormatsToProcess</span></span>

<span data-ttu-id="15ed0-161">Especifica os arquivos de formatação (. ps1xml) que são executados em sessões que usam o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-161">Specifies the formatting files (.ps1xml) that run in sessions that use the role capability file.</span></span> <span data-ttu-id="15ed0-162">O valor desse parâmetro deve ser um caminho completo ou absoluto dos arquivos de formatação.</span><span class="sxs-lookup"><span data-stu-id="15ed0-162">The value of this parameter must be a full or absolute path of the formatting files.</span></span>

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

### <span data-ttu-id="15ed0-163">-FunctionDefinitions</span><span class="sxs-lookup"><span data-stu-id="15ed0-163">-FunctionDefinitions</span></span>

<span data-ttu-id="15ed0-164">Adiciona as funções especificadas às sessões que expõem a capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-164">Adds the specified functions to sessions that expose the role capability.</span></span> <span data-ttu-id="15ed0-165">Insira uma tabela de hash com as seguintes chaves:</span><span class="sxs-lookup"><span data-stu-id="15ed0-165">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="15ed0-166">Nome.</span><span class="sxs-lookup"><span data-stu-id="15ed0-166">Name.</span></span> <span data-ttu-id="15ed0-167">Nome da função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-167">Name of the function.</span></span> <span data-ttu-id="15ed0-168">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="15ed0-168">This key is required.</span></span>
- <span data-ttu-id="15ed0-169">ScriptBlock.</span><span class="sxs-lookup"><span data-stu-id="15ed0-169">ScriptBlock.</span></span> <span data-ttu-id="15ed0-170">Corpo da função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-170">Function body.</span></span> <span data-ttu-id="15ed0-171">Insira um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="15ed0-171">Enter a script block.</span></span> <span data-ttu-id="15ed0-172">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="15ed0-172">This key is required.</span></span>
- <span data-ttu-id="15ed0-173">Opções.</span><span class="sxs-lookup"><span data-stu-id="15ed0-173">Options.</span></span> <span data-ttu-id="15ed0-174">Opções de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-174">Function options.</span></span> <span data-ttu-id="15ed0-175">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="15ed0-175">This key is optional.</span></span> <span data-ttu-id="15ed0-176">O valor padrão é Nenhum.</span><span class="sxs-lookup"><span data-stu-id="15ed0-176">The default value is None.</span></span> <span data-ttu-id="15ed0-177">Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.</span><span class="sxs-lookup"><span data-stu-id="15ed0-177">The acceptable values for this parameter are: are None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="15ed0-178">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="15ed0-178">For example:</span></span>

`@{Name="Get-PowerShellProcess";ScriptBlock={Get-Process PowerShell};Options="AllScope"}`

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15ed0-179">-GUID</span><span class="sxs-lookup"><span data-stu-id="15ed0-179">-Guid</span></span>

<span data-ttu-id="15ed0-180">Especifica um identificador exclusivo para o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-180">Specifies a unique identifier for the role capability file.</span></span> <span data-ttu-id="15ed0-181">Se você omitir esse parâmetro, o `New-PSRoleCapabilityFile` gerará um GUID para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="15ed0-181">If you omit this parameter, `New-PSRoleCapabilityFile` generates a GUID for the file.</span></span> <span data-ttu-id="15ed0-182">Para criar um novo GUID no PowerShell, digite `[guid]::NewGuid()` .</span><span class="sxs-lookup"><span data-stu-id="15ed0-182">To create a new GUID in PowerShell, type `[guid]::NewGuid()`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15ed0-183">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="15ed0-183">-ModulesToImport</span></span>

<span data-ttu-id="15ed0-184">Especifica os módulos que são automaticamente importados para sessões que usam o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-184">Specifies the modules that are automatically imported into sessions that use the role capability file.</span></span> <span data-ttu-id="15ed0-185">Por padrão, todos os comandos nos módulos listados são visíveis.</span><span class="sxs-lookup"><span data-stu-id="15ed0-185">By default, all the commands in listed modules are visible.</span></span> <span data-ttu-id="15ed0-186">Quando usado com **VisibleCmdlets** ou **VisibleFunctions** , os comandos visíveis dos módulos especificados podem ser restritos.</span><span class="sxs-lookup"><span data-stu-id="15ed0-186">When used with **VisibleCmdlets** or **VisibleFunctions** , the commands visible from the specified modules can be restricted.</span></span>

<span data-ttu-id="15ed0-187">Cada módulo usado no valor desse parâmetro pode ser representado por uma cadeia de caracteres ou por uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="15ed0-187">Each module used in the value of this parameter can be represented by a string or by a hash table.</span></span> <span data-ttu-id="15ed0-188">Uma cadeia de caracteres de módulo consiste apenas no nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="15ed0-188">A module string consists only of the name of the module.</span></span> <span data-ttu-id="15ed0-189">Uma tabela de hash de módulo pode incluir as chaves **ModuleName** , **ModuleVersion** e **GUID** .</span><span class="sxs-lookup"><span data-stu-id="15ed0-189">A module hash table can include **ModuleName** , **ModuleVersion** , and **GUID** keys.</span></span> <span data-ttu-id="15ed0-190">Somente a chave **ModuleName** é necessária.</span><span class="sxs-lookup"><span data-stu-id="15ed0-190">Only the **ModuleName** key is required.</span></span>

<span data-ttu-id="15ed0-191">Por exemplo, o seguinte valor consiste em uma cadeia de caracteres e uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="15ed0-191">For example, the following value consists of a string and a hash table.</span></span> <span data-ttu-id="15ed0-192">Qualquer combinação de cadeias de caracteres e tabelas de hash, em qualquer ordem, é válida.</span><span class="sxs-lookup"><span data-stu-id="15ed0-192">Any combination of strings and hash tables, in any order, is valid.</span></span>

`"TroubleshootingPack", @{ModuleName="PSDiagnostics"; ModuleVersion="1.0.0.0";GUID="c61d6278-02a3-4618-ae37-a524d40a7f44"}`

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15ed0-193">-Path</span><span class="sxs-lookup"><span data-stu-id="15ed0-193">-Path</span></span>

<span data-ttu-id="15ed0-194">Especifica o caminho e o nome do arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-194">Specifies the path and filename of the role capability file.</span></span> <span data-ttu-id="15ed0-195">O arquivo deve ter uma `.psrc` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="15ed0-195">The file must have a `.psrc` filename extension.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15ed0-196">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="15ed0-196">-ScriptsToProcess</span></span>

<span data-ttu-id="15ed0-197">Especifica os scripts a serem adicionados às sessões que usam o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-197">Specifies scripts to add to sessions that use the role capability file.</span></span> <span data-ttu-id="15ed0-198">Digite os nomes de arquivo e caminho dos scripts.</span><span class="sxs-lookup"><span data-stu-id="15ed0-198">Enter the path and file names of the scripts.</span></span> <span data-ttu-id="15ed0-199">O valor desse parâmetro deve ser um caminho completo ou absoluto dos nomes de arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="15ed0-199">The value of this parameter must be a full or absolute path of the script file names.</span></span>

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

### <span data-ttu-id="15ed0-200">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="15ed0-200">-TypesToProcess</span></span>

<span data-ttu-id="15ed0-201">Especifica os arquivos de tipo (. ps1xml) a serem adicionados às sessões que usam o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-201">Specifies type files (.ps1xml) to add to sessions that use the role capability file.</span></span> <span data-ttu-id="15ed0-202">Insira os nomes de filetype.</span><span class="sxs-lookup"><span data-stu-id="15ed0-202">Enter the type filenames.</span></span> <span data-ttu-id="15ed0-203">O valor desse parâmetro deve ser um caminho completo ou absoluto do tipo nomes de texto.</span><span class="sxs-lookup"><span data-stu-id="15ed0-203">The value of this parameter must be a full or absolute path of the type filenames.</span></span>

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

### <span data-ttu-id="15ed0-204">-VariableDefinitions</span><span class="sxs-lookup"><span data-stu-id="15ed0-204">-VariableDefinitions</span></span>

<span data-ttu-id="15ed0-205">Especifica as variáveis a serem adicionadas às sessões que usam o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="15ed0-205">Specifies variables to add to sessions that use the role capability file.</span></span> <span data-ttu-id="15ed0-206">Insira uma tabela de hash com as seguintes chaves:</span><span class="sxs-lookup"><span data-stu-id="15ed0-206">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="15ed0-207">Nome.</span><span class="sxs-lookup"><span data-stu-id="15ed0-207">Name.</span></span> <span data-ttu-id="15ed0-208">Nome da variável.</span><span class="sxs-lookup"><span data-stu-id="15ed0-208">Name of the variable.</span></span> <span data-ttu-id="15ed0-209">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="15ed0-209">This key is required.</span></span>
- <span data-ttu-id="15ed0-210">Value.</span><span class="sxs-lookup"><span data-stu-id="15ed0-210">Value.</span></span> <span data-ttu-id="15ed0-211">Valor da variável.</span><span class="sxs-lookup"><span data-stu-id="15ed0-211">Variable value.</span></span> <span data-ttu-id="15ed0-212">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="15ed0-212">This key is required.</span></span>
- <span data-ttu-id="15ed0-213">Opções.</span><span class="sxs-lookup"><span data-stu-id="15ed0-213">Options.</span></span> <span data-ttu-id="15ed0-214">Opções de variáveis.</span><span class="sxs-lookup"><span data-stu-id="15ed0-214">Variable options.</span></span> <span data-ttu-id="15ed0-215">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="15ed0-215">This key is optional.</span></span> <span data-ttu-id="15ed0-216">O valor padrão é Nenhum.</span><span class="sxs-lookup"><span data-stu-id="15ed0-216">The default value is None.</span></span> <span data-ttu-id="15ed0-217">Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.</span><span class="sxs-lookup"><span data-stu-id="15ed0-217">The acceptable values for this parameter are: are None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="15ed0-218">Por exemplo: `@{Name="WarningPreference";Value="SilentlyContinue";Options="AllScope"}`</span><span class="sxs-lookup"><span data-stu-id="15ed0-218">For example: `@{Name="WarningPreference";Value="SilentlyContinue";Options="AllScope"}`</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15ed0-219">-VisibleAliases</span><span class="sxs-lookup"><span data-stu-id="15ed0-219">-VisibleAliases</span></span>

<span data-ttu-id="15ed0-220">Limita os aliases na sessão para os aliases especificados no valor desse parâmetro, além de todos os aliases que você definir no parâmetro **AliasDefinition** .</span><span class="sxs-lookup"><span data-stu-id="15ed0-220">Limits the aliases in the session to those aliases specified in the value of this parameter, plus any aliases that you define in the **AliasDefinition** parameter.</span></span> <span data-ttu-id="15ed0-221">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="15ed0-221">Wildcard characters are supported.</span></span>
<span data-ttu-id="15ed0-222">Por padrão, todos os aliases que são definidos pelo mecanismo do PowerShell e todos os aliases que os módulos exportam são visíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-222">By default, all aliases that are defined by the PowerShell engine and all aliases that modules export are visible in the session.</span></span>

<span data-ttu-id="15ed0-223">Por exemplo, para limitar os aliases disponíveis para o GM e o gcm, use esta sintaxe: `VisibleAliases="gcm", "gp"`</span><span class="sxs-lookup"><span data-stu-id="15ed0-223">For example, to limit the available aliases to gm and gcm use this syntax: `VisibleAliases="gcm", "gp"`</span></span>

<span data-ttu-id="15ed0-224">Quando qualquer parâmetro **visível** é incluído no arquivo de capacidade de função, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-224">When any **Visible** parameter is included in the role capability file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="15ed0-225">-VisibleCmdlets</span><span class="sxs-lookup"><span data-stu-id="15ed0-225">-VisibleCmdlets</span></span>

<span data-ttu-id="15ed0-226">Limita os cmdlets na sessão para aquelas especificadas no valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="15ed0-226">Limits the cmdlets in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="15ed0-227">Há suporte para caracteres curinga e nomes qualificados de módulo.</span><span class="sxs-lookup"><span data-stu-id="15ed0-227">Wildcard characters and Module Qualified Names are supported.</span></span>

<span data-ttu-id="15ed0-228">Por padrão, todos os cmdlets que os módulos na sessão exportam são visíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-228">By default, all cmdlets that the modules in the session export are visible in the session.</span></span> <span data-ttu-id="15ed0-229">Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos e snap-ins são importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-229">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span> <span data-ttu-id="15ed0-230">Se nenhum módulo no **ModulesToImport** expor o cmdlet, o `New-PSRoleCapabilityFile` tentará carregar o módulo apropriado.</span><span class="sxs-lookup"><span data-stu-id="15ed0-230">If no modules in **ModulesToImport** expose the cmdlet, `New-PSRoleCapabilityFile` tries to load the appropriate module.</span></span>

<span data-ttu-id="15ed0-231">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-231">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="15ed0-232">-VisibleExternalCommands</span><span class="sxs-lookup"><span data-stu-id="15ed0-232">-VisibleExternalCommands</span></span>

<span data-ttu-id="15ed0-233">Limita os binários, os scripts e os comandos externos que podem ser executados na sessão para aqueles especificados no valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="15ed0-233">Limits the external binaries, scripts and commands that can be executed in the session to those specified in the value of this parameter.</span></span>

<span data-ttu-id="15ed0-234">Por padrão, nenhum comando externo é visível nesta sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-234">By default, no external commands are visible in this session.</span></span>

<span data-ttu-id="15ed0-235">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-235">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="15ed0-236">-VisibleFunctions</span><span class="sxs-lookup"><span data-stu-id="15ed0-236">-VisibleFunctions</span></span>

<span data-ttu-id="15ed0-237">Limita as funções na sessão àqueles especificados no valor desse parâmetro, além de qualquer função que você definir no parâmetro **FunctionDefinitions** .</span><span class="sxs-lookup"><span data-stu-id="15ed0-237">Limits the functions in the session to those specified in the value of this parameter, plus any functions that you define in the **FunctionDefinitions** parameter.</span></span> <span data-ttu-id="15ed0-238">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="15ed0-238">Wildcard characters are supported.</span></span>

<span data-ttu-id="15ed0-239">Por padrão, todas as funções exportadas por módulos na sessão ficam visíveis nessa sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-239">By default, all functions exported by modules in the session are visible in that session.</span></span> <span data-ttu-id="15ed0-240">Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos serão importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-240">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="15ed0-241">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-241">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="15ed0-242">-VisibleProviders</span><span class="sxs-lookup"><span data-stu-id="15ed0-242">-VisibleProviders</span></span>

<span data-ttu-id="15ed0-243">Limita os provedores do PowerShell na sessão para aqueles especificados no valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="15ed0-243">Limits the PowerShell providers in the session to those specified in the value of this parameter.</span></span>
<span data-ttu-id="15ed0-244">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="15ed0-244">Wildcard characters are supported.</span></span>

<span data-ttu-id="15ed0-245">Por padrão, todos os provedores exportados por um módulo na sessão ficam visíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-245">By default, all providers exported by a module in the session are visible in the session.</span></span> <span data-ttu-id="15ed0-246">Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos serão importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-246">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="15ed0-247">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.</span><span class="sxs-lookup"><span data-stu-id="15ed0-247">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="15ed0-248">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="15ed0-248">CommonParameters</span></span>

<span data-ttu-id="15ed0-249">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="15ed0-249">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="15ed0-250">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="15ed0-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="15ed0-251">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="15ed0-251">INPUTS</span></span>

## <span data-ttu-id="15ed0-252">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="15ed0-252">OUTPUTS</span></span>

## <span data-ttu-id="15ed0-253">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="15ed0-253">NOTES</span></span>

## <span data-ttu-id="15ed0-254">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="15ed0-254">RELATED LINKS</span></span>

[<span data-ttu-id="15ed0-255">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="15ed0-255">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="15ed0-256">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="15ed0-256">Get-PSSessionCapability</span></span>](Get-PSSessionCapability.md)
