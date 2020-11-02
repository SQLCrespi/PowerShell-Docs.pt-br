---
ms.date: 07/17/2020
ms.topic: reference
title: Método EnableDebugConfiguration
description: Método EnableDebugConfiguration
ms.openlocfilehash: 536366e6e1627a249f3bc2dc19bfd8ff3de42117
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644774"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="8ddbb-103">Método EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ddbb-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="8ddbb-104">Habilita a depuração do recurso DSC.</span><span class="sxs-lookup"><span data-stu-id="8ddbb-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="8ddbb-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8ddbb-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="8ddbb-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8ddbb-106">Parameters</span></span>

<span data-ttu-id="8ddbb-107">**BreakAll** \[in\] Define um ponto de interrupção em cada linha do script de recurso.</span><span class="sxs-lookup"><span data-stu-id="8ddbb-107">**BreakAll** \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="8ddbb-108">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="8ddbb-108">Return value</span></span>

<span data-ttu-id="8ddbb-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="8ddbb-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ddbb-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="8ddbb-110">Remarks</span></span>

<span data-ttu-id="8ddbb-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="8ddbb-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8ddbb-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ddbb-112">Requirements</span></span>

<span data-ttu-id="8ddbb-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="8ddbb-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="8ddbb-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ddbb-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="8ddbb-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="8ddbb-115">See also</span></span>

[<span data-ttu-id="8ddbb-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="8ddbb-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
