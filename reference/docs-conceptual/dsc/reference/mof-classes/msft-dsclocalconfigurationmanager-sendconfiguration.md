---
ms.date: 07/17/2020
ms.topic: reference
title: Método SendConfiguration
description: Método SendConfiguration
ms.openlocfilehash: 3939a76ab6672b49559847b0ef1408f1c7be6d0c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650562"
---
# <a name="sendconfiguration-method"></a><span data-ttu-id="5e7ff-103">Método SendConfiguration</span><span class="sxs-lookup"><span data-stu-id="5e7ff-103">SendConfiguration method</span></span>

<span data-ttu-id="5e7ff-104">Envia o documento de configuração para o nó gerenciado e o salva como alteração pendente.</span><span class="sxs-lookup"><span data-stu-id="5e7ff-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="5e7ff-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5e7ff-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="5e7ff-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5e7ff-106">Parameters</span></span>

<span data-ttu-id="5e7ff-107">**ConfigurationData** \[in\] Os dados de ambiente da configuração.</span><span class="sxs-lookup"><span data-stu-id="5e7ff-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="5e7ff-108">**force** \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="5e7ff-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="5e7ff-109">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="5e7ff-109">Return value</span></span>

<span data-ttu-id="5e7ff-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="5e7ff-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="5e7ff-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="5e7ff-111">Remarks</span></span>

<span data-ttu-id="5e7ff-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="5e7ff-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5e7ff-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e7ff-113">Requirements</span></span>

<span data-ttu-id="5e7ff-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="5e7ff-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="5e7ff-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="5e7ff-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="5e7ff-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="5e7ff-116">See also</span></span>

[<span data-ttu-id="5e7ff-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="5e7ff-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
