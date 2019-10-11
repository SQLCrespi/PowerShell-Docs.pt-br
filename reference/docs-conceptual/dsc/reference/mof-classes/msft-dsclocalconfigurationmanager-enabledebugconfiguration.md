---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método EnableDebugConfiguration
ms.openlocfilehash: f1290e4d898332361850ffc85aa0a8d79863c8f7
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953433"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="98bb3-103">Método EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="98bb3-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="98bb3-104">Habilita a depuração do recurso DSC.</span><span class="sxs-lookup"><span data-stu-id="98bb3-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="98bb3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="98bb3-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="98bb3-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="98bb3-106">Parameters</span></span>

<span data-ttu-id="98bb3-107">*BreakAll* \[in\] Define um ponto de interrupção em cada linha do script de recurso.</span><span class="sxs-lookup"><span data-stu-id="98bb3-107">*BreakAll* \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="98bb3-108">Retornar valor</span><span class="sxs-lookup"><span data-stu-id="98bb3-108">Return value</span></span>

<span data-ttu-id="98bb3-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="98bb3-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="98bb3-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="98bb3-110">Remarks</span></span>

<span data-ttu-id="98bb3-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="98bb3-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="98bb3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98bb3-112">Requirements</span></span>

<span data-ttu-id="98bb3-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="98bb3-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="98bb3-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="98bb3-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="98bb3-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="98bb3-115">See also</span></span>

[<span data-ttu-id="98bb3-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="98bb3-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
