---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uiculture?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UICulture
ms.openlocfilehash: cd5bbcae124b1c24438d2821c4da9d71a22d38a2
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192640"
---
# <span data-ttu-id="f1c3e-103">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="f1c3e-103">Get-UICulture</span></span>

## <span data-ttu-id="f1c3e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f1c3e-104">SYNOPSIS</span></span>
<span data-ttu-id="f1c3e-105">Obtém as configurações de cultura da interface do usuário atuais no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="f1c3e-105">Gets the current UI culture settings in the operating system.</span></span>

## <span data-ttu-id="f1c3e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f1c3e-106">SYNTAX</span></span>

```
Get-UICulture [<CommonParameters>]
```

## <span data-ttu-id="f1c3e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f1c3e-107">DESCRIPTION</span></span>

<span data-ttu-id="f1c3e-108">O `Get-UICulture` cmdlet obtém informações sobre as configurações de cultura da interface do usuário (UI) atual para o Windows.</span><span class="sxs-lookup"><span data-stu-id="f1c3e-108">The `Get-UICulture` cmdlet gets information about the current user interface (UI) culture settings for Windows.</span></span>
<span data-ttu-id="f1c3e-109">A cultura da interface do usuário determina quais cadeias de caracteres de texto são usadas para elementos de interface do usuário, como menus e mensagens.</span><span class="sxs-lookup"><span data-stu-id="f1c3e-109">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

<span data-ttu-id="f1c3e-110">Você também pode usar o `Get-Culture` cmdlet, que obtém a cultura atual no sistema.</span><span class="sxs-lookup"><span data-stu-id="f1c3e-110">You can also use the `Get-Culture` cmdlet, which gets the current culture on the system.</span></span>
<span data-ttu-id="f1c3e-111">A cultura determina o formato de exibição de itens como números, moeda e datas.</span><span class="sxs-lookup"><span data-stu-id="f1c3e-111">The culture determines the display format of items such as numbers, currency, and dates.</span></span>

## <span data-ttu-id="f1c3e-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f1c3e-112">EXAMPLES</span></span>

### <span data-ttu-id="f1c3e-113">Exemplo 1: obter a cultura da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="f1c3e-113">Example 1: Get the UI culture</span></span>

```powershell
Get-UICulture
```

<span data-ttu-id="f1c3e-114">Esse comando obtém as informações de cultura da interface do usuário atuais.</span><span class="sxs-lookup"><span data-stu-id="f1c3e-114">This command gets the current UI culture information.</span></span>

### <span data-ttu-id="f1c3e-115">Exemplo 2: obter a cultura da interface do usuário e formatar os resultados</span><span class="sxs-lookup"><span data-stu-id="f1c3e-115">Example 2: Get the UI culture and format the results</span></span>

```powershell
Get-UICulture | Format-List *
```

<span data-ttu-id="f1c3e-116">Esse comando exibe os valores de todas as propriedades da atual cultura da interface do usuário em uma lista.</span><span class="sxs-lookup"><span data-stu-id="f1c3e-116">This command displays the values of all of the properties of the current UI culture in a list.</span></span>

### <span data-ttu-id="f1c3e-117">Exemplo 3: obter o valor da Propriedade Calendar</span><span class="sxs-lookup"><span data-stu-id="f1c3e-117">Example 3: Get the value of the Calendar property</span></span>

```powershell
(Get-UICulture).Calendar
```

<span data-ttu-id="f1c3e-118">Esse comando exibe os valores atuais para a propriedade **Calendar** da cultura da interface do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="f1c3e-118">This command displays the current values for the **Calendar** property of the current UI culture.</span></span>
<span data-ttu-id="f1c3e-119">Calendar é apenas uma propriedade da cultura da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="f1c3e-119">Calendar is just one property of UI culture.</span></span>
<span data-ttu-id="f1c3e-120">Para ver todas as propriedades, digite `Get-UICulture | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="f1c3e-120">To see all of the properties, type `Get-UICulture | Get-Member`.</span></span>

### <span data-ttu-id="f1c3e-121">Exemplo 4: obter o padrão de data abreviada</span><span class="sxs-lookup"><span data-stu-id="f1c3e-121">Example 4: Get the short date pattern</span></span>

```powershell
(Get-UICulture).DateTimeFormat.ShortDatePattern
```

<span data-ttu-id="f1c3e-122">Esse comando exibe o padrão de data abreviada para a cultura da interface do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="f1c3e-122">This command displays the short date pattern for the current UI culture.</span></span>
<span data-ttu-id="f1c3e-123">Para ver todas as subpropriedades da propriedade **DateTimeFormat** da cultura da interface do usuário, digite `(Get-UICulture).DateTimeFormat | gm` .</span><span class="sxs-lookup"><span data-stu-id="f1c3e-123">To see all of the subproperties of the **DateTimeFormat** property of the UI culture, type `(Get-UICulture).DateTimeFormat | gm`.</span></span>

## <span data-ttu-id="f1c3e-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f1c3e-124">PARAMETERS</span></span>

### <span data-ttu-id="f1c3e-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f1c3e-125">CommonParameters</span></span>

<span data-ttu-id="f1c3e-126">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f1c3e-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f1c3e-127">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="f1c3e-127">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="f1c3e-128">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f1c3e-128">INPUTS</span></span>

### <span data-ttu-id="f1c3e-129">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f1c3e-129">None</span></span>

<span data-ttu-id="f1c3e-130">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f1c3e-130">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="f1c3e-131">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f1c3e-131">OUTPUTS</span></span>

### <span data-ttu-id="f1c3e-132">System. Globalization. CultureInfo, Microsoft. PowerShell. VistaCultureInfo</span><span class="sxs-lookup"><span data-stu-id="f1c3e-132">System.Globalization.CultureInfo, Microsoft.PowerShell.VistaCultureInfo</span></span>

<span data-ttu-id="f1c3e-133">`Get-UICulture` Retorna um objeto que representa a cultura da interface do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="f1c3e-133">`Get-UICulture` returns an object that represents the current UI culture.</span></span>
<span data-ttu-id="f1c3e-134">No Windows PowerShell 3,0, ele retorna um objeto **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="f1c3e-134">In Windows PowerShell 3.0, it returns a **CultureInfo** object.</span></span>
<span data-ttu-id="f1c3e-135">No Windows PowerShell 2,0, ele retorna um objeto **VistaCultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="f1c3e-135">In Windows PowerShell 2.0, it returns a **VistaCultureInfo** object.</span></span>

## <span data-ttu-id="f1c3e-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f1c3e-136">NOTES</span></span>

- <span data-ttu-id="f1c3e-137">Você também pode usar as `$PsCulture` `$PsUICulture` variáveis e.</span><span class="sxs-lookup"><span data-stu-id="f1c3e-137">You can also use the `$PsCulture` and `$PsUICulture` variables.</span></span> <span data-ttu-id="f1c3e-138">A `$PsCulture` variável armazena o nome da cultura atual e a `$PsUICulture` variável armazena o nome da cultura da interface do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="f1c3e-138">The `$PsCulture` variable stores the name of the current culture, and the `$PsUICulture` variable stores the name of the current UI culture.</span></span>

## <span data-ttu-id="f1c3e-139">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f1c3e-139">RELATED LINKS</span></span>
