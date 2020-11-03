---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: b76fc092046a29dcad52f755794fd55dd84ac675
ms.sourcegitcommit: 57df49488015e7ac17ff1df402a94441aa6d6064
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2020
ms.locfileid: "93194815"
---
# <span data-ttu-id="e6d6d-103">Read-Host</span><span class="sxs-lookup"><span data-stu-id="e6d6d-103">Read-Host</span></span>

## <span data-ttu-id="e6d6d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e6d6d-104">SYNOPSIS</span></span>
<span data-ttu-id="e6d6d-105">Lê uma linha de entrada do console.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-105">Reads a line of input from the console.</span></span>

## <span data-ttu-id="e6d6d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e6d6d-106">SYNTAX</span></span>

### <span data-ttu-id="e6d6d-107">AsString (padrão)</span><span class="sxs-lookup"><span data-stu-id="e6d6d-107">AsString (Default)</span></span>

```
Read-Host [[-Prompt] <Object>] [-MaskInput] [<CommonParameters>]
```

### <span data-ttu-id="e6d6d-108">AsSecureString</span><span class="sxs-lookup"><span data-stu-id="e6d6d-108">AsSecureString</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="e6d6d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6d6d-109">DESCRIPTION</span></span>

<span data-ttu-id="e6d6d-110">O `Read-Host` cmdlet lê uma linha de entrada do console.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-110">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="e6d6d-111">Você pode usá-lo para solicitar uma entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-111">You can use it to prompt a user for input.</span></span> <span data-ttu-id="e6d6d-112">Como você pode salvar a entrada como uma cadeia de caracteres segura, use esse cmdlet para solicitar aos usuários para proteger os dados, como senhas, bem como dados compartilhados.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-112">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

## <span data-ttu-id="e6d6d-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e6d6d-113">EXAMPLES</span></span>

### <span data-ttu-id="e6d6d-114">Exemplo 1: salvar a entrada do console em uma variável</span><span class="sxs-lookup"><span data-stu-id="e6d6d-114">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="e6d6d-115">Este exemplo exibe a cadeia de caracteres "Insira sua idade:" como um prompt.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-115">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="e6d6d-116">Quando um valor é inserido e a tecla Enter é pressionada, o valor é armazenado na `$Age` variável.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-116">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="e6d6d-117">Exemplo 2: salvar a entrada do console como uma cadeia de caracteres segura</span><span class="sxs-lookup"><span data-stu-id="e6d6d-117">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="e6d6d-118">Este exemplo exibe a cadeia de caracteres "Insira uma senha:" como um prompt.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-118">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="e6d6d-119">Como um valor está sendo inserido, os asteriscos ( `*` ) aparecem no console no lugar da entrada.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-119">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="e6d6d-120">Quando a tecla Enter é pressionada, o valor é armazenado como um objeto **SecureString** na `$pwd_secure_string` variável.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-120">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

### <span data-ttu-id="e6d6d-121">Exemplo 3: mascarar entrada e como uma cadeia de caracteres de texto sem formatação</span><span class="sxs-lookup"><span data-stu-id="e6d6d-121">Example 3: Mask input and as a plaintext string</span></span>

<span data-ttu-id="e6d6d-122">Este exemplo exibe a cadeia de caracteres "Insira uma senha:" como um prompt.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-122">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="e6d6d-123">Como um valor está sendo inserido, os asteriscos ( `*` ) aparecem no console no lugar da entrada.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-123">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="e6d6d-124">Quando a tecla Enter é pressionada, o valor é armazenado como um objeto de **cadeia de caracteres** de texto sem formatação na `$pwd_string` variável.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-124">When the Enter key is pressed, the value is stored as a plaintext **String** object in the `$pwd_string` variable.</span></span>

```powershell
$pwd_string = Read-Host "Enter a Password" -MaskInput
```

## <span data-ttu-id="e6d6d-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e6d6d-125">PARAMETERS</span></span>

### <span data-ttu-id="e6d6d-126">-Assegurastring</span><span class="sxs-lookup"><span data-stu-id="e6d6d-126">-AsSecureString</span></span>

<span data-ttu-id="e6d6d-127">Indica que o cmdlet exibe asteriscos ( `*` ) no lugar dos caracteres que o usuário digita como entrada.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-127">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="e6d6d-128">Quando você usa esse parâmetro, a saída do `Read-Host` cmdlet é um objeto **SecureString** ( **System. Security. SecureString** ).</span><span class="sxs-lookup"><span data-stu-id="e6d6d-128">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object ( **System.Security.SecureString** ).</span></span>

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

### <span data-ttu-id="e6d6d-129">-MaskInput</span><span class="sxs-lookup"><span data-stu-id="e6d6d-129">-MaskInput</span></span>

<span data-ttu-id="e6d6d-130">Indica que o cmdlet exibe asteriscos ( `*` ) no lugar dos caracteres que o usuário digita como entrada.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-130">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="e6d6d-131">Quando você usa esse parâmetro, a saída do `Read-Host` cmdlet é um objeto de **cadeia de caracteres** .</span><span class="sxs-lookup"><span data-stu-id="e6d6d-131">When you use this parameter, the output of the `Read-Host` cmdlet is a **String** object.</span></span>
<span data-ttu-id="e6d6d-132">Isso permite que você solicite com segurança uma senha retornada como texto não criptografado em vez de **SecureString** .</span><span class="sxs-lookup"><span data-stu-id="e6d6d-132">This allows you to safely prompt for a password that is returned as plaintext instead of **SecureString** .</span></span>

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

### <span data-ttu-id="e6d6d-133">-Aviso</span><span class="sxs-lookup"><span data-stu-id="e6d6d-133">-Prompt</span></span>

<span data-ttu-id="e6d6d-134">Especifica o texto do aviso.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-134">Specifies the text of the prompt.</span></span>
<span data-ttu-id="e6d6d-135">Digite uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-135">Type a string.</span></span>
<span data-ttu-id="e6d6d-136">Se a cadeia de caracteres incluir espaços, coloque-a entre aspas.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-136">If the string includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="e6d6d-137">O PowerShell acrescenta um sinal de dois-pontos ( `:` ) ao texto inserido.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-137">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

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

### <span data-ttu-id="e6d6d-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e6d6d-138">CommonParameters</span></span>

<span data-ttu-id="e6d6d-139">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e6d6d-140">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e6d6d-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e6d6d-141">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e6d6d-141">INPUTS</span></span>

### <span data-ttu-id="e6d6d-142">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e6d6d-142">None</span></span>

<span data-ttu-id="e6d6d-143">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-143">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="e6d6d-144">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e6d6d-144">OUTPUTS</span></span>

### <span data-ttu-id="e6d6d-145">System. String ou System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="e6d6d-145">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="e6d6d-146">Se o parâmetro **AsSecureString** for usado, `Read-Host` retornará uma **SecureString** .</span><span class="sxs-lookup"><span data-stu-id="e6d6d-146">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString** .</span></span> <span data-ttu-id="e6d6d-147">Caso contrário, ele retornará uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e6d6d-147">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="e6d6d-148">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e6d6d-148">NOTES</span></span>

## <span data-ttu-id="e6d6d-149">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e6d6d-149">RELATED LINKS</span></span>

[<span data-ttu-id="e6d6d-150">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="e6d6d-150">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="e6d6d-151">Get-Host</span><span class="sxs-lookup"><span data-stu-id="e6d6d-151">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="e6d6d-152">Write-Host</span><span class="sxs-lookup"><span data-stu-id="e6d6d-152">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="e6d6d-153">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="e6d6d-153">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
