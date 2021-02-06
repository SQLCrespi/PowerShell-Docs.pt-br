---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Variable
ms.openlocfilehash: c77eb9c64022d028c3c4b2de6bf4551886b940e1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596169"
---
# <span data-ttu-id="495d5-102">New-Variable</span><span class="sxs-lookup"><span data-stu-id="495d5-102">New-Variable</span></span>

## <span data-ttu-id="495d5-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="495d5-103">SYNOPSIS</span></span>
<span data-ttu-id="495d5-104">Cria uma nova variável.</span><span class="sxs-lookup"><span data-stu-id="495d5-104">Creates a new variable.</span></span>

## <span data-ttu-id="495d5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="495d5-105">SYNTAX</span></span>

```
New-Variable [-Name] <String> [[-Value] <Object>] [-Description <String>] [-Option <ScopedItemOptions>]
 [-Visibility <SessionStateEntryVisibility>] [-Force] [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="495d5-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="495d5-106">DESCRIPTION</span></span>
<span data-ttu-id="495d5-107">O cmdlet **New-Variable** cria uma nova variável no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="495d5-107">The **New-Variable** cmdlet creates a new variable in PowerShell.</span></span>
<span data-ttu-id="495d5-108">Você pode atribuir um valor à variável ao criá-la ou atribuir ou alterar o valor depois que ela é criada.</span><span class="sxs-lookup"><span data-stu-id="495d5-108">You can assign a value to the variable while creating it or assign or change the value after it is created.</span></span>

<span data-ttu-id="495d5-109">Você pode usar os parâmetros de **New-Variable** para definir as propriedades da variável, definir o escopo de uma variável e determinar se as variáveis são públicas ou privadas.</span><span class="sxs-lookup"><span data-stu-id="495d5-109">You can use the parameters of **New-Variable** to set the properties of the variable, set the scope of a variable, and determine whether variables are public or private.</span></span>

<span data-ttu-id="495d5-110">Normalmente, você cria uma nova variável digitando o nome da variável e seu valor, como `$Var = 3` , mas você pode usar o cmdlet **New-Variable** para usar seus parâmetros.</span><span class="sxs-lookup"><span data-stu-id="495d5-110">Typically, you create a new variable by typing the variable name and its value, such as `$Var = 3`, but you can use the **New-Variable** cmdlet to use its parameters.</span></span>

## <span data-ttu-id="495d5-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="495d5-111">EXAMPLES</span></span>

### <span data-ttu-id="495d5-112">Exemplo 1: criar uma variável</span><span class="sxs-lookup"><span data-stu-id="495d5-112">Example 1: Create a variable</span></span>

```
PS C:\> New-Variable days
```

<span data-ttu-id="495d5-113">Este comando cria uma nova variável chamada Days.</span><span class="sxs-lookup"><span data-stu-id="495d5-113">This command creates a new variable named days.</span></span>
<span data-ttu-id="495d5-114">Não é necessário digitar o parâmetro *Name* .</span><span class="sxs-lookup"><span data-stu-id="495d5-114">You are not required to type the *Name* parameter.</span></span>

### <span data-ttu-id="495d5-115">Exemplo 2: criar uma variável e atribuir a ela um valor</span><span class="sxs-lookup"><span data-stu-id="495d5-115">Example 2: Create a variable and assign it a value</span></span>

```
PS C:\> New-Variable -Name "zipcode" -Value 98033
```

<span data-ttu-id="495d5-116">Esse comando cria uma variável chamada ZipCode e atribui a ela o valor 98033.</span><span class="sxs-lookup"><span data-stu-id="495d5-116">This command creates a variable named zipcode and assigns it the value 98033.</span></span>

### <span data-ttu-id="495d5-117">Exemplo 3: criar uma variável com a opção ReadOnly</span><span class="sxs-lookup"><span data-stu-id="495d5-117">Example 3: Create a variable with the ReadOnly option</span></span>

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

<span data-ttu-id="495d5-118">Este exemplo mostra como usar a opção ReadOnly de **New-Variable** para proteger uma variável de ser substituída.</span><span class="sxs-lookup"><span data-stu-id="495d5-118">This example shows how to use the ReadOnly option of **New-Variable** to protect a variable from being overwritten.</span></span>

<span data-ttu-id="495d5-119">O primeiro comando cria uma nova variável chamada Max e define seu valor como 256.</span><span class="sxs-lookup"><span data-stu-id="495d5-119">The first command creates a new variable named Max and sets its value to 256.</span></span>
<span data-ttu-id="495d5-120">Ele usa o parâmetro *Option* com um valor de ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="495d5-120">It uses the *Option* parameter with a value of ReadOnly.</span></span>

<span data-ttu-id="495d5-121">O segundo comando tenta criar uma segunda variável com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="495d5-121">The second command tries to create a second variable with the same name.</span></span>
<span data-ttu-id="495d5-122">Esse comando retorna um erro, porque a opção somente leitura é definida na variável.</span><span class="sxs-lookup"><span data-stu-id="495d5-122">This command returns an error, because the read-only option is set on the variable.</span></span>

<span data-ttu-id="495d5-123">O terceiro comando usa o parâmetro *Force* para substituir a proteção somente leitura na variável.</span><span class="sxs-lookup"><span data-stu-id="495d5-123">The third command uses the *Force* parameter to override the read-only protection on the variable.</span></span>
<span data-ttu-id="495d5-124">Nesse caso, o comando para criar uma nova variável com o mesmo nome é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="495d5-124">In this case, the command to create a new variable with the same name succeeds.</span></span>

### <span data-ttu-id="495d5-125">Exemplo 4: criar uma variável privada</span><span class="sxs-lookup"><span data-stu-id="495d5-125">Example 4: Create a private variable</span></span>

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

<span data-ttu-id="495d5-126">Esse comando demonstra o comportamento de uma variável privada em um módulo.</span><span class="sxs-lookup"><span data-stu-id="495d5-126">This command demonstrates the behavior of a private variable in a module.</span></span>
<span data-ttu-id="495d5-127">O módulo contém o cmdlet Get-Counter, que tem uma variável particular chamada Counter.</span><span class="sxs-lookup"><span data-stu-id="495d5-127">The module contains the Get-Counter cmdlet, which has a private variable named Counter.</span></span>
<span data-ttu-id="495d5-128">O comando usa o parâmetro *Visibility* com um valor de Private para criar a variável.</span><span class="sxs-lookup"><span data-stu-id="495d5-128">The command uses the *Visibility* parameter with a value of Private to create the variable.</span></span>

<span data-ttu-id="495d5-129">A amostra de saída mostra o comportamento de uma variável particular.</span><span class="sxs-lookup"><span data-stu-id="495d5-129">The sample output shows the behavior of a private variable.</span></span>
<span data-ttu-id="495d5-130">O usuário que carregou o módulo não pode exibir ou alterar o valor da variável Counter, mas a variável Counter pode ser lida e alterada pelos comandos no módulo.</span><span class="sxs-lookup"><span data-stu-id="495d5-130">The user who has loaded the module cannot view or change the value of the Counter variable, but the Counter variable can be read and changed by the commands in the module.</span></span>

### <span data-ttu-id="495d5-131">Exemplo 5: criar uma variável com um espaço</span><span class="sxs-lookup"><span data-stu-id="495d5-131">Example 5: Create a variable with a space</span></span>

```
PS C:\> New-Variable -Name 'with space' -Value 'abc123xyz'

PS C:\> Get-Variable -Name 'with space'

Name                           Value
----                           -----
with space                     abc123xyz

PS C:\> ${with space}
abc123xyz
```

<span data-ttu-id="495d5-132">Esse comando demonstra que as variáveis com espaços podem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="495d5-132">This command demonstrates that variables with spaces can be created.</span></span>
<span data-ttu-id="495d5-133">As variáveis podem ser acessadas usando o cmdlet **Get-Variable** ou diretamente delimitando uma variável com chaves.</span><span class="sxs-lookup"><span data-stu-id="495d5-133">The variables can be accessed using the **Get-Variable** cmdlet or directly by delimiting a variable with braces.</span></span>

## <span data-ttu-id="495d5-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="495d5-134">PARAMETERS</span></span>

### <span data-ttu-id="495d5-135">-Description</span><span class="sxs-lookup"><span data-stu-id="495d5-135">-Description</span></span>
<span data-ttu-id="495d5-136">Especifica uma descrição da variável.</span><span class="sxs-lookup"><span data-stu-id="495d5-136">Specifies a description of the variable.</span></span>

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

### <span data-ttu-id="495d5-137">-Force</span><span class="sxs-lookup"><span data-stu-id="495d5-137">-Force</span></span>
<span data-ttu-id="495d5-138">Indica que o cmdlet cria uma variável com o mesmo nome de uma variável somente leitura existente.</span><span class="sxs-lookup"><span data-stu-id="495d5-138">Indicates that the cmdlet creates a variable with the same name as an existing read-only variable.</span></span>

<span data-ttu-id="495d5-139">Por padrão, você pode substituir uma variável, a menos que ela tenha um valor de opção de ReadOnly ou Constant.</span><span class="sxs-lookup"><span data-stu-id="495d5-139">By default, you can overwrite a variable unless the variable has an option value of ReadOnly or Constant.</span></span>
<span data-ttu-id="495d5-140">Para obter mais informações, consulte o parâmetro *Option* .</span><span class="sxs-lookup"><span data-stu-id="495d5-140">For more information, see the *Option* parameter.</span></span>

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

### <span data-ttu-id="495d5-141">-Name</span><span class="sxs-lookup"><span data-stu-id="495d5-141">-Name</span></span>
<span data-ttu-id="495d5-142">Especifica um nome para a nova variável.</span><span class="sxs-lookup"><span data-stu-id="495d5-142">Specifies a name for the new variable.</span></span>

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

### <span data-ttu-id="495d5-143">-Opção</span><span class="sxs-lookup"><span data-stu-id="495d5-143">-Option</span></span>
<span data-ttu-id="495d5-144">Especifica o valor da propriedade **Options** da variável. Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="495d5-144">Specifies the value of the **Options** property of the variable.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="495d5-145">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="495d5-145">None.</span></span>
<span data-ttu-id="495d5-146">Não define nenhuma opção.</span><span class="sxs-lookup"><span data-stu-id="495d5-146">Sets no options.</span></span>
<span data-ttu-id="495d5-147">(Nenhum é o padrão.)</span><span class="sxs-lookup"><span data-stu-id="495d5-147">(None is the default.)</span></span>
- <span data-ttu-id="495d5-148">Leitura.</span><span class="sxs-lookup"><span data-stu-id="495d5-148">ReadOnly.</span></span>
<span data-ttu-id="495d5-149">Pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="495d5-149">Can be deleted.</span></span>
<span data-ttu-id="495d5-150">Não pode ser alterado, exceto pelo uso do parâmetro *Force* .</span><span class="sxs-lookup"><span data-stu-id="495d5-150">Cannot be changed, except by using the *Force* parameter.</span></span>
- <span data-ttu-id="495d5-151">Privado.</span><span class="sxs-lookup"><span data-stu-id="495d5-151">Private.</span></span>
<span data-ttu-id="495d5-152">A variável está disponível somente no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="495d5-152">The variable is available only in the current scope.</span></span>
- <span data-ttu-id="495d5-153">AllScope.</span><span class="sxs-lookup"><span data-stu-id="495d5-153">AllScope.</span></span>
<span data-ttu-id="495d5-154">A variável é copiada para quaisquer novos escopos criados.</span><span class="sxs-lookup"><span data-stu-id="495d5-154">The variable is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="495d5-155">Constante.</span><span class="sxs-lookup"><span data-stu-id="495d5-155">Constant.</span></span>
<span data-ttu-id="495d5-156">Não pode ser excluído ou alterado.</span><span class="sxs-lookup"><span data-stu-id="495d5-156">Cannot be deleted or changed.</span></span>
<span data-ttu-id="495d5-157">A constante é válida somente quando você está criando uma variável.</span><span class="sxs-lookup"><span data-stu-id="495d5-157">Constant is valid only when you are creating a variable.</span></span>
<span data-ttu-id="495d5-158">Você não pode alterar as opções de uma variável existente para constante.</span><span class="sxs-lookup"><span data-stu-id="495d5-158">You cannot change the options of an existing variable to Constant.</span></span>

<span data-ttu-id="495d5-159">Para ver a propriedade **Options** de todas as variáveis na sessão, digite `Get-Variable | Format-Table -Property name, options -autosize` .</span><span class="sxs-lookup"><span data-stu-id="495d5-159">To see the **Options** property of all variables in the session, type `Get-Variable | Format-Table -Property name, options -autosize`.</span></span>

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

### <span data-ttu-id="495d5-160">-PassThru</span><span class="sxs-lookup"><span data-stu-id="495d5-160">-PassThru</span></span>
<span data-ttu-id="495d5-161">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="495d5-161">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="495d5-162">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="495d5-162">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="495d5-163">-Escopo</span><span class="sxs-lookup"><span data-stu-id="495d5-163">-Scope</span></span>
<span data-ttu-id="495d5-164">Especifica o escopo da nova variável.</span><span class="sxs-lookup"><span data-stu-id="495d5-164">Specifies the scope of the new variable.</span></span>
<span data-ttu-id="495d5-165">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="495d5-165">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="495d5-166">Geral.</span><span class="sxs-lookup"><span data-stu-id="495d5-166">Global.</span></span>
<span data-ttu-id="495d5-167">As variáveis criadas no escopo global são acessíveis em todos os lugares em um processo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="495d5-167">Variables created in the global scope are accessible everywhere in a PowerShell process.</span></span>
- <span data-ttu-id="495d5-168">Local.</span><span class="sxs-lookup"><span data-stu-id="495d5-168">Local.</span></span>
<span data-ttu-id="495d5-169">O escopo local refere-se ao escopo atual, que pode ser qualquer escopo, dependendo do contexto.</span><span class="sxs-lookup"><span data-stu-id="495d5-169">The local scope refers to the current scope, this can be any scope depending on the context.</span></span>
- <span data-ttu-id="495d5-170">Script.</span><span class="sxs-lookup"><span data-stu-id="495d5-170">Script.</span></span>
<span data-ttu-id="495d5-171">As variáveis criadas no escopo do script são acessíveis somente no arquivo de script ou no módulo em que são criadas.</span><span class="sxs-lookup"><span data-stu-id="495d5-171">Variables created in the script scope are accessible only within the script file or module they are created in.</span></span>
- <span data-ttu-id="495d5-172">Privado.</span><span class="sxs-lookup"><span data-stu-id="495d5-172">Private.</span></span>
<span data-ttu-id="495d5-173">As variáveis criadas no escopo privado não podem ser acessadas fora do escopo em que existem.</span><span class="sxs-lookup"><span data-stu-id="495d5-173">Variables created in the private scope cannot be accessed outside the scope they exist in.</span></span>
<span data-ttu-id="495d5-174">Você pode usar o escopo privado para criar uma versão privada de um item com o mesmo nome em outro escopo.</span><span class="sxs-lookup"><span data-stu-id="495d5-174">You can use private scope to create a private version of an item with the same name in another scope.</span></span>
- <span data-ttu-id="495d5-175">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual, 1 é seu pai, 2 o pai do escopo pai e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="495d5-175">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope, 1 is its parent, 2 the parent of the parent scope, and so on).</span></span>
<span data-ttu-id="495d5-176">Números negativos não podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="495d5-176">Negative numbers cannot be used.</span></span>

<span data-ttu-id="495d5-177">Local é o escopo padrão quando o parâmetro de escopo não é especificado.</span><span class="sxs-lookup"><span data-stu-id="495d5-177">Local is the default scope when the scope parameter is not specified.</span></span>

<span data-ttu-id="495d5-178">Para obter mais informações, consulte about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="495d5-178">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="495d5-179">-Value</span><span class="sxs-lookup"><span data-stu-id="495d5-179">-Value</span></span>
<span data-ttu-id="495d5-180">Especifica o valor inicial da variável.</span><span class="sxs-lookup"><span data-stu-id="495d5-180">Specifies the initial value of the variable.</span></span>

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

### <span data-ttu-id="495d5-181">-Visibilidade</span><span class="sxs-lookup"><span data-stu-id="495d5-181">-Visibility</span></span>
<span data-ttu-id="495d5-182">Determina se a variável é visível fora da sessão na qual ela foi criada.</span><span class="sxs-lookup"><span data-stu-id="495d5-182">Determines whether the variable is visible outside of the session in which it was created.</span></span>
<span data-ttu-id="495d5-183">Esse parâmetro é voltado para uso em scripts e comandos que serão entregues a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="495d5-183">This parameter is designed for  use in scripts and commands that will be delivered to other users.</span></span>
<span data-ttu-id="495d5-184">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="495d5-184">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="495d5-185">Público.</span><span class="sxs-lookup"><span data-stu-id="495d5-185">Public.</span></span>
<span data-ttu-id="495d5-186">A variável está visível.</span><span class="sxs-lookup"><span data-stu-id="495d5-186">The variable is visible.</span></span>
<span data-ttu-id="495d5-187">(Público é o padrão.)</span><span class="sxs-lookup"><span data-stu-id="495d5-187">(Public is the default.)</span></span>
- <span data-ttu-id="495d5-188">Privado.</span><span class="sxs-lookup"><span data-stu-id="495d5-188">Private.</span></span>
<span data-ttu-id="495d5-189">A variável não é visível.</span><span class="sxs-lookup"><span data-stu-id="495d5-189">The variable is not visible.</span></span>

<span data-ttu-id="495d5-190">Quando uma variável é privada, ele não aparece nas listas de variáveis como aquelas retornadas por Get-Variable ou em exibições da unidade Variable:.</span><span class="sxs-lookup"><span data-stu-id="495d5-190">When a variable is private, it does not appear in lists of variables, such as those returned by Get-Variable, or in displays of the Variable: drive.</span></span>
<span data-ttu-id="495d5-191">Comandos para ler ou alterar o valor de uma variável privada retornam um erro.</span><span class="sxs-lookup"><span data-stu-id="495d5-191">Commands to read or change the value of a private variable return an error.</span></span>
<span data-ttu-id="495d5-192">No entanto, o usuário pode executar comandos que usam uma variável privada se os comandos tiverem sido escritos na sessão em que a variável foi definida.</span><span class="sxs-lookup"><span data-stu-id="495d5-192">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

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

### <span data-ttu-id="495d5-193">-Confirm</span><span class="sxs-lookup"><span data-stu-id="495d5-193">-Confirm</span></span>
<span data-ttu-id="495d5-194">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="495d5-194">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="495d5-195">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="495d5-195">-WhatIf</span></span>
<span data-ttu-id="495d5-196">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="495d5-196">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="495d5-197">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="495d5-197">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="495d5-198">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="495d5-198">CommonParameters</span></span>
<span data-ttu-id="495d5-199">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="495d5-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="495d5-200">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="495d5-200">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="495d5-201">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="495d5-201">INPUTS</span></span>

### <span data-ttu-id="495d5-202">System.Object</span><span class="sxs-lookup"><span data-stu-id="495d5-202">System.Object</span></span>
<span data-ttu-id="495d5-203">É possível canalizar um valor para **nova variável**.</span><span class="sxs-lookup"><span data-stu-id="495d5-203">You can pipe a value to **New-Variable**.</span></span>

## <span data-ttu-id="495d5-204">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="495d5-204">OUTPUTS</span></span>

### <span data-ttu-id="495d5-205">Nenhum ou System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="495d5-205">None or System.Management.Automation.PSVariable</span></span>
<span data-ttu-id="495d5-206">Quando você usa o parâmetro *PassThru* , **New-Variable** gera um objeto **System. Management. Automation. PSVariable** que representa a nova variável.</span><span class="sxs-lookup"><span data-stu-id="495d5-206">When you use the *PassThru* parameter, **New-Variable** generates a **System.Management.Automation.PSVariable** object representing the new variable.</span></span>
<span data-ttu-id="495d5-207">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="495d5-207">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="495d5-208">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="495d5-208">NOTES</span></span>

## <span data-ttu-id="495d5-209">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="495d5-209">RELATED LINKS</span></span>

[<span data-ttu-id="495d5-210">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="495d5-210">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="495d5-211">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="495d5-211">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="495d5-212">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="495d5-212">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="495d5-213">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="495d5-213">Set-Variable</span></span>](Set-Variable.md)

