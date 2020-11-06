---
ms.date: 07/17/2020
ms.topic: reference
title: Método ResourceTest
description: Método ResourceTest
ms.openlocfilehash: cbac53ea96a59ec92fa840f75cd264a3125b965a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650675"
---
# <a name="resourcetest-method"></a><span data-ttu-id="3260c-103">Método ResourceTest</span><span class="sxs-lookup"><span data-stu-id="3260c-103">ResourceTest method</span></span>

<span data-ttu-id="3260c-104">Chama diretamente o método **Test** de um recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="3260c-104">Directly calls the **Test** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="3260c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3260c-105">Syntax</span></span>

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

## <a name="parameters"></a><span data-ttu-id="3260c-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3260c-106">Parameters</span></span>

<span data-ttu-id="3260c-107">**ResourceType** \[in\] O nome do recurso a chamar.</span><span class="sxs-lookup"><span data-stu-id="3260c-107">**ResourceType** \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="3260c-108">**ModuleName** \[in\] O nome do módulo que contém o recurso a chamar.</span><span class="sxs-lookup"><span data-stu-id="3260c-108">**ModuleName** \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="3260c-109">\**_resourceProperty_* \[in\] Especifica o nome da propriedade do recurso e o respectivo valor em uma tabela de hash como chave e valor, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="3260c-109">\**_resourceProperty_* \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="3260c-110">Use o cmdlet [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) para descobrir as propriedades de recurso e seus tipos.</span><span class="sxs-lookup"><span data-stu-id="3260c-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="3260c-111">*InDesiredState*\* \[out\] No retorno, essa propriedade será definida como **true** se o nó de destino estiver no estado desejado.</span><span class="sxs-lookup"><span data-stu-id="3260c-111">*InDesiredState*\* \[out\] On return, this property is set to **true** if the target node is in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="3260c-112">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="3260c-112">Return value</span></span>

<span data-ttu-id="3260c-113">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="3260c-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="3260c-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="3260c-114">Remarks</span></span>

<span data-ttu-id="3260c-115">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="3260c-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3260c-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3260c-116">Requirements</span></span>

<span data-ttu-id="3260c-117">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="3260c-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="3260c-118">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="3260c-118">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="3260c-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="3260c-119">See also</span></span>

[<span data-ttu-id="3260c-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="3260c-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
