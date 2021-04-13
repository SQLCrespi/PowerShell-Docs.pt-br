---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/06/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Variable
ms.openlocfilehash: 39ee20f067125a996cf4ce3b6e5d61894402c279
ms.sourcegitcommit: 241071803915ab7d544576b5652ac23349a86369
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "107027270"
---
# <span data-ttu-id="e05ca-102">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="e05ca-102">Set-Variable</span></span>

## <span data-ttu-id="e05ca-103">Sinopse</span><span class="sxs-lookup"><span data-stu-id="e05ca-103">Synopsis</span></span>
<span data-ttu-id="e05ca-104">Define o valor de uma variável.</span><span class="sxs-lookup"><span data-stu-id="e05ca-104">Sets the value of a variable.</span></span> <span data-ttu-id="e05ca-105">Cria a variável se uma com o nome solicitado não existir.</span><span class="sxs-lookup"><span data-stu-id="e05ca-105">Creates the variable if one with the requested name does not exist.</span></span>

## <span data-ttu-id="e05ca-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e05ca-106">Syntax</span></span>

```
Set-Variable [-Name] <String[]> [[-Value] <Object>] [-Include <String[]>] [-Exclude <String[]>]
 [-Description <String>] [-Option <ScopedItemOptions>] [-Force] [-Visibility <SessionStateEntryVisibility>]
 [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e05ca-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="e05ca-107">Description</span></span>

<span data-ttu-id="e05ca-108">O `Set-Variable` cmdlet atribui um valor a uma variável especificada ou altera o valor atual.</span><span class="sxs-lookup"><span data-stu-id="e05ca-108">The `Set-Variable` cmdlet assigns a value to a specified variable or changes the current value.</span></span> <span data-ttu-id="e05ca-109">Se a variável não existir, o cmdlet a criará.</span><span class="sxs-lookup"><span data-stu-id="e05ca-109">If the variable does not exist, the cmdlet creates it.</span></span>

## <span data-ttu-id="e05ca-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e05ca-110">Examples</span></span>

### <span data-ttu-id="e05ca-111">Exemplo 1: definir uma variável e obter seu valor</span><span class="sxs-lookup"><span data-stu-id="e05ca-111">Example 1: Set a variable and get its value</span></span>

<span data-ttu-id="e05ca-112">Esses comandos definem o valor da `$desc` variável como `A description` e, em seguida, obtém o valor da variável.</span><span class="sxs-lookup"><span data-stu-id="e05ca-112">These commands set the value of the `$desc` variable to `A description`, and then gets the value of the variable.</span></span>

```powershell
Set-Variable -Name "desc" -Value "A description"
Get-Variable -Name "desc"
```

```Output
Name                           Value
----                           -----
desc                           A description
```

### <span data-ttu-id="e05ca-113">Exemplo 2: definir uma variável global, somente leitura</span><span class="sxs-lookup"><span data-stu-id="e05ca-113">Example 2: Set a global, read-only variable</span></span>

<span data-ttu-id="e05ca-114">Este exemplo cria uma variável global, somente leitura que contém todos os processos no sistema e, em seguida, exibe todas as propriedades da variável.</span><span class="sxs-lookup"><span data-stu-id="e05ca-114">This example creates a global, read-only variable that contains all processes on the system, and then it displays all properties of the variable.</span></span>

```powershell
Set-Variable -Name "processes" -Value (Get-Process) -Option constant -Scope global -Description "All processes" -PassThru |
    Format-List -Property *
```

<span data-ttu-id="e05ca-115">O comando usa o `Set-Variable` cmdlet para criar a variável.</span><span class="sxs-lookup"><span data-stu-id="e05ca-115">The command uses the `Set-Variable` cmdlet to create the variable.</span></span> <span data-ttu-id="e05ca-116">Ele usa o parâmetro **PassThru** para criar um objeto que representa a nova variável e usa o operador de pipeline ( `|` ) para passar o objeto para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e05ca-116">It uses the **PassThru** parameter to create an object representing the new variable, and it uses the pipeline operator (`|`) to pass the object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="e05ca-117">Ele usa o parâmetro **Property** de `Format-List` com um valor de All ( `*` ) para exibir todas as propriedades da variável recém-criada.</span><span class="sxs-lookup"><span data-stu-id="e05ca-117">It uses the **Property** parameter of `Format-List` with a value of all (`*`) to display all properties of the newly created variable.</span></span>

<span data-ttu-id="e05ca-118">O valor, `(Get-Process)` , é colocado entre parênteses para garantir que ele seja executado antes de ser armazenado na variável.</span><span class="sxs-lookup"><span data-stu-id="e05ca-118">The value, `(Get-Process)`, is enclosed in parentheses to ensure that it is executed before being stored in the variable.</span></span> <span data-ttu-id="e05ca-119">Caso contrário, a variável conterá as palavras "**Get-Process**".</span><span class="sxs-lookup"><span data-stu-id="e05ca-119">Otherwise, the variable contains the words "**Get-Process**".</span></span>

### <span data-ttu-id="e05ca-120">Exemplo 3: entender as variáveis públicas versus privadas</span><span class="sxs-lookup"><span data-stu-id="e05ca-120">Example 3: Understand public vs. private variables</span></span>

<span data-ttu-id="e05ca-121">Este exemplo mostra como alterar a visibilidade de uma variável para `Private` .</span><span class="sxs-lookup"><span data-stu-id="e05ca-121">This example shows how to change the visibility of a variable to `Private`.</span></span> <span data-ttu-id="e05ca-122">Essa variável pode ser lida e alterada por scripts com as permissões necessárias, mas não fica visível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e05ca-122">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

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

<span data-ttu-id="e05ca-123">Este comando mostra como alterar a visibilidade de uma variável para particular.</span><span class="sxs-lookup"><span data-stu-id="e05ca-123">This command shows how to change the visibility of a variable to Private.</span></span> <span data-ttu-id="e05ca-124">Essa variável pode ser lida e alterada por scripts com as permissões necessárias, mas não fica visível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e05ca-124">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

## <span data-ttu-id="e05ca-125">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e05ca-125">Parameters</span></span>

### <span data-ttu-id="e05ca-126">-Description</span><span class="sxs-lookup"><span data-stu-id="e05ca-126">-Description</span></span>

<span data-ttu-id="e05ca-127">Especifica a descrição da variável.</span><span class="sxs-lookup"><span data-stu-id="e05ca-127">Specifies the description of the variable.</span></span>

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

### <span data-ttu-id="e05ca-128">-Excluir</span><span class="sxs-lookup"><span data-stu-id="e05ca-128">-Exclude</span></span>

<span data-ttu-id="e05ca-129">Especifica uma matriz de itens que esse cmdlet exclui da operação.</span><span class="sxs-lookup"><span data-stu-id="e05ca-129">Specifies an array of items that this cmdlet excludes from the operation.</span></span> <span data-ttu-id="e05ca-130">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="e05ca-130">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="e05ca-131">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="e05ca-131">Enter a path element or pattern, such as `*.txt`.</span></span>
<span data-ttu-id="e05ca-132">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="e05ca-132">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="e05ca-133">-Force</span><span class="sxs-lookup"><span data-stu-id="e05ca-133">-Force</span></span>

<span data-ttu-id="e05ca-134">Permite que você crie uma variável com o mesmo nome de uma variável somente leitura existente, ou altere o valor de uma variável somente leitura.</span><span class="sxs-lookup"><span data-stu-id="e05ca-134">Allows you to create a variable with the same name as an existing read-only variable, or to change the value of a read-only variable.</span></span>

<span data-ttu-id="e05ca-135">Por padrão, você pode substituir uma variável, a menos que a variável tenha um valor de opção de `ReadOnly` ou `Constant` .</span><span class="sxs-lookup"><span data-stu-id="e05ca-135">By default, you can overwrite a variable, unless the variable has an option value of `ReadOnly` or `Constant`.</span></span> <span data-ttu-id="e05ca-136">Para obter mais informações, consulte o parâmetro **Option** .</span><span class="sxs-lookup"><span data-stu-id="e05ca-136">For more information, see the **Option** parameter.</span></span>

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

### <span data-ttu-id="e05ca-137">-Incluir</span><span class="sxs-lookup"><span data-stu-id="e05ca-137">-Include</span></span>

<span data-ttu-id="e05ca-138">Especifica uma matriz de itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="e05ca-138">Specifies an array of items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="e05ca-139">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="e05ca-139">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="e05ca-140">Insira um nome ou padrão de nome, como `c*` .</span><span class="sxs-lookup"><span data-stu-id="e05ca-140">Enter a name or name pattern, such as `c*`.</span></span> <span data-ttu-id="e05ca-141">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="e05ca-141">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="e05ca-142">-Name</span><span class="sxs-lookup"><span data-stu-id="e05ca-142">-Name</span></span>

<span data-ttu-id="e05ca-143">Especifica o nome da variável.</span><span class="sxs-lookup"><span data-stu-id="e05ca-143">Specifies the variable name.</span></span>

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

### <span data-ttu-id="e05ca-144">-Opção</span><span class="sxs-lookup"><span data-stu-id="e05ca-144">-Option</span></span>

<span data-ttu-id="e05ca-145">Especifica o valor da propriedade **Options** da variável.</span><span class="sxs-lookup"><span data-stu-id="e05ca-145">Specifies the value of the **Options** property of the variable.</span></span>

<span data-ttu-id="e05ca-146">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="e05ca-146">Valid values are:</span></span>

- <span data-ttu-id="e05ca-147">`None`: Não define opções.</span><span class="sxs-lookup"><span data-stu-id="e05ca-147">`None`: Sets no options.</span></span> <span data-ttu-id="e05ca-148">( `None` é o padrão.)</span><span class="sxs-lookup"><span data-stu-id="e05ca-148">(`None` is the default.)</span></span>
- <span data-ttu-id="e05ca-149">`ReadOnly`: Pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="e05ca-149">`ReadOnly`: Can be deleted.</span></span> <span data-ttu-id="e05ca-150">Não pode ser alterado, exceto pelo uso do parâmetro Force.</span><span class="sxs-lookup"><span data-stu-id="e05ca-150">Cannot be changed, except by using the Force parameter.</span></span>
- <span data-ttu-id="e05ca-151">`Constant`: Não pode ser excluído ou alterado.</span><span class="sxs-lookup"><span data-stu-id="e05ca-151">`Constant`: Cannot be deleted or changed.</span></span> <span data-ttu-id="e05ca-152">`Constant` é válido somente quando você está criando uma variável.</span><span class="sxs-lookup"><span data-stu-id="e05ca-152">`Constant` is valid only when you are creating a variable.</span></span> <span data-ttu-id="e05ca-153">Você não pode alterar as opções de uma variável existente para `Constant` .</span><span class="sxs-lookup"><span data-stu-id="e05ca-153">You cannot change the options of an existing variable to `Constant`.</span></span>
- <span data-ttu-id="e05ca-154">`Private`: A variável está disponível somente no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="e05ca-154">`Private`: The variable is available only in the current scope.</span></span>
- <span data-ttu-id="e05ca-155">`AllScope`: A variável é copiada para todos os novos escopos criados.</span><span class="sxs-lookup"><span data-stu-id="e05ca-155">`AllScope`: The variable is copied to any new scopes that are created.</span></span>

<span data-ttu-id="e05ca-156">Esses valores são definidos como uma enumeração baseada em sinalizador.</span><span class="sxs-lookup"><span data-stu-id="e05ca-156">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="e05ca-157">Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e05ca-157">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="e05ca-158">Os valores podem ser passados para o parâmetro de **opção** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores.</span><span class="sxs-lookup"><span data-stu-id="e05ca-158">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="e05ca-159">O cmdlet combinará os valores usando uma operação binary ou.</span><span class="sxs-lookup"><span data-stu-id="e05ca-159">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="e05ca-160">Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.</span><span class="sxs-lookup"><span data-stu-id="e05ca-160">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

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

### <span data-ttu-id="e05ca-161">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e05ca-161">-PassThru</span></span>

<span data-ttu-id="e05ca-162">Retorna um objeto que representa a nova variável.</span><span class="sxs-lookup"><span data-stu-id="e05ca-162">Returns an object representing the new variable.</span></span> <span data-ttu-id="e05ca-163">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="e05ca-163">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="e05ca-164">-Escopo</span><span class="sxs-lookup"><span data-stu-id="e05ca-164">-Scope</span></span>

<span data-ttu-id="e05ca-165">Especifica o escopo da variável. Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="e05ca-165">Specifies the scope of the variable.The acceptable values for this parameter are:</span></span>

- `Global`
- `Local`
- `Script`
- `Private`
- <span data-ttu-id="e05ca-166">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai).</span><span class="sxs-lookup"><span data-stu-id="e05ca-166">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>

<span data-ttu-id="e05ca-167">`Local` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="e05ca-167">`Local` is the default.</span></span>

<span data-ttu-id="e05ca-168">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="e05ca-168">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).</span></span>

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

### <span data-ttu-id="e05ca-169">-Value</span><span class="sxs-lookup"><span data-stu-id="e05ca-169">-Value</span></span>

<span data-ttu-id="e05ca-170">Especifica o valor da variável.</span><span class="sxs-lookup"><span data-stu-id="e05ca-170">Specifies the value of the variable.</span></span>

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

### <span data-ttu-id="e05ca-171">-Visibilidade</span><span class="sxs-lookup"><span data-stu-id="e05ca-171">-Visibility</span></span>

<span data-ttu-id="e05ca-172">Determina se a variável é visível fora da sessão na qual ela foi criada.</span><span class="sxs-lookup"><span data-stu-id="e05ca-172">Determines whether the variable is visible outside of the session in which it was created.</span></span> <span data-ttu-id="e05ca-173">Esse parâmetro é projetado para uso em scripts e comandos que serão entregues a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="e05ca-173">This parameter is designed for use in scripts and commands that will be delivered to other users.</span></span>

<span data-ttu-id="e05ca-174">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="e05ca-174">Valid values are:</span></span>

- <span data-ttu-id="e05ca-175">`Public`: A variável está visível.</span><span class="sxs-lookup"><span data-stu-id="e05ca-175">`Public`:  The variable is visible.</span></span> <span data-ttu-id="e05ca-176">( `Public` é o padrão.)</span><span class="sxs-lookup"><span data-stu-id="e05ca-176">(`Public` is the default.)</span></span>
- <span data-ttu-id="e05ca-177">`Private`: A variável não é visível.</span><span class="sxs-lookup"><span data-stu-id="e05ca-177">`Private`: The variable is not visible.</span></span>

<span data-ttu-id="e05ca-178">Quando uma variável é privada, ela não aparece em listas de variáveis, como as retornadas por `Get-Variable` , ou em exibições da unidade **Variable:** .</span><span class="sxs-lookup"><span data-stu-id="e05ca-178">When a variable is private, it does not appear in lists of variables, such as those returned by `Get-Variable`, or in displays of the **Variable:** drive.</span></span> <span data-ttu-id="e05ca-179">Comandos para ler ou alterar o valor de uma variável privada retornam um erro.</span><span class="sxs-lookup"><span data-stu-id="e05ca-179">Commands to read or change the value of a private variable return an error.</span></span> <span data-ttu-id="e05ca-180">No entanto, o usuário pode executar comandos que usam uma variável privada se os comandos tiverem sido escritos na sessão em que a variável foi definida.</span><span class="sxs-lookup"><span data-stu-id="e05ca-180">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

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

### <span data-ttu-id="e05ca-181">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e05ca-181">-Confirm</span></span>

<span data-ttu-id="e05ca-182">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e05ca-182">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e05ca-183">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e05ca-183">-WhatIf</span></span>

<span data-ttu-id="e05ca-184">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="e05ca-184">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e05ca-185">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="e05ca-185">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e05ca-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e05ca-186">CommonParameters</span></span>

<span data-ttu-id="e05ca-187">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e05ca-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e05ca-188">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e05ca-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e05ca-189">Entradas</span><span class="sxs-lookup"><span data-stu-id="e05ca-189">Inputs</span></span>

### <span data-ttu-id="e05ca-190">System.Object</span><span class="sxs-lookup"><span data-stu-id="e05ca-190">System.Object</span></span>

<span data-ttu-id="e05ca-191">É possível canalizar um objeto que representa o valor da variável para `Set-Variable` .</span><span class="sxs-lookup"><span data-stu-id="e05ca-191">You can pipe an object that represents the value of the variable to `Set-Variable`.</span></span>

## <span data-ttu-id="e05ca-192">Saídas</span><span class="sxs-lookup"><span data-stu-id="e05ca-192">Outputs</span></span>

### <span data-ttu-id="e05ca-193">Nenhum ou System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="e05ca-193">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="e05ca-194">Quando você usa o parâmetro **PassThru** , o `Set-Variable` gera um objeto **System. Management. Automation. PSVariable** que representa a variável nova ou alterada.</span><span class="sxs-lookup"><span data-stu-id="e05ca-194">When you use the **PassThru** parameter, `Set-Variable` generates a **System.Management.Automation.PSVariable** object representing the new or changed variable.</span></span>
<span data-ttu-id="e05ca-195">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="e05ca-195">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e05ca-196">Anotações</span><span class="sxs-lookup"><span data-stu-id="e05ca-196">Notes</span></span>

## <span data-ttu-id="e05ca-197">Links Relacionados</span><span class="sxs-lookup"><span data-stu-id="e05ca-197">Related Links</span></span>

[<span data-ttu-id="e05ca-198">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="e05ca-198">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="e05ca-199">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="e05ca-199">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="e05ca-200">New-Variable</span><span class="sxs-lookup"><span data-stu-id="e05ca-200">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="e05ca-201">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="e05ca-201">Remove-Variable</span></span>](Remove-Variable.md)
