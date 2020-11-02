---
ms.date: 07/14/2020
ms.topic: reference
title: Método ApplyConfiguration
description: Método ApplyConfiguration
ms.openlocfilehash: aa99221b33d39c3ecc70156a11eaee10b540e2dc
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664281"
---
# <a name="applyconfiguration-method"></a><span data-ttu-id="1a547-103">Método ApplyConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a547-103">ApplyConfiguration method</span></span>

<span data-ttu-id="1a547-104">Usa o Agente de Configuração para aplicar a configuração pendente.</span><span class="sxs-lookup"><span data-stu-id="1a547-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="1a547-105">Se não houver nenhuma configuração pendente, esse método reaplicará a configuração atual.</span><span class="sxs-lookup"><span data-stu-id="1a547-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="1a547-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1a547-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="1a547-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1a547-107">Parameters</span></span>

### <a name="force"></a><span data-ttu-id="1a547-108">force</span><span class="sxs-lookup"><span data-stu-id="1a547-108">force</span></span>

<span data-ttu-id="1a547-109">Se isso for **true** , a configuração atual é reaplicada, mesmo que haja uma configuração pendente.</span><span class="sxs-lookup"><span data-stu-id="1a547-109">If this is **true** , the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="1a547-110">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="1a547-110">Return value</span></span>

<span data-ttu-id="1a547-111">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="1a547-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="1a547-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="1a547-112">Remarks</span></span>

<span data-ttu-id="1a547-113">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="1a547-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1a547-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1a547-114">Requirements</span></span>

<span data-ttu-id="1a547-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="1a547-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="1a547-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a547-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="1a547-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="1a547-117">See also</span></span>

[<span data-ttu-id="1a547-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="1a547-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
