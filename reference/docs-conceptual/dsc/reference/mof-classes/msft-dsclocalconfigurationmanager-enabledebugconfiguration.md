---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método EnableDebugConfiguration
ms.openlocfilehash: be75b1012f49db79eb75a68c6912ffd5772bf16f
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464087"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="db1e9-103">Método EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="db1e9-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="db1e9-104">Habilita a depuração do recurso DSC.</span><span class="sxs-lookup"><span data-stu-id="db1e9-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="db1e9-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="db1e9-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="db1e9-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="db1e9-106">Parameters</span></span>

<span data-ttu-id="db1e9-107">**BreakAll** \[in\] Define um ponto de interrupção em cada linha do script de recurso.</span><span class="sxs-lookup"><span data-stu-id="db1e9-107">**BreakAll** \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="db1e9-108">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="db1e9-108">Return value</span></span>

<span data-ttu-id="db1e9-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="db1e9-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="db1e9-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="db1e9-110">Remarks</span></span>

<span data-ttu-id="db1e9-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="db1e9-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="db1e9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db1e9-112">Requirements</span></span>

<span data-ttu-id="db1e9-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="db1e9-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="db1e9-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="db1e9-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="db1e9-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="db1e9-115">See also</span></span>

[<span data-ttu-id="db1e9-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="db1e9-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
