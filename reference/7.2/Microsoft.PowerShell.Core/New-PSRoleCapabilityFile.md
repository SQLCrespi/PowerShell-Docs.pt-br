---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-psrolecapabilityfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSRoleCapabilityFile
ms.openlocfilehash: 3ef54618e065a5fca3d52415897b3042d6ba4c65
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598848"
---
# <span data-ttu-id="3670a-102">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="3670a-102">New-PSRoleCapabilityFile</span></span>

## <span data-ttu-id="3670a-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3670a-103">SYNOPSIS</span></span>
<span data-ttu-id="3670a-104">Cria um arquivo que define um conjunto de recursos a serem expostos por meio de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-104">Creates a file that defines a set of capabilities to be exposed through a session configuration.</span></span>

## <span data-ttu-id="3670a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3670a-105">SYNTAX</span></span>

```
New-PSRoleCapabilityFile [-Path] <String> [-Guid <Guid>] [-Author <String>] [-Description <String>]
 [-CompanyName <String>] [-Copyright <String>] [-ModulesToImport <Object[]>] [-VisibleAliases <String[]>]
 [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>] [-VisibleExternalCommands <String[]>]
 [-VisibleProviders <String[]>] [-ScriptsToProcess <String[]>] [-AliasDefinitions <IDictionary[]>]
 [-FunctionDefinitions <IDictionary[]>] [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>]
 [-TypesToProcess <String[]>] [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="3670a-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3670a-106">DESCRIPTION</span></span>

<span data-ttu-id="3670a-107">O `New-PSRoleCapabilityFile` cmdlet cria um arquivo que define um conjunto de recursos de usuário que pode ser exposto por meio de arquivos de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-107">The `New-PSRoleCapabilityFile` cmdlet creates a file that defines a set of user capabilities that can be exposed through session configuration files.</span></span> <span data-ttu-id="3670a-108">Isso inclui determinar quais cmdlets, funções e scripts estão disponíveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="3670a-108">This includes determining which cmdlets, functions, and scripts are available to users.</span></span> <span data-ttu-id="3670a-109">O arquivo de capacidade é um arquivo de texto legível que contém uma tabela de hash de valores e propriedades de configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-109">The capability file is a human-readable text file that contains a hash table of session configuration properties and values.</span></span> <span data-ttu-id="3670a-110">O arquivo tem uma extensão de nome de arquivo. pSrc e pode ser usado por mais de uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-110">The file has a .psrc file name extension, and can be used by more than one session configuration.</span></span>

<span data-ttu-id="3670a-111">Todos os parâmetros de `New-PSRoleCapabilityFile` são opcionais, exceto o parâmetro **Path** , que especifica o caminho do arquivo para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="3670a-111">All the parameters of `New-PSRoleCapabilityFile` are optional except for the **Path** parameter, which specifies the file path for the file.</span></span> <span data-ttu-id="3670a-112">Se você não incluir um parâmetro ao executar o cmdlet, a chave correspondente no arquivo de configuração de sessão será comentada, exceto quando indicado na descrição do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="3670a-112">If you do not include a parameter when you run the cmdlet, the corresponding key in the session configuration file is commented-out, except where noted in the parameter description.</span></span> <span data-ttu-id="3670a-113">Por exemplo, se você não incluir o parâmetro **AssembliesToLoad** , essa seção do arquivo de configuração de sessão será comentada.</span><span class="sxs-lookup"><span data-stu-id="3670a-113">For example, if you do not include the **AssembliesToLoad** parameter then that section of the session configuration file is commented out.</span></span>

<span data-ttu-id="3670a-114">Para usar o arquivo de capacidade de função em uma configuração de sessão, primeiro coloque o arquivo em uma subpasta **RoleCapabilities** de uma pasta de módulo do PowerShell válida.</span><span class="sxs-lookup"><span data-stu-id="3670a-114">To use the role capability file in a session configuration, first place the file in a **RoleCapabilities** subfolder of a valid PowerShell module folder.</span></span> <span data-ttu-id="3670a-115">Em seguida, referencie o arquivo pelo nome no campo **RoleDefinitions** em um arquivo de configuração de sessão do PowerShell (. PSSC).</span><span class="sxs-lookup"><span data-stu-id="3670a-115">Then reference the file by name in the **RoleDefinitions** field in a PowerShell Session Configuration (.pssc) file.</span></span>

<span data-ttu-id="3670a-116">Esse cmdlet foi introduzido no Windows PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="3670a-116">This cmdlet was introduced in Windows PowerShell 5.0.</span></span>

## <span data-ttu-id="3670a-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3670a-117">EXAMPLES</span></span>

### <span data-ttu-id="3670a-118">Exemplo 1: criar um arquivo de capacidade de função em branco</span><span class="sxs-lookup"><span data-stu-id="3670a-118">Example 1: Create a blank role capability file</span></span>

<span data-ttu-id="3670a-119">Este exemplo cria um novo arquivo de capacidade de função que usa os valores padrão (em branco).</span><span class="sxs-lookup"><span data-stu-id="3670a-119">This example creates a new role capability file that uses the default (blank) values.</span></span> <span data-ttu-id="3670a-120">O arquivo pode ser editado posteriormente em um editor de texto para alterar essas definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="3670a-120">The file can later be edited in a text editor to change these configuration settings.</span></span>

```powershell
New-PSRoleCapabilityFile -Path ".\ExampleFile.psrc"
```

### <span data-ttu-id="3670a-121">Exemplo 2: criar um arquivo de capacidade de função permitindo que os usuários reiniciem serviços e qualquer computador VDI</span><span class="sxs-lookup"><span data-stu-id="3670a-121">Example 2: Create a role capability file allowing users to restart services and any VDI computer</span></span>

<span data-ttu-id="3670a-122">Este exemplo cria um arquivo de capacidade de função de exemplo que permite que os usuários reiniciem serviços e computadores que correspondam a um padrão de nome específico.</span><span class="sxs-lookup"><span data-stu-id="3670a-122">This example creates a sample role capability file that enables users to restart services and computers that match a specific name pattern.</span></span> <span data-ttu-id="3670a-123">A filtragem de nomes é definida pela definição do parâmetro **ValidatePattern** para a expressão regular `VDI\d+` .</span><span class="sxs-lookup"><span data-stu-id="3670a-123">Name filtering is defined by setting the **ValidatePattern** parameter to the regular expression `VDI\d+`.</span></span>

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

## <span data-ttu-id="3670a-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3670a-124">PARAMETERS</span></span>

### <span data-ttu-id="3670a-125">-AliasDefinitions</span><span class="sxs-lookup"><span data-stu-id="3670a-125">-AliasDefinitions</span></span>

<span data-ttu-id="3670a-126">Adiciona os aliases especificados a sessões que usam o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-126">Adds the specified aliases to sessions that use the role capability file.</span></span> <span data-ttu-id="3670a-127">Insira uma tabela de hash com as seguintes chaves:</span><span class="sxs-lookup"><span data-stu-id="3670a-127">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="3670a-128">Nome.</span><span class="sxs-lookup"><span data-stu-id="3670a-128">Name.</span></span> <span data-ttu-id="3670a-129">Nome do alias.</span><span class="sxs-lookup"><span data-stu-id="3670a-129">Name of the alias.</span></span> <span data-ttu-id="3670a-130">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="3670a-130">This key is required.</span></span>
- <span data-ttu-id="3670a-131">Value.</span><span class="sxs-lookup"><span data-stu-id="3670a-131">Value.</span></span> <span data-ttu-id="3670a-132">O comando que o alias representa.</span><span class="sxs-lookup"><span data-stu-id="3670a-132">The command that the alias represents.</span></span> <span data-ttu-id="3670a-133">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="3670a-133">This key is required.</span></span>
- <span data-ttu-id="3670a-134">Descrição.</span><span class="sxs-lookup"><span data-stu-id="3670a-134">Description.</span></span> <span data-ttu-id="3670a-135">Uma cadeia de caracteres de texto que descreve o alias.</span><span class="sxs-lookup"><span data-stu-id="3670a-135">A text string that describes the alias.</span></span> <span data-ttu-id="3670a-136">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="3670a-136">This key is optional.</span></span>
- <span data-ttu-id="3670a-137">Opções.</span><span class="sxs-lookup"><span data-stu-id="3670a-137">Options.</span></span> <span data-ttu-id="3670a-138">Opções de alias.</span><span class="sxs-lookup"><span data-stu-id="3670a-138">Alias options.</span></span> <span data-ttu-id="3670a-139">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="3670a-139">This key is optional.</span></span> <span data-ttu-id="3670a-140">O valor padrão é Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3670a-140">The default value is None.</span></span> <span data-ttu-id="3670a-141">Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.</span><span class="sxs-lookup"><span data-stu-id="3670a-141">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="3670a-142">Por exemplo: `@{Name="hlp";Value="Get-Help";Description="Gets help";Options="ReadOnly"}`</span><span class="sxs-lookup"><span data-stu-id="3670a-142">For example: `@{Name="hlp";Value="Get-Help";Description="Gets help";Options="ReadOnly"}`</span></span>

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

### <span data-ttu-id="3670a-143">-AssembliesToLoad</span><span class="sxs-lookup"><span data-stu-id="3670a-143">-AssembliesToLoad</span></span>

<span data-ttu-id="3670a-144">Especifica os assemblies a serem carregados nas sessões que usam o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-144">Specifies the assemblies to load into the sessions that use the role capability file.</span></span>

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

### <span data-ttu-id="3670a-145">-Autor</span><span class="sxs-lookup"><span data-stu-id="3670a-145">-Author</span></span>

<span data-ttu-id="3670a-146">Especifica o usuário que criou o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-146">Specifies the user that created the role capability file.</span></span>

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

### <span data-ttu-id="3670a-147">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="3670a-147">-CompanyName</span></span>

<span data-ttu-id="3670a-148">Identifica a empresa que criou o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-148">Identifies the company that created the role capability file.</span></span>
<span data-ttu-id="3670a-149">O valor padrão é Desconhecido.</span><span class="sxs-lookup"><span data-stu-id="3670a-149">The default value is Unknown.</span></span>

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

### <span data-ttu-id="3670a-150">-Direitos autorais</span><span class="sxs-lookup"><span data-stu-id="3670a-150">-Copyright</span></span>

<span data-ttu-id="3670a-151">Especifica um direito autoral para o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-151">Specifies a copyright for the role capability file.</span></span> <span data-ttu-id="3670a-152">Se você omitir esse parâmetro, o `New-PSRoleCapabilityFile` gerará uma declaração de direitos autorais usando o valor do parâmetro **Author** .</span><span class="sxs-lookup"><span data-stu-id="3670a-152">If you omit this parameter, `New-PSRoleCapabilityFile` generates a copyright statement by using the value of the **Author** parameter.</span></span>

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

### <span data-ttu-id="3670a-153">-Description</span><span class="sxs-lookup"><span data-stu-id="3670a-153">-Description</span></span>

<span data-ttu-id="3670a-154">Especifica uma descrição para o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-154">Specifies a description for the role capability file.</span></span>

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

### <span data-ttu-id="3670a-155">-EnvironmentVariables</span><span class="sxs-lookup"><span data-stu-id="3670a-155">-EnvironmentVariables</span></span>

<span data-ttu-id="3670a-156">Especifica as variáveis de ambiente para sessões que expõem esse arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-156">Specifies the environment variables for sessions that expose this role capability file.</span></span> <span data-ttu-id="3670a-157">Insira uma tabela de hash na qual as chaves são nomes de variáveis de ambiente e os valores são valores de variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="3670a-157">Enter a hash table in which the keys are the environment variable names and the values are the environment variable values.</span></span>

<span data-ttu-id="3670a-158">Por exemplo: `EnvironmentVariables=@{TestShare="\\\\Server01\TestShare"}`</span><span class="sxs-lookup"><span data-stu-id="3670a-158">For example: `EnvironmentVariables=@{TestShare="\\\\Server01\TestShare"}`</span></span>

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

### <span data-ttu-id="3670a-159">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="3670a-159">-FormatsToProcess</span></span>

<span data-ttu-id="3670a-160">Especifica os arquivos de formatação (. ps1xml) que são executados em sessões que usam o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-160">Specifies the formatting files (.ps1xml) that run in sessions that use the role capability file.</span></span> <span data-ttu-id="3670a-161">O valor desse parâmetro deve ser um caminho completo ou absoluto dos arquivos de formatação.</span><span class="sxs-lookup"><span data-stu-id="3670a-161">The value of this parameter must be a full or absolute path of the formatting files.</span></span>

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

### <span data-ttu-id="3670a-162">-FunctionDefinitions</span><span class="sxs-lookup"><span data-stu-id="3670a-162">-FunctionDefinitions</span></span>

<span data-ttu-id="3670a-163">Adiciona as funções especificadas às sessões que expõem a capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-163">Adds the specified functions to sessions that expose the role capability.</span></span> <span data-ttu-id="3670a-164">Insira uma tabela de hash com as seguintes chaves:</span><span class="sxs-lookup"><span data-stu-id="3670a-164">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="3670a-165">Nome.</span><span class="sxs-lookup"><span data-stu-id="3670a-165">Name.</span></span> <span data-ttu-id="3670a-166">Nome da função.</span><span class="sxs-lookup"><span data-stu-id="3670a-166">Name of the function.</span></span> <span data-ttu-id="3670a-167">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="3670a-167">This key is required.</span></span>
- <span data-ttu-id="3670a-168">ScriptBlock.</span><span class="sxs-lookup"><span data-stu-id="3670a-168">ScriptBlock.</span></span> <span data-ttu-id="3670a-169">Corpo da função.</span><span class="sxs-lookup"><span data-stu-id="3670a-169">Function body.</span></span> <span data-ttu-id="3670a-170">Insira um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="3670a-170">Enter a script block.</span></span> <span data-ttu-id="3670a-171">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="3670a-171">This key is required.</span></span>
- <span data-ttu-id="3670a-172">Opções.</span><span class="sxs-lookup"><span data-stu-id="3670a-172">Options.</span></span> <span data-ttu-id="3670a-173">Opções de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-173">Function options.</span></span> <span data-ttu-id="3670a-174">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="3670a-174">This key is optional.</span></span> <span data-ttu-id="3670a-175">O valor padrão é Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3670a-175">The default value is None.</span></span> <span data-ttu-id="3670a-176">Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.</span><span class="sxs-lookup"><span data-stu-id="3670a-176">The acceptable values for this parameter are: are None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="3670a-177">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3670a-177">For example:</span></span>

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

### <span data-ttu-id="3670a-178">-GUID</span><span class="sxs-lookup"><span data-stu-id="3670a-178">-Guid</span></span>

<span data-ttu-id="3670a-179">Especifica um identificador exclusivo para o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-179">Specifies a unique identifier for the role capability file.</span></span> <span data-ttu-id="3670a-180">Se você omitir esse parâmetro, o `New-PSRoleCapabilityFile` gerará um GUID para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="3670a-180">If you omit this parameter, `New-PSRoleCapabilityFile` generates a GUID for the file.</span></span> <span data-ttu-id="3670a-181">Para criar um novo GUID no PowerShell, digite `[guid]::NewGuid()` .</span><span class="sxs-lookup"><span data-stu-id="3670a-181">To create a new GUID in PowerShell, type `[guid]::NewGuid()`.</span></span>

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

### <span data-ttu-id="3670a-182">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="3670a-182">-ModulesToImport</span></span>

<span data-ttu-id="3670a-183">Especifica os módulos que são automaticamente importados para sessões que usam o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-183">Specifies the modules that are automatically imported into sessions that use the role capability file.</span></span> <span data-ttu-id="3670a-184">Por padrão, todos os comandos nos módulos listados são visíveis.</span><span class="sxs-lookup"><span data-stu-id="3670a-184">By default, all the commands in listed modules are visible.</span></span> <span data-ttu-id="3670a-185">Quando usado com **VisibleCmdlets** ou **VisibleFunctions**, os comandos visíveis dos módulos especificados podem ser restritos.</span><span class="sxs-lookup"><span data-stu-id="3670a-185">When used with **VisibleCmdlets** or **VisibleFunctions**, the commands visible from the specified modules can be restricted.</span></span>

<span data-ttu-id="3670a-186">Cada módulo usado no valor desse parâmetro pode ser representado por uma cadeia de caracteres ou por uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="3670a-186">Each module used in the value of this parameter can be represented by a string or by a hash table.</span></span> <span data-ttu-id="3670a-187">Uma cadeia de caracteres de módulo consiste apenas no nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="3670a-187">A module string consists only of the name of the module.</span></span> <span data-ttu-id="3670a-188">Uma tabela de hash de módulo pode incluir as chaves **ModuleName**, **ModuleVersion** e **GUID** .</span><span class="sxs-lookup"><span data-stu-id="3670a-188">A module hash table can include **ModuleName**, **ModuleVersion**, and **GUID** keys.</span></span> <span data-ttu-id="3670a-189">Somente a chave **ModuleName** é necessária.</span><span class="sxs-lookup"><span data-stu-id="3670a-189">Only the **ModuleName** key is required.</span></span>

<span data-ttu-id="3670a-190">Por exemplo, o seguinte valor consiste em uma cadeia de caracteres e uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="3670a-190">For example, the following value consists of a string and a hash table.</span></span> <span data-ttu-id="3670a-191">Qualquer combinação de cadeias de caracteres e tabelas de hash, em qualquer ordem, é válida.</span><span class="sxs-lookup"><span data-stu-id="3670a-191">Any combination of strings and hash tables, in any order, is valid.</span></span>

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

### <span data-ttu-id="3670a-192">-Path</span><span class="sxs-lookup"><span data-stu-id="3670a-192">-Path</span></span>

<span data-ttu-id="3670a-193">Especifica o caminho e o nome do arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-193">Specifies the path and filename of the role capability file.</span></span> <span data-ttu-id="3670a-194">O arquivo deve ter uma `.psrc` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="3670a-194">The file must have a `.psrc` filename extension.</span></span>

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

### <span data-ttu-id="3670a-195">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="3670a-195">-ScriptsToProcess</span></span>

<span data-ttu-id="3670a-196">Especifica os scripts a serem adicionados às sessões que usam o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-196">Specifies scripts to add to sessions that use the role capability file.</span></span> <span data-ttu-id="3670a-197">Digite os nomes de arquivo e caminho dos scripts.</span><span class="sxs-lookup"><span data-stu-id="3670a-197">Enter the path and file names of the scripts.</span></span> <span data-ttu-id="3670a-198">O valor desse parâmetro deve ser um caminho completo ou absoluto dos nomes de arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="3670a-198">The value of this parameter must be a full or absolute path of the script file names.</span></span>

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

### <span data-ttu-id="3670a-199">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="3670a-199">-TypesToProcess</span></span>

<span data-ttu-id="3670a-200">Especifica os arquivos de tipo (. ps1xml) a serem adicionados às sessões que usam o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-200">Specifies type files (.ps1xml) to add to sessions that use the role capability file.</span></span> <span data-ttu-id="3670a-201">Insira os nomes de filetype.</span><span class="sxs-lookup"><span data-stu-id="3670a-201">Enter the type filenames.</span></span> <span data-ttu-id="3670a-202">O valor desse parâmetro deve ser um caminho completo ou absoluto do tipo nomes de texto.</span><span class="sxs-lookup"><span data-stu-id="3670a-202">The value of this parameter must be a full or absolute path of the type filenames.</span></span>

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

### <span data-ttu-id="3670a-203">-VariableDefinitions</span><span class="sxs-lookup"><span data-stu-id="3670a-203">-VariableDefinitions</span></span>

<span data-ttu-id="3670a-204">Especifica as variáveis a serem adicionadas às sessões que usam o arquivo de capacidade de função.</span><span class="sxs-lookup"><span data-stu-id="3670a-204">Specifies variables to add to sessions that use the role capability file.</span></span> <span data-ttu-id="3670a-205">Insira uma tabela de hash com as seguintes chaves:</span><span class="sxs-lookup"><span data-stu-id="3670a-205">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="3670a-206">Nome.</span><span class="sxs-lookup"><span data-stu-id="3670a-206">Name.</span></span> <span data-ttu-id="3670a-207">Nome da variável.</span><span class="sxs-lookup"><span data-stu-id="3670a-207">Name of the variable.</span></span> <span data-ttu-id="3670a-208">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="3670a-208">This key is required.</span></span>
- <span data-ttu-id="3670a-209">Value.</span><span class="sxs-lookup"><span data-stu-id="3670a-209">Value.</span></span> <span data-ttu-id="3670a-210">Valor da variável.</span><span class="sxs-lookup"><span data-stu-id="3670a-210">Variable value.</span></span> <span data-ttu-id="3670a-211">Essa chave é necessária.</span><span class="sxs-lookup"><span data-stu-id="3670a-211">This key is required.</span></span>
- <span data-ttu-id="3670a-212">Opções.</span><span class="sxs-lookup"><span data-stu-id="3670a-212">Options.</span></span> <span data-ttu-id="3670a-213">Opções de variáveis.</span><span class="sxs-lookup"><span data-stu-id="3670a-213">Variable options.</span></span> <span data-ttu-id="3670a-214">Essa chave é opcional.</span><span class="sxs-lookup"><span data-stu-id="3670a-214">This key is optional.</span></span> <span data-ttu-id="3670a-215">O valor padrão é Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3670a-215">The default value is None.</span></span> <span data-ttu-id="3670a-216">Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.</span><span class="sxs-lookup"><span data-stu-id="3670a-216">The acceptable values for this parameter are: are None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="3670a-217">Por exemplo: `@{Name="WarningPreference";Value="SilentlyContinue";Options="AllScope"}`</span><span class="sxs-lookup"><span data-stu-id="3670a-217">For example: `@{Name="WarningPreference";Value="SilentlyContinue";Options="AllScope"}`</span></span>

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

### <span data-ttu-id="3670a-218">-VisibleAliases</span><span class="sxs-lookup"><span data-stu-id="3670a-218">-VisibleAliases</span></span>

<span data-ttu-id="3670a-219">Limita os aliases na sessão para os aliases especificados no valor desse parâmetro, além de todos os aliases que você definir no parâmetro **AliasDefinition** .</span><span class="sxs-lookup"><span data-stu-id="3670a-219">Limits the aliases in the session to those aliases specified in the value of this parameter, plus any aliases that you define in the **AliasDefinition** parameter.</span></span> <span data-ttu-id="3670a-220">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="3670a-220">Wildcard characters are supported.</span></span>
<span data-ttu-id="3670a-221">Por padrão, todos os aliases que são definidos pelo mecanismo do PowerShell e todos os aliases que os módulos exportam são visíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-221">By default, all aliases that are defined by the PowerShell engine and all aliases that modules export are visible in the session.</span></span>

<span data-ttu-id="3670a-222">Por exemplo, para limitar os aliases disponíveis para o GM e o gcm, use esta sintaxe: `VisibleAliases="gcm", "gp"`</span><span class="sxs-lookup"><span data-stu-id="3670a-222">For example, to limit the available aliases to gm and gcm use this syntax: `VisibleAliases="gcm", "gp"`</span></span>

<span data-ttu-id="3670a-223">Quando qualquer parâmetro **visível** é incluído no arquivo de capacidade de função, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-223">When any **Visible** parameter is included in the role capability file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="3670a-224">-VisibleCmdlets</span><span class="sxs-lookup"><span data-stu-id="3670a-224">-VisibleCmdlets</span></span>

<span data-ttu-id="3670a-225">Limita os cmdlets na sessão para aquelas especificadas no valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="3670a-225">Limits the cmdlets in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="3670a-226">Há suporte para caracteres curinga e nomes qualificados de módulo.</span><span class="sxs-lookup"><span data-stu-id="3670a-226">Wildcard characters and Module Qualified Names are supported.</span></span>

<span data-ttu-id="3670a-227">Por padrão, todos os cmdlets que os módulos na sessão exportam são visíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-227">By default, all cmdlets that the modules in the session export are visible in the session.</span></span> <span data-ttu-id="3670a-228">Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos e snap-ins são importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-228">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span> <span data-ttu-id="3670a-229">Se nenhum módulo no **ModulesToImport** expor o cmdlet, o `New-PSRoleCapabilityFile` tentará carregar o módulo apropriado.</span><span class="sxs-lookup"><span data-stu-id="3670a-229">If no modules in **ModulesToImport** expose the cmdlet, `New-PSRoleCapabilityFile` tries to load the appropriate module.</span></span>

<span data-ttu-id="3670a-230">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-230">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="3670a-231">-VisibleExternalCommands</span><span class="sxs-lookup"><span data-stu-id="3670a-231">-VisibleExternalCommands</span></span>

<span data-ttu-id="3670a-232">Limita os binários, os scripts e os comandos externos que podem ser executados na sessão para aqueles especificados no valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="3670a-232">Limits the external binaries, scripts and commands that can be executed in the session to those specified in the value of this parameter.</span></span>

<span data-ttu-id="3670a-233">Por padrão, nenhum comando externo é visível nesta sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-233">By default, no external commands are visible in this session.</span></span>

<span data-ttu-id="3670a-234">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-234">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="3670a-235">-VisibleFunctions</span><span class="sxs-lookup"><span data-stu-id="3670a-235">-VisibleFunctions</span></span>

<span data-ttu-id="3670a-236">Limita as funções na sessão àqueles especificados no valor desse parâmetro, além de qualquer função que você definir no parâmetro **FunctionDefinitions** .</span><span class="sxs-lookup"><span data-stu-id="3670a-236">Limits the functions in the session to those specified in the value of this parameter, plus any functions that you define in the **FunctionDefinitions** parameter.</span></span> <span data-ttu-id="3670a-237">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="3670a-237">Wildcard characters are supported.</span></span>

<span data-ttu-id="3670a-238">Por padrão, todas as funções exportadas por módulos na sessão ficam visíveis nessa sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-238">By default, all functions exported by modules in the session are visible in that session.</span></span> <span data-ttu-id="3670a-239">Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos serão importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-239">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="3670a-240">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-240">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="3670a-241">-VisibleProviders</span><span class="sxs-lookup"><span data-stu-id="3670a-241">-VisibleProviders</span></span>

<span data-ttu-id="3670a-242">Limita os provedores do PowerShell na sessão para aqueles especificados no valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="3670a-242">Limits the PowerShell providers in the session to those specified in the value of this parameter.</span></span>
<span data-ttu-id="3670a-243">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="3670a-243">Wildcard characters are supported.</span></span>

<span data-ttu-id="3670a-244">Por padrão, todos os provedores exportados por um módulo na sessão ficam visíveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-244">By default, all providers exported by a module in the session are visible in the session.</span></span> <span data-ttu-id="3670a-245">Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos serão importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-245">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="3670a-246">Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.</span><span class="sxs-lookup"><span data-stu-id="3670a-246">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="3670a-247">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3670a-247">CommonParameters</span></span>

<span data-ttu-id="3670a-248">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3670a-248">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3670a-249">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3670a-249">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3670a-250">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3670a-250">INPUTS</span></span>

## <span data-ttu-id="3670a-251">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3670a-251">OUTPUTS</span></span>

## <span data-ttu-id="3670a-252">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3670a-252">NOTES</span></span>

## <span data-ttu-id="3670a-253">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3670a-253">RELATED LINKS</span></span>

[<span data-ttu-id="3670a-254">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="3670a-254">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="3670a-255">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="3670a-255">Get-PSSessionCapability</span></span>](Get-PSSessionCapability.md)

