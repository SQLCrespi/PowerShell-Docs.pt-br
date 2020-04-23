---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso User de DSC
ms.openlocfilehash: dec432c2ff1b4e4408165fef391e77cbf1d85ac4
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953003"
---
# <a name="dsc-user-resource"></a><span data-ttu-id="87156-103">Recurso User de DSC</span><span class="sxs-lookup"><span data-stu-id="87156-103">DSC User Resource</span></span>

> <span data-ttu-id="87156-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="87156-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="87156-105">O recurso **User** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para contas de usuário locais no nó de destino.</span><span class="sxs-lookup"><span data-stu-id="87156-105">The **User** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local user accounts on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="87156-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="87156-106">Syntax</span></span>

```Syntax
User [string] #ResourceName
{
    UserName = [string]
    [ Description = [string] ]
    [ Disabled = [bool] ]
    [ FullName = [string] ]
    [ Password = [PSCredential] ]
    [ PasswordChangeNotAllowed = [bool] ]
    [ PasswordChangeRequired = [bool] ]
    [ PasswordNeverExpires = [bool] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="87156-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="87156-107">Properties</span></span>

|<span data-ttu-id="87156-108">Propriedade</span><span class="sxs-lookup"><span data-stu-id="87156-108">Property</span></span> |<span data-ttu-id="87156-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="87156-109">Description</span></span> |
|---|---|
|<span data-ttu-id="87156-110">UserName</span><span class="sxs-lookup"><span data-stu-id="87156-110">UserName</span></span> |<span data-ttu-id="87156-111">Indica o nome da conta para a qual você deseja garantir um estado específico.</span><span class="sxs-lookup"><span data-stu-id="87156-111">Indicates the account name for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="87156-112">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="87156-112">Description</span></span> |<span data-ttu-id="87156-113">Indica a descrição que você deseja usar para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="87156-113">Indicates the description you want to use for the user account.</span></span> |
|<span data-ttu-id="87156-114">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="87156-114">Disabled</span></span> |<span data-ttu-id="87156-115">Indica se a conta está habilitada.</span><span class="sxs-lookup"><span data-stu-id="87156-115">Indicates if the account is enabled.</span></span> <span data-ttu-id="87156-116">Defina essa propriedade como `$true` para garantir que essa conta esteja desabilitada e defina-a como `$false` para garantir que esteja habilitada.</span><span class="sxs-lookup"><span data-stu-id="87156-116">Set this property to `$true` to ensure that this account is disabled, and set it to `$false` to ensure that it is enabled.</span></span> |
|<span data-ttu-id="87156-117">FullName</span><span class="sxs-lookup"><span data-stu-id="87156-117">FullName</span></span> |<span data-ttu-id="87156-118">Representa uma cadeia de caracteres com o nome completo que você deseja usar para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="87156-118">Represents a string with the full name you want to use for the user account.</span></span> |
|<span data-ttu-id="87156-119">Senha</span><span class="sxs-lookup"><span data-stu-id="87156-119">Password</span></span> |<span data-ttu-id="87156-120">Indica a senha que você deseja usar para essa conta.</span><span class="sxs-lookup"><span data-stu-id="87156-120">Indicates the password you want to use for this account.</span></span> |
|<span data-ttu-id="87156-121">PasswordChangeNotAllowed</span><span class="sxs-lookup"><span data-stu-id="87156-121">PasswordChangeNotAllowed</span></span> |<span data-ttu-id="87156-122">Indica se o usuário pode alterar a senha.</span><span class="sxs-lookup"><span data-stu-id="87156-122">Indicates if the user can change the password.</span></span> <span data-ttu-id="87156-123">Defina essa propriedade como `$true` para garantir que o usuário não possa alterar a senha e defina-a como `$false` para permitir que o usuário altere a senha.</span><span class="sxs-lookup"><span data-stu-id="87156-123">Set this property to `$true` to ensure that the user cannot change the password, and set it to `$false` to allow the user to change the password.</span></span> <span data-ttu-id="87156-124">O valor padrão é `$false`.</span><span class="sxs-lookup"><span data-stu-id="87156-124">The default value is `$false`.</span></span> |
|<span data-ttu-id="87156-125">PasswordChangeRequired</span><span class="sxs-lookup"><span data-stu-id="87156-125">PasswordChangeRequired</span></span> |<span data-ttu-id="87156-126">Indica se o usuário deve alterar a senha na próxima entrada.</span><span class="sxs-lookup"><span data-stu-id="87156-126">Indicates if the user must change the password at the next sign in.</span></span> <span data-ttu-id="87156-127">Defina essa propriedade como `$true` se o usuário precisar alterar a senha.</span><span class="sxs-lookup"><span data-stu-id="87156-127">Set this property to `$true` if the user must change the password.</span></span> <span data-ttu-id="87156-128">O valor padrão é `$true`.</span><span class="sxs-lookup"><span data-stu-id="87156-128">The default value is `$true`.</span></span> |
|<span data-ttu-id="87156-129">PasswordNeverExpires</span><span class="sxs-lookup"><span data-stu-id="87156-129">PasswordNeverExpires</span></span> |<span data-ttu-id="87156-130">Indica se a senha vai expirar.</span><span class="sxs-lookup"><span data-stu-id="87156-130">Indicates if the password will expire.</span></span> <span data-ttu-id="87156-131">Para garantir que a senha para essa conta nunca expire, defina essa propriedade como `$true`.</span><span class="sxs-lookup"><span data-stu-id="87156-131">To ensure that the password for this account will never expire, set this property to `$true`.</span></span> <span data-ttu-id="87156-132">Defina-a como `$false` caso a senha vá expirar.</span><span class="sxs-lookup"><span data-stu-id="87156-132">Set it to `$false` if the password will expire.</span></span> <span data-ttu-id="87156-133">O valor padrão é `$false`.</span><span class="sxs-lookup"><span data-stu-id="87156-133">The default value is `$false`.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="87156-134">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="87156-134">Common properties</span></span>

|<span data-ttu-id="87156-135">Propriedade</span><span class="sxs-lookup"><span data-stu-id="87156-135">Property</span></span> |<span data-ttu-id="87156-136">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="87156-136">Description</span></span> |
|---|---|
|<span data-ttu-id="87156-137">DependsOn</span><span class="sxs-lookup"><span data-stu-id="87156-137">DependsOn</span></span> |<span data-ttu-id="87156-138">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="87156-138">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="87156-139">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="87156-139">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="87156-140">Ensure</span><span class="sxs-lookup"><span data-stu-id="87156-140">Ensure</span></span> |<span data-ttu-id="87156-141">Indica se a conta existe.</span><span class="sxs-lookup"><span data-stu-id="87156-141">Indicates if the account exists.</span></span> <span data-ttu-id="87156-142">Defina essa propriedade como **Present** para garantir que a conta exista e defina-o como **Absent** para garantir que a conta não exista.</span><span class="sxs-lookup"><span data-stu-id="87156-142">Set this property to **Present** to ensure that the account exists, and set it to **Absent** to ensure that the account does not exist.</span></span> <span data-ttu-id="87156-143">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="87156-143">The default value is **Present**.</span></span> |
|<span data-ttu-id="87156-144">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="87156-144">PsDscRunAsCredential</span></span> |<span data-ttu-id="87156-145">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="87156-145">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="87156-146">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="87156-146">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="87156-147">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="87156-147">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="87156-148">Exemplo</span><span class="sxs-lookup"><span data-stu-id="87156-148">Example</span></span>

```powershell
User UserExample
{
    Ensure = "Present"  # To ensure the user account does not exist, set Ensure to "Absent"
    UserName = "SomeName"
    Password = $passwordCred # This needs to be a credential object
    DependsOn = "[Group]GroupExample" # Configures GroupExample first
}
```