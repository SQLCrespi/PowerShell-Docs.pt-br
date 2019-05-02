---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
ms.openlocfilehash: ec4ae8e4b2ef0ec226cb75607f7aaf34b48f6b76
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085636"
---
# <a name="authoring-improvements-using-powershell-ise"></a><span data-ttu-id="a3222-102">Criando melhorias usando o ISE do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3222-102">Authoring Improvements using PowerShell ISE</span></span>

<span data-ttu-id="a3222-103">Criar configurações DSC no ISE do Windows PowerShell ficou muito mais fácil, graças às seguintes melhorias:</span><span class="sxs-lookup"><span data-stu-id="a3222-103">Authoring DSC configurations in Windows PowerShell ISE is much easier, thanks to the following improvements:</span></span>

- <span data-ttu-id="a3222-104">Liste todos os recursos DSC dentro de um bloco de **configuração** ou de **nó** inserindo **Ctrl+Espaço** em uma linha em branco nele.</span><span class="sxs-lookup"><span data-stu-id="a3222-104">List all DSC resources within a **configuration** block or **node** block by entering **Ctrl+Space** on a blank line within it.</span></span>
- <span data-ttu-id="a3222-105">O preenchimento automático das propriedades de recurso é do tipo **enumeração**.</span><span class="sxs-lookup"><span data-stu-id="a3222-105">Automatic completion on resource properties that are of the **enumeration** type.</span></span>
- <span data-ttu-id="a3222-106">O preenchimento automático da propriedade **DependsOn** dos recursos DSC baseia-se em outras instâncias de recurso na configuração.</span><span class="sxs-lookup"><span data-stu-id="a3222-106">Automatic completion on the **DependsOn** property of DSC resources, based on other resource instances in the configuration.</span></span>
- <span data-ttu-id="a3222-107">Um melhor preenchimento de tabulação dos valores de propriedade de recurso.</span><span class="sxs-lookup"><span data-stu-id="a3222-107">Better tab completion of resource property values.</span></span>

<span data-ttu-id="a3222-108">**Observação:** é necessário ter uma cadeia de caracteres vazia para valores de propriedade de recurso antes de usar Ctrl+Espaço para listar as opções.</span><span class="sxs-lookup"><span data-stu-id="a3222-108">**Note:** You must have an empty string for resource property values before you can use Ctrl+Space to list the options.</span></span> <span data-ttu-id="a3222-109">Pressionar **Tab** percorrerá as opções.</span><span class="sxs-lookup"><span data-stu-id="a3222-109">Pressing **Tab** cycles through options.</span></span>
