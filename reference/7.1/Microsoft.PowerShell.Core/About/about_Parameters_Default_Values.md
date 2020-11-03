---
description: Descreve como definir valores padrão personalizados para parâmetros de cmdlet e funções avançadas.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 5/31/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters_default_values?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters_Default_Values
ms.openlocfilehash: c16af49308df26fc51f57c9bd176ad2fd5537e2c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195924"
---
# <a name="about-parameters-default-values"></a><span data-ttu-id="95807-104">Sobre valores padrão de parâmetros</span><span class="sxs-lookup"><span data-stu-id="95807-104">About Parameters Default Values</span></span>

## <a name="short-description"></a><span data-ttu-id="95807-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="95807-105">Short description</span></span>

<span data-ttu-id="95807-106">Descreve como definir valores padrão personalizados para parâmetros de cmdlet e funções avançadas.</span><span class="sxs-lookup"><span data-stu-id="95807-106">Describes how to set custom default values for cmdlet parameters and advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="95807-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="95807-107">Long description</span></span>

<span data-ttu-id="95807-108">A `$PSDefaultParameterValues` variável de preferência permite especificar valores padrão personalizados para qualquer cmdlet ou função avançada.</span><span class="sxs-lookup"><span data-stu-id="95807-108">The `$PSDefaultParameterValues` preference variable lets you specify custom default values for any cmdlet or advanced function.</span></span> <span data-ttu-id="95807-109">Os cmdlets e as funções avançadas usam o valor padrão personalizado, a menos que você especifique outro valor no comando.</span><span class="sxs-lookup"><span data-stu-id="95807-109">Cmdlets and advanced functions use the custom default value unless you specify another value in the command.</span></span>

<span data-ttu-id="95807-110">Os autores de cmdlets e funções avançadas definem valores padrão para seus parâmetros.</span><span class="sxs-lookup"><span data-stu-id="95807-110">The authors of cmdlets and advanced functions set standard default values for their parameters.</span></span> <span data-ttu-id="95807-111">Normalmente, os valores padrão são úteis, mas eles podem não ser apropriados para todos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="95807-111">Typically, the standard default values are useful, but they might not be appropriate for all environments.</span></span>

<span data-ttu-id="95807-112">Esse recurso é especialmente útil quando você deve especificar o mesmo valor de parâmetro alternativo quase sempre que usar o comando ou quando um valor de parâmetro específico for difícil de lembrar, como um nome de servidor de email ou GUID de projeto.</span><span class="sxs-lookup"><span data-stu-id="95807-112">This feature is especially useful when you must specify the same alternate parameter value nearly every time you use the command or when a particular parameter value is difficult to remember, such as an email server name or project GUID.</span></span>

<span data-ttu-id="95807-113">Se o valor padrão desejado variar de forma previsível, você poderá especificar um bloco de script que forneça valores padrão diferentes para um parâmetro sob condições diferentes.</span><span class="sxs-lookup"><span data-stu-id="95807-113">If the desired default value varies predictably, you can specify a script block that provides different default values for a parameter under different conditions.</span></span>

<span data-ttu-id="95807-114">`$PSDefaultParameterValues` foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="95807-114">`$PSDefaultParameterValues` was introduced in PowerShell 3.0.</span></span>

## <a name="syntax"></a><span data-ttu-id="95807-115">Syntax</span><span class="sxs-lookup"><span data-stu-id="95807-115">Syntax</span></span>

<span data-ttu-id="95807-116">A `$PSDefaultParameterValues` variável é uma tabela de hash que valida o formato das chaves como um tipo de objeto de **System. Management. Automation. DefaultParameterDictionary** .</span><span class="sxs-lookup"><span data-stu-id="95807-116">The `$PSDefaultParameterValues` variable is a hash table that validates the format of keys as an object type of **System.Management.Automation.DefaultParameterDictionary** .</span></span> <span data-ttu-id="95807-117">A tabela de hash contém pares de **chave/valor** .</span><span class="sxs-lookup"><span data-stu-id="95807-117">The hash table contains **Key/Value** pairs.</span></span> <span data-ttu-id="95807-118">Uma **chave** está no formato `CmdletName:ParameterName` .</span><span class="sxs-lookup"><span data-stu-id="95807-118">A **Key** is in the format `CmdletName:ParameterName`.</span></span> <span data-ttu-id="95807-119">Um **valor** é o **DefaultValue** ou **scriptblock** atribuído à chave.</span><span class="sxs-lookup"><span data-stu-id="95807-119">A **Value** is the **DefaultValue** or **ScriptBlock** assigned to the key.</span></span>

<span data-ttu-id="95807-120">A sintaxe da `$PSDefaultParameterValues` variável de preferência é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="95807-120">The syntax of the `$PSDefaultParameterValues` preference variable is as follows:</span></span>

```
$PSDefaultParameterValues=@{"CmdletName:ParameterName"="DefaultValue"}

$PSDefaultParameterValues=@{ "CmdletName:ParameterName"={{ScriptBlock}} }

$PSDefaultParameterValues["Disabled"]=$True | $False
```

<span data-ttu-id="95807-121">Caracteres curinga são permitidos nos valores **CmdletName** e **ParameterName** .</span><span class="sxs-lookup"><span data-stu-id="95807-121">Wildcard characters are permitted in the **CmdletName** and **ParameterName** values.</span></span>

<span data-ttu-id="95807-122">Para definir, alterar, adicionar ou remover um par de **chave/valor** específico de `$PSDefaultParameterValues` , use os métodos para editar uma tabela de hash padrão.</span><span class="sxs-lookup"><span data-stu-id="95807-122">To set, change, add, or remove a specific **Key/Value** pair from `$PSDefaultParameterValues`, use the methods to edit a standard hash table.</span></span> <span data-ttu-id="95807-123">Por exemplo, os métodos **Add** e **Remove** .</span><span class="sxs-lookup"><span data-stu-id="95807-123">For example, the **Add** and **Remove** methods.</span></span> <span data-ttu-id="95807-124">Esses métodos não substituem outros valores na tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="95807-124">These methods don't overwrite other values in the hash table.</span></span>

<span data-ttu-id="95807-125">Há outra sintaxe que não substitui uma tabela de `$PSDefaultParameterValues` hash existente.</span><span class="sxs-lookup"><span data-stu-id="95807-125">There's another syntax that doesn't overwrite an existing `$PSDefaultParameterValues` hash table.</span></span> <span data-ttu-id="95807-126">Para adicionar ou alterar um par de **chave/valor** específico, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="95807-126">To add or change a specific **Key/Value** pair, use the following syntax:</span></span>

```
$PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

<span data-ttu-id="95807-127">O **CmdletName** deve ser o nome de um cmdlet ou o nome de uma função avançada que usa o atributo **CmdletBinding** .</span><span class="sxs-lookup"><span data-stu-id="95807-127">The **CmdletName** must be the name of a cmdlet or the name of an advanced function that uses the **CmdletBinding** attribute.</span></span> <span data-ttu-id="95807-128">Você não pode usar o `$PSDefaultParameterValues` para especificar valores padrão para scripts ou funções simples.</span><span class="sxs-lookup"><span data-stu-id="95807-128">You can't use `$PSDefaultParameterValues` to specify default values for scripts or simple functions.</span></span>

<span data-ttu-id="95807-129">O **DefaultValue** pode ser um objeto ou um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="95807-129">The **DefaultValue** can be an object or a script block.</span></span> <span data-ttu-id="95807-130">Se o valor for um bloco de script, o PowerShell avaliará o bloco de script e usará o resultado como o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="95807-130">If the value is a script block, PowerShell evaluates the script block and uses the result as the parameter value.</span></span> <span data-ttu-id="95807-131">Quando o parâmetro especificado aceita um valor de bloco de script, coloque o valor de bloco de script em um segundo conjunto de chaves, como:</span><span class="sxs-lookup"><span data-stu-id="95807-131">When the specified parameter accepts a script block value, enclose the script block value in a second set of braces, such as:</span></span>

```powershell
$PSDefaultParameterValues=@{ "Invoke-Command:ScriptBlock"={{Get-Process}} }
```

<span data-ttu-id="95807-132">Para obter mais informações, consulte um dos seguintes documentos:</span><span class="sxs-lookup"><span data-stu-id="95807-132">For more information, see the following documents:</span></span>

- [<span data-ttu-id="95807-133">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="95807-133">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="95807-134">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="95807-134">about_Script_Blocks</span></span>](about_Script_Blocks.md)
- [<span data-ttu-id="95807-135">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="95807-135">about_Preference_Variables</span></span>](about_Preference_Variables.md)

## <a name="examples"></a><span data-ttu-id="95807-136">Exemplos</span><span class="sxs-lookup"><span data-stu-id="95807-136">Examples</span></span>

### <a name="how-to-set-psdefaultparametervalues"></a><span data-ttu-id="95807-137">Como definir \$ PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="95807-137">How to set \$PSDefaultParameterValues</span></span>

<span data-ttu-id="95807-138">`$PSDefaultParameterValues` é uma variável de preferência, portanto, ela existe somente na sessão na qual ela está definida.</span><span class="sxs-lookup"><span data-stu-id="95807-138">`$PSDefaultParameterValues` is a preference variable, so it exists only in the session in which it's set.</span></span> <span data-ttu-id="95807-139">Não tem nenhum valor padrão.</span><span class="sxs-lookup"><span data-stu-id="95807-139">It has no default value.</span></span>

<span data-ttu-id="95807-140">Para definir `$PSDefaultParameterValues` , digite o nome da variável e um ou mais pares **chave/valor** .</span><span class="sxs-lookup"><span data-stu-id="95807-140">To set `$PSDefaultParameterValues`, type the variable name and one or more **Key/Value** pairs.</span></span> <span data-ttu-id="95807-141">Se você executar outro `$PSDefaultParameterValues` comando, ele substituirá a tabela de hash existente.</span><span class="sxs-lookup"><span data-stu-id="95807-141">If you run another `$PSDefaultParameterValues` command, it overwrites the existing hash table.</span></span>

<span data-ttu-id="95807-142">Para obter exemplos de como alterar os pares de **chave/valor** sem substituir os valores de tabela de hash existentes, consulte [como adicionar valores a \$ PSDefaultParameterValues](#how-to-add-values-to-psdefaultparametervalues) ou [como alterar valores em \$ PSDefaultParameterValues](#how-to-change-values-in-psdefaultparametervalues).</span><span class="sxs-lookup"><span data-stu-id="95807-142">For examples about how to change **Key/Value** pairs without overwriting existing hash table values, see [How to add values to \$PSDefaultParameterValues](#how-to-add-values-to-psdefaultparametervalues) or [How to change values in \$PSDefaultParameterValues](#how-to-change-values-in-psdefaultparametervalues).</span></span>

<span data-ttu-id="95807-143">Para salvar em `$PSDefaultParameterValues` sessões futuras, adicione um `$PSDefaultParameterValues` comando ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95807-143">To save `$PSDefaultParameterValues` for future sessions, add a `$PSDefaultParameterValues` command to your PowerShell profile.</span></span> <span data-ttu-id="95807-144">Para obter mais informações, consulte [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="95807-144">For more information, see [about_Profiles](about_Profiles.md).</span></span>

#### <a name="set-a-custom-default-value"></a><span data-ttu-id="95807-145">Definir um valor padrão personalizado</span><span class="sxs-lookup"><span data-stu-id="95807-145">Set a custom default value</span></span>

<span data-ttu-id="95807-146">O par **chave/valor** define a `Send-MailMessage:SmtpServer` chave para um valor padrão personalizado de **Server123** .</span><span class="sxs-lookup"><span data-stu-id="95807-146">The **Key/Value** pair sets the `Send-MailMessage:SmtpServer` key to a custom default value of **Server123** .</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
}
```

#### <a name="set-default-values-for-multiple-parameters"></a><span data-ttu-id="95807-147">Definir valores padrão para vários parâmetros</span><span class="sxs-lookup"><span data-stu-id="95807-147">Set default values for multiple parameters</span></span>

<span data-ttu-id="95807-148">Para definir valores padrão para vários parâmetros, separe cada par de **chave/valor** com um ponto e vírgula ( `;` ).</span><span class="sxs-lookup"><span data-stu-id="95807-148">To set default values for multiple parameters, separate each **Key/Value** pair with a semicolon (`;`).</span></span> <span data-ttu-id="95807-149">As `Send-MailMessage:SmtpServer` `Get-WinEvent:LogName` chaves e são definidas como valores padrão personalizados.</span><span class="sxs-lookup"><span data-stu-id="95807-149">The `Send-MailMessage:SmtpServer` and `Get-WinEvent:LogName` keys are set to custom default values.</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123";
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
}
```

#### <a name="use-wildcards-and-switch-parameters"></a><span data-ttu-id="95807-150">Usar curingas e parâmetros de comutador</span><span class="sxs-lookup"><span data-stu-id="95807-150">Use wildcards and switch parameters</span></span>

<span data-ttu-id="95807-151">Os nomes de cmdlet e parâmetro podem conter caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="95807-151">The cmdlet and parameter names can contain wildcard characters.</span></span> <span data-ttu-id="95807-152">Use `$True` e `$False` para definir valores para parâmetros de comutador, como **detalhado** .</span><span class="sxs-lookup"><span data-stu-id="95807-152">Use `$True` and `$False` to set values for switch parameters, such as **Verbose** .</span></span> <span data-ttu-id="95807-153">O parâmetro **Verbose** do parâmetro comum é definido como `$True` para todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="95807-153">The common parameter's **Verbose** parameter is set to `$True` for all commands.</span></span>

```powershell
$PSDefaultParameterValues = @{"*:Verbose"=$True}
```

#### <a name="use-an-array-for-the-default-value"></a><span data-ttu-id="95807-154">Usar uma matriz para o valor padrão</span><span class="sxs-lookup"><span data-stu-id="95807-154">Use an array for the default value</span></span>

<span data-ttu-id="95807-155">Se um parâmetro puder aceitar vários valores, uma matriz, você poderá definir vários valores como os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="95807-155">If a parameter can accept multiple values, an array, you can set multiple values as the default values.</span></span> <span data-ttu-id="95807-156">O valor padrão da `Invoke-Command:ComputerName` chave é definido como um valor de matriz de **Server01** e **Server02** .</span><span class="sxs-lookup"><span data-stu-id="95807-156">The default value of the `Invoke-Command:ComputerName` key is set to an array value of **Server01** and **Server02** .</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Invoke-Command:ComputerName"="Server01","Server02"
}
```

#### <a name="use-a-script-block"></a><span data-ttu-id="95807-157">Usar um bloco de script</span><span class="sxs-lookup"><span data-stu-id="95807-157">Use a script block</span></span>

<span data-ttu-id="95807-158">Você pode usar um bloco de script para especificar valores padrão diferentes para um parâmetro sob condições diferentes.</span><span class="sxs-lookup"><span data-stu-id="95807-158">You can use a script block to specify different default values for a parameter under different conditions.</span></span> <span data-ttu-id="95807-159">O PowerShell avalia o bloco de script e usa o resultado como o valor do parâmetro padrão.</span><span class="sxs-lookup"><span data-stu-id="95807-159">PowerShell evaluates the script block and uses the result as the default parameter value.</span></span>

<span data-ttu-id="95807-160">Os `Format-Table:AutoSize` conjuntos de chaves que alternam o parâmetro para um valor padrão de **true** .</span><span class="sxs-lookup"><span data-stu-id="95807-160">The `Format-Table:AutoSize` key sets that switch parameter to a default value of **True** .</span></span> <span data-ttu-id="95807-161">A `If` instrução contém uma condição que `$host.Name` deve ser o console do PowerShell, **ConsoleHost** .</span><span class="sxs-lookup"><span data-stu-id="95807-161">The `If` statement contains a condition that the `$host.Name` must be the PowerShell console, **ConsoleHost** .</span></span>

```powershell
$PSDefaultParameterValues=@{
  "Format-Table:AutoSize"={if ($host.Name -eq "ConsoleHost"){$True}}
}
```

<span data-ttu-id="95807-162">Se um parâmetro aceitar um valor de bloco de script, coloque o bloco de script em um conjunto extra de chaves.</span><span class="sxs-lookup"><span data-stu-id="95807-162">If a parameter accepts a script block value, enclose the script block in an extra set of braces.</span></span> <span data-ttu-id="95807-163">Quando o PowerShell avalia o bloco de script externo, o resultado é o bloco de script interno e é definido como o valor de parâmetro padrão.</span><span class="sxs-lookup"><span data-stu-id="95807-163">When PowerShell evaluates the outer script block, the result is the inner script block, and that is set as the default parameter value.</span></span>

<span data-ttu-id="95807-164">A `Invoke-Command:ScriptBlock` chave é definida como um valor padrão do **log de eventos do sistema** porque o bloco de script está incluído em um segundo conjunto de chaves.</span><span class="sxs-lookup"><span data-stu-id="95807-164">The `Invoke-Command:ScriptBlock` key set to a default value of the **System event log** because the script block is enclosed in a second set of braces.</span></span> <span data-ttu-id="95807-165">O resultado do bloco de script é passado para o `Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="95807-165">The result of the script block is passed to the `Invoke-Command` cmdlet.</span></span>

```powershell
$PSDefaultParameterValues=@{
  "Invoke-Command:ScriptBlock"={{Get-EventLog -Log System}}
}
```

### <a name="how-to-get-psdefaultparametervalues"></a><span data-ttu-id="95807-166">Como obter \$ PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="95807-166">How to get \$PSDefaultParameterValues</span></span>

<span data-ttu-id="95807-167">Os valores da tabela de hash são exibidos digitando `$PSDefaultParameterValues` no prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95807-167">The hash table values are displayed by entering `$PSDefaultParameterValues` at the PowerShell prompt.</span></span>

<span data-ttu-id="95807-168">Uma `$PSDefaultParameterValues` tabela de hash é definida com três pares de **chave/valor** .</span><span class="sxs-lookup"><span data-stu-id="95807-168">A `$PSDefaultParameterValues` hash table is set with three **Key/Value** pairs.</span></span>
<span data-ttu-id="95807-169">Essa tabela de hash é usada nos exemplos a seguir que descrevem como adicionar, alterar e remover valores de `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="95807-169">This hash table is used in the following examples that describe how to add, change, and remove values from `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
  "Get-*:Verbose"=$True
}

PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

<span data-ttu-id="95807-170">Para obter o valor de uma `CmdletName:ParameterName` chave específica, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="95807-170">To get the value of a specific `CmdletName:ParameterName` key, use the following syntax:</span></span>

```
$PSDefaultParameterValues["CmdletName:ParameterName"]
```

<span data-ttu-id="95807-171">Por exemplo, para obter o valor da `Send-MailMessage:SmtpServer` chave.</span><span class="sxs-lookup"><span data-stu-id="95807-171">For example, to get the value for the `Send-MailMessage:SmtpServer` key.</span></span>

```
PS> $PSDefaultParameterValues["Send-MailMessage:SmtpServer"]
Server123
```

### <a name="how-to-add-values-to-psdefaultparametervalues"></a><span data-ttu-id="95807-172">Como adicionar valores a \$ PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="95807-172">How to add values to \$PSDefaultParameterValues</span></span>

<span data-ttu-id="95807-173">Para adicionar um valor a `$PSDefaultParameterValues` , use o método **Add** .</span><span class="sxs-lookup"><span data-stu-id="95807-173">To add a value to `$PSDefaultParameterValues`, use the **Add** method.</span></span> <span data-ttu-id="95807-174">A adição de um valor não afeta os valores existentes da tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="95807-174">Adding a value doesn't affect the hash table's existing values.</span></span>

<span data-ttu-id="95807-175">Use uma vírgula ( `,` ) para separar a **chave** do **valor** .</span><span class="sxs-lookup"><span data-stu-id="95807-175">Use a comma (`,`) to separate the **Key** from the **Value** .</span></span> <span data-ttu-id="95807-176">A sintaxe a seguir mostra como usar o método **Add** para `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="95807-176">The following syntax shows how to use the **Add** method for `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues.Add("CmdletName:ParameterName", "DefaultValue")
```

<span data-ttu-id="95807-177">A tabela de hash criada no exemplo anterior é atualizada com um novo par de **chave/valor** .</span><span class="sxs-lookup"><span data-stu-id="95807-177">The hash table created in the prior example is updated with a new **Key/Value** pair.</span></span> <span data-ttu-id="95807-178">O método **Add** define a `Get-Process:Name` chave para o valor **PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="95807-178">The **Add** method sets the `Get-Process:Name` key to the value **PowerShell** .</span></span>

```powershell
$PSDefaultParameterValues.Add("Get-Process:Name", "PowerShell")
```

<span data-ttu-id="95807-179">A sintaxe a seguir realiza o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="95807-179">The following syntax accomplishes the same result.</span></span>

```powershell
$PSDefaultParameterValues["Get-Process:Name"]="PowerShell"
```

<span data-ttu-id="95807-180">A `$PSDefaultParameterValues` variável exibe a tabela de hash atualizada.</span><span class="sxs-lookup"><span data-stu-id="95807-180">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="95807-181">A `Get-Process:Name` chave foi adicionada.</span><span class="sxs-lookup"><span data-stu-id="95807-181">The `Get-Process:Name` key was added.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-Process:Name               PowerShell
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-remove-values-from-psdefaultparametervalues"></a><span data-ttu-id="95807-182">Como remover valores de \$ PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="95807-182">How to remove values from \$PSDefaultParameterValues</span></span>

<span data-ttu-id="95807-183">Para remover um valor de `$PSDefaultParameterValues` , use o método **Remove** de tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="95807-183">To remove a value from `$PSDefaultParameterValues`, use the **Remove** method of hash tables.</span></span> <span data-ttu-id="95807-184">A remoção de um valor não afeta os valores existentes da tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="95807-184">Removing a value doesn't affect the hash table's existing values.</span></span>

<span data-ttu-id="95807-185">A sintaxe a seguir mostra como usar o método **Remove** em `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="95807-185">The following syntax shows how to use the **Remove** method on `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues.Remove("CmdletName:ParameterName")
```

<span data-ttu-id="95807-186">Neste exemplo, a tabela de hash criada no exemplo anterior é atualizada para remover um par de **chave/valor** .</span><span class="sxs-lookup"><span data-stu-id="95807-186">In this example, the hash table created in the prior example is updated to remove a **Key/Value** pair.</span></span> <span data-ttu-id="95807-187">O método **Remove** remove a `Get-Process:Name` chave.</span><span class="sxs-lookup"><span data-stu-id="95807-187">The **Remove** method removes the `Get-Process:Name` key.</span></span>

```powershell
$PSDefaultParameterValues.Remove("Get-Process:Name")
```

<span data-ttu-id="95807-188">A `$PSDefaultParameterValues` variável exibe a tabela de hash atualizada.</span><span class="sxs-lookup"><span data-stu-id="95807-188">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="95807-189">A `Get-Process:Name` chave foi removida.</span><span class="sxs-lookup"><span data-stu-id="95807-189">The `Get-Process:Name` key was removed.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-change-values-in-psdefaultparametervalues"></a><span data-ttu-id="95807-190">Como alterar valores em \$ PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="95807-190">How to change values in \$PSDefaultParameterValues</span></span>

<span data-ttu-id="95807-191">As alterações em um valor específico não afetam os valores de tabela de hash existentes.</span><span class="sxs-lookup"><span data-stu-id="95807-191">Changes to a specific value don't affect existing hash table values.</span></span> <span data-ttu-id="95807-192">Para alterar um par de **chave/valor** específico no `$PSDefaultParameterValues` , use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="95807-192">To change a specific **Key/Value** pair in `$PSDefaultParameterValues`, use the following syntax:</span></span>

```
PS> $PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

<span data-ttu-id="95807-193">Neste exemplo, a tabela de hash criada no exemplo anterior é atualizada para alterar um par de **chave/valor** .</span><span class="sxs-lookup"><span data-stu-id="95807-193">In this example, the hash table created in the prior example is updated to change a **Key/Value** pair.</span></span> <span data-ttu-id="95807-194">O comando a seguir altera a `Send-MailMessage:SmtpServer` chave para um novo valor de **ServerXYZ** .</span><span class="sxs-lookup"><span data-stu-id="95807-194">The following command changes the `Send-MailMessage:SmtpServer` key to a new value of **ServerXYZ** .</span></span>

```powershell
$PSDefaultParameterValues["Send-MailMessage:SmtpServer"]="ServerXYZ"
```

<span data-ttu-id="95807-195">A `$PSDefaultParameterValues` variável exibe a tabela de hash atualizada.</span><span class="sxs-lookup"><span data-stu-id="95807-195">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="95807-196">A `Send-MailMessage:SmtpServer` chave foi alterada para um novo valor.</span><span class="sxs-lookup"><span data-stu-id="95807-196">The `Send-MailMessage:SmtpServer` key was changed to a new value.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

### <a name="how-to-disable-and-re-enable-psdefaultparametervalues"></a><span data-ttu-id="95807-197">Como desabilitar e reabilitar o \$ PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="95807-197">How to disable and re-enable \$PSDefaultParameterValues</span></span>

<span data-ttu-id="95807-198">Você pode desabilitar e, em seguida, reabilitar temporariamente `$PSDefaultParameterValues` .</span><span class="sxs-lookup"><span data-stu-id="95807-198">You can temporarily disable and then re-enable `$PSDefaultParameterValues`.</span></span>
<span data-ttu-id="95807-199">Desabilitar `$PSDefaultParameterValues` será útil se você estiver executando scripts que precisam de valores de parâmetro padrão diferentes.</span><span class="sxs-lookup"><span data-stu-id="95807-199">Disabling `$PSDefaultParameterValues` is useful if you're running scripts that need different default parameter values.</span></span>

<span data-ttu-id="95807-200">Para desabilitar `$PSDefaultParameterValues` , adicione uma chave de `Disabled` com um valor de **true** .</span><span class="sxs-lookup"><span data-stu-id="95807-200">To disable `$PSDefaultParameterValues`, add a key of `Disabled` with a value of **True** .</span></span> <span data-ttu-id="95807-201">Os valores em `$PSDefaultParameterValues` são preservados, mas não são efetivos.</span><span class="sxs-lookup"><span data-stu-id="95807-201">The values in `$PSDefaultParameterValues` are preserved, but aren't effective.</span></span>

```
PS> $PSDefaultParameterValues.Add("Disabled", $True)
```

<span data-ttu-id="95807-202">A sintaxe a seguir realiza o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="95807-202">The following syntax accomplishes the same result.</span></span>

```
PS> $PSDefaultParameterValues["Disabled"]=$True
```

<span data-ttu-id="95807-203">A `$PSDefaultParameterValues` variável exibe a tabela de hash atualizada com o valor para a `Disabled` chave.</span><span class="sxs-lookup"><span data-stu-id="95807-203">The `$PSDefaultParameterValues` variable displays the updated hash table with the value for the `Disabled` key.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       True
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

<span data-ttu-id="95807-204">Para reabilitar `$PSDefaultParameterValues` , remova a chave **desabilitada** ou altere o valor da chave **desabilitada** para `$False` .</span><span class="sxs-lookup"><span data-stu-id="95807-204">To re-enable `$PSDefaultParameterValues`, remove the **Disabled** key or change the value of the **Disabled** key to `$False`.</span></span> <span data-ttu-id="95807-205">O valor anterior de `$PSDefaultParameterValues` é efetivo novamente.</span><span class="sxs-lookup"><span data-stu-id="95807-205">The previous value of `$PSDefaultParameterValues` is effective again.</span></span>

```
PS> $PSDefaultParameterValues.Remove("Disabled")
```

<span data-ttu-id="95807-206">A sintaxe a seguir realiza o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="95807-206">The following syntax accomplishes the same result.</span></span>

```
PS> $PSDefaultParameterValues["Disabled"]=$False
```

<span data-ttu-id="95807-207">A `$PSDefaultParameterValues` variável exibe a tabela de hash atualizada.</span><span class="sxs-lookup"><span data-stu-id="95807-207">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="95807-208">Quando o método **Remove** é usado, a `Disabled` chave é removida da saída.</span><span class="sxs-lookup"><span data-stu-id="95807-208">When the **Remove** method is used, the `Disabled` key is removed from the output.</span></span>
<span data-ttu-id="95807-209">Se a sintaxe alternativa foi usada para reabilitar `$PSDefaultParameterValues` , a `Disabled` chave será exibida como **false** .</span><span class="sxs-lookup"><span data-stu-id="95807-209">If the alternate syntax was used to re-enable `$PSDefaultParameterValues`, the `Disabled` key is displayed as **False** .</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       False
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

## <a name="see-also"></a><span data-ttu-id="95807-210">Confira também</span><span class="sxs-lookup"><span data-stu-id="95807-210">See also</span></span>

[<span data-ttu-id="95807-211">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="95807-211">about_CommonParameters</span></span>](https://go.microsoft.com/fwlink/?LinkID=113216)

[<span data-ttu-id="95807-212">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="95807-212">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="95807-213">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="95807-213">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="95807-214">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="95807-214">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="95807-215">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="95807-215">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="95807-216">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="95807-216">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="95807-217">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="95807-217">about_Script_Blocks</span></span>](about_Script_Blocks.md)

