---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método SendMetaConfigurationApply
ms.openlocfilehash: b2e420bafb8ea22aea43800f6e429d3ed785d1e8
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954873"
---
# <a name="sendmetaconfigurationapply-method"></a><span data-ttu-id="8e37c-103">Método SendMetaConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="8e37c-103">SendMetaConfigurationApply method</span></span>

<span data-ttu-id="8e37c-104">Define as configurações do Gerenciador de Configurações Local usadas para controlar o Agente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="8e37c-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="8e37c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8e37c-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="8e37c-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8e37c-106">Parameters</span></span>

<span data-ttu-id="8e37c-107">*ConfigurationData* \[in\] Os dados de ambiente da configuração.</span><span class="sxs-lookup"><span data-stu-id="8e37c-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="8e37c-108">*force* \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="8e37c-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="8e37c-109">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="8e37c-109">Return value</span></span>

<span data-ttu-id="8e37c-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="8e37c-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="8e37c-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="8e37c-111">Remarks</span></span>

<span data-ttu-id="8e37c-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="8e37c-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8e37c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e37c-113">Requirements</span></span>

<span data-ttu-id="8e37c-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="8e37c-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="8e37c-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="8e37c-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="8e37c-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="8e37c-116">See also</span></span>

[<span data-ttu-id="8e37c-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="8e37c-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
