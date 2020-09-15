---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método ResourceSet
ms.openlocfilehash: c015960b2a5ffca0d28b714d571aa616400555bd
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464037"
---
# <a name="resourceset-method"></a><span data-ttu-id="6eff3-103">Método ResourceSet</span><span class="sxs-lookup"><span data-stu-id="6eff3-103">ResourceSet method</span></span>

<span data-ttu-id="6eff3-104">Chama diretamente o método **Set** de um recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="6eff3-104">Directly calls the **Set** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="6eff3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6eff3-105">Syntax</span></span>

```mof
uint32 ResourceSet(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean RebootRequired
);
```

## <a name="parameters"></a><span data-ttu-id="6eff3-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6eff3-106">Parameters</span></span>

<span data-ttu-id="6eff3-107">**ResourceType** \[in\] O nome do recurso a chamar.</span><span class="sxs-lookup"><span data-stu-id="6eff3-107">**ResourceType** \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="6eff3-108">**ModuleName** \[in\] O nome do módulo que contém o recurso a chamar.</span><span class="sxs-lookup"><span data-stu-id="6eff3-108">**ModuleName** \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="6eff3-109">**resourceProperty** \[in\] Especifica o nome da propriedade do recurso e o respectivo valor em uma tabela de hash como chave e valor, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6eff3-109">**resourceProperty** \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="6eff3-110">Use o cmdlet [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) para descobrir as propriedades de recurso e seus tipos.</span><span class="sxs-lookup"><span data-stu-id="6eff3-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="6eff3-111">**RebootRequired** \[out\] No retorno, essa propriedade será definida como **true**, se for necessário reiniciar o nó de destino.</span><span class="sxs-lookup"><span data-stu-id="6eff3-111">**RebootRequired** \[out\] On return, this property is set to **true** if the target node needs to be rebooted.</span></span>

## <a name="return-value"></a><span data-ttu-id="6eff3-112">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="6eff3-112">Return value</span></span>

<span data-ttu-id="6eff3-113">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="6eff3-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="6eff3-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="6eff3-114">Remarks</span></span>

<span data-ttu-id="6eff3-115">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="6eff3-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="6eff3-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6eff3-116">Requirements</span></span>

<span data-ttu-id="6eff3-117">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="6eff3-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="6eff3-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="6eff3-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="6eff3-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="6eff3-119">See also</span></span>

[<span data-ttu-id="6eff3-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="6eff3-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
