---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método SendConfiguration
ms.openlocfilehash: 4feba090bc58844659c2329a304dd9805255564f
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734316"
---
# <a name="sendconfiguration-method"></a><span data-ttu-id="52b1a-103">Método SendConfiguration</span><span class="sxs-lookup"><span data-stu-id="52b1a-103">SendConfiguration method</span></span>

<span data-ttu-id="52b1a-104">Envia o documento de configuração para o nó gerenciado e o salva como alteração pendente.</span><span class="sxs-lookup"><span data-stu-id="52b1a-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="52b1a-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="52b1a-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="52b1a-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="52b1a-106">Parameters</span></span>

<span data-ttu-id="52b1a-107">*ConfigurationData* \[in\] Dados de ambiente da configuração.</span><span class="sxs-lookup"><span data-stu-id="52b1a-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="52b1a-108">*force* \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="52b1a-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="52b1a-109">Retornar valor</span><span class="sxs-lookup"><span data-stu-id="52b1a-109">Return value</span></span>

<span data-ttu-id="52b1a-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="52b1a-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="52b1a-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="52b1a-111">Remarks</span></span>

<span data-ttu-id="52b1a-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="52b1a-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="52b1a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52b1a-113">Requirements</span></span>

<span data-ttu-id="52b1a-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="52b1a-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="52b1a-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="52b1a-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="52b1a-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="52b1a-116">See also</span></span>

[<span data-ttu-id="52b1a-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="52b1a-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
