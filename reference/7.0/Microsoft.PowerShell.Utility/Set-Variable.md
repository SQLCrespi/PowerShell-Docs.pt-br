---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-variable?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Variable
ms.openlocfilehash: 876129fc8df9a78df257bf95220fc6587e68b9a2
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239837"
---
# <span data-ttu-id="fa9f4-103">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="fa9f4-103">Set-Variable</span></span>

## <span data-ttu-id="fa9f4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fa9f4-104">SYNOPSIS</span></span>
<span data-ttu-id="fa9f4-105">Define o valor de uma variável.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-105">Sets the value of a variable.</span></span> <span data-ttu-id="fa9f4-106">Cria a variável se uma com o nome solicitado não existir.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-106">Creates the variable if one with the requested name does not exist.</span></span>

## <span data-ttu-id="fa9f4-107">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fa9f4-107">SYNTAX</span></span>

```
Set-Variable [-Name] <String[]> [[-Value] <Object>] [-Include <String[]>] [-Exclude <String[]>]
 [-Description <String>] [-Option <ScopedItemOptions>] [-Force] [-Visibility <SessionStateEntryVisibility>]
 [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fa9f4-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fa9f4-108">DESCRIPTION</span></span>

<span data-ttu-id="fa9f4-109">O `Set-Variable` cmdlet atribui um valor a uma variável especificada ou altera o valor atual.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-109">The `Set-Variable` cmdlet assigns a value to a specified variable or changes the current value.</span></span> <span data-ttu-id="fa9f4-110">Se a variável não existir, o cmdlet a criará.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-110">If the variable does not exist, the cmdlet creates it.</span></span>

## <span data-ttu-id="fa9f4-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fa9f4-111">EXAMPLES</span></span>

### <span data-ttu-id="fa9f4-112">Exemplo 1: definir uma variável e obter seu valor</span><span class="sxs-lookup"><span data-stu-id="fa9f4-112">Example 1: Set a variable and get its value</span></span>

<span data-ttu-id="fa9f4-113">Esses comandos definem o valor da `$desc` variável como `A description` e, em seguida, obtém o valor da variável.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-113">These commands set the value of the `$desc` variable to `A description`, and then gets the value of the variable.</span></span>

```powershell
Set-Variable -Name "desc" -Value "A description"
Get-Variable -Name "desc"
```

```Output
Name                           Value
----                           -----
desc                           A description
```

### <span data-ttu-id="fa9f4-114">Exemplo 2: definir uma variável global, somente leitura</span><span class="sxs-lookup"><span data-stu-id="fa9f4-114">Example 2: Set a global, read-only variable</span></span>

<span data-ttu-id="fa9f4-115">Este exemplo cria uma variável global, somente leitura que contém todos os processos no sistema e, em seguida, exibe todas as propriedades da variável.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-115">This example creates a global, read-only variable that contains all processes on the system, and then it displays all properties of the variable.</span></span>

```powershell
Set-Variable -Name "processes" -Value (Get-Process) -Option constant -Scope global -Description "All processes" -PassThru |
    Format-List -Property *
```

<span data-ttu-id="fa9f4-116">O comando usa o `Set-Variable` cmdlet para criar a variável.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-116">The command uses the `Set-Variable` cmdlet to create the variable.</span></span> <span data-ttu-id="fa9f4-117">Ele usa o parâmetro **PassThru** para criar um objeto que representa a nova variável e usa o operador de pipeline ( `|` ) para passar o objeto para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-117">It uses the **PassThru** parameter to create an object representing the new variable, and it uses the pipeline operator (`|`) to pass the object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="fa9f4-118">Ele usa o parâmetro **Property** de `Format-List` com um valor de All ( `*` ) para exibir todas as propriedades da variável recém-criada.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-118">It uses the **Property** parameter of `Format-List` with a value of all (`*`) to display all properties of the newly created variable.</span></span>

<span data-ttu-id="fa9f4-119">O valor, `(Get-Process)` , é colocado entre parênteses para garantir que ele seja executado antes de ser armazenado na variável.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-119">The value, `(Get-Process)`, is enclosed in parentheses to ensure that it is executed before being stored in the variable.</span></span> <span data-ttu-id="fa9f4-120">Caso contrário, a variável conterá as palavras " **Get-Process** ".</span><span class="sxs-lookup"><span data-stu-id="fa9f4-120">Otherwise, the variable contains the words " **Get-Process** ".</span></span>

### <span data-ttu-id="fa9f4-121">Exemplo 3: entender as variáveis públicas versus privadas</span><span class="sxs-lookup"><span data-stu-id="fa9f4-121">Example 3: Understand public vs. private variables</span></span>

<span data-ttu-id="fa9f4-122">Este exemplo mostra como alterar a visibilidade de uma variável para `Private` .</span><span class="sxs-lookup"><span data-stu-id="fa9f4-122">This example shows how to change the visibility of a variable to `Private`.</span></span> <span data-ttu-id="fa9f4-123">Essa variável pode ser lida e alterada por scripts com as permissões necessárias, mas não fica visível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-123">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

```
PS C:\> New-Variable -Name "counter" -Visibility Public -Value 26
PS C:\> $Counter
26

PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}
Counter               26

PS C:\> Set-Variable -Name "counter" -Visibility Private
PS C:\> Get-Variable c*

Name                  Value
----                  -----
Culture               en-US
ConsoleFileName
ConfirmPreference     High
CommandLineParameters {}

PS C:\> $counter
"Cannot access the variable '$counter' because it is a private variable"

PS C:\> .\use-counter.ps1
#Commands completed successfully.
```

<span data-ttu-id="fa9f4-124">Este comando mostra como alterar a visibilidade de uma variável para particular.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-124">This command shows how to change the visibility of a variable to Private.</span></span> <span data-ttu-id="fa9f4-125">Essa variável pode ser lida e alterada por scripts com as permissões necessárias, mas não fica visível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-125">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

## <span data-ttu-id="fa9f4-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fa9f4-126">PARAMETERS</span></span>

### <span data-ttu-id="fa9f4-127">-Description</span><span class="sxs-lookup"><span data-stu-id="fa9f4-127">-Description</span></span>

<span data-ttu-id="fa9f4-128">Especifica a descrição da variável.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-128">Specifies the description of the variable.</span></span>

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

### <span data-ttu-id="fa9f4-129">-Excluir</span><span class="sxs-lookup"><span data-stu-id="fa9f4-129">-Exclude</span></span>

<span data-ttu-id="fa9f4-130">Especifica uma matriz de itens que esse cmdlet exclui da operação.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-130">Specifies an array of items that this cmdlet excludes from the operation.</span></span> <span data-ttu-id="fa9f4-131">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-131">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="fa9f4-132">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="fa9f4-132">Enter a path element or pattern, such as `*.txt`.</span></span>
<span data-ttu-id="fa9f4-133">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-133">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="fa9f4-134">-Force</span><span class="sxs-lookup"><span data-stu-id="fa9f4-134">-Force</span></span>

<span data-ttu-id="fa9f4-135">Permite que você crie uma variável com o mesmo nome de uma variável somente leitura existente, ou altere o valor de uma variável somente leitura.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-135">Allows you to create a variable with the same name as an existing read-only variable, or to change the value of a read-only variable.</span></span>

<span data-ttu-id="fa9f4-136">Por padrão, você pode substituir uma variável, a menos que a variável tenha um valor de opção de `ReadOnly` ou `Constant` .</span><span class="sxs-lookup"><span data-stu-id="fa9f4-136">By default, you can overwrite a variable, unless the variable has an option value of `ReadOnly` or `Constant`.</span></span> <span data-ttu-id="fa9f4-137">Para obter mais informações, consulte o parâmetro **Option** .</span><span class="sxs-lookup"><span data-stu-id="fa9f4-137">For more information, see the **Option** parameter.</span></span>

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

### <span data-ttu-id="fa9f4-138">-Incluir</span><span class="sxs-lookup"><span data-stu-id="fa9f4-138">-Include</span></span>

<span data-ttu-id="fa9f4-139">Especifica uma matriz de itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-139">Specifies an array of items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="fa9f4-140">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="fa9f4-140">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="fa9f4-141">Insira um nome ou padrão de nome, como `c*` .</span><span class="sxs-lookup"><span data-stu-id="fa9f4-141">Enter a name or name pattern, such as `c*`.</span></span> <span data-ttu-id="fa9f4-142">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-142">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="fa9f4-143">-Name</span><span class="sxs-lookup"><span data-stu-id="fa9f4-143">-Name</span></span>

<span data-ttu-id="fa9f4-144">Especifica o nome da variável.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-144">Specifies the variable name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fa9f4-145">-Opção</span><span class="sxs-lookup"><span data-stu-id="fa9f4-145">-Option</span></span>

<span data-ttu-id="fa9f4-146">Especifica o valor da propriedade **Options** da variável.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-146">Specifies the value of the **Options** property of the variable.</span></span>

<span data-ttu-id="fa9f4-147">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="fa9f4-147">Valid values are:</span></span>

- <span data-ttu-id="fa9f4-148">`None`: Não define opções.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-148">`None`: Sets no options.</span></span> <span data-ttu-id="fa9f4-149">("None" é o padrão.)</span><span class="sxs-lookup"><span data-stu-id="fa9f4-149">("None" is the default.)</span></span>
- <span data-ttu-id="fa9f4-150">`ReadOnly`: Pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-150">`ReadOnly`: Can be deleted.</span></span> <span data-ttu-id="fa9f4-151">Não pode ser alterado, exceto pelo uso do parâmetro Force.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-151">Cannot be changed, except by using the Force parameter.</span></span>
- <span data-ttu-id="fa9f4-152">`Constant`: Não pode ser excluído ou alterado.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-152">`Constant`: Cannot be deleted or changed.</span></span> <span data-ttu-id="fa9f4-153">`Constant` é válido somente quando você está criando uma variável.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-153">`Constant` is valid only when you are creating a variable.</span></span> <span data-ttu-id="fa9f4-154">Você não pode alterar as opções de uma variável existente para `Constant` .</span><span class="sxs-lookup"><span data-stu-id="fa9f4-154">You cannot change the options of an existing variable to `Constant`.</span></span>
- <span data-ttu-id="fa9f4-155">`Private`: A variável está disponível somente no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-155">`Private`: The variable is available only in the current scope.</span></span>
- <span data-ttu-id="fa9f4-156">`AllScope`: A variável é copiada para todos os novos escopos criados.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-156">`AllScope`: The variable is copied to any new scopes that are created.</span></span>

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

### <span data-ttu-id="fa9f4-157">-PassThru</span><span class="sxs-lookup"><span data-stu-id="fa9f4-157">-PassThru</span></span>

<span data-ttu-id="fa9f4-158">Retorna um objeto que representa a nova variável.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-158">Returns an object representing the new variable.</span></span> <span data-ttu-id="fa9f4-159">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-159">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="fa9f4-160">-Escopo</span><span class="sxs-lookup"><span data-stu-id="fa9f4-160">-Scope</span></span>

<span data-ttu-id="fa9f4-161">Especifica o escopo da variável. Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="fa9f4-161">Specifies the scope of the variable.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fa9f4-162">Global</span><span class="sxs-lookup"><span data-stu-id="fa9f4-162">Global</span></span>
- <span data-ttu-id="fa9f4-163">Local</span><span class="sxs-lookup"><span data-stu-id="fa9f4-163">Local</span></span>
- <span data-ttu-id="fa9f4-164">script</span><span class="sxs-lookup"><span data-stu-id="fa9f4-164">Script</span></span>
- <span data-ttu-id="fa9f4-165">Privados</span><span class="sxs-lookup"><span data-stu-id="fa9f4-165">Private</span></span>
- <span data-ttu-id="fa9f4-166">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai).</span><span class="sxs-lookup"><span data-stu-id="fa9f4-166">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>

<span data-ttu-id="fa9f4-167">Local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-167">Local is the default.</span></span>

<span data-ttu-id="fa9f4-168">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="fa9f4-168">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fa9f4-169">-Value</span><span class="sxs-lookup"><span data-stu-id="fa9f4-169">-Value</span></span>

<span data-ttu-id="fa9f4-170">Especifica o valor da variável.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-170">Specifies the value of the variable.</span></span>

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

### <span data-ttu-id="fa9f4-171">-Visibilidade</span><span class="sxs-lookup"><span data-stu-id="fa9f4-171">-Visibility</span></span>

<span data-ttu-id="fa9f4-172">Determina se a variável é visível fora da sessão na qual ela foi criada.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-172">Determines whether the variable is visible outside of the session in which it was created.</span></span> <span data-ttu-id="fa9f4-173">Esse parâmetro é projetado para uso em scripts e comandos que serão entregues a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-173">This parameter is designed for use in scripts and commands that will be delivered to other users.</span></span>

<span data-ttu-id="fa9f4-174">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="fa9f4-174">Valid values are:</span></span>

- <span data-ttu-id="fa9f4-175">Público: a variável está visível.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-175">Public:  The variable is visible.</span></span> <span data-ttu-id="fa9f4-176">("Public" é o padrão.)</span><span class="sxs-lookup"><span data-stu-id="fa9f4-176">("Public" is the default.)</span></span>
- <span data-ttu-id="fa9f4-177">Particular: a variável não é visível.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-177">Private: The variable is not visible.</span></span>

<span data-ttu-id="fa9f4-178">Quando uma variável é privada, ela não aparece em listas de variáveis, como as retornadas por `Get-Variable` , ou em exibições da unidade **Variable:** .</span><span class="sxs-lookup"><span data-stu-id="fa9f4-178">When a variable is private, it does not appear in lists of variables, such as those returned by `Get-Variable`, or in displays of the **Variable:** drive.</span></span> <span data-ttu-id="fa9f4-179">Comandos para ler ou alterar o valor de uma variável privada retornam um erro.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-179">Commands to read or change the value of a private variable return an error.</span></span> <span data-ttu-id="fa9f4-180">No entanto, o usuário pode executar comandos que usam uma variável privada se os comandos tiverem sido escritos na sessão em que a variável foi definida.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-180">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

```yaml
Type: System.Management.Automation.SessionStateEntryVisibility
Parameter Sets: (All)
Aliases:
Accepted values: Public, Private

Required: False
Position: Named
Default value: Public
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fa9f4-181">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fa9f4-181">-Confirm</span></span>

<span data-ttu-id="fa9f4-182">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-182">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fa9f4-183">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fa9f4-183">-WhatIf</span></span>

<span data-ttu-id="fa9f4-184">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-184">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="fa9f4-185">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-185">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fa9f4-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fa9f4-186">CommonParameters</span></span>

<span data-ttu-id="fa9f4-187">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fa9f4-188">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fa9f4-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fa9f4-189">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fa9f4-189">INPUTS</span></span>

### <span data-ttu-id="fa9f4-190">System.Object</span><span class="sxs-lookup"><span data-stu-id="fa9f4-190">System.Object</span></span>

<span data-ttu-id="fa9f4-191">É possível canalizar um objeto que representa o valor da variável para `Set-Variable` .</span><span class="sxs-lookup"><span data-stu-id="fa9f4-191">You can pipe an object that represents the value of the variable to `Set-Variable`.</span></span>

## <span data-ttu-id="fa9f4-192">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fa9f4-192">OUTPUTS</span></span>

### <span data-ttu-id="fa9f4-193">Nenhum ou System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="fa9f4-193">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="fa9f4-194">Quando você usa o parâmetro **PassThru** , o `Set-Variable` gera um objeto **System. Management. Automation. PSVariable** que representa a variável nova ou alterada.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-194">When you use the **PassThru** parameter, `Set-Variable` generates a **System.Management.Automation.PSVariable** object representing the new or changed variable.</span></span>
<span data-ttu-id="fa9f4-195">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="fa9f4-195">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fa9f4-196">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fa9f4-196">NOTES</span></span>

## <span data-ttu-id="fa9f4-197">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fa9f4-197">RELATED LINKS</span></span>

[<span data-ttu-id="fa9f4-198">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="fa9f4-198">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="fa9f4-199">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="fa9f4-199">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="fa9f4-200">New-Variable</span><span class="sxs-lookup"><span data-stu-id="fa9f4-200">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="fa9f4-201">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="fa9f4-201">Remove-Variable</span></span>](Remove-Variable.md)
