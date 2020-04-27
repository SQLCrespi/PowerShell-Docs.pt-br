---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método EnableDebugConfiguration
ms.openlocfilehash: f1290e4d898332361850ffc85aa0a8d79863c8f7
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953433"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="27690-103">Método EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="27690-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="27690-104">Habilita a depuração do recurso DSC.</span><span class="sxs-lookup"><span data-stu-id="27690-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="27690-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="27690-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="27690-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="27690-106">Parameters</span></span>

<span data-ttu-id="27690-107">*BreakAll* \[in\] Define um ponto de interrupção em cada linha do script de recurso.</span><span class="sxs-lookup"><span data-stu-id="27690-107">*BreakAll* \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="27690-108">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="27690-108">Return value</span></span>

<span data-ttu-id="27690-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="27690-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="27690-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="27690-110">Remarks</span></span>

<span data-ttu-id="27690-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="27690-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="27690-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27690-112">Requirements</span></span>

<span data-ttu-id="27690-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="27690-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="27690-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="27690-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="27690-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="27690-115">See also</span></span>

[<span data-ttu-id="27690-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="27690-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
