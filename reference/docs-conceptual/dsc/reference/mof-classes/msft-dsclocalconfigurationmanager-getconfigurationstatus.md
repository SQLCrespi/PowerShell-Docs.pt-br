---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método GetConfigurationStatus
ms.openlocfilehash: c2c478151428052d656832fb4079f12d666a910d
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464036"
---
# <a name="getconfigurationstatus-method"></a><span data-ttu-id="657b4-103">Método GetConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="657b4-103">GetConfigurationStatus method</span></span>

<span data-ttu-id="657b4-104">Obtém o histórico do status de configuração.</span><span class="sxs-lookup"><span data-stu-id="657b4-104">Get the configuration status history.</span></span>

## <a name="syntax"></a><span data-ttu-id="657b4-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="657b4-105">Syntax</span></span>

```mof
uint32 GetConfigurationStatus(
  [in]  boolean                     All,
  [out] MSFT_DSCConfigurationStatus configurationStatus[]
);
```

## <a name="parameters"></a><span data-ttu-id="657b4-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="657b4-106">Parameters</span></span>

<span data-ttu-id="657b4-107">**All** \[in\] **true** caso esse método deva retornar informações sobre todas as configurações executadas no computador, incluindo o aplicativo de configuração e a verificação de consistência.</span><span class="sxs-lookup"><span data-stu-id="657b4-107">**All** \[in\] **true** if this method should return information about all the configuration runs on the machine, including the configuration application and the consistency check.</span></span>

<span data-ttu-id="657b4-108">**configurationStatus** \[out\] No retorno, contém uma instância inserida da classe **MSFT_DSCConfigurationStatus** que define as configurações.</span><span class="sxs-lookup"><span data-stu-id="657b4-108">**configurationStatus** \[out\] On return, contains an embedded instance of the **MSFT_DSCConfigurationStatus** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="657b4-109">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="657b4-109">Return value</span></span>

<span data-ttu-id="657b4-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="657b4-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="657b4-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="657b4-111">Remarks</span></span>

<span data-ttu-id="657b4-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="657b4-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="657b4-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="657b4-113">Requirements</span></span>

<span data-ttu-id="657b4-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="657b4-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="657b4-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="657b4-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="657b4-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="657b4-116">See also</span></span>

[<span data-ttu-id="657b4-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="657b4-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
