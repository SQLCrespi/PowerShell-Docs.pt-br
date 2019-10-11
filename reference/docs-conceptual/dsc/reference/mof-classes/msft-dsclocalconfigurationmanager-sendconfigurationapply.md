---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método SendConfigurationApply
ms.openlocfilehash: 11b9d435bbaac1600d25ff074b6c55b236a8378b
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954883"
---
# <a name="sendconfigurationapply-method"></a><span data-ttu-id="dbbda-103">Método SendConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="dbbda-103">SendConfigurationApply method</span></span>

<span data-ttu-id="dbbda-104">Envia o documento de configuração para o nó gerenciado e usa o Agente de Configuração para aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="dbbda-104">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="dbbda-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dbbda-105">Syntax</span></span>

```mof
uint32 SendConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="dbbda-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="dbbda-106">Parameters</span></span>

<span data-ttu-id="dbbda-107">*ConfigurationData* \[in\] Dados de ambiente da configuração.</span><span class="sxs-lookup"><span data-stu-id="dbbda-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="dbbda-108">*force* \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="dbbda-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="dbbda-109">Retornar valor</span><span class="sxs-lookup"><span data-stu-id="dbbda-109">Return value</span></span>

<span data-ttu-id="dbbda-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="dbbda-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="dbbda-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="dbbda-111">Remarks</span></span>

<span data-ttu-id="dbbda-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="dbbda-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="dbbda-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dbbda-113">Requirements</span></span>

<span data-ttu-id="dbbda-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="dbbda-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="dbbda-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="dbbda-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="dbbda-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="dbbda-116">See also</span></span>

[<span data-ttu-id="dbbda-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="dbbda-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
