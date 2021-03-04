---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 4f5a5705c726aef7150b734a6265308a5915decb
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685600"
---
# <span data-ttu-id="b976b-103">Read-Host</span><span class="sxs-lookup"><span data-stu-id="b976b-103">Read-Host</span></span>

## <span data-ttu-id="b976b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b976b-104">SYNOPSIS</span></span>
<span data-ttu-id="b976b-105">Lê uma linha de entrada do console.</span><span class="sxs-lookup"><span data-stu-id="b976b-105">Reads a line of input from the console.</span></span>

## <span data-ttu-id="b976b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b976b-106">SYNTAX</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="b976b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b976b-107">DESCRIPTION</span></span>

<span data-ttu-id="b976b-108">O `Read-Host` cmdlet lê uma linha de entrada do console.</span><span class="sxs-lookup"><span data-stu-id="b976b-108">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="b976b-109">Você pode usá-lo para solicitar uma entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="b976b-109">You can use it to prompt a user for input.</span></span> <span data-ttu-id="b976b-110">Como você pode salvar a entrada como uma cadeia de caracteres segura, use esse cmdlet para solicitar aos usuários para proteger os dados, como senhas, bem como dados compartilhados.</span><span class="sxs-lookup"><span data-stu-id="b976b-110">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

> [!NOTE]
> <span data-ttu-id="b976b-111">`Read-Host` tem um limite de 1022 caracteres que ele pode aceitar como entrada de um usuário.</span><span class="sxs-lookup"><span data-stu-id="b976b-111">`Read-Host` has a limit of 1022 characters it can accept as input from a user.</span></span>

## <span data-ttu-id="b976b-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b976b-112">EXAMPLES</span></span>

### <span data-ttu-id="b976b-113">Exemplo 1: salvar a entrada do console em uma variável</span><span class="sxs-lookup"><span data-stu-id="b976b-113">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="b976b-114">Este exemplo exibe a cadeia de caracteres "Insira sua idade:" como um prompt.</span><span class="sxs-lookup"><span data-stu-id="b976b-114">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="b976b-115">Quando um valor é inserido e a tecla Enter é pressionada, o valor é armazenado na `$Age` variável.</span><span class="sxs-lookup"><span data-stu-id="b976b-115">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="b976b-116">Exemplo 2: salvar a entrada do console como uma cadeia de caracteres segura</span><span class="sxs-lookup"><span data-stu-id="b976b-116">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="b976b-117">Este exemplo exibe a cadeia de caracteres "Insira uma senha:" como um prompt.</span><span class="sxs-lookup"><span data-stu-id="b976b-117">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="b976b-118">Como um valor está sendo inserido, os asteriscos ( `*` ) aparecem no console no lugar da entrada.</span><span class="sxs-lookup"><span data-stu-id="b976b-118">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="b976b-119">Quando a tecla Enter é pressionada, o valor é armazenado como um objeto **SecureString** na `$pwd_secure_string` variável.</span><span class="sxs-lookup"><span data-stu-id="b976b-119">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

## <span data-ttu-id="b976b-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b976b-120">PARAMETERS</span></span>

### <span data-ttu-id="b976b-121">-Assegurastring</span><span class="sxs-lookup"><span data-stu-id="b976b-121">-AsSecureString</span></span>

<span data-ttu-id="b976b-122">Indica que o cmdlet exibe asteriscos ( `*` ) no lugar dos caracteres que o usuário digita como entrada.</span><span class="sxs-lookup"><span data-stu-id="b976b-122">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="b976b-123">Quando você usa esse parâmetro, a saída do `Read-Host` cmdlet é um objeto **SecureString** (**System. Security. SecureString**).</span><span class="sxs-lookup"><span data-stu-id="b976b-123">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object (**System.Security.SecureString**).</span></span>

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

### <span data-ttu-id="b976b-124">-Aviso</span><span class="sxs-lookup"><span data-stu-id="b976b-124">-Prompt</span></span>

<span data-ttu-id="b976b-125">Especifica o texto do aviso.</span><span class="sxs-lookup"><span data-stu-id="b976b-125">Specifies the text of the prompt.</span></span> <span data-ttu-id="b976b-126">Digite uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b976b-126">Type a string.</span></span> <span data-ttu-id="b976b-127">Se a cadeia de caracteres incluir espaços, coloque-a entre aspas.</span><span class="sxs-lookup"><span data-stu-id="b976b-127">If the string includes spaces, enclose it in quotation marks.</span></span> <span data-ttu-id="b976b-128">O PowerShell acrescenta um sinal de dois-pontos ( `:` ) ao texto inserido.</span><span class="sxs-lookup"><span data-stu-id="b976b-128">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

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

### <span data-ttu-id="b976b-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b976b-129">CommonParameters</span></span>

<span data-ttu-id="b976b-130">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b976b-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b976b-131">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b976b-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b976b-132">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b976b-132">INPUTS</span></span>

### <span data-ttu-id="b976b-133">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b976b-133">None</span></span>

<span data-ttu-id="b976b-134">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b976b-134">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="b976b-135">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b976b-135">OUTPUTS</span></span>

### <span data-ttu-id="b976b-136">System. String ou System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="b976b-136">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="b976b-137">Se o parâmetro **AsSecureString** for usado, `Read-Host` retornará uma **SecureString**.</span><span class="sxs-lookup"><span data-stu-id="b976b-137">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString**.</span></span> <span data-ttu-id="b976b-138">Caso contrário, ele retornará uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b976b-138">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="b976b-139">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b976b-139">NOTES</span></span>

## <span data-ttu-id="b976b-140">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b976b-140">RELATED LINKS</span></span>

[<span data-ttu-id="b976b-141">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="b976b-141">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="b976b-142">Get-Host</span><span class="sxs-lookup"><span data-stu-id="b976b-142">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="b976b-143">Write-Host</span><span class="sxs-lookup"><span data-stu-id="b976b-143">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="b976b-144">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="b976b-144">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
