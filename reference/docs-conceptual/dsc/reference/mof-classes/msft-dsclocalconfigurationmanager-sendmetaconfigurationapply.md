---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método SendMetaConfigurationApply
ms.openlocfilehash: b2e420bafb8ea22aea43800f6e429d3ed785d1e8
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954873"
---
# <a name="sendmetaconfigurationapply-method"></a><span data-ttu-id="12f75-103">Método SendMetaConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="12f75-103">SendMetaConfigurationApply method</span></span>

<span data-ttu-id="12f75-104">Define as configurações do Gerenciador de Configurações Local usadas para controlar o Agente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="12f75-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="12f75-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="12f75-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="12f75-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="12f75-106">Parameters</span></span>

<span data-ttu-id="12f75-107">*ConfigurationData* \[in\] Dados de ambiente da configuração.</span><span class="sxs-lookup"><span data-stu-id="12f75-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="12f75-108">*force* \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="12f75-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="12f75-109">Retornar valor</span><span class="sxs-lookup"><span data-stu-id="12f75-109">Return value</span></span>

<span data-ttu-id="12f75-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="12f75-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="12f75-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="12f75-111">Remarks</span></span>

<span data-ttu-id="12f75-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="12f75-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="12f75-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="12f75-113">Requirements</span></span>

<span data-ttu-id="12f75-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="12f75-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="12f75-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="12f75-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="12f75-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="12f75-116">See also</span></span>

[<span data-ttu-id="12f75-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="12f75-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
