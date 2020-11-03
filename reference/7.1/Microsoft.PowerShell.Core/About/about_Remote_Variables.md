---
description: Explica como usar variáveis locais e remotas em comandos remotos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_variables?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Variables
ms.openlocfilehash: f4477b76dd6ef16ca1c4dea6259c2591f1f0b40d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196322"
---
# <a name="about-remote-variables"></a><span data-ttu-id="91da8-104">Sobre variáveis remotas</span><span class="sxs-lookup"><span data-stu-id="91da8-104">About Remote Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="91da8-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="91da8-105">Short description</span></span>

<span data-ttu-id="91da8-106">Explica como usar variáveis locais e remotas em comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="91da8-106">Explains how to use local and remote variables in remote commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="91da8-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="91da8-107">Long description</span></span>

<span data-ttu-id="91da8-108">Você pode usar variáveis em comandos que você executa em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="91da8-108">You can use variables in commands that you run on remote computers.</span></span> <span data-ttu-id="91da8-109">Atribua um valor à variável e, em seguida, use a variável no lugar do valor.</span><span class="sxs-lookup"><span data-stu-id="91da8-109">Assign a value to the variable and then use the variable in place of the value.</span></span>

<span data-ttu-id="91da8-110">Por padrão, as variáveis em comandos remotos são consideradas como definidas na sessão que executa o comando.</span><span class="sxs-lookup"><span data-stu-id="91da8-110">By default, the variables in remote commands are assumed to be defined in the session that runs the command.</span></span> <span data-ttu-id="91da8-111">As variáveis definidas em uma sessão local devem ser identificadas como variáveis locais no comando.</span><span class="sxs-lookup"><span data-stu-id="91da8-111">Variables that are defined in a local session, must be identified as local variables in the command.</span></span>

## <a name="using-remote-variables"></a><span data-ttu-id="91da8-112">Usando variáveis remotas</span><span class="sxs-lookup"><span data-stu-id="91da8-112">Using remote variables</span></span>

<span data-ttu-id="91da8-113">O PowerShell assume que as variáveis usadas em comandos remotos são definidas na sessão em que o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="91da8-113">PowerShell assumes that the variables used in remote commands are defined in the session in which the command runs.</span></span>

<span data-ttu-id="91da8-114">Neste exemplo, a `$ps` variável é definida na sessão temporária na qual o `Get-WinEvent` comando é executado.</span><span class="sxs-lookup"><span data-stu-id="91da8-114">In this example, the `$ps` variable is defined in the temporary session in which the `Get-WinEvent` command runs.</span></span>

```powershell
Invoke-Command -ComputerName S1 -ScriptBlock {
  $ps = "*PowerShell*"; Get-WinEvent -LogName $ps
}
```

<span data-ttu-id="91da8-115">Quando o comando é executado em uma sessão persistente, **PSSession** , a variável remota deve ser definida nessa sessão.</span><span class="sxs-lookup"><span data-stu-id="91da8-115">When the command runs in a persistent session, **PSSession** , the remote variable must be defined in that session.</span></span>

```powershell
$s = New-PSSession -ComputerName S1
Invoke-Command -Session $s -ScriptBlock {$ps = "*PowerShell*"}
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $ps}
```

## <a name="using-local-variables"></a><span data-ttu-id="91da8-116">Usando variáveis locais</span><span class="sxs-lookup"><span data-stu-id="91da8-116">Using local variables</span></span>

<span data-ttu-id="91da8-117">Você pode usar variáveis locais em comandos remotos, mas a variável deve ser definida na sessão local.</span><span class="sxs-lookup"><span data-stu-id="91da8-117">You can use local variables in remote commands, but the variable must be defined in the local session.</span></span>

<span data-ttu-id="91da8-118">A partir do PowerShell 3,0, você pode usar o `Using` modificador de escopo para identificar uma variável local em um comando remoto.</span><span class="sxs-lookup"><span data-stu-id="91da8-118">Beginning in PowerShell 3.0, you can use the `Using` scope modifier to identify a local variable in a remote command.</span></span>

<span data-ttu-id="91da8-119">A sintaxe do `Using` é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="91da8-119">The syntax of `Using` is as follows:</span></span>

```
$Using:<VariableName>
```

<span data-ttu-id="91da8-120">No exemplo a seguir, a `$ps` variável é criada na sessão local, mas é usada na sessão na qual o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="91da8-120">In the following example, the `$ps` variable is created in the local session, but is used in the session in which the command runs.</span></span> <span data-ttu-id="91da8-121">O `Using` modificador de escopo identifica `$ps` como uma variável local.</span><span class="sxs-lookup"><span data-stu-id="91da8-121">The `Using` scope modifier identifies `$ps` as a local variable.</span></span>

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  Get-WinEvent -LogName $Using:ps
}
```

<span data-ttu-id="91da8-122">O `Using` modificador de escopo pode ser usado em uma **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="91da8-122">The `Using` scope modifier can be used in a **PSSession** .</span></span>

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {Get-WinEvent -LogName $Using:ps}
```

<span data-ttu-id="91da8-123">Uma referência de variável, como `$using:var` expande para o valor da variável `$var` do contexto do chamador.</span><span class="sxs-lookup"><span data-stu-id="91da8-123">A variable reference such as `$using:var` expands to the value of variable `$var` from the caller's context.</span></span> <span data-ttu-id="91da8-124">Você não tem acesso ao objeto de variável do chamador.</span><span class="sxs-lookup"><span data-stu-id="91da8-124">You do not get access to the caller's variable object.</span></span>
<span data-ttu-id="91da8-125">O `Using` modificador de escopo não pode ser usado para modificar uma variável local dentro de **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="91da8-125">The `Using` scope modifier cannot be used to modify a local variable within the **PSSession** .</span></span> <span data-ttu-id="91da8-126">Por exemplo, o código a seguir não funciona:</span><span class="sxs-lookup"><span data-stu-id="91da8-126">For example, the following code does not work:</span></span>

```powershell
$s = New-PSSession -ComputerName S1
$ps = "*PowerShell*"
Invoke-Command -Session $s -ScriptBlock {$Using:ps = 'Cannot assign new value'}
```

<span data-ttu-id="91da8-127">Para obter mais informações sobre o `Using` , consulte [about_Scopes](./about_Scopes.md)</span><span class="sxs-lookup"><span data-stu-id="91da8-127">For more information about `Using`, see [about_Scopes](./about_Scopes.md)</span></span>

### <a name="using-splatting"></a><span data-ttu-id="91da8-128">Usando nivelamento</span><span class="sxs-lookup"><span data-stu-id="91da8-128">Using splatting</span></span>

<span data-ttu-id="91da8-129">O PowerShell nivelamento passa uma coleção de valores e nomes de parâmetro para um comando.</span><span class="sxs-lookup"><span data-stu-id="91da8-129">PowerShell splatting passes a collection of parameter names and values to a command.</span></span> <span data-ttu-id="91da8-130">Para obter mais informações, consulte [about_Splatting](about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="91da8-130">For more information, see [about_Splatting](about_Splatting.md).</span></span>

<span data-ttu-id="91da8-131">Neste exemplo, a variável nivelamento `$Splat` é uma tabela de hash configurada no computador local.</span><span class="sxs-lookup"><span data-stu-id="91da8-131">In this example, the splatting variable, `$Splat` is a hash table that is set up on the local computer.</span></span> <span data-ttu-id="91da8-132">O `Invoke-Command` conecta-se a uma sessão de computador remoto.</span><span class="sxs-lookup"><span data-stu-id="91da8-132">The `Invoke-Command` connects to a remote computer session.</span></span> <span data-ttu-id="91da8-133">O **scriptblock** usa o `Using` modificador de escopo com o `@` símbolo arroba () para representar a variável splatted.</span><span class="sxs-lookup"><span data-stu-id="91da8-133">The **ScriptBlock** uses the `Using` scope modifier with the At (`@`) symbol to represent the splatted variable.</span></span>

```powershell
$Splat = @{ Name = "Win*"; Include = "WinRM" }
Invoke-Command -Session $s -ScriptBlock { Get-Service @Using:Splat }
```

### <a name="other-situations-where-the-using-scope-modifier-is-needed"></a><span data-ttu-id="91da8-134">Outras situações em que o modificador de escopo ' Using ' é necessário</span><span class="sxs-lookup"><span data-stu-id="91da8-134">Other situations where the 'Using' scope modifier is needed</span></span>

<span data-ttu-id="91da8-135">Para qualquer script ou comando que é executado fora da sessão, você precisa do `Using` modificador de escopo para inserir valores de variáveis do escopo da sessão de chamada, para que o código fora da sessão possa acessá-los.</span><span class="sxs-lookup"><span data-stu-id="91da8-135">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span> <span data-ttu-id="91da8-136">O `Using` modificador de escopo tem suporte nos seguintes contextos:</span><span class="sxs-lookup"><span data-stu-id="91da8-136">The `Using` scope modifier is supported in the following contexts:</span></span>

- <span data-ttu-id="91da8-137">Comandos executados remotamente, iniciados com `Invoke-Command` o uso dos parâmetros **ComputerName** , **hostname** , **SSHConnection** ou **Session** (sessão remota)</span><span class="sxs-lookup"><span data-stu-id="91da8-137">Remotely executed commands, started with `Invoke-Command` using the **ComputerName** , **HostName** , **SSHConnection** or **Session** parameters (remote session)</span></span>
- <span data-ttu-id="91da8-138">Trabalhos em segundo plano, iniciados com `Start-Job` (sessão fora do processo)</span><span class="sxs-lookup"><span data-stu-id="91da8-138">Background jobs, started with `Start-Job` (out-of-process session)</span></span>
- <span data-ttu-id="91da8-139">Trabalhos de thread, iniciados via `Start-ThreadJob` ou `ForEach-Object -Parallel` (sessão de thread separada)</span><span class="sxs-lookup"><span data-stu-id="91da8-139">Thread jobs, started via `Start-ThreadJob` or `ForEach-Object -Parallel` (separate thread session)</span></span>

<span data-ttu-id="91da8-140">Dependendo do contexto, os valores de variáveis inseridos são cópias independentes dos dados no escopo do chamador ou referências a ele.</span><span class="sxs-lookup"><span data-stu-id="91da8-140">Depending on the context, embedded variable values are either independent copies of the data in the caller's scope or references to it.</span></span> <span data-ttu-id="91da8-141">Em sessões remotas e fora do processo, elas são sempre cópias independentes.</span><span class="sxs-lookup"><span data-stu-id="91da8-141">In remote and out-of-process sessions, they are always independent copies.</span></span> <span data-ttu-id="91da8-142">Em sessões de thread, elas são passadas por referência.</span><span class="sxs-lookup"><span data-stu-id="91da8-142">In thread sessions, they are passed by reference.</span></span>

## <a name="serialization-of-variable-values"></a><span data-ttu-id="91da8-143">Serialização de valores de variáveis</span><span class="sxs-lookup"><span data-stu-id="91da8-143">Serialization of variable values</span></span>

<span data-ttu-id="91da8-144">Comandos executados remotamente e trabalhos em segundo plano são executados fora do processo.</span><span class="sxs-lookup"><span data-stu-id="91da8-144">Remotely executed commands and background jobs run out-of-process.</span></span>
<span data-ttu-id="91da8-145">Sessões fora do processo usam serialização e desserialização baseadas em XML para tornar os valores das variáveis disponíveis nos limites do processo.</span><span class="sxs-lookup"><span data-stu-id="91da8-145">Out-of-process sessions use XML-based serialization and deserialization to make the values of variables available across the process boundaries.</span></span> <span data-ttu-id="91da8-146">O processo de serialização converte objetos em um **PSObject** que contém as propriedades dos objetos originais, mas não seus métodos.</span><span class="sxs-lookup"><span data-stu-id="91da8-146">The serialization process converts objects to a **PSObject** that contains the original objects properties but not its methods.</span></span>

<span data-ttu-id="91da8-147">Para um conjunto limitado de tipos, a desserialização rehydrates objetos de volta para o tipo original.</span><span class="sxs-lookup"><span data-stu-id="91da8-147">For a limited set of types, deserialization rehydrates objects back to the original type.</span></span> <span data-ttu-id="91da8-148">O objeto de resalimentação é uma cópia da instância do objeto original.</span><span class="sxs-lookup"><span data-stu-id="91da8-148">The rehydrated object is a copy of the original object instance.</span></span>
<span data-ttu-id="91da8-149">Ele tem as propriedades e os métodos do tipo.</span><span class="sxs-lookup"><span data-stu-id="91da8-149">It has the type properties and methods.</span></span> <span data-ttu-id="91da8-150">Para tipos simples, como **System. Version** , a cópia é exata.</span><span class="sxs-lookup"><span data-stu-id="91da8-150">For simple types, such as **System.Version** , the copy is exact.</span></span> <span data-ttu-id="91da8-151">Para tipos complexos, a cópia é imperfeita.</span><span class="sxs-lookup"><span data-stu-id="91da8-151">For complex types, the copy is imperfect.</span></span> <span data-ttu-id="91da8-152">Por exemplo, os objetos de certificado resalimentados não incluem a chave privada.</span><span class="sxs-lookup"><span data-stu-id="91da8-152">For example, rehydrated certificate objects do not include the private key.</span></span>

<span data-ttu-id="91da8-153">Instâncias de todos os outros tipos são instâncias de **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="91da8-153">Instances of all other types are **PSObject** instances.</span></span> <span data-ttu-id="91da8-154">A propriedade **PSTypeNames** contém o nome do tipo original prefixado com **desserializado** , por exemplo, **Deserialized.System. Data. DataTable**</span><span class="sxs-lookup"><span data-stu-id="91da8-154">The **PSTypeNames** property contains the original type name prefixed with **Deserialized** , for example, **Deserialized.System.Data.DataTable**</span></span>

## <a name="using-local-variables-with-argumentlist-parameter"></a><span data-ttu-id="91da8-155">Usando variáveis locais com parâmetro **ArgumentList**</span><span class="sxs-lookup"><span data-stu-id="91da8-155">Using local variables with **ArgumentList** parameter</span></span>

<span data-ttu-id="91da8-156">Você pode usar variáveis locais em um comando remoto definindo parâmetros para o comando remoto e usando o parâmetro **ArgumentList** do `Invoke-Command` cmdlet para especificar a variável local como o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="91da8-156">You can use local variables in a remote command by defining parameters for the remote command and using the **ArgumentList** parameter of the `Invoke-Command` cmdlet to specify the local variable as the parameter value.</span></span>

- <span data-ttu-id="91da8-157">Use a `param` palavra-chave para definir parâmetros para o comando remoto.</span><span class="sxs-lookup"><span data-stu-id="91da8-157">Use the `param` keyword to define parameters for the remote command.</span></span> <span data-ttu-id="91da8-158">Os nomes de parâmetro são espaços reservados que não precisam corresponder ao nome da variável local.</span><span class="sxs-lookup"><span data-stu-id="91da8-158">The parameter names are placeholders that don't need to match the local variable's name.</span></span>

- <span data-ttu-id="91da8-159">Use os parâmetros definidos pela `param` palavra-chave no comando.</span><span class="sxs-lookup"><span data-stu-id="91da8-159">Use the parameters defined by the `param` keyword in the command.</span></span>

- <span data-ttu-id="91da8-160">Use o parâmetro **ArgumentList** do `Invoke-Command` cmdlet para especificar a variável local como o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="91da8-160">Use the **ArgumentList** parameter of the `Invoke-Command` cmdlet to specify the local variable as the parameter value.</span></span>

<span data-ttu-id="91da8-161">Por exemplo, os comandos a seguir definem a `$ps` variável na sessão local e, em seguida, o usam em um comando remoto.</span><span class="sxs-lookup"><span data-stu-id="91da8-161">For example, the following commands define the `$ps` variable in the local session and then use it in a remote command.</span></span> <span data-ttu-id="91da8-162">O comando usa `$log` como o nome do parâmetro e a variável local, `$ps` , como seu valor.</span><span class="sxs-lookup"><span data-stu-id="91da8-162">The command uses `$log` as the parameter name and the local variable, `$ps`, as its value.</span></span>

```powershell
$ps = "*PowerShell*"
Invoke-Command -ComputerName S1 -ScriptBlock {
  param($log)
  Get-WinEvent -LogName $log
} -ArgumentList $ps
```

## <a name="see-also"></a><span data-ttu-id="91da8-163">Confira também</span><span class="sxs-lookup"><span data-stu-id="91da8-163">See also</span></span>

[<span data-ttu-id="91da8-164">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="91da8-164">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="91da8-165">about_Remote</span><span class="sxs-lookup"><span data-stu-id="91da8-165">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="91da8-166">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="91da8-166">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="91da8-167">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="91da8-167">about_Splatting</span></span>](about_Splatting.md)

[<span data-ttu-id="91da8-168">about_Variables</span><span class="sxs-lookup"><span data-stu-id="91da8-168">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="91da8-169">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="91da8-169">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="91da8-170">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="91da8-170">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="91da8-171">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="91da8-171">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="91da8-172">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="91da8-172">Start-ThreadJob</span></span>](xref:ThreadJob.Start-ThreadJob)

@Microsoft.PowerShell.Core.ForEach-Object

