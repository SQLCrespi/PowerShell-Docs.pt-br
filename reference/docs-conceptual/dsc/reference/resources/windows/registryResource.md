---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso Registry de DSC
ms.openlocfilehash: 9f65815cbe6a94831b88cb3425bf688e1a99a9c0
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83559895"
---
# <a name="dsc-registry-resource"></a><span data-ttu-id="b2a06-103">Recurso Registry de DSC</span><span class="sxs-lookup"><span data-stu-id="b2a06-103">DSC Registry Resource</span></span>

> <span data-ttu-id="b2a06-104">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="b2a06-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="b2a06-105">O recurso **Registry** na Configuração de Estado Desejado (DSC) do Windows PowerShell fornece um mecanismo para gerenciar chaves e valores do registro em um nó de destino.</span><span class="sxs-lookup"><span data-stu-id="b2a06-105">The **Registry** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage registry keys and values on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2a06-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b2a06-106">Syntax</span></span>

```Syntax
Registry [string] #ResourceName
{
    Key = [string]
    ValueName = [string]
    [ Force =  [bool]   ]
    [ Hex = [bool] ]
    [ ValueData = [string[]] ]
    [ ValueType = [string] { Binary | Dword | ExpandString | MultiString | Qword | String }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Present | Absent }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="b2a06-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="b2a06-107">Properties</span></span>

|<span data-ttu-id="b2a06-108">Propriedade</span><span class="sxs-lookup"><span data-stu-id="b2a06-108">Property</span></span> |<span data-ttu-id="b2a06-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="b2a06-109">Description</span></span> |
|---|---|
|<span data-ttu-id="b2a06-110">Chave</span><span class="sxs-lookup"><span data-stu-id="b2a06-110">Key</span></span> |<span data-ttu-id="b2a06-111">Indica o caminho da chave do Registro para o qual você deseja garantir um estado específico.</span><span class="sxs-lookup"><span data-stu-id="b2a06-111">Indicates the path of the registry key for which you want to ensure a specific state.</span></span> <span data-ttu-id="b2a06-112">Esse caminho deve incluir o hive.</span><span class="sxs-lookup"><span data-stu-id="b2a06-112">This path must include the hive.</span></span> |
|<span data-ttu-id="b2a06-113">ValueName</span><span class="sxs-lookup"><span data-stu-id="b2a06-113">ValueName</span></span> |<span data-ttu-id="b2a06-114">Indica o nome do valor de registro.</span><span class="sxs-lookup"><span data-stu-id="b2a06-114">Indicates the name of the registry value.</span></span> <span data-ttu-id="b2a06-115">Para adicionar ou remover uma chave do Registro, especifique essa propriedade como uma cadeia de caracteres vazia sem especificar **ValueType** ou **ValueData**.</span><span class="sxs-lookup"><span data-stu-id="b2a06-115">To add or remove a registry key, specify this property as an empty string without specifying **ValueType** or **ValueData**.</span></span> <span data-ttu-id="b2a06-116">Para modificar ou remover o valor padrão de uma chave do Registro, especifique essa propriedade como uma cadeia de caracteres vazia e também especifique **ValueType** ou **ValueData**.</span><span class="sxs-lookup"><span data-stu-id="b2a06-116">To modify or remove the default value of a registry key, specify this property as an empty string while also specifying **ValueType** or **ValueData**.</span></span> |
|<span data-ttu-id="b2a06-117">Force</span><span class="sxs-lookup"><span data-stu-id="b2a06-117">Force</span></span> |<span data-ttu-id="b2a06-118">Se a chave do Registro especificada estiver presente, **Force** a substituirá pelo novo valor.</span><span class="sxs-lookup"><span data-stu-id="b2a06-118">If the specified registry key is present, **Force** overwrites it with the new value.</span></span> <span data-ttu-id="b2a06-119">Para excluir uma chave do Registro com subchaves, isso deve ser `$true`.</span><span class="sxs-lookup"><span data-stu-id="b2a06-119">If deleting a registry key with subkeys, this needs to be `$true`.</span></span> |
|<span data-ttu-id="b2a06-120">Hex</span><span class="sxs-lookup"><span data-stu-id="b2a06-120">Hex</span></span> |<span data-ttu-id="b2a06-121">Indica se os dados serão expressos em formato hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="b2a06-121">Indicates if data will be expressed in hexadecimal format.</span></span> <span data-ttu-id="b2a06-122">Se especificado, os dados do valor DWORD/QWORD são apresentados em formato hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="b2a06-122">If specified, the DWORD/QWORD value data is presented in hexadecimal format.</span></span> <span data-ttu-id="b2a06-123">Não é válido para outros tipos.</span><span class="sxs-lookup"><span data-stu-id="b2a06-123">Not valid for other types.</span></span> <span data-ttu-id="b2a06-124">O valor padrão é `$false`.</span><span class="sxs-lookup"><span data-stu-id="b2a06-124">The default value is `$false`.</span></span> |
|<span data-ttu-id="b2a06-125">ValueData</span><span class="sxs-lookup"><span data-stu-id="b2a06-125">ValueData</span></span> |<span data-ttu-id="b2a06-126">Os dados para o valor de registro.</span><span class="sxs-lookup"><span data-stu-id="b2a06-126">The data for the registry value.</span></span> |
|<span data-ttu-id="b2a06-127">ValueType</span><span class="sxs-lookup"><span data-stu-id="b2a06-127">ValueType</span></span> |<span data-ttu-id="b2a06-128">Indica o tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="b2a06-128">Indicates the type of the value.</span></span> <span data-ttu-id="b2a06-129">Há suporte para estes tipos: **Cadeia de caracteres** (REG_SZ), **Binário** (REG-BINARY), **Dword de 32 bits** (REG_DWORD), **Qword de 64 bits** (REG_QWORD), **Cadeia de caracteres múltipla** (REG_MULTI_SZ), **Cadeia de caracteres expansível** (REG_EXPAND_SZ).</span><span class="sxs-lookup"><span data-stu-id="b2a06-129">The supported types are: **String** (REG_SZ), **Binary** (REG-BINARY), **Dword** (32-bit REG_DWORD), **Qword** (64-bit REG_QWORD), **MultiString** (REG_MULTI_SZ), **ExpandString** (REG_EXPAND_SZ).</span></span> |

## <a name="common-properties"></a><span data-ttu-id="b2a06-130">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="b2a06-130">Common properties</span></span>

|<span data-ttu-id="b2a06-131">Propriedade</span><span class="sxs-lookup"><span data-stu-id="b2a06-131">Property</span></span> |<span data-ttu-id="b2a06-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="b2a06-132">Description</span></span> |
|---|---|
|<span data-ttu-id="b2a06-133">DependsOn</span><span class="sxs-lookup"><span data-stu-id="b2a06-133">DependsOn</span></span> |<span data-ttu-id="b2a06-134">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="b2a06-134">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="b2a06-135">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="b2a06-135">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="b2a06-136">Ensure</span><span class="sxs-lookup"><span data-stu-id="b2a06-136">Ensure</span></span> |<span data-ttu-id="b2a06-137">Indica se a chave e o valor existem.</span><span class="sxs-lookup"><span data-stu-id="b2a06-137">Indicates if the key and value exist.</span></span> <span data-ttu-id="b2a06-138">Para garantir que existam, defina essa propriedade como **Present**.</span><span class="sxs-lookup"><span data-stu-id="b2a06-138">To ensure that they do, set this property to **Present**.</span></span> <span data-ttu-id="b2a06-139">Para garantir que não existam, defina a propriedade como **Absent**.</span><span class="sxs-lookup"><span data-stu-id="b2a06-139">To ensure that they do not exist, set the property to **Absent**.</span></span> <span data-ttu-id="b2a06-140">O valor padrão é **Present**.</span><span class="sxs-lookup"><span data-stu-id="b2a06-140">The default value is **Present**.</span></span> |
|<span data-ttu-id="b2a06-141">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="b2a06-141">PsDscRunAsCredential</span></span> |<span data-ttu-id="b2a06-142">Define a credencial para executar todo o recurso.</span><span class="sxs-lookup"><span data-stu-id="b2a06-142">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="b2a06-143">A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais.</span><span class="sxs-lookup"><span data-stu-id="b2a06-143">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="b2a06-144">Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="b2a06-144">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="b2a06-145">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b2a06-145">Example</span></span>

<span data-ttu-id="b2a06-146">Este exemplo assegura que uma chave chamada "ExampleKey" está presente no hive **HKEY\_LOCAL\_MACHINE**.</span><span class="sxs-lookup"><span data-stu-id="b2a06-146">This example ensures that a key named "ExampleKey" is present in the **HKEY\_LOCAL\_MACHINE** hive.</span></span>

```powershell
Configuration RegistryTest
{
    Registry RegistryExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Key         = "HKEY_LOCAL_MACHINE\SOFTWARE\ExampleKey"
        ValueName   = "TestValue"
        ValueData   = "TestData"
    }
}
```

> [!NOTE]
> <span data-ttu-id="b2a06-147">Alterar uma configuração do registro no hive `HKEY_CURRENT_USER` requer que a configuração seja executada com credenciais de usuário, em vez de como o sistema.</span><span class="sxs-lookup"><span data-stu-id="b2a06-147">Changing a registry setting in the `HKEY_CURRENT_USER` hive requires that the configuration runs with user credentials, rather than as the system.</span></span> <span data-ttu-id="b2a06-148">Você pode usar a propriedade **PsDscRunAsCredential** para especificar credenciais de usuário para a configuração.</span><span class="sxs-lookup"><span data-stu-id="b2a06-148">You can use the **PsDscRunAsCredential** property to specify user credentials for the configuration.</span></span> <span data-ttu-id="b2a06-149">Por exemplo, veja [Executar DSC com as credenciais do usuário](../../../configurations/runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="b2a06-149">For an example, see [Running DSC with user credentials](../../../configurations/runAsUser.md).</span></span>
