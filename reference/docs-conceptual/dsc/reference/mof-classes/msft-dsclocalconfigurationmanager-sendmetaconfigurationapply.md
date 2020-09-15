---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método SendMetaConfigurationApply
ms.openlocfilehash: 896afe2f3370e108b48583aafb33ee7b0eb1301b
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463713"
---
# <a name="sendmetaconfigurationapply-method"></a><span data-ttu-id="be262-103">Método SendMetaConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="be262-103">SendMetaConfigurationApply method</span></span>

<span data-ttu-id="be262-104">Define as configurações do Gerenciador de Configurações Local usadas para controlar o Agente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="be262-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="be262-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="be262-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="be262-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="be262-106">Parameters</span></span>

<span data-ttu-id="be262-107">**ConfigurationData** \[in\] Os dados de ambiente da configuração.</span><span class="sxs-lookup"><span data-stu-id="be262-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="be262-108">**force** \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="be262-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="be262-109">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="be262-109">Return value</span></span>

<span data-ttu-id="be262-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="be262-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="be262-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="be262-111">Remarks</span></span>

<span data-ttu-id="be262-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="be262-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="be262-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be262-113">Requirements</span></span>

<span data-ttu-id="be262-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="be262-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="be262-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="be262-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="be262-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="be262-116">See also</span></span>

[<span data-ttu-id="be262-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="be262-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
