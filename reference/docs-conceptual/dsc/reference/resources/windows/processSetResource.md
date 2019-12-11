---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso ProcessSet da DSC
ms.openlocfilehash: 72925d3a9516f5c0040427773a3b1d66034667bb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953123"
---
# <a name="dsc-processset-resource"></a><span data-ttu-id="61098-103">Recurso ProcessSet da DSC</span><span class="sxs-lookup"><span data-stu-id="61098-103">DSC ProcessSet Resource</span></span>

> <span data-ttu-id="61098-104">Aplica-se a: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="61098-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="61098-105">O recurso **ProcessSet** na DSC (Configuração de Estado Desejado) do Windows PowerShell fornece um mecanismo para configurar processos em um nó de destino.</span><span class="sxs-lookup"><span data-stu-id="61098-105">The **ProcessSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to configure processes on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="61098-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="61098-106">Syntax</span></span>

```Syntax
ProcessSet [string] #ResourceName
{
    Path = [string]
    [ Credential = [PSCredential] ]
    [ StandardOutputPath = [string] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="61098-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="61098-107">Properties</span></span>

|<span data-ttu-id="61098-108">Propriedade</span><span class="sxs-lookup"><span data-stu-id="61098-108">Property</span></span> |<span data-ttu-id="61098-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="61098-109">Description</span></span> |
|---|---|
|<span data-ttu-id="61098-110">Caminho</span><span class="sxs-lookup"><span data-stu-id="61098-110">Path</span></span> |<span data-ttu-id="61098-111">O caminho para o executável do processo.</span><span class="sxs-lookup"><span data-stu-id="61098-111">The path to the process executable.</span></span> <span data-ttu-id="61098-112">Se esses forem os nomes dos arquivos executáveis (caminhos não totalmente qualificados), o recurso DSC pesquisará a variável de ambiente `$env:Path` para localizar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="61098-112">If these are the names of the executable files (not fully qualified paths), the DSC resource will search the environment `$env:Path` variable to find the files.</span></span> <span data-ttu-id="61098-113">Se os valores dessa propriedade forem caminhos totalmente qualificados, o DSC não usará a variável de ambiente `$env:Path` para localizar os arquivos e gerará um erro se qualquer um dos caminhos não existir.</span><span class="sxs-lookup"><span data-stu-id="61098-113">If the values of this property are fully qualified paths, DSC will not use the `$env:Path` environment variable to find the files, and will throw an error if any of the paths do not exist.</span></span> <span data-ttu-id="61098-114">Caminhos relativos não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="61098-114">Relative paths are not allowed.</span></span> |
|<span data-ttu-id="61098-115">Credential</span><span class="sxs-lookup"><span data-stu-id="61098-115">Credential</span></span> |<span data-ttu-id="61098-116">Indica as credenciais para iniciar o processo.</span><span class="sxs-lookup"><span data-stu-id="61098-116">Indicates the credentials for starting the process.</span></span> |
|<span data-ttu-id="61098-117">StandardErrorPath</span><span class="sxs-lookup"><span data-stu-id="61098-117">StandardErrorPath</span></span> |<span data-ttu-id="61098-118">O caminho para o qual os processos gravam o erro padrão.</span><span class="sxs-lookup"><span data-stu-id="61098-118">The path to which the processes write standard error.</span></span> <span data-ttu-id="61098-119">Qualquer arquivo existente será substituído.</span><span class="sxs-lookup"><span data-stu-id="61098-119">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="61098-120">StandardInputPath</span><span class="sxs-lookup"><span data-stu-id="61098-120">StandardInputPath</span></span> |<span data-ttu-id="61098-121">O fluxo do qual o processo recebe entrada padrão.</span><span class="sxs-lookup"><span data-stu-id="61098-121">The stream from which the process receives standard input.</span></span> |
|<span data-ttu-id="61098-122">StandardOutputPath</span><span class="sxs-lookup"><span data-stu-id="61098-122">StandardOutputPath</span></span> |<span data-ttu-id="61098-123">O caminho do arquivo para o qual os processos gravam a saída padrão.</span><span class="sxs-lookup"><span data-stu-id="61098-123">The path of the file to which the processes write standard output.</span></span> <span data-ttu-id="61098-124">Qualquer arquivo existente será substituído.</span><span class="sxs-lookup"><span data-stu-id="61098-124">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="61098-125">WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="61098-125">WorkingDirectory</span></span> |<span data-ttu-id="61098-126">O local usado como diretório de trabalho atual para os processos.</span><span class="sxs-lookup"><span data-stu-id="61098-126">The location used as the current working directory for the processes.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="61098-127">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="61098-127">Common properties</span></span>

|<span data-ttu-id="61098-128">Propriedade</span><span class="sxs-lookup"><span data-stu-id="61098-128">Property</span></span> |<span data-ttu-id="61098-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="61098-129">Description</span></span> |
|---|---|
|<span data-ttu-id="61098-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="61098-130">DependsOn</span></span> |<span data-ttu-id="61098-131">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="61098-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="61098-132">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="61098-132">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="61098-133">Ensure</span><span class="sxs-lookup"><span data-stu-id="61098-133">Ensure</span></span> |<span data-ttu-id="61098-134">Especifica se os processos existem.</span><span class="sxs-lookup"><span data-stu-id="61098-134">Specifies whether the processes exists.</span></span> <span data-ttu-id="61098-135">Defina essa propriedade como **Present** para garantir que o processo exista.</span><span class="sxs-lookup"><span data-stu-id="61098-135">Set this property to **Present** to ensure that the process exists.</span></span> <span data-ttu-id="61098-136">Caso contrário, defina-a como **Absent**.</span><span class="sxs-lookup"><span data-stu-id="61098-136">Otherwise, set it to **Absent**.</span></span> <span data-ttu-id="61098-137">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="61098-137">The default value is **Present**.</span></span> |
|<span data-ttu-id="61098-138">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="61098-138">PsDscRunAsCredential</span></span> |<span data-ttu-id="61098-139">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="61098-139">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="61098-140">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="61098-140">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="61098-141">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="61098-141">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>