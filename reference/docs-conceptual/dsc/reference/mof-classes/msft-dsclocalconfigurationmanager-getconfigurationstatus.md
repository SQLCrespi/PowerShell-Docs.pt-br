---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método GetConfigurationStatus
ms.openlocfilehash: 83b30ba2612d962fcf2fa658d07d18fb2d91ccc7
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71955013"
---
# <a name="getconfigurationstatus-method"></a><span data-ttu-id="611d6-103">Método GetConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="611d6-103">GetConfigurationStatus method</span></span>

<span data-ttu-id="611d6-104">Obtém o histórico do status de configuração.</span><span class="sxs-lookup"><span data-stu-id="611d6-104">Get the configuration status history.</span></span>

## <a name="syntax"></a><span data-ttu-id="611d6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="611d6-105">Syntax</span></span>

```mof
uint32 GetConfigurationStatus(
  [in]  boolean                     All,
  [out] MSFT_DSCConfigurationStatus configurationStatus[]
);
```

## <a name="parameters"></a><span data-ttu-id="611d6-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="611d6-106">Parameters</span></span>

<span data-ttu-id="611d6-107">*All* \[in\] **true** caso esse método deva retornar informações sobre todas as configurações executadas no computador, incluindo o aplicativo de configuração e a verificação de consistência.</span><span class="sxs-lookup"><span data-stu-id="611d6-107">*All* \[in\] **true** if this method should return information about all the configuration runs on the machine, including the configuration application and the consistency check.</span></span>

<span data-ttu-id="611d6-108">*configurationStatus* \[out\] No retorno, contém uma instância inserida da classe **MSFT_DSCConfigurationStatus** que define as configurações.</span><span class="sxs-lookup"><span data-stu-id="611d6-108">*configurationStatus* \[out\] On return, contains an embedded instance of the **MSFT_DSCConfigurationStatus** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="611d6-109">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="611d6-109">Return value</span></span>

<span data-ttu-id="611d6-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="611d6-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="611d6-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="611d6-111">Remarks</span></span>

<span data-ttu-id="611d6-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="611d6-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="611d6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="611d6-113">Requirements</span></span>

<span data-ttu-id="611d6-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="611d6-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="611d6-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="611d6-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="611d6-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="611d6-116">See also</span></span>

[<span data-ttu-id="611d6-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="611d6-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
