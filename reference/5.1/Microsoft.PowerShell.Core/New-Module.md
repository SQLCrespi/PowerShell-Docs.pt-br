---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Module
ms.openlocfilehash: 2a30b8a86098a9d3ffdf8e48b092ac419d6b6e95
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193310"
---
# <span data-ttu-id="cfbcb-103">New-Module</span><span class="sxs-lookup"><span data-stu-id="cfbcb-103">New-Module</span></span>

## <span data-ttu-id="cfbcb-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="cfbcb-104">SYNOPSIS</span></span>
<span data-ttu-id="cfbcb-105">Cria um novo módulo dinâmico que existe apenas na memória.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-105">Creates a new dynamic module that exists only in memory.</span></span>

## <span data-ttu-id="cfbcb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cfbcb-106">SYNTAX</span></span>

### <span data-ttu-id="cfbcb-107">ScriptBlock (padrão)</span><span class="sxs-lookup"><span data-stu-id="cfbcb-107">ScriptBlock (Default)</span></span>

```
New-Module [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>] [-ReturnResult]
 [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="cfbcb-108">Name</span><span class="sxs-lookup"><span data-stu-id="cfbcb-108">Name</span></span>

```
New-Module [-Name] <String> [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>]
 [-ReturnResult] [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="cfbcb-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cfbcb-109">DESCRIPTION</span></span>

<span data-ttu-id="cfbcb-110">O `New-Module` cmdlet cria um módulo dinâmico a partir de um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-110">The `New-Module` cmdlet creates a dynamic module from a script block.</span></span> <span data-ttu-id="cfbcb-111">Os membros do módulo dinâmico, como funções e variáveis, ficam imediatamente disponíveis na sessão e permanecem disponíveis até que você feche a sessão.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-111">The members of the dynamic module, such as functions and variables, are immediately available in the session and remain available until you close the session.</span></span>

<span data-ttu-id="cfbcb-112">Semelhante aos módulos estáticos, por padrão, os cmdlets e funções em um módulo dinâmico são exportadas e as variáveis e os aliases não são.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-112">Like static modules, by default, the cmdlets and functions in a dynamic module are exported and the variables and aliases are not.</span></span> <span data-ttu-id="cfbcb-113">No entanto, você pode usar o cmdlet Export-ModuleMember e os parâmetros de `New-Module` para substituir os padrões.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-113">However, you can use the Export-ModuleMember cmdlet and the parameters of `New-Module` to override the defaults.</span></span>

<span data-ttu-id="cfbcb-114">Você também pode usar o parâmetro **AsCustomObject** de `New-Module` para retornar o módulo dinâmico como um objeto personalizado.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-114">You can also use the **AsCustomObject** parameter of `New-Module` to return the dynamic module as a custom object.</span></span> <span data-ttu-id="cfbcb-115">Os membros dos módulos, como funções, são implementados como métodos de script do objeto personalizado em vez de serem importadas para a sessão.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-115">The members of the modules, such as functions, are implemented as script methods of the custom object instead of being imported into the session.</span></span>

<span data-ttu-id="cfbcb-116">Módulos dinâmicos existem apenas na memória, não no disco.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-116">Dynamic modules exist only in memory, not on disk.</span></span> <span data-ttu-id="cfbcb-117">Assim como todos os módulos, os membros de módulos dinâmicos são executados em um escopo de módulo privado que é um filho do escopo global.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-117">Like all modules, the members of dynamic modules run in a private module scope that is a child of the global scope.</span></span> <span data-ttu-id="cfbcb-118">Get-Module não obtém um módulo dinâmico, mas Get-Command pode obter os membros exportados.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-118">Get-Module cannot get a dynamic module, but Get-Command can get the exported members.</span></span>

<span data-ttu-id="cfbcb-119">Para disponibilizar um módulo dinâmico para `Get-Module` o, direcione um `New-Module` comando para Import-Module ou direcione o objeto de módulo que `New-Module` retorna para `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="cfbcb-119">To make a dynamic module available to `Get-Module`, pipe a `New-Module` command to Import-Module, or pipe the module object that `New-Module` returns to `Import-Module`.</span></span> <span data-ttu-id="cfbcb-120">Essa ação adiciona o módulo dinâmico à `Get-Module` lista, mas não salva o módulo no disco nem o torna persistente.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-120">This action adds the dynamic module to the `Get-Module` list, but it does not save the module to disk or make it persistent.</span></span>

## <span data-ttu-id="cfbcb-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="cfbcb-121">EXAMPLES</span></span>

### <span data-ttu-id="cfbcb-122">Exemplo 1: criar um módulo dinâmico</span><span class="sxs-lookup"><span data-stu-id="cfbcb-122">Example 1: Create a dynamic module</span></span>

<span data-ttu-id="cfbcb-123">Este exemplo cria um novo módulo dinâmico com uma função chamada `Hello` .</span><span class="sxs-lookup"><span data-stu-id="cfbcb-123">This example creates a new dynamic module with a function called `Hello`.</span></span> <span data-ttu-id="cfbcb-124">O comando retorna um objeto de módulo que representa o novo módulo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-124">The command returns a module object that represents the new dynamic module.</span></span>

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

### <span data-ttu-id="cfbcb-125">Exemplo 2: trabalhando com módulos dinâmicos e Get-Module e Get-Command</span><span class="sxs-lookup"><span data-stu-id="cfbcb-125">Example 2: Working with dynamic modules and Get-Module and Get-Command</span></span>

<span data-ttu-id="cfbcb-126">Este exemplo demonstra que os módulos dinâmicos não são retornados pelo `Get-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-126">This example demonstrates that dynamic modules are not returned by the `Get-Module` cmdlet.</span></span> <span data-ttu-id="cfbcb-127">Os membros que eles exportam são retornados pelo `Get-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-127">The members that they export are returned by the `Get-Command` cmdlet.</span></span>

```powershell
new-module -scriptblock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Module

Get-Command Hello
```

```Output
CommandType     Name   Definition
-----------     ----   ----------
Function        Hello  "Hello!"
```

### <span data-ttu-id="cfbcb-128">Exemplo 3: exportar uma variável para a sessão atual</span><span class="sxs-lookup"><span data-stu-id="cfbcb-128">Example 3: Export a variable into the current session</span></span>

<span data-ttu-id="cfbcb-129">Este exemplo usa o `Export-ModuleMember` cmdlet para exportar uma variável para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-129">This example uses the `Export-ModuleMember` cmdlet to export a variable into the current session.</span></span>
<span data-ttu-id="cfbcb-130">Sem o `Export-ModuleMember` comando, apenas a função é exportada.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-130">Without the `Export-ModuleMember` command, only the function is exported.</span></span>

```powershell
New-Module -ScriptBlock {$SayHelloHelp="Type 'SayHello', a space, and a name."; function SayHello ($name) { "Hello, $name" }; Export-ModuleMember -function SayHello -Variable SayHelloHelp}
$SayHelloHelp
```

```Output
Type 'SayHello', a space, and a name.
```

```powershell
SayHello Jeffrey
```

```Output
Hello, Jeffrey
```

<span data-ttu-id="cfbcb-131">A saída mostra que a variável e a função foram exportadas para a sessão.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-131">The output shows that both the variable and the function were exported into the session.</span></span>

### <span data-ttu-id="cfbcb-132">Exemplo 4: tornar um módulo dinâmico disponível para Get-Module</span><span class="sxs-lookup"><span data-stu-id="cfbcb-132">Example 4: Make a dynamic module available to Get-Module</span></span>

<span data-ttu-id="cfbcb-133">Este exemplo demonstra que você pode disponibilizar um módulo dinâmico para `Get-Module` o ao canalizar o módulo dinâmico para o `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="cfbcb-133">This example demonstrates that you can make a dynamic module available to `Get-Module` by piping the dynamic module to `Import-Module`.</span></span>

<span data-ttu-id="cfbcb-134">`New-Module` Cria um objeto de módulo que é canalizado para o `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-134">`New-Module` creates a module object that is piped to the `Import-Module` cmdlet.</span></span> <span data-ttu-id="cfbcb-135">O parâmetro **Name** de `New-Module` atribui um nome amigável ao módulo.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-135">The **Name** parameter of `New-Module` assigns a friendly name to the module.</span></span> <span data-ttu-id="cfbcb-136">Como `Import-Module` o não retorna nenhum objeto por padrão, não há nenhuma saída desse comando.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-136">Because `Import-Module` does not return any objects by default, there is no output from this command.</span></span> <span data-ttu-id="cfbcb-137">`Get-Module` Se o **GreetingModule** foi importado para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-137">`Get-Module` that the **GreetingModule** has been imported into the current session.</span></span>

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}} -name GreetingModule | Import-Module
Get-Module
```

```Output
Name              : GreetingModule
Path              : d54dfdac-4531-4db2-9dec-0b4b9c57a1e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Command hello
```

```Output
CommandType     Name                                                               Definition
-----------     ----                                                               ----------
Function        Hello                                                              "Hello!"
```

<span data-ttu-id="cfbcb-138">O `Get-Command` cmdlet mostra a `Hello` função que o módulo dinâmico exporta.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-138">The `Get-Command` cmdlet shows the `Hello` function that the dynamic module exports.</span></span>

### <span data-ttu-id="cfbcb-139">Exemplo 5: gerar um objeto personalizado que tem funções exportadas</span><span class="sxs-lookup"><span data-stu-id="cfbcb-139">Example 5: Generate a custom object that has exported functions</span></span>

<span data-ttu-id="cfbcb-140">Este exemplo mostra como usar o parâmetro **AsCustomObject** de `New-Module` para gerar um objeto personalizado que tem métodos de script que representam as funções exportadas.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-140">This example shows how to use the **AsCustomObject** parameter of `New-Module` to generate a custom object that has script methods that represent the exported functions.</span></span>

<span data-ttu-id="cfbcb-141">O `New-Module` cmdlet cria um módulo dinâmico com duas funções `Hello` e `Goodbye` .</span><span class="sxs-lookup"><span data-stu-id="cfbcb-141">The `New-Module` cmdlet creates a dynamic module with two functions, `Hello` and `Goodbye`.</span></span> <span data-ttu-id="cfbcb-142">O parâmetro **AsCustomObject** cria um objeto personalizado em vez do objeto **PSModuleInfo** que `New-Module` gera por padrão.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-142">The **AsCustomObject** parameter creates a custom object instead of the **PSModuleInfo** object that `New-Module` generates by default.</span></span> <span data-ttu-id="cfbcb-143">Esse objeto personalizado é salvo na `$m` variável.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-143">This custom object is saved in the `$m` variable.</span></span>
<span data-ttu-id="cfbcb-144">A `$m` variável parece não ter nenhum valor atribuído.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-144">The `$m` variable appears to have no assigned value.</span></span>

```powershell
$m = New-Module -ScriptBlock {
  function Hello ($name) {"Hello, $name"}
  function Goodbye ($name) {"Goodbye, $name"}
} -AsCustomObject
$m
$m | Get-Member
```

```Output
TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Goodbye     ScriptMethod System.Object Goodbye();
Hello       ScriptMethod System.Object Hello();
```

```powershell
$m.goodbye("Jane")
```

```Output
Goodbye, Jane
```

```powershell
$m.hello("Manoj")
```

```Output
Hello, Manoj
```

<span data-ttu-id="cfbcb-145">A tubulação `$m` ao `Get-Member` cmdlet exibe as propriedades e os métodos do objeto personalizado.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-145">Piping `$m` to the `Get-Member` cmdlet displays the properties and methods of the custom object.</span></span> <span data-ttu-id="cfbcb-146">A saída mostra que o objeto tem métodos de script que representam `Hello` as `Goodbye` funções e.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-146">The output shows that the object has script methods that represent the `Hello` and `Goodbye` functions.</span></span>
<span data-ttu-id="cfbcb-147">Por fim, chamamos esses métodos de script e exibimos os resultados.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-147">Finally, we call these script methods and display the results.</span></span>

### <span data-ttu-id="cfbcb-148">Exemplo 6: obter os resultados do bloco de script</span><span class="sxs-lookup"><span data-stu-id="cfbcb-148">Example 6: Get the results of the script block</span></span>

<span data-ttu-id="cfbcb-149">Este exemplo usa o parâmetro **ReturnResult** para solicitar os resultados da execução do bloco de script em vez de solicitar um objeto de módulo.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-149">This example uses the **ReturnResult** parameter to request the results of running the script block instead of requesting a module object.</span></span> <span data-ttu-id="cfbcb-150">O bloco de script no novo módulo define a `SayHello` função e, em seguida, chama a função.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-150">The script block in the new module defines the `SayHello` function and then calls the function.</span></span>

```powershell
New-Module -ScriptBlock {function SayHello {"Hello, World!"}; SayHello} -ReturnResult
```

```Output
Hello, World!
```

## <span data-ttu-id="cfbcb-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cfbcb-151">PARAMETERS</span></span>

### <span data-ttu-id="cfbcb-152">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="cfbcb-152">-ArgumentList</span></span>

<span data-ttu-id="cfbcb-153">Especifica uma matriz de argumentos que são valores de parâmetro que são passados para o bloco de script.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-153">Specifies an array of arguments which are parameter values that are passed to the script block.</span></span> <span data-ttu-id="cfbcb-154">Para obter mais informações sobre o comportamento de **ArgumentList** , consulte [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="cfbcb-154">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfbcb-155">-AsCustomObject</span><span class="sxs-lookup"><span data-stu-id="cfbcb-155">-AsCustomObject</span></span>

<span data-ttu-id="cfbcb-156">Indica que esse cmdlet retorna um objeto personalizado que representa o módulo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-156">Indicates that this cmdlet returns a custom object that represents the dynamic module.</span></span> <span data-ttu-id="cfbcb-157">Os membros do módulo são implementados como métodos de script do objeto personalizado, mas eles não são importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-157">The module members are implemented as script methods of the custom object, but they are not imported into the session.</span></span> <span data-ttu-id="cfbcb-158">Você pode salvar o objeto personalizado em uma variável e usar a notação de ponto para invocar os membros.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-158">You can save the custom object in a variable and use dot notation to invoke the members.</span></span>

<span data-ttu-id="cfbcb-159">Se o módulo tiver vários membros com o mesmo nome, como uma função e uma variável que são nomeados como, somente um membro com cada nome poderá ser acessado do objeto personalizado.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-159">If the module has multiple members with the same name, such as a function and a variable that are both named A, only one member with each name can be accessed from the custom object.</span></span>

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

### <span data-ttu-id="cfbcb-160">-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="cfbcb-160">-Cmdlet</span></span>

<span data-ttu-id="cfbcb-161">Especifica uma matriz de cmdlets que esse cmdlet exporta do módulo para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-161">Specifies an array of cmdlets that this cmdlet exports from the module into the current session.</span></span>
<span data-ttu-id="cfbcb-162">Digite uma lista separada por vírgulas dos cmdlets.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-162">Enter a comma-separated list of cmdlets.</span></span> <span data-ttu-id="cfbcb-163">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-163">Wildcard characters are permitted.</span></span> <span data-ttu-id="cfbcb-164">Por padrão, todos os cmdlets no módulo são exportados.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-164">By default, all cmdlets in the module are exported.</span></span>

<span data-ttu-id="cfbcb-165">Você não pode definir os cmdlets em um bloco de script, mas um módulo dinâmico pode incluir cmdlets se importar os cmdlets de um módulo binário.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-165">You cannot define cmdlets in a script block, but a dynamic module can include cmdlets if it imports the cmdlets from a binary module.</span></span>

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

### <span data-ttu-id="cfbcb-166">-Função</span><span class="sxs-lookup"><span data-stu-id="cfbcb-166">-Function</span></span>

<span data-ttu-id="cfbcb-167">Especifica uma matriz de funções que esse cmdlet exporta do módulo para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-167">Specifies an array of functions that this cmdlet exports from the module into the current session.</span></span>
<span data-ttu-id="cfbcb-168">Digite uma lista separada por vírgulas de funções.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-168">Enter a comma-separated list of functions.</span></span> <span data-ttu-id="cfbcb-169">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-169">Wildcard characters are permitted.</span></span> <span data-ttu-id="cfbcb-170">Por padrão, todas as funções definidas em um módulo são exportadas.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-170">By default, all functions defined in a module are exported.</span></span>

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

### <span data-ttu-id="cfbcb-171">-Name</span><span class="sxs-lookup"><span data-stu-id="cfbcb-171">-Name</span></span>

<span data-ttu-id="cfbcb-172">Especifica um nome para o novo módulo.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-172">Specifies a name for the new module.</span></span> <span data-ttu-id="cfbcb-173">Também é possível direcionar um nome de computador para New-Module.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-173">You can also pipe a module name to New-Module.</span></span>

<span data-ttu-id="cfbcb-174">O valor padrão é um nome gerado automaticamente que começa com `__DynamicModule_` e é seguido por um GUID que especifica o caminho do módulo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-174">The default value is an autogenerated name that starts with `__DynamicModule_` and is followed by a GUID that specifies the path of the dynamic module.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="cfbcb-175">-ReturnResult</span><span class="sxs-lookup"><span data-stu-id="cfbcb-175">-ReturnResult</span></span>

<span data-ttu-id="cfbcb-176">Indica que esse cmdlet executa o bloco de script e retorna os resultados de bloco de script em vez de retornar um objeto de módulo.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-176">Indicates that this cmdlet runs the script block and returns the script block results instead of returning a module object.</span></span>

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

### <span data-ttu-id="cfbcb-177">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="cfbcb-177">-ScriptBlock</span></span>

<span data-ttu-id="cfbcb-178">Especifica o conteúdo do módulo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-178">Specifies the contents of the dynamic module.</span></span> <span data-ttu-id="cfbcb-179">Coloque o conteúdo entre chaves ( `{}` ) para criar um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-179">Enclose the contents in braces (`{}`) to create a script block.</span></span> <span data-ttu-id="cfbcb-180">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-180">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfbcb-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cfbcb-181">CommonParameters</span></span>

<span data-ttu-id="cfbcb-182">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cfbcb-183">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cfbcb-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cfbcb-184">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="cfbcb-184">INPUTS</span></span>

### <span data-ttu-id="cfbcb-185">System.String</span><span class="sxs-lookup"><span data-stu-id="cfbcb-185">System.String</span></span>

<span data-ttu-id="cfbcb-186">É possível canalizar um nome de módulo para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-186">You can pipe a module name to this cmdlet.</span></span>

## <span data-ttu-id="cfbcb-187">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="cfbcb-187">OUTPUTS</span></span>

### <span data-ttu-id="cfbcb-188">System. Management. Automation. PSModuleInfo, System. Management. Automation. PSCustomObject ou None</span><span class="sxs-lookup"><span data-stu-id="cfbcb-188">System.Management.Automation.PSModuleInfo, System.Management.Automation.PSCustomObject, or None</span></span>

<span data-ttu-id="cfbcb-189">Por padrão, esse cmdlet gera um objeto **PSModuleInfo** .</span><span class="sxs-lookup"><span data-stu-id="cfbcb-189">This cmdlet generates a **PSModuleInfo** object, by default.</span></span> <span data-ttu-id="cfbcb-190">Se você usar o parâmetro **AsCustomObject** , ele gerará um objeto **PSCustomObject** .</span><span class="sxs-lookup"><span data-stu-id="cfbcb-190">If you use the **AsCustomObject** parameter, it generates a **PSCustomObject** object.</span></span> <span data-ttu-id="cfbcb-191">Se você usar o parâmetro **ReturnResult** , ele retornará o resultado da avaliação do bloco de script no módulo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="cfbcb-191">If you use the **ReturnResult** parameter, it returns the result of evaluating the script block in the dynamic module.</span></span>

## <span data-ttu-id="cfbcb-192">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="cfbcb-192">NOTES</span></span>

<span data-ttu-id="cfbcb-193">Você também pode se referir `New-Module` por seu alias, `nmo` .</span><span class="sxs-lookup"><span data-stu-id="cfbcb-193">You can also refer to `New-Module` by its alias, `nmo`.</span></span> <span data-ttu-id="cfbcb-194">Para obter mais informações, consulte [about_Aliases](About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="cfbcb-194">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>

## <span data-ttu-id="cfbcb-195">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="cfbcb-195">RELATED LINKS</span></span>

[<span data-ttu-id="cfbcb-196">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="cfbcb-196">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="cfbcb-197">Get-Module</span><span class="sxs-lookup"><span data-stu-id="cfbcb-197">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="cfbcb-198">Import-Module</span><span class="sxs-lookup"><span data-stu-id="cfbcb-198">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="cfbcb-199">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="cfbcb-199">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="cfbcb-200">about_Modules</span><span class="sxs-lookup"><span data-stu-id="cfbcb-200">about_Modules</span></span>](About/about_Modules.md)
