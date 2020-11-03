---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 9017d2352f1d2735f21343f4c1194c5e97ce2848
ms.sourcegitcommit: 57df49488015e7ac17ff1df402a94441aa6d6064
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2020
ms.locfileid: "93194816"
---
# <span data-ttu-id="12e97-103">Read-Host</span><span class="sxs-lookup"><span data-stu-id="12e97-103">Read-Host</span></span>

## <span data-ttu-id="12e97-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="12e97-104">SYNOPSIS</span></span>
<span data-ttu-id="12e97-105">Lê uma linha de entrada do console.</span><span class="sxs-lookup"><span data-stu-id="12e97-105">Reads a line of input from the console.</span></span>

## <span data-ttu-id="12e97-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="12e97-106">SYNTAX</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="12e97-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="12e97-107">DESCRIPTION</span></span>

<span data-ttu-id="12e97-108">O `Read-Host` cmdlet lê uma linha de entrada do console.</span><span class="sxs-lookup"><span data-stu-id="12e97-108">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="12e97-109">Você pode usá-lo para solicitar uma entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="12e97-109">You can use it to prompt a user for input.</span></span> <span data-ttu-id="12e97-110">Como você pode salvar a entrada como uma cadeia de caracteres segura, use esse cmdlet para solicitar aos usuários para proteger os dados, como senhas, bem como dados compartilhados.</span><span class="sxs-lookup"><span data-stu-id="12e97-110">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

## <span data-ttu-id="12e97-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="12e97-111">EXAMPLES</span></span>

### <span data-ttu-id="12e97-112">Exemplo 1: salvar a entrada do console em uma variável</span><span class="sxs-lookup"><span data-stu-id="12e97-112">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="12e97-113">Este exemplo exibe a cadeia de caracteres "Insira sua idade:" como um prompt.</span><span class="sxs-lookup"><span data-stu-id="12e97-113">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="12e97-114">Quando um valor é inserido e a tecla Enter é pressionada, o valor é armazenado na `$Age` variável.</span><span class="sxs-lookup"><span data-stu-id="12e97-114">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="12e97-115">Exemplo 2: salvar a entrada do console como uma cadeia de caracteres segura</span><span class="sxs-lookup"><span data-stu-id="12e97-115">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="12e97-116">Este exemplo exibe a cadeia de caracteres "Insira uma senha:" como um prompt.</span><span class="sxs-lookup"><span data-stu-id="12e97-116">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="12e97-117">Como um valor está sendo inserido, os asteriscos ( `*` ) aparecem no console no lugar da entrada.</span><span class="sxs-lookup"><span data-stu-id="12e97-117">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="12e97-118">Quando a tecla Enter é pressionada, o valor é armazenado como um objeto **SecureString** na `$pwd_secure_string` variável.</span><span class="sxs-lookup"><span data-stu-id="12e97-118">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

## <span data-ttu-id="12e97-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="12e97-119">PARAMETERS</span></span>

### <span data-ttu-id="12e97-120">-Assegurastring</span><span class="sxs-lookup"><span data-stu-id="12e97-120">-AsSecureString</span></span>

<span data-ttu-id="12e97-121">Indica que o cmdlet exibe asteriscos ( `*` ) no lugar dos caracteres que o usuário digita como entrada.</span><span class="sxs-lookup"><span data-stu-id="12e97-121">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="12e97-122">Quando você usa esse parâmetro, a saída do `Read-Host` cmdlet é um objeto **SecureString** ( **System. Security. SecureString** ).</span><span class="sxs-lookup"><span data-stu-id="12e97-122">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object ( **System.Security.SecureString** ).</span></span>

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

### <span data-ttu-id="12e97-123">-Aviso</span><span class="sxs-lookup"><span data-stu-id="12e97-123">-Prompt</span></span>

<span data-ttu-id="12e97-124">Especifica o texto do aviso.</span><span class="sxs-lookup"><span data-stu-id="12e97-124">Specifies the text of the prompt.</span></span>
<span data-ttu-id="12e97-125">Digite uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="12e97-125">Type a string.</span></span>
<span data-ttu-id="12e97-126">Se a cadeia de caracteres incluir espaços, coloque-a entre aspas.</span><span class="sxs-lookup"><span data-stu-id="12e97-126">If the string includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="12e97-127">O PowerShell acrescenta um sinal de dois-pontos ( `:` ) ao texto inserido.</span><span class="sxs-lookup"><span data-stu-id="12e97-127">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

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

### <span data-ttu-id="12e97-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="12e97-128">CommonParameters</span></span>

<span data-ttu-id="12e97-129">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="12e97-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="12e97-130">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="12e97-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="12e97-131">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="12e97-131">INPUTS</span></span>

### <span data-ttu-id="12e97-132">Nenhum</span><span class="sxs-lookup"><span data-stu-id="12e97-132">None</span></span>

<span data-ttu-id="12e97-133">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="12e97-133">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="12e97-134">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="12e97-134">OUTPUTS</span></span>

### <span data-ttu-id="12e97-135">System. String ou System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="12e97-135">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="12e97-136">Se o parâmetro **AsSecureString** for usado, `Read-Host` retornará uma **SecureString** .</span><span class="sxs-lookup"><span data-stu-id="12e97-136">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString** .</span></span> <span data-ttu-id="12e97-137">Caso contrário, ele retornará uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="12e97-137">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="12e97-138">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="12e97-138">NOTES</span></span>

## <span data-ttu-id="12e97-139">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="12e97-139">RELATED LINKS</span></span>

[<span data-ttu-id="12e97-140">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="12e97-140">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="12e97-141">Get-Host</span><span class="sxs-lookup"><span data-stu-id="12e97-141">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="12e97-142">Write-Host</span><span class="sxs-lookup"><span data-stu-id="12e97-142">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="12e97-143">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="12e97-143">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
