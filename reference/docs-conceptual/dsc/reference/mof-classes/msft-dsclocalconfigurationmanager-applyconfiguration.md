---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método ApplyConfiguration
ms.openlocfilehash: 0425b9a7db37e421830ba37da8f5c0a4877a1b72
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953453"
---
# <a name="applyconfiguration-method"></a><span data-ttu-id="e6c4b-103">Método ApplyConfiguration</span><span class="sxs-lookup"><span data-stu-id="e6c4b-103">ApplyConfiguration method</span></span>

<span data-ttu-id="e6c4b-104">Usa o Agente de Configuração para aplicar a configuração pendente.</span><span class="sxs-lookup"><span data-stu-id="e6c4b-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="e6c4b-105">Se não houver nenhuma configuração pendente, esse método reaplicará a configuração atual.</span><span class="sxs-lookup"><span data-stu-id="e6c4b-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6c4b-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e6c4b-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="e6c4b-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e6c4b-107">Parameters</span></span>

<span data-ttu-id="e6c4b-108">*force* \[in\] Se for **true**, a configuração atual será reaplicada, mesmo que haja uma configuração pendente.</span><span class="sxs-lookup"><span data-stu-id="e6c4b-108">*force* \[in\] If this is **true**, the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="e6c4b-109">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="e6c4b-109">Return value</span></span>

<span data-ttu-id="e6c4b-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="e6c4b-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="e6c4b-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="e6c4b-111">Remarks</span></span>

<span data-ttu-id="e6c4b-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="e6c4b-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e6c4b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6c4b-113">Requirements</span></span>

<span data-ttu-id="e6c4b-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="e6c4b-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="e6c4b-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="e6c4b-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="e6c4b-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="e6c4b-116">See also</span></span>

[<span data-ttu-id="e6c4b-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="e6c4b-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
