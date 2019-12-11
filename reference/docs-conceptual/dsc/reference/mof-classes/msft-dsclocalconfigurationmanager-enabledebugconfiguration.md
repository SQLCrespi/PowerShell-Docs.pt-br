---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método EnableDebugConfiguration
ms.openlocfilehash: f1290e4d898332361850ffc85aa0a8d79863c8f7
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953433"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="45b16-103">Método EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="45b16-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="45b16-104">Habilita a depuração do recurso DSC.</span><span class="sxs-lookup"><span data-stu-id="45b16-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="45b16-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="45b16-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="45b16-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="45b16-106">Parameters</span></span>

<span data-ttu-id="45b16-107">*BreakAll* \[in\] Define um ponto de interrupção em cada linha do script de recurso.</span><span class="sxs-lookup"><span data-stu-id="45b16-107">*BreakAll* \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="45b16-108">Retornar valor</span><span class="sxs-lookup"><span data-stu-id="45b16-108">Return value</span></span>

<span data-ttu-id="45b16-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="45b16-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="45b16-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="45b16-110">Remarks</span></span>

<span data-ttu-id="45b16-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="45b16-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="45b16-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45b16-112">Requirements</span></span>

<span data-ttu-id="45b16-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="45b16-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="45b16-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="45b16-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="45b16-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="45b16-115">See also</span></span>

[<span data-ttu-id="45b16-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="45b16-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
