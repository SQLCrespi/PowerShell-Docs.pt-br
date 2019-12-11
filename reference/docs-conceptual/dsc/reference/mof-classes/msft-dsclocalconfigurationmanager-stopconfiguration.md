---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método StopConfiguration
ms.openlocfilehash: e1de175032a3bddf11af218bc4a15bdbe554a9d5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953353"
---
# <a name="stopconfiguration-method"></a><span data-ttu-id="fce62-103">Método StopConfiguration</span><span class="sxs-lookup"><span data-stu-id="fce62-103">StopConfiguration method</span></span>

<span data-ttu-id="fce62-104">Interrompe a alteração da configuração em andamento.</span><span class="sxs-lookup"><span data-stu-id="fce62-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="fce62-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fce62-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="fce62-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="fce62-106">Parameters</span></span>

<span data-ttu-id="fce62-107">*force* \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="fce62-107">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="fce62-108">Retornar valor</span><span class="sxs-lookup"><span data-stu-id="fce62-108">Return value</span></span>

<span data-ttu-id="fce62-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="fce62-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="fce62-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="fce62-110">Remarks</span></span>

<span data-ttu-id="fce62-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="fce62-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="fce62-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fce62-112">Requirements</span></span>

<span data-ttu-id="fce62-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="fce62-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="fce62-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="fce62-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="fce62-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fce62-115">See also</span></span>

[<span data-ttu-id="fce62-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="fce62-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
