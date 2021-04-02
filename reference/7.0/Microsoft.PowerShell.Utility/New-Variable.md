---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/30/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-variable?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Variable
ms.openlocfilehash: f23f725a92d5157001a1327cff3dbb3e785fd776
ms.sourcegitcommit: 4d6ed6f7d747a9bbb3fcfcf6c981c5aa8a973a08
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "106072777"
---
# <span data-ttu-id="139b3-103">New-Variable</span><span class="sxs-lookup"><span data-stu-id="139b3-103">New-Variable</span></span>

## <span data-ttu-id="139b3-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="139b3-104">Synopsis</span></span>
<span data-ttu-id="139b3-105">Cria uma nova variável.</span><span class="sxs-lookup"><span data-stu-id="139b3-105">Creates a new variable.</span></span>

## <span data-ttu-id="139b3-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="139b3-106">Syntax</span></span>

```
New-Variable [-Name] <String> [[-Value] <Object>] [-Description <String>] [-Option <ScopedItemOptions>]
 [-Visibility <SessionStateEntryVisibility>] [-Force] [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="139b3-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="139b3-107">Description</span></span>

<span data-ttu-id="139b3-108">O `New-Variable` cmdlet cria uma nova variável no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="139b3-108">The `New-Variable` cmdlet creates a new variable in Windows PowerShell.</span></span> <span data-ttu-id="139b3-109">Você pode atribuir um valor à variável ao criá-la ou atribuir ou alterar o valor depois que ela é criada.</span><span class="sxs-lookup"><span data-stu-id="139b3-109">You can assign a value to the variable while creating it or assign or change the value after it is created.</span></span>

<span data-ttu-id="139b3-110">Você pode usar os parâmetros de `New-Variable` para definir as propriedades da variável, definir o escopo de uma variável e determinar se as variáveis são públicas ou privadas.</span><span class="sxs-lookup"><span data-stu-id="139b3-110">You can use the parameters of `New-Variable` to set the properties of the variable, set the scope of a variable, and determine whether variables are public or private.</span></span>

<span data-ttu-id="139b3-111">Normalmente, você cria uma nova variável digitando o nome da variável e seu valor, como `$Var = 3` , mas você pode usar o `New-Variable` cmdlet para usar seus parâmetros.</span><span class="sxs-lookup"><span data-stu-id="139b3-111">Typically, you create a new variable by typing the variable name and its value, such as `$Var = 3`, but you can use the `New-Variable` cmdlet to use its parameters.</span></span>

## <span data-ttu-id="139b3-112">Exemplos</span><span class="sxs-lookup"><span data-stu-id="139b3-112">Examples</span></span>

### <span data-ttu-id="139b3-113">Exemplo 1: criar uma variável</span><span class="sxs-lookup"><span data-stu-id="139b3-113">Example 1: Create a variable</span></span>

```
New-Variable days
```

<span data-ttu-id="139b3-114">Este comando cria uma nova variável chamada Days.</span><span class="sxs-lookup"><span data-stu-id="139b3-114">This command creates a new variable named days.</span></span> <span data-ttu-id="139b3-115">Não é necessário digitar o parâmetro **Name** .</span><span class="sxs-lookup"><span data-stu-id="139b3-115">You are not required to type the **Name** parameter.</span></span>

### <span data-ttu-id="139b3-116">Exemplo 2: criar uma variável e atribuir a ela um valor</span><span class="sxs-lookup"><span data-stu-id="139b3-116">Example 2: Create a variable and assign it a value</span></span>

```
New-Variable -Name "zipcode" -Value 98033
```

<span data-ttu-id="139b3-117">Esse comando cria uma variável chamada ZipCode e atribui a ela o valor 98033.</span><span class="sxs-lookup"><span data-stu-id="139b3-117">This command creates a variable named zipcode and assigns it the value 98033.</span></span>

### <span data-ttu-id="139b3-118">Exemplo 3: criar uma variável com a opção ReadOnly</span><span class="sxs-lookup"><span data-stu-id="139b3-118">Example 3: Create a variable with the ReadOnly option</span></span>

```
PS C:\> New-Variable -Name Max -Value 256 -Option ReadOnly
PS C:\> New-Variable -Name max -Value 1024

New-Variable : A variable with name 'max' already exists.
At line:1 char:1
+ New-Variable -Name max -Value 1024
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ResourceExists: (max:String) [New-Variable], SessionStateException
    + FullyQualifiedErrorId : VariableAlreadyExists,Microsoft.PowerShell.Commands.NewVariableCommand

PS C:\> New-Variable -Name max -Value 1024 -Force
```

<span data-ttu-id="139b3-119">Este exemplo mostra como usar a `ReadOnly` opção de `New-Variable` para proteger uma variável de ser substituída.</span><span class="sxs-lookup"><span data-stu-id="139b3-119">This example shows how to use the `ReadOnly` option of `New-Variable` to protect a variable from being overwritten.</span></span>

<span data-ttu-id="139b3-120">O primeiro comando cria uma nova variável chamada Max e define seu valor como 256.</span><span class="sxs-lookup"><span data-stu-id="139b3-120">The first command creates a new variable named Max and sets its value to 256.</span></span> <span data-ttu-id="139b3-121">Ele usa o parâmetro **Option** com um valor de `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="139b3-121">It uses the **Option** parameter with a value of `ReadOnly`.</span></span>

<span data-ttu-id="139b3-122">O segundo comando tenta criar uma segunda variável com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="139b3-122">The second command tries to create a second variable with the same name.</span></span> <span data-ttu-id="139b3-123">Esse comando retorna um erro, porque a opção somente leitura é definida na variável.</span><span class="sxs-lookup"><span data-stu-id="139b3-123">This command returns an error, because the read-only option is set on the variable.</span></span>

<span data-ttu-id="139b3-124">O terceiro comando usa o parâmetro **Force** para substituir a proteção somente leitura na variável.</span><span class="sxs-lookup"><span data-stu-id="139b3-124">The third command uses the **Force** parameter to override the read-only protection on the variable.</span></span>
<span data-ttu-id="139b3-125">Nesse caso, o comando para criar uma nova variável com o mesmo nome é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="139b3-125">In this case, the command to create a new variable with the same name succeeds.</span></span>

### <span data-ttu-id="139b3-126">Exemplo 4: atribuir várias opções a uma variável</span><span class="sxs-lookup"><span data-stu-id="139b3-126">Example 4: Assign multiple options to a variable</span></span>

```powershell
New-Variable -Name 'TestVariable' -Value 'Test Value' -Option AllScope,Constant
```

<span data-ttu-id="139b3-127">Este exemplo cria uma variável e atribui as `AllScope` `Constant` Opções e, portanto, a variável estará disponível no escopo atual e quaisquer novos escopos criados e não poderão ser alterados ou excluídos.</span><span class="sxs-lookup"><span data-stu-id="139b3-127">This example creates a variable and assigns the `AllScope` and `Constant` options so the variable will be available in the current scope and any new scopes created and cannot be changed or deleted.</span></span>

### <span data-ttu-id="139b3-128">Exemplo 5: criar uma variável privada</span><span class="sxs-lookup"><span data-stu-id="139b3-128">Example 5: Create a private variable</span></span>

```
PS C:\> New-Variable -Name counter -Visibility Private

#Effect of private variable in a module.

PS C:\> Get-Variable c*

Name                           Value
----                           -----
Culture                        en-US
ConsoleFileName
ConfirmPreference              High
CommandLineParameters          {}

PS C:\> $counter
"Cannot access the variable '$counter' because it is a private variable"
At line:1 char:1
+ $counter
+ ~~~~~~~~
    + CategoryInfo          : PermissionDenied: (counter:String) [], SessionStateException
    + FullyQualifiedErrorId : VariableIsPrivate

PS C:\> Get-Counter
Name         Value
----         -----
Counter1     3.1415
...
```

<span data-ttu-id="139b3-129">Esse comando demonstra o comportamento de uma variável privada em um módulo.</span><span class="sxs-lookup"><span data-stu-id="139b3-129">This command demonstrates the behavior of a private variable in a module.</span></span> <span data-ttu-id="139b3-130">O módulo contém o `Get-Counter` cmdlet, que tem uma variável particular chamada Counter.</span><span class="sxs-lookup"><span data-stu-id="139b3-130">The module contains the `Get-Counter` cmdlet, which has a private variable named Counter.</span></span> <span data-ttu-id="139b3-131">O comando usa o parâmetro **Visibility** com um valor de Private para criar a variável.</span><span class="sxs-lookup"><span data-stu-id="139b3-131">The command uses the **Visibility** parameter with a value of Private to create the variable.</span></span>

<span data-ttu-id="139b3-132">A amostra de saída mostra o comportamento de uma variável particular.</span><span class="sxs-lookup"><span data-stu-id="139b3-132">The sample output shows the behavior of a private variable.</span></span> <span data-ttu-id="139b3-133">O usuário que carregou o módulo não pode exibir ou alterar o valor da variável Counter, mas a variável Counter pode ser lida e alterada pelos comandos no módulo.</span><span class="sxs-lookup"><span data-stu-id="139b3-133">The user who has loaded the module cannot view or change the value of the Counter variable, but the Counter variable can be read and changed by the commands in the module.</span></span>

### <span data-ttu-id="139b3-134">Exemplo 6: criar uma variável com um espaço</span><span class="sxs-lookup"><span data-stu-id="139b3-134">Example 6: Create a variable with a space</span></span>

```
PS C:\> New-Variable -Name 'with space' -Value 'abc123xyz'

PS C:\> Get-Variable -Name 'with space'

Name                           Value
----                           -----
with space                     abc123xyz

PS C:\> ${with space}
abc123xyz
```

<span data-ttu-id="139b3-135">Esse comando demonstra que as variáveis com espaços podem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="139b3-135">This command demonstrates that variables with spaces can be created.</span></span> <span data-ttu-id="139b3-136">As variáveis podem ser acessadas usando o `Get-Variable` cmdlet ou diretamente delimitando uma variável com chaves.</span><span class="sxs-lookup"><span data-stu-id="139b3-136">The variables can be accessed using the `Get-Variable` cmdlet or directly by delimiting a variable with braces.</span></span>

## <span data-ttu-id="139b3-137">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="139b3-137">Parameters</span></span>

### <span data-ttu-id="139b3-138">-Description</span><span class="sxs-lookup"><span data-stu-id="139b3-138">-Description</span></span>

<span data-ttu-id="139b3-139">Especifica uma descrição da variável.</span><span class="sxs-lookup"><span data-stu-id="139b3-139">Specifies a description of the variable.</span></span>

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

### <span data-ttu-id="139b3-140">-Force</span><span class="sxs-lookup"><span data-stu-id="139b3-140">-Force</span></span>

<span data-ttu-id="139b3-141">Indica que o cmdlet cria uma variável com o mesmo nome de uma variável somente leitura existente.</span><span class="sxs-lookup"><span data-stu-id="139b3-141">Indicates that the cmdlet creates a variable with the same name as an existing read-only variable.</span></span>

<span data-ttu-id="139b3-142">Por padrão, você pode substituir uma variável, a menos que a variável tenha um valor de opção de `ReadOnly` ou `Constant` .</span><span class="sxs-lookup"><span data-stu-id="139b3-142">By default, you can overwrite a variable unless the variable has an option value of `ReadOnly` or `Constant`.</span></span> <span data-ttu-id="139b3-143">Para obter mais informações, consulte o parâmetro **Option** .</span><span class="sxs-lookup"><span data-stu-id="139b3-143">For more information, see the **Option** parameter.</span></span>

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

### <span data-ttu-id="139b3-144">-Name</span><span class="sxs-lookup"><span data-stu-id="139b3-144">-Name</span></span>

<span data-ttu-id="139b3-145">Especifica um nome para a nova variável.</span><span class="sxs-lookup"><span data-stu-id="139b3-145">Specifies a name for the new variable.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="139b3-146">-Opção</span><span class="sxs-lookup"><span data-stu-id="139b3-146">-Option</span></span>

<span data-ttu-id="139b3-147">Especifica o valor da propriedade **Options** da variável.</span><span class="sxs-lookup"><span data-stu-id="139b3-147">Specifies the value of the **Options** property of the variable.</span></span> <span data-ttu-id="139b3-148">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="139b3-148">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="139b3-149">`None` -Não define opções.</span><span class="sxs-lookup"><span data-stu-id="139b3-149">`None` - Sets no options.</span></span> <span data-ttu-id="139b3-150">`None` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="139b3-150">`None` is the default.</span></span>
- <span data-ttu-id="139b3-151">`ReadOnly` -Pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="139b3-151">`ReadOnly` - Can be deleted.</span></span> <span data-ttu-id="139b3-152">Não pode ser alterado, exceto pelo uso do parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="139b3-152">Cannot be changed, except by using the **Force** parameter.</span></span>
- <span data-ttu-id="139b3-153">`Private` -A variável está disponível somente no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="139b3-153">`Private` - The variable is available only in the current scope.</span></span>
- <span data-ttu-id="139b3-154">`AllScope` -A variável é copiada para todos os novos escopos criados.</span><span class="sxs-lookup"><span data-stu-id="139b3-154">`AllScope` - The variable is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="139b3-155">`Constant` -Não pode ser excluído ou alterado.</span><span class="sxs-lookup"><span data-stu-id="139b3-155">`Constant` - Cannot be deleted or changed.</span></span> <span data-ttu-id="139b3-156">`Constant` é válido somente quando você está criando uma variável.</span><span class="sxs-lookup"><span data-stu-id="139b3-156">`Constant` is valid only when you are creating a variable.</span></span> <span data-ttu-id="139b3-157">Você não pode alterar as opções de uma variável existente para `Constant` .</span><span class="sxs-lookup"><span data-stu-id="139b3-157">You cannot change the options of an existing variable to `Constant`.</span></span>

<span data-ttu-id="139b3-158">Esses valores são definidos como uma enumeração baseada em sinalizador.</span><span class="sxs-lookup"><span data-stu-id="139b3-158">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="139b3-159">Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="139b3-159">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="139b3-160">Os valores podem ser passados para o parâmetro de **opção** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores.</span><span class="sxs-lookup"><span data-stu-id="139b3-160">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="139b3-161">O cmdlet combinará os valores usando uma operação binary ou.</span><span class="sxs-lookup"><span data-stu-id="139b3-161">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="139b3-162">Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.</span><span class="sxs-lookup"><span data-stu-id="139b3-162">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

<span data-ttu-id="139b3-163">Para ver a propriedade Options de todas as variáveis na sessão, digite `Get-Variable | Format-Table -Property name, options -AutoSize` .</span><span class="sxs-lookup"><span data-stu-id="139b3-163">To see the Options property of all variables in the session, type `Get-Variable | Format-Table -Property name, options -AutoSize`.</span></span>

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="139b3-164">-PassThru</span><span class="sxs-lookup"><span data-stu-id="139b3-164">-PassThru</span></span>

<span data-ttu-id="139b3-165">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="139b3-165">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="139b3-166">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="139b3-166">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="139b3-167">-Escopo</span><span class="sxs-lookup"><span data-stu-id="139b3-167">-Scope</span></span>

<span data-ttu-id="139b3-168">Especifica o escopo da nova variável.</span><span class="sxs-lookup"><span data-stu-id="139b3-168">Specifies the scope of the new variable.</span></span> <span data-ttu-id="139b3-169">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="139b3-169">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="139b3-170">`Global` -As variáveis criadas no escopo global são acessíveis em todos os lugares em um processo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="139b3-170">`Global` - Variables created in the global scope are accessible everywhere in a PowerShell process.</span></span>
- <span data-ttu-id="139b3-171">`Local` -O escopo local refere-se ao escopo atual, que pode ser qualquer escopo, dependendo do contexto.</span><span class="sxs-lookup"><span data-stu-id="139b3-171">`Local` - The local scope refers to the current scope, this can be any scope depending on the context.</span></span>
- <span data-ttu-id="139b3-172">`Script` -As variáveis criadas no escopo do script são acessíveis somente no arquivo de script ou no módulo em que são criadas.</span><span class="sxs-lookup"><span data-stu-id="139b3-172">`Script` - Variables created in the script scope are accessible only within the script file or module they are created in.</span></span>
- <span data-ttu-id="139b3-173">`Private` -As variáveis criadas no escopo privado não podem ser acessadas fora do escopo em que existem.</span><span class="sxs-lookup"><span data-stu-id="139b3-173">`Private` - Variables created in the private scope cannot be accessed outside the scope they exist in.</span></span> <span data-ttu-id="139b3-174">Você pode usar o escopo privado para criar uma versão privada de um item com o mesmo nome em outro escopo.</span><span class="sxs-lookup"><span data-stu-id="139b3-174">You can use private scope to create a private version of an item with the same name in another scope.</span></span>
- <span data-ttu-id="139b3-175">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual, 1 é seu pai, 2 o pai do escopo pai e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="139b3-175">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope, 1 is its parent, 2 the parent of the parent scope, and so on).</span></span> <span data-ttu-id="139b3-176">Números negativos não podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="139b3-176">Negative numbers cannot be used.</span></span>

<span data-ttu-id="139b3-177">`Local` é o escopo padrão quando o parâmetro de escopo não é especificado.</span><span class="sxs-lookup"><span data-stu-id="139b3-177">`Local` is the default scope when the scope parameter is not specified.</span></span>

<span data-ttu-id="139b3-178">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="139b3-178">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="139b3-179">-Value</span><span class="sxs-lookup"><span data-stu-id="139b3-179">-Value</span></span>

<span data-ttu-id="139b3-180">Especifica o valor inicial da variável.</span><span class="sxs-lookup"><span data-stu-id="139b3-180">Specifies the initial value of the variable.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="139b3-181">-Visibilidade</span><span class="sxs-lookup"><span data-stu-id="139b3-181">-Visibility</span></span>

<span data-ttu-id="139b3-182">Determina se a variável é visível fora da sessão na qual ela foi criada.</span><span class="sxs-lookup"><span data-stu-id="139b3-182">Determines whether the variable is visible outside of the session in which it was created.</span></span> <span data-ttu-id="139b3-183">Esse parâmetro é projetado para uso em scripts e comandos que serão entregues a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="139b3-183">This parameter is designed for use in scripts and commands that will be delivered to other users.</span></span> <span data-ttu-id="139b3-184">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="139b3-184">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="139b3-185">`Public` -A variável é visível.</span><span class="sxs-lookup"><span data-stu-id="139b3-185">`Public` - The variable is visible.</span></span> <span data-ttu-id="139b3-186">`Public` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="139b3-186">`Public` is the default.</span></span>
- <span data-ttu-id="139b3-187">`Private` -A variável não é visível.</span><span class="sxs-lookup"><span data-stu-id="139b3-187">`Private` - The variable is not visible.</span></span>

<span data-ttu-id="139b3-188">Quando uma variável é privada, ela não aparece em listas de variáveis, como aquelas retornadas por `Get-Variable` ou em exibições da `Variable:` unidade.</span><span class="sxs-lookup"><span data-stu-id="139b3-188">When a variable is private, it does not appear in lists of variables, such as those returned by `Get-Variable`, or in displays of the `Variable:` drive.</span></span> <span data-ttu-id="139b3-189">Comandos para ler ou alterar o valor de uma variável privada retornam um erro.</span><span class="sxs-lookup"><span data-stu-id="139b3-189">Commands to read or change the value of a private variable return an error.</span></span> <span data-ttu-id="139b3-190">No entanto, o usuário pode executar comandos que usam uma variável privada se os comandos tiverem sido escritos na sessão em que a variável foi definida.</span><span class="sxs-lookup"><span data-stu-id="139b3-190">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

```yaml
Type: System.Management.Automation.SessionStateEntryVisibility
Parameter Sets: (All)
Aliases:
Accepted values: Public, Private

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="139b3-191">-Confirm</span><span class="sxs-lookup"><span data-stu-id="139b3-191">-Confirm</span></span>

<span data-ttu-id="139b3-192">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="139b3-192">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="139b3-193">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="139b3-193">-WhatIf</span></span>

<span data-ttu-id="139b3-194">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="139b3-194">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="139b3-195">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="139b3-195">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="139b3-196">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="139b3-196">CommonParameters</span></span>

<span data-ttu-id="139b3-197">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="139b3-197">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="139b3-198">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="139b3-198">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="139b3-199">Entradas</span><span class="sxs-lookup"><span data-stu-id="139b3-199">Inputs</span></span>

### <span data-ttu-id="139b3-200">System.Object</span><span class="sxs-lookup"><span data-stu-id="139b3-200">System.Object</span></span>

<span data-ttu-id="139b3-201">É possível canalizar um valor para `New-Variable` .</span><span class="sxs-lookup"><span data-stu-id="139b3-201">You can pipe a value to `New-Variable`.</span></span>

## <span data-ttu-id="139b3-202">Saídas</span><span class="sxs-lookup"><span data-stu-id="139b3-202">Outputs</span></span>

### <span data-ttu-id="139b3-203">Nenhum ou System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="139b3-203">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="139b3-204">Quando você usa o parâmetro **PassThru** , o `New-Variable` gera um objeto **System. Management. Automation. PSVariable** que representa a nova variável.</span><span class="sxs-lookup"><span data-stu-id="139b3-204">When you use the **PassThru** parameter, `New-Variable` generates a **System.Management.Automation.PSVariable** object representing the new variable.</span></span> <span data-ttu-id="139b3-205">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="139b3-205">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="139b3-206">Observações</span><span class="sxs-lookup"><span data-stu-id="139b3-206">Notes</span></span>

## <span data-ttu-id="139b3-207">Links Relacionados</span><span class="sxs-lookup"><span data-stu-id="139b3-207">Related Links</span></span>

[<span data-ttu-id="139b3-208">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="139b3-208">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="139b3-209">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="139b3-209">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="139b3-210">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="139b3-210">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="139b3-211">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="139b3-211">Set-Variable</span></span>](Set-Variable.md)
