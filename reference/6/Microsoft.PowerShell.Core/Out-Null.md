---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-null?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Null
ms.openlocfilehash: a9d5c47eaf189e37f7f16b11cd48101f7b0e584d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194415"
---
# <span data-ttu-id="aa465-103">Out-Null</span><span class="sxs-lookup"><span data-stu-id="aa465-103">Out-Null</span></span>

## <span data-ttu-id="aa465-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="aa465-104">SYNOPSIS</span></span>
<span data-ttu-id="aa465-105">Oculta a saída em vez de enviá-la pelo pipeline ou exibi-la.</span><span class="sxs-lookup"><span data-stu-id="aa465-105">Hides the output instead of sending it down the pipeline or displaying it.</span></span>

## <span data-ttu-id="aa465-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aa465-106">SYNTAX</span></span>

```
Out-Null [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="aa465-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aa465-107">DESCRIPTION</span></span>

<span data-ttu-id="aa465-108">O cmdlet **out-null** envia sua saída para NULL, em vigor, removendo-a do pipeline e impedindo que a saída seja exibida na tela.</span><span class="sxs-lookup"><span data-stu-id="aa465-108">The **Out-Null** cmdlet sends its output to NULL, in effect, removing it from the pipeline and preventing the output to be displayed at the screen.</span></span>

## <span data-ttu-id="aa465-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="aa465-109">EXAMPLES</span></span>

### <span data-ttu-id="aa465-110">Exemplo 1: excluir saída</span><span class="sxs-lookup"><span data-stu-id="aa465-110">Example 1: Delete output</span></span>

```powershell
Get-ChildItem | Out-Null
```

<span data-ttu-id="aa465-111">Esse comando obtém itens no local/diretório atual, mas sua saída não é passada pelo pipeline nem exibida na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="aa465-111">This command gets items in the current location/directory, but its output is not passed through the pipeline nor displayed at the command line.</span></span>
<span data-ttu-id="aa465-112">Isso é útil para ocultar a saída que você não precisa.</span><span class="sxs-lookup"><span data-stu-id="aa465-112">This is useful for hiding output that you do not need.</span></span>

## <span data-ttu-id="aa465-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aa465-113">PARAMETERS</span></span>

### <span data-ttu-id="aa465-114">-InputObject</span><span class="sxs-lookup"><span data-stu-id="aa465-114">-InputObject</span></span>

<span data-ttu-id="aa465-115">Especifica o objeto a ser enviado para NULL (removido do Pipeline).</span><span class="sxs-lookup"><span data-stu-id="aa465-115">Specifies the object to be sent to NULL (removed from pipeline).</span></span>
<span data-ttu-id="aa465-116">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="aa465-116">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="aa465-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aa465-117">CommonParameters</span></span>

<span data-ttu-id="aa465-118">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aa465-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aa465-119">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="aa465-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aa465-120">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="aa465-120">INPUTS</span></span>

### <span data-ttu-id="aa465-121">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="aa465-121">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="aa465-122">É possível canalizar qualquer objeto para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aa465-122">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="aa465-123">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="aa465-123">OUTPUTS</span></span>

### <span data-ttu-id="aa465-124">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa465-124">None</span></span>

<span data-ttu-id="aa465-125">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="aa465-125">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="aa465-126">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="aa465-126">NOTES</span></span>

* <span data-ttu-id="aa465-127">Os cmdlets que contêm o verbo **out** (os cmdlets **out** ) não têm parâmetros para nomes ou caminhos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="aa465-127">The cmdlets that contain the **Out** verb (the **Out** cmdlets) do not have parameters for names or file paths.</span></span> <span data-ttu-id="aa465-128">Para enviar dados para um cmdlet **out** , use um operador de pipeline (|) para enviar a saída de um comando do PowerShell para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aa465-128">To send data to an **Out** cmdlet, use a pipeline operator (|) to send the output of a PowerShell command to the cmdlet.</span></span> <span data-ttu-id="aa465-129">Você também pode armazenar dados em uma variável e usar o parâmetro *InputObject* para passar os dados para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aa465-129">You can also store data in a variable and use the *InputObject* parameter to pass the data to the cmdlet.</span></span> <span data-ttu-id="aa465-130">Para obter mais informações, consulte os exemplos.</span><span class="sxs-lookup"><span data-stu-id="aa465-130">For more information, see the examples.</span></span>
* <span data-ttu-id="aa465-131">**Out-null** não retorna nenhum objeto de saída.</span><span class="sxs-lookup"><span data-stu-id="aa465-131">**Out-Null** does not return any output objects.</span></span> <span data-ttu-id="aa465-132">Se você canalizar a saída de **out-null** para o cmdlet Get-Member, **Get-Member** relatará que nenhum objeto foi especificado.</span><span class="sxs-lookup"><span data-stu-id="aa465-132">If you pipe the output of **Out-Null** to the Get-Member cmdlet, **Get-Member** reports that no objects have been specified.</span></span>

## <span data-ttu-id="aa465-133">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="aa465-133">RELATED LINKS</span></span>

[<span data-ttu-id="aa465-134">Out-Default</span><span class="sxs-lookup"><span data-stu-id="aa465-134">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="aa465-135">Out-Host</span><span class="sxs-lookup"><span data-stu-id="aa465-135">Out-Host</span></span>](Out-Host.md)
