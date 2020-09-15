---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método SendConfigurationApply
ms.openlocfilehash: 9b684790e5a7d6c7bdf074caca6040e13807f1ca
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464308"
---
# <a name="sendconfigurationapply-method"></a><span data-ttu-id="42b49-103">Método SendConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="42b49-103">SendConfigurationApply method</span></span>

<span data-ttu-id="42b49-104">Envia o documento de configuração para o nó gerenciado e usa o Agente de Configuração para aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="42b49-104">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="42b49-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="42b49-105">Syntax</span></span>

```mof
uint32 SendConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="42b49-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="42b49-106">Parameters</span></span>

<span data-ttu-id="42b49-107">**ConfigurationData** \[in\] Os dados de ambiente da configuração.</span><span class="sxs-lookup"><span data-stu-id="42b49-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="42b49-108">**force** \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="42b49-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="42b49-109">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="42b49-109">Return value</span></span>

<span data-ttu-id="42b49-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="42b49-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="42b49-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="42b49-111">Remarks</span></span>

<span data-ttu-id="42b49-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="42b49-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="42b49-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42b49-113">Requirements</span></span>

<span data-ttu-id="42b49-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="42b49-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="42b49-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="42b49-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="42b49-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="42b49-116">See also</span></span>

[<span data-ttu-id="42b49-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="42b49-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
