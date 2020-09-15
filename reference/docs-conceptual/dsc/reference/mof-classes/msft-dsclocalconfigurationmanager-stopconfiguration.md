---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método StopConfiguration
ms.openlocfilehash: 76e50c98b09dca86983320918c6899082580672a
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463696"
---
# <a name="stopconfiguration-method"></a><span data-ttu-id="b4927-103">Método StopConfiguration</span><span class="sxs-lookup"><span data-stu-id="b4927-103">StopConfiguration method</span></span>

<span data-ttu-id="b4927-104">Interrompe a alteração da configuração em andamento.</span><span class="sxs-lookup"><span data-stu-id="b4927-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="b4927-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b4927-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="b4927-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b4927-106">Parameters</span></span>

<span data-ttu-id="b4927-107">**force** \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="b4927-107">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="b4927-108">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="b4927-108">Return value</span></span>

<span data-ttu-id="b4927-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="b4927-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4927-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="b4927-110">Remarks</span></span>

<span data-ttu-id="b4927-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="b4927-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b4927-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4927-112">Requirements</span></span>

<span data-ttu-id="b4927-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="b4927-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="b4927-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="b4927-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="b4927-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="b4927-115">See also</span></span>

[<span data-ttu-id="b4927-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="b4927-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
