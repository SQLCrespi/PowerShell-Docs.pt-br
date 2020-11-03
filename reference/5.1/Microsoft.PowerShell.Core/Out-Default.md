---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-default?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Default
ms.openlocfilehash: 5e434b6af523da25b0128f6d8e85a196eaf09ff2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193529"
---
# <span data-ttu-id="a62d0-103">Out-Default</span><span class="sxs-lookup"><span data-stu-id="a62d0-103">Out-Default</span></span>

## <span data-ttu-id="a62d0-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a62d0-104">SYNOPSIS</span></span>
<span data-ttu-id="a62d0-105">Envia a saída para o formatador padrão e para o cmdlet de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="a62d0-105">Sends the output to the default formatter and to the default output cmdlet.</span></span>

## <span data-ttu-id="a62d0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a62d0-106">SYNTAX</span></span>

```
Out-Default [-Transcript] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="a62d0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a62d0-107">DESCRIPTION</span></span>

<span data-ttu-id="a62d0-108">O PowerShell é adicionado automaticamente `Out-Default` ao final de cada pipeline.</span><span class="sxs-lookup"><span data-stu-id="a62d0-108">PowerShell automatically adds `Out-Default` to the end of every pipeline.</span></span> <span data-ttu-id="a62d0-109">`Out-Default` decide como formatar e gerar a saída do fluxo de objeto.</span><span class="sxs-lookup"><span data-stu-id="a62d0-109">`Out-Default` decides how to format and output the object stream.</span></span> <span data-ttu-id="a62d0-110">Se o fluxo do objeto for um fluxo de cadeias de caracteres, o `Out-Default` canalizará diretamente para `Out-Host` o qual chamará as APIs apropriadas fornecidas pelo host.</span><span class="sxs-lookup"><span data-stu-id="a62d0-110">If the object stream is a stream of strings, `Out-Default` pipes these directly to `Out-Host` which calls the appropriate APIs provided by the host.</span></span> <span data-ttu-id="a62d0-111">Se o fluxo de objeto não contiver cadeias de caracteres, `Out-Default` o inspecionará o objeto para determinar o que fazer.</span><span class="sxs-lookup"><span data-stu-id="a62d0-111">If the object stream does not contain strings, `Out-Default` inspects the object to determine what to do.</span></span>
<span data-ttu-id="a62d0-112">Em primeiro lugar, ele examina o tipo de objeto e determina se há uma _exibição_ registrada para esse tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="a62d0-112">First it looks at the object type and determines whether there is a registered _view_ for this object type.</span></span>

<span data-ttu-id="a62d0-113">O PowerShell define o esquema XML e um mecanismo (o `Update-FormatData` cmdlet) em que qualquer pessoa pode registrar exibições para um tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="a62d0-113">PowerShell defines XML schema and a mechanism (the `Update-FormatData` cmdlet) where anyone can register views for an object type.</span></span> <span data-ttu-id="a62d0-114">Você pode especificar exibições **amplas** , de **lista** , de **tabela** ou **personalizadas** para qualquer tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="a62d0-114">You can specify **wide** , **list** , **table** , or **custom** views for any object type.</span></span> <span data-ttu-id="a62d0-115">As exibições especificam quais propriedades exibir e como elas devem ser exibidas.</span><span class="sxs-lookup"><span data-stu-id="a62d0-115">The views specify which properties to display and how they should be displayed.</span></span> <span data-ttu-id="a62d0-116">Se uma exibição for registrada, ela definirá qual formatador usar.</span><span class="sxs-lookup"><span data-stu-id="a62d0-116">If a view is registered, it defines which formatter to use.</span></span> <span data-ttu-id="a62d0-117">Portanto, se a exibição registrada for uma exibição de **tabela** , `Out-Default` o transmitirá os objetos para `Format-Table | Out-Host` .</span><span class="sxs-lookup"><span data-stu-id="a62d0-117">So if the registered view is a **table** view, `Out-Default` streams the objects to `Format-Table | Out-Host`.</span></span> <span data-ttu-id="a62d0-118">`Format-Table` transforma os objetos em um fluxo de registros de formatação (controlados pelos dados na definição da exibição) e `Out-Host` transforma os registros de formatação em chamadas na interface do host.</span><span class="sxs-lookup"><span data-stu-id="a62d0-118">`Format-Table` transforms the objects into a stream of Formatting records (driven by the data in the view definition) and `Out-Host` transforms the formatting records into calls on the Host interface.</span></span>

## <span data-ttu-id="a62d0-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a62d0-119">EXAMPLES</span></span>

### <span data-ttu-id="a62d0-120">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="a62d0-120">Example 1</span></span>

<span data-ttu-id="a62d0-121">Embora esse cmdlet não se destinar a ser executado diretamente pelo usuário final, ele pode ser.</span><span class="sxs-lookup"><span data-stu-id="a62d0-121">While this cmdlet is not intended to be run directly by the end user, it can be.</span></span>

```powershell
Get-Process | Select-Object -First 5 | Out-Default
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     12     2.56       5.20       0.00    7376   0 aesm_service
     48    34.32      18.10      26.64    9320  13 AlertusDesktopAlert
     24    13.97      12.74       0.77   12656  13 ApplicationFrameHost
      8     1.79       4.41       0.00    8180   0 AppVShNotify
      9     1.99       5.07       0.19   19320  13 AppVShNotify
```

## <span data-ttu-id="a62d0-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a62d0-122">PARAMETERS</span></span>

### <span data-ttu-id="a62d0-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a62d0-123">-InputObject</span></span>

<span data-ttu-id="a62d0-124">Aceita entradas para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a62d0-124">Accepts input to the cmdlet.</span></span>

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

### <span data-ttu-id="a62d0-125">-Transcrição</span><span class="sxs-lookup"><span data-stu-id="a62d0-125">-Transcript</span></span>

<span data-ttu-id="a62d0-126">Determina se a saída deve ser enviada aos serviços de transcrição do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a62d0-126">Determines whether the output should be sent to PowerShell's transcription services.</span></span>

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

### <span data-ttu-id="a62d0-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a62d0-127">CommonParameters</span></span>

<span data-ttu-id="a62d0-128">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a62d0-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a62d0-129">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a62d0-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a62d0-130">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a62d0-130">INPUTS</span></span>

## <span data-ttu-id="a62d0-131">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a62d0-131">OUTPUTS</span></span>

## <span data-ttu-id="a62d0-132">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a62d0-132">NOTES</span></span>

## <span data-ttu-id="a62d0-133">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a62d0-133">RELATED LINKS</span></span>

[<span data-ttu-id="a62d0-134">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="a62d0-134">Format-Custom</span></span>](../Microsoft.PowerShell.Utility/Format-Custom.md)

[<span data-ttu-id="a62d0-135">Format-List</span><span class="sxs-lookup"><span data-stu-id="a62d0-135">Format-List</span></span>](../Microsoft.PowerShell.Utility/Format-List.md)

[<span data-ttu-id="a62d0-136">Format-Table</span><span class="sxs-lookup"><span data-stu-id="a62d0-136">Format-Table</span></span>](../Microsoft.PowerShell.Utility/Format-Table.md)

[<span data-ttu-id="a62d0-137">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="a62d0-137">Format-Wide</span></span>](../Microsoft.PowerShell.Utility/Format-Wide.md)

[<span data-ttu-id="a62d0-138">about_Format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="a62d0-138">about_Format.ps1xml</span></span>](About/about_Format.ps1xml.md)

[<span data-ttu-id="a62d0-139">Como a formatação e a saída do PowerShell realmente funcionam</span><span class="sxs-lookup"><span data-stu-id="a62d0-139">How PowerShell Formatting and Outputting REALLY works</span></span>](https://devblogs.microsoft.com/powershell/how-powershell-formatting-and-outputting-really-works/)
