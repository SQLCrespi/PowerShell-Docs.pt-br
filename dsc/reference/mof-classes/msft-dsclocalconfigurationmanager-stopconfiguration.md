---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método StopConfiguration da classe MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 1cd887d205967c3d282143df4e6199027639230e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078225"
---
# <a name="stopconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="1dc66-103">Método StopConfiguration da classe MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="1dc66-103">StopConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="1dc66-104">Interrompe a alteração da configuração em andamento.</span><span class="sxs-lookup"><span data-stu-id="1dc66-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="1dc66-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1dc66-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="1dc66-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1dc66-106">Parameters</span></span>

<span data-ttu-id="1dc66-107">*force* \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="1dc66-107">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="1dc66-108">Retornar valor</span><span class="sxs-lookup"><span data-stu-id="1dc66-108">Return value</span></span>

<span data-ttu-id="1dc66-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="1dc66-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="1dc66-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="1dc66-110">Remarks</span></span>

<span data-ttu-id="1dc66-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="1dc66-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1dc66-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1dc66-112">Requirements</span></span>

<span data-ttu-id="1dc66-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="1dc66-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="1dc66-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="1dc66-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="1dc66-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1dc66-115">See also</span></span>

[<span data-ttu-id="1dc66-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="1dc66-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)