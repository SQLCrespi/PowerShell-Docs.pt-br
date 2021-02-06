---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-argumentcompleter?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ArgumentCompleter
ms.openlocfilehash: e98de608630a59ff77ca701876986ffb29780a4a
ms.sourcegitcommit: 9a86cac80402d8193147058d4ba50e07b26059dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "99597009"
---
# <span data-ttu-id="90587-102">Register-ArgumentCompleter</span><span class="sxs-lookup"><span data-stu-id="90587-102">Register-ArgumentCompleter</span></span>

## <span data-ttu-id="90587-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="90587-103">SYNOPSIS</span></span>

<span data-ttu-id="90587-104">Registra um argumento personalizado completo.</span><span class="sxs-lookup"><span data-stu-id="90587-104">Registers a custom argument completer.</span></span>

## <span data-ttu-id="90587-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="90587-105">SYNTAX</span></span>

### <span data-ttu-id="90587-106">Nativeset</span><span class="sxs-lookup"><span data-stu-id="90587-106">NativeSet</span></span>

```
Register-ArgumentCompleter -CommandName <String[]> -ScriptBlock <ScriptBlock> [-Native]
 [<CommonParameters>]
```

### <span data-ttu-id="90587-107">PowerShellset</span><span class="sxs-lookup"><span data-stu-id="90587-107">PowerShellSet</span></span>

```
Register-ArgumentCompleter [-CommandName <String[]>] -ParameterName <String>
 -ScriptBlock <ScriptBlock> [<CommonParameters>]
```

## <span data-ttu-id="90587-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="90587-108">DESCRIPTION</span></span>

<span data-ttu-id="90587-109">O `Register-ArgumentCompleter` cmdlet registra um argumento personalizado de conclusão.</span><span class="sxs-lookup"><span data-stu-id="90587-109">The `Register-ArgumentCompleter` cmdlet registers a custom argument completer.</span></span> <span data-ttu-id="90587-110">Um argumento completo permite que você forneça preenchimento dinâmico de tabulação, em tempo de execução para qualquer comando que você especificar.</span><span class="sxs-lookup"><span data-stu-id="90587-110">An argument completer allows you to provide dynamic tab completion, at run time for any command that you specify.</span></span>

## <span data-ttu-id="90587-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="90587-111">EXAMPLES</span></span>

### <span data-ttu-id="90587-112">Exemplo 1: registrar um argumento personalizado como completo</span><span class="sxs-lookup"><span data-stu-id="90587-112">Example 1: Register a custom argument completer</span></span>

<span data-ttu-id="90587-113">O exemplo a seguir registra um argumento Complete para o parâmetro **ID** do `Set-TimeZone` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="90587-113">The following example registers an argument completer for the **Id** parameter of the `Set-TimeZone` cmdlet.</span></span>

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

<span data-ttu-id="90587-114">O primeiro comando cria um bloco de script que usa os parâmetros necessários que são passados quando o usuário pressiona a tecla <kbd>Tab</kbd>. Para obter mais informações, consulte a descrição do parâmetro **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="90587-114">The first command creates a script block which takes the required parameters which are passed in when the user presses <kbd>Tab</kbd>. For more information, see the **ScriptBlock** parameter description.</span></span>

<span data-ttu-id="90587-115">No bloco de script, os valores disponíveis para **ID** são recuperados usando o `Get-TimeZone` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="90587-115">Within the script block, the available values for **Id** are retrieved using the `Get-TimeZone` cmdlet.</span></span> <span data-ttu-id="90587-116">A propriedade **ID** para cada fuso horário é canalizada para o `Where-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="90587-116">The **Id** property for each Time Zone is piped to the `Where-Object` cmdlet.</span></span> <span data-ttu-id="90587-117">O `Where-Object` cmdlet filtra todas as IDs que não começam com o valor fornecido pelo `$wordToComplete` , que representa o texto que o usuário digitou antes de pressionar a <kbd>tecla Tab</kbd>. As IDs filtradas são canalizadas para o `ForEach-Object` cmdlet que inclui cada valor entre aspas, caso o valor contenha espaços.</span><span class="sxs-lookup"><span data-stu-id="90587-117">The `Where-Object` cmdlet filters out any ids that do not start with the value provided by `$wordToComplete`, which represents the text the user typed before they pressed <kbd>Tab</kbd>. The filtered ids are piped to the `ForEach-Object` cmdlet which encloses each value in quotes, should the value contain spaces.</span></span>

<span data-ttu-id="90587-118">O segundo comando registra o argumento Complete, passando o scriptblock, a ID **ParameterName**  e o **CommandName** `Set-TimeZone` .</span><span class="sxs-lookup"><span data-stu-id="90587-118">The second command registers the argument completer by passing the scriptblock, the **ParameterName** **Id** and the **CommandName** `Set-TimeZone`.</span></span>

### <span data-ttu-id="90587-119">Exemplo 2: adicionar detalhes aos valores de preenchimento de guia</span><span class="sxs-lookup"><span data-stu-id="90587-119">Example 2: Add details to your tab completion values</span></span>

<span data-ttu-id="90587-120">O exemplo a seguir substitui a conclusão da Tabulação pelo parâmetro **Name** do `Stop-Service` cmdlet e retorna apenas os serviços em execução.</span><span class="sxs-lookup"><span data-stu-id="90587-120">The following example overwrites tab completion for the **Name** parameter of the `Stop-Service` cmdlet and only returns running services.</span></span>

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

<span data-ttu-id="90587-121">O primeiro comando cria um bloco de script que usa os parâmetros necessários que são passados quando o usuário pressiona a tecla <kbd>Tab</kbd>. Para obter mais informações, consulte a descrição do parâmetro **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="90587-121">The first command creates a script block which takes the required parameters which are passed in when the user presses <kbd>Tab</kbd>. For more information, see the **ScriptBlock** parameter description.</span></span>

<span data-ttu-id="90587-122">No bloco de script, o primeiro comando recupera todos os serviços em execução usando o `Where-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="90587-122">Within the script block, the first command retrieves all running services using the `Where-Object` cmdlet.</span></span> <span data-ttu-id="90587-123">Os serviços são canalizados para o `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="90587-123">The services are piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="90587-124">O `ForEach-Object` cmdlet cria um novo objeto [System. Management. Automation. CompletionResult](/dotnet/api/system.management.automation.completionresult) e o popula com o nome do serviço atual (representado pela variável de pipeline `$_.Name` ).</span><span class="sxs-lookup"><span data-stu-id="90587-124">The `ForEach-Object` cmdlet creates a new [System.Management.Automation.CompletionResult](/dotnet/api/system.management.automation.completionresult) object and populates it with the name of the current service (represented by the pipeline variable `$_.Name`).</span></span>

<span data-ttu-id="90587-125">O objeto **CompletionResult** permite que você forneça detalhes adicionais para cada valor retornado:</span><span class="sxs-lookup"><span data-stu-id="90587-125">The **CompletionResult** object allows you to provide additional details to each returned value:</span></span>

- <span data-ttu-id="90587-126">**completionText** (cadeia de caracteres)-o texto a ser usado como o resultado da conclusão automática.</span><span class="sxs-lookup"><span data-stu-id="90587-126">**completionText** (String) - The text to be used as the auto completion result.</span></span> <span data-ttu-id="90587-127">Esse é o valor enviado para o comando.</span><span class="sxs-lookup"><span data-stu-id="90587-127">This is the value sent to the command.</span></span>
- <span data-ttu-id="90587-128">**listItemText** (cadeia de caracteres)-o texto a ser exibido em uma lista, como quando o usuário pressiona <kbd></kbd>o + <kbd>espaço</kbd>Ctrl.</span><span class="sxs-lookup"><span data-stu-id="90587-128">**listItemText** (String) - The text to be displayed in a list, such as when the user presses <kbd>Ctrl</kbd>+<kbd>Space</kbd>.</span></span> <span data-ttu-id="90587-129">Isso é usado somente para exibição e não é passado para o comando quando selecionado.</span><span class="sxs-lookup"><span data-stu-id="90587-129">This is used for display only and is not passed to the command when selected.</span></span>
- <span data-ttu-id="90587-130">**ResultType** ([CompletionResultType](/dotnet/api/system.management.automation.completionresulttype)) – o tipo de resultado de conclusão.</span><span class="sxs-lookup"><span data-stu-id="90587-130">**resultType** ([CompletionResultType](/dotnet/api/system.management.automation.completionresulttype)) - The type of completion result.</span></span>
- <span data-ttu-id="90587-131">**dica de ferramenta** (cadeia de caracteres)-o texto da dica de ferramenta com detalhes a serem exibidos sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="90587-131">**toolTip** (String) - The text for the tooltip with details to be displayed about the object.</span></span>
  <span data-ttu-id="90587-132">Isso fica visível quando o usuário seleciona um item depois de pressionar <kbd>Ctrl</kbd> + <kbd>espaço</kbd>.</span><span class="sxs-lookup"><span data-stu-id="90587-132">This is visible when the user selects an item after pressing <kbd>Ctrl</kbd>+<kbd>Space</kbd>.</span></span>

<span data-ttu-id="90587-133">O último comando demonstra que os serviços interrompidos ainda podem ser passados manualmente para o `Stop-Service` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="90587-133">The last command demonstrates that stopped services can still be passed in manually to the `Stop-Service` cmdlet.</span></span> <span data-ttu-id="90587-134">O preenchimento com Tab é o único aspecto afetado.</span><span class="sxs-lookup"><span data-stu-id="90587-134">The tab completion is the only aspect affected.</span></span>

### <span data-ttu-id="90587-135">Exemplo 3: registrar um argumento nativo personalizado completo</span><span class="sxs-lookup"><span data-stu-id="90587-135">Example 3: Register a custom Native argument completer</span></span>

<span data-ttu-id="90587-136">Você pode usar o parâmetro **nativo** para fornecer a conclusão de tabulação para um comando nativo.</span><span class="sxs-lookup"><span data-stu-id="90587-136">You can use the **Native** parameter to provide tab-completion for a native command.</span></span> <span data-ttu-id="90587-137">O exemplo a seguir adiciona Tab-Complete para a `dotnet` interface de linha de comando (CLI).</span><span class="sxs-lookup"><span data-stu-id="90587-137">The following example adds tab-completion for the `dotnet` Command Line Interface (CLI).</span></span>

> [!NOTE]
> <span data-ttu-id="90587-138">O `dotnet complete` comando só está disponível na versão 2,0 e superior da CLI dotnet.</span><span class="sxs-lookup"><span data-stu-id="90587-138">The `dotnet complete` command is only available in version 2.0 and greater of the dotnet cli.</span></span>

```powershell
$scriptblock = {
    param($wordToComplete, $commandAst, $cursorPosition)
        dotnet complete --position $cursorPosition $commandAst.ToString() | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
        }
}
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock $scriptblock
```

<span data-ttu-id="90587-139">O primeiro comando cria um bloco de script que usa os parâmetros necessários que são passados quando o usuário pressiona a tecla <kbd>Tab</kbd>. Para obter mais informações, consulte a descrição do parâmetro **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="90587-139">The first command creates a script block which takes the required parameters which are passed in when the user presses <kbd>Tab</kbd>. For more information, see the **ScriptBlock** parameter description.</span></span>

<span data-ttu-id="90587-140">No bloco de script, o `dotnet complete` comando é usado para executar a conclusão da Tabulação.</span><span class="sxs-lookup"><span data-stu-id="90587-140">Within the script block, the `dotnet complete` command is used to perform the tab completion.</span></span>
<span data-ttu-id="90587-141">Os resultados são canalizados para o `ForEach-Object` cmdlet que usa o **novo** método estático da classe [System. Management. Automation. CompletionResult](/dotnet/api/system.management.automation.completionresult) para criar um novo objeto **CompletionResult** para cada valor.</span><span class="sxs-lookup"><span data-stu-id="90587-141">The results are piped to the `ForEach-Object` cmdlet which use the **new** static method of the [System.Management.Automation.CompletionResult](/dotnet/api/system.management.automation.completionresult) class to create a new **CompletionResult** object for each value.</span></span>

## <span data-ttu-id="90587-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="90587-142">PARAMETERS</span></span>

### <span data-ttu-id="90587-143">-CommandName</span><span class="sxs-lookup"><span data-stu-id="90587-143">-CommandName</span></span>

<span data-ttu-id="90587-144">Especifica o nome dos comandos como uma matriz.</span><span class="sxs-lookup"><span data-stu-id="90587-144">Specifies the name of the commands as an array.</span></span>

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

### <span data-ttu-id="90587-145">-Nativo</span><span class="sxs-lookup"><span data-stu-id="90587-145">-Native</span></span>

<span data-ttu-id="90587-146">Indica que o argumento completo é para um comando nativo em que o PowerShell não pode concluir nomes de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="90587-146">Indicates that the argument completer is for a native command where PowerShell cannot complete parameter names.</span></span>

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

### <span data-ttu-id="90587-147">-ParameterName</span><span class="sxs-lookup"><span data-stu-id="90587-147">-ParameterName</span></span>

<span data-ttu-id="90587-148">Especifica o nome do parâmetro cujo argumento está sendo concluído.</span><span class="sxs-lookup"><span data-stu-id="90587-148">Specifies the name of the parameter whose argument is being completed.</span></span> <span data-ttu-id="90587-149">O nome do parâmetro especificado não pode ser um valor enumerado, como o parâmetro **ForegroundColor** do `Write-Host` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="90587-149">The parameter name specified cannot be an enumerated value, such as the **ForegroundColor** parameter of the `Write-Host` cmdlet.</span></span>

<span data-ttu-id="90587-150">Para obter mais informações sobre enums, consulte [about_Enum](./About/about_Enum.md).</span><span class="sxs-lookup"><span data-stu-id="90587-150">For more information on enums, see [about_Enum](./About/about_Enum.md).</span></span>

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

### <span data-ttu-id="90587-151">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="90587-151">-ScriptBlock</span></span>

<span data-ttu-id="90587-152">Especifica os comandos a serem executados para executar a conclusão da Tabulação.</span><span class="sxs-lookup"><span data-stu-id="90587-152">Specifies the commands to run to perform tab completion.</span></span> <span data-ttu-id="90587-153">O bloco de script que você fornece deve retornar os valores que concluem a entrada.</span><span class="sxs-lookup"><span data-stu-id="90587-153">The script block you provide should return the values that complete the input.</span></span> <span data-ttu-id="90587-154">O bloco de script deve desdistribuir os valores usando o pipeline ( `ForEach-Object` , `Where-Object` , etc.) ou outro método adequado.</span><span class="sxs-lookup"><span data-stu-id="90587-154">The script block must unroll the values using the pipeline (`ForEach-Object`, `Where-Object`, etc.), or another suitable method.</span></span> <span data-ttu-id="90587-155">Retornar uma matriz de valores faz com que o PowerShell trate toda a matriz como **um** valor de conclusão de tabulação.</span><span class="sxs-lookup"><span data-stu-id="90587-155">Returning an array of values causes PowerShell to treat the entire array as **one** tab completion value.</span></span>

<span data-ttu-id="90587-156">O bloco de script deve aceitar os seguintes parâmetros na ordem especificada abaixo.</span><span class="sxs-lookup"><span data-stu-id="90587-156">The script block must accept the following parameters in the order specified below.</span></span> <span data-ttu-id="90587-157">Os nomes dos parâmetros não são importantes porque o PowerShell passa os valores por posição.</span><span class="sxs-lookup"><span data-stu-id="90587-157">The names of the parameters aren't important because PowerShell passes in the values by position.</span></span>

- <span data-ttu-id="90587-158">`$commandName` (Posição 0)-esse parâmetro é definido como o nome do comando para o qual o bloco de script está fornecendo preenchimento com Tab.</span><span class="sxs-lookup"><span data-stu-id="90587-158">`$commandName` (Position 0) - This parameter is set to the name of the command for which the script block is providing tab completion.</span></span>
- <span data-ttu-id="90587-159">`$parameterName` (Posição 1)-esse parâmetro é definido como o parâmetro cujo valor requer preenchimento com Tab.</span><span class="sxs-lookup"><span data-stu-id="90587-159">`$parameterName` (Position 1) - This parameter is set to the parameter whose value requires tab completion.</span></span>
- <span data-ttu-id="90587-160">`$wordToComplete` (Posição 2)-esse parâmetro é definido como o valor que o usuário forneceu antes de pressionar a <kbd>tecla Tab</kbd>. O bloco de script deve usar esse valor para determinar valores de preenchimento de guia.</span><span class="sxs-lookup"><span data-stu-id="90587-160">`$wordToComplete` (Position 2) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="90587-161">`$commandAst` (Posição 3)-esse parâmetro é definido como a árvore de sintaxe abstrata (AST) para a linha de entrada atual.</span><span class="sxs-lookup"><span data-stu-id="90587-161">`$commandAst` (Position 3) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="90587-162">Para obter mais informações, consulte [AST Class](/dotnet/api/system.management.automation.language.ast).</span><span class="sxs-lookup"><span data-stu-id="90587-162">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="90587-163">`$fakeBoundParameters` (Posição 4)-esse parâmetro é definido como uma tabela de hash que contém o `$PSBoundParameters` para o cmdlet, antes da <kbd>guia</kbd>ser pressionada pelo usuário. Para obter mais informações, consulte [about_Automatic_Variables](./About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="90587-163">`$fakeBoundParameters` (Position 4) - This parameter is set to a hashtable containing the `$PSBoundParameters` for the cmdlet, before the user pressed <kbd>Tab</kbd>. For more information, see [about_Automatic_Variables](./About/about_Automatic_Variables.md).</span></span>

<span data-ttu-id="90587-164">Quando você especifica o parâmetro **nativo** , o bloco de script deve usar os seguintes parâmetros na ordem especificada.</span><span class="sxs-lookup"><span data-stu-id="90587-164">When you specify the **Native** parameter, the script block must take the following parameters in the specified order.</span></span> <span data-ttu-id="90587-165">Os nomes dos parâmetros não são importantes porque o PowerShell passa os valores por posição.</span><span class="sxs-lookup"><span data-stu-id="90587-165">The names of the parameters aren't important because PowerShell passes in the values by position.</span></span>

- <span data-ttu-id="90587-166">`$wordToComplete` (Posição 0)-esse parâmetro é definido como o valor que o usuário forneceu antes de pressionar a <kbd>tecla Tab</kbd>. O bloco de script deve usar esse valor para determinar valores de preenchimento de guia.</span><span class="sxs-lookup"><span data-stu-id="90587-166">`$wordToComplete` (Position 0) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="90587-167">`$commandAst` (Posição 1)-esse parâmetro é definido como a árvore de sintaxe abstrata (AST) para a linha de entrada atual.</span><span class="sxs-lookup"><span data-stu-id="90587-167">`$commandAst` (Position 1) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="90587-168">Para obter mais informações, consulte [AST Class](/dotnet/api/system.management.automation.language.ast).</span><span class="sxs-lookup"><span data-stu-id="90587-168">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="90587-169">`$cursorPosition` (Posição 2)-esse parâmetro é definido como a posição do cursor quando a <kbd>guia</kbd>do usuário é pressionada.</span><span class="sxs-lookup"><span data-stu-id="90587-169">`$cursorPosition` (Position 2) - This parameter is set to the position of the cursor when the user pressed <kbd>Tab</kbd>.</span></span>

<span data-ttu-id="90587-170">Você também pode fornecer um **ArgumentCompleter** como um atributo de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="90587-170">You can also provide an **ArgumentCompleter** as a parameter attribute.</span></span> <span data-ttu-id="90587-171">Para obter mais informações, consulte [about_Functions_Advanced_Parameters](./About/about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="90587-171">For more information, see [about_Functions_Advanced_Parameters](./About/about_Functions_Advanced_Parameters.md).</span></span>

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

### <span data-ttu-id="90587-172">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="90587-172">CommonParameters</span></span>

<span data-ttu-id="90587-173">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="90587-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="90587-174">Para obter mais informações, confira [about_CommonParameters](./About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="90587-174">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="90587-175">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="90587-175">INPUTS</span></span>

### <span data-ttu-id="90587-176">Nenhum</span><span class="sxs-lookup"><span data-stu-id="90587-176">None</span></span>

<span data-ttu-id="90587-177">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="90587-177">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="90587-178">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="90587-178">OUTPUTS</span></span>

### <span data-ttu-id="90587-179">Nenhum</span><span class="sxs-lookup"><span data-stu-id="90587-179">None</span></span>

<span data-ttu-id="90587-180">Esse cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="90587-180">This cmdlet returns no output.</span></span>

## <span data-ttu-id="90587-181">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="90587-181">NOTES</span></span>

## <span data-ttu-id="90587-182">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="90587-182">RELATED LINKS</span></span>

