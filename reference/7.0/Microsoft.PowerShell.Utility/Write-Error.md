---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-error?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Error
ms.openlocfilehash: 883990ace87c947ad9f0e10100d4d1dc7f1b8cbe
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "93196428"
---
# <span data-ttu-id="5fa05-103">Write-Error</span><span class="sxs-lookup"><span data-stu-id="5fa05-103">Write-Error</span></span>

## <span data-ttu-id="5fa05-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5fa05-104">SYNOPSIS</span></span>
<span data-ttu-id="5fa05-105">Grava um objeto no fluxo de erros.</span><span class="sxs-lookup"><span data-stu-id="5fa05-105">Writes an object to the error stream.</span></span>

## <span data-ttu-id="5fa05-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5fa05-106">SYNTAX</span></span>

### <span data-ttu-id="5fa05-107">Noexception (padrão)</span><span class="sxs-lookup"><span data-stu-id="5fa05-107">NoException (Default)</span></span>

```
Write-Error [-Message] <String> [-Category <ErrorCategory>] [-ErrorId <String>] [-TargetObject <Object>]
 [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### <span data-ttu-id="5fa05-108">COMException</span><span class="sxs-lookup"><span data-stu-id="5fa05-108">WithException</span></span>

```
Write-Error -Exception <Exception> [-Message <String>] [-Category <ErrorCategory>] [-ErrorId <String>]
 [-TargetObject <Object>] [-RecommendedAction <String>] [-CategoryActivity <String>] [-CategoryReason <String>]
 [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

### <span data-ttu-id="5fa05-109">ErrorRecord</span><span class="sxs-lookup"><span data-stu-id="5fa05-109">ErrorRecord</span></span>

```
Write-Error -ErrorRecord <ErrorRecord> [-RecommendedAction <String>] [-CategoryActivity <String>]
 [-CategoryReason <String>] [-CategoryTargetName <String>] [-CategoryTargetType <String>] [<CommonParameters>]
```

## <span data-ttu-id="5fa05-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5fa05-110">DESCRIPTION</span></span>

<span data-ttu-id="5fa05-111">O `Write-Error` cmdlet declara um erro de não finalização.</span><span class="sxs-lookup"><span data-stu-id="5fa05-111">The `Write-Error` cmdlet declares a non-terminating error.</span></span> <span data-ttu-id="5fa05-112">Por padrão, os erros serão enviados no fluxo de erros para o programa do host para serem exibidos, juntamente com a saída.</span><span class="sxs-lookup"><span data-stu-id="5fa05-112">By default, errors are sent in the error stream to the host program to be displayed, along with output.</span></span>

<span data-ttu-id="5fa05-113">Para gravar um erro não fatal, digite uma cadeia de caracteres de mensagem de erro, um objeto **ErrorRecord** ou um **Exception** .</span><span class="sxs-lookup"><span data-stu-id="5fa05-113">To write a non-terminating error, enter an error message string, an **ErrorRecord** object, or an **Exception** object.</span></span> <span data-ttu-id="5fa05-114">Use os outros parâmetros do `Write-Error` para popular o registro de erro.</span><span class="sxs-lookup"><span data-stu-id="5fa05-114">Use the other parameters of `Write-Error` to populate the error record.</span></span>

<span data-ttu-id="5fa05-115">Erros não fatais gravam um erro no fluxo de erros, mas não param o processamento do comando.</span><span class="sxs-lookup"><span data-stu-id="5fa05-115">Non-terminating errors write an error to the error stream, but they do not stop command processing.</span></span>
<span data-ttu-id="5fa05-116">Se um erro não fatal for declarado em um item em uma coleção de itens de entrada, o comando continuará a processar os outros itens na coleção.</span><span class="sxs-lookup"><span data-stu-id="5fa05-116">If a non-terminating error is declared on one item in a collection of input items, the command continues to process the other items in the collection.</span></span>

<span data-ttu-id="5fa05-117">Para declarar um erro de encerramento, use a `Throw` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="5fa05-117">To declare a terminating error, use the `Throw` keyword.</span></span>
<span data-ttu-id="5fa05-118">Para obter mais informações, consulte [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md).</span><span class="sxs-lookup"><span data-stu-id="5fa05-118">For more information, see [about_Throw](../Microsoft.PowerShell.Core/About/about_Throw.md).</span></span>

## <span data-ttu-id="5fa05-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5fa05-119">EXAMPLES</span></span>

### <span data-ttu-id="5fa05-120">Exemplo 1: gravar um erro para o objeto RegistryKey</span><span class="sxs-lookup"><span data-stu-id="5fa05-120">Example 1: Write an error for RegistryKey object</span></span>

```powershell
Get-ChildItem | ForEach-Object {
    if ($_.GetType().ToString() -eq "Microsoft.Win32.RegistryKey")
    {
        Write-Error "Invalid object" -ErrorId B1 -TargetObject $_
    }
    else
    {
        $_
    }
}
```

<span data-ttu-id="5fa05-121">Esse comando declara um erro de não finalização quando o `Get-ChildItem` cmdlet retorna um `Microsoft.Win32.RegistryKey` objeto, como os objetos nas `HKLM:` `HKCU:` unidades ou do provedor de registro do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fa05-121">This command declares a non-terminating error when the `Get-ChildItem` cmdlet returns a `Microsoft.Win32.RegistryKey` object, such as the objects in the `HKLM:` or `HKCU:` drives of the PowerShell Registry provider.</span></span>

### <span data-ttu-id="5fa05-122">Exemplo 2: gravar uma mensagem de erro no console</span><span class="sxs-lookup"><span data-stu-id="5fa05-122">Example 2: Write an error message to the console</span></span>

```powershell
Write-Error "Access denied."
```

<span data-ttu-id="5fa05-123">Esse comando declara um erro não fatal e grava um erro "Acesso negado".</span><span class="sxs-lookup"><span data-stu-id="5fa05-123">This command declares a non-terminating error and writes an "Access denied" error.</span></span> <span data-ttu-id="5fa05-124">O comando usa o parâmetro **Message** para especificar a mensagem, mas omite o nome do parâmetro **Message** opcional.</span><span class="sxs-lookup"><span data-stu-id="5fa05-124">The command uses the **Message** parameter to specify the message, but omits the optional **Message** parameter name.</span></span>

### <span data-ttu-id="5fa05-125">Exemplo 3: gravar um erro no console e especificar a categoria</span><span class="sxs-lookup"><span data-stu-id="5fa05-125">Example 3: Write an error to the console and specify the category</span></span>

```powershell
Write-Error -Message "Error: Too many input values." -Category InvalidArgument
```

<span data-ttu-id="5fa05-126">Esse comando declara um erro não fatal e especifica uma categoria de erro.</span><span class="sxs-lookup"><span data-stu-id="5fa05-126">This command declares a non-terminating error and specifies an error category.</span></span>

### <span data-ttu-id="5fa05-127">Exemplo 4: gravar um erro usando um objeto de exceção</span><span class="sxs-lookup"><span data-stu-id="5fa05-127">Example 4: Write an error using an Exception object</span></span>

```powershell
$E = [System.Exception]@{Source="Get-ParameterNames.ps1";HelpLink="https://go.microsoft.com/fwlink/?LinkID=113425"}
Write-Error -Exception $E -Message "Files not found. The $Files location does not contain any XML files."
```

<span data-ttu-id="5fa05-128">Este comando usa um objeto **Exception** para declarar um erro não fatal.</span><span class="sxs-lookup"><span data-stu-id="5fa05-128">This command uses an **Exception** object to declare a non-terminating error.</span></span>

<span data-ttu-id="5fa05-129">O primeiro comando usa uma tabela de hash para criar o objeto **System.Exception** .</span><span class="sxs-lookup"><span data-stu-id="5fa05-129">The first command uses a hash table to create the **System.Exception** object.</span></span> <span data-ttu-id="5fa05-130">Ele salva o objeto de exceção na `$E` variável.</span><span class="sxs-lookup"><span data-stu-id="5fa05-130">It saves the exception object in the `$E` variable.</span></span> <span data-ttu-id="5fa05-131">Você pode usar uma tabela de hash para criar qualquer objeto de um tipo que possui um construtor nulo.</span><span class="sxs-lookup"><span data-stu-id="5fa05-131">You can use a hash table to create any object of a type that has a null constructor.</span></span>

<span data-ttu-id="5fa05-132">O segundo comando usa o `Write-Error` cmdlet para declarar um erro de não finalização.</span><span class="sxs-lookup"><span data-stu-id="5fa05-132">The second command uses the `Write-Error` cmdlet to declare a non-terminating error.</span></span> <span data-ttu-id="5fa05-133">O valor do parâmetro de **exceção** é o objeto de **exceção** na `$E` variável.</span><span class="sxs-lookup"><span data-stu-id="5fa05-133">The value of the **Exception** parameter is the **Exception** object in the `$E` variable.</span></span>

## <span data-ttu-id="5fa05-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5fa05-134">PARAMETERS</span></span>

### <span data-ttu-id="5fa05-135">-Categoria</span><span class="sxs-lookup"><span data-stu-id="5fa05-135">-Category</span></span>

<span data-ttu-id="5fa05-136">Especifica a categoria do erro.</span><span class="sxs-lookup"><span data-stu-id="5fa05-136">Specifies the category of the error.</span></span> <span data-ttu-id="5fa05-137">O valor padrão não é **especificado** .</span><span class="sxs-lookup"><span data-stu-id="5fa05-137">The default value is **NotSpecified** .</span></span> <span data-ttu-id="5fa05-138">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="5fa05-138">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5fa05-139">NotSpecified</span><span class="sxs-lookup"><span data-stu-id="5fa05-139">NotSpecified</span></span>
- <span data-ttu-id="5fa05-140">OpenError</span><span class="sxs-lookup"><span data-stu-id="5fa05-140">OpenError</span></span>
- <span data-ttu-id="5fa05-141">CloseError</span><span class="sxs-lookup"><span data-stu-id="5fa05-141">CloseError</span></span>
- <span data-ttu-id="5fa05-142">DeviceError</span><span class="sxs-lookup"><span data-stu-id="5fa05-142">DeviceError</span></span>
- <span data-ttu-id="5fa05-143">DeadlockDetected</span><span class="sxs-lookup"><span data-stu-id="5fa05-143">DeadlockDetected</span></span>
- <span data-ttu-id="5fa05-144">InvalidArgument</span><span class="sxs-lookup"><span data-stu-id="5fa05-144">InvalidArgument</span></span>
- <span data-ttu-id="5fa05-145">InvalidData</span><span class="sxs-lookup"><span data-stu-id="5fa05-145">InvalidData</span></span>
- <span data-ttu-id="5fa05-146">InvalidOperation</span><span class="sxs-lookup"><span data-stu-id="5fa05-146">InvalidOperation</span></span>
- <span data-ttu-id="5fa05-147">InvalidResult</span><span class="sxs-lookup"><span data-stu-id="5fa05-147">InvalidResult</span></span>
- <span data-ttu-id="5fa05-148">Invalidartype</span><span class="sxs-lookup"><span data-stu-id="5fa05-148">InvalidType</span></span>
- <span data-ttu-id="5fa05-149">MetadataError</span><span class="sxs-lookup"><span data-stu-id="5fa05-149">MetadataError</span></span>
- <span data-ttu-id="5fa05-150">NotImplemented</span><span class="sxs-lookup"><span data-stu-id="5fa05-150">NotImplemented</span></span>
- <span data-ttu-id="5fa05-151">Não instalado</span><span class="sxs-lookup"><span data-stu-id="5fa05-151">NotInstalled</span></span>
- <span data-ttu-id="5fa05-152">ObjectNotFound</span><span class="sxs-lookup"><span data-stu-id="5fa05-152">ObjectNotFound</span></span>
- <span data-ttu-id="5fa05-153">OperationStopped</span><span class="sxs-lookup"><span data-stu-id="5fa05-153">OperationStopped</span></span>
- <span data-ttu-id="5fa05-154">OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="5fa05-154">OperationTimeout</span></span>
- <span data-ttu-id="5fa05-155">SyntaxError</span><span class="sxs-lookup"><span data-stu-id="5fa05-155">SyntaxError</span></span>
- <span data-ttu-id="5fa05-156">ParserError</span><span class="sxs-lookup"><span data-stu-id="5fa05-156">ParserError</span></span>
- <span data-ttu-id="5fa05-157">PermissionDenied</span><span class="sxs-lookup"><span data-stu-id="5fa05-157">PermissionDenied</span></span>
- <span data-ttu-id="5fa05-158">ResourceBusy</span><span class="sxs-lookup"><span data-stu-id="5fa05-158">ResourceBusy</span></span>
- <span data-ttu-id="5fa05-159">ResourceExists</span><span class="sxs-lookup"><span data-stu-id="5fa05-159">ResourceExists</span></span>
- <span data-ttu-id="5fa05-160">ResourceUnavailable</span><span class="sxs-lookup"><span data-stu-id="5fa05-160">ResourceUnavailable</span></span>
- <span data-ttu-id="5fa05-161">ReadError</span><span class="sxs-lookup"><span data-stu-id="5fa05-161">ReadError</span></span>
- <span data-ttu-id="5fa05-162">WriteError</span><span class="sxs-lookup"><span data-stu-id="5fa05-162">WriteError</span></span>
- <span data-ttu-id="5fa05-163">FromStdErr</span><span class="sxs-lookup"><span data-stu-id="5fa05-163">FromStdErr</span></span>
- <span data-ttu-id="5fa05-164">SecurityError</span><span class="sxs-lookup"><span data-stu-id="5fa05-164">SecurityError</span></span>
- <span data-ttu-id="5fa05-165">ProtocolError</span><span class="sxs-lookup"><span data-stu-id="5fa05-165">ProtocolError</span></span>
- <span data-ttu-id="5fa05-166">ConnectionError</span><span class="sxs-lookup"><span data-stu-id="5fa05-166">ConnectionError</span></span>
- <span data-ttu-id="5fa05-167">AuthenticationError</span><span class="sxs-lookup"><span data-stu-id="5fa05-167">AuthenticationError</span></span>
- <span data-ttu-id="5fa05-168">LimitsExceeded</span><span class="sxs-lookup"><span data-stu-id="5fa05-168">LimitsExceeded</span></span>
- <span data-ttu-id="5fa05-169">QuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="5fa05-169">QuotaExceeded</span></span>
- <span data-ttu-id="5fa05-170">Não habilitado</span><span class="sxs-lookup"><span data-stu-id="5fa05-170">NotEnabled</span></span>

<span data-ttu-id="5fa05-171">Para obter informações sobre as categorias de erro, consulte [Enumeração ErrorCategory](https://go.microsoft.com/fwlink/?LinkId=143600).</span><span class="sxs-lookup"><span data-stu-id="5fa05-171">For information about the error categories, see [ErrorCategory Enumeration](https://go.microsoft.com/fwlink/?LinkId=143600).</span></span>

```yaml
Type: System.Management.Automation.ErrorCategory
Parameter Sets: NoException, WithException
Aliases:
Accepted values: NotSpecified, OpenError, CloseError, DeviceError, DeadlockDetected, InvalidArgument, InvalidData, InvalidOperation, InvalidResult, InvalidType, MetadataError, NotImplemented, NotInstalled, ObjectNotFound, OperationStopped, OperationTimeout, SyntaxError, ParserError, PermissionDenied, ResourceBusy, ResourceExists, ResourceUnavailable, ReadError, WriteError, FromStdErr, SecurityError, ProtocolError, ConnectionError, AuthenticationError, LimitsExceeded, QuotaExceeded, NotEnabled

Required: False
Position: Named
Default value: NotSpecified
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fa05-172">-CategoryActivity</span><span class="sxs-lookup"><span data-stu-id="5fa05-172">-CategoryActivity</span></span>

<span data-ttu-id="5fa05-173">Especifica a ação que causou o erro.</span><span class="sxs-lookup"><span data-stu-id="5fa05-173">Specifies the action that caused the error.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Activity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fa05-174">-CategoryReason</span><span class="sxs-lookup"><span data-stu-id="5fa05-174">-CategoryReason</span></span>

<span data-ttu-id="5fa05-175">Especifica como ou por que a atividade causou o erro.</span><span class="sxs-lookup"><span data-stu-id="5fa05-175">Specifies how or why the activity caused the error.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Reason

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fa05-176">-CategoryTargetName</span><span class="sxs-lookup"><span data-stu-id="5fa05-176">-CategoryTargetName</span></span>

<span data-ttu-id="5fa05-177">Especifica o nome do objeto que estava sendo processado quando o erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="5fa05-177">Specifies the name of the object that was being processed when the error occurred.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fa05-178">-CategoryTargetType</span><span class="sxs-lookup"><span data-stu-id="5fa05-178">-CategoryTargetType</span></span>

<span data-ttu-id="5fa05-179">Especifica o tipo do objeto que estava sendo processado quando o erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="5fa05-179">Specifies the type of the object that was being processed when the error occurred.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TargetType

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fa05-180">-ErrorID</span><span class="sxs-lookup"><span data-stu-id="5fa05-180">-ErrorId</span></span>

<span data-ttu-id="5fa05-181">Especifica uma cadeia de caracteres de identificação para identificar o erro.</span><span class="sxs-lookup"><span data-stu-id="5fa05-181">Specifies an ID string to identify the error.</span></span> <span data-ttu-id="5fa05-182">A cadeia de caracteres deve ser exclusiva para o erro.</span><span class="sxs-lookup"><span data-stu-id="5fa05-182">The string should be unique to the error.</span></span>

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fa05-183">-ErrorRecord</span><span class="sxs-lookup"><span data-stu-id="5fa05-183">-ErrorRecord</span></span>

<span data-ttu-id="5fa05-184">Especifica um objeto de registro de erro que representa o erro.</span><span class="sxs-lookup"><span data-stu-id="5fa05-184">Specifies an error record object that represents the error.</span></span> <span data-ttu-id="5fa05-185">Usa as propriedades do objeto para descrever o erro.</span><span class="sxs-lookup"><span data-stu-id="5fa05-185">Use the properties of the object to describe the error.</span></span>

<span data-ttu-id="5fa05-186">Para criar um objeto de registro de erro, use o `New-Object` cmdlet ou obtenha um objeto de registro de erro da matriz na `$Error` variável automática.</span><span class="sxs-lookup"><span data-stu-id="5fa05-186">To create an error record object, use the `New-Object` cmdlet or get an error record object from the array in the `$Error` automatic variable.</span></span>

```yaml
Type: System.Management.Automation.ErrorRecord
Parameter Sets: ErrorRecord
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fa05-187">-Exceção</span><span class="sxs-lookup"><span data-stu-id="5fa05-187">-Exception</span></span>

<span data-ttu-id="5fa05-188">Especifica um objeto de exceção que representa o erro.</span><span class="sxs-lookup"><span data-stu-id="5fa05-188">Specifies an exception object that represents the error.</span></span> <span data-ttu-id="5fa05-189">Usa as propriedades do objeto para descrever o erro.</span><span class="sxs-lookup"><span data-stu-id="5fa05-189">Use the properties of the object to describe the error.</span></span>

<span data-ttu-id="5fa05-190">Para criar um objeto de exceção, use uma tabela de hash ou use o `New-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5fa05-190">To create an exception object, use a hash table or use the `New-Object` cmdlet.</span></span>

```yaml
Type: System.Exception
Parameter Sets: WithException
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fa05-191">-Mensagem</span><span class="sxs-lookup"><span data-stu-id="5fa05-191">-Message</span></span>

<span data-ttu-id="5fa05-192">Especifica o texto da mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="5fa05-192">Specifies the message text of the error.</span></span> <span data-ttu-id="5fa05-193">Se a expressão incluir espaços ou caracteres especiais, coloque-a entre aspas.</span><span class="sxs-lookup"><span data-stu-id="5fa05-193">If the text includes spaces or special characters, enclose it in quotation marks.</span></span> <span data-ttu-id="5fa05-194">Você também pode canalizar uma cadeia de caracteres de mensagem para `Write-Error` .</span><span class="sxs-lookup"><span data-stu-id="5fa05-194">You can also pipe a message string to `Write-Error`.</span></span>

```yaml
Type: System.String
Parameter Sets: NoException, WithException
Aliases: Msg

Required: True (NoException), False (WithException)
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5fa05-195">-Recomendadoaction</span><span class="sxs-lookup"><span data-stu-id="5fa05-195">-RecommendedAction</span></span>

<span data-ttu-id="5fa05-196">Especifica a ação que o usuário deve executar para resolver ou impedir o erro.</span><span class="sxs-lookup"><span data-stu-id="5fa05-196">Specifies the action that the user should take to resolve or prevent the error.</span></span>

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

### <span data-ttu-id="5fa05-197">-TargetObject</span><span class="sxs-lookup"><span data-stu-id="5fa05-197">-TargetObject</span></span>

<span data-ttu-id="5fa05-198">Especifica o objeto que estava sendo processado quando o erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="5fa05-198">Specifies the object that was being processed when the error occurred.</span></span> <span data-ttu-id="5fa05-199">Insira o objeto, uma variável que contém o objeto ou um comando que obtém o objeto.</span><span class="sxs-lookup"><span data-stu-id="5fa05-199">Enter the object, a variable that contains the object, or a command that gets the object.</span></span>

```yaml
Type: System.Object
Parameter Sets: NoException, WithException
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5fa05-200">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5fa05-200">CommonParameters</span></span>

<span data-ttu-id="5fa05-201">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5fa05-201">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5fa05-202">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5fa05-202">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5fa05-203">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5fa05-203">INPUTS</span></span>

### <span data-ttu-id="5fa05-204">System.String</span><span class="sxs-lookup"><span data-stu-id="5fa05-204">System.String</span></span>

<span data-ttu-id="5fa05-205">É possível canalizar uma cadeia de caracteres que contém uma mensagem de erro para `Write-Error` .</span><span class="sxs-lookup"><span data-stu-id="5fa05-205">You can pipe a string that contains an error message to `Write-Error`.</span></span>

## <span data-ttu-id="5fa05-206">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5fa05-206">OUTPUTS</span></span>

### <span data-ttu-id="5fa05-207">Objeto de erro</span><span class="sxs-lookup"><span data-stu-id="5fa05-207">Error object</span></span>

<span data-ttu-id="5fa05-208">`Write-Error` grava somente no fluxo de erro.</span><span class="sxs-lookup"><span data-stu-id="5fa05-208">`Write-Error` writes only to the error stream.</span></span> <span data-ttu-id="5fa05-209">Ele não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="5fa05-209">It does not return any objects.</span></span>

## <span data-ttu-id="5fa05-210">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5fa05-210">NOTES</span></span>

<span data-ttu-id="5fa05-211">`Write-Error` Não altera o valor da `$?` variável automática, portanto, não sinaliza uma condição de erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="5fa05-211">`Write-Error` does not change the value of the `$?` automatic variable, therefore it does not signal a terminating error condition.</span></span> <span data-ttu-id="5fa05-212">Para sinalizar um erro de encerramento, use o método [$PSCmdlet. WriteError ()](/dotnet/api/system.management.automation.cmdlet.writeerror) .</span><span class="sxs-lookup"><span data-stu-id="5fa05-212">To signal a terminating error, use the [$PSCmdlet.WriteError()](/dotnet/api/system.management.automation.cmdlet.writeerror) method.</span></span>

## <span data-ttu-id="5fa05-213">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5fa05-213">RELATED LINKS</span></span>

[<span data-ttu-id="5fa05-214">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="5fa05-214">about_Automatic_Variables</span></span>](../microsoft.powershell.core/about/about_automatic_variables.md)

[<span data-ttu-id="5fa05-215">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="5fa05-215">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="5fa05-216">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="5fa05-216">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="5fa05-217">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="5fa05-217">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="5fa05-218">Write-Host</span><span class="sxs-lookup"><span data-stu-id="5fa05-218">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="5fa05-219">Write-Output</span><span class="sxs-lookup"><span data-stu-id="5fa05-219">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="5fa05-220">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="5fa05-220">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="5fa05-221">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="5fa05-221">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="5fa05-222">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="5fa05-222">Write-Warning</span></span>](Write-Warning.md)
