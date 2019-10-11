---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método SendConfiguration
ms.openlocfilehash: 4feba090bc58844659c2329a304dd9805255564f
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953383"
---
# <a name="sendconfiguration-method"></a><span data-ttu-id="e6259-103">Método SendConfiguration</span><span class="sxs-lookup"><span data-stu-id="e6259-103">SendConfiguration method</span></span>

<span data-ttu-id="e6259-104">Envia o documento de configuração para o nó gerenciado e o salva como alteração pendente.</span><span class="sxs-lookup"><span data-stu-id="e6259-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6259-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e6259-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="e6259-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e6259-106">Parameters</span></span>

<span data-ttu-id="e6259-107">*ConfigurationData* \[in\] Dados de ambiente da configuração.</span><span class="sxs-lookup"><span data-stu-id="e6259-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="e6259-108">*force* \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="e6259-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="e6259-109">Retornar valor</span><span class="sxs-lookup"><span data-stu-id="e6259-109">Return value</span></span>

<span data-ttu-id="e6259-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="e6259-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="e6259-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="e6259-111">Remarks</span></span>

<span data-ttu-id="e6259-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="e6259-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e6259-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6259-113">Requirements</span></span>

<span data-ttu-id="e6259-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="e6259-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="e6259-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="e6259-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="e6259-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e6259-116">See also</span></span>

[<span data-ttu-id="e6259-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="e6259-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
