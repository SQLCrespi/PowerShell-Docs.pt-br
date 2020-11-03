---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-variable?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Variable
ms.openlocfilehash: faf8bc399185da402bebb678b02927e0e5628662
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194333"
---
# <span data-ttu-id="5c08e-103">New-Variable</span><span class="sxs-lookup"><span data-stu-id="5c08e-103">New-Variable</span></span>

## <span data-ttu-id="5c08e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5c08e-104">SYNOPSIS</span></span>
<span data-ttu-id="5c08e-105">Cria uma nova variável.</span><span class="sxs-lookup"><span data-stu-id="5c08e-105">Creates a new variable.</span></span>

## <span data-ttu-id="5c08e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5c08e-106">SYNTAX</span></span>

```
New-Variable [-Name] <String> [[-Value] <Object>] [-Description <String>] [-Option <ScopedItemOptions>]
 [-Visibility <SessionStateEntryVisibility>] [-Force] [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="5c08e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c08e-107">DESCRIPTION</span></span>
<span data-ttu-id="5c08e-108">O cmdlet **New-Variable** cria uma nova variável no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c08e-108">The **New-Variable** cmdlet creates a new variable in PowerShell.</span></span>
<span data-ttu-id="5c08e-109">Você pode atribuir um valor à variável ao criá-la ou atribuir ou alterar o valor depois que ela é criada.</span><span class="sxs-lookup"><span data-stu-id="5c08e-109">You can assign a value to the variable while creating it or assign or change the value after it is created.</span></span>

<span data-ttu-id="5c08e-110">Você pode usar os parâmetros de **New-Variable** para definir as propriedades da variável, definir o escopo de uma variável e determinar se as variáveis são públicas ou privadas.</span><span class="sxs-lookup"><span data-stu-id="5c08e-110">You can use the parameters of **New-Variable** to set the properties of the variable, set the scope of a variable, and determine whether variables are public or private.</span></span>

<span data-ttu-id="5c08e-111">Normalmente, você cria uma nova variável digitando o nome da variável e seu valor, como `$Var = 3` , mas você pode usar o cmdlet **New-Variable** para usar seus parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5c08e-111">Typically, you create a new variable by typing the variable name and its value, such as `$Var = 3`, but you can use the **New-Variable** cmdlet to use its parameters.</span></span>

## <span data-ttu-id="5c08e-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5c08e-112">EXAMPLES</span></span>

### <span data-ttu-id="5c08e-113">Exemplo 1: criar uma variável</span><span class="sxs-lookup"><span data-stu-id="5c08e-113">Example 1: Create a variable</span></span>

```
PS C:\> New-Variable days
```

<span data-ttu-id="5c08e-114">Este comando cria uma nova variável chamada Days.</span><span class="sxs-lookup"><span data-stu-id="5c08e-114">This command creates a new variable named days.</span></span>
<span data-ttu-id="5c08e-115">Não é necessário digitar o parâmetro *Name* .</span><span class="sxs-lookup"><span data-stu-id="5c08e-115">You are not required to type the *Name* parameter.</span></span>

### <span data-ttu-id="5c08e-116">Exemplo 2: criar uma variável e atribuir a ela um valor</span><span class="sxs-lookup"><span data-stu-id="5c08e-116">Example 2: Create a variable and assign it a value</span></span>

```
PS C:\> New-Variable -Name "zipcode" -Value 98033
```

<span data-ttu-id="5c08e-117">Esse comando cria uma variável chamada ZipCode e atribui a ela o valor 98033.</span><span class="sxs-lookup"><span data-stu-id="5c08e-117">This command creates a variable named zipcode and assigns it the value 98033.</span></span>

### <span data-ttu-id="5c08e-118">Exemplo 3: criar uma variável com a opção ReadOnly</span><span class="sxs-lookup"><span data-stu-id="5c08e-118">Example 3: Create a variable with the ReadOnly option</span></span>

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

<span data-ttu-id="5c08e-119">Este exemplo mostra como usar a opção ReadOnly de **New-Variable** para proteger uma variável de ser substituída.</span><span class="sxs-lookup"><span data-stu-id="5c08e-119">This example shows how to use the ReadOnly option of **New-Variable** to protect a variable from being overwritten.</span></span>

<span data-ttu-id="5c08e-120">O primeiro comando cria uma nova variável chamada Max e define seu valor como 256.</span><span class="sxs-lookup"><span data-stu-id="5c08e-120">The first command creates a new variable named Max and sets its value to 256.</span></span>
<span data-ttu-id="5c08e-121">Ele usa o parâmetro *Option* com um valor de ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="5c08e-121">It uses the *Option* parameter with a value of ReadOnly.</span></span>

<span data-ttu-id="5c08e-122">O segundo comando tenta criar uma segunda variável com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="5c08e-122">The second command tries to create a second variable with the same name.</span></span>
<span data-ttu-id="5c08e-123">Esse comando retorna um erro, porque a opção somente leitura é definida na variável.</span><span class="sxs-lookup"><span data-stu-id="5c08e-123">This command returns an error, because the read-only option is set on the variable.</span></span>

<span data-ttu-id="5c08e-124">O terceiro comando usa o parâmetro *Force* para substituir a proteção somente leitura na variável.</span><span class="sxs-lookup"><span data-stu-id="5c08e-124">The third command uses the *Force* parameter to override the read-only protection on the variable.</span></span>
<span data-ttu-id="5c08e-125">Nesse caso, o comando para criar uma nova variável com o mesmo nome é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="5c08e-125">In this case, the command to create a new variable with the same name succeeds.</span></span>

### <span data-ttu-id="5c08e-126">Exemplo 4: criar uma variável privada</span><span class="sxs-lookup"><span data-stu-id="5c08e-126">Example 4: Create a private variable</span></span>

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

<span data-ttu-id="5c08e-127">Esse comando demonstra o comportamento de uma variável privada em um módulo.</span><span class="sxs-lookup"><span data-stu-id="5c08e-127">This command demonstrates the behavior of a private variable in a module.</span></span>
<span data-ttu-id="5c08e-128">O módulo contém o cmdlet Get-Counter, que tem uma variável particular chamada Counter.</span><span class="sxs-lookup"><span data-stu-id="5c08e-128">The module contains the Get-Counter cmdlet, which has a private variable named Counter.</span></span>
<span data-ttu-id="5c08e-129">O comando usa o parâmetro *Visibility* com um valor de Private para criar a variável.</span><span class="sxs-lookup"><span data-stu-id="5c08e-129">The command uses the *Visibility* parameter with a value of Private to create the variable.</span></span>

<span data-ttu-id="5c08e-130">A amostra de saída mostra o comportamento de uma variável particular.</span><span class="sxs-lookup"><span data-stu-id="5c08e-130">The sample output shows the behavior of a private variable.</span></span>
<span data-ttu-id="5c08e-131">O usuário que carregou o módulo não pode exibir ou alterar o valor da variável Counter, mas a variável Counter pode ser lida e alterada pelos comandos no módulo.</span><span class="sxs-lookup"><span data-stu-id="5c08e-131">The user who has loaded the module cannot view or change the value of the Counter variable, but the Counter variable can be read and changed by the commands in the module.</span></span>

### <span data-ttu-id="5c08e-132">Exemplo 5: criar uma variável com um espaço</span><span class="sxs-lookup"><span data-stu-id="5c08e-132">Example 5: Create a variable with a space</span></span>

```
PS C:\> New-Variable -Name 'with space' -Value 'abc123xyz'

PS C:\> Get-Variable -Name 'with space'

Name                           Value
----                           -----
with space                     abc123xyz

PS C:\> ${with space}
abc123xyz
```

<span data-ttu-id="5c08e-133">Esse comando demonstra que as variáveis com espaços podem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="5c08e-133">This command demonstrates that variables with spaces can be created.</span></span>
<span data-ttu-id="5c08e-134">As variáveis podem ser acessadas usando o cmdlet **Get-Variable** ou diretamente delimitando uma variável com chaves.</span><span class="sxs-lookup"><span data-stu-id="5c08e-134">The variables can be accessed using the **Get-Variable** cmdlet or directly by delimiting a variable with braces.</span></span>

## <span data-ttu-id="5c08e-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5c08e-135">PARAMETERS</span></span>

### <span data-ttu-id="5c08e-136">-Description</span><span class="sxs-lookup"><span data-stu-id="5c08e-136">-Description</span></span>
<span data-ttu-id="5c08e-137">Especifica uma descrição da variável.</span><span class="sxs-lookup"><span data-stu-id="5c08e-137">Specifies a description of the variable.</span></span>

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

### <span data-ttu-id="5c08e-138">-Force</span><span class="sxs-lookup"><span data-stu-id="5c08e-138">-Force</span></span>
<span data-ttu-id="5c08e-139">Indica que o cmdlet cria uma variável com o mesmo nome de uma variável somente leitura existente.</span><span class="sxs-lookup"><span data-stu-id="5c08e-139">Indicates that the cmdlet creates a variable with the same name as an existing read-only variable.</span></span>

<span data-ttu-id="5c08e-140">Por padrão, você pode substituir uma variável, a menos que ela tenha um valor de opção de ReadOnly ou Constant.</span><span class="sxs-lookup"><span data-stu-id="5c08e-140">By default, you can overwrite a variable unless the variable has an option value of ReadOnly or Constant.</span></span>
<span data-ttu-id="5c08e-141">Para obter mais informações, consulte o parâmetro *Option* .</span><span class="sxs-lookup"><span data-stu-id="5c08e-141">For more information, see the *Option* parameter.</span></span>

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

### <span data-ttu-id="5c08e-142">-Name</span><span class="sxs-lookup"><span data-stu-id="5c08e-142">-Name</span></span>
<span data-ttu-id="5c08e-143">Especifica um nome para a nova variável.</span><span class="sxs-lookup"><span data-stu-id="5c08e-143">Specifies a name for the new variable.</span></span>

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

### <span data-ttu-id="5c08e-144">-Opção</span><span class="sxs-lookup"><span data-stu-id="5c08e-144">-Option</span></span>
<span data-ttu-id="5c08e-145">Especifica o valor da propriedade **Options** da variável. Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="5c08e-145">Specifies the value of the **Options** property of the variable.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5c08e-146">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="5c08e-146">None.</span></span>
<span data-ttu-id="5c08e-147">Não define nenhuma opção.</span><span class="sxs-lookup"><span data-stu-id="5c08e-147">Sets no options.</span></span>
<span data-ttu-id="5c08e-148">(Nenhum é o padrão.)</span><span class="sxs-lookup"><span data-stu-id="5c08e-148">(None is the default.)</span></span>
- <span data-ttu-id="5c08e-149">Leitura.</span><span class="sxs-lookup"><span data-stu-id="5c08e-149">ReadOnly.</span></span>
<span data-ttu-id="5c08e-150">Pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="5c08e-150">Can be deleted.</span></span>
<span data-ttu-id="5c08e-151">Não pode ser alterado, exceto pelo uso do parâmetro *Force* .</span><span class="sxs-lookup"><span data-stu-id="5c08e-151">Cannot be changed, except by using the *Force* parameter.</span></span>
- <span data-ttu-id="5c08e-152">Privado.</span><span class="sxs-lookup"><span data-stu-id="5c08e-152">Private.</span></span>
<span data-ttu-id="5c08e-153">A variável está disponível somente no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="5c08e-153">The variable is available only in the current scope.</span></span>
- <span data-ttu-id="5c08e-154">AllScope.</span><span class="sxs-lookup"><span data-stu-id="5c08e-154">AllScope.</span></span>
<span data-ttu-id="5c08e-155">A variável é copiada para quaisquer novos escopos criados.</span><span class="sxs-lookup"><span data-stu-id="5c08e-155">The variable is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="5c08e-156">Constante.</span><span class="sxs-lookup"><span data-stu-id="5c08e-156">Constant.</span></span>
<span data-ttu-id="5c08e-157">Não pode ser excluído ou alterado.</span><span class="sxs-lookup"><span data-stu-id="5c08e-157">Cannot be deleted or changed.</span></span>
<span data-ttu-id="5c08e-158">A constante é válida somente quando você está criando uma variável.</span><span class="sxs-lookup"><span data-stu-id="5c08e-158">Constant is valid only when you are creating a variable.</span></span>
<span data-ttu-id="5c08e-159">Você não pode alterar as opções de uma variável existente para constante.</span><span class="sxs-lookup"><span data-stu-id="5c08e-159">You cannot change the options of an existing variable to Constant.</span></span>

<span data-ttu-id="5c08e-160">Para ver a propriedade **Options** de todas as variáveis na sessão, digite `Get-Variable | Format-Table -Property name, options -autosize` .</span><span class="sxs-lookup"><span data-stu-id="5c08e-160">To see the **Options** property of all variables in the session, type `Get-Variable | Format-Table -Property name, options -autosize`.</span></span>

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

### <span data-ttu-id="5c08e-161">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5c08e-161">-PassThru</span></span>
<span data-ttu-id="5c08e-162">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="5c08e-162">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="5c08e-163">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="5c08e-163">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="5c08e-164">-Escopo</span><span class="sxs-lookup"><span data-stu-id="5c08e-164">-Scope</span></span>
<span data-ttu-id="5c08e-165">Especifica o escopo da nova variável.</span><span class="sxs-lookup"><span data-stu-id="5c08e-165">Specifies the scope of the new variable.</span></span>
<span data-ttu-id="5c08e-166">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="5c08e-166">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5c08e-167">Geral.</span><span class="sxs-lookup"><span data-stu-id="5c08e-167">Global.</span></span>
<span data-ttu-id="5c08e-168">As variáveis criadas no escopo global são acessíveis em todos os lugares em um processo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c08e-168">Variables created in the global scope are accessible everywhere in a PowerShell process.</span></span>
- <span data-ttu-id="5c08e-169">Local.</span><span class="sxs-lookup"><span data-stu-id="5c08e-169">Local.</span></span>
<span data-ttu-id="5c08e-170">O escopo local refere-se ao escopo atual, que pode ser qualquer escopo, dependendo do contexto.</span><span class="sxs-lookup"><span data-stu-id="5c08e-170">The local scope refers to the current scope, this can be any scope depending on the context.</span></span>
- <span data-ttu-id="5c08e-171">Script.</span><span class="sxs-lookup"><span data-stu-id="5c08e-171">Script.</span></span>
<span data-ttu-id="5c08e-172">As variáveis criadas no escopo do script são acessíveis somente no arquivo de script ou no módulo em que são criadas.</span><span class="sxs-lookup"><span data-stu-id="5c08e-172">Variables created in the script scope are accessible only within the script file or module they are created in.</span></span>
- <span data-ttu-id="5c08e-173">Privado.</span><span class="sxs-lookup"><span data-stu-id="5c08e-173">Private.</span></span>
<span data-ttu-id="5c08e-174">As variáveis criadas no escopo privado não podem ser acessadas fora do escopo em que existem.</span><span class="sxs-lookup"><span data-stu-id="5c08e-174">Variables created in the private scope cannot be accessed outside the scope they exist in.</span></span>
<span data-ttu-id="5c08e-175">Você pode usar o escopo privado para criar uma versão privada de um item com o mesmo nome em outro escopo.</span><span class="sxs-lookup"><span data-stu-id="5c08e-175">You can use private scope to create a private version of an item with the same name in another scope.</span></span>
- <span data-ttu-id="5c08e-176">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual, 1 é seu pai, 2 o pai do escopo pai e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="5c08e-176">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope, 1 is its parent, 2 the parent of the parent scope, and so on).</span></span>
<span data-ttu-id="5c08e-177">Números negativos não podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="5c08e-177">Negative numbers cannot be used.</span></span>

<span data-ttu-id="5c08e-178">Local é o escopo padrão quando o parâmetro de escopo não é especificado.</span><span class="sxs-lookup"><span data-stu-id="5c08e-178">Local is the default scope when the scope parameter is not specified.</span></span>

<span data-ttu-id="5c08e-179">Para obter mais informações, consulte about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="5c08e-179">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="5c08e-180">-Value</span><span class="sxs-lookup"><span data-stu-id="5c08e-180">-Value</span></span>
<span data-ttu-id="5c08e-181">Especifica o valor inicial da variável.</span><span class="sxs-lookup"><span data-stu-id="5c08e-181">Specifies the initial value of the variable.</span></span>

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

### <span data-ttu-id="5c08e-182">-Visibilidade</span><span class="sxs-lookup"><span data-stu-id="5c08e-182">-Visibility</span></span>
<span data-ttu-id="5c08e-183">Determina se a variável é visível fora da sessão na qual ela foi criada.</span><span class="sxs-lookup"><span data-stu-id="5c08e-183">Determines whether the variable is visible outside of the session in which it was created.</span></span>
<span data-ttu-id="5c08e-184">Esse parâmetro é voltado para uso em scripts e comandos que serão entregues a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="5c08e-184">This parameter is designed for  use in scripts and commands that will be delivered to other users.</span></span>
<span data-ttu-id="5c08e-185">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="5c08e-185">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5c08e-186">Público.</span><span class="sxs-lookup"><span data-stu-id="5c08e-186">Public.</span></span>
<span data-ttu-id="5c08e-187">A variável está visível.</span><span class="sxs-lookup"><span data-stu-id="5c08e-187">The variable is visible.</span></span>
<span data-ttu-id="5c08e-188">(Público é o padrão.)</span><span class="sxs-lookup"><span data-stu-id="5c08e-188">(Public is the default.)</span></span>
- <span data-ttu-id="5c08e-189">Privado.</span><span class="sxs-lookup"><span data-stu-id="5c08e-189">Private.</span></span>
<span data-ttu-id="5c08e-190">A variável não é visível.</span><span class="sxs-lookup"><span data-stu-id="5c08e-190">The variable is not visible.</span></span>

<span data-ttu-id="5c08e-191">Quando uma variável é privada, ele não aparece nas listas de variáveis como aquelas retornadas por Get-Variable ou em exibições da unidade Variable:.</span><span class="sxs-lookup"><span data-stu-id="5c08e-191">When a variable is private, it does not appear in lists of variables, such as those returned by Get-Variable, or in displays of the Variable: drive.</span></span>
<span data-ttu-id="5c08e-192">Comandos para ler ou alterar o valor de uma variável privada retornam um erro.</span><span class="sxs-lookup"><span data-stu-id="5c08e-192">Commands to read or change the value of a private variable return an error.</span></span>
<span data-ttu-id="5c08e-193">No entanto, o usuário pode executar comandos que usam uma variável privada se os comandos tiverem sido escritos na sessão em que a variável foi definida.</span><span class="sxs-lookup"><span data-stu-id="5c08e-193">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

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

### <span data-ttu-id="5c08e-194">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5c08e-194">-Confirm</span></span>
<span data-ttu-id="5c08e-195">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5c08e-195">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5c08e-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5c08e-196">-WhatIf</span></span>
<span data-ttu-id="5c08e-197">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="5c08e-197">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5c08e-198">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="5c08e-198">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5c08e-199">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5c08e-199">CommonParameters</span></span>
<span data-ttu-id="5c08e-200">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5c08e-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5c08e-201">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5c08e-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5c08e-202">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5c08e-202">INPUTS</span></span>

### <span data-ttu-id="5c08e-203">System.Object</span><span class="sxs-lookup"><span data-stu-id="5c08e-203">System.Object</span></span>
<span data-ttu-id="5c08e-204">É possível canalizar um valor para **nova variável** .</span><span class="sxs-lookup"><span data-stu-id="5c08e-204">You can pipe a value to **New-Variable** .</span></span>

## <span data-ttu-id="5c08e-205">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5c08e-205">OUTPUTS</span></span>

### <span data-ttu-id="5c08e-206">Nenhum ou System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="5c08e-206">None or System.Management.Automation.PSVariable</span></span>
<span data-ttu-id="5c08e-207">Quando você usa o parâmetro *PassThru* , **New-Variable** gera um objeto **System. Management. Automation. PSVariable** que representa a nova variável.</span><span class="sxs-lookup"><span data-stu-id="5c08e-207">When you use the *PassThru* parameter, **New-Variable** generates a **System.Management.Automation.PSVariable** object representing the new variable.</span></span>
<span data-ttu-id="5c08e-208">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="5c08e-208">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5c08e-209">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5c08e-209">NOTES</span></span>

## <span data-ttu-id="5c08e-210">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5c08e-210">RELATED LINKS</span></span>

[<span data-ttu-id="5c08e-211">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="5c08e-211">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="5c08e-212">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="5c08e-212">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="5c08e-213">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="5c08e-213">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="5c08e-214">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="5c08e-214">Set-Variable</span></span>](Set-Variable.md)
