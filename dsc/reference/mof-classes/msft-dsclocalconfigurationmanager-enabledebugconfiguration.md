---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método EnableDebugConfiguration
ms.openlocfilehash: f1290e4d898332361850ffc85aa0a8d79863c8f7
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67727137"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="b4571-103">Método EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="b4571-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="b4571-104">Habilita a depuração do recurso DSC.</span><span class="sxs-lookup"><span data-stu-id="b4571-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="b4571-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b4571-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="b4571-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b4571-106">Parameters</span></span>

<span data-ttu-id="b4571-107">*BreakAll* \[in\] Define um ponto de interrupção em cada linha do script de recurso.</span><span class="sxs-lookup"><span data-stu-id="b4571-107">*BreakAll* \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="b4571-108">Retornar valor</span><span class="sxs-lookup"><span data-stu-id="b4571-108">Return value</span></span>

<span data-ttu-id="b4571-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="b4571-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4571-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="b4571-110">Remarks</span></span>

<span data-ttu-id="b4571-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="b4571-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b4571-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4571-112">Requirements</span></span>

<span data-ttu-id="b4571-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="b4571-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="b4571-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="b4571-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="b4571-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b4571-115">See also</span></span>

[<span data-ttu-id="b4571-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="b4571-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
