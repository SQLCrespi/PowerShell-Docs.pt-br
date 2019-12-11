---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método RollBack
ms.openlocfilehash: 6452bdffd5160d9956576fb59c98e2f9ff7ddbbb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954933"
---
# <a name="rollback-method"></a><span data-ttu-id="a2485-103">Método RollBack</span><span class="sxs-lookup"><span data-stu-id="a2485-103">RollBack method</span></span>

<span data-ttu-id="a2485-104">Reverte a configuração a uma versão anterior.</span><span class="sxs-lookup"><span data-stu-id="a2485-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2485-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a2485-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="a2485-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a2485-106">Parameters</span></span>

<span data-ttu-id="a2485-107">*configurationNumber* \[in\] Especifica a configuração solicitada.</span><span class="sxs-lookup"><span data-stu-id="a2485-107">*configurationNumber* \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="a2485-108">Retornar valor</span><span class="sxs-lookup"><span data-stu-id="a2485-108">Return value</span></span>

<span data-ttu-id="a2485-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="a2485-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2485-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="a2485-110">Remarks</span></span>

<span data-ttu-id="a2485-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="a2485-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a2485-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2485-112">Requirements</span></span>

<span data-ttu-id="a2485-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="a2485-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="a2485-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="a2485-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="a2485-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a2485-115">See also</span></span>

[<span data-ttu-id="a2485-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="a2485-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
