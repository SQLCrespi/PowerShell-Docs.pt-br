---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método RemoveConfiguration
ms.openlocfilehash: aacbed96beb960d7e0d449423a4de9a27f0a287e
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953393"
---
# <a name="removeconfiguration-method"></a><span data-ttu-id="0bff7-103">Método RemoveConfiguration</span><span class="sxs-lookup"><span data-stu-id="0bff7-103">RemoveConfiguration method</span></span>

<span data-ttu-id="0bff7-104">Remove os arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="0bff7-104">Removes the configuration files.</span></span>

## <a name="syntax"></a><span data-ttu-id="0bff7-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0bff7-105">Syntax</span></span>

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a><span data-ttu-id="0bff7-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0bff7-106">Parameters</span></span>

<span data-ttu-id="0bff7-107">*Stage* \[in\] Especifica qual documento de configuração deve ser removido.</span><span class="sxs-lookup"><span data-stu-id="0bff7-107">*Stage* \[in\] Specifies which configuration document to remove.</span></span> <span data-ttu-id="0bff7-108">Os seguintes valores são válidos:</span><span class="sxs-lookup"><span data-stu-id="0bff7-108">The following values are valid:</span></span>

|<span data-ttu-id="0bff7-109">Valor</span><span class="sxs-lookup"><span data-stu-id="0bff7-109">Value</span></span> |<span data-ttu-id="0bff7-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="0bff7-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="0bff7-111">**1**</span><span class="sxs-lookup"><span data-stu-id="0bff7-111">**1**</span></span> | <span data-ttu-id="0bff7-112">O documento de configuração **atual** (current.mof).</span><span class="sxs-lookup"><span data-stu-id="0bff7-112">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="0bff7-113">**2**</span><span class="sxs-lookup"><span data-stu-id="0bff7-113">**2**</span></span> | <span data-ttu-id="0bff7-114">O documento de configuração **Pendente** (current.mof).</span><span class="sxs-lookup"><span data-stu-id="0bff7-114">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="0bff7-115">**4**</span><span class="sxs-lookup"><span data-stu-id="0bff7-115">**4**</span></span> | <span data-ttu-id="0bff7-116">O documento de configuração **Anterior** (current.mof).</span><span class="sxs-lookup"><span data-stu-id="0bff7-116">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="0bff7-117">*Force* \[in\] **true** para forçar a remoção da configuração.</span><span class="sxs-lookup"><span data-stu-id="0bff7-117">*Force* \[in\] **true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="0bff7-118">Retornar valor</span><span class="sxs-lookup"><span data-stu-id="0bff7-118">Return value</span></span>

<span data-ttu-id="0bff7-119">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="0bff7-119">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="0bff7-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="0bff7-120">Remarks</span></span>

<span data-ttu-id="0bff7-121">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="0bff7-121">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="0bff7-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0bff7-122">Requirements</span></span>

<span data-ttu-id="0bff7-123">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="0bff7-123">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="0bff7-124">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="0bff7-124">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="0bff7-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0bff7-125">See also</span></span>

[<span data-ttu-id="0bff7-126">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="0bff7-126">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
