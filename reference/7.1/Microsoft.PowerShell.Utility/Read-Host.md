---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 1c799a5b0f9041d285ce0e83a98582d6888c607e
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685299"
---
# <span data-ttu-id="2de42-103">Read-Host</span><span class="sxs-lookup"><span data-stu-id="2de42-103">Read-Host</span></span>

## <span data-ttu-id="2de42-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2de42-104">SYNOPSIS</span></span>
<span data-ttu-id="2de42-105">Lê uma linha de entrada do console.</span><span class="sxs-lookup"><span data-stu-id="2de42-105">Reads a line of input from the console.</span></span>

## <span data-ttu-id="2de42-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2de42-106">SYNTAX</span></span>

### <span data-ttu-id="2de42-107">AsString (padrão)</span><span class="sxs-lookup"><span data-stu-id="2de42-107">AsString (Default)</span></span>

```
Read-Host [[-Prompt] <Object>] [-MaskInput] [<CommonParameters>]
```

### <span data-ttu-id="2de42-108">AsSecureString</span><span class="sxs-lookup"><span data-stu-id="2de42-108">AsSecureString</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="2de42-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2de42-109">DESCRIPTION</span></span>

<span data-ttu-id="2de42-110">O `Read-Host` cmdlet lê uma linha de entrada do console.</span><span class="sxs-lookup"><span data-stu-id="2de42-110">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="2de42-111">Você pode usá-lo para solicitar uma entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="2de42-111">You can use it to prompt a user for input.</span></span> <span data-ttu-id="2de42-112">Como você pode salvar a entrada como uma cadeia de caracteres segura, use esse cmdlet para solicitar aos usuários para proteger os dados, como senhas, bem como dados compartilhados.</span><span class="sxs-lookup"><span data-stu-id="2de42-112">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

> [!NOTE]
> <span data-ttu-id="2de42-113">`Read-Host` tem um limite de 1022 caracteres que ele pode aceitar como entrada de um usuário.</span><span class="sxs-lookup"><span data-stu-id="2de42-113">`Read-Host` has a limit of 1022 characters it can accept as input from a user.</span></span>

## <span data-ttu-id="2de42-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2de42-114">EXAMPLES</span></span>

### <span data-ttu-id="2de42-115">Exemplo 1: salvar a entrada do console em uma variável</span><span class="sxs-lookup"><span data-stu-id="2de42-115">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="2de42-116">Este exemplo exibe a cadeia de caracteres "Insira sua idade:" como um prompt.</span><span class="sxs-lookup"><span data-stu-id="2de42-116">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="2de42-117">Quando um valor é inserido e a tecla Enter é pressionada, o valor é armazenado na `$Age` variável.</span><span class="sxs-lookup"><span data-stu-id="2de42-117">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="2de42-118">Exemplo 2: salvar a entrada do console como uma cadeia de caracteres segura</span><span class="sxs-lookup"><span data-stu-id="2de42-118">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="2de42-119">Este exemplo exibe a cadeia de caracteres "Insira uma senha:" como um prompt.</span><span class="sxs-lookup"><span data-stu-id="2de42-119">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="2de42-120">Como um valor está sendo inserido, os asteriscos ( `*` ) aparecem no console no lugar da entrada.</span><span class="sxs-lookup"><span data-stu-id="2de42-120">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="2de42-121">Quando a tecla Enter é pressionada, o valor é armazenado como um objeto **SecureString** na `$pwd_secure_string` variável.</span><span class="sxs-lookup"><span data-stu-id="2de42-121">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

### <span data-ttu-id="2de42-122">Exemplo 3: mascarar entrada e como uma cadeia de caracteres de texto sem formatação</span><span class="sxs-lookup"><span data-stu-id="2de42-122">Example 3: Mask input and as a plaintext string</span></span>

<span data-ttu-id="2de42-123">Este exemplo exibe a cadeia de caracteres "Insira uma senha:" como um prompt.</span><span class="sxs-lookup"><span data-stu-id="2de42-123">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="2de42-124">Como um valor está sendo inserido, os asteriscos ( `*` ) aparecem no console no lugar da entrada.</span><span class="sxs-lookup"><span data-stu-id="2de42-124">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="2de42-125">Quando a tecla Enter é pressionada, o valor é armazenado como um objeto de **cadeia de caracteres** de texto sem formatação na `$pwd_string` variável.</span><span class="sxs-lookup"><span data-stu-id="2de42-125">When the Enter key is pressed, the value is stored as a plaintext **String** object in the `$pwd_string` variable.</span></span>

```powershell
$pwd_string = Read-Host "Enter a Password" -MaskInput
```

## <span data-ttu-id="2de42-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2de42-126">PARAMETERS</span></span>

### <span data-ttu-id="2de42-127">-Assegurastring</span><span class="sxs-lookup"><span data-stu-id="2de42-127">-AsSecureString</span></span>

<span data-ttu-id="2de42-128">Indica que o cmdlet exibe asteriscos ( `*` ) no lugar dos caracteres que o usuário digita como entrada.</span><span class="sxs-lookup"><span data-stu-id="2de42-128">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="2de42-129">Quando você usa esse parâmetro, a saída do `Read-Host` cmdlet é um objeto **SecureString** (**System. Security. SecureString**).</span><span class="sxs-lookup"><span data-stu-id="2de42-129">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object (**System.Security.SecureString**).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsSecureString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2de42-130">-MaskInput</span><span class="sxs-lookup"><span data-stu-id="2de42-130">-MaskInput</span></span>

<span data-ttu-id="2de42-131">Indica que o cmdlet exibe asteriscos ( `*` ) no lugar dos caracteres que o usuário digita como entrada.</span><span class="sxs-lookup"><span data-stu-id="2de42-131">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="2de42-132">Quando você usa esse parâmetro, a saída do `Read-Host` cmdlet é um objeto de **cadeia de caracteres** .</span><span class="sxs-lookup"><span data-stu-id="2de42-132">When you use this parameter, the output of the `Read-Host` cmdlet is a **String** object.</span></span>
<span data-ttu-id="2de42-133">Isso permite que você solicite com segurança uma senha retornada como texto não criptografado em vez de **SecureString**.</span><span class="sxs-lookup"><span data-stu-id="2de42-133">This allows you to safely prompt for a password that is returned as plaintext instead of **SecureString**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2de42-134">-Aviso</span><span class="sxs-lookup"><span data-stu-id="2de42-134">-Prompt</span></span>

<span data-ttu-id="2de42-135">Especifica o texto do aviso.</span><span class="sxs-lookup"><span data-stu-id="2de42-135">Specifies the text of the prompt.</span></span> <span data-ttu-id="2de42-136">Digite uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2de42-136">Type a string.</span></span> <span data-ttu-id="2de42-137">Se a cadeia de caracteres incluir espaços, coloque-a entre aspas.</span><span class="sxs-lookup"><span data-stu-id="2de42-137">If the string includes spaces, enclose it in quotation marks.</span></span> <span data-ttu-id="2de42-138">O PowerShell acrescenta um sinal de dois-pontos ( `:` ) ao texto inserido.</span><span class="sxs-lookup"><span data-stu-id="2de42-138">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2de42-139">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2de42-139">CommonParameters</span></span>

<span data-ttu-id="2de42-140">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2de42-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2de42-141">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2de42-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2de42-142">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2de42-142">INPUTS</span></span>

### <span data-ttu-id="2de42-143">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2de42-143">None</span></span>

<span data-ttu-id="2de42-144">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2de42-144">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2de42-145">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2de42-145">OUTPUTS</span></span>

### <span data-ttu-id="2de42-146">System. String ou System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="2de42-146">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="2de42-147">Se o parâmetro **AsSecureString** for usado, `Read-Host` retornará uma **SecureString**.</span><span class="sxs-lookup"><span data-stu-id="2de42-147">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString**.</span></span> <span data-ttu-id="2de42-148">Caso contrário, ele retornará uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2de42-148">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="2de42-149">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2de42-149">NOTES</span></span>

## <span data-ttu-id="2de42-150">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2de42-150">RELATED LINKS</span></span>

[<span data-ttu-id="2de42-151">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="2de42-151">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="2de42-152">Get-Host</span><span class="sxs-lookup"><span data-stu-id="2de42-152">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="2de42-153">Write-Host</span><span class="sxs-lookup"><span data-stu-id="2de42-153">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="2de42-154">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="2de42-154">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
