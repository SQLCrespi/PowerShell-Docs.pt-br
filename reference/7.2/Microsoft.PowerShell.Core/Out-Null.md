---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-null?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Null
ms.openlocfilehash: fe28f52088a82b93799724de7a7a3f20ce42e36b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596805"
---
# <span data-ttu-id="9dbb2-102">Out-Null</span><span class="sxs-lookup"><span data-stu-id="9dbb2-102">Out-Null</span></span>

## <span data-ttu-id="9dbb2-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9dbb2-103">SYNOPSIS</span></span>
<span data-ttu-id="9dbb2-104">Oculta a saída em vez de enviá-la pelo pipeline ou exibi-la.</span><span class="sxs-lookup"><span data-stu-id="9dbb2-104">Hides the output instead of sending it down the pipeline or displaying it.</span></span>

## <span data-ttu-id="9dbb2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9dbb2-105">SYNTAX</span></span>

```
Out-Null [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="9dbb2-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9dbb2-106">DESCRIPTION</span></span>

<span data-ttu-id="9dbb2-107">O cmdlet **out-null** envia sua saída para NULL, em vigor, removendo-a do pipeline e impedindo que a saída seja exibida na tela.</span><span class="sxs-lookup"><span data-stu-id="9dbb2-107">The **Out-Null** cmdlet sends its output to NULL, in effect, removing it from the pipeline and preventing the output to be displayed at the screen.</span></span>

## <span data-ttu-id="9dbb2-108">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9dbb2-108">EXAMPLES</span></span>

### <span data-ttu-id="9dbb2-109">Exemplo 1: excluir saída</span><span class="sxs-lookup"><span data-stu-id="9dbb2-109">Example 1: Delete output</span></span>

```powershell
Get-ChildItem | Out-Null
```

<span data-ttu-id="9dbb2-110">Esse comando obtém itens no local/diretório atual, mas sua saída não é passada pelo pipeline nem exibida na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="9dbb2-110">This command gets items in the current location/directory, but its output is not passed through the pipeline nor displayed at the command line.</span></span>
<span data-ttu-id="9dbb2-111">Isso é útil para ocultar a saída que você não precisa.</span><span class="sxs-lookup"><span data-stu-id="9dbb2-111">This is useful for hiding output that you do not need.</span></span>

## <span data-ttu-id="9dbb2-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9dbb2-112">PARAMETERS</span></span>

### <span data-ttu-id="9dbb2-113">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9dbb2-113">-InputObject</span></span>

<span data-ttu-id="9dbb2-114">Especifica o objeto a ser enviado para NULL (removido do Pipeline).</span><span class="sxs-lookup"><span data-stu-id="9dbb2-114">Specifies the object to be sent to NULL (removed from pipeline).</span></span>
<span data-ttu-id="9dbb2-115">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="9dbb2-115">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="9dbb2-116">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9dbb2-116">CommonParameters</span></span>

<span data-ttu-id="9dbb2-117">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9dbb2-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9dbb2-118">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9dbb2-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9dbb2-119">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9dbb2-119">INPUTS</span></span>

### <span data-ttu-id="9dbb2-120">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="9dbb2-120">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="9dbb2-121">É possível canalizar qualquer objeto para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9dbb2-121">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="9dbb2-122">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9dbb2-122">OUTPUTS</span></span>

### <span data-ttu-id="9dbb2-123">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9dbb2-123">None</span></span>

<span data-ttu-id="9dbb2-124">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="9dbb2-124">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9dbb2-125">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9dbb2-125">NOTES</span></span>

* <span data-ttu-id="9dbb2-126">Os cmdlets que contêm o verbo **out** (os cmdlets **out** ) não têm parâmetros para nomes ou caminhos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="9dbb2-126">The cmdlets that contain the **Out** verb (the **Out** cmdlets) do not have parameters for names or file paths.</span></span> <span data-ttu-id="9dbb2-127">Para enviar dados para um cmdlet **out** , use um operador de pipeline (|) para enviar a saída de um comando do PowerShell para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9dbb2-127">To send data to an **Out** cmdlet, use a pipeline operator (|) to send the output of a PowerShell command to the cmdlet.</span></span> <span data-ttu-id="9dbb2-128">Você também pode armazenar dados em uma variável e usar o parâmetro *InputObject* para passar os dados para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9dbb2-128">You can also store data in a variable and use the *InputObject* parameter to pass the data to the cmdlet.</span></span> <span data-ttu-id="9dbb2-129">Para obter mais informações, consulte os exemplos.</span><span class="sxs-lookup"><span data-stu-id="9dbb2-129">For more information, see the examples.</span></span>
* <span data-ttu-id="9dbb2-130">**Out-null** não retorna nenhum objeto de saída.</span><span class="sxs-lookup"><span data-stu-id="9dbb2-130">**Out-Null** does not return any output objects.</span></span> <span data-ttu-id="9dbb2-131">Se você canalizar a saída de **out-null** para o cmdlet Get-Member, **Get-Member** relatará que nenhum objeto foi especificado.</span><span class="sxs-lookup"><span data-stu-id="9dbb2-131">If you pipe the output of **Out-Null** to the Get-Member cmdlet, **Get-Member** reports that no objects have been specified.</span></span>

## <span data-ttu-id="9dbb2-132">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9dbb2-132">RELATED LINKS</span></span>

[<span data-ttu-id="9dbb2-133">Out-Default</span><span class="sxs-lookup"><span data-stu-id="9dbb2-133">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="9dbb2-134">Out-Host</span><span class="sxs-lookup"><span data-stu-id="9dbb2-134">Out-Host</span></span>](Out-Host.md)

