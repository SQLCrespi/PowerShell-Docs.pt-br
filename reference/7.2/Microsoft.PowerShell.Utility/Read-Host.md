---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 2efe75730ef7d35618dc0d1fbf7a8d6f8a5db5ae
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603760"
---
# <span data-ttu-id="e28da-102">Read-Host</span><span class="sxs-lookup"><span data-stu-id="e28da-102">Read-Host</span></span>

## <span data-ttu-id="e28da-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e28da-103">SYNOPSIS</span></span>
<span data-ttu-id="e28da-104">Lê uma linha de entrada do console.</span><span class="sxs-lookup"><span data-stu-id="e28da-104">Reads a line of input from the console.</span></span>

## <span data-ttu-id="e28da-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e28da-105">SYNTAX</span></span>

### <span data-ttu-id="e28da-106">AsString (padrão)</span><span class="sxs-lookup"><span data-stu-id="e28da-106">AsString (Default)</span></span>

```
Read-Host [[-Prompt] <Object>] [-MaskInput] [<CommonParameters>]
```

### <span data-ttu-id="e28da-107">AsSecureString</span><span class="sxs-lookup"><span data-stu-id="e28da-107">AsSecureString</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="e28da-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e28da-108">DESCRIPTION</span></span>

<span data-ttu-id="e28da-109">O `Read-Host` cmdlet lê uma linha de entrada do console.</span><span class="sxs-lookup"><span data-stu-id="e28da-109">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="e28da-110">Você pode usá-lo para solicitar uma entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="e28da-110">You can use it to prompt a user for input.</span></span> <span data-ttu-id="e28da-111">Como você pode salvar a entrada como uma cadeia de caracteres segura, use esse cmdlet para solicitar aos usuários para proteger os dados, como senhas, bem como dados compartilhados.</span><span class="sxs-lookup"><span data-stu-id="e28da-111">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

## <span data-ttu-id="e28da-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e28da-112">EXAMPLES</span></span>

### <span data-ttu-id="e28da-113">Exemplo 1: salvar a entrada do console em uma variável</span><span class="sxs-lookup"><span data-stu-id="e28da-113">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="e28da-114">Este exemplo exibe a cadeia de caracteres "Insira sua idade:" como um prompt.</span><span class="sxs-lookup"><span data-stu-id="e28da-114">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="e28da-115">Quando um valor é inserido e a tecla Enter é pressionada, o valor é armazenado na `$Age` variável.</span><span class="sxs-lookup"><span data-stu-id="e28da-115">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="e28da-116">Exemplo 2: salvar a entrada do console como uma cadeia de caracteres segura</span><span class="sxs-lookup"><span data-stu-id="e28da-116">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="e28da-117">Este exemplo exibe a cadeia de caracteres "Insira uma senha:" como um prompt.</span><span class="sxs-lookup"><span data-stu-id="e28da-117">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="e28da-118">Como um valor está sendo inserido, os asteriscos ( `*` ) aparecem no console no lugar da entrada.</span><span class="sxs-lookup"><span data-stu-id="e28da-118">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="e28da-119">Quando a tecla Enter é pressionada, o valor é armazenado como um objeto **SecureString** na `$pwd_secure_string` variável.</span><span class="sxs-lookup"><span data-stu-id="e28da-119">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

### <span data-ttu-id="e28da-120">Exemplo 3: mascarar entrada e como uma cadeia de caracteres de texto sem formatação</span><span class="sxs-lookup"><span data-stu-id="e28da-120">Example 3: Mask input and as a plaintext string</span></span>

<span data-ttu-id="e28da-121">Este exemplo exibe a cadeia de caracteres "Insira uma senha:" como um prompt.</span><span class="sxs-lookup"><span data-stu-id="e28da-121">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="e28da-122">Como um valor está sendo inserido, os asteriscos ( `*` ) aparecem no console no lugar da entrada.</span><span class="sxs-lookup"><span data-stu-id="e28da-122">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="e28da-123">Quando a tecla Enter é pressionada, o valor é armazenado como um objeto de **cadeia de caracteres** de texto sem formatação na `$pwd_string` variável.</span><span class="sxs-lookup"><span data-stu-id="e28da-123">When the Enter key is pressed, the value is stored as a plaintext **String** object in the `$pwd_string` variable.</span></span>

```powershell
$pwd_string = Read-Host "Enter a Password" -MaskInput
```

## <span data-ttu-id="e28da-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e28da-124">PARAMETERS</span></span>

### <span data-ttu-id="e28da-125">-Assegurastring</span><span class="sxs-lookup"><span data-stu-id="e28da-125">-AsSecureString</span></span>

<span data-ttu-id="e28da-126">Indica que o cmdlet exibe asteriscos ( `*` ) no lugar dos caracteres que o usuário digita como entrada.</span><span class="sxs-lookup"><span data-stu-id="e28da-126">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="e28da-127">Quando você usa esse parâmetro, a saída do `Read-Host` cmdlet é um objeto **SecureString** (**System. Security. SecureString**).</span><span class="sxs-lookup"><span data-stu-id="e28da-127">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object (**System.Security.SecureString**).</span></span>

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

### <span data-ttu-id="e28da-128">-MaskInput</span><span class="sxs-lookup"><span data-stu-id="e28da-128">-MaskInput</span></span>

<span data-ttu-id="e28da-129">Indica que o cmdlet exibe asteriscos ( `*` ) no lugar dos caracteres que o usuário digita como entrada.</span><span class="sxs-lookup"><span data-stu-id="e28da-129">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="e28da-130">Quando você usa esse parâmetro, a saída do `Read-Host` cmdlet é um objeto de **cadeia de caracteres** .</span><span class="sxs-lookup"><span data-stu-id="e28da-130">When you use this parameter, the output of the `Read-Host` cmdlet is a **String** object.</span></span>
<span data-ttu-id="e28da-131">Isso permite que você solicite com segurança uma senha retornada como texto não criptografado em vez de **SecureString**.</span><span class="sxs-lookup"><span data-stu-id="e28da-131">This allows you to safely prompt for a password that is returned as plaintext instead of **SecureString**.</span></span>

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

### <span data-ttu-id="e28da-132">-Aviso</span><span class="sxs-lookup"><span data-stu-id="e28da-132">-Prompt</span></span>

<span data-ttu-id="e28da-133">Especifica o texto do aviso.</span><span class="sxs-lookup"><span data-stu-id="e28da-133">Specifies the text of the prompt.</span></span>
<span data-ttu-id="e28da-134">Digite uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e28da-134">Type a string.</span></span>
<span data-ttu-id="e28da-135">Se a cadeia de caracteres incluir espaços, coloque-a entre aspas.</span><span class="sxs-lookup"><span data-stu-id="e28da-135">If the string includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="e28da-136">O PowerShell acrescenta um sinal de dois-pontos ( `:` ) ao texto inserido.</span><span class="sxs-lookup"><span data-stu-id="e28da-136">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

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

### <span data-ttu-id="e28da-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e28da-137">CommonParameters</span></span>

<span data-ttu-id="e28da-138">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e28da-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e28da-139">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e28da-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e28da-140">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e28da-140">INPUTS</span></span>

### <span data-ttu-id="e28da-141">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e28da-141">None</span></span>

<span data-ttu-id="e28da-142">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e28da-142">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="e28da-143">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e28da-143">OUTPUTS</span></span>

### <span data-ttu-id="e28da-144">System. String ou System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="e28da-144">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="e28da-145">Se o parâmetro **AsSecureString** for usado, `Read-Host` retornará uma **SecureString**.</span><span class="sxs-lookup"><span data-stu-id="e28da-145">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString**.</span></span> <span data-ttu-id="e28da-146">Caso contrário, ele retornará uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e28da-146">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="e28da-147">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e28da-147">NOTES</span></span>

## <span data-ttu-id="e28da-148">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e28da-148">RELATED LINKS</span></span>

[<span data-ttu-id="e28da-149">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="e28da-149">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="e28da-150">Get-Host</span><span class="sxs-lookup"><span data-stu-id="e28da-150">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="e28da-151">Write-Host</span><span class="sxs-lookup"><span data-stu-id="e28da-151">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="e28da-152">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="e28da-152">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
