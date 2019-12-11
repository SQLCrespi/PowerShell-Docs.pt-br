---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
description: Oferece um mecanismo para gerenciar grupos locais no nó de destino.
title: Recurso de GroupSet DSC
ms.openlocfilehash: d36274741b2c96a0852f384ccf5d187ac8d27131
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953173"
---
# <a name="dsc-groupset-resource"></a><span data-ttu-id="dc4b1-104">Recurso de GroupSet DSC</span><span class="sxs-lookup"><span data-stu-id="dc4b1-104">DSC GroupSet Resource</span></span>

> <span data-ttu-id="dc4b1-105">Aplica-se a: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="dc4b1-105">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="dc4b1-106">O recurso **GroupSet** na DSC (Configuração de Estado Desejado) do Windows PowerShell oferece um mecanismo para gerenciar grupos locais no nó de destino.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-106">The **GroupSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on the target node.</span></span> <span data-ttu-id="dc4b1-107">Esse recurso é um [recurso composto](../../../resources/authoringResourceComposite.md) que chama o [Recurso de grupo](groupResource.md) para cada grupo especificado no parâmetro `GroupName`.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-107">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [Group resource](groupResource.md) for each group specified in the `GroupName` parameter.</span></span>

<span data-ttu-id="dc4b1-108">Use esse recurso quando desejar adicionar e/ou remover a mesma lista de membros para mais de um grupo, remova mais de um grupo ou adicionar mais de um grupo com a mesma lista de membros.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-108">Use this resource when you want to add and/or remove the same list of members to more than one group, remove more than one group, or add more than one group with the same list of members.</span></span>

## <a name="syntax"></a><span data-ttu-id="dc4b1-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dc4b1-109">Syntax</span></span>

```Syntax
Group [string] #ResourceName
{
    GroupName = [string[]]
    [ Members = [string[]] ]
    [ Description = [string[]] ]
    [ MembersToInclude = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="dc4b1-110">Propriedades</span><span class="sxs-lookup"><span data-stu-id="dc4b1-110">Properties</span></span>

|<span data-ttu-id="dc4b1-111">Propriedade</span><span class="sxs-lookup"><span data-stu-id="dc4b1-111">Property</span></span> |<span data-ttu-id="dc4b1-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="dc4b1-112">Description</span></span> |
|---|---|
|<span data-ttu-id="dc4b1-113">GroupName</span><span class="sxs-lookup"><span data-stu-id="dc4b1-113">GroupName</span></span> |<span data-ttu-id="dc4b1-114">Os nomes dos grupos para os quais você deseja garantir um estado específico.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-114">The names of the groups for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="dc4b1-115">Membros</span><span class="sxs-lookup"><span data-stu-id="dc4b1-115">Members</span></span> |<span data-ttu-id="dc4b1-116">Use essa propriedade para substituir a associação ao grupo pelos membros especificados.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-116">Use this property to replace the current group membership with the specified members.</span></span> <span data-ttu-id="dc4b1-117">O valor dessa propriedade é uma matriz de cadeias de caracteres do formulário `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-117">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="dc4b1-118">Se você definir essa propriedade em uma configuração, não use a propriedade **MembersToExclude** ou **MembersToInclude**.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-118">If you set this property in a configuration, do not use either the **MembersToExclude** or **MembersToInclude** property.</span></span> <span data-ttu-id="dc4b1-119">Isso vai gerar um erro.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-119">Doing so will generate an error.</span></span> |
|<span data-ttu-id="dc4b1-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="dc4b1-120">Description</span></span> |<span data-ttu-id="dc4b1-121">A descrição do grupo.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-121">The description of the group.</span></span> |
|<span data-ttu-id="dc4b1-122">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="dc4b1-122">MembersToInclude</span></span> |<span data-ttu-id="dc4b1-123">Use essa propriedade para adicionar membros à associação existente do grupo.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-123">Use this property to add members to the existing membership of the group.</span></span> <span data-ttu-id="dc4b1-124">O valor dessa propriedade é uma matriz de cadeias de caracteres do formulário `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-124">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="dc4b1-125">Se você definir essa propriedade em uma configuração, não use a propriedade **Membros**.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-125">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="dc4b1-126">Isso vai gerar um erro.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-126">Doing so will generate an error.</span></span> |
|<span data-ttu-id="dc4b1-127">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="dc4b1-127">MembersToExclude</span></span> |<span data-ttu-id="dc4b1-128">Use essa propriedade para remover membros da associação existente dos grupos.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-128">Use this property to remove members from the existing membership of the groups.</span></span> <span data-ttu-id="dc4b1-129">O valor dessa propriedade é uma matriz de cadeias de caracteres do formulário `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-129">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="dc4b1-130">Se você definir essa propriedade em uma configuração, não use a propriedade **Membros**.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-130">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="dc4b1-131">Isso vai gerar um erro.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-131">Doing so will generate an error.</span></span> |
|<span data-ttu-id="dc4b1-132">Credential</span><span class="sxs-lookup"><span data-stu-id="dc4b1-132">Credential</span></span> |<span data-ttu-id="dc4b1-133">As credenciais necessárias para acessar recursos remotos.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-133">The credentials required to access remote resources.</span></span> <span data-ttu-id="dc4b1-134">Essa conta deve ter as permissões apropriadas do Active Directory para adicionar todas as contas não locais ao grupo; caso contrário, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-134">This account must have the appropriate Active Directory permissions to add all non-local accounts to the group; otherwise, an error will occur.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="dc4b1-135">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="dc4b1-135">Common properties</span></span>

|<span data-ttu-id="dc4b1-136">Propriedade</span><span class="sxs-lookup"><span data-stu-id="dc4b1-136">Property</span></span> |<span data-ttu-id="dc4b1-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="dc4b1-137">Description</span></span> |
|---|---|
|<span data-ttu-id="dc4b1-138">DependsOn</span><span class="sxs-lookup"><span data-stu-id="dc4b1-138">DependsOn</span></span> |<span data-ttu-id="dc4b1-139">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-139">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="dc4b1-140">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-140">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="dc4b1-141">Ensure</span><span class="sxs-lookup"><span data-stu-id="dc4b1-141">Ensure</span></span> |<span data-ttu-id="dc4b1-142">Indica se os grupos existem.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-142">Indicates whether the groups exist.</span></span> <span data-ttu-id="dc4b1-143">Defina essa propriedade como **Absent** para garantir que os grupos não existam.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-143">Set this property to **Absent** to ensure that the groups do not exist.</span></span> <span data-ttu-id="dc4b1-144">Ao defini-la como **Present**, você garante que os grupos existam.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-144">Setting it to **Present** ensures that the groups exist.</span></span> <span data-ttu-id="dc4b1-145">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-145">The default value is **Present**.</span></span> |
|<span data-ttu-id="dc4b1-146">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="dc4b1-146">PsDscRunAsCredential</span></span> |<span data-ttu-id="dc4b1-147">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-147">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="dc4b1-148">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-148">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="dc4b1-149">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="dc4b1-149">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example-1-ensuring-groups-are-present"></a><span data-ttu-id="dc4b1-150">Exemplo 1: Garantindo que grupos estejam presentes</span><span class="sxs-lookup"><span data-stu-id="dc4b1-150">Example 1: Ensuring Groups are present</span></span>

<span data-ttu-id="dc4b1-151">O exemplo a seguir mostra como garantir que dois grupos chamados "myGroup" e "myOtherGroup" estejam presentes.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-151">The following example shows how to ensure that two groups called "myGroup" and "myOtherGroup" are present.</span></span>

```powershell
configuration GroupSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {
        GroupSet GroupSetTest
        {
            GroupName        = @("myGroup", "myOtherGroup")
            Ensure           = "Present"
            MembersToInclude = @("contoso\alice", "contoso\bob")
            MembersToExclude = $("contoso\john")
            Credential       = Get-Credential
        }
    }
}
$cd = @{
    AllNodes = @(
        @{
            NodeName                    = 'localhost'
            PSDscAllowPlainTextPassword = $true
            PSDscAllowDomainUser        = $true
        }
    )
}

GroupSetTest -ConfigurationData $cd
```

> [!NOTE]
> <span data-ttu-id="dc4b1-152">Este exemplo usa as credenciais de texto sem formatação para manter a simplicidade.</span><span class="sxs-lookup"><span data-stu-id="dc4b1-152">This example uses plaintext credentials for simplicity.</span></span> <span data-ttu-id="dc4b1-153">Para obter informações sobre como criptografar credenciais no arquivo MOF de configuração, consulte [Protegendo o Arquivo MOF](../../../pull-server/secureMOF.md).</span><span class="sxs-lookup"><span data-stu-id="dc4b1-153">For information about how to encrypt credentials in the configuration MOF file, see [Securing the MOF File](../../../pull-server/secureMOF.md).</span></span>