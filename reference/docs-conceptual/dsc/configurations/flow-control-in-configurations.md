---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Instruções condicionais e loops em configurações
ms.openlocfilehash: 86f75be4a3d1c1760dd6269335431e8ab9fd8d09
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736889"
---
# <a name="conditional-statements-and-loops-in-a-configuration"></a><span data-ttu-id="3c43d-103">Instruções condicionais e loops em uma configuração</span><span class="sxs-lookup"><span data-stu-id="3c43d-103">Conditional statements and loops in a Configuration</span></span>

<span data-ttu-id="3c43d-104">Você pode tornar sua [Configuração](configurations.md) mais dinâmica usando palavras-chave de controle de fluxo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c43d-104">You can make your [Configuration](configurations.md) more dynamic by using PowerShell flow-control keywords.</span></span> <span data-ttu-id="3c43d-105">Este artigo mostra como usar instruções condicionais e loops para tornar a `Configuration` mais dinâmica.</span><span class="sxs-lookup"><span data-stu-id="3c43d-105">This article shows you how you can use conditional statements and loops to make your `Configuration` more dynamic.</span></span> <span data-ttu-id="3c43d-106">Combinar instruções condicionais e loops com [parâmetros](add-parameters-to-a-configuration.md) e [Dados de Configuração](configData.md) proporciona a você mais flexibilidade e controle ao compilar a `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="3c43d-106">Combining conditional statements and loops with [parameters](add-parameters-to-a-configuration.md) and [Configuration Data](configData.md) allows you more flexibility and control when compiling your `Configuration`.</span></span>

<span data-ttu-id="3c43d-107">Assim como uma função ou um bloco de script, é possível usar qualquer recurso de linguagem do PowerShell em uma `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="3c43d-107">Just like a function or a script block, you can use any PowerShell language feature within a `Configuration`.</span></span>
<span data-ttu-id="3c43d-108">As instruções usadas serão avaliadas somente quando você chamar a `Configuration` para compilar um arquivo `.mof`.</span><span class="sxs-lookup"><span data-stu-id="3c43d-108">The statements you use will only be evaluated when you call your `Configuration` to compile a `.mof` file.</span></span> <span data-ttu-id="3c43d-109">Os exemplos abaixo mostram cenários para demonstrar conceitos.</span><span class="sxs-lookup"><span data-stu-id="3c43d-109">The examples below show scenarios to demonstrate concepts.</span></span> <span data-ttu-id="3c43d-110">As instruções condicionais e loops são usados com mais frequência com parâmetros e Dados de Configuração.</span><span class="sxs-lookup"><span data-stu-id="3c43d-110">Conditional statements and loops are more often used with parameters and configuration Data.</span></span>

<span data-ttu-id="3c43d-111">Neste exemplo, o bloco de recurso **Service** recupera o estado atual de um serviço no tempo de compilação para gerar um arquivo `.mof` que mantém seu estado atual.</span><span class="sxs-lookup"><span data-stu-id="3c43d-111">In this  example, the **Service** resource block retrieves the current state of a service at compile time to generate a `.mof` file that maintains its current state.</span></span>

> [!NOTE]
> <span data-ttu-id="3c43d-112">Usar blocos de recurso dinâmicos inviabiliza a eficácia do Intellisense.</span><span class="sxs-lookup"><span data-stu-id="3c43d-112">Using dynamic Resource blocks will preempt the effectiveness of Intellisense.</span></span> <span data-ttu-id="3c43d-113">O analisador do PowerShell não pode determinar se os valores especificados são aceitáveis até que a `Configuration` seja compilada.</span><span class="sxs-lookup"><span data-stu-id="3c43d-113">The PowerShell parser cannot determine if the values specified are acceptable until the `Configuration` is compiled.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        Service Spooler
        {
            Name = "Spooler"
            State = $(Get-Service -Name 'spooler').Status
            StartType = $(Get-Service -Name 'spooler').StartType
        }
    }
}
```

<span data-ttu-id="3c43d-114">Além disso, você pode criar um bloco de recurso **Service** para cada serviço no computador atual usando um loop `foreach`.</span><span class="sxs-lookup"><span data-stu-id="3c43d-114">Additionally, you could create a **Service** resource block for every service on the current machine using a `foreach` loop.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        foreach ($service in $(Get-Service))
        {
            Service $service.Name
            {
                Name = $service.Name
                State = $service.Status
                StartType = $service.StartType
            }
        }
    }
}
```

<span data-ttu-id="3c43d-115">Também é possível criar uma `Configuration` somente para computadores que estão online usando uma instrução `if`.</span><span class="sxs-lookup"><span data-stu-id="3c43d-115">You could also create a `Configuration` only for machines that are online by using an `if` statement.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration

    foreach ($computer in @('Server01', 'Server02', 'Server03'))
    {
        if (Test-Connection -ComputerName $computer)
        {
            Node $computer
            {
                Service "Spooler"
                {
                    Name = "Spooler"
                    State = "Started"
                }
            }
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="3c43d-116">Os blocos de recurso dinâmicos nos exemplos acima fazem referência ao computador atual.</span><span class="sxs-lookup"><span data-stu-id="3c43d-116">The dynamic resource blocks in the above examples reference the current machine.</span></span> <span data-ttu-id="3c43d-117">Nesse caso, esse seria o computador no qual você cria a `Configuration`, e não o Nó de destino.</span><span class="sxs-lookup"><span data-stu-id="3c43d-117">In this instance, that would be the machine you are authoring the `Configuration` on, not the target Node.</span></span>

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a><span data-ttu-id="3c43d-118">Resumo</span><span class="sxs-lookup"><span data-stu-id="3c43d-118">Summary</span></span>

<span data-ttu-id="3c43d-119">Resumindo, você pode usar qualquer recurso de linguagem do PowerShell em uma `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="3c43d-119">In summary, you can use any PowerShell language feature within a `Configuration`.</span></span>

<span data-ttu-id="3c43d-120">Isso inclui itens como:</span><span class="sxs-lookup"><span data-stu-id="3c43d-120">This includes things like:</span></span>

- <span data-ttu-id="3c43d-121">Objetos personalizados</span><span class="sxs-lookup"><span data-stu-id="3c43d-121">Custom Objects</span></span>
- <span data-ttu-id="3c43d-122">Tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="3c43d-122">Hashtables</span></span>
- <span data-ttu-id="3c43d-123">Manipulação da cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3c43d-123">String manipulation</span></span>
- <span data-ttu-id="3c43d-124">Comunicação remota</span><span class="sxs-lookup"><span data-stu-id="3c43d-124">Remoting</span></span>
- <span data-ttu-id="3c43d-125">WMI e CIM</span><span class="sxs-lookup"><span data-stu-id="3c43d-125">WMI and CIM</span></span>
- <span data-ttu-id="3c43d-126">Objetos do ActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="3c43d-126">ActiveDirectory objects</span></span>
- <span data-ttu-id="3c43d-127">e mais...</span><span class="sxs-lookup"><span data-stu-id="3c43d-127">and more...</span></span>

<span data-ttu-id="3c43d-128">Qualquer código do PowerShell definido em uma `Configuration` será avaliado no tempo de compilação, mas você também pode colocar o código no script que contém sua `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="3c43d-128">Any PowerShell code defined in a `Configuration` is evaluated at compile time, but you can also place code in the script containing your `Configuration`.</span></span> <span data-ttu-id="3c43d-129">Qualquer código fora do bloco de `Configuration` será executado quando você importar sua `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="3c43d-129">Any code outside of the `Configuration` block is executed when you import your `Configuration`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c43d-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="3c43d-130">See also</span></span>

- [<span data-ttu-id="3c43d-131">Adicionar parâmetros a uma configuração</span><span class="sxs-lookup"><span data-stu-id="3c43d-131">Add parameters to a Configuration</span></span>](add-parameters-to-a-configuration.md)
- [<span data-ttu-id="3c43d-132">Separar dados de configuração das Configurações</span><span class="sxs-lookup"><span data-stu-id="3c43d-132">Separate Configuration data from Configurations</span></span>](configData.md)
