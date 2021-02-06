---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uiculture?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UICulture
ms.openlocfilehash: 4bd912db3f86ffa8b495faf3e62259f207340938
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603556"
---
# <span data-ttu-id="902d9-102">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="902d9-102">Get-UICulture</span></span>

## <span data-ttu-id="902d9-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="902d9-103">SYNOPSIS</span></span>
<span data-ttu-id="902d9-104">Obtém as configurações de cultura da interface do usuário atuais no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="902d9-104">Gets the current UI culture settings in the operating system.</span></span>

## <span data-ttu-id="902d9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="902d9-105">SYNTAX</span></span>

```
Get-UICulture [<CommonParameters>]
```

## <span data-ttu-id="902d9-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="902d9-106">DESCRIPTION</span></span>

<span data-ttu-id="902d9-107">O `Get-UICulture` cmdlet obtém informações sobre as configurações de cultura da interface do usuário (UI) atual para o Windows.</span><span class="sxs-lookup"><span data-stu-id="902d9-107">The `Get-UICulture` cmdlet gets information about the current user interface (UI) culture settings for Windows.</span></span>
<span data-ttu-id="902d9-108">A cultura da interface do usuário determina quais cadeias de caracteres de texto são usadas para elementos de interface do usuário, como menus e mensagens.</span><span class="sxs-lookup"><span data-stu-id="902d9-108">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span>

<span data-ttu-id="902d9-109">Você também pode usar o `Get-Culture` cmdlet, que obtém a cultura atual no sistema.</span><span class="sxs-lookup"><span data-stu-id="902d9-109">You can also use the `Get-Culture` cmdlet, which gets the current culture on the system.</span></span>
<span data-ttu-id="902d9-110">A cultura determina o formato de exibição de itens como números, moeda e datas.</span><span class="sxs-lookup"><span data-stu-id="902d9-110">The culture determines the display format of items such as numbers, currency, and dates.</span></span>

## <span data-ttu-id="902d9-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="902d9-111">EXAMPLES</span></span>

### <span data-ttu-id="902d9-112">Exemplo 1: obter a cultura da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="902d9-112">Example 1: Get the UI culture</span></span>

```powershell
Get-UICulture
```

<span data-ttu-id="902d9-113">Esse comando obtém as informações de cultura da interface do usuário atuais.</span><span class="sxs-lookup"><span data-stu-id="902d9-113">This command gets the current UI culture information.</span></span>

### <span data-ttu-id="902d9-114">Exemplo 2: obter a cultura da interface do usuário e formatar os resultados</span><span class="sxs-lookup"><span data-stu-id="902d9-114">Example 2: Get the UI culture and format the results</span></span>

```powershell
Get-UICulture | Format-List *
```

<span data-ttu-id="902d9-115">Esse comando exibe os valores de todas as propriedades da atual cultura da interface do usuário em uma lista.</span><span class="sxs-lookup"><span data-stu-id="902d9-115">This command displays the values of all of the properties of the current UI culture in a list.</span></span>

### <span data-ttu-id="902d9-116">Exemplo 3: obter o valor da Propriedade Calendar</span><span class="sxs-lookup"><span data-stu-id="902d9-116">Example 3: Get the value of the Calendar property</span></span>

```powershell
(Get-UICulture).Calendar
```

<span data-ttu-id="902d9-117">Esse comando exibe os valores atuais para a propriedade **Calendar** da cultura da interface do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="902d9-117">This command displays the current values for the **Calendar** property of the current UI culture.</span></span>
<span data-ttu-id="902d9-118">Calendar é apenas uma propriedade da cultura da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="902d9-118">Calendar is just one property of UI culture.</span></span>
<span data-ttu-id="902d9-119">Para ver todas as propriedades, digite `Get-UICulture | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="902d9-119">To see all of the properties, type `Get-UICulture | Get-Member`.</span></span>

### <span data-ttu-id="902d9-120">Exemplo 4: obter o padrão de data abreviada</span><span class="sxs-lookup"><span data-stu-id="902d9-120">Example 4: Get the short date pattern</span></span>

```powershell
(Get-UICulture).DateTimeFormat.ShortDatePattern
```

<span data-ttu-id="902d9-121">Esse comando exibe o padrão de data abreviada para a cultura da interface do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="902d9-121">This command displays the short date pattern for the current UI culture.</span></span>
<span data-ttu-id="902d9-122">Para ver todas as subpropriedades da propriedade **DateTimeFormat** da cultura da interface do usuário, digite `(Get-UICulture).DateTimeFormat | gm` .</span><span class="sxs-lookup"><span data-stu-id="902d9-122">To see all of the subproperties of the **DateTimeFormat** property of the UI culture, type `(Get-UICulture).DateTimeFormat | gm`.</span></span>

## <span data-ttu-id="902d9-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="902d9-123">PARAMETERS</span></span>

### <span data-ttu-id="902d9-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="902d9-124">CommonParameters</span></span>

<span data-ttu-id="902d9-125">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="902d9-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="902d9-126">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="902d9-126">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="902d9-127">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="902d9-127">INPUTS</span></span>

### <span data-ttu-id="902d9-128">Nenhum</span><span class="sxs-lookup"><span data-stu-id="902d9-128">None</span></span>

<span data-ttu-id="902d9-129">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="902d9-129">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="902d9-130">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="902d9-130">OUTPUTS</span></span>

### <span data-ttu-id="902d9-131">System. Globalization. CultureInfo, Microsoft. PowerShell. VistaCultureInfo</span><span class="sxs-lookup"><span data-stu-id="902d9-131">System.Globalization.CultureInfo, Microsoft.PowerShell.VistaCultureInfo</span></span>

<span data-ttu-id="902d9-132">`Get-UICulture` Retorna um objeto que representa a cultura da interface do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="902d9-132">`Get-UICulture` returns an object that represents the current UI culture.</span></span>
<span data-ttu-id="902d9-133">No Windows PowerShell 3,0, ele retorna um objeto **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="902d9-133">In Windows PowerShell 3.0, it returns a **CultureInfo** object.</span></span>
<span data-ttu-id="902d9-134">No Windows PowerShell 2,0, ele retorna um objeto **VistaCultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="902d9-134">In Windows PowerShell 2.0, it returns a **VistaCultureInfo** object.</span></span>

## <span data-ttu-id="902d9-135">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="902d9-135">NOTES</span></span>

- <span data-ttu-id="902d9-136">Você também pode usar as `$PsCulture` `$PsUICulture` variáveis e.</span><span class="sxs-lookup"><span data-stu-id="902d9-136">You can also use the `$PsCulture` and `$PsUICulture` variables.</span></span> <span data-ttu-id="902d9-137">A `$PsCulture` variável armazena o nome da cultura atual e a `$PsUICulture` variável armazena o nome da cultura da interface do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="902d9-137">The `$PsCulture` variable stores the name of the current culture, and the `$PsUICulture` variable stores the name of the current UI culture.</span></span>

## <span data-ttu-id="902d9-138">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="902d9-138">RELATED LINKS</span></span>

