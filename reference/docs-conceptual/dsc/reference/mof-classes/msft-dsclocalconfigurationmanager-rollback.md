---
ms.date: 07/17/2020
ms.topic: reference
title: Método RollBack
description: Método RollBack
ms.openlocfilehash: 82ca54ed23a3a892b785f603be3b423def5ee636
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650630"
---
# <a name="rollback-method"></a><span data-ttu-id="211c3-103">Método RollBack</span><span class="sxs-lookup"><span data-stu-id="211c3-103">RollBack method</span></span>

<span data-ttu-id="211c3-104">Reverte a configuração a uma versão anterior.</span><span class="sxs-lookup"><span data-stu-id="211c3-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="211c3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="211c3-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="211c3-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="211c3-106">Parameters</span></span>

<span data-ttu-id="211c3-107">**configurationNumber** \[in\] Especifica a configuração solicitada.</span><span class="sxs-lookup"><span data-stu-id="211c3-107">**configurationNumber** \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="211c3-108">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="211c3-108">Return value</span></span>

<span data-ttu-id="211c3-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="211c3-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="211c3-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="211c3-110">Remarks</span></span>

<span data-ttu-id="211c3-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="211c3-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="211c3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="211c3-112">Requirements</span></span>

<span data-ttu-id="211c3-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="211c3-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="211c3-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="211c3-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="211c3-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="211c3-115">See also</span></span>

[<span data-ttu-id="211c3-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="211c3-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
