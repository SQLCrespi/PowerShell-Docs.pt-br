---
ms.date: 07/16/2020
keywords: DSC,powershell,configuração,instalação
title: Recurso Log de DSC
ms.openlocfilehash: bc59bb2670561306a039d024fcff5e0746a659f2
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464019"
---
# <a name="dsc-log-resource"></a><span data-ttu-id="58059-103">Recurso Log de DSC</span><span class="sxs-lookup"><span data-stu-id="58059-103">DSC Log Resource</span></span>

> <span data-ttu-id="58059-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="58059-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="58059-105">O recurso **Log** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para escrever mensagens no log de eventos Microsoft-Windows-Desired State Configuration/Analytic.</span><span class="sxs-lookup"><span data-stu-id="58059-105">The **Log** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to write messages to the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>

## <a name="syntax"></a><span data-ttu-id="58059-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="58059-106">Syntax</span></span>

```Syntax
Log [string] #ResourceName
{
    Message = [string]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

> [!NOTE]
> <span data-ttu-id="58059-107">Por padrão, somente os logs operacionais da DSC são habilitados.</span><span class="sxs-lookup"><span data-stu-id="58059-107">By default only the Operational logs for DSC are enabled.</span></span> <span data-ttu-id="58059-108">Antes que o log Analítico esteja disponível ou visível, ele deve ser habilitado.</span><span class="sxs-lookup"><span data-stu-id="58059-108">Before the Analytic log will be available or visible, it must be enabled.</span></span> <span data-ttu-id="58059-109">Para obter mais informações, veja [Onde estão os logs de eventos da DSC?](../../../troubleshooting/troubleshooting.md#where-are-dsc-event-logs).</span><span class="sxs-lookup"><span data-stu-id="58059-109">For more information, see [Where are DSC Event Logs?](../../../troubleshooting/troubleshooting.md#where-are-dsc-event-logs).</span></span>

## <a name="properties"></a><span data-ttu-id="58059-110">Propriedades</span><span class="sxs-lookup"><span data-stu-id="58059-110">Properties</span></span>

| <span data-ttu-id="58059-111">Propriedade</span><span class="sxs-lookup"><span data-stu-id="58059-111">Property</span></span> |                                                   <span data-ttu-id="58059-112">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="58059-112">Description</span></span>                                                    |
| -------- | ---------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="58059-113">Mensagem</span><span class="sxs-lookup"><span data-stu-id="58059-113">Message</span></span>  | <span data-ttu-id="58059-114">Indica a mensagem que você deseja escreve no log de eventos Microsoft-Windows-Desired State Configuration/Analytic.</span><span class="sxs-lookup"><span data-stu-id="58059-114">Indicates the message you want to write to the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="58059-115">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="58059-115">Common properties</span></span>

|       <span data-ttu-id="58059-116">Propriedade</span><span class="sxs-lookup"><span data-stu-id="58059-116">Property</span></span>       |                                                                                                                                                          <span data-ttu-id="58059-117">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="58059-117">Description</span></span>                                                                                                                                                           |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <span data-ttu-id="58059-118">DependsOn</span><span class="sxs-lookup"><span data-stu-id="58059-118">DependsOn</span></span>            | <span data-ttu-id="58059-119">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="58059-119">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="58059-120">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="58059-120">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
| <span data-ttu-id="58059-121">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="58059-121">PsDscRunAsCredential</span></span> | <span data-ttu-id="58059-122">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="58059-122">Sets the credential for running the entire resource as.</span></span>                                                                                                                                                                                                                                                                        |

> [!NOTE]
> <span data-ttu-id="58059-123">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="58059-123">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="58059-124">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="58059-124">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="58059-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="58059-125">Example</span></span>

<span data-ttu-id="58059-126">O exemplo a seguir mostra como incluir uma mensagem no log de eventos Microsoft-Windows-Desired State Configuration/Analytic.</span><span class="sxs-lookup"><span data-stu-id="58059-126">The following example shows how to include a message in the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>

> [!NOTE]
> <span data-ttu-id="58059-127">Se você executar [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/test-dscconfiguration?view=powershell-5.1) com esse recurso configurado, ele sempre retornará **$false**.</span><span class="sxs-lookup"><span data-stu-id="58059-127">If you run [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/test-dscconfiguration?view=powershell-5.1) with this resource configured, it will always return **$false**.</span></span>

```powershell
Configuration logResourceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    Node localhost
    {
        Log LogExample
        {
            Message = 'This message will appear in the Microsoft-Windows-Desired State Configuration/Analytic event log.'
        }
    }
}
```
