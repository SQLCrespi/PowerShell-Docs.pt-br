---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método RollBack
ms.openlocfilehash: 301b8926d2ebf1ebe524f52a67928d34e26d860e
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464325"
---
# <a name="rollback-method"></a><span data-ttu-id="24127-103">Método RollBack</span><span class="sxs-lookup"><span data-stu-id="24127-103">RollBack method</span></span>

<span data-ttu-id="24127-104">Reverte a configuração a uma versão anterior.</span><span class="sxs-lookup"><span data-stu-id="24127-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="24127-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="24127-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="24127-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="24127-106">Parameters</span></span>

<span data-ttu-id="24127-107">**configurationNumber** \[in\] Especifica a configuração solicitada.</span><span class="sxs-lookup"><span data-stu-id="24127-107">**configurationNumber** \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="24127-108">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="24127-108">Return value</span></span>

<span data-ttu-id="24127-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="24127-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="24127-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="24127-110">Remarks</span></span>

<span data-ttu-id="24127-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="24127-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="24127-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24127-112">Requirements</span></span>

<span data-ttu-id="24127-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="24127-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="24127-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="24127-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="24127-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="24127-115">See also</span></span>

[<span data-ttu-id="24127-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="24127-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
