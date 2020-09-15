---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método SendConfigurationApplyAsync
ms.openlocfilehash: 4cfac5edb5fed94ee69deb98d7aa6be56b51c5b3
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463730"
---
# <a name="sendconfigurationapplyasync-method"></a><span data-ttu-id="03ff9-103">Método SendConfigurationApplyAsync</span><span class="sxs-lookup"><span data-stu-id="03ff9-103">SendConfigurationApplyAsync method</span></span>

<span data-ttu-id="03ff9-104">Envia o documento de configuração de maneira assíncrona para o nó gerenciado e usa o Agente de Configuração para aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="03ff9-104">Sends the configuration document asynchronously to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="03ff9-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="03ff9-105">Syntax</span></span>

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

## <a name="parameters"></a><span data-ttu-id="03ff9-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="03ff9-106">Parameters</span></span>

<span data-ttu-id="03ff9-107">**ConfigurationData** \[in\] Os dados de ambiente da configuração.</span><span class="sxs-lookup"><span data-stu-id="03ff9-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="03ff9-108">**force** \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="03ff9-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

<span data-ttu-id="03ff9-109">**jobId** \[in\] A ID do trabalho para a qual enviar a configuração.</span><span class="sxs-lookup"><span data-stu-id="03ff9-109">**jobId** \[in\] The ID of the job for which to send the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="03ff9-110">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="03ff9-110">Return value</span></span>

<span data-ttu-id="03ff9-111">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="03ff9-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="03ff9-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="03ff9-112">Remarks</span></span>

<span data-ttu-id="03ff9-113">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="03ff9-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="03ff9-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03ff9-114">Requirements</span></span>

<span data-ttu-id="03ff9-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="03ff9-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="03ff9-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="03ff9-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="03ff9-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="03ff9-117">See also</span></span>

[<span data-ttu-id="03ff9-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="03ff9-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
