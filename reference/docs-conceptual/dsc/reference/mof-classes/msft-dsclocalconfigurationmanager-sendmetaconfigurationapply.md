---
ms.date: 07/17/2020
ms.topic: reference
title: Método SendMetaConfigurationApply
description: Método SendMetaConfigurationApply
ms.openlocfilehash: 27c58819c0249ace011c475e500e565e5daed9bb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648955"
---
# <a name="sendmetaconfigurationapply-method"></a><span data-ttu-id="0c7d4-103">Método SendMetaConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="0c7d4-103">SendMetaConfigurationApply method</span></span>

<span data-ttu-id="0c7d4-104">Define as configurações do Gerenciador de Configurações Local usadas para controlar o Agente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="0c7d4-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="0c7d4-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0c7d4-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="0c7d4-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0c7d4-106">Parameters</span></span>

<span data-ttu-id="0c7d4-107">**ConfigurationData** \[in\] Os dados de ambiente da configuração.</span><span class="sxs-lookup"><span data-stu-id="0c7d4-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="0c7d4-108">**force** \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="0c7d4-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="0c7d4-109">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="0c7d4-109">Return value</span></span>

<span data-ttu-id="0c7d4-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="0c7d4-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="0c7d4-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="0c7d4-111">Remarks</span></span>

<span data-ttu-id="0c7d4-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="0c7d4-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="0c7d4-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c7d4-113">Requirements</span></span>

<span data-ttu-id="0c7d4-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="0c7d4-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="0c7d4-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="0c7d4-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="0c7d4-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="0c7d4-116">See also</span></span>

[<span data-ttu-id="0c7d4-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="0c7d4-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
