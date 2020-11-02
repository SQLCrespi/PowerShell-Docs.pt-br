---
ms.date: 07/17/2020
ms.topic: reference
title: Método SendConfigurationApply
description: Método SendConfigurationApply
ms.openlocfilehash: 9bd63220644e096b348f71ee9d4ac216af6a7ccc
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648967"
---
# <a name="sendconfigurationapply-method"></a><span data-ttu-id="faa8d-103">Método SendConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="faa8d-103">SendConfigurationApply method</span></span>

<span data-ttu-id="faa8d-104">Envia o documento de configuração para o nó gerenciado e usa o Agente de Configuração para aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="faa8d-104">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="faa8d-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="faa8d-105">Syntax</span></span>

```mof
uint32 SendConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="faa8d-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="faa8d-106">Parameters</span></span>

<span data-ttu-id="faa8d-107">**ConfigurationData** \[in\] Os dados de ambiente da configuração.</span><span class="sxs-lookup"><span data-stu-id="faa8d-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="faa8d-108">**force** \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="faa8d-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="faa8d-109">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="faa8d-109">Return value</span></span>

<span data-ttu-id="faa8d-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="faa8d-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="faa8d-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="faa8d-111">Remarks</span></span>

<span data-ttu-id="faa8d-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="faa8d-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="faa8d-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="faa8d-113">Requirements</span></span>

<span data-ttu-id="faa8d-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="faa8d-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="faa8d-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="faa8d-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="faa8d-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="faa8d-116">See also</span></span>

[<span data-ttu-id="faa8d-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="faa8d-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
