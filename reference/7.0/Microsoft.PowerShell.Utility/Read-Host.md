---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/18/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 63af2f300f78b4059420ba0aec7e09318729f9e4
ms.sourcegitcommit: 16a02ae47d1a85b01692101aa0aa6e91e1ba398e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104726427"
---
# <span data-ttu-id="470ee-102">Read-Host</span><span class="sxs-lookup"><span data-stu-id="470ee-102">Read-Host</span></span>

## <span data-ttu-id="470ee-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="470ee-103">SYNOPSIS</span></span>
<span data-ttu-id="470ee-104">Lê uma linha de entrada do console.</span><span class="sxs-lookup"><span data-stu-id="470ee-104">Reads a line of input from the console.</span></span>

## <span data-ttu-id="470ee-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="470ee-105">SYNTAX</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="470ee-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="470ee-106">DESCRIPTION</span></span>

<span data-ttu-id="470ee-107">O `Read-Host` cmdlet lê uma linha de entrada do console do (STDIN).</span><span class="sxs-lookup"><span data-stu-id="470ee-107">The `Read-Host` cmdlet reads a line of input from the console (stdin).</span></span> <span data-ttu-id="470ee-108">Você pode usá-lo para solicitar uma entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="470ee-108">You can use it to prompt a user for input.</span></span> <span data-ttu-id="470ee-109">Como você pode salvar a entrada como uma cadeia de caracteres segura, você pode usar esse cmdlet para solicitar aos usuários dados seguros, como senhas.</span><span class="sxs-lookup"><span data-stu-id="470ee-109">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords.</span></span>

> [!NOTE]
> <span data-ttu-id="470ee-110">`Read-Host` tem um limite de 1022 caracteres que ele pode aceitar como entrada de um usuário.</span><span class="sxs-lookup"><span data-stu-id="470ee-110">`Read-Host` has a limit of 1022 characters it can accept as input from a user.</span></span>

## <span data-ttu-id="470ee-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="470ee-111">EXAMPLES</span></span>

### <span data-ttu-id="470ee-112">Exemplo 1: salvar a entrada do console em uma variável</span><span class="sxs-lookup"><span data-stu-id="470ee-112">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="470ee-113">Este exemplo exibe a cadeia de caracteres "Insira sua idade:" como um prompt.</span><span class="sxs-lookup"><span data-stu-id="470ee-113">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="470ee-114">Quando um valor é inserido e a tecla Enter é pressionada, o valor é armazenado na `$Age` variável.</span><span class="sxs-lookup"><span data-stu-id="470ee-114">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="470ee-115">Exemplo 2: salvar a entrada do console como uma cadeia de caracteres segura</span><span class="sxs-lookup"><span data-stu-id="470ee-115">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="470ee-116">Este exemplo exibe a cadeia de caracteres "Insira uma senha:" como um prompt.</span><span class="sxs-lookup"><span data-stu-id="470ee-116">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="470ee-117">Como um valor está sendo inserido, os asteriscos ( `*` ) aparecem no console no lugar da entrada.</span><span class="sxs-lookup"><span data-stu-id="470ee-117">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="470ee-118">Quando a tecla Enter é pressionada, o valor é armazenado como um objeto **SecureString** na `$pwd_secure_string` variável.</span><span class="sxs-lookup"><span data-stu-id="470ee-118">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

## <span data-ttu-id="470ee-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="470ee-119">PARAMETERS</span></span>

### <span data-ttu-id="470ee-120">-Assegurastring</span><span class="sxs-lookup"><span data-stu-id="470ee-120">-AsSecureString</span></span>

<span data-ttu-id="470ee-121">Indica que o cmdlet exibe asteriscos ( `*` ) no lugar dos caracteres que o usuário digita como entrada.</span><span class="sxs-lookup"><span data-stu-id="470ee-121">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="470ee-122">Quando você usa esse parâmetro, a saída do `Read-Host` cmdlet é um objeto **SecureString** (**System. Security. SecureString**).</span><span class="sxs-lookup"><span data-stu-id="470ee-122">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object (**System.Security.SecureString**).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="470ee-123">-Aviso</span><span class="sxs-lookup"><span data-stu-id="470ee-123">-Prompt</span></span>

<span data-ttu-id="470ee-124">Especifica o texto do aviso.</span><span class="sxs-lookup"><span data-stu-id="470ee-124">Specifies the text of the prompt.</span></span> <span data-ttu-id="470ee-125">Digite uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="470ee-125">Type a string.</span></span> <span data-ttu-id="470ee-126">Se a cadeia de caracteres incluir espaços, coloque-a entre aspas.</span><span class="sxs-lookup"><span data-stu-id="470ee-126">If the string includes spaces, enclose it in quotation marks.</span></span> <span data-ttu-id="470ee-127">O PowerShell acrescenta um sinal de dois-pontos ( `:` ) ao texto inserido.</span><span class="sxs-lookup"><span data-stu-id="470ee-127">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

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

### <span data-ttu-id="470ee-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="470ee-128">CommonParameters</span></span>

<span data-ttu-id="470ee-129">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="470ee-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="470ee-130">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="470ee-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="470ee-131">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="470ee-131">INPUTS</span></span>

### <span data-ttu-id="470ee-132">Nenhum</span><span class="sxs-lookup"><span data-stu-id="470ee-132">None</span></span>

<span data-ttu-id="470ee-133">Esse cmdlet não aceita a entrada do pipeline do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="470ee-133">This cmdlet does not accept input from the PowerShell pipeline.</span></span>

## <span data-ttu-id="470ee-134">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="470ee-134">OUTPUTS</span></span>

### <span data-ttu-id="470ee-135">System. String ou System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="470ee-135">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="470ee-136">Se o parâmetro **AsSecureString** for usado, `Read-Host` retornará uma **SecureString**.</span><span class="sxs-lookup"><span data-stu-id="470ee-136">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString**.</span></span> <span data-ttu-id="470ee-137">Caso contrário, ele retornará uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="470ee-137">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="470ee-138">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="470ee-138">NOTES</span></span>

<span data-ttu-id="470ee-139">Esse cmdlet só lê a partir do fluxo stdin do processo de host.</span><span class="sxs-lookup"><span data-stu-id="470ee-139">This cmdlet only reads from the stdin stream of the host process.</span></span> <span data-ttu-id="470ee-140">Normalmente, o fluxo stdin é conectado ao teclado do console do host.</span><span class="sxs-lookup"><span data-stu-id="470ee-140">Usually, the stdin stream is connected to the keyboard of the host console.</span></span>

## <span data-ttu-id="470ee-141">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="470ee-141">RELATED LINKS</span></span>

[<span data-ttu-id="470ee-142">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="470ee-142">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="470ee-143">Get-Host</span><span class="sxs-lookup"><span data-stu-id="470ee-143">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="470ee-144">Write-Host</span><span class="sxs-lookup"><span data-stu-id="470ee-144">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="470ee-145">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="470ee-145">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
