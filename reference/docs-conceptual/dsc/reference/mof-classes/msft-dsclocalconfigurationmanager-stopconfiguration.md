---
ms.date: 07/17/2020
ms.topic: reference
title: Método StopConfiguration
description: Método StopConfiguration
ms.openlocfilehash: 854c0dbe8554c08413735a5a7bc872776e0b0a6c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644615"
---
# <a name="stopconfiguration-method"></a><span data-ttu-id="7ac69-103">Método StopConfiguration</span><span class="sxs-lookup"><span data-stu-id="7ac69-103">StopConfiguration method</span></span>

<span data-ttu-id="7ac69-104">Interrompe a alteração da configuração em andamento.</span><span class="sxs-lookup"><span data-stu-id="7ac69-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="7ac69-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7ac69-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="7ac69-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7ac69-106">Parameters</span></span>

<span data-ttu-id="7ac69-107">**force** \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="7ac69-107">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="7ac69-108">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="7ac69-108">Return value</span></span>

<span data-ttu-id="7ac69-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="7ac69-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ac69-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="7ac69-110">Remarks</span></span>

<span data-ttu-id="7ac69-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="7ac69-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="7ac69-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ac69-112">Requirements</span></span>

<span data-ttu-id="7ac69-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="7ac69-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="7ac69-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="7ac69-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="7ac69-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="7ac69-115">See also</span></span>

[<span data-ttu-id="7ac69-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="7ac69-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
