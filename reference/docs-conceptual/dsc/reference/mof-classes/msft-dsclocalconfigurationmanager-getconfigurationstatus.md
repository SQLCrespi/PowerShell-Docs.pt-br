---
ms.date: 07/17/2020
ms.topic: reference
title: Método GetConfigurationStatus
description: Método GetConfigurationStatus
ms.openlocfilehash: fe25d17069d9011e931ac50fec27cb9ebafba365
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650865"
---
# <a name="getconfigurationstatus-method"></a><span data-ttu-id="99ffe-103">Método GetConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="99ffe-103">GetConfigurationStatus method</span></span>

<span data-ttu-id="99ffe-104">Obtém o histórico do status de configuração.</span><span class="sxs-lookup"><span data-stu-id="99ffe-104">Get the configuration status history.</span></span>

## <a name="syntax"></a><span data-ttu-id="99ffe-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="99ffe-105">Syntax</span></span>

```mof
uint32 GetConfigurationStatus(
  [in]  boolean                     All,
  [out] MSFT_DSCConfigurationStatus configurationStatus[]
);
```

## <a name="parameters"></a><span data-ttu-id="99ffe-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="99ffe-106">Parameters</span></span>

<span data-ttu-id="99ffe-107">**All** \[in\] **true** caso esse método deva retornar informações sobre todas as configurações executadas no computador, incluindo o aplicativo de configuração e a verificação de consistência.</span><span class="sxs-lookup"><span data-stu-id="99ffe-107">**All** \[in\] **true** if this method should return information about all the configuration runs on the machine, including the configuration application and the consistency check.</span></span>

<span data-ttu-id="99ffe-108">**configurationStatus** \[out\] No retorno, contém uma instância inserida da classe **MSFT_DSCConfigurationStatus** que define as configurações.</span><span class="sxs-lookup"><span data-stu-id="99ffe-108">**configurationStatus** \[out\] On return, contains an embedded instance of the **MSFT_DSCConfigurationStatus** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="99ffe-109">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="99ffe-109">Return value</span></span>

<span data-ttu-id="99ffe-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="99ffe-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="99ffe-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="99ffe-111">Remarks</span></span>

<span data-ttu-id="99ffe-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="99ffe-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="99ffe-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99ffe-113">Requirements</span></span>

<span data-ttu-id="99ffe-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="99ffe-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="99ffe-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="99ffe-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="99ffe-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="99ffe-116">See also</span></span>

[<span data-ttu-id="99ffe-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="99ffe-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
