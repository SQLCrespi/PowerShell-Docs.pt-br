---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-printer?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Printer
ms.openlocfilehash: bd9a141537c7f075d3c02827af4694813d6f0db6
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346914"
---
# <span data-ttu-id="de73f-103">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="de73f-103">Out-Printer</span></span>

## <span data-ttu-id="de73f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="de73f-104">SYNOPSIS</span></span>
<span data-ttu-id="de73f-105">Envia a saída para uma impressora.</span><span class="sxs-lookup"><span data-stu-id="de73f-105">Sends output to a printer.</span></span>

## <span data-ttu-id="de73f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="de73f-106">SYNTAX</span></span>

```
Out-Printer [[-Name] <String>] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="de73f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="de73f-107">DESCRIPTION</span></span>

<span data-ttu-id="de73f-108">O `Out-Printer` cmdlet envia a saída para a impressora padrão ou para uma impressora alternativa, se uma for especificada.</span><span class="sxs-lookup"><span data-stu-id="de73f-108">The `Out-Printer` cmdlet sends output to the default printer or to an alternate printer, if one is specified.</span></span>

> [!NOTE]
> <span data-ttu-id="de73f-109">Esse cmdlet foi reintroduzido no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="de73f-109">This cmdlet was reintroduced in PowerShell 7.</span></span> <span data-ttu-id="de73f-110">Esse cmdlet só está disponível em sistemas Windows que dão suporte à área de trabalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="de73f-110">This cmdlet is only available on Windows systems that support the Windows Desktop.</span></span>

## <span data-ttu-id="de73f-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="de73f-111">EXAMPLES</span></span>

### <span data-ttu-id="de73f-112">Exemplo 1 – enviar um arquivo a ser impresso na impressora padrão</span><span class="sxs-lookup"><span data-stu-id="de73f-112">Example 1 - Send a file to be printed on the default printer</span></span>

<span data-ttu-id="de73f-113">Este exemplo mostra como imprimir um arquivo, mesmo que não `Out-Printer` tenha um parâmetro de **caminho** .</span><span class="sxs-lookup"><span data-stu-id="de73f-113">This example shows how to print a file, even though `Out-Printer` does not have a **Path** parameter.</span></span>

```powershell
Get-Content -Path ./readme.txt | Out-Printer
```

<span data-ttu-id="de73f-114">`Get-Content`Obtém o conteúdo do `readme.txt` arquivo no diretório atual e o canaliza para `Out-Printer` o, que o envia para a impressora padrão.</span><span class="sxs-lookup"><span data-stu-id="de73f-114">`Get-Content`gets the contents of the `readme.txt` file in the current directory and pipes it to `Out-Printer`, which sends it to the default printer.</span></span>

### <span data-ttu-id="de73f-115">Exemplo 2: imprimir uma cadeia de caracteres em uma impressora remota</span><span class="sxs-lookup"><span data-stu-id="de73f-115">Example 2: Print a string to a remote printer</span></span>

<span data-ttu-id="de73f-116">Este exemplo imprime na `Hello, World` impressora de **cores PRT-6B** em Server01.</span><span class="sxs-lookup"><span data-stu-id="de73f-116">This example prints `Hello, World` to the **Prt-6B Color** printer on Server01.</span></span>

```powershell
"Hello, World" | Out-Printer -Name "\\Server01\Prt-6B Color"
```

<span data-ttu-id="de73f-117">O parâmetro **Name** seleciona uma impressora específica, em vez do padrão.</span><span class="sxs-lookup"><span data-stu-id="de73f-117">The **Name** parameter selects a specific printer, rather than the default.</span></span>

### <span data-ttu-id="de73f-118">Exemplo 3-imprimir um tópico da ajuda para a impressora padrão</span><span class="sxs-lookup"><span data-stu-id="de73f-118">Example 3 - Print a help topic to the default printer</span></span>

<span data-ttu-id="de73f-119">Este exemplo imprime a versão completa do tópico da ajuda para `Get-CimInstance` .</span><span class="sxs-lookup"><span data-stu-id="de73f-119">This example prints the full version of the Help topic for `Get-CimInstance`.</span></span>

```powershell
$H = Get-Help -Full Get-CimInstance
Out-Printer -InputObject $H
```

<span data-ttu-id="de73f-120">`Get-Help` Obtém a versão completa do tópico da ajuda para `Get-CimInstance` e armazena-a na `$H` variável.</span><span class="sxs-lookup"><span data-stu-id="de73f-120">`Get-Help` gets the full version of the Help topic for `Get-CimInstance` and stores it in the `$H` variable.</span></span> <span data-ttu-id="de73f-121">O parâmetro **InputObject** passa o valor de `$H` para `Out-Printer` .</span><span class="sxs-lookup"><span data-stu-id="de73f-121">The **InputObject** parameter passes the value of `$H` to `Out-Printer`.</span></span>

## <span data-ttu-id="de73f-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="de73f-122">PARAMETERS</span></span>

### <span data-ttu-id="de73f-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="de73f-123">-InputObject</span></span>

<span data-ttu-id="de73f-124">Especifica os objetos a serem enviados para a impressora.</span><span class="sxs-lookup"><span data-stu-id="de73f-124">Specifies the objects to be sent to the printer.</span></span> <span data-ttu-id="de73f-125">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="de73f-125">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="de73f-126">-Name</span><span class="sxs-lookup"><span data-stu-id="de73f-126">-Name</span></span>

<span data-ttu-id="de73f-127">Envia a saída para a impressora especificada.</span><span class="sxs-lookup"><span data-stu-id="de73f-127">Sends the output to the specified printer.</span></span> <span data-ttu-id="de73f-128">O **nome** do parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="de73f-128">The parameter name **Name** is optional.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PrinterName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de73f-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="de73f-129">CommonParameters</span></span>

<span data-ttu-id="de73f-130">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="de73f-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="de73f-131">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="de73f-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="de73f-132">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="de73f-132">INPUTS</span></span>

### <span data-ttu-id="de73f-133">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="de73f-133">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="de73f-134">Você pode canalizar qualquer objeto para `Out-Printer` .</span><span class="sxs-lookup"><span data-stu-id="de73f-134">You can pipe any object to `Out-Printer`.</span></span>

## <span data-ttu-id="de73f-135">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="de73f-135">OUTPUTS</span></span>

### <span data-ttu-id="de73f-136">Nenhum</span><span class="sxs-lookup"><span data-stu-id="de73f-136">None</span></span>

<span data-ttu-id="de73f-137">`Out-Printer` Não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="de73f-137">`Out-Printer` does not return any objects.</span></span>

## <span data-ttu-id="de73f-138">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="de73f-138">NOTES</span></span>

<span data-ttu-id="de73f-139">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="de73f-139">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="de73f-140">Os cmdlets que contêm o `Out` verbo não formatam objetos.</span><span class="sxs-lookup"><span data-stu-id="de73f-140">The cmdlets that contain the `Out` verb do not format objects.</span></span> <span data-ttu-id="de73f-141">Eles apenas os renderizam e os enviam para o destino de exibição especificado.</span><span class="sxs-lookup"><span data-stu-id="de73f-141">They just render them and send them to the specified display destination.</span></span> <span data-ttu-id="de73f-142">Se você enviar um objeto não formatado para um `Out` cmdlet, o cmdlet o enviará a um cmdlet de formatação antes de renderizá-lo.</span><span class="sxs-lookup"><span data-stu-id="de73f-142">If you send an unformatted object to an `Out` cmdlet, the cmdlet sends it to a formatting cmdlet before rendering it.</span></span>

<span data-ttu-id="de73f-143">`Out-Printer` envia dados para a impressora, mas não emite nenhum objeto de saída para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="de73f-143">`Out-Printer` sends data to the printer, but does not emit any output objects to the pipeline.</span></span> <span data-ttu-id="de73f-144">Se você canalizar a saída de `Out-Printer` para `Get-Member` , o `Get-Member` relatará que nenhum objeto foi especificado.</span><span class="sxs-lookup"><span data-stu-id="de73f-144">If you pipe the output of `Out-Printer` to `Get-Member`, `Get-Member` reports that no objects have been specified.</span></span>

## <span data-ttu-id="de73f-145">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="de73f-145">RELATED LINKS</span></span>

[<span data-ttu-id="de73f-146">Out-File</span><span class="sxs-lookup"><span data-stu-id="de73f-146">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="de73f-147">Out-String</span><span class="sxs-lookup"><span data-stu-id="de73f-147">Out-String</span></span>](Out-String.md)
