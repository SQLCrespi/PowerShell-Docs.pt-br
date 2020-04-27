---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método SendConfiguration
ms.openlocfilehash: 4feba090bc58844659c2329a304dd9805255564f
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953383"
---
# <a name="sendconfiguration-method"></a><span data-ttu-id="cacdc-103">Método SendConfiguration</span><span class="sxs-lookup"><span data-stu-id="cacdc-103">SendConfiguration method</span></span>

<span data-ttu-id="cacdc-104">Envia o documento de configuração para o nó gerenciado e o salva como alteração pendente.</span><span class="sxs-lookup"><span data-stu-id="cacdc-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="cacdc-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cacdc-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="cacdc-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="cacdc-106">Parameters</span></span>

<span data-ttu-id="cacdc-107">*ConfigurationData* \[in\] Os dados de ambiente da configuração.</span><span class="sxs-lookup"><span data-stu-id="cacdc-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="cacdc-108">*force* \[in\] **true** para forçar a configuração a parar.</span><span class="sxs-lookup"><span data-stu-id="cacdc-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="cacdc-109">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="cacdc-109">Return value</span></span>

<span data-ttu-id="cacdc-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="cacdc-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="cacdc-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="cacdc-111">Remarks</span></span>

<span data-ttu-id="cacdc-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="cacdc-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="cacdc-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cacdc-113">Requirements</span></span>

<span data-ttu-id="cacdc-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="cacdc-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="cacdc-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="cacdc-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="cacdc-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="cacdc-116">See also</span></span>

[<span data-ttu-id="cacdc-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="cacdc-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
