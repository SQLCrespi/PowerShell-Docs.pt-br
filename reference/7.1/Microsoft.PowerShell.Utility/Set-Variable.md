---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/06/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-variable?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Variable
ms.openlocfilehash: 823e9b8376489464105940856b17f3e23cf048d3
ms.sourcegitcommit: 241071803915ab7d544576b5652ac23349a86369
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "107027185"
---
# <span data-ttu-id="2a59b-103">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="2a59b-103">Set-Variable</span></span>

## <span data-ttu-id="2a59b-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="2a59b-104">Synopsis</span></span>
<span data-ttu-id="2a59b-105">Define o valor de uma variável.</span><span class="sxs-lookup"><span data-stu-id="2a59b-105">Sets the value of a variable.</span></span> <span data-ttu-id="2a59b-106">Cria a variável se uma com o nome solicitado não existir.</span><span class="sxs-lookup"><span data-stu-id="2a59b-106">Creates the variable if one with the requested name does not exist.</span></span>

## <span data-ttu-id="2a59b-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2a59b-107">Syntax</span></span>

```
Set-Variable [-Name] <String[]> [[-Value] <Object>] [-Include <String[]>] [-Exclude <String[]>]
 [-Description <String>] [-Option <ScopedItemOptions>] [-Force] [-Visibility <SessionStateEntryVisibility>]
 [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2a59b-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="2a59b-108">Description</span></span>

<span data-ttu-id="2a59b-109">O `Set-Variable` cmdlet atribui um valor a uma variável especificada ou altera o valor atual.</span><span class="sxs-lookup"><span data-stu-id="2a59b-109">The `Set-Variable` cmdlet assigns a value to a specified variable or changes the current value.</span></span> <span data-ttu-id="2a59b-110">Se a variável não existir, o cmdlet a criará.</span><span class="sxs-lookup"><span data-stu-id="2a59b-110">If the variable does not exist, the cmdlet creates it.</span></span>

## <span data-ttu-id="2a59b-111">Exemplos</span><span class="sxs-lookup"><span data-stu-id="2a59b-111">Examples</span></span>

### <span data-ttu-id="2a59b-112">Exemplo 1: definir uma variável e obter seu valor</span><span class="sxs-lookup"><span data-stu-id="2a59b-112">Example 1: Set a variable and get its value</span></span>

<span data-ttu-id="2a59b-113">Esses comandos definem o valor da `$desc` variável como `A description` e, em seguida, obtém o valor da variável.</span><span class="sxs-lookup"><span data-stu-id="2a59b-113">These commands set the value of the `$desc` variable to `A description`, and then gets the value of the variable.</span></span>

```powershell
Set-Variable -Name "desc" -Value "A description"
Get-Variable -Name "desc"
```

```Output
Name                           Value
----                           -----
desc                           A description
```

### <span data-ttu-id="2a59b-114">Exemplo 2: definir uma variável global, somente leitura</span><span class="sxs-lookup"><span data-stu-id="2a59b-114">Example 2: Set a global, read-only variable</span></span>

<span data-ttu-id="2a59b-115">Este exemplo cria uma variável global, somente leitura que contém todos os processos no sistema e, em seguida, exibe todas as propriedades da variável.</span><span class="sxs-lookup"><span data-stu-id="2a59b-115">This example creates a global, read-only variable that contains all processes on the system, and then it displays all properties of the variable.</span></span>

```powershell
Set-Variable -Name "processes" -Value (Get-Process) -Option Constant -Scope global -Description "All processes" -PassThru |
    Format-List -Property *
```

<span data-ttu-id="2a59b-116">O comando usa o `Set-Variable` cmdlet para criar a variável.</span><span class="sxs-lookup"><span data-stu-id="2a59b-116">The command uses the `Set-Variable` cmdlet to create the variable.</span></span> <span data-ttu-id="2a59b-117">Ele usa o parâmetro **PassThru** para criar um objeto que representa a nova variável e usa o operador de pipeline ( `|` ) para passar o objeto para o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2a59b-117">It uses the **PassThru** parameter to create an object representing the new variable, and it uses the pipeline operator (`|`) to pass the object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="2a59b-118">Ele usa o parâmetro **Property** de `Format-List` com um valor de All ( `*` ) para exibir todas as propriedades da variável recém-criada.</span><span class="sxs-lookup"><span data-stu-id="2a59b-118">It uses the **Property** parameter of `Format-List` with a value of all (`*`) to display all properties of the newly created variable.</span></span>

<span data-ttu-id="2a59b-119">O valor, `(Get-Process)` , é colocado entre parênteses para garantir que ele seja executado antes de ser armazenado na variável.</span><span class="sxs-lookup"><span data-stu-id="2a59b-119">The value, `(Get-Process)`, is enclosed in parentheses to ensure that it is executed before being stored in the variable.</span></span> <span data-ttu-id="2a59b-120">Caso contrário, a variável conterá as palavras "**Get-Process**".</span><span class="sxs-lookup"><span data-stu-id="2a59b-120">Otherwise, the variable contains the words "**Get-Process**".</span></span>

### <span data-ttu-id="2a59b-121">Exemplo 3: entender as variáveis públicas versus privadas</span><span class="sxs-lookup"><span data-stu-id="2a59b-121">Example 3: Understand public vs. private variables</span></span>

<span data-ttu-id="2a59b-122">Este exemplo mostra como alterar a visibilidade de uma variável para `Private` .</span><span class="sxs-lookup"><span data-stu-id="2a59b-122">This example shows how to change the visibility of a variable to `Private`.</span></span> <span data-ttu-id="2a59b-123">Essa variável pode ser lida e alterada por scripts com as permissões necessárias, mas não fica visível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="2a59b-123">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

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

<span data-ttu-id="2a59b-124">Este comando mostra como alterar a visibilidade de uma variável para particular.</span><span class="sxs-lookup"><span data-stu-id="2a59b-124">This command shows how to change the visibility of a variable to Private.</span></span> <span data-ttu-id="2a59b-125">Essa variável pode ser lida e alterada por scripts com as permissões necessárias, mas não fica visível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="2a59b-125">This variable can be read and changed by scripts with the required permissions, but it is not visible to the user.</span></span>

## <span data-ttu-id="2a59b-126">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2a59b-126">Parameters</span></span>

### <span data-ttu-id="2a59b-127">-Description</span><span class="sxs-lookup"><span data-stu-id="2a59b-127">-Description</span></span>

<span data-ttu-id="2a59b-128">Especifica a descrição da variável.</span><span class="sxs-lookup"><span data-stu-id="2a59b-128">Specifies the description of the variable.</span></span>

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

### <span data-ttu-id="2a59b-129">-Excluir</span><span class="sxs-lookup"><span data-stu-id="2a59b-129">-Exclude</span></span>

<span data-ttu-id="2a59b-130">Especifica uma matriz de itens que esse cmdlet exclui da operação.</span><span class="sxs-lookup"><span data-stu-id="2a59b-130">Specifies an array of items that this cmdlet excludes from the operation.</span></span> <span data-ttu-id="2a59b-131">O valor deste parâmetro qualifica o parâmetro **Path**.</span><span class="sxs-lookup"><span data-stu-id="2a59b-131">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="2a59b-132">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="2a59b-132">Enter a path element or pattern, such as `*.txt`.</span></span>
<span data-ttu-id="2a59b-133">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="2a59b-133">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="2a59b-134">-Force</span><span class="sxs-lookup"><span data-stu-id="2a59b-134">-Force</span></span>

<span data-ttu-id="2a59b-135">Permite que você crie uma variável com o mesmo nome de uma variável somente leitura existente, ou altere o valor de uma variável somente leitura.</span><span class="sxs-lookup"><span data-stu-id="2a59b-135">Allows you to create a variable with the same name as an existing read-only variable, or to change the value of a read-only variable.</span></span>

<span data-ttu-id="2a59b-136">Por padrão, você pode substituir uma variável, a menos que a variável tenha um valor de opção de `ReadOnly` ou `Constant` .</span><span class="sxs-lookup"><span data-stu-id="2a59b-136">By default, you can overwrite a variable, unless the variable has an option value of `ReadOnly` or `Constant`.</span></span> <span data-ttu-id="2a59b-137">Para obter mais informações, consulte o parâmetro **Option** .</span><span class="sxs-lookup"><span data-stu-id="2a59b-137">For more information, see the **Option** parameter.</span></span>

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

### <span data-ttu-id="2a59b-138">-Incluir</span><span class="sxs-lookup"><span data-stu-id="2a59b-138">-Include</span></span>

<span data-ttu-id="2a59b-139">Especifica uma matriz de itens que esse cmdlet inclui na operação.</span><span class="sxs-lookup"><span data-stu-id="2a59b-139">Specifies an array of items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="2a59b-140">O valor desse parâmetro qualifica o parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="2a59b-140">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="2a59b-141">Insira um nome ou padrão de nome, como `c*` .</span><span class="sxs-lookup"><span data-stu-id="2a59b-141">Enter a name or name pattern, such as `c*`.</span></span> <span data-ttu-id="2a59b-142">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="2a59b-142">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="2a59b-143">-Name</span><span class="sxs-lookup"><span data-stu-id="2a59b-143">-Name</span></span>

<span data-ttu-id="2a59b-144">Especifica o nome da variável.</span><span class="sxs-lookup"><span data-stu-id="2a59b-144">Specifies the variable name.</span></span>

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

### <span data-ttu-id="2a59b-145">-Opção</span><span class="sxs-lookup"><span data-stu-id="2a59b-145">-Option</span></span>

<span data-ttu-id="2a59b-146">Especifica o valor da propriedade **Options** da variável.</span><span class="sxs-lookup"><span data-stu-id="2a59b-146">Specifies the value of the **Options** property of the variable.</span></span>

<span data-ttu-id="2a59b-147">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="2a59b-147">Valid values are:</span></span>

- <span data-ttu-id="2a59b-148">`None`: Não define opções.</span><span class="sxs-lookup"><span data-stu-id="2a59b-148">`None`: Sets no options.</span></span> <span data-ttu-id="2a59b-149">( `None` é o padrão.)</span><span class="sxs-lookup"><span data-stu-id="2a59b-149">(`None` is the default.)</span></span>
- <span data-ttu-id="2a59b-150">`ReadOnly`: Pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="2a59b-150">`ReadOnly`: Can be deleted.</span></span> <span data-ttu-id="2a59b-151">Não pode ser alterado, exceto pelo uso do parâmetro Force.</span><span class="sxs-lookup"><span data-stu-id="2a59b-151">Cannot be changed, except by using the Force parameter.</span></span>
- <span data-ttu-id="2a59b-152">`Constant`: Não pode ser excluído ou alterado.</span><span class="sxs-lookup"><span data-stu-id="2a59b-152">`Constant`: Cannot be deleted or changed.</span></span> <span data-ttu-id="2a59b-153">`Constant` é válido somente quando você está criando uma variável.</span><span class="sxs-lookup"><span data-stu-id="2a59b-153">`Constant` is valid only when you are creating a variable.</span></span> <span data-ttu-id="2a59b-154">Você não pode alterar as opções de uma variável existente para `Constant` .</span><span class="sxs-lookup"><span data-stu-id="2a59b-154">You cannot change the options of an existing variable to `Constant`.</span></span>
- <span data-ttu-id="2a59b-155">`Private`: A variável está disponível somente no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="2a59b-155">`Private`: The variable is available only in the current scope.</span></span>
- <span data-ttu-id="2a59b-156">`AllScope`: A variável é copiada para todos os novos escopos criados.</span><span class="sxs-lookup"><span data-stu-id="2a59b-156">`AllScope`: The variable is copied to any new scopes that are created.</span></span>

<span data-ttu-id="2a59b-157">Esses valores são definidos como uma enumeração baseada em sinalizador.</span><span class="sxs-lookup"><span data-stu-id="2a59b-157">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="2a59b-158">Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2a59b-158">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="2a59b-159">Os valores podem ser passados para o parâmetro de **opção** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores.</span><span class="sxs-lookup"><span data-stu-id="2a59b-159">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="2a59b-160">O cmdlet combinará os valores usando uma operação binary ou.</span><span class="sxs-lookup"><span data-stu-id="2a59b-160">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="2a59b-161">Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.</span><span class="sxs-lookup"><span data-stu-id="2a59b-161">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

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

### <span data-ttu-id="2a59b-162">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2a59b-162">-PassThru</span></span>

<span data-ttu-id="2a59b-163">Retorna um objeto que representa a nova variável.</span><span class="sxs-lookup"><span data-stu-id="2a59b-163">Returns an object representing the new variable.</span></span> <span data-ttu-id="2a59b-164">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="2a59b-164">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="2a59b-165">-Escopo</span><span class="sxs-lookup"><span data-stu-id="2a59b-165">-Scope</span></span>

<span data-ttu-id="2a59b-166">Especifica o escopo da variável. Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="2a59b-166">Specifies the scope of the variable.The acceptable values for this parameter are:</span></span>

- `Global`
- `Local`
- `Script`
- `Private`
- <span data-ttu-id="2a59b-167">Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai).</span><span class="sxs-lookup"><span data-stu-id="2a59b-167">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>

<span data-ttu-id="2a59b-168">`Local` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="2a59b-168">`Local` is the default.</span></span>

<span data-ttu-id="2a59b-169">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="2a59b-169">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_scopes.md).</span></span>

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

### <span data-ttu-id="2a59b-170">-Value</span><span class="sxs-lookup"><span data-stu-id="2a59b-170">-Value</span></span>

<span data-ttu-id="2a59b-171">Especifica o valor da variável.</span><span class="sxs-lookup"><span data-stu-id="2a59b-171">Specifies the value of the variable.</span></span>

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

### <span data-ttu-id="2a59b-172">-Visibilidade</span><span class="sxs-lookup"><span data-stu-id="2a59b-172">-Visibility</span></span>

<span data-ttu-id="2a59b-173">Determina se a variável é visível fora da sessão na qual ela foi criada.</span><span class="sxs-lookup"><span data-stu-id="2a59b-173">Determines whether the variable is visible outside of the session in which it was created.</span></span> <span data-ttu-id="2a59b-174">Esse parâmetro é projetado para uso em scripts e comandos que serão entregues a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="2a59b-174">This parameter is designed for use in scripts and commands that will be delivered to other users.</span></span>

<span data-ttu-id="2a59b-175">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="2a59b-175">Valid values are:</span></span>

- <span data-ttu-id="2a59b-176">`Public`: A variável está visível.</span><span class="sxs-lookup"><span data-stu-id="2a59b-176">`Public`:  The variable is visible.</span></span> <span data-ttu-id="2a59b-177">( `Public` é o padrão.)</span><span class="sxs-lookup"><span data-stu-id="2a59b-177">(`Public` is the default.)</span></span>
- <span data-ttu-id="2a59b-178">`Private`: A variável não é visível.</span><span class="sxs-lookup"><span data-stu-id="2a59b-178">`Private`: The variable is not visible.</span></span>

<span data-ttu-id="2a59b-179">Quando uma variável é privada, ela não aparece em listas de variáveis, como as retornadas por `Get-Variable` , ou em exibições da unidade **Variable:** .</span><span class="sxs-lookup"><span data-stu-id="2a59b-179">When a variable is private, it does not appear in lists of variables, such as those returned by `Get-Variable`, or in displays of the **Variable:** drive.</span></span> <span data-ttu-id="2a59b-180">Comandos para ler ou alterar o valor de uma variável privada retornam um erro.</span><span class="sxs-lookup"><span data-stu-id="2a59b-180">Commands to read or change the value of a private variable return an error.</span></span> <span data-ttu-id="2a59b-181">No entanto, o usuário pode executar comandos que usam uma variável privada se os comandos tiverem sido escritos na sessão em que a variável foi definida.</span><span class="sxs-lookup"><span data-stu-id="2a59b-181">However, the user can run commands that use a private variable if the commands were written in the session in which the variable was defined.</span></span>

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

### <span data-ttu-id="2a59b-182">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2a59b-182">-Confirm</span></span>

<span data-ttu-id="2a59b-183">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2a59b-183">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2a59b-184">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2a59b-184">-WhatIf</span></span>

<span data-ttu-id="2a59b-185">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="2a59b-185">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2a59b-186">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="2a59b-186">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2a59b-187">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2a59b-187">CommonParameters</span></span>

<span data-ttu-id="2a59b-188">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2a59b-188">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2a59b-189">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2a59b-189">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2a59b-190">Entradas</span><span class="sxs-lookup"><span data-stu-id="2a59b-190">Inputs</span></span>

### <span data-ttu-id="2a59b-191">System.Object</span><span class="sxs-lookup"><span data-stu-id="2a59b-191">System.Object</span></span>

<span data-ttu-id="2a59b-192">É possível canalizar um objeto que representa o valor da variável para `Set-Variable` .</span><span class="sxs-lookup"><span data-stu-id="2a59b-192">You can pipe an object that represents the value of the variable to `Set-Variable`.</span></span>

## <span data-ttu-id="2a59b-193">Saídas</span><span class="sxs-lookup"><span data-stu-id="2a59b-193">Outputs</span></span>

### <span data-ttu-id="2a59b-194">Nenhum ou System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="2a59b-194">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="2a59b-195">Quando você usa o parâmetro **PassThru** , o `Set-Variable` gera um objeto **System. Management. Automation. PSVariable** que representa a variável nova ou alterada.</span><span class="sxs-lookup"><span data-stu-id="2a59b-195">When you use the **PassThru** parameter, `Set-Variable` generates a **System.Management.Automation.PSVariable** object representing the new or changed variable.</span></span>
<span data-ttu-id="2a59b-196">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="2a59b-196">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2a59b-197">Observações</span><span class="sxs-lookup"><span data-stu-id="2a59b-197">Notes</span></span>

## <span data-ttu-id="2a59b-198">Links Relacionados</span><span class="sxs-lookup"><span data-stu-id="2a59b-198">Related Links</span></span>

[<span data-ttu-id="2a59b-199">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="2a59b-199">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="2a59b-200">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="2a59b-200">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="2a59b-201">New-Variable</span><span class="sxs-lookup"><span data-stu-id="2a59b-201">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="2a59b-202">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="2a59b-202">Remove-Variable</span></span>](Remove-Variable.md)
