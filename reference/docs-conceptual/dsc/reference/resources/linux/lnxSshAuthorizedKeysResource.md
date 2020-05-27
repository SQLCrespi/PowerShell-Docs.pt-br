---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso nxSshAuthorizedKeys de DSC para Linux
ms.openlocfilehash: 4c35590095732a478e3edc56438f3bdd1c0b24df
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557185"
---
# <a name="dsc-for-linux-nxsshauthorizedkeys-resource"></a><span data-ttu-id="b4190-103">Recurso nxSshAuthorizedKeys de DSC para Linux</span><span class="sxs-lookup"><span data-stu-id="b4190-103">DSC for Linux nxSshAuthorizedKeys Resource</span></span>

<span data-ttu-id="b4190-104">O recurso **nxAuthorizedKeys** na Configuração de Estado Desejado (DSC) do PowerShell fornece um mecanismo para gerenciar chaves ssh autorizadas para um usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="b4190-104">The **nxAuthorizedKeys** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage authorized ssh keys for a specified user.</span></span>

## <a name="syntax"></a><span data-ttu-id="b4190-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b4190-105">Syntax</span></span>

```Syntax
nxAuthorizedKeys <string> #ResourceName
{
    KeyComment = <string>
    [ Username = <string> ]
    [ Key = <string> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a><span data-ttu-id="b4190-106">Propriedades</span><span class="sxs-lookup"><span data-stu-id="b4190-106">Properties</span></span>

|<span data-ttu-id="b4190-107">Propriedade</span><span class="sxs-lookup"><span data-stu-id="b4190-107">Property</span></span> |<span data-ttu-id="b4190-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="b4190-108">Description</span></span> |
|---|---|
|<span data-ttu-id="b4190-109">KeyComment</span><span class="sxs-lookup"><span data-stu-id="b4190-109">KeyComment</span></span> |<span data-ttu-id="b4190-110">Um comentário exclusivo para a chave.</span><span class="sxs-lookup"><span data-stu-id="b4190-110">A unique comment for the key.</span></span> <span data-ttu-id="b4190-111">É usado para identificar as chaves com exclusividade.</span><span class="sxs-lookup"><span data-stu-id="b4190-111">This is used to uniquely identify keys.</span></span> |
|<span data-ttu-id="b4190-112">Nome de Usuário</span><span class="sxs-lookup"><span data-stu-id="b4190-112">Username</span></span> |<span data-ttu-id="b4190-113">O nome de usuário para o qual as chaves ssh autorizadas serão gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="b4190-113">The username to manage ssh authorized keys for.</span></span> <span data-ttu-id="b4190-114">Se não for definido, o usuário padrão será **root**.</span><span class="sxs-lookup"><span data-stu-id="b4190-114">If not defined, the default user is **root**.</span></span> |
|<span data-ttu-id="b4190-115">Chave</span><span class="sxs-lookup"><span data-stu-id="b4190-115">Key</span></span> |<span data-ttu-id="b4190-116">O conteúdo da chave.</span><span class="sxs-lookup"><span data-stu-id="b4190-116">The contents of the key.</span></span> <span data-ttu-id="b4190-117">Será obrigatório se **Ensure** for definido como **Present**.</span><span class="sxs-lookup"><span data-stu-id="b4190-117">This is required if **Ensure** is set to **Present**.</span></span>|

## <a name="common-properties"></a><span data-ttu-id="b4190-118">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="b4190-118">Common properties</span></span>

|<span data-ttu-id="b4190-119">Propriedade</span><span class="sxs-lookup"><span data-stu-id="b4190-119">Property</span></span> |<span data-ttu-id="b4190-120">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="b4190-120">Description</span></span> |
|---|---|
|<span data-ttu-id="b4190-121">DependsOn</span><span class="sxs-lookup"><span data-stu-id="b4190-121">DependsOn</span></span> |<span data-ttu-id="b4190-122">Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado.</span><span class="sxs-lookup"><span data-stu-id="b4190-122">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="b4190-123">Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="b4190-123">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="b4190-124">Ensure</span><span class="sxs-lookup"><span data-stu-id="b4190-124">Ensure</span></span> |<span data-ttu-id="b4190-125">Especifica se a chave foi definida.</span><span class="sxs-lookup"><span data-stu-id="b4190-125">Specifies whether the key is defined.</span></span> <span data-ttu-id="b4190-126">Defina essa propriedade como **Absent** para garantir que a chave não exista no arquivo de chaves autorizadas do usuário.</span><span class="sxs-lookup"><span data-stu-id="b4190-126">Set this property to **Absent** to ensure the key does not exist in the user's authorized keys file.</span></span> <span data-ttu-id="b4190-127">Defina-a como **Present** para garantir que a chave seja definida no arquivo de chaves autorizadas do usuário.</span><span class="sxs-lookup"><span data-stu-id="b4190-127">Set it to **Present** to ensure the key is defined in the user's authorized key file.</span></span> |

## <a name="example"></a><span data-ttu-id="b4190-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b4190-128">Example</span></span>

<span data-ttu-id="b4190-129">O exemplo a seguir define uma chave ssh pública autorizada para o usuário "monuser".</span><span class="sxs-lookup"><span data-stu-id="b4190-129">The following example defines a public ssh authorized key for the user "monuser".</span></span>

```powershell
Import-DSCResource -Module nx

Node $node
{
    nxSshAuthorizedKeys myKey
    {
        KeyComment = "myKey"
        Ensure = "Present"
        Key = 'ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEA0b+0xSd07QXRifm3FXj7Pn/DblA6QI5VAkDm6OivFzj3U6qGD1VJ6AAxWPCyMl/qhtpRtxZJDu/TxD8AyZNgc8aN2CljN1hOMbBRvH2q5QPf/nCnnJRaGsrxIqZjyZdYo9ZEEzjZUuMDM5HI1LA9B99k/K6PK2Bc1NLivpu7nbtVG2tLOQs+GefsnHuetsRMwo/+c3LtwYm9M0XfkGjYVCLO4CoFuSQpvX6AB3TedUy6NZ0iuxC0kRGg1rIQTwSRcw+McLhslF0drs33fw6tYdzlLBnnzimShMuiDWiT37WqCRovRGYrGCaEFGTG2e0CN8Co8nryXkyWc6NSDNpMzw== rsa-key-20150401'
        UserName = "monuser"
    }
}
```
