---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso WindowsProcess de DSC
ms.openlocfilehash: e168cdebb04f7ec83b73a537a5f188299f40d8b7
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71952833"
---
# <a name="dsc-windowsprocess-resource"></a><span data-ttu-id="62985-103">Recurso WindowsProcess de DSC</span><span class="sxs-lookup"><span data-stu-id="62985-103">DSC WindowsProcess Resource</span></span>

> <span data-ttu-id="62985-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="62985-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="62985-105">O recurso **WindowsProcess** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para configurar processos em um nó de destino.</span><span class="sxs-lookup"><span data-stu-id="62985-105">The **WindowsProcess** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to configure processes on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="62985-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="62985-106">Syntax</span></span>

```Syntax
WindowsProcess [string] #ResourceName
{
    Arguments = [string]
    Path = [string]
    [ Credential = [PSCredential] ]
    [ StandardErrorPath = [string] ]
    [ StandardInputPath = [string] ]
    [ StandardOutputPath = [string] ]
    [ WorkingDirectory = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="62985-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="62985-107">Properties</span></span>

|<span data-ttu-id="62985-108">Propriedade</span><span class="sxs-lookup"><span data-stu-id="62985-108">Property</span></span> |<span data-ttu-id="62985-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="62985-109">Description</span></span> |
|---|---|
|<span data-ttu-id="62985-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="62985-110">Arguments</span></span> |<span data-ttu-id="62985-111">Indica uma cadeia de caracteres de argumentos para passar para o processo no estado em que se encontra.</span><span class="sxs-lookup"><span data-stu-id="62985-111">Indicates a string of arguments to pass to the process as-is.</span></span> <span data-ttu-id="62985-112">Se você precisar passar vários argumentos, coloque todos nessa cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="62985-112">If you need to pass several arguments, put them all in this string.</span></span> |
|<span data-ttu-id="62985-113">Caminho</span><span class="sxs-lookup"><span data-stu-id="62985-113">Path</span></span> |<span data-ttu-id="62985-114">O caminho para o executável do processo.</span><span class="sxs-lookup"><span data-stu-id="62985-114">The path to the process executable.</span></span> <span data-ttu-id="62985-115">Se esse for o nome do arquivo do executável (não o caminho totalmente qualificado), o recurso DSC pesquisará a variável de ambiente `$env:Path` para localizar o arquivo executável.</span><span class="sxs-lookup"><span data-stu-id="62985-115">If this the file name of the executable (not the fully qualified path), the DSC resource will search the environment `$env:Path` variable to find the executable file.</span></span> <span data-ttu-id="62985-116">Se o valor dessa propriedade for um caminho totalmente qualificado, o DSC não usará a variável de ambiente `$env:Path` para localizar o arquivo e emitirá um erro se o caminho não existir.</span><span class="sxs-lookup"><span data-stu-id="62985-116">If the value of this property is a fully qualified path, DSC will not use the `$env:Path` variable to find the file, and will throw an error if the path does not exist.</span></span> <span data-ttu-id="62985-117">Caminhos relativos não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="62985-117">Relative paths are not allowed.</span></span> |
|<span data-ttu-id="62985-118">Credencial</span><span class="sxs-lookup"><span data-stu-id="62985-118">Credential</span></span> |<span data-ttu-id="62985-119">Indica as credenciais para iniciar o processo.</span><span class="sxs-lookup"><span data-stu-id="62985-119">Indicates the credentials for starting the process.</span></span> |
|<span data-ttu-id="62985-120">StandardErrorPath</span><span class="sxs-lookup"><span data-stu-id="62985-120">StandardErrorPath</span></span> |<span data-ttu-id="62985-121">Indica o caminho do diretório para escrever o erro padrão.</span><span class="sxs-lookup"><span data-stu-id="62985-121">Indicates the directory path to write the standard error.</span></span> <span data-ttu-id="62985-122">Qualquer arquivo existente será substituído.</span><span class="sxs-lookup"><span data-stu-id="62985-122">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="62985-123">StandardInputPath</span><span class="sxs-lookup"><span data-stu-id="62985-123">StandardInputPath</span></span> |<span data-ttu-id="62985-124">Indica o local de entrada padrão.</span><span class="sxs-lookup"><span data-stu-id="62985-124">Indicates the standard input location.</span></span> |
|<span data-ttu-id="62985-125">StandardOutputPath</span><span class="sxs-lookup"><span data-stu-id="62985-125">StandardOutputPath</span></span> |<span data-ttu-id="62985-126">Indica o local para escrever a saída padrão.</span><span class="sxs-lookup"><span data-stu-id="62985-126">Indicates the location to write the standard output.</span></span> <span data-ttu-id="62985-127">Qualquer arquivo existente será substituído.</span><span class="sxs-lookup"><span data-stu-id="62985-127">Any existing file there will be overwritten.</span></span> |
|<span data-ttu-id="62985-128">WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="62985-128">WorkingDirectory</span></span> |<span data-ttu-id="62985-129">Indica o local que será usado como diretório de trabalho atual para o processo.</span><span class="sxs-lookup"><span data-stu-id="62985-129">Indicates the location that will be used as the current working directory for the process.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="62985-130">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="62985-130">Common properties</span></span>

|<span data-ttu-id="62985-131">Propriedade</span><span class="sxs-lookup"><span data-stu-id="62985-131">Property</span></span> |<span data-ttu-id="62985-132">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="62985-132">Description</span></span> |
|---|---|
|<span data-ttu-id="62985-133">DependsOn</span><span class="sxs-lookup"><span data-stu-id="62985-133">DependsOn</span></span> |<span data-ttu-id="62985-134">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="62985-134">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="62985-135">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="62985-135">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="62985-136">Ensure</span><span class="sxs-lookup"><span data-stu-id="62985-136">Ensure</span></span> |<span data-ttu-id="62985-137">Indica se o processo existe.</span><span class="sxs-lookup"><span data-stu-id="62985-137">Indicates if the process exists.</span></span> <span data-ttu-id="62985-138">Defina essa propriedade como **Present** para garantir que o processo exista.</span><span class="sxs-lookup"><span data-stu-id="62985-138">Set this property to **Present** to ensure that the process exists.</span></span> <span data-ttu-id="62985-139">Caso contrário, defina-a como **Absent**.</span><span class="sxs-lookup"><span data-stu-id="62985-139">Otherwise, set it to **Absent**.</span></span> <span data-ttu-id="62985-140">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="62985-140">The default value is **Present**.</span></span> |
|<span data-ttu-id="62985-141">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="62985-141">PsDscRunAsCredential</span></span> |<span data-ttu-id="62985-142">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="62985-142">Sets the credential for running the entire resource as.</span></span> |