---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso Group de DSC
ms.openlocfilehash: 695a914683c6daff44dd2a6c94b6353acf881030
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954653"
---
# <a name="dsc-group-resource"></a><span data-ttu-id="49d50-103">Recurso Group de DSC</span><span class="sxs-lookup"><span data-stu-id="49d50-103">DSC Group Resource</span></span>

> <span data-ttu-id="49d50-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="49d50-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="49d50-105">O recurso **Grupo** na DSC (Desired State Configuration) do Windows PowerShell fornece um mecanismo para gerenciar grupos locais no nó de destino.</span><span class="sxs-lookup"><span data-stu-id="49d50-105">The **Group** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="49d50-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="49d50-106">Syntax</span></span>

```Syntax
Group [string] #ResourceName
{
    GroupName = [string]
    [ Credential = [PSCredential] ]
    [ Description = [string[]] ]
    [ Members = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ MembersToInclude = [string[]] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="49d50-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="49d50-107">Properties</span></span>

|<span data-ttu-id="49d50-108">Propriedade</span><span class="sxs-lookup"><span data-stu-id="49d50-108">Property</span></span> |<span data-ttu-id="49d50-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="49d50-109">Description</span></span> |
|---|---|
|<span data-ttu-id="49d50-110">GroupName</span><span class="sxs-lookup"><span data-stu-id="49d50-110">GroupName</span></span> |<span data-ttu-id="49d50-111">O nome do grupo para o qual você deseja garantir um estado específico.</span><span class="sxs-lookup"><span data-stu-id="49d50-111">The name of the group for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="49d50-112">Credencial</span><span class="sxs-lookup"><span data-stu-id="49d50-112">Credential</span></span> |<span data-ttu-id="49d50-113">As credenciais necessárias para acessar recursos remotos.</span><span class="sxs-lookup"><span data-stu-id="49d50-113">The credentials required to access remote resources.</span></span> <span data-ttu-id="49d50-114">Essa conta deve ter as permissões apropriadas do Active Directory para adicionar todas as contas não locais ao grupo; caso contrário, ocorrerá um erro quando a configuração for executada no nó de destino.</span><span class="sxs-lookup"><span data-stu-id="49d50-114">This account must have the appropriate Active Directory permissions to add all non-local accounts to the group; otherwise, an error occurs when the configuration is executed on the target node.</span></span>
|<span data-ttu-id="49d50-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="49d50-115">Description</span></span> |<span data-ttu-id="49d50-116">A descrição do grupo.</span><span class="sxs-lookup"><span data-stu-id="49d50-116">The description of the group.</span></span> |
|<span data-ttu-id="49d50-117">Membros</span><span class="sxs-lookup"><span data-stu-id="49d50-117">Members</span></span> |<span data-ttu-id="49d50-118">Use essa propriedade para substituir a associação ao grupo pelos membros especificados.</span><span class="sxs-lookup"><span data-stu-id="49d50-118">Use this property to replace the current group membership with the specified members.</span></span> <span data-ttu-id="49d50-119">O valor dessa propriedade é uma matriz de cadeias de caracteres do formulário `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="49d50-119">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="49d50-120">Se você definir essa propriedade em uma configuração, não use a propriedade **MembersToExclude** ou **MembersToInclude**.</span><span class="sxs-lookup"><span data-stu-id="49d50-120">If you set this property in a configuration, do not use either the **MembersToExclude** or **MembersToInclude** property.</span></span> <span data-ttu-id="49d50-121">Isso gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="49d50-121">Doing so generates an error.</span></span> |
|<span data-ttu-id="49d50-122">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="49d50-122">MembersToExclude</span></span> |<span data-ttu-id="49d50-123">Use essa propriedade para remover membros da associação existente do grupo.</span><span class="sxs-lookup"><span data-stu-id="49d50-123">Use this property to remove members from the existing membership of the group.</span></span> <span data-ttu-id="49d50-124">O valor dessa propriedade é uma matriz de cadeias de caracteres do formulário `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="49d50-124">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="49d50-125">Se você definir essa propriedade em uma configuração, não use a propriedade **Membros**.</span><span class="sxs-lookup"><span data-stu-id="49d50-125">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="49d50-126">Isso gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="49d50-126">Doing so generates an error.</span></span> |
|<span data-ttu-id="49d50-127">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="49d50-127">MembersToInclude</span></span> |<span data-ttu-id="49d50-128">Use essa propriedade para adicionar membros à associação existente do grupo.</span><span class="sxs-lookup"><span data-stu-id="49d50-128">Use this property to add members to the existing membership of the group.</span></span> <span data-ttu-id="49d50-129">O valor dessa propriedade é uma matriz de cadeias de caracteres do formulário `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="49d50-129">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="49d50-130">Se você definir essa propriedade em uma configuração, não use a propriedade **Membros**.</span><span class="sxs-lookup"><span data-stu-id="49d50-130">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="49d50-131">Isso vai gerar um erro.</span><span class="sxs-lookup"><span data-stu-id="49d50-131">Doing so will generate an error.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="49d50-132">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="49d50-132">Common properties</span></span>

|<span data-ttu-id="49d50-133">Propriedade</span><span class="sxs-lookup"><span data-stu-id="49d50-133">Property</span></span> |<span data-ttu-id="49d50-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="49d50-134">Description</span></span> |
|---|---|
|<span data-ttu-id="49d50-135">DependsOn</span><span class="sxs-lookup"><span data-stu-id="49d50-135">DependsOn</span></span> |<span data-ttu-id="49d50-136">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="49d50-136">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="49d50-137">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="49d50-137">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="49d50-138">Ensure</span><span class="sxs-lookup"><span data-stu-id="49d50-138">Ensure</span></span> |<span data-ttu-id="49d50-139">Indica se o grupo existe.</span><span class="sxs-lookup"><span data-stu-id="49d50-139">Indicates if the group exists.</span></span> <span data-ttu-id="49d50-140">Defina essa propriedade como **Absent** para garantir que o grupo não exista.</span><span class="sxs-lookup"><span data-stu-id="49d50-140">Set this property to **Absent** to ensure that the group does not exist.</span></span> <span data-ttu-id="49d50-141">Ao defini-la como **Present**, você garante que o grupo exista.</span><span class="sxs-lookup"><span data-stu-id="49d50-141">Setting it to **Present** ensures that the group exists.</span></span> <span data-ttu-id="49d50-142">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="49d50-142">The default value is **Present**.</span></span> |
|<span data-ttu-id="49d50-143">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="49d50-143">PsDscRunAsCredential</span></span> |<span data-ttu-id="49d50-144">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="49d50-144">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="49d50-145">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="49d50-145">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="49d50-146">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="49d50-146">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example-1-ensure-group-is-not-present"></a><span data-ttu-id="49d50-147">Exemplo 1: garanta que o grupo não esteja presente</span><span class="sxs-lookup"><span data-stu-id="49d50-147">Example 1: Ensure group is not present</span></span>

<span data-ttu-id="49d50-148">O exemplo a seguir mostra como garantir que um grupo chamado "TestGroup" esteja ausente.</span><span class="sxs-lookup"><span data-stu-id="49d50-148">The following example shows how to ensure that a group called "TestGroup" is absent.</span></span>

```powershell
Group GroupExample
{
    # This removes TestGroup, if present
    # To create a new group, set Ensure to "Present"
    Ensure = "Absent"
    GroupName = "TestGroup"
}
```

## <a name="example-2-add-domain-user-to-local-group"></a><span data-ttu-id="49d50-149">Exemplo 2: adicione um usuário de domínio ao grupo local</span><span class="sxs-lookup"><span data-stu-id="49d50-149">Example 2: Add domain user to local group</span></span>

<span data-ttu-id="49d50-150">O exemplo a seguir mostra como adicionar um usuário do Active Directory ao grupo de administradores locais como parte de um build de laboratório com vários computadores, em que você já está usando um PSCredential para a conta de Administrador Local.</span><span class="sxs-lookup"><span data-stu-id="49d50-150">The following example shows how to add an Active Directory User to the local administrators group as part of a Multi-Machine Lab build where you are already using a PSCredential for the Local Administrator account.</span></span> <span data-ttu-id="49d50-151">Como isso também é usado para a conta de administrador do domínio (após a promoção do domínio), devemos converter essa PSCredential existente em uma credencial de domínio amigável.</span><span class="sxs-lookup"><span data-stu-id="49d50-151">As this is also used for the Domain Admin Account (after Domain promotion), we then need to convert this existing PSCredential to a Domain Friendly credential.</span></span> <span data-ttu-id="49d50-152">Em seguida, podemos adicionar um usuário do domínio ao grupo de administradores local no servidor membro.</span><span class="sxs-lookup"><span data-stu-id="49d50-152">Then we can add a Domain User to the Local Administrators Group on the Member server.</span></span>

```powershell
@{
    AllNodes = @(
        @{
            NodeName = '*';
            DomainName = 'SubTest.contoso.com';
         }
        @{
            NodeName = 'Box2';
            AdminAccount = 'Admin-Dave_Alexanderson'
        }
    )
}

$domain = $node.DomainName.split('.')[0]
$DCredential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList ("$domain\$($credential.Username)", $Credential.Password)

Group AddADUserToLocalAdminGroup {
    GroupName='Administrators'
    Ensure= 'Present'
    MembersToInclude= "$domain\$($Node.AdminAccount)"
    Credential = $dCredential
    PsDscRunAsCredential = $DCredential
}
```

## <a name="example-3"></a><span data-ttu-id="49d50-153">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="49d50-153">Example 3</span></span>

<span data-ttu-id="49d50-154">O exemplo a seguir mostra como verificar se um grupo local, TigerTeamAdmins, no servidor TigerTeamSource.Contoso.Com, não contém uma conta de domínio específico, Contoso\JerryG.</span><span class="sxs-lookup"><span data-stu-id="49d50-154">The following example shows how to ensure a local group, TigerTeamAdmins, on the server TigerTeamSource.Contoso.Com does not contain a particular domain account, Contoso\JerryG.</span></span>

```powershell
Configuration SecureTigerTeamSource {
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node TigerTeamSource.Contoso.Com {
        Group TigerTeamAdmins {
            GroupName        = 'TigerTeamAdmins'
            Ensure           = 'Present'
            MembersToExclude = "Contoso\JerryG"
        }
    }
}
```