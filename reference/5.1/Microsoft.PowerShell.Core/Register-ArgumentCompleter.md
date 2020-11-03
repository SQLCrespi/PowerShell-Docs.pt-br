---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-argumentcompleter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ArgumentCompleter
ms.openlocfilehash: 1cc6f9f62efc92005c02865ac91cad04164f7655
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193516"
---
# <span data-ttu-id="174ee-103">Register-ArgumentCompleter</span><span class="sxs-lookup"><span data-stu-id="174ee-103">Register-ArgumentCompleter</span></span>

## <span data-ttu-id="174ee-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="174ee-104">SYNOPSIS</span></span>

<span data-ttu-id="174ee-105">Registra um argumento personalizado completo.</span><span class="sxs-lookup"><span data-stu-id="174ee-105">Registers a custom argument completer.</span></span>

## <span data-ttu-id="174ee-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="174ee-106">SYNTAX</span></span>

### <span data-ttu-id="174ee-107">Nativeset</span><span class="sxs-lookup"><span data-stu-id="174ee-107">NativeSet</span></span>

```
Register-ArgumentCompleter -CommandName <String[]> -ScriptBlock <ScriptBlock> [-Native]
 [<CommonParameters>]
```

### <span data-ttu-id="174ee-108">PowerShellset</span><span class="sxs-lookup"><span data-stu-id="174ee-108">PowerShellSet</span></span>

```
Register-ArgumentCompleter [-CommandName <String[]>] -ParameterName <String>
 -ScriptBlock <ScriptBlock> [<CommonParameters>]
```

## <span data-ttu-id="174ee-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="174ee-109">DESCRIPTION</span></span>

<span data-ttu-id="174ee-110">O `Register-ArgumentCompleter` cmdlet registra um argumento personalizado de conclusão.</span><span class="sxs-lookup"><span data-stu-id="174ee-110">The `Register-ArgumentCompleter` cmdlet registers a custom argument completer.</span></span> <span data-ttu-id="174ee-111">Um argumento completo permite que você forneça preenchimento dinâmico de tabulação, em tempo de execução para qualquer comando que você especificar.</span><span class="sxs-lookup"><span data-stu-id="174ee-111">An argument completer allows you to provide dynamic tab completion, at run time for any command that you specify.</span></span>

## <span data-ttu-id="174ee-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="174ee-112">EXAMPLES</span></span>

### <span data-ttu-id="174ee-113">Exemplo 1: registrar um argumento personalizado como completo</span><span class="sxs-lookup"><span data-stu-id="174ee-113">Example 1: Register a custom argument completer</span></span>

<span data-ttu-id="174ee-114">O exemplo a seguir registra um argumento Complete para o parâmetro **ID** do `Set-TimeZone` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="174ee-114">The following example registers an argument completer for the **Id** parameter of the `Set-TimeZone` cmdlet.</span></span>

```powershell
$scriptBlock = {
    param($commandName, $parameterName, $wordToComplete, $commandAst, $fakeBoundParameters)

    (Get-TimeZone -ListAvailable).Id | Where-Object {
        $_ -like "$wordToComplete*"
    } | ForEach-Object {
          "'$_'"
    }
}
Register-ArgumentCompleter -CommandName Set-TimeZone -ParameterName Id -ScriptBlock $scriptBlock
```

<span data-ttu-id="174ee-115">O primeiro comando cria um bloco de script que usa os parâmetros necessários que são passados quando o usuário pressiona a tecla <kbd>Tab</kbd>. Para obter mais informações, consulte a descrição do parâmetro **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="174ee-115">The first command creates a script block which takes the required parameters which are passed in when the user presses <kbd>Tab</kbd>. For more information, see the **ScriptBlock** parameter description.</span></span>

<span data-ttu-id="174ee-116">No bloco de script, os valores disponíveis para **ID** são recuperados usando o `Get-TimeZone` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="174ee-116">Within the script block, the available values for **Id** are retrieved using the `Get-TimeZone` cmdlet.</span></span> <span data-ttu-id="174ee-117">A propriedade **ID** para cada fuso horário é canalizada para o `Where-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="174ee-117">The **Id** property for each Time Zone is piped to the `Where-Object` cmdlet.</span></span> <span data-ttu-id="174ee-118">O `Where-Object` cmdlet filtra todas as IDs que não começam com o valor fornecido pelo `$wordToComplete` , que representa o texto que o usuário digitou antes de pressionar a <kbd>tecla Tab</kbd>. As IDs filtradas são canalizadas para o `For-EachObject` cmdlet que inclui cada valor entre aspas, caso o valor contenha espaços.</span><span class="sxs-lookup"><span data-stu-id="174ee-118">The `Where-Object` cmdlet filters out any ids that do not start with the value provided by `$wordToComplete`, which represents the text the user typed before they pressed <kbd>Tab</kbd>. The filtered ids are piped to the `For-EachObject` cmdlet which encloses each value in quotes, should the value contain spaces.</span></span>

<span data-ttu-id="174ee-119">O segundo comando registra o argumento Complete, passando o scriptblock, a ID **ParameterName** **Id** e o **CommandName** `Set-TimeZone` .</span><span class="sxs-lookup"><span data-stu-id="174ee-119">The second command registers the argument completer by passing the scriptblock, the **ParameterName** **Id** and the **CommandName** `Set-TimeZone`.</span></span>

### <span data-ttu-id="174ee-120">Exemplo 2: adicionar detalhes aos valores de preenchimento de guia</span><span class="sxs-lookup"><span data-stu-id="174ee-120">Example 2: Add details to your tab completion values</span></span>

<span data-ttu-id="174ee-121">O exemplo a seguir substitui a conclusão da Tabulação pelo parâmetro **Name** do `Stop-Service` cmdlet e retorna apenas os serviços em execução.</span><span class="sxs-lookup"><span data-stu-id="174ee-121">The following example overwrites tab completion for the **Name** parameter of the `Stop-Service` cmdlet and only returns running services.</span></span>

```powershell
$s = {
    param($commandName, $parameterName, $wordToComplete, $commandAst, $fakeBoundParameters)
    $services = Get-Service | Where-Object {$_.Status -eq "Running" -and $_.Name -like "$wordToComplete*"}
    $services | ForEach-Object {
        New-Object -Type System.Management.Automation.CompletionResult -ArgumentList $_.Name,
            $_.Name,
            "ParameterValue",
            $_.Name
    }
}
Register-ArgumentCompleter -CommandName Stop-Service -ParameterName Name -ScriptBlock $s
```

<span data-ttu-id="174ee-122">O primeiro comando cria um bloco de script que usa os parâmetros necessários que são passados quando o usuário pressiona a tecla <kbd>Tab</kbd>. Para obter mais informações, consulte a descrição do parâmetro **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="174ee-122">The first command creates a script block which takes the required parameters which are passed in when the user presses <kbd>Tab</kbd>. For more information, see the **ScriptBlock** parameter description.</span></span>

<span data-ttu-id="174ee-123">No bloco de script, o primeiro comando recupera todos os serviços em execução usando o `Where-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="174ee-123">Within the script block, the first command retrieves all running services using the `Where-Object` cmdlet.</span></span> <span data-ttu-id="174ee-124">Os serviços são canalizados para o `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="174ee-124">The services are piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="174ee-125">O `ForEach-Object` cmdlet cria um novo [`[System.Management.Automation.CompletionResult]`](/dotnet/api/system.management.automation.completionresult) objeto e o preenche com os valores do serviço atual (representado pela variável de pipeline `$_` ).</span><span class="sxs-lookup"><span data-stu-id="174ee-125">The `ForEach-Object` cmdlet creates a new [`[System.Management.Automation.CompletionResult]`](/dotnet/api/system.management.automation.completionresult) object and populates it with the values of the current service (represented by the pipeline variable `$_`).</span></span>

<span data-ttu-id="174ee-126">O objeto **CompletionResult** permite que você forneça detalhes adicionais para cada valor retornado:</span><span class="sxs-lookup"><span data-stu-id="174ee-126">The **CompletionResult** object allows you to provide additional details to each returned value:</span></span>

- <span data-ttu-id="174ee-127">**completionText** (cadeia de caracteres)-o texto a ser usado como o resultado da conclusão automática.</span><span class="sxs-lookup"><span data-stu-id="174ee-127">**completionText** (String) - The text to be used as the auto completion result.</span></span> <span data-ttu-id="174ee-128">Esse é o valor enviado para o comando.</span><span class="sxs-lookup"><span data-stu-id="174ee-128">This is the value sent to the command.</span></span>
- <span data-ttu-id="174ee-129">**listItemText** (cadeia de caracteres)-o texto a ser exibido em uma lista, como quando o usuário pressiona <kbd>Ctrl</kbd>o + <kbd>espaço</kbd>Ctrl.</span><span class="sxs-lookup"><span data-stu-id="174ee-129">**listItemText** (String) - The text to be displayed in a list, such as when the user presses <kbd>Ctrl</kbd>+<kbd>Space</kbd>.</span></span> <span data-ttu-id="174ee-130">Isso é usado somente para exibição e não é passado para o comando quando selecionado.</span><span class="sxs-lookup"><span data-stu-id="174ee-130">This is used for display only and is not passed to the command when selected.</span></span>
- <span data-ttu-id="174ee-131">**ResultType** ( [CompletionResultType](/dotnet/api/system.management.automation.completionresulttype)) – o tipo de resultado de conclusão.</span><span class="sxs-lookup"><span data-stu-id="174ee-131">**resultType** ([CompletionResultType](/dotnet/api/system.management.automation.completionresulttype)) - The type of completion result.</span></span>
- <span data-ttu-id="174ee-132">**dica de ferramenta** (cadeia de caracteres)-o texto da dica de ferramenta com detalhes a serem exibidos sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="174ee-132">**toolTip** (String) - The text for the tooltip with details to be displayed about the object.</span></span>
  <span data-ttu-id="174ee-133">Isso fica visível quando o usuário seleciona um item depois de pressionar <kbd>Ctrl</kbd> + <kbd>espaço</kbd>.</span><span class="sxs-lookup"><span data-stu-id="174ee-133">This is visible when the user selects an item after pressing <kbd>Ctrl</kbd>+<kbd>Space</kbd>.</span></span>

<span data-ttu-id="174ee-134">O último comando demonstra que os serviços interrompidos ainda podem ser passados manualmente para o `Stop-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="174ee-134">The last command demonstrates that stopped services can still be passed in manually to the `Stop-Service` cmdlet.</span></span> <span data-ttu-id="174ee-135">O preenchimento com Tab é o único aspecto afetado.</span><span class="sxs-lookup"><span data-stu-id="174ee-135">The tab completion is the only aspect affected.</span></span>

### <span data-ttu-id="174ee-136">Exemplo 3: registrar um argumento nativo personalizado completo</span><span class="sxs-lookup"><span data-stu-id="174ee-136">Example 3: Register a custom Native argument completer</span></span>

<span data-ttu-id="174ee-137">Você pode usar o parâmetro **nativo** para fornecer a conclusão de tabulação para um comando nativo.</span><span class="sxs-lookup"><span data-stu-id="174ee-137">You can use the **Native** parameter to provide tab-completion for a native command.</span></span> <span data-ttu-id="174ee-138">O exemplo a seguir adiciona Tab-Complete para a `dotnet` interface de linha de comando (CLI).</span><span class="sxs-lookup"><span data-stu-id="174ee-138">The following example adds tab-completion for the `dotnet` Command Line Interface (CLI).</span></span>

> [!NOTE]
> <span data-ttu-id="174ee-139">O `dotnet complete` comando só está disponível na versão 2,0 e superior da CLI dotnet.</span><span class="sxs-lookup"><span data-stu-id="174ee-139">The `dotnet complete` command is only available in version 2.0 and greater of the dotnet cli.</span></span>

```powershell
$scriptblock = {
    param($wordToComplete, $commandAst, $cursorPosition)
        dotnet complete --position $cursorPosition $commandAst.ToString() | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
        }
}
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock $scriptblock
```

<span data-ttu-id="174ee-140">O primeiro comando cria um bloco de script que usa os parâmetros necessários que são passados quando o usuário pressiona a tecla <kbd>Tab</kbd>. Para obter mais informações, consulte a descrição do parâmetro **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="174ee-140">The first command creates a script block which takes the required parameters which are passed in when the user presses <kbd>Tab</kbd>. For more information, see the **ScriptBlock** parameter description.</span></span>

<span data-ttu-id="174ee-141">No bloco de script, o `dotnet complete` comando é usado para executar a conclusão da Tabulação.</span><span class="sxs-lookup"><span data-stu-id="174ee-141">Within the script block, the `dotnet complete` command is used to perform the tab completion.</span></span>
<span data-ttu-id="174ee-142">Os resultados são canalizados para o `ForEach-Object` cmdlet que usa o **novo** método estático da classe [System. Management. Automation. CompletionResult](/dotnet/api/system.management.automation.completionresult) para criar um novo objeto **CompletionResult** para cada valor.</span><span class="sxs-lookup"><span data-stu-id="174ee-142">The results are piped to the `ForEach-Object` cmdlet which use the **new** static method of the [System.Management.Automation.CompletionResult](/dotnet/api/system.management.automation.completionresult) class to create a new **CompletionResult** object for each value.</span></span>

## <span data-ttu-id="174ee-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="174ee-143">PARAMETERS</span></span>

### <span data-ttu-id="174ee-144">-CommandName</span><span class="sxs-lookup"><span data-stu-id="174ee-144">-CommandName</span></span>

<span data-ttu-id="174ee-145">Especifica o nome dos comandos como uma matriz.</span><span class="sxs-lookup"><span data-stu-id="174ee-145">Specifies the name of the commands as an array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NativeSet, PowerShellSet
Aliases:

Required: True (NativeSet), False (PowerShellSet)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="174ee-146">-Nativo</span><span class="sxs-lookup"><span data-stu-id="174ee-146">-Native</span></span>

<span data-ttu-id="174ee-147">Indica que o argumento completo é para um comando nativo em que o PowerShell não pode concluir nomes de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="174ee-147">Indicates that the argument completer is for a native command where PowerShell cannot complete parameter names.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NativeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="174ee-148">-ParameterName</span><span class="sxs-lookup"><span data-stu-id="174ee-148">-ParameterName</span></span>

<span data-ttu-id="174ee-149">Especifica o nome do parâmetro cujo argumento está sendo concluído.</span><span class="sxs-lookup"><span data-stu-id="174ee-149">Specifies the name of the parameter whose argument is being completed.</span></span> <span data-ttu-id="174ee-150">O nome do parâmetro especificado não pode ser um valor enumerado, como o parâmetro **ForegroundColor** do `Write-Host` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="174ee-150">The parameter name specified cannot be an enumerated value, such as the **ForegroundColor** parameter of the `Write-Host` cmdlet.</span></span>

<span data-ttu-id="174ee-151">Para obter mais informações sobre enums, consulte [about_Enum](./About/about_Enum.md).</span><span class="sxs-lookup"><span data-stu-id="174ee-151">For more information on enums, see [about_Enum](./About/about_Enum.md).</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="174ee-152">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="174ee-152">-ScriptBlock</span></span>

<span data-ttu-id="174ee-153">Especifica os comandos a serem executados para executar a conclusão da Tabulação.</span><span class="sxs-lookup"><span data-stu-id="174ee-153">Specifies the commands to run to perform tab completion.</span></span> <span data-ttu-id="174ee-154">O bloco de script que você fornece deve retornar os valores que concluem a entrada.</span><span class="sxs-lookup"><span data-stu-id="174ee-154">The script block you provide should return the values that complete the input.</span></span> <span data-ttu-id="174ee-155">O bloco de script deve desdistribuir os valores usando o pipeline ( `ForEach-Object` , `Where-Object` , etc.) ou outro método adequado.</span><span class="sxs-lookup"><span data-stu-id="174ee-155">The script block must unroll the values using the pipeline (`ForEach-Object`, `Where-Object`, etc.), or another suitable method.</span></span> <span data-ttu-id="174ee-156">Retornar uma matriz de valores faz com que o PowerShell trate toda a matriz como **um** valor de conclusão de tabulação.</span><span class="sxs-lookup"><span data-stu-id="174ee-156">Returning an array of values causes PowerShell to treat the entire array as **one** tab completion value.</span></span>

<span data-ttu-id="174ee-157">O bloco de script deve aceitar os seguintes parâmetros na ordem especificada abaixo.</span><span class="sxs-lookup"><span data-stu-id="174ee-157">The script block must accept the following parameters in the order specified below.</span></span> <span data-ttu-id="174ee-158">Os nomes dos parâmetros não são importantes porque o PowerShell passa os valores por posição.</span><span class="sxs-lookup"><span data-stu-id="174ee-158">The names of the parameters aren't important because PowerShell passes in the values by position.</span></span>

- <span data-ttu-id="174ee-159">`$commandName` (Posição 0)-esse parâmetro é definido como o nome do comando para o qual o bloco de script está fornecendo preenchimento com Tab.</span><span class="sxs-lookup"><span data-stu-id="174ee-159">`$commandName` (Position 0) - This parameter is set to the name of the command for which the script block is providing tab completion.</span></span>
- <span data-ttu-id="174ee-160">`$parameterName` (Posição 1)-esse parâmetro é definido como o parâmetro cujo valor requer preenchimento com Tab.</span><span class="sxs-lookup"><span data-stu-id="174ee-160">`$parameterName` (Position 1) - This parameter is set to the parameter whose value requires tab completion.</span></span>
- <span data-ttu-id="174ee-161">`$wordToComplete` (Posição 2)-esse parâmetro é definido como o valor que o usuário forneceu antes de pressionar a <kbd>tecla Tab</kbd>. O bloco de script deve usar esse valor para determinar valores de preenchimento de guia.</span><span class="sxs-lookup"><span data-stu-id="174ee-161">`$wordToComplete` (Position 2) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="174ee-162">`$commandAst` (Posição 3)-esse parâmetro é definido como a árvore de sintaxe abstrata (AST) para a linha de entrada atual.</span><span class="sxs-lookup"><span data-stu-id="174ee-162">`$commandAst` (Position 3) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="174ee-163">Para obter mais informações, consulte [AST Class](/dotnet/api/system.management.automation.language.ast).</span><span class="sxs-lookup"><span data-stu-id="174ee-163">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="174ee-164">`$fakeBoundParameters` (Posição 4)-esse parâmetro é definido como uma tabela de hash que contém o `$PSBoundParameters` para o cmdlet, antes da <kbd>guia</kbd>ser pressionada pelo usuário. Para obter mais informações, consulte [about_Automatic_Variables](./About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="174ee-164">`$fakeBoundParameters` (Position 4) - This parameter is set to a hashtable containing the `$PSBoundParameters` for the cmdlet, before the user pressed <kbd>Tab</kbd>. For more information, see [about_Automatic_Variables](./About/about_Automatic_Variables.md).</span></span>

<span data-ttu-id="174ee-165">Quando você especifica o parâmetro **nativo** , o bloco de script deve usar os seguintes parâmetros na ordem especificada.</span><span class="sxs-lookup"><span data-stu-id="174ee-165">When you specify the **Native** parameter, the script block must take the following parameters in the specified order.</span></span> <span data-ttu-id="174ee-166">Os nomes dos parâmetros não são importantes porque o PowerShell passa os valores por posição.</span><span class="sxs-lookup"><span data-stu-id="174ee-166">The names of the parameters aren't important because PowerShell passes in the values by position.</span></span>

- <span data-ttu-id="174ee-167">`$wordToComplete` (Posição 0)-esse parâmetro é definido como o valor que o usuário forneceu antes de pressionar a <kbd>tecla Tab</kbd>. O bloco de script deve usar esse valor para determinar valores de preenchimento de guia.</span><span class="sxs-lookup"><span data-stu-id="174ee-167">`$wordToComplete` (Position 0) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="174ee-168">`$commandAst` (Posição 1)-esse parâmetro é definido como a árvore de sintaxe abstrata (AST) para a linha de entrada atual.</span><span class="sxs-lookup"><span data-stu-id="174ee-168">`$commandAst` (Position 1) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="174ee-169">Para obter mais informações, consulte [AST Class](/dotnet/api/system.management.automation.language.ast).</span><span class="sxs-lookup"><span data-stu-id="174ee-169">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="174ee-170">`$cursorPosition` (Posição 2)-esse parâmetro é definido como a posição do cursor quando a <kbd>guia</kbd>do usuário é pressionada.</span><span class="sxs-lookup"><span data-stu-id="174ee-170">`$cursorPosition` (Position 2) - This parameter is set to the position of the cursor when the user pressed <kbd>Tab</kbd>.</span></span>

<span data-ttu-id="174ee-171">Você também pode fornecer um **ArgumentCompleter** como um atributo de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="174ee-171">You can also provide an **ArgumentCompleter** as a parameter attribute.</span></span> <span data-ttu-id="174ee-172">Para obter mais informações, consulte [about_Functions_Advanced_Parameters](./About/about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="174ee-172">For more information, see [about_Functions_Advanced_Parameters](./About/about_Functions_Advanced_Parameters.md).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="174ee-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="174ee-173">CommonParameters</span></span>

<span data-ttu-id="174ee-174">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="174ee-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="174ee-175">Para obter mais informações, confira [about_CommonParameters](./About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="174ee-175">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="174ee-176">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="174ee-176">INPUTS</span></span>

### <span data-ttu-id="174ee-177">Nenhum</span><span class="sxs-lookup"><span data-stu-id="174ee-177">None</span></span>

<span data-ttu-id="174ee-178">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="174ee-178">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="174ee-179">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="174ee-179">OUTPUTS</span></span>

### <span data-ttu-id="174ee-180">Nenhum</span><span class="sxs-lookup"><span data-stu-id="174ee-180">None</span></span>

<span data-ttu-id="174ee-181">Esse cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="174ee-181">This cmdlet returns no output.</span></span>

## <span data-ttu-id="174ee-182">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="174ee-182">NOTES</span></span>

## <span data-ttu-id="174ee-183">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="174ee-183">RELATED LINKS</span></span>
