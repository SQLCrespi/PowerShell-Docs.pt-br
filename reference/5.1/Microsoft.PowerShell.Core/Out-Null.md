---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-null?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Null
ms.openlocfilehash: 5a949629cdf0f0822866863822e82e70fc38d8c2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193527"
---
# <span data-ttu-id="b5612-103">Out-Null</span><span class="sxs-lookup"><span data-stu-id="b5612-103">Out-Null</span></span>

## <span data-ttu-id="b5612-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b5612-104">SYNOPSIS</span></span>
<span data-ttu-id="b5612-105">Oculta a saída em vez de enviá-la pelo pipeline ou exibi-la.</span><span class="sxs-lookup"><span data-stu-id="b5612-105">Hides the output instead of sending it down the pipeline or displaying it.</span></span>

## <span data-ttu-id="b5612-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b5612-106">SYNTAX</span></span>

```
Out-Null [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="b5612-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b5612-107">DESCRIPTION</span></span>
<span data-ttu-id="b5612-108">O cmdlet **out-null** envia sua saída para NULL, em vigor, removendo-a do pipeline e impedindo que a saída seja exibida na tela.</span><span class="sxs-lookup"><span data-stu-id="b5612-108">The **Out-Null** cmdlet sends its output to NULL, in effect, removing it from the pipeline and preventing the output to be displayed at the screen.</span></span> <span data-ttu-id="b5612-109">Isso afeta apenas o fluxo de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="b5612-109">This only affects the standard output stream.</span></span>
<span data-ttu-id="b5612-110">Outros fluxos de saída, como o fluxo de erros, não são afetados.</span><span class="sxs-lookup"><span data-stu-id="b5612-110">Other output streams, like the Error stream are not affected.</span></span> <span data-ttu-id="b5612-111">As exceções serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="b5612-111">Exceptions will be displayed.</span></span> <span data-ttu-id="b5612-112">Isso torna mais fácil testar o comando em busca de erros.</span><span class="sxs-lookup"><span data-stu-id="b5612-112">This makes it easier to test your command for any errors.</span></span>

## <span data-ttu-id="b5612-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b5612-113">EXAMPLES</span></span>

### <span data-ttu-id="b5612-114">Exemplo 1: excluir saída</span><span class="sxs-lookup"><span data-stu-id="b5612-114">Example 1: Delete output</span></span>

```
PS C:\> Get-ChildItem | Out-Null
```

<span data-ttu-id="b5612-115">Esse comando obtém itens no local/diretório atual, mas sua saída não é passada pelo pipeline nem exibida na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="b5612-115">This command gets items in the current location/directory, but its output is not passed through the pipeline nor displayed at the command line.</span></span>
<span data-ttu-id="b5612-116">Isso é útil para ocultar a saída que você não precisa.</span><span class="sxs-lookup"><span data-stu-id="b5612-116">This is useful for hiding output that you do not need.</span></span>

## <span data-ttu-id="b5612-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b5612-117">PARAMETERS</span></span>

### <span data-ttu-id="b5612-118">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b5612-118">-InputObject</span></span>
<span data-ttu-id="b5612-119">Especifica o objeto a ser enviado para NULL (removido do Pipeline).</span><span class="sxs-lookup"><span data-stu-id="b5612-119">Specifies the object to be sent to NULL (removed from pipeline).</span></span>
<span data-ttu-id="b5612-120">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="b5612-120">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="b5612-121">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b5612-121">CommonParameters</span></span>
<span data-ttu-id="b5612-122">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b5612-122">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b5612-123">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b5612-123">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b5612-124">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b5612-124">INPUTS</span></span>

### <span data-ttu-id="b5612-125">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="b5612-125">System.Management.Automation.PSObject</span></span>
<span data-ttu-id="b5612-126">É possível canalizar qualquer objeto para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b5612-126">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="b5612-127">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b5612-127">OUTPUTS</span></span>

### <span data-ttu-id="b5612-128">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b5612-128">None</span></span>
<span data-ttu-id="b5612-129">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="b5612-129">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b5612-130">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b5612-130">NOTES</span></span>

* <span data-ttu-id="b5612-131">Os cmdlets que contêm o verbo **out** (os cmdlets **out** ) não têm parâmetros para nomes ou caminhos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="b5612-131">The cmdlets that contain the **Out** verb (the **Out** cmdlets) do not have parameters for names or file paths.</span></span> <span data-ttu-id="b5612-132">Para enviar dados a um cmdlet **Out** , use um operador de pipeline (|) para enviar a saída de um comando do Windows PowerShell para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b5612-132">To send data to an **Out** cmdlet, use a pipeline operator (|) to send the output of a Windows PowerShell command to the cmdlet.</span></span> <span data-ttu-id="b5612-133">Você também pode armazenar dados em uma variável e usar o parâmetro *InputObject* para passar os dados para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b5612-133">You can also store data in a variable and use the *InputObject* parameter to pass the data to the cmdlet.</span></span> <span data-ttu-id="b5612-134">Para obter mais informações, consulte os exemplos.</span><span class="sxs-lookup"><span data-stu-id="b5612-134">For more information, see the examples.</span></span>
* <span data-ttu-id="b5612-135">**Out-null** não retorna nenhum objeto de saída.</span><span class="sxs-lookup"><span data-stu-id="b5612-135">**Out-Null** does not return any output objects.</span></span> <span data-ttu-id="b5612-136">Se você canalizar a saída de **out-null** para o cmdlet Get-Member, **Get-Member** relatará que nenhum objeto foi especificado.</span><span class="sxs-lookup"><span data-stu-id="b5612-136">If you pipe the output of **Out-Null** to the Get-Member cmdlet, **Get-Member** reports that no objects have been specified.</span></span>

## <span data-ttu-id="b5612-137">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b5612-137">RELATED LINKS</span></span>

[<span data-ttu-id="b5612-138">Out-Default</span><span class="sxs-lookup"><span data-stu-id="b5612-138">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="b5612-139">Out-Host</span><span class="sxs-lookup"><span data-stu-id="b5612-139">Out-Host</span></span>](Out-Host.md)
