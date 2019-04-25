---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: 5919a68c87ae8827a1b97befc653bb74713f33fe
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085772"
---
# <a name="creating-custom-types-using-powershell-classes"></a><span data-ttu-id="4137e-102">Criando tipos personalizados usando classes do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4137e-102">Creating Custom Types using PowerShell Classes</span></span>

<span data-ttu-id="4137e-103">Melhoramos a linguagem do PowerShell para definir classes e outros tipos definidos pelo usuário usando uma sintaxe formal e semântica que são semelhantes a outras linguagens de programação orientada a objeto.</span><span class="sxs-lookup"><span data-stu-id="4137e-103">We’ve improved the PowerShell language for defining classes and other user-defined types by using formal syntax and semantics that are similar to other object-oriented programming languages.</span></span> <span data-ttu-id="4137e-104">O objetivo é permitir que desenvolvedores e profissionais de TI adotem o PowerShell para uma grande variedade de casos de uso, simplificar o desenvolvimento de artefatos do PowerShell (como recursos DSC) e acelerar a cobertura de superfícies de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="4137e-104">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts (such as DSC resources), and accelerate coverage of management surfaces.</span></span>

## <a name="supported-scenarios-in-this-release"></a><span data-ttu-id="4137e-105">Cenários com suporte nesta versão</span><span class="sxs-lookup"><span data-stu-id="4137e-105">Supported scenarios in this release</span></span>

-   <span data-ttu-id="4137e-106">Definir recursos DSC e os tipos associados usando a linguagem do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4137e-106">Define DSC resources and their associated types by using the PowerShell language</span></span>
-   <span data-ttu-id="4137e-107">Definir tipos personalizados no PowerShell usando constructos de programação orientada a objeto conhecidos, como classes, propriedades, métodos, etc.</span><span class="sxs-lookup"><span data-stu-id="4137e-107">Define custom types in PowerShell by using familiar object-oriented programming constructs, such as classes, properties, methods, etc.</span></span>
-   <span data-ttu-id="4137e-108">Suporte à herança com classe no PowerShell e no recurso DSC de classe base</span><span class="sxs-lookup"><span data-stu-id="4137e-108">Inheritance support with class in PowerShell and class base DSC resource</span></span>
-   <span data-ttu-id="4137e-109">Depurar tipos usando a linguagem do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4137e-109">Debug types by using the PowerShell language</span></span>
-   <span data-ttu-id="4137e-110">Gerar e manipular exceções usando mecanismos formais e no nível certo</span><span class="sxs-lookup"><span data-stu-id="4137e-110">Generate and handle exceptions by using formal mechanisms, and at the right level</span></span>
