---
ms.date: 07/16/2020
keywords: DSC,powershell,configuração,instalação
title: Recurso Archive da DSC
ms.openlocfilehash: cbe32012c2035fb3e145bd06fadd73cdba93fd3e
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463781"
---
# <a name="dsc-archive-resource"></a><span data-ttu-id="74e61-103">Recurso Archive da DSC</span><span class="sxs-lookup"><span data-stu-id="74e61-103">DSC Archive Resource</span></span>

> <span data-ttu-id="74e61-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="74e61-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="74e61-105">O recurso Archive na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para descompactar arquivos mortos (.zip) em um caminho específico.</span><span class="sxs-lookup"><span data-stu-id="74e61-105">The Archive resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to unpack archive (.zip) files at a specific path.</span></span>

## <a name="syntax"></a><span data-ttu-id="74e61-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="74e61-106">Syntax</span></span>

```Syntax
Archive [string] #ResourceName
{
    Destination = [string]
    Path = [string]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Credential = [PSCredential] ]
    [ Force = [bool] ]
    [ Validate = [bool] ]
    [ Ensure = [string] { Absent | Present } ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="74e61-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="74e61-107">Properties</span></span>

|<span data-ttu-id="74e61-108">Propriedade</span><span class="sxs-lookup"><span data-stu-id="74e61-108">Property</span></span> |<span data-ttu-id="74e61-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="74e61-109">Description</span></span> |
|---|---|
| <span data-ttu-id="74e61-110">Destino</span><span class="sxs-lookup"><span data-stu-id="74e61-110">Destination</span></span> | <span data-ttu-id="74e61-111">Especifica o local onde você deseja garantir que o conteúdo do arquivo seja extraído.</span><span class="sxs-lookup"><span data-stu-id="74e61-111">Specifies the location where you want to ensure the archive contents are extracted.</span></span> |
| <span data-ttu-id="74e61-112">Caminho</span><span class="sxs-lookup"><span data-stu-id="74e61-112">Path</span></span> | <span data-ttu-id="74e61-113">Especifica o caminho de origem do arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="74e61-113">Specifies the source path of the archive file.</span></span> |
| <span data-ttu-id="74e61-114">Checksum (soma de verificação)</span><span class="sxs-lookup"><span data-stu-id="74e61-114">Checksum</span></span> | <span data-ttu-id="74e61-115">Define o tipo que deve ser usado para determinar se dois arquivos são iguais.</span><span class="sxs-lookup"><span data-stu-id="74e61-115">Defines the type to use when determining whether two files are the same.</span></span> <span data-ttu-id="74e61-116">Se **Checksum** não for especificado, somente o nome de arquivo ou diretório será usado para comparação.</span><span class="sxs-lookup"><span data-stu-id="74e61-116">If **Checksum** is not specified, only the file or directory name is used for comparison.</span></span> <span data-ttu-id="74e61-117">Os valores válidos incluem: **SHA-1**, **SHA-256**, **SHA-512**, **createdDate**, **modifiedDate**.</span><span class="sxs-lookup"><span data-stu-id="74e61-117">Valid values include: **SHA-1**, **SHA-256**, **SHA-512**, **createdDate**, **modifiedDate**.</span></span> <span data-ttu-id="74e61-118">Se você especificar **Checksum** sem **Validate**, ocorrerá uma falha na configuração.</span><span class="sxs-lookup"><span data-stu-id="74e61-118">If you specify **Checksum** without **Validate**, the configuration will fail.</span></span> |
| <span data-ttu-id="74e61-119">Credencial</span><span class="sxs-lookup"><span data-stu-id="74e61-119">Credential</span></span> | <span data-ttu-id="74e61-120">A credencial de uma conta de usuário com permissões para acessar o caminho e o destino de arquivamento especificados, se necessário.</span><span class="sxs-lookup"><span data-stu-id="74e61-120">The credential of a user account with permissions to access the specified archive path and destination if needed.</span></span> |
| <span data-ttu-id="74e61-121">Force</span><span class="sxs-lookup"><span data-stu-id="74e61-121">Force</span></span> | <span data-ttu-id="74e61-122">Determinadas operações de arquivo (como substituição de um arquivo ou exclusão de um diretório que não esteja vazio) resultarão em erro.</span><span class="sxs-lookup"><span data-stu-id="74e61-122">Certain file operations (such as overwriting a file or deleting a directory that is not empty) will result in an error.</span></span> <span data-ttu-id="74e61-123">O uso da propriedade **Force** substitui esses erros.</span><span class="sxs-lookup"><span data-stu-id="74e61-123">Using the **Force** property overrides such errors.</span></span> <span data-ttu-id="74e61-124">O valor padrão é **Falso**.</span><span class="sxs-lookup"><span data-stu-id="74e61-124">The default value is **False**.</span></span> |
| <span data-ttu-id="74e61-125">Validar</span><span class="sxs-lookup"><span data-stu-id="74e61-125">Validate</span></span>| <span data-ttu-id="74e61-126">Usa a propriedade **Checksum** para determinar se o arquivo corresponde à assinatura.</span><span class="sxs-lookup"><span data-stu-id="74e61-126">Uses the **Checksum** property to determine if the archive matches the signature.</span></span> <span data-ttu-id="74e61-127">Se você especificar **Checksum** sem **Validate**, ocorrerá uma falha na configuração.</span><span class="sxs-lookup"><span data-stu-id="74e61-127">If you specify **Checksum** without **Validate**, the configuration will fail.</span></span> <span data-ttu-id="74e61-128">Se você especificar **Validate** sem **Checksum**, uma soma de verificação _SHA-256_ **Checksum** será usada por padrão.</span><span class="sxs-lookup"><span data-stu-id="74e61-128">If you specify **Validate** without **Checksum**, a _SHA-256_ **Checksum** is used by default.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="74e61-129">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="74e61-129">Common properties</span></span>

|<span data-ttu-id="74e61-130">Propriedade</span><span class="sxs-lookup"><span data-stu-id="74e61-130">Property</span></span> |<span data-ttu-id="74e61-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="74e61-131">Description</span></span> |
|---|---|
|<span data-ttu-id="74e61-132">DependsOn</span><span class="sxs-lookup"><span data-stu-id="74e61-132">DependsOn</span></span> |<span data-ttu-id="74e61-133">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="74e61-133">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="74e61-134">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="74e61-134">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="74e61-135">Ensure</span><span class="sxs-lookup"><span data-stu-id="74e61-135">Ensure</span></span> |<span data-ttu-id="74e61-136">Determina se é necessário verificar se o conteúdo do arquivo existe em **Destination**.</span><span class="sxs-lookup"><span data-stu-id="74e61-136">Determines whether to check if the content of the archive exists at the **Destination**.</span></span> <span data-ttu-id="74e61-137">Defina essa propriedade como **Present** para garantir que o conteúdo exista.</span><span class="sxs-lookup"><span data-stu-id="74e61-137">Set this property to **Present** to ensure the contents exist.</span></span> <span data-ttu-id="74e61-138">Defina-a como **Absent** para garantir que não exista.</span><span class="sxs-lookup"><span data-stu-id="74e61-138">Set it to **Absent** to ensure they do not exist.</span></span> <span data-ttu-id="74e61-139">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="74e61-139">The default value is **Present**.</span></span> |
|<span data-ttu-id="74e61-140">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="74e61-140">PsDscRunAsCredential</span></span> |<span data-ttu-id="74e61-141">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="74e61-141">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="74e61-142">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="74e61-142">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="74e61-143">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="74e61-143">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="74e61-144">Exemplo</span><span class="sxs-lookup"><span data-stu-id="74e61-144">Example</span></span>

<span data-ttu-id="74e61-145">O exemplo a seguir mostra como usar o recurso Archive para garantir que o conteúdo de um arquivo chamado `Test.zip` exista e seja extraído em um destino específico usado e autorizado.</span><span class="sxs-lookup"><span data-stu-id="74e61-145">The following example shows how to use the Archive resource to ensure that the contents of an archive file called `Test.zip` exist and are extracted at a given destination using and authorized.</span></span>

```powershell
Archive ArchiveExample {
    Ensure = "Present"
    Path = "C:\Users\Public\Documents\Test.zip"
    Destination = "C:\Users\Public\Documents\ExtractionPath"
}
```
